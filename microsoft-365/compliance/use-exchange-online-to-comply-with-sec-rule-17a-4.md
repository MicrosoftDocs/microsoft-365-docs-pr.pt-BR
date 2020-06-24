---
title: Usar o Exchange Online e o Centro de Conformidade e Segurança para atender à norma 17a-4 da SEC
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Configurar o Exchange Online e Centro de conformidade para ajudar a cumprir os requisitos regulatórios da Regra CFTC 1.31 (c)-(d), da Regra 4511 e da Regra 17a-4 da SEC.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6dc53ec9dd016a2423ca96886bba400e2f17e17a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819071"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="dd925-103">Usar o Exchange Online e o Centro de Conformidade e Segurança para atender à norma 17a-4 da SEC</span><span class="sxs-lookup"><span data-stu-id="dd925-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="dd925-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="dd925-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="dd925-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd925-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="dd925-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="dd925-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="dd925-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="dd925-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="dd925-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="dd925-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="dd925-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="dd925-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="dd925-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="dd925-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="dd925-111">Para ajudar essas organizações a entender melhor como aproveitar o Centro de Conformidade e Segurança para atender às obrigações regulamentares do Exchange Online, especificamente em relação aos requisitos da norma 17a-4, lançamos uma avaliação em parceria com a Cohasset Associates.</span><span class="sxs-lookup"><span data-stu-id="dd925-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="dd925-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="dd925-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="dd925-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="dd925-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="dd925-114">Baixar a avaliação da Cohasset</span><span class="sxs-lookup"><span data-stu-id="dd925-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="dd925-115">[Baixe a avaliação da Cohasset aqui](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span><span class="sxs-lookup"><span data-stu-id="dd925-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Página de título da avaliação baixável da Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="dd925-117">Esta avaliação foi feita especificamente para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd925-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="dd925-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd925-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="dd925-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="dd925-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="dd925-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd925-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="dd925-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="dd925-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="dd925-122">O uso do Bloqueio de Preservação é fundamental para a configuração recomendada</span><span class="sxs-lookup"><span data-stu-id="dd925-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="dd925-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="dd925-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="dd925-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="dd925-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="dd925-125">Retido por um período de retenção obrigatório, que não pode ser reduzido, mas apenas aumentado.</span><span class="sxs-lookup"><span data-stu-id="dd925-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="dd925-126">Imutável, o que significa que não é possível substituir, apagar ou alterar o registro durante o período de retenção obrigatório.</span><span class="sxs-lookup"><span data-stu-id="dd925-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="dd925-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="dd925-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="dd925-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="dd925-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="dd925-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="dd925-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="dd925-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="dd925-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="dd925-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="dd925-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="dd925-132">O período de retenção da política pode apenas ser aumentado, mas não reduzido.</span><span class="sxs-lookup"><span data-stu-id="dd925-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="dd925-133">É possível adicionar usuários à política, mas não é possível removê-los.</span><span class="sxs-lookup"><span data-stu-id="dd925-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="dd925-134">A política de retenção não pode ser excluída por um administrador.</span><span class="sxs-lookup"><span data-stu-id="dd925-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="dd925-135">O Bloqueio de Preservação pode ajudar na conformidade com os requisitos regulamentares da norma 17a-4 da SEC.</span><span class="sxs-lookup"><span data-stu-id="dd925-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="dd925-136">Como configurar o Bloqueio de Preservação</span><span class="sxs-lookup"><span data-stu-id="dd925-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="dd925-137">Você pode bloquear uma política de retenção usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd925-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="dd925-138">Para obter mais informações, consulte [Use o Bloqueio de preservação para cumprir os requisitos regulamentares](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span><span class="sxs-lookup"><span data-stu-id="dd925-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dd925-139">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="dd925-139">Known limitations</span></span>

<span data-ttu-id="dd925-140">No momento, há algumas limitações no Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="dd925-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="dd925-141">As comunicações encadeadas não estão disponíveis para mensagens de canal e chat do Teams.</span><span class="sxs-lookup"><span data-stu-id="dd925-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="dd925-142">As curtidas não são retidas para mensagens de canal e chat do Teams.</span><span class="sxs-lookup"><span data-stu-id="dd925-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="dd925-143">A auditoria no nível do item já está disponível para as caixas de correio de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dd925-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="dd925-144">Para saber mais, consulte [Gerenciar a auditoria da caixa de correio](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="dd925-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
