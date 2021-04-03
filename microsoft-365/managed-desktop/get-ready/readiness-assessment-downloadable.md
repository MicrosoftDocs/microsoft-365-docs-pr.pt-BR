---
title: Verificador de avaliação de prontidão para download
description: Verifica as configurações de dispositivo e rede, incluindo pontos de extremidade necessários
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581029"
---
# <a name="downloadable-readiness-assessment-checker"></a><span data-ttu-id="efac3-104">Verificador de avaliação de prontidão para download</span><span class="sxs-lookup"><span data-stu-id="efac3-104">Downloadable readiness assessment checker</span></span>

<span data-ttu-id="efac3-105">Para funcionar bem com a Área de Trabalho Gerenciada da Microsoft, os dispositivos devem atender a determinados requisitos de hardware e configurações.</span><span class="sxs-lookup"><span data-stu-id="efac3-105">To work well with Microsoft Managed Desktop, devices must meet certain requirements for hardware and settings.</span></span> <span data-ttu-id="efac3-106">Além disso, cada dispositivo deve ser capaz de alcançar pontos de extremidade principais.</span><span class="sxs-lookup"><span data-stu-id="efac3-106">Also, each device must be able to reach key endpoints.</span></span> <span data-ttu-id="efac3-107">Baixe e execute essa ferramenta para obter um relatório HTML, exibir resultados e, em seguida, tomar medidas.</span><span class="sxs-lookup"><span data-stu-id="efac3-107">Download and run this tool to obtain an HTML report, view results, and then take action.</span></span> <span data-ttu-id="efac3-108">Você precisará baixar a ferramenta e os arquivos de suporte e, em seguida, execute-a manualmente em cada dispositivo que você deseja registrar na Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efac3-108">You will need to download the tool and supporting files, and then run it manually on each device you want to enroll in Microsoft Managed Desktop.</span></span>

<span data-ttu-id="efac3-109">Para cada verificação, a ferramenta relatará um dos três resultados possíveis:</span><span class="sxs-lookup"><span data-stu-id="efac3-109">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="efac3-110">Resultado</span><span class="sxs-lookup"><span data-stu-id="efac3-110">Result</span></span>  |<span data-ttu-id="efac3-111">Significado</span><span class="sxs-lookup"><span data-stu-id="efac3-111">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="efac3-112">Pronto</span><span class="sxs-lookup"><span data-stu-id="efac3-112">Ready</span></span>     | <span data-ttu-id="efac3-113">Nenhuma ação é necessária antes de concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="efac3-113">No action is required before you complete enrollment.</span></span>        |
|<span data-ttu-id="efac3-114">Aviso</span><span class="sxs-lookup"><span data-stu-id="efac3-114">Advisory</span></span>    | <span data-ttu-id="efac3-115">Siga as etapas na ferramenta para ter a melhor experiência com registro e usuários.</span><span class="sxs-lookup"><span data-stu-id="efac3-115">Follow the steps in the tool for the best experience with enrollment and for users.</span></span> <span data-ttu-id="efac3-116">Você *pode* concluir o registro, mas deve corrigir esses problemas antes de implantar seu primeiro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="efac3-116">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="efac3-117">Não está pronto</span><span class="sxs-lookup"><span data-stu-id="efac3-117">Not ready</span></span> | <span data-ttu-id="efac3-118">*O registro falhará* se você não corrigir esses problemas.</span><span class="sxs-lookup"><span data-stu-id="efac3-118">*Enrollment will fail* if you don't fix these issues.</span></span> <span data-ttu-id="efac3-119">Siga as etapas na ferramenta para resolvê-las.</span><span class="sxs-lookup"><span data-stu-id="efac3-119">Follow the steps in the tool to resolve them.</span></span>        |

## <a name="obtain-the-checker"></a><span data-ttu-id="efac3-120">Obter o checker</span><span class="sxs-lookup"><span data-stu-id="efac3-120">Obtain the checker</span></span>

<span data-ttu-id="efac3-121">Baixe o arquivo .zip de https://aka.ms/mmddratoolv0 .</span><span class="sxs-lookup"><span data-stu-id="efac3-121">Download the .zip file from https://aka.ms/mmddratoolv0.</span></span>

