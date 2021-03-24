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
ms.openlocfilehash: cc6fbfbfc130cc6e64b5d7c30e0a9db5f39036ac
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051562"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="6b027-103">Configuração do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="6b027-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="6b027-104">Os administradores podem usar o Centro de administração do Microsoft 365 para configurar o [Microsoft SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="6b027-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](index.md).</span></span> 

<span data-ttu-id="6b027-105">Considere o seguinte antes de começar:</span><span class="sxs-lookup"><span data-stu-id="6b027-105">Consider the following before you start:</span></span>

- <span data-ttu-id="6b027-106">Em quais sites do Microsoft Office SharePoint Online você habilitará o processamento de formulários?</span><span class="sxs-lookup"><span data-stu-id="6b027-106">In which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="6b027-107">Todos, alguns ou sites selecionados?</span><span class="sxs-lookup"><span data-stu-id="6b027-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="6b027-108">Como você nomeará seu centro de conteúdo padrão?</span><span class="sxs-lookup"><span data-stu-id="6b027-108">What will you name your default content center?</span></span>

<span data-ttu-id="6b027-109">É possível alterar suas configurações após a configuração inicial no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b027-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="6b027-110">Antes da configuração, certifique-se de planejar a melhor maneira de estabelecer e configurar a compreensão de conteúdo no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="6b027-110">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="6b027-111">Por exemplo, você precisa tomar as seguintes decisões:</span><span class="sxs-lookup"><span data-stu-id="6b027-111">For example, you need to make the following decisions:</span></span>

- <span data-ttu-id="6b027-112">Os sites do Microsoft Office SharePoint Online nos quais você deseja habilitar o processamento de formulários - todos, alguns ou sites selecionados</span><span class="sxs-lookup"><span data-stu-id="6b027-112">The SharePoint sites in which you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="6b027-113">O nome e os administradores do seu centro de conteúdo</span><span class="sxs-lookup"><span data-stu-id="6b027-113">The name and admins for your content center</span></span>

## <a name="requirements"></a><span data-ttu-id="6b027-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b027-114">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="6b027-115">Você precisa ter permissões administrativas globais ou de administrador do SharePoint para poder acessar o Centro de administração do Microsoft 365 e configurar o SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="6b027-115">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up SharePoint Syntex.</span></span>

<span data-ttu-id="6b027-116">Como administrador, também é possível fazer alterações nas configurações selecionadas a qualquer momento após a configuração e ao longo das configurações de gerenciamento de compreensão de conteúdo no Centro de Administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6b027-116">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

### <a name="licensing"></a><span data-ttu-id="6b027-117">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="6b027-117">Licensing</span></span>

<span data-ttu-id="6b027-118">Para usar o SharePoint Syntex, sua organização deve ter uma assinatura do SharePoint Syntex e cada usuário deve ter as seguintes licenças atribuídas:</span><span class="sxs-lookup"><span data-stu-id="6b027-118">To use SharePoint Syntex, your organization must have a subscription to SharePoint Syntex, and each user must have the following licenses assigned:</span></span>

- <span data-ttu-id="6b027-119">SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="6b027-119">SharePoint Syntex</span></span>
- <span data-ttu-id="6b027-120">SharePoint Syntex - tipo SPO</span><span class="sxs-lookup"><span data-stu-id="6b027-120">SharePoint Syntex - SPO type</span></span>
- <span data-ttu-id="6b027-121">Serviço de dados comum para SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="6b027-121">Common Data Service for SharePoint Syntex</span></span>

<span data-ttu-id="6b027-122">Se você cancelar sua assinatura do SharePoint Syntex em uma data futura (ou se sua avaliação expirar), os usuários não poderão mais criar ou executar modelos de processamento de formulários ou compreensão de documentos, e o modelo do centro de conteúdo não estará mais disponível.</span><span class="sxs-lookup"><span data-stu-id="6b027-122">If you cancel your SharePoint Syntex subscription at a future date (or your trial expires), users will no longer be able to create or run document understanding or form processing models, and the content center template will no longer be available.</span></span> <span data-ttu-id="6b027-123">Além disso, relatórios de armazenamento de termos, importação de taxonomia SKOS e push de tipo de conteúdo não estarão mais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6b027-123">Additionally, term store reports, SKOS taxonomy import, and Content type push will no longer be available.</span></span> <span data-ttu-id="6b027-124">Nenhum conteúdo será excluído e as permissões do site não serão alteradas.</span><span class="sxs-lookup"><span data-stu-id="6b027-124">No content will be deleted and site permissions will not be changed.</span></span>

### <a name="ai-builder-credits"></a><span data-ttu-id="6b027-125">Créditos do Construtor de IA</span><span class="sxs-lookup"><span data-stu-id="6b027-125">AI Builder credits</span></span>

<span data-ttu-id="6b027-126">Se você tiver 300 ou mais licenças do SharePoint Syntex para o SharePoint Syntex na sua organização, você receberá um milhão de créditos do Construtor de IA.</span><span class="sxs-lookup"><span data-stu-id="6b027-126">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="6b027-127">Se você tiver menos de 300 licenças, você deve comprar créditos do Construtor de IA para usar o processamento de formulários.</span><span class="sxs-lookup"><span data-stu-id="6b027-127">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="6b027-128">Você pode estimar a capacidade correta do Construtor de IA com a [calculadora do Construtor de IA](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="6b027-128">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="6b027-129">Vá até o [Centro de administração da Plataforma Power ](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.</span><span class="sxs-lookup"><span data-stu-id="6b027-129">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="6b027-130">Para configurar o SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="6b027-130">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="6b027-131">No centro de administração do Microsoft 365, selecione **Configurar** e visualize a seção **Arquivos e conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="6b027-131">In the Microsoft 365 admin center, select **Setup**, and then view the **Files and content** section.</span></span>

2. <span data-ttu-id="6b027-132">Na seção **Arquivos e conteúdo**, selecione **Automatizar a compreensão de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="6b027-132">In the **Files and content** section, select **Automate content understanding**.</span></span><br/>

3. <span data-ttu-id="6b027-133">Na página **Compreensão automatizada de conteúdo**, clique em **Começar** para percorrer o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="6b027-133">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b027-134">![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</span><span class="sxs-lookup"><span data-stu-id="6b027-134">![Begin setup](../media/content-understanding/admin-content-understanding-get-started.png)</span></span></br>

4. <span data-ttu-id="6b027-135">Na página **Configurar Processamento de Formulário**, você pode escolher se quer permitir que os usuários sejam capazes de criar modelos de processamento de formulários em bibliotecas específicas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6b027-135">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="6b027-136">Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **Criar um modelo de processamento de formulário** nas bibliotecas de documentos do SharePoint nas quais ele está ativado.</span><span class="sxs-lookup"><span data-stu-id="6b027-136">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="6b027-137">Para **Quais bibliotecas do SharePoint devem exibir a opção para criar um modelo de processamento de formulário**, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="6b027-137">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="6b027-138">**Bibliotecas em todos os sites do Microsoft Office SharePoint Online** para torná-lo disponível para todas as bibliotecas do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b027-138">**Libraries in all SharePoint sites** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="6b027-139">**Bibliotecas em sites selecionados do Microsoft Office SharePoint Online** e, a seguir, selecione os sites nos quais deseja disponibilizá-las ou carregue uma lista de até 50 sites.</span><span class="sxs-lookup"><span data-stu-id="6b027-139">**Libraries in selected SharePoint sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="6b027-140">**Nenhuma biblioteca do SharePoint** se você não deseja torná-lo disponível para nenhum site (você pode alterar isto após a configuração).</span><span class="sxs-lookup"><span data-stu-id="6b027-140">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b027-141">![Configurar o processamento de formulário](../media/content-understanding/admin-configforms.png)</span><span class="sxs-lookup"><span data-stu-id="6b027-141">![Configure form processing](../media/content-understanding/admin-configforms.png)</span></span>

   > [!Note]
   > <span data-ttu-id="6b027-142">A remoção de um site após a sua insalubridade não afeta os modelos existentes aplicados às bibliotecas naquele site ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6b027-142">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
5. <span data-ttu-id="6b027-143">Na página **Criar Centro de Conteúdo**, você pode criar um site de centro de conteúdo do SharePoint, no qual seus usuários poderão criar e gerenciar modelos de compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="6b027-143">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span>

    1. <span data-ttu-id="6b027-144">Para **Nome do site**, digite o nome que você quer dar ao site do centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6b027-144">For **Site name**, type the name you want to give your content center site.</span></span>
    
    1. <span data-ttu-id="6b027-145">O **Endereço do site** mostrará o URL do seu site, baseado no que você selecionou para o nome do site.</span><span class="sxs-lookup"><span data-stu-id="6b027-145">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="6b027-146">Se você desejar mudá-lo, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6b027-146">If you want to change it, click **Edit**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="6b027-147">![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</span><span class="sxs-lookup"><span data-stu-id="6b027-147">![Create content center](../media/content-understanding/admin-cu-create-cc.png)</span></span></br>

       <span data-ttu-id="6b027-148">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6b027-148">Select **Next**.</span></span>

6. <span data-ttu-id="6b027-149">Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="6b027-149">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="6b027-150">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="6b027-150">If you are satisfied with your selections, select **Activate**.</span></span>

7. <span data-ttu-id="6b027-151">Na página de confirmação, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="6b027-151">On the confirmation page, click **Done**.</span></span>

8. <span data-ttu-id="6b027-152">Você retornará à sua página **Compreensão automatizada de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="6b027-152">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="6b027-153">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="6b027-153">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="6b027-154">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="6b027-154">Assign licenses</span></span>

<span data-ttu-id="6b027-155">Uma vez configurado o SharePoint Syntex, será necessário atribuir licenças para os usuários que farão uso dos recursos do SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="6b027-155">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="6b027-156">Atribuição de licenças:</span><span class="sxs-lookup"><span data-stu-id="6b027-156">To assign licenses:</span></span>

1. <span data-ttu-id="6b027-157">No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="6b027-157">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="6b027-158">Selecione os usuários que você deseja licenciar, e escolha **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="6b027-158">Select the users that you want to license, and choose **Manage product licenses**.</span></span>

3. <span data-ttu-id="6b027-159">Escolha **Aplicativos** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="6b027-159">Choose **Apps** from the drop-down menu.</span></span>

4. <span data-ttu-id="6b027-160">Selecione **Mostrar aplicativos para o SharePoint Syntex**.</span><span class="sxs-lookup"><span data-stu-id="6b027-160">Select **Show apps for  SharePoint Syntex**.</span></span> <span data-ttu-id="6b027-161">Em **Aplicativos**, certifique-se de que **Common Data Service para o SharePoint Syntex**, **SharePoint Syntex** e **SharePoint Syntex - tipo de SPO** estão todos selecionados.</span><span class="sxs-lookup"><span data-stu-id="6b027-161">Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6b027-162">![Licenças do SharePoint Syntex no Centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)</span><span class="sxs-lookup"><span data-stu-id="6b027-162">![SharePoint Syntex licenses in the Microsoft 365 admin center](../media/content-understanding/sharepoint-syntex-licenses.png)</span></span>

5. <span data-ttu-id="6b027-163">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="6b027-163">Click **Save changes**.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b027-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="6b027-164">See also</span></span>

<span data-ttu-id="6b027-165">[Visão geral do modelo de processamento de formulários](/ai-builder/form-processing-model-overview).</span><span class="sxs-lookup"><span data-stu-id="6b027-165">[Overview of the form processing model](/ai-builder/form-processing-model-overview)</span></span>

[<span data-ttu-id="6b027-166">Passo a passo: como construir um modelo de compreensão de documentos (vídeo)</span><span class="sxs-lookup"><span data-stu-id="6b027-166">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)
