---
title: Marcação de imagem no SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre a marcação de imagens no SharePoint Syntex
ms.openlocfilehash: c6d7513db2fd6aadabe5d813f3b49073a8f8c933
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413729"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="92c76-103">Marcação de imagem no SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="92c76-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="92c76-104">(Em breve)</span><span class="sxs-lookup"><span data-stu-id="92c76-104">(Coming soon)</span></span>

<span data-ttu-id="92c76-105">Com a marcação de imagens no SharePoint Syntex, os usuários podem encontrar imagens por meio de pesquisa, pesquisando em marcas de imagem e criar fluxos de trabalho com base em marcas de imagem.</span><span class="sxs-lookup"><span data-stu-id="92c76-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="92c76-106">Por padrão, a marcação de imagem básica está habilitada no SharePoint e no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="92c76-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="92c76-107">As imagens carregadas para qualquer local são automaticamente verificadas e as marcas aplicáveis são aplicadas, caso disponíveis, em uma lista de 37 marcas básicas.</span><span class="sxs-lookup"><span data-stu-id="92c76-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="92c76-108">Os usuários podem encontrar imagens pesquisando nas marcas de imagem.</span><span class="sxs-lookup"><span data-stu-id="92c76-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="92c76-109">Quando um usuário carrega uma imagem, o processo de marcação é executado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92c76-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="92c76-110">Se uma imagem for editada, o processo de marcação será executado novamente para atualizar as marcas.</span><span class="sxs-lookup"><span data-stu-id="92c76-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="92c76-111">Os usuários com permissões para o arquivo de imagem podem ver e editar as marcas no painel de informações do arquivo ou na página de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="92c76-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="92c76-112">Quando um usuário edita as marcas de uma imagem, o sistema deixa de marcar automaticamente essa imagem, mesmo que ela seja editada.</span><span class="sxs-lookup"><span data-stu-id="92c76-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="92c76-113">Se você desativar a marcação, as imagens não serão mais marcadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="92c76-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="92c76-114">As marcas existentes não serão removidas.</span><span class="sxs-lookup"><span data-stu-id="92c76-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="92c76-115">As marcas geradas pelo sistema podem ser alteradas com as atualizações na imagem ou na nossa tecnologia de marcas.</span><span class="sxs-lookup"><span data-stu-id="92c76-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="92c76-116">Configurar marcação de imagem</span><span class="sxs-lookup"><span data-stu-id="92c76-116">Configure image tagging</span></span>

<span data-ttu-id="92c76-117">Depois de [configurar o SharePoint Syntex](set-up-content-understanding.md), você pode configurar a marcação de imagens no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="92c76-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="92c76-118">Para ativar ou desativar a marcação de imagem</span><span class="sxs-lookup"><span data-stu-id="92c76-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="92c76-119">No Centro de Administração do Microsoft 365, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="92c76-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="92c76-120">Em **Conhecimento organizacional**, clique em **Automatizar o entendimento do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="92c76-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="92c76-121">Clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="92c76-121">Click **Manage**.</span></span>

4. <span data-ttu-id="92c76-122">Na guia **Marcação de imagem**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="92c76-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="92c76-123">Opte por permitir a **marcação básica** ou **desabilite**a marcação.</span><span class="sxs-lookup"><span data-stu-id="92c76-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="92c76-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="92c76-124">Click **Save**.</span></span>

    ![Captura de tela do controle de marcação de imagem](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
