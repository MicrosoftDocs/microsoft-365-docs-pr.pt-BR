---
title: Enviar os tipos de conteúdo a um hub
description: Saiba como enviar tipos de conteúdo a um hub
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 89c03a70da364bd4b945debc64de02255dec15e1
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975710"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="c0bd7-103">Enviar os tipos de conteúdo a um hub</span><span class="sxs-lookup"><span data-stu-id="c0bd7-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="c0bd7-104">Para disponibilizar os tipos de conteúdo importantes com mais consistência nas listas e bibliotecas do SharePoint, você pode enviá-los para os hubs que você escolher.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="c0bd7-105">Enviar automaticamente os tipos de conteúdo os adiciona a quaisquer novas listas e bibliotecas criadas nos sites associados ao hub e a quaisquer novos sites adicionados ao hub.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="c0bd7-106">Para que esse recurso funcione, os tipos de conteúdo que estão sendo enviados já devem estar publicados.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-106">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="c0bd7-107">Para enviar tipos de conteúdo a um hub</span><span class="sxs-lookup"><span data-stu-id="c0bd7-107">To push content types to hubs</span></span>

1. <span data-ttu-id="c0bd7-108">No Centro de administração do SharePoint, expanda **Serviços de conteúdo** e selecione **Galeria de tipo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-108">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="c0bd7-109">Selecione o tipo de conteúdo que você deseja enviar aos hubs.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-109">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="c0bd7-110">Selecione **Editar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-110">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="c0bd7-111">Selecione **Escolher sites de hub**.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-111">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="c0bd7-112">Selecione os sites de hub desejados e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-112">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="c0bd7-113">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-113">Choose **Save**.</span></span>

<span data-ttu-id="c0bd7-114">Quando você envia pela primeira vez um tipo de conteúdo para um hub existente e seus sites associados existentes, pode levar até uma hora a partir da visita do hub ou dos sites associados para que as configurações sejam atualizadas no site.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-114">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="c0bd7-115">Quaisquer novas associações ao hub não exigirão essa espera e terão as configurações refletidas em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-115">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="c0bd7-116">Depois que as configurações forem atualizadas, o tipo de conteúdo com essas configurações estará disponível em qualquer site recém-associado ao hub em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-116">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="c0bd7-117">Em seguida, qualquer nova lista ou biblioteca criada terá o tipo de conteúdo automaticamente adicionado a ela alguns minutos após a criação.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-117">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="c0bd7-118">Um tipo de conteúdo enviado será adicionado a uma biblioteca de documentos somente se ele derivar direta ou indiretamente do tipo de conteúdo do documento, e um tipo de conteúdo será adicionado a uma lista apenas se não for derivado direta ou indiretamente do tipo de conteúdo do documento.</span><span class="sxs-lookup"><span data-stu-id="c0bd7-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0bd7-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="c0bd7-119">See also</span></span>
