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
ms.openlocfilehash: 3646d86cd9edac95975958458eb52a44fe30d2f5
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417500"
---
# <a name="release-notes-for-compliance-manager-preview"></a><span data-ttu-id="a8b6f-104">Notas de versão do Gerenciador de conformidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="a8b6f-104">Release Notes for Compliance Manager (Preview)</span></span>

<span data-ttu-id="a8b6f-105">A visualização pública do Gerenciador de conformidade fornece acesso antecipado às futuras funcionalidades e atualizações.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-105">The public preview of Compliance Manager provides you with early access to upcoming functionality and updates.</span></span>

<span data-ttu-id="a8b6f-106">Você pode usar a ferramenta atualizada do [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) no portal de [confiança do serviço](https://servicetrust.microsoft.com) para rastrear, atribuir e verificar as atividades de conformidade regulatória relacionadas aos serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-106">You can use the updated [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) tool on the [Service Trust Portal](https://servicetrust.microsoft.com) to track, assign, and verify regulatory compliance activities related to Microsoft cloud services.</span></span>

## <a name="whats-new-in-compliance-manager-preview"></a><span data-ttu-id="a8b6f-107">O que há de novo no Gerenciador de conformidade (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="a8b6f-107">What’s new in Compliance Manager (Preview)</span></span>

- <span data-ttu-id="a8b6f-108">**Acesso baseado em função ao Gerenciador de conformidade:** A função de **acesso de adivinhação** padrão foi removida.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-108">**Role-based access to Compliance Manager:** The default **Guess access** role has been removed.</span></span> <span data-ttu-id="a8b6f-109">Para que um usuário acesse o gerente de conformidade, o administrador global deve [atribuir a cada usuário uma permissão](compliance-manager-overview#permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a8b6f-109">In order for a user to access Compliance Manager, the global admin must [assign each user a permission](compliance-manager-overview#permissions.md).</span></span>

- <span data-ttu-id="a8b6f-110">**Integração com a pontuação segura da Microsoft:** O Gerenciador de conformidade oferece suporte à integração com a [Pontuação segura da Microsoft](../security/mtp/microsoft-secure-score.md) , mapeando as ações gerenciadas pelo cliente para mais de 50 de Pontuação segura.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-110">**Integration with Microsoft Secure Score:** Compliance Manager supports integration with [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md) by mapping customer-managed Actions to more than 50 Secure Score actions.</span></span> <span data-ttu-id="a8b6f-111">Quando você completa uma ação mapeada na pontuação segura, a ação correspondente do Gerenciador de conformidade é atualizada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-111">When you complete a mapped action in Secure Score, the corresponding Compliance Manager Action automatically updates.</span></span>

- <span data-ttu-id="a8b6f-112">**Importe avaliações personalizadas:** Além das avaliações internas, o Gerenciador de conformidade agora oferece suporte à importação de modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-112">**Import custom Assessments:** In addition to built-in Assessments, Compliance Manager now supports importing custom Templates.</span></span> <span data-ttu-id="a8b6f-113">Você pode criar avaliações personalizadas para qualquer produto ou serviço e qualquer padrão ou regulamentação.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-113">You can create custom Assessments for any product or service and any standard or regulation.</span></span>

- <span data-ttu-id="a8b6f-114">**Itens de ações:** Os itens de ação agora são itens individuais e muitos incluem coleção de telemetria da API do Microsoft Secure Score Graph.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-114">**Actions Items:** Action Items are now individual items and many include telemetry collection from the Microsoft Secure Score Graph API.</span></span> <span data-ttu-id="a8b6f-115">Sempre que possível, as recomendações de ações técnicas agora têm links para a página de configuração aplicável no serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-115">Where possible, technical action recommendations now have links to the applicable configuration page in the Office 365 service.</span></span>

- <span data-ttu-id="a8b6f-116">**Gerenciamento de locatário:** Nova interface para gerenciar novos elementos de dados no Gerenciador de conformidade (visualização):</span><span class="sxs-lookup"><span data-stu-id="a8b6f-116">**Tenant Management:** New interface for managing new data elements in Compliance Manager (Preview):</span></span>
    - <span data-ttu-id="a8b6f-117">**Dimensões:** Exibir, adicionar e personalizar metadados para modelos, avaliações e itens de ação que permitem que você crie pivôs personalizados para filtros.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-117">**Dimensions:** View, add and customize metadata for Templates, Assessments, and Action Items that allow you to create custom pivots for filters.</span></span>
    - <span data-ttu-id="a8b6f-118">**Proprietários:** Especifique um proprietário para cada item de ação.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-118">**Owners:** Specify an owner for each Action Item.</span></span>
    - <span data-ttu-id="a8b6f-119">**Ações do cliente:** Gerencie a lista completa de itens de ações incluídas no Gerenciador de conformidade (visualização) e habilite/desabilite o monitoramento de Pontuação segura para itens de ação integrados à pontuação segura.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-119">**Customer Actions:** Manage the complete list of Actions Items included in Compliance Manager (Preview) and enable/disable Secure Score monitoring for Action Items integrated with Secure Score.</span></span>

- <span data-ttu-id="a8b6f-120">**Pontuação de conformidade atualizada**: a metodologia mudou para suportar a sincronização com a pontuação segura da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-120">**Updated Compliance Score**: The methodology has changed to support syncing with Microsoft Secure Score.</span></span> <span data-ttu-id="a8b6f-121">A pontuação é calculada com base nas pontuações de ação gerenciada pela Microsoft e nas pontuações de ação gerenciada pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-121">The score is calculated based on Microsoft-managed action scores and customer-managed action scores.</span></span>

## <a name="known-issues-in-compliance-manager-preview"></a><span data-ttu-id="a8b6f-122">Problemas conhecidos no gerente de conformidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="a8b6f-122">Known issues in Compliance Manager (Preview)</span></span>

<span data-ttu-id="a8b6f-123">As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões do Gerenciador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-123">The following sections cover known issues to be resolved in upcoming releases of Compliance Manager.</span></span>

### <a name="compliance-score"></a><span data-ttu-id="a8b6f-124">Pontuação de conformidade</span><span class="sxs-lookup"><span data-stu-id="a8b6f-124">Compliance Score</span></span>

- <span data-ttu-id="a8b6f-125">Para itens de ação marcados como **não no escopo**, a pontuação atribuída ao item de ação não é excluída do cálculo da Pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-125">For Action Items marked as **Not in Scope**, the score assigned to the Action Item is not excluded from the Compliance Score calculation.</span></span> <span data-ttu-id="a8b6f-126">Itens de ação marcados **não no escopo** não aumentam sua pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-126">Action Items marked **Not in Scope** do not increase your Compliance Score.</span></span>

### <a name="secure-score"></a><span data-ttu-id="a8b6f-127">Classificação de Segurança</span><span class="sxs-lookup"><span data-stu-id="a8b6f-127">Secure Score</span></span>

- <span data-ttu-id="a8b6f-128">Resultados de Pontuação segura não estão disponíveis para alguns itens de ações em determinadas assinaturas do Microsoft 365 e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-128">Secure Score results are not available for some Actions Items in certain Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="a8b6f-129">O resultado da Pontuação segura é ' não pôde ser detectado ' nesses casos.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-129">The Secure Score result is 'Could not be detected' in these cases.</span></span>
- <span data-ttu-id="a8b6f-130">Às vezes, os resultados de Pontuação segura são retornados para políticas correspondentes e itens de ação não concluídos.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-130">Sometimes Secure Score results are returned for corresponding policies and Action Items not completed.</span></span>

### <a name="microsoft-managed-controls"></a><span data-ttu-id="a8b6f-131">Controles gerenciados pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8b6f-131">Microsoft-managed Controls</span></span>

- <span data-ttu-id="a8b6f-132">A data de teste dos controles gerenciados pela Microsoft não aparecerá na interface do usuário, mesmo quando estiver incluída na avaliação.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-132">The test date for Microsoft-managed controls is not appearing in the UI, even when included in the Assessment.</span></span> <span data-ttu-id="a8b6f-133">Para ver as informações de data de teste, você deve exportar a avaliação.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-133">To see test date information, you must export the Assessment.</span></span>

### <a name="customization"></a><span data-ttu-id="a8b6f-134">Personalização</span><span class="sxs-lookup"><span data-stu-id="a8b6f-134">Customization</span></span>

- <span data-ttu-id="a8b6f-135">Adicionar controles personalizados permite adicionar um novo controle a uma família de controles existente, mas não permite que você adicione uma nova família de controle.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-135">Adding custom Controls enables adding a new control to an existing control family, but it does not allow you to add a new Control Family.</span></span>
- <span data-ttu-id="a8b6f-136">Esta versão não dá suporte à vinculação de itens de ação ou à adição de itens de ações ou controles a uma avaliação.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-136">This release does not support linking Action Items or adding Actions Items or Controls to an Assessment.</span></span>
- <span data-ttu-id="a8b6f-137">Se você criar uma ação personalizada, não será possível editá-la ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-137">If you create a custom Action, you cannot edit or delete it.</span></span>

### <a name="control-families-not-shown-in-assessments"></a><span data-ttu-id="a8b6f-138">Famílias de controle não exibidas em avaliações</span><span class="sxs-lookup"><span data-stu-id="a8b6f-138">Control Families Not Shown in Assessments</span></span>

- <span data-ttu-id="a8b6f-139">Quando você importa um modelo, todas as avaliações baseadas nesse modelo refletem todas as famílias de controle que fazem parte do modelo.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-139">When you import a Template, all Assessments based on that Template reflect all Control Families that are part of the Template.</span></span> <span data-ttu-id="a8b6f-140">Mas se você adicionar novas famílias de controle ao modelo, qualquer avaliação existente não refletirá as alterações.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-140">But if you add new Control Families to the Template, any existing Assessments will not reflect the changes.</span></span> <span data-ttu-id="a8b6f-141">Somente novas avaliações criadas a partir do modelo atualizado refletem as alterações.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-141">Only new Assessments created off the updated Template reflect the changes.</span></span>

### <a name="filters"></a><span data-ttu-id="a8b6f-142">Filtros</span><span class="sxs-lookup"><span data-stu-id="a8b6f-142">Filters</span></span>

- <span data-ttu-id="a8b6f-143">A filtragem em itens de ação ou controles não produz resultados corretos de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-143">Filtering on Action Items or Controls does not consistently produce correct results.</span></span>

### <a name="templates"></a><span data-ttu-id="a8b6f-144">Modelos</span><span class="sxs-lookup"><span data-stu-id="a8b6f-144">Templates</span></span>

- <span data-ttu-id="a8b6f-145">Os modelos arquivados são editáveis e não devem ser editáveis.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-145">Archived templates are editable and they should not be editable.</span></span>
- <span data-ttu-id="a8b6f-146">Os modelos bloqueados permitem a criação da avaliação, quando não deveriam.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-146">Locked templates allow for Assessment creation when they should not.</span></span> <span data-ttu-id="a8b6f-147">Bloquear um modelo é destinado a impedir que ele seja usado para criar avaliações.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-147">Locking a Template is meant to prevent it from being used to create Assessments.</span></span>

### <a name="export"></a><span data-ttu-id="a8b6f-148">Exportar</span><span class="sxs-lookup"><span data-stu-id="a8b6f-148">Export</span></span>

- <span data-ttu-id="a8b6f-149">O modelo exportar para JSON falha quando o status do modelo é definido como **importado** ou com **aprovação pendente**.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-149">Template export to JSON fails when the template status is set to **Imported** or **Pending Approval**.</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="a8b6f-150">Navegadores com suporte</span><span class="sxs-lookup"><span data-stu-id="a8b6f-150">Supported browsers</span></span>

- <span data-ttu-id="a8b6f-151">As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-151">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="a8b6f-152">Pode haver casos em que os dados atualizados não aparecem até que seu navegador seja atualizado.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-152">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="a8b6f-153">A versão de visualização do Microsoft Edge não é suportada, mas não tem problemas conhecidos.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-153">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="a8b6f-154">Não há suporte para o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-154">Internet Explorer is not supported.</span></span>

### <a name="session-timeout"></a><span data-ttu-id="a8b6f-155">Tempo limite da sessão</span><span class="sxs-lookup"><span data-stu-id="a8b6f-155">Session timeout</span></span>

- <span data-ttu-id="a8b6f-156">Quando uma sessão expira, um erro "algo deu errado" pode ser exibido.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-156">When a session times out, a “Something went wrong” error may appear.</span></span> <span data-ttu-id="a8b6f-157">Para resolver, vá para o [Gerenciador de conformidade](https://servicetrust.microsoft.com/ComplianceManager) e faça login novamente.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-157">To resolve, go to [Compliance Manager](https://servicetrust.microsoft.com/ComplianceManager) and log in again.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="a8b6f-158">Suporte a idiomas</span><span class="sxs-lookup"><span data-stu-id="a8b6f-158">Language support</span></span>

- <span data-ttu-id="a8b6f-159">Todos os idiomas não são compatíveis com todas as páginas da Web.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-159">All languages are not supported for all webpages.</span></span> <span data-ttu-id="a8b6f-160">Se seu idioma local não é suportado, veja em inglês dos EUA.</span><span class="sxs-lookup"><span data-stu-id="a8b6f-160">If your local language is unsupported, view in US English.</span></span>