---
title: Notas de versão da Pontuação de conformidade da Microsoft
f1.keywords:
- NOCSH
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
description: Notas de versão e problemas conhecidos para a pontuação de conformidade da Microsoft (visualização), um recurso no centro de conformidade do M365 que ajuda a simplificar e automatizar avaliações de risco.
ms.openlocfilehash: d89e1415b836e79187c9e484fef72670f828cfbf
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078618"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a><span data-ttu-id="e2698-103">Notas de versão da Pontuação de conformidade da Microsoft (visualização)</span><span class="sxs-lookup"><span data-stu-id="e2698-103">Microsoft Compliance Score (Preview) release notes</span></span>

<span data-ttu-id="e2698-104">A visualização pública da Pontuação de conformidade da Microsoft fornece acesso antecipado às futuras funcionalidades e atualizações.</span><span class="sxs-lookup"><span data-stu-id="e2698-104">The public preview of Microsoft Compliance Score provides you with early access to upcoming functionality and updates.</span></span> <span data-ttu-id="e2698-105">Verifique esta página com frequência para saber o que há de novo.</span><span class="sxs-lookup"><span data-stu-id="e2698-105">Check this page frequently to learn what's new.</span></span>

<span data-ttu-id="e2698-106">A pontuação de conformidade é um novo recurso do [centro de conformidade da Microsoft 365](microsoft-365-compliance-center.md) que calcula uma pontuação baseada em risco, medindo seu progresso em direção à conclusão de ações recomendadas que ajudam a reduzir os riscos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e2698-106">Compliance Score is a new feature in the [Microsoft 365 compliance center](microsoft-365-compliance-center.md) that calculates a risk-based score, measuring your progress towards completing recommended actions that help reduce compliance risks.</span></span>

## <a name="whats-new"></a><span data-ttu-id="e2698-107">Novidades</span><span class="sxs-lookup"><span data-stu-id="e2698-107">What's new</span></span>

### <a name="new-templates-for-assessments"></a><span data-ttu-id="e2698-108">Novos modelos para avaliações</span><span class="sxs-lookup"><span data-stu-id="e2698-108">New templates for assessments</span></span>

<span data-ttu-id="e2698-109">Novos modelos pré-configurados para avaliações são lançados em produção para a pontuação de conformidade (visualização) à medida que eles se tornam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e2698-109">New pre-configured templates for assessments are released into production for Compliance Score (Preview) as they become available.</span></span> <span data-ttu-id="e2698-110">Confira a [lista completa de modelos aqui](compliance-score.md#templates).</span><span class="sxs-lookup"><span data-stu-id="e2698-110">Check the [full list of templates here](compliance-score.md#templates).</span></span> <span data-ttu-id="e2698-111">Os modelos adicionados recentemente incluem:</span><span class="sxs-lookup"><span data-stu-id="e2698-111">Recently-added templates include:</span></span>

