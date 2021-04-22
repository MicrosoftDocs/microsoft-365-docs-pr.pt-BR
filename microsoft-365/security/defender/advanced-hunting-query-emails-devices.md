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
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="721cf-104">Buscar ameaças em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="721cf-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="721cf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="721cf-105">**Applies to:**</span></span>
- <span data-ttu-id="721cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="721cf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="721cf-107">[A busca avançada](advanced-hunting-overview.md) no Microsoft 365 Defender permite que você cace proativamente ameaças em:</span><span class="sxs-lookup"><span data-stu-id="721cf-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="721cf-108">Dispositivos gerenciados pelo Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="721cf-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="721cf-109">Emails processados pelo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="721cf-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="721cf-110">Atividades de aplicativo na nuvem, eventos de autenticação e atividades de controlador de domínio controladas pelo Microsoft Cloud App Security e pelo Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="721cf-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="721cf-111">Com esse nível de visibilidade, você pode procurar rapidamente por ameaças que atravessam seções da sua rede, incluindo invasões sofisticadas que chegam ao email ou à Web, elevam privilégios locais, adquirem credenciais de domínio privilegiado e se movem lateralmente para seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="721cf-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="721cf-112">Aqui estão técnicas gerais e consultas de exemplo com base em vários cenários de busca que podem ajudá-lo a explorar como você pode construir consultas ao procurar ameaças tão sofisticadas.</span><span class="sxs-lookup"><span data-stu-id="721cf-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="721cf-113">Obter informações de entidade</span><span class="sxs-lookup"><span data-stu-id="721cf-113">Get entity info</span></span>
<span data-ttu-id="721cf-114">Use essas consultas para saber como obter informações rapidamente sobre contas de usuário, dispositivos e arquivos.</span><span class="sxs-lookup"><span data-stu-id="721cf-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="721cf-115">Adicionar contas de usuário a partir de endereços de email</span><span class="sxs-lookup"><span data-stu-id="721cf-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="721cf-116">Ao criar consultas em [tabelas que abrangem dispositivos e emails](advanced-hunting-schema-tables.md), provavelmente será necessário obter nomes de contas de usuário dos endereços de email de remetentes ou destinatários.</span><span class="sxs-lookup"><span data-stu-id="721cf-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="721cf-117">Geralmente, você pode fazer isso para destinatário ou endereço de remetente usando *o host local* do endereço de email.</span><span class="sxs-lookup"><span data-stu-id="721cf-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="721cf-118">No trecho abaixo, usamos a função [kusto tostring()](/azure/data-explorer/kusto/query/tostringfunction) para extrair o host local logo antes dos endereços de email do destinatário `@` na coluna `RecipientEmailAddress` .</span><span class="sxs-lookup"><span data-stu-id="721cf-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="721cf-119">A consulta a seguir mostra como esse trecho pode ser usado:</span><span class="sxs-lookup"><span data-stu-id="721cf-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="721cf-120">Mesclar a tabela IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="721cf-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="721cf-121">Você pode obter nomes de conta e outras informações de conta mesclando ou in juntando-se à [tabela IdentityInfo](advanced-hunting-identityinfo-table.md).</span><span class="sxs-lookup"><span data-stu-id="721cf-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="721cf-122">A consulta a seguir obtém a lista de detecções de phishing e malware da tabela [EmailEvents](advanced-hunting-emailevents-table.md) e, em seguida, instala essas informações com a tabela para obter informações detalhadas sobre cada `IdentityInfo` destinatário.</span><span class="sxs-lookup"><span data-stu-id="721cf-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

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

### <a name="get-device-information"></a><span data-ttu-id="721cf-123">Obter informações do dispositivo</span><span class="sxs-lookup"><span data-stu-id="721cf-123">Get device information</span></span>
<span data-ttu-id="721cf-124">O [esquema de busca avançado fornece](advanced-hunting-schema-tables.md) informações abrangentes do dispositivo em várias tabelas.</span><span class="sxs-lookup"><span data-stu-id="721cf-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="721cf-125">Por exemplo, a tabela [DeviceInfo fornece](advanced-hunting-deviceinfo-table.md) informações abrangentes do dispositivo com base nos dados de evento agregados regularmente.</span><span class="sxs-lookup"><span data-stu-id="721cf-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="721cf-126">Essa consulta usa a tabela para verificar se um usuário potencialmente comprometido ( ) fez logon em qualquer dispositivo e lista os alertas que foram `DeviceInfo` `<account-name>` disparados nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="721cf-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="721cf-127">Essa consulta usa para especificar uma junção interna , o que impede `kind=inner` a deduplicação de [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor)valores do lado esquerdo para `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="721cf-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

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

