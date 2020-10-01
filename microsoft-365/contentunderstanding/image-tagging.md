---
title: Marcação de imagem no SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: MET150
localization_priority: Priority
description: Saiba mais sobre a marcação de imagens no SharePoint Syntex
ms.openlocfilehash: 7b41422633934593de881bdb0c04f0a845a3fe5f
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321248"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="b2ae0-103">Marcação de imagem no SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b2ae0-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="b2ae0-104">Com a marcação de imagens no SharePoint Syntex, os usuários podem encontrar imagens por meio de pesquisa, pesquisando em marcas de imagem e criar fluxos de trabalho com base em marcas de imagem.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-104">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="b2ae0-105">Por padrão, a marcação de imagem básica está habilitada no SharePoint e no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-105">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="b2ae0-106">As imagens carregadas para qualquer local são automaticamente verificadas e as marcas aplicáveis são aplicadas, caso disponíveis, em uma lista de 37 marcas básicas.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-106">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="b2ae0-107">Os usuários podem encontrar imagens pesquisando nas marcas de imagem.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-107">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="b2ae0-108">Quando um usuário carrega uma imagem, o processo de marcação é executado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-108">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="b2ae0-109">Se uma imagem for editada, o processo de marcação será executado novamente para atualizar as marcas.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-109">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="b2ae0-110">Os usuários com permissões para o arquivo de imagem podem ver e editar as marcas no painel de informações do arquivo ou na página de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-110">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="b2ae0-111">Quando um usuário edita as marcas de uma imagem, o sistema deixa de marcar automaticamente essa imagem, mesmo que ela seja editada.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-111">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="b2ae0-112">Se você desativar a marcação, as imagens não serão mais marcadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-112">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="b2ae0-113">As marcas existentes não serão removidas.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-113">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="b2ae0-114">As marcas geradas pelo sistema podem ser alteradas com as atualizações na imagem ou na nossa tecnologia de marcas.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-114">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="b2ae0-115">Configurar marcação de imagem</span><span class="sxs-lookup"><span data-stu-id="b2ae0-115">Configure image tagging</span></span>

<span data-ttu-id="b2ae0-116">Depois de [configurar o SharePoint Syntex](set-up-content-understanding.md), você pode configurar a marcação de imagens no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-116">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="b2ae0-117">Para ativar ou desativar a marcação de imagem</span><span class="sxs-lookup"><span data-stu-id="b2ae0-117">To turn image tagging on or off</span></span>

1. <span data-ttu-id="b2ae0-118">No Centro de Administração do Microsoft 365, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-118">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="b2ae0-119">Em **Conhecimento organizacional**, clique em **Automatizar o entendimento do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-119">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="b2ae0-120">Clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-120">Click **Manage**.</span></span>

4. <span data-ttu-id="b2ae0-121">Na guia **Marcação de imagem**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-121">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="b2ae0-122">Opte por permitir a **marcação básica** ou **desabilite**a marcação.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-122">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="b2ae0-123">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b2ae0-123">Click **Save**.</span></span>

    ![Captura de tela do controle de marcação de imagem](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
