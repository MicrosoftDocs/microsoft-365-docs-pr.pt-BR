---
title: Configuração do SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Configure a compreensão de conteúdo no Projeto Cortex
ms.openlocfilehash: 1abcc71200642de3f74a92e83299e079ffffb038
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604255"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="004ec-103">Configuração do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="004ec-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="004ec-104">Os administradores podem usar o Centro de administração do Microsoft 365 para configurar o [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="004ec-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="004ec-105">Considere o seguinte antes de começar:</span><span class="sxs-lookup"><span data-stu-id="004ec-105">Consider the following before you start:</span></span>

- <span data-ttu-id="004ec-106">Em quais sites do SharePoint você vai ativar o processamento de formulários?</span><span class="sxs-lookup"><span data-stu-id="004ec-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="004ec-107">Todos, alguns ou sites selecionados?</span><span class="sxs-lookup"><span data-stu-id="004ec-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="004ec-108">Qual será o nome do seu centro de conteúdo padrão?</span><span class="sxs-lookup"><span data-stu-id="004ec-108">What will you name of your default content center?</span></span>

<span data-ttu-id="004ec-109">É possível alterar suas configurações após a configuração inicial no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="004ec-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="004ec-110">Antes da configuração, certifique-se de planejar a melhor maneira de estabelecer e configurar a compreensão de conteúdo no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="004ec-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="004ec-111">Por exemplo, você precisa levar em consideração os seguintes nomes de:</span><span class="sxs-lookup"><span data-stu-id="004ec-111">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="004ec-112">Sites do SharePoint que você deseja ativar o processamento de formulários - todos, alguns ou sites selecionados</span><span class="sxs-lookup"><span data-stu-id="004ec-112">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="004ec-113">Seu centro de conteúdo e o nome do administrador do site principal</span><span class="sxs-lookup"><span data-stu-id="004ec-113">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="004ec-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="004ec-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="004ec-115">Você deve ter permissões administrativas globais ou de administrador do SharePoint para poder acessar o Centro de administração do Microsoft 365 e configurar a compreensão de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="004ec-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="004ec-116">Como administrador, também é possível fazer alterações nas configurações selecionadas a qualquer momento após a configuração e ao longo das configurações de gerenciamento de compreensão de conteúdo no Centro de Administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="004ec-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="004ec-117">Para configurar o SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="004ec-117">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="004ec-118">No centro de administração do Microsoft 365, selecione **Configurar** e visualize a seção **Arquivos e conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="004ec-118">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="004ec-119">Na seção **Arquivos e conteúdo**, selecione **Automatizar a compreensão de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="004ec-119">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="004ec-120">Na página **Compreensão automatizada de conteúdo**, clique em **Começar** para percorrer o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="004ec-120">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="004ec-121">![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="004ec-121">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="004ec-122">Na página **Configurar Processamento de Formulário**, você pode escolher se quer permitir que os usuários sejam capazes de criar modelos de processamento de formulários em bibliotecas específicas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="004ec-122">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="004ec-123">Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **Criar um modelo de processamento de formulário** nas bibliotecas de documentos do SharePoint nas quais ele está ativado.</span><span class="sxs-lookup"><span data-stu-id="004ec-123">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="004ec-124">Para **Quais bibliotecas do SharePoint devem exibir a opção para criar um modelo de processamento de formulário**, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="004ec-124">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="004ec-125">**Todas as bibliotecas do SharePoint** para torná-lo disponível em todas as bibliotecas do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="004ec-125">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="004ec-126">**Bibliotecas somente em sites selecionados**, e então selecione os sites nos quais você quer disponibilizá-lo ou carregue uma lista de até 50 sites.</span><span class="sxs-lookup"><span data-stu-id="004ec-126">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="004ec-127">**Nenhuma biblioteca do SharePoint** se você não deseja torná-lo disponível para nenhum site (você pode alterar isto após a configuração).</span><span class="sxs-lookup"><span data-stu-id="004ec-127">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="004ec-128">![Configurar o processamento de formulário](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="004ec-128">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="004ec-129">A remoção de um site após a sua insalubridade não afeta os modelos existentes aplicados às bibliotecas naquele site ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="004ec-129">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="004ec-130">Na página **Criar Centro de Conteúdo**, você pode criar um site de centro de conteúdo do SharePoint, no qual seus usuários poderão criar e gerenciar modelos de compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="004ec-130">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="004ec-131">Para **Nome do site**, digite o nome que você quer dar ao site do centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="004ec-131">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="004ec-132">O **Endereço do site** mostrará o URL do seu site, baseado no que você selecionou para o nome do site.</span><span class="sxs-lookup"><span data-stu-id="004ec-132">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="004ec-133">Se você desejar mudá-lo, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="004ec-133">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="004ec-134">![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="004ec-134">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="004ec-135">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="004ec-135">Select **Next**.</span></span>

6. <span data-ttu-id="004ec-136">Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="004ec-136">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="004ec-137">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="004ec-137">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="004ec-138">Na página de confirmação, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="004ec-138">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="004ec-139">Você retornará à sua página **Compreensão automatizada de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="004ec-139">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="004ec-140">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="004ec-140">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="004ec-141">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="004ec-141">Assign licenses</span></span>

<span data-ttu-id="004ec-142">Uma vez configurado o SharePoint Syntex, será necessário atribuir licenças para os usuários que farão uso dos recursos do SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="004ec-142">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="004ec-143">Atribuição de licenças:</span><span class="sxs-lookup"><span data-stu-id="004ec-143">To assign licenses:</span></span>

1. <span data-ttu-id="004ec-144">No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="004ec-144">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="004ec-145">Selecione os usuários que você deseja licenciar, e clique **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="004ec-145">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="004ec-146">Selecione **Atribuir mais**.</span><span class="sxs-lookup"><span data-stu-id="004ec-146">Select **Assign more**.</span></span>

4. <span data-ttu-id="004ec-147">Selecione **SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="004ec-147">Select **SharePoint Syntex**.</span></span> <span data-ttu-id="004ec-148">Em **Aplicativos**, certifique-se de que **Common Data Service para o SharePoint Syntex**, **SharePoint Syntex** e **SharePoint Syntex - tipo de SPO** estão todos selecionados.</span><span class="sxs-lookup"><span data-stu-id="004ec-148">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="004ec-149">![Licenças do SharePoint Syntex no Centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="004ec-149">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="004ec-150">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="004ec-150">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="004ec-151">Créditos do Construtor de IA</span><span class="sxs-lookup"><span data-stu-id="004ec-151">AI Builder credits</span></span>

<span data-ttu-id="004ec-152">Se você tiver 300 ou mais licenças do SharePoint Syntex para o SharePoint Syntex na sua organização, você receberá um milhão de créditos do Construtor de IA.</span><span class="sxs-lookup"><span data-stu-id="004ec-152">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="004ec-153">Se você tiver menos de 300 licenças, você deve comprar créditos do Construtor de IA para usar o processamento de formulários.</span><span class="sxs-lookup"><span data-stu-id="004ec-153">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="004ec-154">Você pode estimar a capacidade correta do Construtor de IA com a [calculadora do Construtor de IA](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="004ec-154">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="004ec-155">Vá até o [Centro de administração da Plataforma Power ](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.</span><span class="sxs-lookup"><span data-stu-id="004ec-155">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="004ec-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="004ec-156">See also</span></span>

<span data-ttu-id="004ec-157">[Visão geral do modelo de processamento de formulários](https://docs.microsoft.com/ai-builder/form-processing-model-overview).</span><span class="sxs-lookup"><span data-stu-id="004ec-157">[Overview of the form processing model](https://docs.microsoft.com/ai-builder/form-processing-model-overview)</span></span>

[<span data-ttu-id="004ec-158">Passo a passo: como construir um modelo de compreensão de documentos (vídeo)</span><span class="sxs-lookup"><span data-stu-id="004ec-158">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

