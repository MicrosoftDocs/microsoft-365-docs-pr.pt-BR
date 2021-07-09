---
title: Configurar a descoberta de dispositivo
description: Saiba como configurar a descoberta de dispositivos em Microsoft 365 Defender usando a descoberta básica ou padrão
keywords: básico, padrão, configurar descoberta de ponto de extremidade, descoberta de dispositivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 7125a6953b9be46af9073b50c9268ce65dc0cd30
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339521"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="234c7-104">Configurar a descoberta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="234c7-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="234c7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="234c7-105">**Applies to:**</span></span>
- [<span data-ttu-id="234c7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="234c7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="234c7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="234c7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="234c7-108">A descoberta pode ser configurada para estar no modo padrão ou básico.</span><span class="sxs-lookup"><span data-stu-id="234c7-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="234c7-109">Use a opção padrão para encontrar ativamente dispositivos em sua rede, o que garantirá melhor a descoberta de pontos de extremidade e fornecerá uma classificação de dispositivo mais rica.</span><span class="sxs-lookup"><span data-stu-id="234c7-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="234c7-110">Você pode personalizar a lista de dispositivos usados para executar a descoberta padrão.</span><span class="sxs-lookup"><span data-stu-id="234c7-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="234c7-111">Você pode habilitar a descoberta padrão em todos os dispositivos conectados que também suportam esse recurso (atualmente - somente dispositivos Windows 10) ou selecionar um subconjunto ou subconjunto de seus dispositivos especificando suas marcas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="234c7-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="234c7-112">Para visualizar, primeiro você precisará ativar os recursos de visualização no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="234c7-112">For preview, you'll first need to turn on the Preview features in Microsoft 365 Defender.</span></span>
> <span data-ttu-id="234c7-113">Em seguida, você pode acessar a configuração de descoberta de dispositivo Microsoft 365 centro de segurança.</span><span class="sxs-lookup"><span data-stu-id="234c7-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="234c7-114">A lista de dispositivos não administrativos e recomendações de segurança estará disponível no centro de segurança do Microsoft 365 Defender e do Microsoft 365, enquanto os blocos do painel estarão disponíveis apenas no centro de segurança Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="234c7-114">The list of unmanaged devices and security recommendations will be available in both Microsoft 365 Defender and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>

<span data-ttu-id="234c7-115">Tome as seguintes etapas de configuração no Microsoft 365 de segurança:</span><span class="sxs-lookup"><span data-stu-id="234c7-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1. <span data-ttu-id="234c7-116">Navegue **até Configurações > Descoberta de dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="234c7-116">Navigate to **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="234c7-117">Selecione o modo de descoberta a ser usado em seus dispositivos conectados.</span><span class="sxs-lookup"><span data-stu-id="234c7-117">Select the discovery mode to use on your onboarded devices.</span></span>
3. <span data-ttu-id="234c7-118">Se você tiver selecionado para usar a descoberta padrão, selecione quais dispositivos usar para sondagem ativa: todos os dispositivos ou em um subconjunto especificando suas marcas de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="234c7-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="234c7-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="234c7-119">Click **Save**.</span></span>

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="234c7-120">Excluir dispositivos de serem sondados ativamente na descoberta padrão</span><span class="sxs-lookup"><span data-stu-id="234c7-120">Exclude devices from being actively probed in standard discovery</span></span>

<span data-ttu-id="234c7-121">Se houver dispositivos em sua rede que não devem ser verificados ativamente (por exemplo, dispositivos usados como honeypots para outra ferramenta de segurança), você também pode definir uma lista de exclusões para impedir que eles sejam verificados.</span><span class="sxs-lookup"><span data-stu-id="234c7-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="234c7-122">Observe que os dispositivos ainda podem ser descobertos usando o modo de descoberta básico.</span><span class="sxs-lookup"><span data-stu-id="234c7-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="234c7-123">Esses dispositivos serão descobertos passivamente, mas não serão sondados ativamente.</span><span class="sxs-lookup"><span data-stu-id="234c7-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="234c7-124">Selecionar redes para monitorar</span><span class="sxs-lookup"><span data-stu-id="234c7-124">Select networks to monitor</span></span>

 <span data-ttu-id="234c7-125">O Microsoft Defender for Endpoint analisa uma rede e determina se é uma rede corporativa que precisa ser monitorada ou uma rede não corporativa que pode ser ignorada.</span><span class="sxs-lookup"><span data-stu-id="234c7-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="234c7-126">As redes corporativas geralmente são escolhidas para serem monitoradas.</span><span class="sxs-lookup"><span data-stu-id="234c7-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="234c7-127">No entanto, você pode substituir essa decisão optando por monitorar redes não corporativas onde os dispositivos conectados são encontrados.</span><span class="sxs-lookup"><span data-stu-id="234c7-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="234c7-128">Você pode configurar onde a descoberta de dispositivo pode ser realizada especificando quais redes monitorar.</span><span class="sxs-lookup"><span data-stu-id="234c7-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="234c7-129">Quando uma rede é monitorada, a descoberta de dispositivo pode ser realizada nele.</span><span class="sxs-lookup"><span data-stu-id="234c7-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="234c7-130">Uma lista de redes onde a descoberta de dispositivos pode ser executada é mostrada na **página Redes Monitoradas.**</span><span class="sxs-lookup"><span data-stu-id="234c7-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="234c7-131">Somente as 50 principais redes (de acordo com o número de dispositivos associados) estarão disponíveis na lista de rede.</span><span class="sxs-lookup"><span data-stu-id="234c7-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 

<span data-ttu-id="234c7-132">A lista de redes monitoradas é classificação com base no número total de dispositivos vistos na rede nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="234c7-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>

<span data-ttu-id="234c7-133">Você pode aplicar um filtro para exibir qualquer um dos seguintes estados de descoberta de rede:</span><span class="sxs-lookup"><span data-stu-id="234c7-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="234c7-134">**Redes monitoradas** - Redes em que a descoberta de dispositivo é realizada.</span><span class="sxs-lookup"><span data-stu-id="234c7-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="234c7-135">**Redes ignoradas** - Essa rede será ignorada e a descoberta do dispositivo não será executada nele.</span><span class="sxs-lookup"><span data-stu-id="234c7-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="234c7-136">**Todos** - Redes monitoradas e ignoradas serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="234c7-136">**All** - Both monitored and ignored networks will be displayed.</span></span>

### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="234c7-137">Configurar o estado do monitor de rede</span><span class="sxs-lookup"><span data-stu-id="234c7-137">Configure the network monitor state</span></span>

<span data-ttu-id="234c7-138">Você controla onde ocorre a descoberta do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="234c7-138">You control where device discovery takes place.</span></span> <span data-ttu-id="234c7-139">Redes monitoradas são onde a descoberta de dispositivos será realizada e normalmente são redes corporativas.</span><span class="sxs-lookup"><span data-stu-id="234c7-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="234c7-140">Você também pode optar por ignorar redes ou selecionar a classificação de descoberta inicial após modificar um estado.</span><span class="sxs-lookup"><span data-stu-id="234c7-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span>

<span data-ttu-id="234c7-141">Escolher a classificação de descoberta inicial significa aplicar o estado padrão do monitor de rede feito pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="234c7-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="234c7-142">Selecionar o estado padrão do monitor de rede feito pelo sistema significa que as redes identificadas como corporativas serão monitoradas e as identificadas como não corporativas serão ignoradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="234c7-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>

1. <span data-ttu-id="234c7-143">Selecione **Configurações > Descoberta de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="234c7-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="234c7-144">Selecione **Redes monitoradas**.</span><span class="sxs-lookup"><span data-stu-id="234c7-144">Select **Monitored networks**.</span></span>
3. <span data-ttu-id="234c7-145">Exibir a lista de redes.</span><span class="sxs-lookup"><span data-stu-id="234c7-145">View the list of networks.</span></span>
4. <span data-ttu-id="234c7-146">Selecione os três pontos ao lado do nome da rede.</span><span class="sxs-lookup"><span data-stu-id="234c7-146">Select the three dots next to the network name.</span></span>
5. <span data-ttu-id="234c7-147">Escolha se deseja monitorar, ignorar ou usar a classificação de descoberta inicial.</span><span class="sxs-lookup"><span data-stu-id="234c7-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span>

    > [!WARNING]
    >
    > - <span data-ttu-id="234c7-148">A escolha de monitorar uma rede que não foi identificada pelo Microsoft Defender para o Ponto de Extremidade como uma rede corporativa pode causar a descoberta de dispositivo fora da rede corporativa e, portanto, pode detectar dispositivos não corporativos ou de residência.</span><span class="sxs-lookup"><span data-stu-id="234c7-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span>
    > - <span data-ttu-id="234c7-149">A escolha de ignorar uma rede interromperá o monitoramento e a descoberta de dispositivos nessa rede.</span><span class="sxs-lookup"><span data-stu-id="234c7-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="234c7-150">Os dispositivos que já foram descobertos não serão removidos do inventário, mas não serão mais atualizados e os detalhes serão mantidos até que o período de retenção de dados do Defender for Endpoint expire.</span><span class="sxs-lookup"><span data-stu-id="234c7-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="234c7-151">Antes de optar por monitorar redes não corporativas, você deve garantir que tenha permissão para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="234c7-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span>

6. <span data-ttu-id="234c7-152">Confirme se você deseja fazer a alteração.</span><span class="sxs-lookup"><span data-stu-id="234c7-152">Confirm that you want to make the change.</span></span> 

## <a name="explore-devices-in-the-network"></a><span data-ttu-id="234c7-153">Explorar dispositivos na rede</span><span class="sxs-lookup"><span data-stu-id="234c7-153">Explore devices in the network</span></span>

<span data-ttu-id="234c7-154">Você pode usar a seguinte consulta de busca avançada para obter mais contexto sobre cada nome de rede descrito na lista de redes.</span><span class="sxs-lookup"><span data-stu-id="234c7-154">You can use the following advanced hunting query to get more context about each network name described in the networks list.</span></span> <span data-ttu-id="234c7-155">A consulta lista todos os dispositivos conectados a uma determinada rede nos últimos 7 dias.</span><span class="sxs-lookup"><span data-stu-id="234c7-155">The query lists all the onboarded devices that were connected to a certain network within the last 7 days.</span></span>

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a><span data-ttu-id="234c7-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="234c7-156">See also</span></span>

- [<span data-ttu-id="234c7-157">Visão geral sobre descoberta de dispositivo</span><span class="sxs-lookup"><span data-stu-id="234c7-157">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="234c7-158">Perguntas frequentes sobre descoberta de dispositivos</span><span class="sxs-lookup"><span data-stu-id="234c7-158">Device discovery FAQs</span></span>](device-discovery-faq.md)