## <a name="hunting-scenarios"></a><span data-ttu-id="721cf-128">Cenários de busca</span><span class="sxs-lookup"><span data-stu-id="721cf-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="721cf-129">Listar atividades de logon de usuários que receberam emails que não foram destruídos com êxito</span><span class="sxs-lookup"><span data-stu-id="721cf-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="721cf-130">[O ZAP (limpeza automática](../office-365-security/zero-hour-auto-purge.md) de hora zero) aborda emails mal-intencionados depois que eles são recebidos.</span><span class="sxs-lookup"><span data-stu-id="721cf-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="721cf-131">Se o ZAP falhar, o código mal-intencionado poderá ser executado no dispositivo e deixar contas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="721cf-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="721cf-132">Essa consulta verifica se há atividade de logon feita pelos destinatários de emails que não foram abordados com êxito pela ZAP.</span><span class="sxs-lookup"><span data-stu-id="721cf-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

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

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="721cf-133">Obter tentativas de logon por contas de domínio direcionadas por roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="721cf-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="721cf-134">Essa consulta identifica primeiro todos os alertas de acesso de credenciais na `AlertInfo` tabela.</span><span class="sxs-lookup"><span data-stu-id="721cf-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="721cf-135">Em seguida, mescla ou ingressa na tabela, que é analisado apenas para os nomes das contas direcionadas e filtros para contas `AlertEvidence` ingressadas no domínio.</span><span class="sxs-lookup"><span data-stu-id="721cf-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="721cf-136">Por fim, ele verifica `IdentityLogonEvents` a tabela para obter todas as atividades de logon pelas contas direcionadas ingressadas no domínio.</span><span class="sxs-lookup"><span data-stu-id="721cf-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

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

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="721cf-137">Verificar se os arquivos de um remetente mal-intencionado conhecido estão nos seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="721cf-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="721cf-138">Supondo que você saiba de um endereço de email enviando arquivos mal-intencionados ( ), você pode executar essa consulta para determinar se os arquivos desse remetente `MaliciousSender@example.com` existem em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="721cf-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="721cf-139">Você pode usar essa consulta, por exemplo, para identificar dispositivos afetados por uma campanha de distribuição de malware.</span><span class="sxs-lookup"><span data-stu-id="721cf-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

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

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="721cf-140">Analisar as tentativas de logon após o recebimento de emails mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="721cf-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="721cf-141">Essa consulta localiza os 10 logons mais recentes executados pelos destinatários de email em 30 minutos depois do recebimento de emails mal-intencionados conhecidos.</span><span class="sxs-lookup"><span data-stu-id="721cf-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="721cf-142">Você pode usar essa consulta para verificar se as contas dos destinatários de email foram comprometidas.</span><span class="sxs-lookup"><span data-stu-id="721cf-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

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

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="721cf-143">Analisar as atividades do PowerShell após o recebimento de emails mal-intencionados de remetentes conhecidos</span><span class="sxs-lookup"><span data-stu-id="721cf-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="721cf-144">Os emails mal-intencionados geralmente contêm documentos e outros anexos especialmente criados que executam comandos do PowerShell para fornecer cargas adicionais.</span><span class="sxs-lookup"><span data-stu-id="721cf-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="721cf-145">Se você estiver ciente dos emails provenientes de um remetente mal-intencionado conhecido ( ), poderá usar essa consulta para listar e revisar as atividades do PowerShell que ocorreram dentro de 30 minutos depois que um email foi recebido do `MaliciousSender@example.com` remetente.</span><span class="sxs-lookup"><span data-stu-id="721cf-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

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

## <a name="related-topics"></a><span data-ttu-id="721cf-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="721cf-146">Related topics</span></span>
- [<span data-ttu-id="721cf-147">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="721cf-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="721cf-148">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="721cf-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="721cf-149">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="721cf-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="721cf-150">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="721cf-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="721cf-151">Entender o esquema</span><span class="sxs-lookup"><span data-stu-id="721cf-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="721cf-152">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="721cf-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)