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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6c758c05a64cd7ce84a2b021fe32f9e5ce5c1090
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48431058"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="29ded-104">Busca de ameaças em dispositivos, emails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="29ded-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="29ded-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="29ded-105">**Applies to:**</span></span>
- <span data-ttu-id="29ded-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="29ded-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="29ded-107">A [busca avançada](advanced-hunting-overview.md) na proteção contra ameaças da Microsoft permite que você entre em busca de ameaças de forma proativa:</span><span class="sxs-lookup"><span data-stu-id="29ded-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="29ded-108">Dispositivos gerenciados pelo Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="29ded-108">Devices managed by Microsoft Defender ATP</span></span>
- <span data-ttu-id="29ded-109">Emails processados pelo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="29ded-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="29ded-110">Atividades de aplicativo em nuvem, eventos de autenticação e atividades de controlador de domínio rastreadas pelo Microsoft Cloud app Security e pelo Azure ATP</span><span class="sxs-lookup"><span data-stu-id="29ded-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Azure ATP</span></span>

<span data-ttu-id="29ded-111">Com esse nível de visibilidade, você pode rapidamente procurar ameaças que atravessam as seções de sua rede, incluindo intrusões sofisticadas que chegam ao email ou à Web, elevam privilégios locais, adquirem credenciais de domínio privilegiadas e se movem mais tarde para todos os seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29ded-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="29ded-112">Aqui estão as técnicas gerais e as consultas de exemplo com base em vários cenários de busca que podem ajudá-lo a explorar o modo como você pode construir consultas ao buscar essas ameaças sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="29ded-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="29ded-113">Obter informações de entidade</span><span class="sxs-lookup"><span data-stu-id="29ded-113">Get entity info</span></span>
<span data-ttu-id="29ded-114">Use estas consultas para saber como você pode obter informações rapidamente sobre contas de usuário, dispositivos e arquivos.</span><span class="sxs-lookup"><span data-stu-id="29ded-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="29ded-115">Adicionar contas de usuário a partir de endereços de email</span><span class="sxs-lookup"><span data-stu-id="29ded-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="29ded-116">Ao criar consultas em [tabelas que abrangem dispositivos e emails](advanced-hunting-schema-tables.md), provavelmente será necessário obter nomes de contas de usuário dos endereços de email de remetentes ou destinatários.</span><span class="sxs-lookup"><span data-stu-id="29ded-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="29ded-117">Em geral, você pode fazer isso para o endereço do remetente ou destinatário usando o *host local* do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="29ded-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="29ded-118">No trecho de código abaixo, usamos a função [ToString ()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto para extrair o local do host local antes do `@` endereço de email do destinatário na coluna `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="29ded-118">In the snippet below, we use the [tostring()](https://docs.microsoft.com/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="29ded-119">A consulta abaixo mostra como este trecho de código pode ser usado:</span><span class="sxs-lookup"><span data-stu-id="29ded-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="29ded-120">Mesclar a tabela IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="29ded-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="29ded-121">Você pode obter nomes de conta e outras informações de conta mesclando ou unindo a [tabela IdentityInfo](advanced-hunting-identityinfo-table.md).</span><span class="sxs-lookup"><span data-stu-id="29ded-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="29ded-122">A consulta a seguir obtém a lista de detecções de phishing e malware da [tabela EmailEvents](advanced-hunting-emailevents-table.md) e une essas informações com a `IdentityInfo` tabela para obter informações detalhadas sobre cada destinatário.</span><span class="sxs-lookup"><span data-stu-id="29ded-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="29ded-123">Obter informações sobre o dispositivo</span><span class="sxs-lookup"><span data-stu-id="29ded-123">Get device information</span></span>
<span data-ttu-id="29ded-124">O [esquema de busca avançada](advanced-hunting-schema-tables.md) fornece informações de dispositivo abrangentes em várias tabelas.</span><span class="sxs-lookup"><span data-stu-id="29ded-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="29ded-125">Por exemplo, a [tabela DeviceInfo](advanced-hunting-deviceinfo-table.md) fornece informações abrangentes de dispositivo com base em dados de eventos agregados regularmente.</span><span class="sxs-lookup"><span data-stu-id="29ded-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="29ded-126">Esta consulta usa a `DeviceInfo` tabela para verificar se um usuário potencialmente comprometido ( `<account-name>` ) fez logon em qualquer dispositivo e, em seguida, lista os alertas que foram disparados nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29ded-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="29ded-127">Esta consulta usa `kind=inner` para especificar uma [junção interna](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), o que impede a eliminação de duplicação de valores do lado esquerdo `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="29ded-127">This query uses `kind=inner` to specify an [inner-join](https://docs.microsoft.com/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="29ded-128">Cenários de busca</span><span class="sxs-lookup"><span data-stu-id="29ded-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="29ded-129">Listar atividades de logon de usuários que receberam emails que não foram zapped com êxito</span><span class="sxs-lookup"><span data-stu-id="29ded-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="29ded-130">[A limpeza automática de zero horas (zap)](../office-365-security/zero-hour-auto-purge.md) endereça emails mal-intencionados após serem recebidos.</span><span class="sxs-lookup"><span data-stu-id="29ded-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="29ded-131">Se o ZAP falhar, o código mal-intencionado poderá ser executado no dispositivo e deixar as contas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="29ded-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="29ded-132">Esta consulta verifica a atividade de logon feita pelos destinatários de emails que não foram tratados com êxito por ZAP.</span><span class="sxs-lookup"><span data-stu-id="29ded-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="29ded-133">Obter tentativas de logon por contas de domínio direcionadas por roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="29ded-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="29ded-134">Essa consulta primeiro identifica todos os alertas de acesso de credenciais na `AlertInfo` tabela.</span><span class="sxs-lookup"><span data-stu-id="29ded-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="29ded-135">Em seguida, ele mescla ou une a `AlertEvidence` tabela, que ela analisa para os nomes das contas e filtros direcionados apenas para contas unidas por domínio.</span><span class="sxs-lookup"><span data-stu-id="29ded-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="29ded-136">Por fim, ele verifica a `IdentityLogonEvents` tabela para obter todas as atividades de logon pelas contas direcionadas que ingressaram no domínio.</span><span class="sxs-lookup"><span data-stu-id="29ded-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="29ded-137">Verificar se os arquivos de um remetente mal-intencionado conhecido estão nos seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="29ded-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="29ded-138">Supondo que você conhece um endereço de email enviando arquivos mal-intencionados ( `MaliciousSender@example.com` ), você pode executar essa consulta para determinar se os arquivos desse remetente existem em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="29ded-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="29ded-139">Você pode usar essa consulta, por exemplo, para identificar dispositivos afetados por uma campanha de distribuição de malware.</span><span class="sxs-lookup"><span data-stu-id="29ded-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="29ded-140">Analisar as tentativas de logon após o recebimento de emails mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="29ded-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="29ded-141">Essa consulta localiza os 10 logons mais recentes executados pelos destinatários de email em 30 minutos depois do recebimento de emails mal-intencionados conhecidos.</span><span class="sxs-lookup"><span data-stu-id="29ded-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="29ded-142">Você pode usar essa consulta para verificar se as contas dos destinatários de email foram comprometidas.</span><span class="sxs-lookup"><span data-stu-id="29ded-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="29ded-143">Analisar as atividades do PowerShell após o recebimento de emails mal-intencionados de remetentes conhecidos</span><span class="sxs-lookup"><span data-stu-id="29ded-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="29ded-144">Os emails mal-intencionados geralmente contêm documentos e outros anexos especialmente criados que executam comandos do PowerShell para fornecer cargas adicionais.</span><span class="sxs-lookup"><span data-stu-id="29ded-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="29ded-145">Se você estiver ciente de emails provenientes de um remetente mal-intencionado conhecido ( `MaliciousSender@example.com` ), poderá usar essa consulta para listar e revisar as atividades do PowerShell que ocorreram em 30 minutos após o recebimento de um email do remetente.</span><span class="sxs-lookup"><span data-stu-id="29ded-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="29ded-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="29ded-146">Related topics</span></span>
- [<span data-ttu-id="29ded-147">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="29ded-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="29ded-148">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="29ded-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="29ded-149">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="29ded-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="29ded-150">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="29ded-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="29ded-151">Entender o esquema</span><span class="sxs-lookup"><span data-stu-id="29ded-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="29ded-152">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="29ded-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
