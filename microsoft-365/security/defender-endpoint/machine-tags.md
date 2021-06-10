---
title: Criar e gerenciar marcas de dispositivo
description: Usar marcas de dispositivo para agrupar dispositivos para capturar contexto e habilitar a criação de listas dinâmicas como parte de um incidente
keywords: tags, marcas de dispositivo, grupos de dispositivos, grupos, correção, nível, regras, grupo aad, função, atribuir, classificação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187584"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="74ab4-104">Criar e gerenciar marcas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="74ab4-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="74ab4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="74ab4-105">**Applies to:**</span></span>
- [<span data-ttu-id="74ab4-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="74ab4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="74ab4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="74ab4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="74ab4-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="74ab4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="74ab4-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="74ab4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="74ab4-110">Adicionar marcas em dispositivos para criar uma afiliação de grupo lógico.</span><span class="sxs-lookup"><span data-stu-id="74ab4-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="74ab4-111">As marcas de dispositivo oferecem suporte ao mapeamento correto da rede, permitindo anexar marcas diferentes para capturar contexto e habilitar a criação de lista dinâmica como parte de um incidente.</span><span class="sxs-lookup"><span data-stu-id="74ab4-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="74ab4-112">As marcas podem ser usadas como filtro no **exibição de** lista Dispositivos ou para agrupar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="74ab4-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="74ab4-113">Para obter mais informações sobre o grupo de dispositivos, consulte [Create and manage device groups](machine-groups.md).</span><span class="sxs-lookup"><span data-stu-id="74ab4-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="74ab4-114">Você pode adicionar marcas em dispositivos usando as seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="74ab4-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="74ab4-115">Usar o portal</span><span class="sxs-lookup"><span data-stu-id="74ab4-115">Using the portal</span></span>
- <span data-ttu-id="74ab4-116">Definir um valor de chave de registro</span><span class="sxs-lookup"><span data-stu-id="74ab4-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="74ab4-117">Pode haver alguma latência entre o momento em que uma marca é adicionada a um dispositivo e sua disponibilidade na lista de dispositivos e na página do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74ab4-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="74ab4-118">Para adicionar marcas de dispositivo usando a API, veja a [API Adicionar ou remover marcas de dispositivo](add-or-remove-machine-tags.md).</span><span class="sxs-lookup"><span data-stu-id="74ab4-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="74ab4-119">Adicionar e gerenciar marcas de dispositivo usando o portal</span><span class="sxs-lookup"><span data-stu-id="74ab4-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="74ab4-120">Selecione o dispositivo o qual você deseja gerenciar as marcas.</span><span class="sxs-lookup"><span data-stu-id="74ab4-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="74ab4-121">Você pode selecionar ou procurar um dispositivo a partir de qualquer uma dos modos de exibição a seguir:</span><span class="sxs-lookup"><span data-stu-id="74ab4-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="74ab4-122">**Painel de operações de segurança** - Selecione o nome do dispositivo na seção Principais dispositivos com alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="74ab4-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="74ab4-123">**Fila de alertas** - Selecione o nome do dispositivo ao lado do ícone do dispositivo na fila de alertas.</span><span class="sxs-lookup"><span data-stu-id="74ab4-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="74ab4-124">**Lista de dispositivos** - Selecione o nome do dispositivo na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="74ab4-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="74ab4-125">**Caixa de pesquisa** - Selecione Dispositivo no menu suspenso e insira o nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74ab4-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="74ab4-126">Você também pode acessar a página de alertas através do modo de exibição de arquivo e IP.</span><span class="sxs-lookup"><span data-stu-id="74ab4-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="74ab4-127">Selecione **Gerenciar Marcas** na linha de ações de Resposta.</span><span class="sxs-lookup"><span data-stu-id="74ab4-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![Imagem do botão gerenciar marcas](images/manage-tags.png)

3. <span data-ttu-id="74ab4-129">Digite para encontrar ou criar marcas</span><span class="sxs-lookup"><span data-stu-id="74ab4-129">Type to find or create tags</span></span>

    ![Imagem da adição de marcas em um dispositivo1](images/new-tags.png)

<span data-ttu-id="74ab4-131">As marcas são adicionadas à exibição do dispositivo e também serão refletidas no **exibição de** lista Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="74ab4-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="74ab4-132">Em seguida, você pode usar o **filtro Tags** para ver a lista relevante de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="74ab4-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="74ab4-133">A filtragem pode não funcionar em nomes de marca que contenham parênteses.</span><span class="sxs-lookup"><span data-stu-id="74ab4-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="74ab4-134">Quando você cria uma nova marca, uma lista de marcas existentes é exibida.</span><span class="sxs-lookup"><span data-stu-id="74ab4-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="74ab4-135">A lista mostra apenas marcas criadas por meio do portal.</span><span class="sxs-lookup"><span data-stu-id="74ab4-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="74ab4-136">As marcas existentes criadas a partir de dispositivos cliente não serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="74ab4-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="74ab4-137">Você também pode excluir marcas deste exibição.</span><span class="sxs-lookup"><span data-stu-id="74ab4-137">You can also delete tags from this view.</span></span>

![Imagem da adição de marcas em um dispositivo2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="74ab4-139">Adicionar marcas de dispositivo definindo um valor de chave do Registro</span><span class="sxs-lookup"><span data-stu-id="74ab4-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="74ab4-140">Aplicável somente nos seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="74ab4-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="74ab4-141">Windows 10, versão 1709 ou posterior</span><span class="sxs-lookup"><span data-stu-id="74ab4-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="74ab4-142">Windows Servidor, versão 1803 ou posterior</span><span class="sxs-lookup"><span data-stu-id="74ab4-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="74ab4-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="74ab4-143">Windows Server 2016</span></span>
>- <span data-ttu-id="74ab4-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="74ab4-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="74ab4-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="74ab4-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="74ab4-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="74ab4-146">Windows 8.1</span></span>
>- <span data-ttu-id="74ab4-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="74ab4-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="74ab4-148">O número máximo de caracteres que podem ser definidos em uma marca é 200.</span><span class="sxs-lookup"><span data-stu-id="74ab4-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="74ab4-149">Dispositivos com marcas semelhantes podem ser úteis quando você precisa aplicar uma ação contextual em uma lista específica de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="74ab4-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="74ab4-150">Use a seguinte entrada da chave do Registro para adicionar uma marca em um dispositivo:</span><span class="sxs-lookup"><span data-stu-id="74ab4-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="74ab4-151">Chave do Registro: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="74ab4-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="74ab4-152">Valor da chave do Registro (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="74ab4-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="74ab4-153">Dados principais do Registro: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="74ab4-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="74ab4-154">A marca do dispositivo faz parte do relatório de informações do dispositivo gerado uma vez por dia.</span><span class="sxs-lookup"><span data-stu-id="74ab4-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="74ab4-155">Como alternativa, você pode optar por reiniciar o ponto de extremidade que transferiria um novo relatório de informações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="74ab4-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="74ab4-156">Se você precisar remover uma marca que foi adicionada usando a chave do Registro acima, limpe o conteúdo dos dados da chave do Registro em vez de remover a chave 'Group'.</span><span class="sxs-lookup"><span data-stu-id="74ab4-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