> [!NOTE]
> <span data-ttu-id="efac3-122">O usuário que executa a ferramenta deve ter direitos de Administrador local no dispositivo em que a está executando.</span><span class="sxs-lookup"><span data-stu-id="efac3-122">The user running the tool must have local Administrator rights on the device where they're running it.</span></span>

 <span data-ttu-id="efac3-123">Em seguida, execute a ferramenta seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="efac3-123">Then run the tool by following these steps:</span></span>

1. <span data-ttu-id="efac3-124">Copie o arquivo .zip baixado para cada dispositivo que você deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="efac3-124">Copy the downloaded .zip file to each device you want to check.</span></span>
2. <span data-ttu-id="efac3-125">Extraia todos os arquivos no download compactado.</span><span class="sxs-lookup"><span data-stu-id="efac3-125">Extract all files in the compressed download.</span></span>
3. <span data-ttu-id="efac3-126">Execute **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span><span class="sxs-lookup"><span data-stu-id="efac3-126">Run **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.</span></span>
4. <span data-ttu-id="efac3-127">Quando o prompt controle de acesso do usuário for exibido, selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="efac3-127">When the User Access Control prompt appears, select **Yes**.</span></span> <span data-ttu-id="efac3-128">A ferramenta é executado e abre um relatório no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="efac3-128">The tool runs and opens a report in your default browser.</span></span>

<span data-ttu-id="efac3-129">Você também pode baixar e extrair o arquivo  morto .zip para um local compartilhado, acessarMicrosoft.MMD.DeviceReadinessAssessmentTool.exede cada dispositivo e, em seguida, execute-o localmente.</span><span class="sxs-lookup"><span data-stu-id="efac3-129">You could also download and extract the .zip archive to a shared location, access **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** from each device, and then run it locally.</span></span>


## <a name="checks"></a><span data-ttu-id="efac3-130">Verificações</span><span class="sxs-lookup"><span data-stu-id="efac3-130">Checks</span></span>

<span data-ttu-id="efac3-131">A ferramenta baixável verifica esses itens relacionados ao dispositivo e à rede:</span><span class="sxs-lookup"><span data-stu-id="efac3-131">The downloadable tool checks these device- and network-related items:</span></span>

### <a name="hardware"></a><span data-ttu-id="efac3-132">Hardware</span><span class="sxs-lookup"><span data-stu-id="efac3-132">Hardware</span></span>

<span data-ttu-id="efac3-133">Os dispositivos devem atender a requisitos de hardware específicos para trabalhar com a Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efac3-133">Devices must meet specific hardware requirements to work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="efac3-134">Atualmente, somente dispositivos [aprovados](../service-description/device-list.md) específicos têm permissão para se inscrever.</span><span class="sxs-lookup"><span data-stu-id="efac3-134">Currently, only specific [approved devices](../service-description/device-list.md) are allowed to enroll.</span></span> 

<span data-ttu-id="efac3-135">Se o dispositivo falhar em qualquer uma das verificações, ele não será compatível com a Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efac3-135">If your device fails any of the checks, it's not compatible with Microsoft Managed Desktop.</span></span>

### <a name="network-endpoints"></a><span data-ttu-id="efac3-136">Pontos de extremidade de rede</span><span class="sxs-lookup"><span data-stu-id="efac3-136">Network endpoints</span></span>

<span data-ttu-id="efac3-137">Os dispositivos podem alcançar vários pontos [de extremidade principais](network.md) para trabalhar com a Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efac3-137">Devices much be able to reach several [key endpoints](network.md) to work with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="efac3-138">Se a ferramenta relatar um **resultado Não** pronto, consulte o relatório detalhado para descobrir quais pontos de extremidade não eram acessíveis.</span><span class="sxs-lookup"><span data-stu-id="efac3-138">If the tool reports a **Not ready** result, see the detailed report to find out which endpoints weren't reachable.</span></span> <span data-ttu-id="efac3-139">Em seguida, ajuste o firewall ou outras configurações de rede para garantir que esses pontos de extremidade possam ser atingidos.</span><span class="sxs-lookup"><span data-stu-id="efac3-139">Then adjust your firewall or other network settings to ensure those endpoints can be reached.</span></span>

### <a name="other-settings"></a><span data-ttu-id="efac3-140">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="efac3-140">Other settings</span></span>

#### <a name="enterprise-wi-fi-profiles"></a><span data-ttu-id="efac3-141">Perfis wi-fi corporativos</span><span class="sxs-lookup"><span data-stu-id="efac3-141">Enterprise wi-fi profiles</span></span>

