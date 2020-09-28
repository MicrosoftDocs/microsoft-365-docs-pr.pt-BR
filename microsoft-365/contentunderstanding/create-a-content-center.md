---
title: Criar um centro de conteúdo no Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como criar um centro de conteúdo.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295427"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="8961e-103">Criar um centro de conteúdo no Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="8961e-103">Create a content center in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="8961e-104">O conteúdo deste artigo é para a visualização privada do projeto Cortex.</span><span class="sxs-lookup"><span data-stu-id="8961e-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="8961e-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="8961e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="8961e-106">Para criar e gerenciar modelos de compreensão de documentos, primeiro você precisa de um centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8961e-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="8961e-107">O centro de conteúdo é a interface de criação de modelo e também contém informações sobre quais modelos publicados de bibliotecas de documentos foram aplicados.</span><span class="sxs-lookup"><span data-stu-id="8961e-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied to.</span></span></br>

   ![Selecionar uma biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="8961e-109">Você cria um centro de conteúdo inicial durante [a configuração](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="8961e-109">You create an initial content center during [setup](set-up-content-understanding.md).</span></span> <span data-ttu-id="8961e-110">Mas um administrador do SharePoint também pode optar por criar centros adicionais, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8961e-110">But a SharePoint admin can also choose to create additional centers as needed.</span></span> <span data-ttu-id="8961e-111">Embora um único centro de conteúdo possa ser bom para ambientes para os quais você deseja um lançamento de toda a atividade do modelo, talvez você queira ter centros adicionais para vários departamentos em sua organização, que podem ter necessidades e requisitos diferentes para seus modelos.</span><span class="sxs-lookup"><span data-stu-id="8961e-111">While a single content center may be fine for environments for which you want a roll-up of all model activity, you may want to have additional centers for multiple departments within your organization, which may have different needs and requirements for their models.</span></span>

> [!NOTE]
> <span data-ttu-id="8961e-112">Um administrador do SharePoint pode criar um site do centro de conteúdo como [criaria qualquer outro site do SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) usando um modelo de site.</span><span class="sxs-lookup"><span data-stu-id="8961e-112">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) by using a site template.</span></span>

<span data-ttu-id="8961e-113">Para criar um novo centro de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="8961e-113">To create a new content center:</span></span>

1. <span data-ttu-id="8961e-114">No centro de administração do Microsoft 365, vá para o centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8961e-114">From the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="8961e-115">No centro de administração do SharePoint, em **sites**, selecione **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="8961e-115">In the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="8961e-116">Na página **sites ativos** , clique em **criar**e, em seguida, selecione **outras opções**.</span><span class="sxs-lookup"><span data-stu-id="8961e-116">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="8961e-117">No menu **escolher um modelo** , selecione **central de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="8961e-117">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="8961e-118">Para o novo site, forneça um **nome de site**, **administrador principal**e um **idioma**.</span><span class="sxs-lookup"><span data-stu-id="8961e-118">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!NOTE] 
> <span data-ttu-id="8961e-119">Opcionalmente, você pode selecionar um site de centro de conteúdo para renderizar em qualquer um dos idiomas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8961e-119">You can optionally select a content center site to render in any of the available languages.</span></span> <span data-ttu-id="8961e-120">Somente modelos atuais podem ser criados para arquivos em inglês.</span><span class="sxs-lookup"><span data-stu-id="8961e-120">Only current models can be created for English files.</span></span></br>

6. <span data-ttu-id="8961e-121">Selecione **concluído**.</span><span class="sxs-lookup"><span data-stu-id="8961e-121">Select **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="8961e-122">Conceder acesso a usuários adicionais</span><span class="sxs-lookup"><span data-stu-id="8961e-122">Give access to additional users</span></span>
 
<span data-ttu-id="8961e-123">Depois de criar o site, você pode permitir que usuários adicionais acessem o site por meio do [modelo de permissões de site padrão do SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="8961e-123">After you create the site, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>

## <a name="see-also"></a><span data-ttu-id="8961e-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="8961e-124">See Also</span></span>
[<span data-ttu-id="8961e-125">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="8961e-125">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="8961e-126">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="8961e-126">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="8961e-127">[Criar um centro](create-a-content-center.md) 
 de conteúdo [Visão geral da compreensão do documento](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8961e-127">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="8961e-128">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="8961e-128">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="8961e-129">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="8961e-129">Apply a model</span></span>](apply-a-model.md)    
