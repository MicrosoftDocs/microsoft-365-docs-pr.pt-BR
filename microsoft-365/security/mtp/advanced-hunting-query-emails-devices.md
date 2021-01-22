---
title: Busca por ameaças em dispositivos, emails, aplicativos e identidades com busca avançada
description: Estudo de cenários comuns de busca e consultas de exemplo que abrangem dispositivos, emails, aplicativos e identidades.
keywords: busca avançada, dados do Office365, dispositivos Windows, normalização de emails do Office365, emails, aplicativos, identidades, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, Microsoft 365, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b408f574ab4b89806be9154394f49c00a7fd1e99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932245"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Busca por ameaças em dispositivos, emails, aplicativos e identidades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[A busca](advanced-hunting-overview.md) avançada no Microsoft 365 Defender permite que você busca proativamente por ameaças em:
- Dispositivos gerenciados pelo Microsoft Defender para Ponto de Extremidade
- Emails processados pelo Microsoft 365
- Atividades do aplicativo na nuvem, eventos de autenticação e atividades do controlador de domínio controladas pelo Microsoft Cloud App Security e pelo Microsoft Defender for Identity

Com esse nível de visibilidade, você pode rapidamente procurar por ameaças que atravessam seções da sua rede, incluindo invasões sofisticadas que chegam ao email ou na Web, elevam os privilégios locais, adquirem credenciais de domínio privilegiado e se movem lateralmente para seus dispositivos. 

Aqui estão técnicas gerais e consultas de exemplo com base em vários cenários de busca que podem ajudá-lo a explorar como você pode construir consultas ao procurar ameaças sofisticadas.

## <a name="get-entity-info"></a>Obter informações de entidade
Use essas consultas para saber como você pode obter rapidamente informações sobre contas de usuário, dispositivos e arquivos. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Adicionar contas de usuário a partir de endereços de email
Ao criar consultas em [tabelas que abrangem dispositivos e emails](advanced-hunting-schema-tables.md), provavelmente será necessário obter nomes de contas de usuário dos endereços de email de remetentes ou destinatários. Geralmente, você pode fazer isso para o destinatário ou o endereço do remetente usando *o host local* do endereço de email.

No trecho abaixo, usamos a função [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto para extrair o host local imediatamente antes dos endereços de email do destinatário `@` na `RecipientEmailAddress` coluna.

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
A consulta abaixo mostra como esse trecho de código pode ser usado:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Mesclar a tabela IdentityInfo

Você pode obter nomes de conta e outras informações de conta mesclando ou inando na [tabela IdentityInfo.](advanced-hunting-identityinfo-table.md) A consulta abaixo obtém a lista de detecções de phishing e malware da tabela [EmailEvents](advanced-hunting-emailevents-table.md) e, em seguida, adiciona essas informações à tabela para obter informações detalhadas sobre cada `IdentityInfo` destinatário. 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where MalwareFilterVerdict == 'Malware' or PhishFilterVerdict == 'Phish'
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, PhishFilterVerdict, MalwareFilterVerdict,
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a>Obter informações do dispositivo
O [esquema de busca avançada fornece](advanced-hunting-schema-tables.md) extensas informações do dispositivo em várias tabelas. Por exemplo, a [tabela DeviceInfo fornece](advanced-hunting-deviceinfo-table.md) informações abrangentes do dispositivo com base nos dados de eventos agregados regularmente. Essa consulta usa a tabela para verificar se um usuário potencialmente comprometido ( ) fez logon em qualquer dispositivo e lista os alertas que foram `DeviceInfo` `<account-name>` disparados nesses dispositivos.

>[!Tip]
> This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId` .

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

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Listar atividades de logon de usuários que receberam emails que não foram recebidos com êxito
[A ZAP (Limpeza Automática Zero Hora)](../office-365-security/zero-hour-auto-purge.md) resolve emails mal-intencionados depois que eles são recebidos. Se a ZAP falhar, um código mal-intencionado pode acabar sendo executado no dispositivo e deixar contas comprometidas. Essa consulta verifica a atividade de logon feita pelos destinatários de emails que não foram abordados com êxito pela ZAP.

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
Esta consulta identifica primeiro todos os alertas de acesso de credenciais na `AlertInfo` tabela. Em seguida, ele mescla ou ingressa na tabela, que ela analisará para os nomes das contas direcionadas e filtros somente para contas `AlertEvidence` ingressadas no domínio. Por fim, ele verifica a tabela para obter todas `IdentityLogonEvents` as atividades de logon das contas direcionadas ingressadas no domínio.

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
| where MalwareFilterVerdict == "Malware"
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
Os emails mal-intencionados geralmente contêm documentos e outros anexos especialmente criados que executam comandos do PowerShell para fornecer cargas adicionais. Se você estiver ciente de emails provenientes de um remetente mal-intencionado conhecido ( ), você pode usar essa consulta para listar e revisar as atividades do PowerShell que ocorreram dentro de 30 minutos depois que um email foi recebido do `MaliciousSender@example.com` remetente.  

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