<span data-ttu-id="efac3-142">Um **resultado de Consultoria** significa que você está usando alguns perfis wi-fi que precisam de certificados e perfis para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="efac3-142">An **Advisory** result means that you are using some wi-fi profiles that need certificates and profiles to work properly.</span></span> <span data-ttu-id="efac3-143">Para obter mais informações, [consulte Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span><span class="sxs-lookup"><span data-stu-id="efac3-143">For more information, see [Deploy certificates and Wi-Fi/VPN profile](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile).</span></span>

#### <a name="lan-profiles"></a><span data-ttu-id="efac3-144">Perfis de LAN</span><span class="sxs-lookup"><span data-stu-id="efac3-144">LAN profiles</span></span>

<span data-ttu-id="efac3-145">Um **resultado de Consultoria** significa que você tem LANs que precisam de certificados e perfis para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="efac3-145">An **Advisory** result means that you have LANs that need certificates and profiles to work properly.</span></span> <span data-ttu-id="efac3-146">Para obter mais informações, [consulte Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="efac3-146">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="vpn-profiles"></a><span data-ttu-id="efac3-147">Perfis VPN</span><span class="sxs-lookup"><span data-stu-id="efac3-147">VPN profiles</span></span>

<span data-ttu-id="efac3-148">Um **resultado de Consultoria** significa que você está usando uma VPN (rede virtual privada).</span><span class="sxs-lookup"><span data-stu-id="efac3-148">An **Advisory** result means that you're using a virtual private network (VPN).</span></span> <span data-ttu-id="efac3-149">Crie um perfil VPN que implante certificados integrados ao Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="efac3-149">Create a VPN profile that deploys certificates integrated with Microsoft Intune.</span></span> <span data-ttu-id="efac3-150">Para obter mais informações, [consulte Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="efac3-150">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

#### <a name="mapped-drives"></a><span data-ttu-id="efac3-151">Unidades mapeadas</span><span class="sxs-lookup"><span data-stu-id="efac3-151">Mapped drives</span></span>

<span data-ttu-id="efac3-152">Um **resultado de Consultoria** significa que você tem algumas unidades mapeadas, que não são recomendadas.</span><span class="sxs-lookup"><span data-stu-id="efac3-152">An **Advisory** result means that you have some mapped drives, which aren't recommended.</span></span> <span data-ttu-id="efac3-153">Para obter mais informações, [consulte Preparar unidades mapeadas para a Área de Trabalho Gerenciada da Microsoft.](mapped-drives.md)</span><span class="sxs-lookup"><span data-stu-id="efac3-153">For more information, see [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).</span></span>

#### <a name="print-queues"></a><span data-ttu-id="efac3-154">Filas de impressão</span><span class="sxs-lookup"><span data-stu-id="efac3-154">Print queues</span></span>

<span data-ttu-id="efac3-155">Um **resultado de Consultoria** significa que você tem algumas filas de impressão pendentes, que não são recomendadas.</span><span class="sxs-lookup"><span data-stu-id="efac3-155">An **Advisory** result means that you have some outstanding print queues, which aren't recommended.</span></span> <span data-ttu-id="efac3-156">Uma solução é usar a impressão em nuvem.</span><span class="sxs-lookup"><span data-stu-id="efac3-156">One solution is to use cloud printing.</span></span> <span data-ttu-id="efac3-157">Para obter mais informações, [consulte Prepare printing resources for Microsoft Managed Desktop](printing.md).</span><span class="sxs-lookup"><span data-stu-id="efac3-157">For more information, see [Prepare printing resources for Microsoft Managed Desktop](printing.md).</span></span>

#### <a name="proxies"></a><span data-ttu-id="efac3-158">Proxies</span><span class="sxs-lookup"><span data-stu-id="efac3-158">Proxies</span></span>

<span data-ttu-id="efac3-159">Um **resultado de Consultoria** significa que você tem um servidor proxy em uso.</span><span class="sxs-lookup"><span data-stu-id="efac3-159">An **Advisory** result means that you have a proxy server in use.</span></span> <span data-ttu-id="efac3-160">Para obter mais informações, consulte [Configuração de rede para Área de Trabalho Gerenciada da Microsoft.](network.md)</span><span class="sxs-lookup"><span data-stu-id="efac3-160">For more information, see [Network configuration for Microsoft Managed Desktop](network.md).</span></span>

