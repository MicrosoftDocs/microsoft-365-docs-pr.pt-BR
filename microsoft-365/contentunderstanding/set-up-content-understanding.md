---
title: Configuração do SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
search.appverid: MET150
localization_priority: Priority
description: Configure a compreensão de conteúdo no Projeto Cortex
ms.openlocfilehash: 2f9fd4e035152a127f9f1c254f4c489a6ca4c976
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994694"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="31c5b-103">Configuração do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="31c5b-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="31c5b-104">Os administradores podem usar o Centro de administração do Microsoft 365 para configurar o [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="31c5b-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="31c5b-105">Considere o seguinte antes de começar:</span><span class="sxs-lookup"><span data-stu-id="31c5b-105">Consider the following before you start:</span></span>

- <span data-ttu-id="31c5b-106">Em quais sites do Microsoft Office SharePoint Online você habilitará o processamento de formulários?</span><span class="sxs-lookup"><span data-stu-id="31c5b-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="31c5b-107">Todos, alguns ou sites selecionados?</span><span class="sxs-lookup"><span data-stu-id="31c5b-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="31c5b-108">Como você nomeará seu centro de conteúdo padrão?</span><span class="sxs-lookup"><span data-stu-id="31c5b-108">What will you name your default content center?</span></span>

<span data-ttu-id="31c5b-109">É possível alterar suas configurações após a configuração inicial no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31c5b-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="31c5b-110">Antes da configuração, certifique-se de planejar a melhor maneira de estabelecer e configurar a compreensão de conteúdo no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="31c5b-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="31c5b-111">Por exemplo, você precisa tomar as seguintes decisões:</span><span class="sxs-lookup"><span data-stu-id="31c5b-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="31c5b-112">Os sites do Microsoft Office SharePoint Online nos quais você deseja habilitar o processamento de formulários - todos, alguns ou sites selecionados</span><span class="sxs-lookup"><span data-stu-id="31c5b-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="31c5b-113">O nome e os administradores do seu centro de conteúdo</span><span class="sxs-lookup"><span data-stu-id="31c5b-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="31c5b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31c5b-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="31c5b-115">Você precisa ter permissões administrativas globais ou de administrador do SharePoint para poder acessar o Centro de administração do Microsoft 365 e configurar o SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="31c5b-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="31c5b-116">Como administrador, também é possível fazer alterações nas configurações selecionadas a qualquer momento após a configuração e ao longo das configurações de gerenciamento de compreensão de conteúdo no Centro de Administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="31c5b-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="31c5b-117">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="31c5b-117">Licensing</span></span>

<span data-ttu-id="31c5b-118">Para usar o SharePoint Syntex, sua organização deve ter uma assinatura do SharePoint Syntex e cada usuário deve ter as seguintes licenças atribuídas:</span><span class="sxs-lookup"><span data-stu-id="31c5b-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="31c5b-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="31c5b-119">SharePoint Syntex</span></span>
- <span data-ttu-id="31c5b-120">SharePoint Syntex - tipo SPO</span><span class="sxs-lookup"><span data-stu-id="31c5b-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="31c5b-121">Serviço de dados comum para SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="31c5b-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="31c5b-122">Se você cancelar sua assinatura do SharePoint Syntex em uma data futura (ou se sua avaliação expirar), os usuários não poderão mais criar ou executar modelos de processamento de formulários ou compreensão de documentos, e o modelo do centro de conteúdo não estará mais disponível.</span><span class="sxs-lookup"><span data-stu-id="31c5b-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="31c5b-123">Além disso, relatórios de armazenamento de termos, importação de taxonomia SKOS e push de tipo de conteúdo não estarão mais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="31c5b-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="31c5b-124">Nenhum conteúdo será excluído e as permissões do site não serão alteradas.</span><span class="sxs-lookup"><span data-stu-id="31c5b-124">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="31c5b-125">Créditos do Construtor de IA</span><span class="sxs-lookup"><span data-stu-id="31c5b-125">AI Builder credits</span></span>

<span data-ttu-id="31c5b-126">Se você tiver 300 ou mais licenças do SharePoint Syntex para o SharePoint Syntex na sua organização, você receberá um milhão de créditos do Construtor de IA.</span><span class="sxs-lookup"><span data-stu-id="31c5b-126">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="31c5b-127">Se você tiver menos de 300 licenças, você deve comprar créditos do Construtor de IA para usar o processamento de formulários.</span><span class="sxs-lookup"><span data-stu-id="31c5b-127">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="31c5b-128">Você pode estimar a capacidade correta do Construtor de IA com a [calculadora do Construtor de IA](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="31c5b-128">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="31c5b-129">Se você planeja usar um ambiente personalizado do Power Platform, deverá [alocar créditos para esse ambiente](/power-platform/admin/capacity-add-on).</span><span class="sxs-lookup"><span data-stu-id="31c5b-129">If you plan to use a custom Power Platform environment, you must [allocate credits to that environment](/power-platform/admin/capacity-add-on).</span></span>

<span data-ttu-id="31c5b-130">Vá até o [Centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.</span><span class="sxs-lookup"><span data-stu-id="31c5b-130">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="31c5b-131">Para configurar o SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="31c5b-131">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="31c5b-132">No centro de administração do Microsoft 365, selecione **Configurar** e visualize a seção **Arquivos e conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-132">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="31c5b-133">Na seção **Arquivos e conteúdo**, selecione **Automatizar a compreensão de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-133">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="31c5b-134">Na página **Compreensão automatizada de conteúdo**, clique em **Começar** para percorrer o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="31c5b-134">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="31c5b-135">![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="31c5b-135">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="31c5b-136">Na página **Configurar Processamento de Formulário**, você pode escolher se quer permitir que os usuários sejam capazes de criar modelos de processamento de formulários em bibliotecas específicas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="31c5b-136">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="31c5b-137">Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **Criar um modelo de processamento de formulário** nas bibliotecas de documentos do SharePoint nas quais ele está ativado.</span><span class="sxs-lookup"><span data-stu-id="31c5b-137">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="31c5b-138">Para **Quais bibliotecas do SharePoint devem exibir a opção para criar um modelo de processamento de formulário**, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="31c5b-138">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="31c5b-139">**Bibliotecas em todos os sites do Microsoft Office SharePoint Online** para torná-lo disponível para todas as bibliotecas do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="31c5b-139">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="31c5b-140">**Bibliotecas em sites selecionados do Microsoft Office SharePoint Online** e, a seguir, selecione os sites nos quais deseja disponibilizá-las ou carregue uma lista de até 50 sites.</span><span class="sxs-lookup"><span data-stu-id="31c5b-140">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="31c5b-141">**Nenhuma biblioteca do SharePoint** se você não deseja torná-lo disponível para nenhum site (você pode alterar isto após a configuração).</span><span class="sxs-lookup"><span data-stu-id="31c5b-141">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="31c5b-142">![Configurar opções do site de processamento de formulário](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="31c5b-142">![Configure form processing site options](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="31c5b-143">A remoção de um site após a sua insalubridade não afeta os modelos existentes aplicados às bibliotecas naquele site ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="31c5b-143">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
    <span data-ttu-id="31c5b-144">Se você tiver vários ambientes do Power Platform configurados, poderá escolher qual deles deseja usar para processamento de formulário.</span><span class="sxs-lookup"><span data-stu-id="31c5b-144">If you have multiple Power Platform environments configured, you can choose which one you want to use with for form processing.</span></span> <span data-ttu-id="31c5b-145">(Essa opção não será exibida se você tiver apenas um ambiente.)</span><span class="sxs-lookup"><span data-stu-id="31c5b-145">(This option will not appear if you only have one environment.)</span></span>

    ![Configurar opções de processamento de formulário do Power Platform](../media/content-understanding/setup-power-platform-env.png)

    <span data-ttu-id="31c5b-147">Para **ambiente do Power Platform**, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="31c5b-147">For **Power Platform environment**, you can select:</span></span>
    - <span data-ttu-id="31c5b-148">**Use o ambiente padrão** para utilizar seu ambiente padrão do Power Platform.</span><span class="sxs-lookup"><span data-stu-id="31c5b-148">**Use the default environment** to use your default Power Platform environment.</span></span>
    - <span data-ttu-id="31c5b-149">**Use um ambiente personalizado** para utilizar um ambiente personalizado.</span><span class="sxs-lookup"><span data-stu-id="31c5b-149">**Use a custom environment** to use a custom environment.</span></span> <span data-ttu-id="31c5b-150">Escolha o ambiente que você deseja usar na lista.</span><span class="sxs-lookup"><span data-stu-id="31c5b-150">Choose the environment that you want to use from the list.</span></span> <span data-ttu-id="31c5b-151">Você deve instalar o aplicativo *AI Builder para Project Cortex* neste ambiente e alocar créditos do AI Builder a ele antes de criar modelos de processamento de formulário.</span><span class="sxs-lookup"><span data-stu-id="31c5b-151">You must install the *AI Builder for Project Cortex* app in this environment and allocate AI Builder credits to it before you can create form processing models.</span></span>

    <span data-ttu-id="31c5b-152">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-152">Click **Next**.</span></span>

5. <span data-ttu-id="31c5b-153">Na página **Criar Centro de Conteúdo**, você pode criar um site de centro de conteúdo do SharePoint, no qual seus usuários poderão criar e gerenciar modelos de compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="31c5b-153">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="31c5b-154">Para **Nome do site**, digite o nome que você quer dar ao site do centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="31c5b-154">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="31c5b-155">O **Endereço do site** mostrará o URL do seu site, baseado no que você selecionou para o nome do site.</span><span class="sxs-lookup"><span data-stu-id="31c5b-155">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="31c5b-156">Se você desejar mudá-lo, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-156">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="31c5b-157">![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="31c5b-157">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="31c5b-158">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-158">Select **Next**.</span></span>

6. <span data-ttu-id="31c5b-159">Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="31c5b-159">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="31c5b-160">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-160">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="31c5b-161">Na página de confirmação, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-161">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="31c5b-162">Você retornará à sua página **Compreensão automatizada de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-162">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="31c5b-163">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="31c5b-163">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="31c5b-164">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="31c5b-164">Assign licenses</span></span>

<span data-ttu-id="31c5b-165">Uma vez configurado o SharePoint Syntex, será necessário atribuir licenças para os usuários que farão uso dos recursos do SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="31c5b-165">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="31c5b-166">Atribuição de licenças:</span><span class="sxs-lookup"><span data-stu-id="31c5b-166">To assign licenses:</span></span>

1. <span data-ttu-id="31c5b-167">No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-167">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="31c5b-168">Selecione os usuários que você deseja licenciar, e escolha **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-168">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="31c5b-169">Escolha **Aplicativos** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="31c5b-169">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="31c5b-170">Selecione **Mostrar aplicativos para o SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-170">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="31c5b-171">Em **Aplicativos**, certifique-se de que **Common Data Service para o SharePoint Syntex**, **SharePoint Syntex** e **SharePoint Syntex - tipo de SPO** estão todos selecionados.</span><span class="sxs-lookup"><span data-stu-id="31c5b-171">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="31c5b-172">![Licenças do SharePoint Syntex no Centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="31c5b-172">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="31c5b-173">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="31c5b-173">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="31c5b-174">Confira também</span><span class="sxs-lookup"><span data-stu-id="31c5b-174">See also</span></span>

<span data-ttu-id="31c5b-175">[Visão geral do modelo de processamento de formulários](/ai-builder/form-processing-model-overview).</span><span class="sxs-lookup"><span data-stu-id="31c5b-175">[Overview of the form processing model](/ai-builder/form-processing-model-overview)</span></span>

[<span data-ttu-id="31c5b-176">Passo a passo: como construir um modelo de compreensão de documentos (vídeo)</span><span class="sxs-lookup"><span data-stu-id="31c5b-176">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

[<span data-ttu-id="31c5b-177">Criar e gerenciar ambientes no centro de administração do Power Platform</span><span class="sxs-lookup"><span data-stu-id="31c5b-177">Create and manage environments in the Power Platform admin center</span></span>](/power-platform/admin/create-environment)
