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
localization_priority: Priority
ms.openlocfilehash: 03e1be51b35447376be5adfc2f2cd3c944cf89fa
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321332"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="9f7ce-103">Enviar os tipos de conteúdo a um hub</span><span class="sxs-lookup"><span data-stu-id="9f7ce-103">Push content types to a hub</span></span>

<span data-ttu-id="9f7ce-104">Para disponibilizar os tipos de conteúdo importantes com mais consistência nas listas e bibliotecas do SharePoint, você pode enviá-los para os hubs que você escolher.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="9f7ce-105">Isso os adiciona automaticamente a todas as novas listas e bibliotecas criadas nos sites associados ao hub e a todos os novos sites adicionados ao hub.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-105">This automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span>

<span data-ttu-id="9f7ce-106">Para que esse recurso funcione, os tipos de conteúdo que estão sendo enviados já devem ser publicados.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-106">For this feature to work, The content types being pushed must already be published.</span></span>

<span data-ttu-id="9f7ce-107">Para enviar tipos de conteúdo a um hub</span><span class="sxs-lookup"><span data-stu-id="9f7ce-107">To push content types to hubs</span></span>

1. <span data-ttu-id="9f7ce-108">No Centro de administração do SharePoint, expanda **Serviços de conteúdo** e, em seguida, clique em **Galeria do tipo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-108">In the SharePoint admin center, expand **Content services**, and then click **Content type gallery**.</span></span>

2. <span data-ttu-id="9f7ce-109">Clique no tipo de conteúdo que você deseja enviar para os hubs.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-109">Click the content type that you want to push to hubs.</span></span>

3. <span data-ttu-id="9f7ce-110">Clique em **Editar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-110">Click **Edit** in the command bar.</span></span>
 
4. <span data-ttu-id="9f7ce-111">Clique **Escolher sites do hub**.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-111">Click **Choose hub sites**.</span></span>
 
5. <span data-ttu-id="9f7ce-112">Selecione os sites do hub desejados e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-112">Select the desired hub sites and then click **OK**.</span></span>
 
6. <span data-ttu-id="9f7ce-113">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-113">Click **Save**.</span></span>

<span data-ttu-id="9f7ce-114">Ao enviar um tipo de conteúdo para um hub existente e seus sites associados existentes pela primeira vez, pode levar até uma hora de quando os hubs ou sites associados são visitados, para que as configurações sejam atualizadas no site.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-114">When pushing a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="9f7ce-115">As novas associações ao hub não exigem essa espera e terão as configurações refletidas em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-115">Any new associations to the hub will not require this wait and will have the settings reflected in a few minutes.</span></span> 

<span data-ttu-id="9f7ce-116">Após a configuração, o tipo de conteúdo com essas configurações estará disponível em qualquer site recentemente associado com o hub em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-116">Once this is configured, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="9f7ce-117">Uma vez disponível, todas as novas listas ou bibliotecas criadas terão o tipo de conteúdo adicionado automaticamente a elas dentro de alguns minutos após serem criadas.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-117">Once available, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="9f7ce-118">Um tipo de conteúdo enviado será adicionado a uma biblioteca de documentos somente se ele derivar direta ou indiretamente do tipo de conteúdo do documento, e um tipo de conteúdo será adicionado a uma lista apenas se não for derivado direta ou indiretamente do tipo de conteúdo do documento.</span><span class="sxs-lookup"><span data-stu-id="9f7ce-118">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f7ce-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="9f7ce-119">See also</span></span>



  






