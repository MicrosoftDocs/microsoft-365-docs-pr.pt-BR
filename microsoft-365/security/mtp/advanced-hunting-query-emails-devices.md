---
title: Busca de ameaças entre dispositivos, emails, aplicativos e identidades com busca avançada
description: Estudar cenários comuns de busca e consultas de exemplo que cobrem dispositivos, emails, aplicativos e identidades.
keywords: busca avançada, dados do Office365, dispositivos do Windows, emails do Office365 normalizar, emails, aplicativos, identidades, busca de ameaças, busca de ameaças no cyber, pesquisa, consulta, telemetria, Microsoft 365, proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9f5468ccb853bbbe126198a14f7b824d953a2738
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412629"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a>Busca de ameaças em dispositivos, emails, aplicativos e identidades

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A [busca avançada](advanced-hunting-overview.md) na proteção contra ameaças da Microsoft permite que você entre em busca de ameaças de forma proativa:
- Dispositivos gerenciados pelo Microsoft defender ATP
- Emails processados pelo Microsoft 365
- Atividades de aplicativo em nuvem, eventos de autenticação e atividades de controlador de domínio rastreadas pelo Microsoft Cloud app Security e pelo Azure ATP

Com esse nível de visibilidade, você pode rapidamente procurar ameaças que atravessam as seções de sua rede, incluindo intrusões sofisticadas que chegam ao email ou à Web, elevam privilégios locais, adquirem credenciais de domínio privilegiadas e se movem mais tarde para todos os seus dispositivos. 

Aqui estão as técnicas gerais e as consultas de exemplo com base em vários cenários de busca que podem ajudá-lo a explorar o modo como você pode construir consultas ao buscar essas ameaças sofisticadas.

## <a name="get-entity-info"></a>Obter informações de entidade
Use estas consultas para saber como você pode obter informações rapidamente sobre contas de usuário, dispositivos e arquivos. 

### <a name="obtain-user-accounts-from-email-addresses"></a>Adicionar contas de usuário a partir de endereços de email
Ao criar consultas em [tabelas que abrangem dispositivos e emails](advanced-hunting-schema-tables.md), provavelmente será necessário obter nomes de contas de usuário dos endereços de email de remetentes ou destinatários. Em geral, você pode fazer isso para o endereço do remetente ou destinatário usando o *host local* do endereço de email.

No trecho de código abaixo, usamos a função [ToString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto para extrair o local do host local antes do `@` endereço de email do destinatário na coluna `RecipientEmailAddress` .

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
A consulta abaixo mostra como este trecho de código pode ser usado:

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a>Mesclar a tabela IdentityInfo

Você pode obter nomes de conta e outras informações de conta mesclando ou unindo a [tabela IdentityInfo](advanced-hunting-identityinfo-table.md). A consulta a seguir obtém a lista de detecções de phishing e malware da [tabela EmailEvents](advanced-hunting-emailevents-table.md) e une essas informações com a `IdentityInfo` tabela para obter informações detalhadas sobre cada destinatário. 

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

### <a name="get-device-information"></a>Obter informações sobre o dispositivo
O [esquema de busca avançada](advanced-hunting-schema-tables.md) fornece informações de dispositivo abrangentes em várias tabelas. Por exemplo, a [tabela DeviceInfo](advanced-hunting-deviceinfo-table.md) fornece informações abrangentes de dispositivo com base em dados de eventos agregados regularmente. Esta consulta usa a `DeviceInfo` tabela para verificar se um usuário potencialmente comprometido ( `<account-name>` ) fez logon em qualquer dispositivo e, em seguida, lista os alertas que foram disparados nesses dispositivos.

>[!Tip]
> Esta consulta usa `kind=inner` para especificar uma [junção interna](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), o que impede a eliminação de duplicação de valores do lado esquerdo `DeviceId` .

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

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a>Listar atividades de logon de usuários que receberam emails que não foram zapped com êxito
[A limpeza automática de zero horas (zap)](../office-365-security/zero-hour-auto-purge.md) endereça emails mal-intencionados após serem recebidos. Se o ZAP falhar, o código mal-intencionado poderá ser executado no dispositivo e deixar as contas comprometidas. Esta consulta verifica a atividade de logon feita pelos destinatários de emails que não foram tratados com êxito por ZAP.

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
Essa consulta primeiro identifica todos os alertas de acesso de credenciais na `AlertInfo` tabela. Em seguida, ele mescla ou une a `AlertEvidence` tabela, que ela analisa para os nomes das contas e filtros direcionados apenas para contas unidas por domínio. Por fim, ele verifica a `IdentityLogonEvents` tabela para obter todas as atividades de logon pelas contas direcionadas que ingressaram no domínio.

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
Supondo que você conhece um endereço de email enviando arquivos mal-intencionados ( `MaliciousSender@example.com` ), você pode executar essa consulta para determinar se os arquivos desse remetente existem em seus dispositivos. Você pode usar essa consulta, por exemplo, para identificar dispositivos afetados por uma campanha de distribuição de malware.

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
Os emails mal-intencionados geralmente contêm documentos e outros anexos especialmente criados que executam comandos do PowerShell para fornecer cargas adicionais. Se você estiver ciente de emails provenientes de um remetente mal-intencionado conhecido ( `MaliciousSender@example.com` ), poderá usar essa consulta para listar e revisar as atividades do PowerShell que ocorreram em 30 minutos após o recebimento de um email do remetente.  

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
