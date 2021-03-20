---
title: Criar um centro de conteúdo no Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Aprenda a criar um centro de conteúdo.
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905819"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="35236-103">Criar um centro de conteúdo no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="35236-103">Create a content center in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="35236-104">Para criar e gerenciar modelos de compreensão de documentos, primeiro é necessário um centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="35236-104">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="35236-105">O centro de conteúdo é a interface de criação do modelo e também contém informações sobre as bibliotecas de documentos às quais os modelos publicados foram aplicados.</span><span class="sxs-lookup"><span data-stu-id="35236-105">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Selecionar uma biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="35236-107">Você cria um centro de conteúdo padrão durante a[configuração](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="35236-107">You create a default content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="35236-108">No entanto, um administrador do SharePoint também pode optar por criar centros adicionais conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="35236-108">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="35236-109">Embora um único centro de conteúdo possa ser bom para ambientes para os quais você deseja obter uma distribuição de todas as atividades do modelo, talvez você queira ter centros adicionais para vários departamentos dentro da organização, o que pode ter necessidades e requisitos de permissão diferentes para seus modelos.</span><span class="sxs-lookup"><span data-stu-id="35236-109">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and permission requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="35236-110">Em um [Ambiente Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md), se você tiver um único centro de conteúdo padrão em seu local central, só poderá fornecer uma rolagem da atividade do modelo de dentro desse local.</span><span class="sxs-lookup"><span data-stu-id="35236-110">In a [Microsoft 365 Multi-Geo environment](../enterprise/microsoft-365-multi-geo.md), if you have a single default content center in your central location, you can only provide a roll-up of model activity from within that location.</span></span> <span data-ttu-id="35236-111">Atualmente, você não pode obter um roll-up da atividade do modelo através dos limites da fazenda em um ambiente Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="35236-111">You currently cannot get a roll-up of model activity across farm-boundaries in Multi-Geo environment.</span></span> 


## <a name="create-a-content-center"></a><span data-ttu-id="35236-112">Criar um centro de conteúdo</span><span class="sxs-lookup"><span data-stu-id="35236-112">Create a content center</span></span>

<span data-ttu-id="35236-113">Um administrador do SharePoint pode criar um site de centro de conteúdo como [criar qualquer outro site do SharePoint](/sharepoint/create-site-collection) por meio do painel de provisionamento do site do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="35236-113">A SharePoint admin can create a content center site like they would [create any other SharePoint site](/sharepoint/create-site-collection) through the admin center site provisioning panel.</span></span>

<span data-ttu-id="35236-114">Para criar um novo tipo de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="35236-114">To create a new content center:</span></span>

1. <span data-ttu-id="35236-115">No centro de administração do Microsoft 365, acesse o centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="35236-115">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>

2. <span data-ttu-id="35236-116">No novo Centro de administração do SharePoint, em **Sites**, selecione **Sites Ativos**.</span><span class="sxs-lookup"><span data-stu-id="35236-116">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>

3. <span data-ttu-id="35236-117">Na página **Sites Ativos**, clique em **Criar** e selecione **Outras opções**.</span><span class="sxs-lookup"><span data-stu-id="35236-117">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>

4. <span data-ttu-id="35236-118">No menu **Escolha um modelo**, selecione **Centro de Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="35236-118">On the **Choose a template** menu, select **Content Center**.</span></span>

5. <span data-ttu-id="35236-119">Forneça um **Nome de Site**, **Administrador principal** e um **Idioma** para o novo site.</span><span class="sxs-lookup"><span data-stu-id="35236-119">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

   > [!NOTE] 
   > <span data-ttu-id="35236-120">Você pode selecionar um site de centro de conteúdo para renderizar em qualquer um dos idiomas disponíveis, mas observe que modelos, no momento, só podem ser criados para arquivos em inglês.</span><span class="sxs-lookup"><span data-stu-id="35236-120">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span> <span data-ttu-id="35236-121">Além disso, observe que, como outros modelos de site, o idioma padrão do site não é editável após o site ser criado.</span><span class="sxs-lookup"><span data-stu-id="35236-121">Also note that like other site templates, the default site language isn't editable after the site is created.</span></span></br>

6. <span data-ttu-id="35236-122">Marque **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="35236-122">Select **Finished**.</span></span>
 
<span data-ttu-id="35236-123">Depois de criar um site de centro de conteúdo, você o verá listado na página **Sites Ativos** no centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="35236-123">After you create a content center site, you will see it listed on the **Active sites** page in the SharePoint admin center.</span></span> 

### <a name="give-access-to-additional-users"></a><span data-ttu-id="35236-124">Conceder acesso a usuários adicionais</span><span class="sxs-lookup"><span data-stu-id="35236-124">Give access to additional users</span></span>
 
<span data-ttu-id="35236-125">Depois de criar o site, você pode permitir que os usuários adicionais acessem o site por meio do[modelo de permissões de site do SharePoint.](/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="35236-125">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="35236-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="35236-126">See Also</span></span>
[<span data-ttu-id="35236-127">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="35236-127">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="35236-128">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="35236-128">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="35236-129">Criar um centro de conteúdo</span><span class="sxs-lookup"><span data-stu-id="35236-129">Create a content center</span></span>](create-a-content-center.md)

[<span data-ttu-id="35236-130">Visão geral compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="35236-130">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="35236-131">Criar um modelo de processamento de formulário</span><span class="sxs-lookup"><span data-stu-id="35236-131">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="35236-132">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="35236-132">Apply a model</span></span>](apply-a-model.md)