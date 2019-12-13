---
title: Encontrar ameaças em dispositivos e emails usando a busca avançada
description: Estude cenários comuns de busca e consultas de exemplo que abrangem dispositivos e emails.
keywords: busca avançada, dados do Office365, dispositivos Windows, normalização de emails do Office365, emails, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, Microsoft 365, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: b374aac84b309d18a88ee7248021b50a893e120c
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910695"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="73c80-104">Busca por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="73c80-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="73c80-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="73c80-105">**Applies to:**</span></span>
- <span data-ttu-id="73c80-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="73c80-106">Microsoft Threat Protection</span></span>

[!include[Prerelease information](prerelease.md)]

<span data-ttu-id="73c80-107">A [Busca avançada](advanced-hunting-overview.md) da Proteção contra Ameaças da Microsoft permite procurar proativamente por ameaças em dispositivos Windows e emails do Office 365.</span><span class="sxs-lookup"><span data-stu-id="73c80-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="73c80-108">Aqui estão alguns cenários de busca e exemplos de consultas que podem ajudá-lo a explorar como é possível criar consultas que abrangem dispositivos e emails.</span><span class="sxs-lookup"><span data-stu-id="73c80-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="73c80-109">Adicionar contas de usuário a partir de endereços de email</span><span class="sxs-lookup"><span data-stu-id="73c80-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="73c80-110">Ao criar consultas em [tabelas que abrangem dispositivos e emails](advanced-hunting-schema-tables.md), provavelmente será necessário obter nomes de contas de usuário dos endereços de email de remetentes ou destinatários.</span><span class="sxs-lookup"><span data-stu-id="73c80-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="73c80-111">Para fazer isso, use o *host local* no endereço de email:</span><span class="sxs-lookup"><span data-stu-id="73c80-111">To do this use the *local-host* from the email address:</span></span>

```
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="73c80-112">Essa técnica de normalização é usada nos seguintes cenários.</span><span class="sxs-lookup"><span data-stu-id="73c80-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="73c80-113">Cenários de busca</span><span class="sxs-lookup"><span data-stu-id="73c80-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="73c80-114">Verificar se os arquivos de um remetente mal-intencionado conhecido estão nos seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="73c80-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="73c80-115">Supondo que você saiba de um endereço de email que envia arquivos mal-intencionados, é possível executar essa consulta para determinar se os arquivos desse remetente existem nos seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73c80-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="73c80-116">Por exemplo, você pode usar essa consulta para determinar o número de dispositivos afetados por uma campanha de distribuição de malware.</span><span class="sxs-lookup"><span data-stu-id="73c80-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
FileCreationEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="73c80-117">Analisar as tentativas de logon após o recebimento de emails mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="73c80-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="73c80-118">Essa consulta localiza os 10 logons mais recentes executados pelos destinatários de email em 30 minutos depois do recebimento de emails mal-intencionados conhecidos.</span><span class="sxs-lookup"><span data-stu-id="73c80-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="73c80-119">Você pode usar essa consulta para verificar se as contas dos destinatários de email foram comprometidas.</span><span class="sxs-lookup"><span data-stu-id="73c80-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
LogonEvents
| project LogonTime = EventTime, AccountName, ComputerName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="73c80-120">Analisar as atividades do PowerShell após o recebimento de emails mal-intencionados de remetentes conhecidos</span><span class="sxs-lookup"><span data-stu-id="73c80-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="73c80-121">Os emails mal-intencionados geralmente contêm documentos e outros anexos especialmente criados que executam comandos do PowerShell para fornecer cargas adicionais.</span><span class="sxs-lookup"><span data-stu-id="73c80-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="73c80-122">Se você estiver ciente de emails recebidos de um remetente mal-intencionado conhecido, poderá usar essa consulta para listar e revisar as atividades do PowerShell que ocorreram dentro de 30 minutos após o recebimento de um email do remetente.</span><span class="sxs-lookup"><span data-stu-id="73c80-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = EventTime, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
ProcessCreationEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = EventTime, AccountName, ComputerName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="73c80-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="73c80-123">Related topics</span></span>
- [<span data-ttu-id="73c80-124">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="73c80-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="73c80-125">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="73c80-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="73c80-126">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="73c80-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="73c80-127">Entender o esquema</span><span class="sxs-lookup"><span data-stu-id="73c80-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="73c80-128">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="73c80-128">Apply query best practices</span></span>](advanced-hunting-best-practices.md)