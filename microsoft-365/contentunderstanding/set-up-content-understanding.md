---
title: 'Configurar a compreensão do conteúdo (versão prévia) '
description: Como configurar o Project Cortex.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612697"
---
# <a name="set-up-content-understanding-preview"></a><span data-ttu-id="194de-103">Configurar a compreensão do conteúdo (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="194de-103">Set up content understanding (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="194de-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="194de-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="194de-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="194de-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="194de-106">Os administradores podem usar o centro de administração do Microsoft 365 para configurar e configurar a compreensão do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="194de-106">Admins can use the Microsoft 365 admin center to set up and configure content understanding.</span></span> 

<span data-ttu-id="194de-107">Antes da instalação, certifique-se de planejar a melhor maneira de configurar e configurar a compreensão do conteúdo em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="194de-107">Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment.</span></span> <span data-ttu-id="194de-108">Por exemplo, você precisará fazer considerações sobre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="194de-108">For example, you will need to make considerations about the following:</span></span>
- <span data-ttu-id="194de-109">Quais sites do SharePoint você habilitará o processamento de formulários?</span><span class="sxs-lookup"><span data-stu-id="194de-109">Which SharePoint sites will you enable form processing?</span></span> <span data-ttu-id="194de-110">Todos eles, alguns ou selecionar sites?</span><span class="sxs-lookup"><span data-stu-id="194de-110">All of them, some, or select sites?</span></span>
- <span data-ttu-id="194de-111">Nome do seu centro de conteúdo e quem é o administrador do site principal?</span><span class="sxs-lookup"><span data-stu-id="194de-111">Name of your content center, and who is the primary site admin?</span></span>

<span data-ttu-id="194de-112">Um administrador também pode fazer alterações nas configurações selecionadas a qualquer momento após a configuração por meio das configurações de gerenciamento de compreensão do conteúdo no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194de-112">An admin can also make changes to your selected settings anytime after setup through the content understanding management settings in the Microsoft 365 admin center.</span></span>


## <a name="requirements"></a><span data-ttu-id="194de-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="194de-113">Requirements</span></span> 
<span data-ttu-id="194de-114">Você precisa ter permissões de administrador global ou administrador do SharePoint para poder acessar o centro de administração do Microsoft 365 e configurar a compreensão do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="194de-114">You must have Global Admin or SharePoint admin permissions to be able to access the Microsoft 365 admin center and set up content understanding.</span></span>


## <a name="to-set-up-content-understanding"></a><span data-ttu-id="194de-115">Para configurar a compreensão do conteúdo</span><span class="sxs-lookup"><span data-stu-id="194de-115">To set up content understanding</span></span>

