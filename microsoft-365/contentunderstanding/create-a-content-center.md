---
title: Criar um centro de conteúdo (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como criar um centro de conteúdo.
ms.openlocfilehash: 5332ffa195519aebd5ae8dd2c26d7d62fd9b3267
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612745"
---
# <a name="create-a-content-center-preview"></a><span data-ttu-id="4a342-103">Criar um centro de conteúdo (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="4a342-103">Create a content center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="4a342-104">O conteúdo deste artigo é para a visualização privada do Project Cortex.</span><span class="sxs-lookup"><span data-stu-id="4a342-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="4a342-105">[Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="4a342-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span></br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

<span data-ttu-id="4a342-106">Para criar e gerenciar modelos de compreensão de documentos, primeiro você precisa de um centro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4a342-106">To create and manage document understanding models, you first need a content center.</span></span> <span data-ttu-id="4a342-107">O centro de conteúdo é a interface de criação de modelo e também contém informações sobre quais modelos publicados de bibliotecas de documentos foram aplicados.</span><span class="sxs-lookup"><span data-stu-id="4a342-107">The content center is the model creation interface and also contains information about which document libraries published models have been applied.</span></span></br>

   ![Selecionar uma biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

<span data-ttu-id="4a342-109">Um centro de conteúdo inicial é criado durante [a instalação](set-up-content-understanding.md), mas um administrador do SharePoint pode optar por criar outros, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4a342-109">An initial content center is created during [setup](set-up-content-understanding.md), but a SharePoint admin can choose to create additional ones as needed.</span></span> <span data-ttu-id="4a342-110">Embora um único centro de conteúdo possa ser bom para ambientes nos quais você deseja ver uma acumulação de toda a atividade do modelo, talvez você queira ter outros, caso tenha vários departamentos em sua organização que possam ter necessidades e requisitos diferentes para seus modelos.</span><span class="sxs-lookup"><span data-stu-id="4a342-110">While a single content center may be fine for environments in which you want to see a roll-up of all model activity, you may want to have additional ones if your have multiple departments within your organization that may have different needs and requirements for their models.</span></span>

<span data-ttu-id="4a342-111">Um administrador do SharePoint pode criar um site do centro de conteúdo como [criaria qualquer outro site do SharePoint](https://docs.microsoft.com/sharepoint/create-site-collection) em um modelo de site.</span><span class="sxs-lookup"><span data-stu-id="4a342-111">A SharePoint admin can create a content center site like they would [create any other SharePoint site](https://docs.microsoft.com/sharepoint/create-site-collection) - through a site template.</span></span>

<span data-ttu-id="4a342-112">Para criar um novo centro de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="4a342-112">To create a new content center:</span></span>

1. <span data-ttu-id="4a342-113">No centro de administração do Microsoft 365, vá para o centro de administração do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4a342-113">On the Microsoft 365 admin center, go to the SharePoint admin center.</span></span>
2. <span data-ttu-id="4a342-114">No centro de administração do SharePoint, em **sites**, selecione **sites ativos**.</span><span class="sxs-lookup"><span data-stu-id="4a342-114">On the SharePoint admin center, under **Sites**, select **Active Sites**.</span></span>
3. <span data-ttu-id="4a342-115">Na página **sites ativos** , clique em **criar**e, em seguida, selecione **outras opções**.</span><span class="sxs-lookup"><span data-stu-id="4a342-115">On the **Active Sites** page, click **Create**, and then select **Other options**.</span></span>
4. <span data-ttu-id="4a342-116">No menu **escolher um modelo** , selecione **central de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="4a342-116">On the **Choose a template** menu, select **Content Center**.</span></span>
5. <span data-ttu-id="4a342-117">Para o novo site, forneça um **nome de site**, **administrador principal**e um **idioma**.</span><span class="sxs-lookup"><span data-stu-id="4a342-117">For the new site, provide a **Site Name**, **Primary administrator**, and a **Language**.</span></span></br>

> [!Note] 
> <span data-ttu-id="4a342-118">Você pode selecionar um site de centro de conteúdo para renderizar em qualquer um dos idiomas disponíveis, mas observe que modelos no momento só podem ser criados para arquivos em inglês.</span><span class="sxs-lookup"><span data-stu-id="4a342-118">You can select a content center site to render in any of the available languages, but note that currently models can only be created for English files.</span></span></br>

6. <span data-ttu-id="4a342-119">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="4a342-119">Click **Finished**.</span></span>

### <a name="give-access-to-additional-users"></a><span data-ttu-id="4a342-120">Conceder acesso a usuários adicionais</span><span class="sxs-lookup"><span data-stu-id="4a342-120">Give access to additional users</span></span>
 
<span data-ttu-id="4a342-121">Depois que o site for criado, você poderá permitir que usuários adicionais acessem o site por meio do [modelo de permissões de site padrão do SharePoint](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span><span class="sxs-lookup"><span data-stu-id="4a342-121">After the site is created, you can give additional users access to the site through the standard [SharePoint site permissions model](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span>





## <a name="see-also"></a><span data-ttu-id="4a342-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="4a342-122">See Also</span></span>
[<span data-ttu-id="4a342-123">Criar um classificador</span><span class="sxs-lookup"><span data-stu-id="4a342-123">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="4a342-124">Criar um extrator</span><span class="sxs-lookup"><span data-stu-id="4a342-124">Create an extractor</span></span>](create-an-extractor.md)</br>
<span data-ttu-id="4a342-125">[Criar um centro](create-a-content-center.md) 
 de conteúdo [Visão geral da compreensão do documento](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="4a342-125">[Create a content center](create-a-content-center.md)
[Document understanding overview](document-understanding-overview.md)</span></span></br>
[<span data-ttu-id="4a342-126">Criar um modelo de processamento de formulários</span><span class="sxs-lookup"><span data-stu-id="4a342-126">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="4a342-127">Aplicar um modelo</span><span class="sxs-lookup"><span data-stu-id="4a342-127">Apply a model</span></span>](apply-a-model.md)    




