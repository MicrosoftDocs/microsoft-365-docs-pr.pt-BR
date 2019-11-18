---
title: Notas de versão do Gerenciador de conformidade da Microsoft
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: O Gerenciador de conformidade da Microsoft é uma ferramenta de avaliação de riscos gratuita baseada em fluxo de trabalho no portal de confiança do serviço Microsoft. O Gerenciador de conformidade permite que você rastreie, atribua e verifique as atividades de conformidade normativa relacionadas aos serviços em nuvem da Microsoft.
ms.openlocfilehash: 1a490212b2275b9f297e2585e7242f5331d0fe56
ms.sourcegitcommit: 5c6c30ec5541d2fb77e53a1309db1fe7b75fc3e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2019
ms.locfileid: "38684766"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="48255-104">Notas de versão do Gerenciador de conformidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="48255-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="48255-105">A visualização pública do Gerenciador de conformidade fornece acesso antecipado às futuras funcionalidades e atualizações.</span><span class="sxs-lookup"><span data-stu-id="48255-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="48255-106">Você pode usar a ferramenta atualizada do [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) no portal de [confiança do serviço](https://servicetrust.microsoft.com) para rastrear, atribuir e verificar as atividades de conformidade regulatória relacionadas aos serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="48255-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="48255-107">O que há de novo no Gerenciador de conformidade (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="48255-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="48255-108">**Acesso baseado em função ao Gerenciador de conformidade:** A função de **acesso de convidado** padrão foi removida.</span><span class="sxs-lookup"><span data-stu-id="48255-108">**Role-based access to Compliance Manager:** The default **Guest access** role has been removed.</span></span> <span data-ttu-id="48255-109">Para que um usuário acesse o gerente de conformidade, o administrador global deve [atribuir a cada usuário uma permissão](compliance-manager-overview.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="48255-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview.md#permissions).</span></span>

- <span data-ttu-id="48255-110">**Nota de conformidade atualizada**: a pontuação de conformidade agora inclui pontuações para ações gerenciadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="48255-110">**Updated Compliance Score**: Compliance Score now includes scores for Microsoft-managed actions.</span></span> <span data-ttu-id="48255-111">A pontuação aumentará como resultado.</span><span class="sxs-lookup"><span data-stu-id="48255-111">Your score will increase as a result.</span></span>

- <span data-ttu-id="48255-112">**Itens de ações:** Os itens de ação agora são itens individuais e muitos incluem coleção de telemetria da API do Microsoft Secure Score Graph.</span><span class="sxs-lookup"><span data-stu-id="48255-112">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="48255-113">Sempre que possível, as recomendações de ações técnicas agora têm links para a página de configuração aplicável no serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="48255-113">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="48255-114">**Gerenciamento de locatário:** Nova interface para gerenciar novos elementos de dados no Gerenciador de conformidade (visualização):</span><span class="sxs-lookup"><span data-stu-id="48255-114">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="48255-115">**Dimensões:** Exibir, adicionar e personalizar metadados para modelos, avaliações e itens de ação que permitem que você crie pivôs personalizados para filtros.</span><span class="sxs-lookup"><span data-stu-id="48255-115">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="48255-116">**Proprietários:** Especifique um proprietário para cada item de ação.</span><span class="sxs-lookup"><span data-stu-id="48255-116">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="48255-117">**Ações do cliente:** Gerencie a lista completa de itens de ações incluídas no Gerenciador de conformidade (visualização) e habilite/desabilite o monitoramento de Pontuação segura para itens de ação integrados à pontuação segura.</span><span class="sxs-lookup"><span data-stu-id="48255-117">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="48255-118">Problemas conhecidos no gerente de conformidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="48255-118">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="48255-119">As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões do Gerenciador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="48255-119">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="48255-120">Pontuação de conformidade</span><span class="sxs-lookup"><span data-stu-id="48255-120">Compliance Score</span></span>

- <span data-ttu-id="48255-121">Para itens de ação marcados como **não no escopo**, a pontuação atribuída ao item de ação não é excluída do cálculo da Pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="48255-121">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the compliance score calculation.</span></span> <span data-ttu-id="48255-122">Itens de ação marcados **não no escopo** não aumentam sua pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="48255-122">Action Items marked **Not in Scope** do not increase your compliance score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="48255-123">Classificação de Segurança</span><span class="sxs-lookup"><span data-stu-id="48255-123">Secure Score</span></span>

- <span data-ttu-id="48255-124">Resultados de Pontuação segura não estão disponíveis para alguns itens de ações em determinadas assinaturas do Microsoft 365 e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="48255-124">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="48255-125">**Não foi possível detectar** o resultado da Pontuação segura nesses casos.</span><span class="sxs-lookup"><span data-stu-id="48255-125">The Secure Score result is **Could not be detected** in these cases.</span></span>
- <span data-ttu-id="48255-126">Às vezes, os resultados de Pontuação segura são retornados para políticas correspondentes e itens de ação não concluídos.</span><span class="sxs-lookup"><span data-stu-id="48255-126">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>
- <span data-ttu-id="48255-127">Para novos locatários, as atualizações de Pontuação segura para todas as ações são automaticamente ativadas.</span><span class="sxs-lookup"><span data-stu-id="48255-127">For new tenants, Secure Score updates for all actions is automatically turned on.</span></span> <span data-ttu-id="48255-128">O administrador global pode definir a opção de atualização contínua de Pontuação segura como desativada, o que desativa as atualizações de todas as ações.</span><span class="sxs-lookup"><span data-stu-id="48255-128">The global administrator can set the Secure Score continuous update switch to off, which turns off updates for all actions.</span></span>
- <span data-ttu-id="48255-129">Quando as atualizações de Pontuação segura estiverem ativadas, as ações serão ativamente monitoradas por Pontuação segura, embora a data de teste da ação não seja atualizada para refletir o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="48255-129">When Secure Score updates are turned on, actions are actively monitored by Secure Score, although the action’s test date will not be updated to reflect monitoring.</span></span>
- <span data-ttu-id="48255-130">Quando novas avaliações são criadas, as pontuações incluem automaticamente pontuações de controle gerenciado pela Microsoft e integração de Pontuação segura.</span><span class="sxs-lookup"><span data-stu-id="48255-130">When new assessments are created, scores automatically include Microsoft-managed control scores and Secure Score integration.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="48255-131">Controles gerenciados pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="48255-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="48255-132">A data de teste dos controles gerenciados pela Microsoft não aparecerá na interface do usuário, mesmo quando estiver incluída na avaliação.</span><span class="sxs-lookup"><span data-stu-id="48255-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="48255-133">Para ver as informações de data de teste, você deve exportar a avaliação.</span><span class="sxs-lookup"><span data-stu-id="48255-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="48255-134">Personalização</span><span class="sxs-lookup"><span data-stu-id="48255-134">Customization</span></span>

- <span data-ttu-id="48255-135">Adicionar controles personalizados permite adicionar um novo controle a uma família de controles existente, mas não permite que você adicione uma nova família de controle.</span><span class="sxs-lookup"><span data-stu-id="48255-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="48255-136">Esta versão não dá suporte à vinculação de itens de ação ou à adição de itens de ações ou controles a uma avaliação.</span><span class="sxs-lookup"><span data-stu-id="48255-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="48255-137">Se você criar uma ação personalizada, não será possível editá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="48255-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="48255-138">Famílias de controle não exibidas em avaliações</span><span class="sxs-lookup"><span data-stu-id="48255-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="48255-139">Quando você importa um modelo, todas as avaliações baseadas nesse modelo refletem todas as famílias de controle que fazem parte do modelo.</span><span class="sxs-lookup"><span data-stu-id="48255-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="48255-140">Mas se você adicionar novas famílias de controle ao modelo, qualquer avaliação existente não refletirá as alterações.</span><span class="sxs-lookup"><span data-stu-id="48255-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="48255-141">Somente novas avaliações criadas a partir do modelo atualizado refletem as alterações.</span><span class="sxs-lookup"><span data-stu-id="48255-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="templates"></a><span data-ttu-id="48255-142">Modelos</span><span class="sxs-lookup"><span data-stu-id="48255-142">Templates</span></span>

- <span data-ttu-id="48255-143">Ao criar um modelo, você deve incluir as dimensões de **produto** e **certificação** para garantir que seu modelo seja exibido na pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="48255-143">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
- <span data-ttu-id="48255-144">Os modelos arquivados são editáveis e não devem ser editáveis.</span><span class="sxs-lookup"><span data-stu-id="48255-144">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="48255-145">Os modelos bloqueados permitem a criação da avaliação, quando não deveriam.</span><span class="sxs-lookup"><span data-stu-id="48255-145">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="48255-146">Bloquear um modelo é destinado a impedir que ele seja usado para criar avaliações.</span><span class="sxs-lookup"><span data-stu-id="48255-146">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="48255-147">Exportar</span><span class="sxs-lookup"><span data-stu-id="48255-147">Export</span></span>

- <span data-ttu-id="48255-148">O modelo exportar para JSON falha quando o status do modelo é definido como **importado** ou com **aprovação pendente**.</span><span class="sxs-lookup"><span data-stu-id="48255-148">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="48255-149">Navegadores com suporte</span><span class="sxs-lookup"><span data-stu-id="48255-149">Supported browsers</span></span>

- <span data-ttu-id="48255-150">As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.</span><span class="sxs-lookup"><span data-stu-id="48255-150">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="48255-151">Pode haver casos em que os dados atualizados não aparecem até que seu navegador seja atualizado.</span><span class="sxs-lookup"><span data-stu-id="48255-151">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="48255-152">A versão de visualização do Microsoft Edge não é suportada, mas não tem problemas conhecidos.</span><span class="sxs-lookup"><span data-stu-id="48255-152">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="48255-153">Não há suporte para o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="48255-153">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="48255-154">Tempo limite da sessão</span><span class="sxs-lookup"><span data-stu-id="48255-154">Session timeout</span></span>

- <span data-ttu-id="48255-155">Quando uma sessão expira, um erro "algo deu errado" pode ser exibido.</span><span class="sxs-lookup"><span data-stu-id="48255-155">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="48255-156">Para resolver, vá para o [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) e faça login novamente.</span><span class="sxs-lookup"><span data-stu-id="48255-156">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="48255-157">Suporte a idiomas</span><span class="sxs-lookup"><span data-stu-id="48255-157">Language support</span></span>

- <span data-ttu-id="48255-158">Todos os idiomas não são compatíveis com todas as páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="48255-158">All languages are not supported for all webpages.</span></span> <span data-ttu-id="48255-159">Se seu idioma local não é suportado, veja em inglês dos EUA.</span><span class="sxs-lookup"><span data-stu-id="48255-159">If your local language is unsupported, view in US English.</span></span>