- <span data-ttu-id="e2698-112">Lei de proteção de dados gerais do Brasil (LGPD)</span><span class="sxs-lookup"><span data-stu-id="e2698-112">Brazil General Data Protection Law (LGPD)</span></span>
- <span data-ttu-id="e2698-113">IRAP/ISM do governo australiano (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="e2698-113">IRAP / Australian Government ISM (Preview)</span></span>
- <span data-ttu-id="e2698-114">ISO 27701:2019</span><span class="sxs-lookup"><span data-stu-id="e2698-114">ISO 27701:2019</span></span>
- <span data-ttu-id="e2698-115">SOC 1</span><span class="sxs-lookup"><span data-stu-id="e2698-115">SOC 1</span></span>
- <span data-ttu-id="e2698-116">SOC 2</span><span class="sxs-lookup"><span data-stu-id="e2698-116">SOC 2</span></span>

### <a name="compliance-score-relationship-to-compliance-manager"></a><span data-ttu-id="e2698-117">Relação de Pontuação de conformidade com o Gerenciador de conformidade</span><span class="sxs-lookup"><span data-stu-id="e2698-117">Compliance Score relationship to Compliance Manager</span></span>

<span data-ttu-id="e2698-118">Muitas das funções de conformidade manipuladas no Gerenciador de conformidade agora podem ser feitas na pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e2698-118">Many of the compliance functions handled in Compliance Manager can now be done in Compliance Score.</span></span> <span data-ttu-id="e2698-119">No entanto, algumas funcionalidades ainda residem apenas no gerente de conformidade, e alguma funcionalidade anterior no Gerenciador de conformidade é alterada durante o período de visualização pública.</span><span class="sxs-lookup"><span data-stu-id="e2698-119">However some functionality still resides only in Compliance Manager, and some previous functionality in Compliance Manager is altered during the public preview period.</span></span> 

<span data-ttu-id="e2698-120">Mantenha esses pontos em mente ao trabalhar com a pontuação de conformidade e o gerente de conformidade durante a visualização pública:</span><span class="sxs-lookup"><span data-stu-id="e2698-120">Keep these points in mind as you work with Compliance Score and Compliance Manager during public preview:</span></span>

- <span data-ttu-id="e2698-121">**Gerenciando avaliações**: os usuários podem exibir avaliações e seus detalhes de status na pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e2698-121">**Managing assessments**: users can view assessments and their status details in Compliance Score.</span></span> <span data-ttu-id="e2698-122">No entanto, os usuários só podem executar tarefas de gerenciamento de avaliação no gerente de conformidade ([instruções de exibição](working-with-compliance-manager.md#assessments)) e as tarefas são limitadas ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="e2698-122">However users can only perform assessment management tasks in Compliance Manager ([view instructions](working-with-compliance-manager.md#assessments)), and tasks are limited to the following:</span></span>
    - <span data-ttu-id="e2698-123">Carregar novas avaliações, mas não modificar as avaliações existentes.</span><span class="sxs-lookup"><span data-stu-id="e2698-123">Upload new assessments, but not modify existing assessments.</span></span> <span data-ttu-id="e2698-124">Se você precisar modificar uma avaliação existente, será necessário carregar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="e2698-124">If you need to modify an existing assessment, you will need to upload a new template.</span></span>
    - <span data-ttu-id="e2698-125">Avaliações de exportação</span><span class="sxs-lookup"><span data-stu-id="e2698-125">Export assessments</span></span>
    - <span data-ttu-id="e2698-126">Avaliações de arquivamento</span><span class="sxs-lookup"><span data-stu-id="e2698-126">Archive assessments</span></span>
    - <span data-ttu-id="e2698-127">Exibir avaliações arquivadas</span><span class="sxs-lookup"><span data-stu-id="e2698-127">View archived assessments</span></span>
 - <span data-ttu-id="e2698-128">**Criar modelos para avaliações**:</span><span class="sxs-lookup"><span data-stu-id="e2698-128">**Creating templates for assessments**:</span></span> 
   - <span data-ttu-id="e2698-129">Os usuários devem acessar o Gerenciador de conformidade para criar novos modelos e exportar modelos existentes.</span><span class="sxs-lookup"><span data-stu-id="e2698-129">Users must go to Compliance Manager to create new templates and export existing templates.</span></span> 
   - <span data-ttu-id="e2698-130">Os modelos existentes não podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="e2698-130">Existing templates cannot be customized.</span></span> <span data-ttu-id="e2698-131">Leia as instruções de [Gerenciamento de modelos no Gerenciador de conformidade](working-with-compliance-manager.md#templates).</span><span class="sxs-lookup"><span data-stu-id="e2698-131">Read instructions for [managing templates in Compliance Manager](working-with-compliance-manager.md#templates).</span></span>
   - <span data-ttu-id="e2698-132">Ao criar um modelo, você deve incluir as dimensões de **produto** e **certificação** para garantir que seu modelo seja exibido na pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e2698-132">When creating a template, you must include Dimensions for both **Product** and **Certification** to ensure your template displays in Compliance Score.</span></span>
 - <span data-ttu-id="e2698-133">**Definir permissões**: Pontuação de conformidade os usuários que não receberam permissões anteriormente no Gerenciador de conformidade devem ter suas permissões definidas no centro de conformidade da Microsoft 365 ([saiba mais](compliance-score-setup.md#set-user-permissions-and-assign-roles)).</span><span class="sxs-lookup"><span data-stu-id="e2698-133">**Setting permissions**: Compliance Score users who were not previously granted permissions in Compliance Manager must have their permissions set in the Microsoft 365 compliance center ([learn more](compliance-score-setup.md#set-user-permissions-and-assign-roles)).</span></span> <span data-ttu-id="e2698-134">Os usuários cujas funções foram definidas anteriormente no gerente de conformidade podem usar o mesmo nível de acesso ao trabalhar em Pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e2698-134">Users whose roles were previously set in Compliance Manager can use that same level of access when working in Compliance Score.</span></span>
- <span data-ttu-id="e2698-135">**Transferência de dados**: as organizações com dados residentes no Gerenciador de conformidade verão os dados na pontuação de conformidade e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="e2698-135">**Transfer of data**: organizations with data residing in Compliance Manger will see that data in Compliance Score, and vice-versa.</span></span>
- <span data-ttu-id="e2698-136">**Entrar no Gerenciador de conformidade da Pontuação de conformidade**: se um usuário estiver conectado à pontuação de conformidade e selecionar um link para acessar o Gerenciador de conformidade, o usuário não terá que entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="e2698-136">**Signing in to Compliance Manager from Compliance Score**: if a user is signed in to Compliance Score and selects a link to go to Compliance Manager, the user will not have to sign in again.</span></span> <span data-ttu-id="e2698-137">Após clicar no link, uma nova guia é aberta no navegador com uma caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="e2698-137">After clicking the link, a new tab opens in your browser featuring a dialogue box.</span></span> <span data-ttu-id="e2698-138">Na seção superior com o cabeçalho, "já é um cliente dos serviços de nuvem da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="e2698-138">In the top section with the header, “Already a Microsoft cloud services customer?</span></span> <span data-ttu-id="e2698-139">Entre em sua conta, "Selecione o botão **entrar** para entrar automaticamente no Gerenciador de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e2698-139">Sign in to your account,” select the **Sign In** button to automatically sign in to Compliance Manager.</span></span>

## <a name="known-issues-in-compliance-score-preview"></a><span data-ttu-id="e2698-140">Problemas conhecidos na pontuação de conformidade (visualização)</span><span class="sxs-lookup"><span data-stu-id="e2698-140">Known issues in Compliance Score (Preview)</span></span>

<span data-ttu-id="e2698-141">As seções a seguir abordam problemas conhecidos a serem resolvidos em futuras versões da Pontuação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="e2698-141">The following sections cover known issues to be resolved in upcoming releases of Compliance Score.</span></span>

### <a name="launch-now-links-in-certain-improvement-actions"></a><span data-ttu-id="e2698-142">Iniciar agora links em algumas ações de aperfeiçoamento</span><span class="sxs-lookup"><span data-stu-id="e2698-142">Launch Now links in certain improvement actions</span></span>

<span data-ttu-id="e2698-143">Em determinadas ações de aprimoramento, selecionar o link **Iniciar agora** que aparece sob as instruções de implementação resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="e2698-143">In certain improvement actions, selecting the **Launch Now** link that appears underneath the implementation instructions gives an error.</span></span> <span data-ttu-id="e2698-144">Para acessar o destino apropriado, que é o centro de administração do SharePoint, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e2698-144">To access the proper destination, which is the SharePoint admin center, follow these steps:</span></span>

1. <span data-ttu-id="e2698-145">Vá para o [centro de administração do Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e2698-145">Go to the [Microsoft 365 Admin Center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="e2698-146">No menu de navegação à esquerda, selecione **Mostrar tudo**.</span><span class="sxs-lookup"><span data-stu-id="e2698-146">On the left navigation menu, select **Show all**.</span></span>
3. <span data-ttu-id="e2698-147">Em **centros de administração,** selecione **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="e2698-147">Under **Admin centers,** select **SharePoint**.</span></span>

<span data-ttu-id="e2698-148">Veja a seguir as ações de aperfeiçoamento afetadas, que residem na categoria **proteger informações** :</span><span class="sxs-lookup"><span data-stu-id="e2698-148">Below are the affected improvement actions, which all reside in the **Protect information** category:</span></span>
  - <span data-ttu-id="e2698-149">Aplicar criptografia à biblioteca do SharePoint</span><span class="sxs-lookup"><span data-stu-id="e2698-149">Apply encryption to SharePoint Library</span></span>
  - <span data-ttu-id="e2698-150">Classificar dados no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e2698-150">Classify Data in SharePoint Online</span></span>
  - <span data-ttu-id="e2698-151">Configurar links de compartilhamento externos para expirar</span><span class="sxs-lookup"><span data-stu-id="e2698-151">Configure External Sharing Links to Expire</span></span>
  - <span data-ttu-id="e2698-152">Habilitar o controle de versão para bibliotecas de documentos</span><span class="sxs-lookup"><span data-stu-id="e2698-152">Enable Versioning for Document Libraries</span></span>

### <a name="long-load-times-for-non-admin-users"></a><span data-ttu-id="e2698-153">Tempos de carregamento longos para usuários que não são administradores</span><span class="sxs-lookup"><span data-stu-id="e2698-153">Long load times for non-admin users</span></span>
<span data-ttu-id="e2698-154">Nota de conformidade os usuários que possuem funções diferentes de uma função de administrador podem enfrentar tempos de carregamento longos ao tentar uma entrada.</span><span class="sxs-lookup"><span data-stu-id="e2698-154">Compliance Score users who hold roles other than an admin role may experience long load times when trying to a sign in.</span></span> <span data-ttu-id="e2698-155">A atualização do navegador resolverá esse problema.</span><span class="sxs-lookup"><span data-stu-id="e2698-155">Refreshing your browser will resolve this issue.</span></span> <span data-ttu-id="e2698-156">(Saiba mais sobre as [funções de Pontuação de conformidade](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span><span class="sxs-lookup"><span data-stu-id="e2698-156">(Learn more about [Compliance Score roles](compliance-score-setup.md#set-user-permissions-and-assign-roles).)</span></span>

### <a name="supported-browsers"></a><span data-ttu-id="e2698-157">Navegadores com suporte</span><span class="sxs-lookup"><span data-stu-id="e2698-157">Supported browsers</span></span>

- <span data-ttu-id="e2698-158">As versões mais recentes do Microsoft Edge, do Chrome e do Safari são suportadas.</span><span class="sxs-lookup"><span data-stu-id="e2698-158">The latest versions of Microsoft Edge, Chrome, and Safari are supported.</span></span>
- <span data-ttu-id="e2698-159">Pode haver casos em que os dados atualizados não aparecem até que seu navegador seja atualizado.</span><span class="sxs-lookup"><span data-stu-id="e2698-159">There may be instances where updated data does not appear until your browser is refreshed.</span></span>
- <span data-ttu-id="e2698-160">A versão de visualização do Microsoft Edge não é suportada, mas não tem problemas conhecidos.</span><span class="sxs-lookup"><span data-stu-id="e2698-160">The preview version of Microsoft Edge is not supported but has no known issues.</span></span>
- <span data-ttu-id="e2698-161">Não há suporte para o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e2698-161">Internet Explorer is not supported.</span></span>
 
### <a name="language-support"></a><span data-ttu-id="e2698-162">Suporte a idiomas</span><span class="sxs-lookup"><span data-stu-id="e2698-162">Language support</span></span>

- <span data-ttu-id="e2698-163">A pontuação de conformidade só está disponível no inglês dos EUA.</span><span class="sxs-lookup"><span data-stu-id="e2698-163">Compliance Score is only available in U.S. English.</span></span>
