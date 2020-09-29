---
title: Configurar o SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Configurar a compreensão do conteúdo no Project Cortex
ms.openlocfilehash: 31c6b6dd31b3f1bc47deb8424dd847cc0af6d429
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304775"
---
# <a name="set-up-sharepoint-syntex"></a><span data-ttu-id="70f88-103">Configurar o SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="70f88-103">Set up SharePoint Syntex</span></span>

<span data-ttu-id="70f88-104">Os administradores podem usar o centro de administração do Microsoft 365 para configurar o e o Microsoft SharePoint Syntex.</span><span class="sxs-lookup"><span data-stu-id="70f88-104">Admins can use the Microsoft 365 admin center to set up and Microsoft SharePoint Syntex.</span></span> 

<span data-ttu-id="70f88-105">Antes de começar, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="70f88-105">Consider the following before you start:</span></span>

- <span data-ttu-id="70f88-106">Quais sites do SharePoint você habilitará o processamento de formulários?</span><span class="sxs-lookup"><span data-stu-id="70f88-106">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="70f88-107">Todos eles, alguns ou selecionar sites?</span><span class="sxs-lookup"><span data-stu-id="70f88-107">All of them, some, or select sites?</span></span>
- <span data-ttu-id="70f88-108">Qual será o nome do seu centro de conteúdo e quem é o administrador do site principal?</span><span class="sxs-lookup"><span data-stu-id="70f88-108">What will you name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="70f88-109">Você pode alterar suas configurações após a configuração inicial no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70f88-109">You can change your settings after initial setup in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="70f88-110">O conteúdo deste artigo é para a visualização privada do projeto Cortex.</span><span class="sxs-lookup"><span data-stu-id="70f88-110">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="70f88-111">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="70f88-111">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="70f88-112">Antes da instalação, certifique-se de planejar a melhor maneira de configurar e configurar a compreensão do conteúdo em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="70f88-112">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="70f88-113">Por exemplo, você precisa fazer considerações sobre os seguintes nomes:</span><span class="sxs-lookup"><span data-stu-id="70f88-113">For example, you need to make considerations about the following names of:</span></span>

- <span data-ttu-id="70f88-114">Os sites do SharePoint que você deseja habilitar o processamento de formulários, alguns ou sites selecionados</span><span class="sxs-lookup"><span data-stu-id="70f88-114">The SharePoint sites that you want to enable form processing - all of them, some, or selected sites</span></span>
- <span data-ttu-id="70f88-115">Seu centro de conteúdo e o nome do administrador do site principal</span><span class="sxs-lookup"><span data-stu-id="70f88-115">Your content center and the name of the primary site admin</span></span>

## <a name="requirements"></a><span data-ttu-id="70f88-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70f88-116">Requirements</span></span> 

> [!NOTE]
> <span data-ttu-id="70f88-117">Você precisa ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e configurar a compreensão do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="70f88-117">You must have Global admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>

<span data-ttu-id="70f88-118">Como administrador, você também pode fazer alterações nas configurações selecionadas a qualquer momento após a instalação, e por todo o conteúdo entendendo as configurações de gerenciamento no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70f88-118">As an admin, you can also make changes to your selected settings anytime after setup, and throughout the content understanding management settings in the Microsoft 365 Admin Center.</span></span>

## <a name="to-set-up-sharepoint-syntex"></a><span data-ttu-id="70f88-119">Para configurar o SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="70f88-119">To set up SharePoint Syntex</span></span>

1. <span data-ttu-id="70f88-120">No centro de administração do Microsoft 365, selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .</span><span class="sxs-lookup"><span data-stu-id="70f88-120">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>

