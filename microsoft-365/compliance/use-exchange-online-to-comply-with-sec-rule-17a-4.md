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
ms.openlocfilehash: 769e13951ce15fb698131860fa78f25fa133e327
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127298"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="888e5-103">Usar o Exchange Online e o Centro de Conformidade e Segurança para atender à norma 17a-4 da SEC</span><span class="sxs-lookup"><span data-stu-id="888e5-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="888e5-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="888e5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="888e5-p101">Se sua organização precisa obedecer aos padrões regulamentares de retenção de dados, o Centro de conformidade e segurança fornecerá recursos para gerenciar o ciclo de vida dos seus dados no Exchange Online. Isso inclui a capacidade de reter, auditar, pesquisar e exportar seus dados. Esses recursos são suficientes para atender às necessidades da maioria das organizações.</span><span class="sxs-lookup"><span data-stu-id="888e5-p101">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online. This includes the ability to retain, audit, search, and export your data. These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="888e5-p102">No entanto, algumas organizações em setores altamente regulamentados estão sujeitas a requisitos regulamentares mais rigorosos. Por exemplo, instituições financeiras, como bancos ou corretoras, estão sujeitas à norma 17a-4 estabelecida pela SEC (Comissão de Títulos e Câmbio dos Estados Unidos). A norma 17a-4 tem requisitos específicos para armazenamento de dados eletrônicos, inclusive vários aspectos do gerenciamento de registros, como duração, formato, qualidade, disponibilidade e responsabilidade da retenção de registros.</span><span class="sxs-lookup"><span data-stu-id="888e5-p102">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements. For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC). Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="888e5-111">Para ajudar essas organizações a entender melhor como aproveitar o Centro de Conformidade e Segurança para atender às obrigações regulamentares do Exchange Online, especificamente em relação aos requisitos da norma 17a-4, lançamos uma avaliação em parceria com a Cohasset Associates.</span><span class="sxs-lookup"><span data-stu-id="888e5-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="888e5-p103">A Cohasset Associates comprovou que, quando o Exchange Online e o Centro de Conformidade e Segurança são configurados conforme recomendado, eles atendem aos requisitos de armazenamento relevantes das normas 1.31(c)-(d) da CFTC, 4511 da FINRA e 17a-4 da SEC. Visamos esse conjunto de normas porque elas representam a orientação mais normativa globalmente para retenção de registros por instituições financeiras.</span><span class="sxs-lookup"><span data-stu-id="888e5-p103">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4. We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="888e5-114">Baixar a avaliação da Cohasset</span><span class="sxs-lookup"><span data-stu-id="888e5-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="888e5-115">[Baixe a avaliação da Cohasset aqui](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span><span class="sxs-lookup"><span data-stu-id="888e5-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Página de título da avaliação baixável da Cohasset Associates](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="888e5-117">Esta avaliação foi feita especificamente para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="888e5-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="888e5-p104">Observe que esta avaliação é específica para o Exchange Online. A avaliação não inclui outros serviços do Microsoft 365, como o SharePoint Online ou o OneDrive for Business, embora planejemos suporte para esses serviços com relação à SEC 17a-4 no futuro.</span><span class="sxs-lookup"><span data-stu-id="888e5-p104">Note that this assessment is specific to Exchange Online. The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="888e5-p105">É importante entender que o Skype for Business e o Teams também armazenam dados no Exchange Online. Assim, a avaliação abrange mensagens do Skype for Business e mensagens de canal e bate-papo do Teams.</span><span class="sxs-lookup"><span data-stu-id="888e5-p105">It's important to understand that Skype for Business and Teams also store data in Exchange Online. Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="888e5-122">O uso do Bloqueio de Preservação é fundamental para a configuração recomendada</span><span class="sxs-lookup"><span data-stu-id="888e5-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="888e5-p106">Os setores altamente regulamentados são sempre obrigados a armazenar comunicações eletrônicas para atender ao requisito de WORM (gravar uma vez, ler muitas). Este requisito estabelece uma solução de armazenamento na qual um registro deve ser:</span><span class="sxs-lookup"><span data-stu-id="888e5-p106">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement. The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="888e5-125">Retido por um período de retenção obrigatório, que não pode ser reduzido, mas apenas aumentado.</span><span class="sxs-lookup"><span data-stu-id="888e5-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="888e5-126">Imutável, o que significa que não é possível substituir, apagar ou alterar o registro durante o período de retenção obrigatório.</span><span class="sxs-lookup"><span data-stu-id="888e5-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="888e5-p107">No Exchange Online, quando uma [política de retenção](retention.md) é aplicada à caixa de correio de um usuário, todo o conteúdo do usuário será retido com base nos critérios da política. De fato, se um usuário tentar excluir ou modificar um e-mail, uma cópia do e-mail antes que a alteração seja feita será preservada em um local seguro e oculto na caixa de correio do usuário. As políticas de retenção podem ajudar a garantir que uma organização retenha comunicações eletrônicas, mas essas políticas podem ser modificadas.</span><span class="sxs-lookup"><span data-stu-id="888e5-p107">In Exchange Online, when a [retention policy](retention.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy. In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox. Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="888e5-p108">Ao aplicar o Bloqueio de Preservação em uma política de retenção, a empresa garante que a política não seja modificada. De fato, após aplicar o Bloqueio de Preservação a uma política de retenção, as seguintes ações serão restritas:</span><span class="sxs-lookup"><span data-stu-id="888e5-p108">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified. In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="888e5-132">O período de retenção da política pode apenas ser aumentado, mas não reduzido.</span><span class="sxs-lookup"><span data-stu-id="888e5-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="888e5-133">É possível adicionar usuários à política, mas não é possível removê-los.</span><span class="sxs-lookup"><span data-stu-id="888e5-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="888e5-134">A política de retenção não pode ser excluída por um administrador.</span><span class="sxs-lookup"><span data-stu-id="888e5-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="888e5-135">O Bloqueio de Preservação pode ajudar na conformidade com os requisitos regulamentares da norma 17a-4 da SEC.</span><span class="sxs-lookup"><span data-stu-id="888e5-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="888e5-136">Como configurar o Bloqueio de Preservação</span><span class="sxs-lookup"><span data-stu-id="888e5-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="888e5-137">Você pode bloquear uma política de retenção usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="888e5-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="888e5-138">Para obter mais informações, consulte [Use o Bloqueio de preservação para cumprir os requisitos regulamentares](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span><span class="sxs-lookup"><span data-stu-id="888e5-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="888e5-139">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="888e5-139">Known limitations</span></span>

<span data-ttu-id="888e5-140">No momento, há algumas limitações no Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="888e5-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="888e5-141">As comunicações encadeadas não estão disponíveis para mensagens de canal e chat do Teams.</span><span class="sxs-lookup"><span data-stu-id="888e5-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="888e5-142">As curtidas não são retidas para mensagens de canal e chat do Teams.</span><span class="sxs-lookup"><span data-stu-id="888e5-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="888e5-143">A auditoria no nível do item já está disponível para as caixas de correio de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="888e5-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="888e5-144">Para saber mais, consulte [Gerenciar a auditoria da caixa de correio](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="888e5-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
