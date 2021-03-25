---
title: Implantação com um sistema MDM (Gerenciamento de Dispositivo Móvel) diferente para o Microsoft Defender ATP para Mac
description: Instale o Microsoft Defender ATP para Mac em outras soluções de gerenciamento.
keywords: microsoft, defender, atp, mac, installation, deploy, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e3a20f0a356a32eddc05b3792c0c04c23197a7b0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185690"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="cf3e5-104">Implantação com um sistema MDM (Gerenciamento de Dispositivo Móvel) diferente para o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="cf3e5-104">Deployment with a different Mobile Device Management (MDM) system for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="cf3e5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cf3e5-105">**Applies to:**</span></span>
- [<span data-ttu-id="cf3e5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cf3e5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cf3e5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf3e5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cf3e5-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cf3e5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cf3e5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="cf3e5-110">Pré-requisitos e requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="cf3e5-110">Prerequisites and system requirements</span></span>

<span data-ttu-id="cf3e5-111">Antes de começar, consulte a página principal do [Microsoft Defender para Ponto](microsoft-defender-endpoint-mac.md) de Extremidade para Mac para obter uma descrição dos pré-requisitos e requisitos do sistema para a versão de software atual.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-111">Before you get started, see [the main Microsoft Defender for Endpoint for Mac page](microsoft-defender-endpoint-mac.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="approach"></a><span data-ttu-id="cf3e5-112">Abordagem</span><span class="sxs-lookup"><span data-stu-id="cf3e5-112">Approach</span></span>

> [!CAUTION]
> <span data-ttu-id="cf3e5-113">Atualmente, a Microsoft dá suporte oficial apenas ao Intune e ao JAMF para implantação e gerenciamento do Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-113">Currently, Microsoft oficially supports only Intune and JAMF for the deployment and management of Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="cf3e5-114">A Microsoft não faz garantias, expressas ou implícitas, com relação às informações fornecidas abaixo.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-114">Microsoft makes no warranties, express or implied, with respect to the information provided below.</span></span>

<span data-ttu-id="cf3e5-115">Se sua organização usa uma solução MDM (Gerenciamento de Dispositivo Móvel) que não tem suporte oficial, isso não significa que você não é capaz de implantar ou executar o Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-115">If your organization uses a Mobile Device Management (MDM) solution that is not officially supported, this does not mean you are unable to deploy or run Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="cf3e5-116">O Microsoft Defender para Ponto de Extremidade para Mac não depende de recursos específicos do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-116">Microsoft Defender for Endpoint for Mac does not depend on any vendor-specific features.</span></span> <span data-ttu-id="cf3e5-117">Ele pode ser usado com qualquer solução MDM que oferece suporte aos seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="cf3e5-117">It can be used with any MDM solution that supports the following features:</span></span>

- <span data-ttu-id="cf3e5-118">Implante um macOS .pkg em dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-118">Deploy a macOS .pkg to managed devices.</span></span>
- <span data-ttu-id="cf3e5-119">Implantar perfis de configuração do sistema macOS em dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-119">Deploy macOS system configuration profiles to managed devices.</span></span>
- <span data-ttu-id="cf3e5-120">Execute uma ferramenta/script arbitrária configurada pelo administrador em dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-120">Run an arbitrary admin-configured tool/script on managed devices.</span></span>

<span data-ttu-id="cf3e5-121">A maioria das soluções MDM modernas incluem esses recursos, no entanto, eles podem chamá-los de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-121">Most modern MDM solutions include these features, however, they may call them differently.</span></span>

<span data-ttu-id="cf3e5-122">No entanto, você pode implantar o Defender sem o último requisito da lista anterior:</span><span class="sxs-lookup"><span data-stu-id="cf3e5-122">You can deploy Defender without the last requirement from the preceding list, however:</span></span>

- <span data-ttu-id="cf3e5-123">Você não poderá coletar status de forma centralizada</span><span class="sxs-lookup"><span data-stu-id="cf3e5-123">You will not be able to collect status in a centralized way</span></span>
- <span data-ttu-id="cf3e5-124">Se você decidir desinstalar o Defender, precisará fazer logoff no dispositivo cliente localmente como administrador</span><span class="sxs-lookup"><span data-stu-id="cf3e5-124">If you decide to uninstall Defender, you will need to log on to the client device locally as an administrator</span></span>

## <a name="deployment"></a><span data-ttu-id="cf3e5-125">Implantação</span><span class="sxs-lookup"><span data-stu-id="cf3e5-125">Deployment</span></span>

<span data-ttu-id="cf3e5-126">A maioria das soluções MDM usa o mesmo modelo para gerenciar dispositivos macOS, com terminologia semelhante.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-126">Most MDM solutions use the same model for managing macOS devices, with similar terminology.</span></span> <span data-ttu-id="cf3e5-127">Use [a implantação baseada em JAMF](mac-install-with-jamf.md) como modelo.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-127">Use [JAMF-based deployment](mac-install-with-jamf.md) as a template.</span></span>

### <a name="package"></a><span data-ttu-id="cf3e5-128">Pacote</span><span class="sxs-lookup"><span data-stu-id="cf3e5-128">Package</span></span>

<span data-ttu-id="cf3e5-129">Configurar a implantação [de um pacote de](mac-install-with-jamf.md)aplicativos necessário , com o pacote de instalação (wdav.pkg) baixado do Centro de Segurança do Microsoft [Defender](mac-install-with-jamf.md).</span><span class="sxs-lookup"><span data-stu-id="cf3e5-129">Configure deployment of a [required application package](mac-install-with-jamf.md), with the installation package (wdav.pkg) downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>

<span data-ttu-id="cf3e5-130">Para implantar o pacote em sua empresa, use as instruções associadas à sua solução MDM.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-130">In order to deploy the package to your enterprise, use the instructions associated with your MDM solution.</span></span>

### <a name="license-settings"></a><span data-ttu-id="cf3e5-131">Configurações de licença</span><span class="sxs-lookup"><span data-stu-id="cf3e5-131">License settings</span></span>

<span data-ttu-id="cf3e5-132">Configurar um [perfil de configuração do sistema.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="cf3e5-132">Set up [a system configuration profile](mac-install-with-jamf.md).</span></span> <span data-ttu-id="cf3e5-133">Sua solução MDM pode chamá-la de algo como "Perfil de Configurações Personalizadas", pois o Microsoft Defender para Ponto de Extremidade para Mac não faz parte do macOS.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-133">Your MDM solution may call it something like "Custom Settings Profile", as Microsoft Defender for Endpoint for Mac is not part of macOS.</span></span>

<span data-ttu-id="cf3e5-134">Use a lista de propriedades, jamf/WindowsDefenderATPOnboarding.plist, que pode ser extraída de um pacote de integração baixado do Centro de Segurança do [Microsoft Defender.](mac-install-with-jamf.md)</span><span class="sxs-lookup"><span data-stu-id="cf3e5-134">Use the property list, jamf/WindowsDefenderATPOnboarding.plist, which can be extracted from an onboarding package downloaded from [Microsoft Defender Security Center](mac-install-with-jamf.md).</span></span>
<span data-ttu-id="cf3e5-135">Seu sistema pode dar suporte a uma lista de propriedades arbitrárias no formato XML.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-135">Your system may support an arbitrary property list in XML format.</span></span> <span data-ttu-id="cf3e5-136">Você pode carregar o arquivo jamf/WindowsDefenderATPOnboarding.plist como está nesse caso.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-136">You can upload the jamf/WindowsDefenderATPOnboarding.plist file as-is in that case.</span></span>
<span data-ttu-id="cf3e5-137">Como alternativa, pode exigir que você converta a lista de propriedades em um formato diferente primeiro.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-137">Alternatively, it may require you to convert the property list to a different format first.</span></span>

<span data-ttu-id="cf3e5-138">Normalmente, seu perfil personalizado tem uma ID, nome ou atributo de domínio.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-138">Typically, your custom profile has an ID, name, or domain attribute.</span></span> <span data-ttu-id="cf3e5-139">Você deve usar exatamente "com.microsoft.wdav.atp" para esse valor.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-139">You must use exactly "com.microsoft.wdav.atp" for this value.</span></span>
<span data-ttu-id="cf3e5-140">O MDM o usa para implantar o arquivo de configurações em **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** em um dispositivo cliente, e o Defender usa esse arquivo para carregar as informações de integração.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-140">MDM uses it to deploy the settings file to **/Library/Managed Preferences/com.microsoft.wdav.atp.plist** on a client device, and Defender uses this file for loading the onboarding information.</span></span>

### <a name="kernel-extension-policy"></a><span data-ttu-id="cf3e5-141">Política de extensão de kernel</span><span class="sxs-lookup"><span data-stu-id="cf3e5-141">Kernel extension policy</span></span>

<span data-ttu-id="cf3e5-142">Configurar uma política de extensão KEXT ou kernel.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-142">Set up a KEXT or kernel extension policy.</span></span> <span data-ttu-id="cf3e5-143">Use o identificador de **equipe UBF8T346G9** para permitir extensões de kernel fornecidas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-143">Use team identifier **UBF8T346G9** to allow kernel extensions provided by Microsoft.</span></span>

### <a name="system-extension-policy"></a><span data-ttu-id="cf3e5-144">Política de extensão do sistema</span><span class="sxs-lookup"><span data-stu-id="cf3e5-144">System extension policy</span></span>

<span data-ttu-id="cf3e5-145">Configurar uma política de extensão do sistema.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-145">Set up a system extension policy.</span></span> <span data-ttu-id="cf3e5-146">Use o identificador de **equipe UBF8T346G9** e aprove os seguintes identificadores de pacote:</span><span class="sxs-lookup"><span data-stu-id="cf3e5-146">Use team identifier **UBF8T346G9** and approve the following bundle identifiers:</span></span>

- <span data-ttu-id="cf3e5-147">com.microsoft.wdav.epsext</span><span class="sxs-lookup"><span data-stu-id="cf3e5-147">com.microsoft.wdav.epsext</span></span>
- <span data-ttu-id="cf3e5-148">com.microsoft.wdav.netext</span><span class="sxs-lookup"><span data-stu-id="cf3e5-148">com.microsoft.wdav.netext</span></span>

### <a name="full-disk-access-policy"></a><span data-ttu-id="cf3e5-149">Política de acesso em disco completo</span><span class="sxs-lookup"><span data-stu-id="cf3e5-149">Full disk access policy</span></span>

<span data-ttu-id="cf3e5-150">Conceda acesso em disco completo aos seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="cf3e5-150">Grant Full Disk Access to the following components:</span></span>

- <span data-ttu-id="cf3e5-151">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cf3e5-151">Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="cf3e5-152">Identificador: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-152">Identifier: `com.microsoft.wdav`</span></span>
    - <span data-ttu-id="cf3e5-153">Tipo de identificador: ID do pacote</span><span class="sxs-lookup"><span data-stu-id="cf3e5-153">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="cf3e5-154">Requisito de código: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-154">Code Requirement: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

- <span data-ttu-id="cf3e5-155">Extensão de Segurança do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cf3e5-155">Microsoft Defender for Endpoint Security Extension</span></span>
    - <span data-ttu-id="cf3e5-156">Identificador: `com.microsoft.wdav.epsext`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-156">Identifier: `com.microsoft.wdav.epsext`</span></span>
    - <span data-ttu-id="cf3e5-157">Tipo de identificador: ID do pacote</span><span class="sxs-lookup"><span data-stu-id="cf3e5-157">Identifier Type: Bundle ID</span></span>
    - <span data-ttu-id="cf3e5-158">Requisito de código: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-158">Code Requirement: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>

### <a name="network-extension-policy"></a><span data-ttu-id="cf3e5-159">Política de extensão de rede</span><span class="sxs-lookup"><span data-stu-id="cf3e5-159">Network extension policy</span></span>

<span data-ttu-id="cf3e5-160">Como parte dos recursos de Detecção e Resposta do Ponto de Extremidade, o Microsoft Defender para Ponto de Extremidade para Mac inspeciona o tráfego de soquete e relata essas informações ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-160">As part of the Endpoint Detection and Response capabilities, Microsoft Defender for Endpoint for Mac inspects socket traffic and reports this information to the Microsoft Defender Security Center portal.</span></span> <span data-ttu-id="cf3e5-161">A política a seguir permite que a extensão de rede execute essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-161">The following policy allows the network extension to perform this functionality.</span></span>

- <span data-ttu-id="cf3e5-162">Tipo de filtro: Plug-in</span><span class="sxs-lookup"><span data-stu-id="cf3e5-162">Filter type: Plugin</span></span>
- <span data-ttu-id="cf3e5-163">Identificador do pacote de plug-in: `com.microsoft.wdav`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-163">Plugin bundle identifier: `com.microsoft.wdav`</span></span>
- <span data-ttu-id="cf3e5-164">Filtrar o identificador de pacote do provedor de dados: `com.microsoft.wdav.netext`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-164">Filter data provider bundle identifier: `com.microsoft.wdav.netext`</span></span>
- <span data-ttu-id="cf3e5-165">Requisito designado do provedor de dados de filtro: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-165">Filter data provider designated requirement: `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`</span></span>
- <span data-ttu-id="cf3e5-166">Soquetes de filtro: `true`</span><span class="sxs-lookup"><span data-stu-id="cf3e5-166">Filter sockets: `true`</span></span>

## <a name="check-installation-status"></a><span data-ttu-id="cf3e5-167">Verificar o status da instalação</span><span class="sxs-lookup"><span data-stu-id="cf3e5-167">Check installation status</span></span>

<span data-ttu-id="cf3e5-168">Execute [o Microsoft Defender para Ponto de](mac-install-with-jamf.md) Extremidade em um dispositivo cliente para verificar o status de integração.</span><span class="sxs-lookup"><span data-stu-id="cf3e5-168">Run [Microsoft Defender for Endpoint](mac-install-with-jamf.md) on a client device to check the onboarding status.</span></span>