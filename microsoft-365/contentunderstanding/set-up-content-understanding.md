---
title: Configuração do SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Configure a compreensão de conteúdo no Projeto Cortex
ms.openlocfilehash: 7fb5998729c9f11902f8fdfaffa62b160928077c
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321344"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="935c4-103">Configuração do SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="935c4-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="935c4-104">Os administradores podem usar o Centro de administração do Microsoft 365 para configurar o [Microsoft SharePoint Syntex](document-understanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="935c4-104">Admins can use the Microsoft 365 admin center to set up [Microsoft SharePoint Syntex](document-understanding-overview.md).</span></span> 

<span data-ttu-id="935c4-105">Considere o seguinte antes de começar:</span><span class="sxs-lookup"><span data-stu-id="935c4-105">Consider the following before you start:</span></span>

- <span data-ttu-id="935c4-106">Em quais sites do SharePoint você vai ativar o processamento de formulários?</span><span class="sxs-lookup"><span data-stu-id="935c4-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="935c4-107">Todos, alguns ou sites selecionados?</span><span class="sxs-lookup"><span data-stu-id="935c4-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="935c4-108">Qual será o nome do seu centro de conteúdo padrão?</span><span class="sxs-lookup"><span data-stu-id="935c4-108">What will you name of your default content center?</span></span>

<span data-ttu-id="935c4-109">É possível alterar suas configurações após a configuração inicial no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="935c4-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="935c4-110">O conteúdo deste artigo é para a visualização do Projeto Particular Cortex.</span><span class="sxs-lookup"><span data-stu-id="935c4-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="935c4-111">[Mais informações sobre o Projeto Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="935c4-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="935c4-112">Antes da configuração, certifique-se de planejar a melhor maneira de estabelecer e configurar a compreensão de conteúdo no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="935c4-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="935c4-113">Por exemplo, você precisa levar em consideração os seguintes nomes de:</span><span class="sxs-lookup"><span data-stu-id="935c4-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="935c4-114">Sites do SharePoint que você deseja ativar o processamento de formulários - todos, alguns ou sites selecionados</span><span class="sxs-lookup"><span data-stu-id="935c4-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="935c4-115">Seu centro de conteúdo e o nome do administrador do site principal</span><span class="sxs-lookup"><span data-stu-id="935c4-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="935c4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="935c4-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="935c4-117">Você deve ter permissões administrativas globais ou de administrador do SharePoint para poder acessar o Centro de administração do Microsoft 365 e configurar a compreensão de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="935c4-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="935c4-118">Como administrador, também é possível fazer alterações nas configurações selecionadas a qualquer momento após a configuração e ao longo das configurações de gerenciamento de compreensão de conteúdo no Centro de Administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="935c4-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="935c4-119">Para configurar o SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="935c4-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="935c4-120">No Centro de administração do Microsoft 365, selecione **Configuração**, e depois veja a seção **Conhecimento organizacional**.</span><span class="sxs-lookup"><span data-stu-id="935c4-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="935c4-121">Na seção **Conhecimento organizacional**, selecione **Compreensão automatizada de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="935c4-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Página de configuração de conhecimento organizacional](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="935c4-123">Na página **Compreensão automatizada de conteúdo**, clique em **Começar** para percorrer o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="935c4-123">On the **Automate content understanding** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="935c4-125">Na página Ativar marcação de imagem, escolha se você quer permitir a [ marcação de imagens](image-tagging.md).</span><span class="sxs-lookup"><span data-stu-id="935c4-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Captura de tela das opções de marcação de imagens](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="935c4-127">Na página **Configurar Processamento de Formulário**, você pode escolher se quer permitir que os usuários sejam capazes de criar modelos de processamento de formulários em bibliotecas específicas de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="935c4-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="935c4-128">Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **Criar um modelo de processamento de formulário** nas bibliotecas de documentos do SharePoint nas quais ele está ativado.</span><span class="sxs-lookup"><span data-stu-id="935c4-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="935c4-129">Para **Quais bibliotecas do SharePoint devem exibir a opção para criar um modelo de processamento de formulário**, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="935c4-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="935c4-130">**Todas as bibliotecas do SharePoint** para torná-lo disponível em todas as bibliotecas do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="935c4-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="935c4-131">**Bibliotecas somente em sites selecionados**, e então selecione os sites nos quais você quer disponibilizá-lo ou carregue uma lista de até 50 sites.</span><span class="sxs-lookup"><span data-stu-id="935c4-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available or upload a list of up to 50 sites.</span></span></br>
      - <span data-ttu-id="935c4-132">**Nenhuma biblioteca do SharePoint** se você não deseja torná-lo disponível para nenhum site (você pode alterar isto após a configuração).</span><span class="sxs-lookup"><span data-stu-id="935c4-132">**No SharePoint libraries** if you don't want to make it available to any sites (you can change this after setup).</span></span>

   ![Configurar o processamento de formulário](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="935c4-134">A remoção de um site após a sua insalubridade não afeta os modelos existentes aplicados às bibliotecas naquele site ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="935c4-134">Removing a site after it has been included does not affect existing models applied to the libraries in that site or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="935c4-135">Na página **Criar Centro de Conteúdo**, você pode criar um site de centro de conteúdo do SharePoint, no qual seus usuários poderão criar e gerenciar modelos de compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="935c4-135">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="935c4-136">a.</span><span class="sxs-lookup"><span data-stu-id="935c4-136">a.</span></span> <span data-ttu-id="935c4-137">Para **Nome do site**, digite o nome que você quer dar ao seu site do centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="935c4-137">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="935c4-138">b.</span><span class="sxs-lookup"><span data-stu-id="935c4-138">b.</span></span> <span data-ttu-id="935c4-139">O **Endereço do site** mostrará o URL do seu site, baseado no que você selecionou para o nome do site.</span><span class="sxs-lookup"><span data-stu-id="935c4-139">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="935c4-140">Se você desejar mudá-lo, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="935c4-140">If you want to change it, click **Edit**.</span></span></br>

      ![Crie um centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="935c4-142">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="935c4-142">Select **Next**.</span></span>

7. <span data-ttu-id="935c4-143">Na página **Revisão e acabamento**, você pode olhar para a configuração selecionada e escolher fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="935c4-143">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="935c4-144">Se estiver satisfeito com as suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="935c4-144">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="935c4-145">Na página de confirmação, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="935c4-145">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="935c4-146">Você retornará à sua página **Compreensão automatizada de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="935c4-146">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="935c4-147">A partir desta página, é possível selecionar **Gerenciar** para fazer quaisquer alterações em suas configurações.</span><span class="sxs-lookup"><span data-stu-id="935c4-147">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="935c4-148">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="935c4-148">Assign licenses</span></span>

<span data-ttu-id="935c4-149">Uma vez configurado o SharePoint Syntex, será necessário atribuir licenças para os usuários que farão uso dos recursos do SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="935c4-149">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using any SharePoint Syntex features.</span></span>

<span data-ttu-id="935c4-150">Atribuição de licenças:</span><span class="sxs-lookup"><span data-stu-id="935c4-150">To assign licenses:</span></span>

1. <span data-ttu-id="935c4-151">No Centro de administração do Microsoft 365, em **Usuários**, clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="935c4-151">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="935c4-152">Selecione os usuários que você deseja licenciar, e clique **Gerenciar licenças de produtos**.</span><span class="sxs-lookup"><span data-stu-id="935c4-152">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="935c4-153">Selecione **Atribuir mais**.</span><span class="sxs-lookup"><span data-stu-id="935c4-153">Select **Assign more**.</span></span>

4. <span data-ttu-id="935c4-154">Selecione **Serviços de Conteúdo Inteligente**.</span><span class="sxs-lookup"><span data-stu-id="935c4-154">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="935c4-155">Em **Aplicativos**, certifique-se de que **Serviço de Dados Comum para Serviços de Conteúdo Inteligente** e **Serviços de Conteúdo Inteligente** estejam ambos selecionados.</span><span class="sxs-lookup"><span data-stu-id="935c4-155">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Licenças do SharePoint Syntex no Centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="935c4-157">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="935c4-157">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="935c4-158">Créditos do Construtor de IA</span><span class="sxs-lookup"><span data-stu-id="935c4-158">AI Builder credits</span></span>

<span data-ttu-id="935c4-159">Se você tiver 300 ou mais licenças do SharePoint Syntex para o SharePoint Syntex na sua organização, você receberá um milhão de créditos do Construtor de IA.</span><span class="sxs-lookup"><span data-stu-id="935c4-159">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="935c4-160">Se você tiver menos de 300 licenças, você deve comprar créditos do Construtor de IA para usar o processamento de formulários.</span><span class="sxs-lookup"><span data-stu-id="935c4-160">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="935c4-161">Você pode estimar a capacidade correta do Construtor de IA com a [calculadora do Construtor de IA](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="935c4-161">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="935c4-162">Vá até o [Centro de administração da Plataforma Power ](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.</span><span class="sxs-lookup"><span data-stu-id="935c4-162">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="935c4-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="935c4-163">See also</span></span>

<span data-ttu-id="935c4-164">[Visão geral do modelo de processamento de formulários](https://docs.microsoft.com/ai-builder/form-processing-model-overview).</span><span class="sxs-lookup"><span data-stu-id="935c4-164">[Overview of the form processing model](https://docs.microsoft.com/ai-builder/form-processing-model-overview)</span></span>

[<span data-ttu-id="935c4-165">Passo a passo: como construir um modelo de compreensão de documentos (vídeo)</span><span class="sxs-lookup"><span data-stu-id="935c4-165">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

