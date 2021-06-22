---
title: Descoberta e Gerenciamento de Vulnerabilidades
description: As recomendações de segurança e a detecção de vulnerabilidades agora estão disponíveis para sistemas operacionais de comutadores, roteadores, controladores WLAN e firewalls.
keywords: dispositivos de rede, detecção de vulnerabilidade de dispositivos de rede, sistemas operacionais de comutadores, roteadores, controladores WLAN e firewalls
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 86b8a37fd6b2d6f9906321b5d74de0e21c45fca3
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062143"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="77e99-104">Descoberta e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="77e99-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77e99-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="77e99-105">**Applies to:**</span></span>

- [<span data-ttu-id="77e99-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="77e99-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="77e99-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="77e99-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="77e99-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77e99-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="77e99-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="77e99-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77e99-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="77e99-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="77e99-111">O Blog de avaliação de vulnerabilidade e descoberta de [dispositivos](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) de rede publicado em \( 13/04/2021 fornece informações sobre os novos recursos de descoberta de dispositivos de rede no \) Defender for Endpoint. </span><span class="sxs-lookup"><span data-stu-id="77e99-111">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="77e99-112">Este artigo fornece uma visão  geral do desafio que a descoberta de dispositivos de rede foi projetada para resolver e informações detalhadas sobre como começar a usar esses novos recursos.</span><span class="sxs-lookup"><span data-stu-id="77e99-112">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="77e99-113">Os recursos de descoberta de rede estão disponíveis na **seção** Inventário de dispositivos do centro Microsoft 365 de segurança e Central de Segurança do Microsoft Defender consoles.</span><span class="sxs-lookup"><span data-stu-id="77e99-113">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="77e99-114">Um dispositivo do Microsoft Defender for Endpoint designado será usado em cada segmento de rede para executar verificações autenticadas periódicas de dispositivos de rede pré-configurados.</span><span class="sxs-lookup"><span data-stu-id="77e99-114">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="77e99-115">Depois de descoberto, os recursos de Gerenciamento de Ameaças e Vulnerabilidades do Defender for Endpoint fornecem fluxos de trabalho integrados para proteger comutadores, roteadores, controladores WLAN, firewalls e gateways VPN descobertos.</span><span class="sxs-lookup"><span data-stu-id="77e99-115">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="77e99-116">Depois que os dispositivos de rede são descobertos e classificados, os administradores de segurança poderão receber as recomendações de segurança mais recentes e revisar as vulnerabilidades descobertas recentemente em dispositivos de rede implantados em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="77e99-116">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="77e99-117">Abordagem</span><span class="sxs-lookup"><span data-stu-id="77e99-117">Approach</span></span>

<span data-ttu-id="77e99-118">Os dispositivos de rede não são gerenciados como pontos de extremidade padrão, pois o Defender para Ponto de Extremidade não tem um sensor integrado nos dispositivos de rede.</span><span class="sxs-lookup"><span data-stu-id="77e99-118">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="77e99-119">Esses tipos de dispositivos exigem uma abordagem sem agente em que uma verificação remota obterá as informações necessárias dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="77e99-119">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="77e99-120">Dependendo da topologia de rede e das características, um único dispositivo ou alguns dispositivos conectados ao Microsoft Defender para Ponto de Extremidade executará verificações autenticadas de dispositivos de rede usando SNMP (somente leitura).</span><span class="sxs-lookup"><span data-stu-id="77e99-120">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="77e99-121">Haverá dois tipos de dispositivos para ter em mente:</span><span class="sxs-lookup"><span data-stu-id="77e99-121">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="77e99-122">**Dispositivo de** avaliação : um dispositivo que já está conectado que você usará para examinar os dispositivos de rede.</span><span class="sxs-lookup"><span data-stu-id="77e99-122">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="77e99-123">**Dispositivos de** rede : os dispositivos de rede que você planeja examinar e integrar.</span><span class="sxs-lookup"><span data-stu-id="77e99-123">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="77e99-124">Gerenciamento de vulnerabilidades para dispositivos de rede</span><span class="sxs-lookup"><span data-stu-id="77e99-124">Vulnerability management for network devices</span></span> 

<span data-ttu-id="77e99-125">Depois que os dispositivos de rede são descobertos e classificados, os administradores de segurança poderão receber as recomendações de segurança mais recentes e revisar as vulnerabilidades descobertas recentemente em dispositivos de rede implantados em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="77e99-125">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="77e99-126">Sistemas operacionais com suporte</span><span class="sxs-lookup"><span data-stu-id="77e99-126">Operating systems that are supported</span></span>

<span data-ttu-id="77e99-127">No momento, há suporte para os seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="77e99-127">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="77e99-128">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="77e99-128">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="77e99-129">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="77e99-129">Juniper JUNOS</span></span>
- <span data-ttu-id="77e99-130">HPE ArubaOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="77e99-130">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="77e99-131">Pan-OS de Redes de Palo Alto</span><span class="sxs-lookup"><span data-stu-id="77e99-131">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="77e99-132">Mais fornecedores de rede e sistema operacional serão adicionados ao longo do tempo, com base nos dados coletados do uso do cliente.</span><span class="sxs-lookup"><span data-stu-id="77e99-132">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="77e99-133">Portanto, você é incentivado a configurar todos os dispositivos de rede, mesmo que eles não sejam especificados nesta lista.</span><span class="sxs-lookup"><span data-stu-id="77e99-133">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="77e99-134">Como iniciar</span><span class="sxs-lookup"><span data-stu-id="77e99-134">How to get started</span></span>

<span data-ttu-id="77e99-135">Sua primeira etapa é selecionar um dispositivo que executará as verificações de rede autenticadas.</span><span class="sxs-lookup"><span data-stu-id="77e99-135">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="77e99-136">Decida um dispositivo (cliente ou servidor) do Defender for Endpoint que tenha uma conexão de rede com a porta de gerenciamento dos dispositivos de rede que você planeja fazer a verificação.</span><span class="sxs-lookup"><span data-stu-id="77e99-136">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="77e99-137">O tráfego SNMP entre o dispositivo de avaliação do Defender para o Ponto de Extremidade e os dispositivos de rede direcionados deve ser permitido (por exemplo, pelo Firewall).</span><span class="sxs-lookup"><span data-stu-id="77e99-137">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="77e99-138">Decida quais dispositivos de rede serão avaliados em busca de vulnerabilidades (por exemplo: uma opção Cisco ou um firewall de Redes de Palo Alto).</span><span class="sxs-lookup"><span data-stu-id="77e99-138">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="77e99-139">Certifique-se de que somente leitura SNMP está habilitado em todos os dispositivos de rede configurados para permitir que o dispositivo de avaliação do Defender for Endpoint consulte os dispositivos de rede configurados.</span><span class="sxs-lookup"><span data-stu-id="77e99-139">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="77e99-140">'Gravação SNMP' não é necessária para a funcionalidade adequada deste recurso.</span><span class="sxs-lookup"><span data-stu-id="77e99-140">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="77e99-141">Obtenha os endereços IP dos dispositivos de rede a serem verificados (ou as sub-redes onde esses dispositivos são implantados).</span><span class="sxs-lookup"><span data-stu-id="77e99-141">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="77e99-142">Obtenha as credenciais SNMP dos dispositivos de rede (por exemplo: string Community, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="77e99-142">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="77e99-143">Você será obrigado a fornecer as credenciais ao configurar um novo trabalho de avaliação.</span><span class="sxs-lookup"><span data-stu-id="77e99-143">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="77e99-144">Configuração do cliente proxy: nenhuma configuração extra é necessária além dos requisitos de proxy do dispositivo Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="77e99-144">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="77e99-145">Para permitir que o scanner de rede seja autenticado e funcione corretamente, é essencial adicionar os seguintes domínios/URLs:</span><span class="sxs-lookup"><span data-stu-id="77e99-145">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="77e99-146">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="77e99-146">login.windows.net</span></span>  
    - <span data-ttu-id="77e99-147">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="77e99-147">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="77e99-148">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="77e99-148">login.microsoftonline.com</span></span>
    - <span data-ttu-id="77e99-149">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="77e99-149">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="77e99-150">Nem todas as URLs são especificadas na lista documentada do Defender for Endpoint da coleção de dados permitida.</span><span class="sxs-lookup"><span data-stu-id="77e99-150">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="77e99-151">Permissões</span><span class="sxs-lookup"><span data-stu-id="77e99-151">Permissions</span></span>

<span data-ttu-id="77e99-152">Para configurar trabalhos de avaliação, a seguinte opção de permissão de usuário é necessária: **Gerenciar configurações de segurança no Centro de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="77e99-152">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="77e99-153">Você pode encontrar a permissão indo **para** Configurações  >  **Funções**.</span><span class="sxs-lookup"><span data-stu-id="77e99-153">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="77e99-154">Para obter mais informações, [consulte Create and manage roles for role-based access control](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="77e99-154">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="77e99-155">Instalar o scanner de rede</span><span class="sxs-lookup"><span data-stu-id="77e99-155">Install the network scanner</span></span>

1. <span data-ttu-id="77e99-156">Vá para os **Microsoft 365 de Configurações** de Avaliação de Pontos de Extremidade  >    >    >   (em **Avaliações de rede).**</span><span class="sxs-lookup"><span data-stu-id="77e99-156">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="77e99-157">Na Central de Segurança do Microsoft Defender, vá para a página Trabalhos de Avaliação Configurações > Avaliação.</span><span class="sxs-lookup"><span data-stu-id="77e99-157">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="77e99-158">Baixe o scanner de rede e instale-o no dispositivo de avaliação do Defender para Ponto de Extremidade designado.</span><span class="sxs-lookup"><span data-stu-id="77e99-158">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="77e99-159">![Botão Baixar scanner](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="77e99-159">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="77e99-160">Instalação do scanner de rede & registro</span><span class="sxs-lookup"><span data-stu-id="77e99-160">Network scanner installation & registration</span></span>

<span data-ttu-id="77e99-161">O processo de entrada pode ser concluído no próprio dispositivo de avaliação designado ou em qualquer outro dispositivo (por exemplo, seu dispositivo cliente pessoal).</span><span class="sxs-lookup"><span data-stu-id="77e99-161">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="77e99-162">Para concluir o processo de registro do scanner de rede:</span><span class="sxs-lookup"><span data-stu-id="77e99-162">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="77e99-163">Copie e siga a URL que aparece na linha de comando e use o código de instalação fornecido para concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="77e99-163">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77e99-164">Talvez seja necessário alterar as configurações do Prompt de Comando para poder copiar a URL.</span><span class="sxs-lookup"><span data-stu-id="77e99-164">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="77e99-165">Insira o código e entre usando uma conta da Microsoft que tenha a permissão Defender para Ponto de Extremidade chamada "Gerenciar configurações de segurança no Centro de Segurança".</span><span class="sxs-lookup"><span data-stu-id="77e99-165">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="77e99-166">Quando terminar, você deverá ver uma mensagem confirmando que você se inscreveu.</span><span class="sxs-lookup"><span data-stu-id="77e99-166">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="77e99-167">Configurar um novo trabalho de avaliação</span><span class="sxs-lookup"><span data-stu-id="77e99-167">Configure a new assessment job</span></span>  

<span data-ttu-id="77e99-168">Na página Trabalhos de Avaliação **em Configurações**, selecione Adicionar trabalho **de avaliação de rede**.</span><span class="sxs-lookup"><span data-stu-id="77e99-168">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="77e99-169">Siga o processo de configuração para escolher dispositivos de rede a serem verificados regularmente e adicionados ao inventário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77e99-169">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="77e99-170">Para impedir a duplicação de dispositivos no inventário de dispositivos de rede, certifique-se de que cada endereço IP está configurado apenas uma vez em vários dispositivos de avaliação.</span><span class="sxs-lookup"><span data-stu-id="77e99-170">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77e99-171">![Adicionar botão de trabalho de avaliação de rede](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="77e99-171">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="77e99-172">Adicionando etapas de trabalho de avaliação de rede:</span><span class="sxs-lookup"><span data-stu-id="77e99-172">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="77e99-173">Escolha um nome "Trabalho de Avaliação" e o "Dispositivo de Avaliação" no qual o scanner de rede foi instalado.</span><span class="sxs-lookup"><span data-stu-id="77e99-173">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="77e99-174">Este dispositivo executará as verificações autenticadas periódicas.</span><span class="sxs-lookup"><span data-stu-id="77e99-174">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="77e99-175">Adicione endereços IP de dispositivos de rede de destino a serem verificados (ou as sub-redes onde esses dispositivos são implantados).</span><span class="sxs-lookup"><span data-stu-id="77e99-175">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="77e99-176">Adicione credenciais SNMP necessárias dos dispositivos de rede de destino.</span><span class="sxs-lookup"><span data-stu-id="77e99-176">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="77e99-177">Salve o trabalho de avaliação de rede recém-configurado para iniciar a verificação periódica da rede.</span><span class="sxs-lookup"><span data-stu-id="77e99-177">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="77e99-178">Examinar e adicionar dispositivos de rede</span><span class="sxs-lookup"><span data-stu-id="77e99-178">Scan and add network devices</span></span>

<span data-ttu-id="77e99-179">Durante o processo de configuração, você pode executar uma verificação de teste de uma única vez para verificar se:</span><span class="sxs-lookup"><span data-stu-id="77e99-179">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="77e99-180">Há conectividade entre o dispositivo de avaliação do Defender for Endpoint e os dispositivos de rede de destino configurados.</span><span class="sxs-lookup"><span data-stu-id="77e99-180">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="77e99-181">As credenciais SNMP configuradas estão corretas.</span><span class="sxs-lookup"><span data-stu-id="77e99-181">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="77e99-182">Cada dispositivo de avaliação pode suportar até 1.500 endereços IP bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="77e99-182">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="77e99-183">Por exemplo, se você examinar 10 sub-redes diferentes em que apenas 100 endereços IP retornam resultados bem-sucedidos, você poderá verificar 1.400 endereços IP adicionais de outras sub-redes no mesmo dispositivo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="77e99-183">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="77e99-184">Se houver vários intervalos de endereços IP/sub-redes a verificar, os resultados da verificação de teste levarão vários minutos para aparecer.</span><span class="sxs-lookup"><span data-stu-id="77e99-184">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="77e99-185">Uma verificação de teste estará disponível para até 1.024 endereços.</span><span class="sxs-lookup"><span data-stu-id="77e99-185">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="77e99-186">Depois que os resultados aparecerem, você poderá escolher quais dispositivos serão incluídos na verificação periódica.</span><span class="sxs-lookup"><span data-stu-id="77e99-186">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="77e99-187">Se você ignorar a exibição dos resultados da verificação, todos os endereços IP configurados serão adicionados ao trabalho de avaliação de rede (independentemente da resposta do dispositivo).</span><span class="sxs-lookup"><span data-stu-id="77e99-187">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="77e99-188">Os resultados da verificação também podem ser exportados.</span><span class="sxs-lookup"><span data-stu-id="77e99-188">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="77e99-189">Inventário de dispositivos</span><span class="sxs-lookup"><span data-stu-id="77e99-189">Device inventory</span></span>

<span data-ttu-id="77e99-190">Os dispositivos recém-descobertos serão mostrados na nova guia **Dispositivos** de rede na página **Inventário de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="77e99-190">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="77e99-191">Pode levar até duas horas após adicionar um trabalho de avaliação até que os dispositivos sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="77e99-191">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="77e99-192">![Seção Dispositivos de rede no inventário de dispositivos](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="77e99-192">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="77e99-193">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="77e99-193">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="77e99-194">Falha na instalação do scanner de rede</span><span class="sxs-lookup"><span data-stu-id="77e99-194">Network scanner installation has failed</span></span>

<span data-ttu-id="77e99-195">Verifique se as URLs necessárias são adicionadas aos domínios permitidos em suas configurações de firewall.</span><span class="sxs-lookup"><span data-stu-id="77e99-195">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="77e99-196">Além disso, certifique-se de que as configurações de proxy estão configuradas conforme descrito em [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="77e99-196">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="77e99-197">A Microsoft.com/devicelogin da Web não foi a aparecer</span><span class="sxs-lookup"><span data-stu-id="77e99-197">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="77e99-198">Verifique se as URLs necessárias são adicionadas aos domínios permitidos no firewall.</span><span class="sxs-lookup"><span data-stu-id="77e99-198">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="77e99-199">Além disso, certifique-se de que as configurações de proxy estão configuradas conforme descrito em [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="77e99-199">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="77e99-200">Os dispositivos de rede não são mostrados no inventário de dispositivos após várias horas</span><span class="sxs-lookup"><span data-stu-id="77e99-200">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="77e99-201">Os resultados da verificação devem ser atualizados algumas horas após a verificação inicial que ocorreu após a conclusão da configuração do trabalho de avaliação.</span><span class="sxs-lookup"><span data-stu-id="77e99-201">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="77e99-202">Se os dispositivos ainda não são mostrados, verifique se o serviço 'MdatpNetworkScanService' está sendo executado em seus dispositivos de avaliação, nos quais você instalou o scanner de rede, e execute uma "Verificação de execução" na configuração de trabalho de avaliação relevante.</span><span class="sxs-lookup"><span data-stu-id="77e99-202">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="77e99-203">Se você ainda não receber resultados após 5 minutos, reinicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="77e99-203">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="77e99-204">O tempo visto pela última vez por dispositivos é maior do que 24 horas</span><span class="sxs-lookup"><span data-stu-id="77e99-204">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="77e99-205">Valide se o scanner está sendo executado corretamente.</span><span class="sxs-lookup"><span data-stu-id="77e99-205">Validate that the scanner is running properly.</span></span> <span data-ttu-id="77e99-206">Em seguida, vá para a definição de verificação e selecione "Executar teste".</span><span class="sxs-lookup"><span data-stu-id="77e99-206">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="77e99-207">Verifique quais mensagens de erro estão retornando dos endereços IP relevantes.</span><span class="sxs-lookup"><span data-stu-id="77e99-207">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="77e99-208">Permissão de Gerenciamento de Ameaças e Vulnerabilidades usuário necessária</span><span class="sxs-lookup"><span data-stu-id="77e99-208">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="77e99-209">O registro terminou com um erro: "Parece que você não tem permissões suficientes para adicionar um novo agente.</span><span class="sxs-lookup"><span data-stu-id="77e99-209">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="77e99-210">A permissão necessária é "Gerenciar configurações de segurança no Centro de Segurança".</span><span class="sxs-lookup"><span data-stu-id="77e99-210">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="77e99-211">Pressione qualquer tecla para sair.</span><span class="sxs-lookup"><span data-stu-id="77e99-211">Press any key to exit.</span></span>

<span data-ttu-id="77e99-212">Peça ao administrador do sistema para atribuir as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="77e99-212">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="77e99-213">Como alternativa, peça a outro membro relevante para ajudá-lo com o processo de login fornecendo a eles o código de login e o link.</span><span class="sxs-lookup"><span data-stu-id="77e99-213">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="77e99-214">Falha no processo de registro usando o link fornecido na linha de comando no processo de registro</span><span class="sxs-lookup"><span data-stu-id="77e99-214">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="77e99-215">Experimente um navegador diferente ou copie o link de entrada e o código para um dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="77e99-215">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="77e99-216">Texto muito pequeno ou não pode copiar texto da linha de comando</span><span class="sxs-lookup"><span data-stu-id="77e99-216">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="77e99-217">Altere as configurações da linha de comando em seu dispositivo para permitir copiar e alterar o tamanho do texto.</span><span class="sxs-lookup"><span data-stu-id="77e99-217">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="77e99-218">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="77e99-218">Related articles</span></span>

- [<span data-ttu-id="77e99-219">Inventário de dispositivos</span><span class="sxs-lookup"><span data-stu-id="77e99-219">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="77e99-220">Configurar recursos avançados</span><span class="sxs-lookup"><span data-stu-id="77e99-220">Configure advanced features</span></span>](advanced-features.md)
