---
title: Procurar ameaças em dispositivos, emails, aplicativos e identidades com busca avançada
description: Estudo cenários comuns de busca e consultas de exemplo que abrangem dispositivos, emails, aplicativos e identidades.
keywords: busca avançada, dados do Office365, dispositivos Windows, emails do Office365 normalizam, emails, aplicativos, identidades, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, Microsoft 365, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8a811d60af281bb534776736e77c3eb54ab6a760
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932960"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Buscar ameaças em dispositivos, e-mails, aplicativos e identidades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[A busca](advanced-hunting-overview.md) avançada no Microsoft 365 Defender permite que você cace proativamente ameaças em:
- Dispositivos gerenciados pelo Microsoft Defender para Ponto de Extremidade
- Emails processados por Microsoft 365
- Atividades de aplicativo na nuvem, eventos de autenticação e atividades de controlador de domínio controladas pelo Microsoft Cloud App Security e o Microsoft Defender for Identity

Com esse nível de visibilidade, você pode procurar rapidamente por ameaças que atravessam seções da sua rede, incluindo invasões sofisticadas que chegam ao email ou à Web, elevam privilégios locais, adquirem credenciais de domínio privilegiado e se movem lateralmente para seus dispositivos. 

Aqui estão técnicas gerais e consultas de exemplo com base em vários cenários de busca que podem ajudá-lo a explorar como você pode construir consultas ao procurar ameaças tão sofisticadas.

## <a name="get-entity-info"></a>Obter informações de entidade
Use essas consultas para saber como obter informações rapidamente sobre contas de usuário, dispositivos e arquivos. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Adicionar contas de usuário a partir de endereços de email
Ao criar consultas em [tabelas que abrangem dispositivos e emails](advanced-hunting-schema-tables.md), provavelmente será necessário obter nomes de contas de usuário dos endereços de email de remetentes ou destinatários. Geralmente, você pode fazer isso para destinatário ou endereço de remetente usando *o host local* do endereço de email.

No trecho abaixo, usamos a função [kusto tostring()](/azure/data-explorer/kusto/query/tostringfunction) para extrair o host local logo antes dos endereços de email do destinatário `@` na coluna `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
A consulta a seguir mostra como esse trecho pode ser usado:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Mesclar a tabela IdentityInfo

Você pode obter nomes de conta e outras informações de conta mesclando ou in juntando-se à [tabela IdentityInfo](advanced-hunting-identityinfo-table.md). A consulta a seguir obtém a lista de detecções de phishing e malware da tabela [EmailEvents](advanced-hunting-emailevents-table.md) e, em seguida, instala essas informações com a tabela para obter informações detalhadas sobre cada `IdentityInfo` destinatário. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Obter informações do dispositivo
O [esquema de busca avançado fornece](advanced-hunting-schema-tables.md) informações abrangentes do dispositivo em várias tabelas. Por exemplo, a tabela [DeviceInfo fornece](advanced-hunting-deviceinfo-table.md) informações abrangentes do dispositivo com base nos dados de evento agregados regularmente. Essa consulta usa a tabela para verificar se um usuário potencialmente comprometido ( ) fez logon em qualquer dispositivo e lista os alertas que foram `DeviceInfo` `<account-name>` disparados nesses dispositivos.

>[!Tip]
> Essa consulta usa para especificar uma junção interna , o que impede `kind=inner` a deduplicação de [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)valores do lado esquerdo para `DeviceId` .

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a>Cenários de busca

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Listar atividades de logon de usuários que receberam emails que não foram destruídos com êxito
[O ZAP (limpeza automática](../office-365-security/zero-hour-auto-purge.md) de hora zero) aborda emails mal-intencionados depois que eles são recebidos. Se o ZAP falhar, o código mal-intencionado poderá ser executado no dispositivo e deixar contas comprometidas. Essa consulta verifica se há atividade de logon feita pelos destinatários de emails que não foram abordados com êxito pela ZAP.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a>Obter tentativas de logon por contas de domínio direcionadas por roubo de credenciais
Essa consulta identifica primeiro todos os alertas de acesso de credenciais na `AlertInfo` tabela. Em seguida, mescla ou ingressa na tabela, que é analisado apenas para os nomes das contas direcionadas e filtros para contas `AlertEvidence` ingressadas no domínio. Por fim, ele verifica `IdentityLogonEvents` a tabela para obter todas as atividades de logon pelas contas direcionadas ingressadas no domínio.

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Verificar se os arquivos de um remetente mal-intencionado conhecido estão nos seus dispositivos
Supondo que você saiba de um endereço de email enviando arquivos mal-intencionados ( ), você pode executar essa consulta para determinar se os arquivos desse remetente `MaliciousSender@example.com` existem em seus dispositivos. Você pode usar essa consulta, por exemplo, para identificar dispositivos afetados por uma campanha de distribuição de malware.

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Analisar as tentativas de logon após o recebimento de emails mal-intencionados
Essa consulta localiza os 10 logons mais recentes executados pelos destinatários de email em 30 minutos depois do recebimento de emails mal-intencionados conhecidos. Você pode usar essa consulta para verificar se as contas dos destinatários de email foram comprometidas.

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Analisar as atividades do PowerShell após o recebimento de emails mal-intencionados de remetentes conhecidos
Os emails mal-intencionados geralmente contêm documentos e outros anexos especialmente criados que executam comandos do PowerShell para fornecer cargas adicionais. Se você estiver ciente dos emails provenientes de um remetente mal-intencionado conhecido ( ), poderá usar essa consulta para listar e revisar as atividades do PowerShell que ocorreram dentro de 30 minutos depois que um email foi recebido do `MaliciousSender@example.com` remetente.  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Entender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)