1. <span data-ttu-id="194de-116">No centro de administração do Microsoft 365, selecione **configuração**e, em seguida, exiba a seção de **conhecimento organizacional** .</span><span class="sxs-lookup"><span data-stu-id="194de-116">In the Microsoft 365 admin center, select **Setup**, and then view the **Organizational knowledge** section.</span></span>
2. <span data-ttu-id="194de-117">Na seção **conhecimento organizacional** , selecione **automatizar a compreensão do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="194de-117">In the **Organizational knowledge** section, select **Automate content understanding**.</span></span><br/>

    ![Página de configuração de conhecimento organizacional](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. <span data-ttu-id="194de-119">Na página **automatizar o conteúdo** **, clique em introdução para** orientá-lo no processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="194de-119">On the **Automate content understanding** page, click **Get started** to walk you through the setup process.</span></span><br/>

    ![Iniciar a instalação](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. <span data-ttu-id="194de-121">Na página **Configurar processamento de formulário** , você pode escolher se deseja permitir que os usuários possam usar o Construtor ai para criar modelos de processamento de formulário em bibliotecas de documentos específicas do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="194de-121">On the **Configure Form Processing** page, you can choose if you want to let users be able to use AI Builder to create form processing models in specific SharePoint document libraries.</span></span> <span data-ttu-id="194de-122">Uma opção de menu estará disponível na faixa de opções da biblioteca de documentos para **criar um modelo de processamento de formulário** em bibliotecas de documentos do SharePoint na qual ele está habilitado.</span><span class="sxs-lookup"><span data-stu-id="194de-122">A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.</span></span>
 
     <span data-ttu-id="194de-123">Para **quais bibliotecas do SharePoint devem mostrar a opção para criar um modelo de processamento de formulário**, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="194de-123">For **Which SharePoint libraries should show option to create a form processing model**, you can select:</span></span></br>
    - <span data-ttu-id="194de-124">**Todas as bibliotecas do SharePoint** para torná-lo disponível para todas as bibliotecas do SharePoint em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="194de-124">**All SharePoint libraries** to make it available to all SharePoint libraries in your tenant.</span></span></br>
    - <span data-ttu-id="194de-125">**Somente as bibliotecas nos sites selecionados**e, em seguida, selecione os sites nos quais você deseja torná-lo disponível.</span><span class="sxs-lookup"><span data-stu-id="194de-125">**Only libraries in selected sites**, and then select the sites in which you want to make it available.</span></span></br>
    - <span data-ttu-id="194de-126">**Nenhuma biblioteca do SharePoint** , se você não quiser disponibilizá-la para nenhum site (você pode alterar isso após a instalação).</span><span class="sxs-lookup"><span data-stu-id="194de-126">**No SharePoint libraries** if you currently don't want to make it available to any sites (you can change this after setup).</span></span>
</br>

   <span data-ttu-id="194de-127">![Configurar o processamento de formulários](../media/content-understanding/admin-configforms.png)
</span><span class="sxs-lookup"><span data-stu-id="194de-127">![Configure form processing](../media/content-understanding/admin-configforms.png)
</span></span></br>

   > [!Note]
   > <span data-ttu-id="194de-128">Habilitar essa configuração em uma biblioteca de documentos do SharePoint não afeta os modelos existentes aplicados à biblioteca ou a capacidade de aplicar modelos de compreensão de documentos a uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="194de-128">Enabling this setting on a SharePoint document library does not affect existing models applied to the library or the ability to apply document understanding models to a library.</span></span> 

    
5. <span data-ttu-id="194de-129">Na página **criar centro de conteúdo** , você pode criar um site do centro de conteúdo do SharePoint no qual os usuários podem criar e gerenciar modelos de compreensão de documentos.</span><span class="sxs-lookup"><span data-stu-id="194de-129">On the **Create Content Center** page, you can create a SharePoint content center site on which your users can create and manage document understanding models.</span></span> </br>
    <span data-ttu-id="194de-130">a.</span><span class="sxs-lookup"><span data-stu-id="194de-130">a.</span></span> <span data-ttu-id="194de-131">Em **nome do site**, digite o nome que você deseja dar ao site do centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="194de-131">For **Site name**, type the name you want to give your content center site.</span></span></br>
    <span data-ttu-id="194de-132">b.</span><span class="sxs-lookup"><span data-stu-id="194de-132">b.</span></span> <span data-ttu-id="194de-133">O **endereço do site** mostrará a URL do seu site, com base no que você selecionou para o nome do site.</span><span class="sxs-lookup"><span data-stu-id="194de-133">The **Site address** will show the URL for your site, based on what you selected for the site name.</span></span></br>

    > [!Note] 
    > <span data-ttu-id="194de-134">Embora seja possível selecionar qualquer idioma suportado, observe que o conteúdo entendendo modelos só pode ser criado para o inglês.</span><span class="sxs-lookup"><span data-stu-id="194de-134">While you can select any supported language, note that content understanding models can only be created for English.</span></span></br>

      ![Criar centro de conteúdo](../media/content-understanding/admin-cu-create-cc.png)</br>


    <span data-ttu-id="194de-136">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="194de-136">Select **Next**.</span></span>
6. <span data-ttu-id="194de-137">Na página **concluir e revisar** , você pode examinar a configuração selecionada e optar por fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="194de-137">On the **Finish and review** page, you can look at your selected setting and choose to make changes.</span></span> <span data-ttu-id="194de-138">Se estiver satisfeito com suas seleções, selecione **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="194de-138">If you are satisfied with your selections, select **Activate**.</span></span>



7. <span data-ttu-id="194de-139">A página **conteúdo de compreensão ativada** será exibida, confirmando que o sistema adicionou suas preferências de processamento de formulário e criando o site do centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="194de-139">The **Content understanding activated** page will display, confirming that the system has added your form processing preferences and creating the Content Center site.</span></span> <span data-ttu-id="194de-140">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="194de-140">Select **Done**.</span></span>

8. <span data-ttu-id="194de-141">Você retornará à página **automatizar o conteúdo de compreensão** .</span><span class="sxs-lookup"><span data-stu-id="194de-141">You'll be returned to your **Automate content understanding** page.</span></span> <span data-ttu-id="194de-142">Nessa página, você pode selecionar **gerenciar** para fazer quaisquer alterações nas suas definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="194de-142">From this page, you can select **Manage** to make any changes to your configuration settings.</span></span> 

## <a name="see-also"></a><span data-ttu-id="194de-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="194de-143">See also</span></span>



  






