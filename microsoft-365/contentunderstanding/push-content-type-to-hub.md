---
title: Tipos de conteúdo por push para um hub
description: Saiba como enviar tipos de conteúdo para um hub
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295728"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="34b45-103">Tipos de conteúdo por push para um hub</span><span class="sxs-lookup"><span data-stu-id="34b45-103">Push content types to a hub</span></span>

<span data-ttu-id="34b45-104">Para disponibilizar os tipos de conteúdo importantes de forma mais consistente às bibliotecas e listas do SharePoint, você pode enviá-los aos hubs escolhidos.</span><span class="sxs-lookup"><span data-stu-id="34b45-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="34b45-105">Isso os adiciona automaticamente às novas listas e bibliotecas criadas nos sites associados ao Hub e a todos os novos sites adicionados ao Hub.</span><span class="sxs-lookup"><span data-stu-id="34b45-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="34b45-106">Para que este recurso funcione, os tipos de conteúdo que estão sendo enviados já devem ser publicados.</span><span class="sxs-lookup"><span data-stu-id="34b45-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="34b45-107">Para enviar tipos de conteúdo para hubs</span><span class="sxs-lookup"><span data-stu-id="34b45-107">To push content types to hubs</span></span>

1. <span data-ttu-id="34b45-108">No centro de administração do SharePoint, expanda **serviços de conteúdo**e, em seguida, clique em Galeria de **tipos de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="34b45-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="34b45-109">Clique no tipo de conteúdo que você deseja enviar para hubs.</span><span class="sxs-lookup"><span data-stu-id="34b45-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="34b45-110">Clique em **Editar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="34b45-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="34b45-111">Clique em **escolher sites do Hub**.</span><span class="sxs-lookup"><span data-stu-id="34b45-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="34b45-112">Selecione os sites de Hub desejados e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34b45-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="34b45-113">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="34b45-113">Click **Save**.</span></span>

<span data-ttu-id="34b45-114">Ao enviar um tipo de conteúdo para um Hub existente & seus sites associados pela primeira vez, pode levar até uma hora de quando o Hub ou sites associados são visitados, para que as configurações sejam atualizadas no site.</span><span class="sxs-lookup"><span data-stu-id="34b45-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="34b45-115">Qualquer associação nova ao Hub não exigirá essa espera e as configurações serão refletidas em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="34b45-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="34b45-116">Após a configuração, o tipo de conteúdo com essas configurações estará disponível em qualquer site recentemente associado com o Hub em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="34b45-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="34b45-117">Uma vez disponível, qualquer nova lista ou biblioteca criada terá o tipo de conteúdo automaticamente adicionado a ela em alguns minutos de criação.</span><span class="sxs-lookup"><span data-stu-id="34b45-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="34b45-118">Um tipo de conteúdo enviado será adicionado a uma biblioteca de documentos somente se ele derivar direta ou indiretamente do tipo de conteúdo do documento, e um tipo de conteúdo será adicionado a uma lista somente se ele não for derivado do tipo de conteúdo de documento direta ou indiretamente.</span><span class="sxs-lookup"><span data-stu-id="34b45-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="34b45-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="34b45-119">See also</span></span>



  