2. <span data-ttu-id="70f88-121">Na seção **conhecimento organizacional** , selecione **automatizar a compreensão do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="70f88-121">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Página de configuração de conhecimento organizacional](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="70f88-123">Na página **automatizar o SharePoint Syntex** , clique em **começar** para percorrer o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="70f88-123">On the **Automate SharePoint Syntex** page, click **Get started** to walk through the setup process.</span></span><br/>

    ![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. <span data-ttu-id="70f88-125">Na página ativar marcação de imagem, escolha se deseja permitir a [marcação de imagem](image-tagging.md).</span><span class="sxs-lookup"><span data-stu-id="70f88-125">On the Turn on image tagging page, choose if you want to allow [image tagging](image-tagging.md).</span></span>

    ![Captura de tela das opções de marcação de imagem](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. <span data-ttu-id="70f88-127">Na página **Configurar processamento de formulário** , você pode escolher se deseja permitir que os usuários possam usar o Construtor ai para criar modelos de processamento de formulário em bibliotecas de documentos específicas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="70f88-127">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="70f88-128">Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **criar um modelo de processamento de formulário** em bibliotecas de documentos do SharePoint na qual ele está habilitado.</span><span class="sxs-lookup"><span data-stu-id="70f88-128">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="70f88-129">Para **quais bibliotecas do SharePoint devem mostrar a opção para criar um modelo de processamento de formulário**, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="70f88-129">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
      - <span data-ttu-id="70f88-130">**Todas as bibliotecas do SharePoint** para torná-lo disponível para todas as bibliotecas do SharePoint em sua organização.</span><span class="sxs-lookup"><span data-stu-id="70f88-130">**All SharePoint libraries** to make it available to all SharePoint libraries in your organization.</span></span></br>
      - <span data-ttu-id="70f88-131">**Somente as bibliotecas nos sites selecionados**e, em seguida, selecione os sites nos quais você deseja torná-lo disponível.</span><span class="sxs-lookup"><span data-stu-id="70f88-131">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>

   ![Configurar o processamento de formulários](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > <span data-ttu-id="70f88-133">Habilitar essa configuração em uma biblioteca de documentos do SharePoint não afeta os modelos existentes aplicados à biblioteca ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="70f88-133">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 
    
6. <span data-ttu-id="70f88-134">Na página **criar centro de conteúdo** , você pode criar um site do centro de conteúdo do SharePoint no qual os usuários podem criar e gerenciar modelos de compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="70f88-134">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="70f88-135">a.</span><span class="sxs-lookup"><span data-stu-id="70f88-135">a.</span></span> <span data-ttu-id="70f88-136">Em **nome do site**, digite o nome que você deseja dar ao site do centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="70f88-136">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="70f88-137">b.</span><span class="sxs-lookup"><span data-stu-id="70f88-137">b.</span></span> <span data-ttu-id="70f88-138">O **endereço do site** mostrará a URL do seu site, com base no que você selecionou para o nome do site.</span><span class="sxs-lookup"><span data-stu-id="70f88-138">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span> <span data-ttu-id="70f88-139">Se você quiser alterá-lo, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="70f88-139">If you want to change it, click **Edit**.</span></span></br>

      ![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>

    <span data-ttu-id="70f88-141">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="70f88-141">Select **Next**.</span></span>

7. <span data-ttu-id="70f88-142">Na página **revisão e término** , você pode examinar a configuração selecionada e optar por fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="70f88-142">On the **Review and finish** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="70f88-143">Se estiver satisfeito com suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="70f88-143">If you are satisfied with your selections, select **Activate**.</span></span>

8. <span data-ttu-id="70f88-144">Na página confirmação, clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="70f88-144">On the confirmation page, click **Done**.</span></span>

9. <span data-ttu-id="70f88-145">Você retornará à página **automatizar o conteúdo de compreensão** .</span><span class="sxs-lookup"><span data-stu-id="70f88-145">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="70f88-146">Nessa página, você pode selecionar **gerenciar** para fazer quaisquer alterações nas suas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="70f88-146">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="assign-licenses"></a><span data-ttu-id="70f88-147">Atribua licenças</span><span class="sxs-lookup"><span data-stu-id="70f88-147">Assign licenses</span></span>

<span data-ttu-id="70f88-148">Depois de configurar o SharePoint Syntex, você deve atribuir licenças para os usuários que utilizarão o processamento de formulários e os recursos de compreensão do documento.</span><span class="sxs-lookup"><span data-stu-id="70f88-148">Once you have configured SharePoint Syntex, you must assign licenses for the users who will be using form processing and document understanding features.</span></span>

<span data-ttu-id="70f88-149">Para atribuir licenças:</span><span class="sxs-lookup"><span data-stu-id="70f88-149">To assign licenses:</span></span>

1. <span data-ttu-id="70f88-150">No centro de administração do Microsoft 365, em **usuários**, clique em **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="70f88-150">In the Microsoft 365 admin center, under **Users**, click **Active users**.</span></span>

2. <span data-ttu-id="70f88-151">Selecione os usuários que você deseja licenciar e clique em **gerenciar licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="70f88-151">Select the users that you want to license, and click **Manage product licenses**.</span></span>

3. <span data-ttu-id="70f88-152">Selecione **atribuir mais**.</span><span class="sxs-lookup"><span data-stu-id="70f88-152">Select **Assign more**.</span></span>

4. <span data-ttu-id="70f88-153">Selecione **serviços de conteúdo inteligente**.</span><span class="sxs-lookup"><span data-stu-id="70f88-153">Select **Intelligent Content Services**.</span></span> <span data-ttu-id="70f88-154">Em **aplicativos**, verifique se o **serviço de dados comuns para serviços de conteúdo inteligente** e **serviços de conteúdo inteligente** estão selecionados.</span><span class="sxs-lookup"><span data-stu-id="70f88-154">Under **Apps**, make sure **Common Data Service for Intelligent Content Services** and **Intelligent Content Services** are both selected.</span></span>

    ![Licenças do Syntex do SharePoint no centro de administração do Microsoft 365](../media/content-understanding/sharepoint-syntex-licenses.png)

5. <span data-ttu-id="70f88-156">Clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="70f88-156">Click **Save changes**.</span></span>

## <a name="ai-builder-credits"></a><span data-ttu-id="70f88-157">Créditos do Construtor AI</span><span class="sxs-lookup"><span data-stu-id="70f88-157">AI Builder credits</span></span>

<span data-ttu-id="70f88-158">Se você tiver 300 ou mais licenças do Syntex do SharePoint para o SharePoint Syntex em sua organização, serão alocados os créditos do Construtor AI de 1 milhão.</span><span class="sxs-lookup"><span data-stu-id="70f88-158">If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits.</span></span> <span data-ttu-id="70f88-159">Se você tiver menos de 300 licenças, deverá adquirir créditos do Construtor AI para usar o processamento de formulários.</span><span class="sxs-lookup"><span data-stu-id="70f88-159">If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.</span></span>

<span data-ttu-id="70f88-160">Você pode estimar a capacidade do Construtor AI mais adequada para a [calculadora do ai Builder](https://powerapps.microsoft.com/ai-builder-calculator).</span><span class="sxs-lookup"><span data-stu-id="70f88-160">You can estimate the AI Builder capacity that’s right for you with the [AI Builder calculator](https://powerapps.microsoft.com/ai-builder-calculator).</span></span>

<span data-ttu-id="70f88-161">Vá para o [centro de administração da plataforma de energia](https://admin.powerplatform.microsoft.com/resources/capacity) para verificar seus créditos e uso.</span><span class="sxs-lookup"><span data-stu-id="70f88-161">Go to the [Power Platform admin center](https://admin.powerplatform.microsoft.com/resources/capacity) to check your credits and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="70f88-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="70f88-162">See also</span></span>

[<span data-ttu-id="70f88-163">Visão geral do modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="70f88-163">Overview of the form processing model</span></span>](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[<span data-ttu-id="70f88-164">Passo a passo: como criar um documento entendendo o modelo (vídeo)</span><span class="sxs-lookup"><span data-stu-id="70f88-164">Step-by-Step: How to Build a Document Understanding Model (video)</span></span>](https://www.youtube.com/watch?v=DymSHObD-bg)

