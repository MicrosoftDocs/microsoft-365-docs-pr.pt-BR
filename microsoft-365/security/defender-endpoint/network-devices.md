---
title: Gerenciamento de vulnerabilidade e descoberta de dispositivo de rede
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
ms.openlocfilehash: d0ae82c2e284235d96531c04dc2240063d4e4183
ms.sourcegitcommit: dcc6bfd228ca9070975ce9eb14574e084f9ed92c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2021
ms.locfileid: "51657026"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="f9038-104">Gerenciamento de vulnerabilidade e descoberta de dispositivo de rede</span><span class="sxs-lookup"><span data-stu-id="f9038-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f9038-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f9038-105">**Applies to:**</span></span>

- [<span data-ttu-id="f9038-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f9038-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f9038-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="f9038-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f9038-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f9038-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="f9038-109">**A verificação e o gerenciamento de dispositivos de rede estão atualmente em visualização pública**</span><span class="sxs-lookup"><span data-stu-id="f9038-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="f9038-110">Esta versão de visualização é fornecida sem um contrato de nível de serviço e não é recomendada para cargas de trabalho de produção.</span><span class="sxs-lookup"><span data-stu-id="f9038-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="f9038-111">Determinados recursos podem não ser suportados ou podem ter recursos restritos.</span><span class="sxs-lookup"><span data-stu-id="f9038-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="f9038-112">Para obter mais informações, consulte Recursos de visualização do [Microsoft Defender for Endpoint](preview.md).</span><span class="sxs-lookup"><span data-stu-id="f9038-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="f9038-113">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f9038-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f9038-114">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f9038-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="f9038-115">Os recursos de descoberta de rede estão disponíveis na **seção** Inventário de dispositivos do Centro de Segurança do Microsoft 365 e consoles do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f9038-115">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="f9038-116">Um dispositivo do Microsoft Defender for Endpoint designado será usado em cada segmento de rede para executar verificações autenticadas periódicas de dispositivos de rede pré-configurados.</span><span class="sxs-lookup"><span data-stu-id="f9038-116">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="f9038-117">Depois de descoberto, os recursos de gerenciamento de ameaças e vulnerabilidades do Defender for Endpoint fornecem fluxos de trabalho integrados para proteger opções descobertas, roteadores, controladores WLAN, firewalls e gateways VPN.</span><span class="sxs-lookup"><span data-stu-id="f9038-117">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="f9038-118">Depois que os dispositivos de rede são descobertos e classificados, os administradores de segurança poderão receber as recomendações de segurança mais recentes e revisar as vulnerabilidades descobertas recentemente em dispositivos de rede implantados em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="f9038-118">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="f9038-119">Abordagem</span><span class="sxs-lookup"><span data-stu-id="f9038-119">Approach</span></span>

<span data-ttu-id="f9038-120">Os dispositivos de rede não são gerenciados como pontos de extremidade padrão, pois o Defender para Ponto de Extremidade não tem um sensor integrado nos dispositivos de rede.</span><span class="sxs-lookup"><span data-stu-id="f9038-120">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="f9038-121">Esses tipos de dispositivos exigem uma abordagem sem agente em que uma verificação remota obterá as informações necessárias dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f9038-121">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="f9038-122">Dependendo da topologia de rede e das características, um único dispositivo ou alguns dispositivos conectados ao Microsoft Defender para Ponto de Extremidade executará verificações autenticadas de dispositivos de rede usando SNMP (somente leitura).</span><span class="sxs-lookup"><span data-stu-id="f9038-122">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="f9038-123">Haverá dois tipos de dispositivos para ter em mente:</span><span class="sxs-lookup"><span data-stu-id="f9038-123">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="f9038-124">**Dispositivo de** avaliação : um dispositivo que já está conectado que você usará para examinar os dispositivos de rede.</span><span class="sxs-lookup"><span data-stu-id="f9038-124">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="f9038-125">**Dispositivos de** rede : os dispositivos de rede que você planeja examinar e integrar.</span><span class="sxs-lookup"><span data-stu-id="f9038-125">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="f9038-126">Gerenciamento de vulnerabilidades para dispositivos de rede</span><span class="sxs-lookup"><span data-stu-id="f9038-126">Vulnerability management for network devices</span></span> 

<span data-ttu-id="f9038-127">Depois que os dispositivos de rede são descobertos e classificados, os administradores de segurança poderão receber as recomendações de segurança mais recentes e revisar as vulnerabilidades descobertas recentemente em dispositivos de rede implantados em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="f9038-127">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="f9038-128">Sistemas operacionais com suporte</span><span class="sxs-lookup"><span data-stu-id="f9038-128">Operating systems that are supported</span></span>

<span data-ttu-id="f9038-129">No momento, há suporte para os seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="f9038-129">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="f9038-130">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="f9038-130">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="f9038-131">Juniper JUNOS</span><span class="sxs-lookup"><span data-stu-id="f9038-131">Juniper JUNOS</span></span>
- <span data-ttu-id="f9038-132">HPE ArubaOS, Procurve Switch Software</span><span class="sxs-lookup"><span data-stu-id="f9038-132">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="f9038-133">Pan-OS de Redes de Palo Alto</span><span class="sxs-lookup"><span data-stu-id="f9038-133">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="f9038-134">Mais fornecedores de rede e sistema operacional serão adicionados ao longo do tempo, com base nos dados coletados do uso do cliente.</span><span class="sxs-lookup"><span data-stu-id="f9038-134">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="f9038-135">Portanto, você é incentivado a configurar todos os dispositivos de rede, mesmo que eles não sejam especificados nesta lista.</span><span class="sxs-lookup"><span data-stu-id="f9038-135">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="f9038-136">Como iniciar</span><span class="sxs-lookup"><span data-stu-id="f9038-136">How to get started</span></span>

<span data-ttu-id="f9038-137">Sua primeira etapa é selecionar um dispositivo que executará as verificações de rede autenticadas.</span><span class="sxs-lookup"><span data-stu-id="f9038-137">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="f9038-138">Decida um dispositivo (cliente ou servidor) do Defender for Endpoint que tenha uma conexão de rede com a porta de gerenciamento dos dispositivos de rede que você planeja fazer a verificação.</span><span class="sxs-lookup"><span data-stu-id="f9038-138">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="f9038-139">O tráfego SNMP entre o dispositivo de avaliação do Defender para o Ponto de Extremidade e os dispositivos de rede direcionados deve ser permitido (por exemplo, pelo Firewall).</span><span class="sxs-lookup"><span data-stu-id="f9038-139">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="f9038-140">Decida quais dispositivos de rede serão avaliados em busca de vulnerabilidades (por exemplo: uma opção Cisco ou um firewall de Redes de Palo Alto).</span><span class="sxs-lookup"><span data-stu-id="f9038-140">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="f9038-141">Certifique-se de que somente leitura SNMP está habilitado em todos os dispositivos de rede configurados para permitir que o dispositivo de avaliação do Defender for Endpoint consulte os dispositivos de rede configurados.</span><span class="sxs-lookup"><span data-stu-id="f9038-141">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="f9038-142">'Gravação SNMP' não é necessária para a funcionalidade adequada deste recurso.</span><span class="sxs-lookup"><span data-stu-id="f9038-142">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="f9038-143">Obtenha os endereços IP dos dispositivos de rede a serem verificados (ou as sub-redes onde esses dispositivos são implantados).</span><span class="sxs-lookup"><span data-stu-id="f9038-143">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="f9038-144">Obtenha as credenciais SNMP dos dispositivos de rede (por exemplo: Cadeia de caracteres da comunidade, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="f9038-144">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="f9038-145">Você será obrigado a fornecer as credenciais ao configurar um novo trabalho de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f9038-145">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="f9038-146">Configuração do cliente proxy: nenhuma configuração extra é necessária além dos requisitos de proxy do dispositivo Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f9038-146">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="f9038-147">Para permitir que o scanner de rede seja autenticado e funcione corretamente, é essencial adicionar os seguintes domínios/URLs:</span><span class="sxs-lookup"><span data-stu-id="f9038-147">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="f9038-148">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="f9038-148">login.windows.net</span></span>  
    - <span data-ttu-id="f9038-149">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="f9038-149">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="f9038-150">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f9038-150">login.microsoftonline.com</span></span>
    - <span data-ttu-id="f9038-151">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="f9038-151">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    <span data-ttu-id="f9038-152">Observação: nem todas as URLs não são especificadas na lista documentada do Defender for Endpoint da coleção de dados permitida.</span><span class="sxs-lookup"><span data-stu-id="f9038-152">Note: Not all URLs are not specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="f9038-153">Permissões</span><span class="sxs-lookup"><span data-stu-id="f9038-153">Permissions</span></span>

<span data-ttu-id="f9038-154">Para configurar trabalhos de avaliação, a seguinte opção de permissão de usuário é necessária: **Gerenciar configurações de segurança no Centro de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="f9038-154">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="f9038-155">Você pode encontrar a permissão indo para **Configurações**  >  **Funções**.</span><span class="sxs-lookup"><span data-stu-id="f9038-155">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="f9038-156">Para obter mais informações, [consulte Create and manage roles for role-based access control](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f9038-156">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="f9038-157">Instalar o scanner de rede</span><span class="sxs-lookup"><span data-stu-id="f9038-157">Install the network scanner</span></span>

1. <span data-ttu-id="f9038-158">Vá para **Configurações de Segurança do Microsoft 365** Trabalhos de Avaliação de Pontos de Extremidade  >    >    >   (em 'Avaliações de rede').</span><span class="sxs-lookup"><span data-stu-id="f9038-158">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under 'Network assessments').</span></span>
    1. <span data-ttu-id="f9038-159">Na Central de Segurança do Microsoft Defender, acesse Configurações > Trabalhos de Avaliação.</span><span class="sxs-lookup"><span data-stu-id="f9038-159">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="f9038-160">Baixe o scanner de rede e instale-o no dispositivo de avaliação do Defender para Ponto de Extremidade designado.</span><span class="sxs-lookup"><span data-stu-id="f9038-160">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

![Botão Baixar scanner](images/assessment-jobs-download-scanner.png)

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="f9038-162">Instalação do scanner de rede & registro</span><span class="sxs-lookup"><span data-stu-id="f9038-162">Network scanner installation & registration</span></span>

<span data-ttu-id="f9038-163">O processo de entrada pode ser concluído no próprio dispositivo de avaliação designado ou em qualquer outro dispositivo (por exemplo, seu dispositivo cliente pessoal).</span><span class="sxs-lookup"><span data-stu-id="f9038-163">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="f9038-164">Para concluir o processo de registro do scanner de rede:</span><span class="sxs-lookup"><span data-stu-id="f9038-164">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="f9038-165">Copie e siga a URL que aparece na linha de comando e use o código de instalação fornecido para concluir o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="f9038-165">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>
    - <span data-ttu-id="f9038-166">Observação: talvez seja necessário alterar as configurações do Prompt de Comando para poder copiar a URL.</span><span class="sxs-lookup"><span data-stu-id="f9038-166">Note: You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="f9038-167">Insira o código e entre usando uma conta da Microsoft que tenha a permissão Defender para Ponto de Extremidade chamada "Gerenciar configurações de segurança no Centro de Segurança".</span><span class="sxs-lookup"><span data-stu-id="f9038-167">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="f9038-168">Quando terminar, você deverá ver uma mensagem confirmando que você se inscreveu.</span><span class="sxs-lookup"><span data-stu-id="f9038-168">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="f9038-169">Configurar um novo trabalho de avaliação</span><span class="sxs-lookup"><span data-stu-id="f9038-169">Configure a new assessment job</span></span>  

<span data-ttu-id="f9038-170">Na página Trabalhos de Avaliação em **Configurações,** selecione **Adicionar trabalho de avaliação de rede.**</span><span class="sxs-lookup"><span data-stu-id="f9038-170">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="f9038-171">Siga o processo de configuração para escolher dispositivos de rede a serem verificados regularmente e adicionados ao inventário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f9038-171">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="f9038-172">Para impedir a duplicação de dispositivos no inventário de dispositivos de rede, certifique-se de que cada endereço IP está configurado apenas uma vez em vários dispositivos de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f9038-172">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

![Adicionar botão de trabalho de avaliação de rede](images/assessment-jobs-add.png)

<span data-ttu-id="f9038-174">Adicionando etapas de trabalho de avaliação de rede:</span><span class="sxs-lookup"><span data-stu-id="f9038-174">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="f9038-175">Escolha um nome "Trabalho de Avaliação" e o "Dispositivo de Avaliação" no qual o scanner de rede foi instalado.</span><span class="sxs-lookup"><span data-stu-id="f9038-175">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="f9038-176">Este dispositivo executará as verificações autenticadas periódicas.</span><span class="sxs-lookup"><span data-stu-id="f9038-176">This device will perform the periodic authenticated scans.</span></span> 
2. <span data-ttu-id="f9038-177">Adicione endereços IP de dispositivos de rede de destino a serem verificados (ou as sub-redes onde esses dispositivos são implantados).</span><span class="sxs-lookup"><span data-stu-id="f9038-177">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 
3. <span data-ttu-id="f9038-178">Adicione credenciais SNMP necessárias dos dispositivos de rede de destino.</span><span class="sxs-lookup"><span data-stu-id="f9038-178">Add required SNMP credentials of the target network devices.</span></span> 
4. <span data-ttu-id="f9038-179">Salve o trabalho de avaliação de rede recém-configurado para iniciar a verificação periódica da rede.</span><span class="sxs-lookup"><span data-stu-id="f9038-179">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="f9038-180">Examinar e adicionar dispositivos de rede</span><span class="sxs-lookup"><span data-stu-id="f9038-180">Scan and add network devices</span></span>

<span data-ttu-id="f9038-181">Durante o processo de configuração, você pode executar uma verificação de teste de uma única vez para verificar se:</span><span class="sxs-lookup"><span data-stu-id="f9038-181">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="f9038-182">Há conectividade entre o dispositivo de avaliação do Defender for Endpoint e os dispositivos de rede de destino configurados.</span><span class="sxs-lookup"><span data-stu-id="f9038-182">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="f9038-183">As credenciais SNMP configuradas estão corretas.</span><span class="sxs-lookup"><span data-stu-id="f9038-183">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="f9038-184">Cada dispositivo de avaliação pode suportar até 1.500 endereços IP bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="f9038-184">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="f9038-185">Por exemplo, se você examinar 10 sub-redes diferentes em que apenas 100 endereços IP retornam resultados bem-sucedidos, você poderá verificar 1.400 endereços IP adicionais de outras sub-redes no mesmo dispositivo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f9038-185">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="f9038-186">Se houver vários intervalos de endereços IP/sub-redes a verificar, os resultados da verificação de teste levarão vários minutos para aparecer.</span><span class="sxs-lookup"><span data-stu-id="f9038-186">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="f9038-187">Uma verificação de teste estará disponível para até 1.024 endereços.</span><span class="sxs-lookup"><span data-stu-id="f9038-187">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="f9038-188">Depois que os resultados aparecerem, você poderá escolher quais dispositivos serão incluídos na verificação periódica.</span><span class="sxs-lookup"><span data-stu-id="f9038-188">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="f9038-189">Se você ignorar a exibição dos resultados da verificação, todos os endereços IP configurados serão adicionados ao trabalho de avaliação de rede (independentemente da resposta do dispositivo).</span><span class="sxs-lookup"><span data-stu-id="f9038-189">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="f9038-190">Os resultados da verificação também podem ser exportados.</span><span class="sxs-lookup"><span data-stu-id="f9038-190">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="f9038-191">Inventário de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f9038-191">Device inventory</span></span>

<span data-ttu-id="f9038-192">Os dispositivos recém-descobertos serão mostrados na nova guia **Dispositivos** de rede na página **Inventário de** dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f9038-192">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="f9038-193">Pode levar até duas horas após adicionar um trabalho de avaliação até que os dispositivos sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="f9038-193">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

![Seção Dispositivos de rede no inventário de dispositivos](images/assessment-jobs-device-inventory.png)

## <a name="troubleshooting"></a><span data-ttu-id="f9038-195">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="f9038-195">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="f9038-196">Falha na instalação do scanner de rede</span><span class="sxs-lookup"><span data-stu-id="f9038-196">Network scanner installation has failed</span></span>

<span data-ttu-id="f9038-197">Verifique se as URLs necessárias são adicionadas aos domínios permitidos em suas configurações de firewall.</span><span class="sxs-lookup"><span data-stu-id="f9038-197">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="f9038-198">Além disso, certifique-se de que as configurações de proxy estão configuradas conforme descrito em [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="f9038-198">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md)</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="f9038-199">A Microsoft.com/devicelogin da Web não foi a aparecer</span><span class="sxs-lookup"><span data-stu-id="f9038-199">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="f9038-200">Verifique se as URLs necessárias são adicionadas aos domínios permitidos no firewall.</span><span class="sxs-lookup"><span data-stu-id="f9038-200">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="f9038-201">Além disso, certifique-se de que as configurações de proxy estão configuradas conforme descrito em [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="f9038-201">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="f9038-202">Os dispositivos de rede não são mostrados no inventário de dispositivos após várias horas</span><span class="sxs-lookup"><span data-stu-id="f9038-202">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="f9038-203">Os resultados da verificação devem ser atualizados algumas horas após a verificação inicial que ocorreu após a conclusão da configuração do trabalho de avaliação.</span><span class="sxs-lookup"><span data-stu-id="f9038-203">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="f9038-204">Se os dispositivos ainda não são mostrados, verifique se o serviço 'MdatpNetworkScanService' está sendo executado em seus dispositivos de avaliação, nos quais você instalou o scanner de rede, e execute uma "Verificação de execução" na configuração de trabalho de avaliação relevante.</span><span class="sxs-lookup"><span data-stu-id="f9038-204">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="f9038-205">Se você ainda não receber resultados após 5 minutos, reinicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="f9038-205">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="f9038-206">O tempo visto pela última vez por dispositivos é maior do que 24 horas</span><span class="sxs-lookup"><span data-stu-id="f9038-206">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="f9038-207">Valide se o scanner está sendo executado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f9038-207">Validate that the scanner is running properly.</span></span> <span data-ttu-id="f9038-208">Em seguida, vá para a definição de verificação e selecione "Executar teste".</span><span class="sxs-lookup"><span data-stu-id="f9038-208">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="f9038-209">Verifique quais mensagens de erro estão retornando dos endereços IP relevantes.</span><span class="sxs-lookup"><span data-stu-id="f9038-209">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="f9038-210">Permissão de usuário de gerenciamento de vulnerabilidades e ameaças necessárias</span><span class="sxs-lookup"><span data-stu-id="f9038-210">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="f9038-211">O registro terminou com um erro: "Parece que você não tem permissões suficientes para adicionar um novo agente.</span><span class="sxs-lookup"><span data-stu-id="f9038-211">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="f9038-212">A permissão necessária é "Gerenciar configurações de segurança no Centro de Segurança".</span><span class="sxs-lookup"><span data-stu-id="f9038-212">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="f9038-213">Pressione qualquer tecla para sair.</span><span class="sxs-lookup"><span data-stu-id="f9038-213">Press any key to exit.</span></span>

<span data-ttu-id="f9038-214">Peça ao administrador do sistema para atribuir as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="f9038-214">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="f9038-215">Como alternativa, peça a outro membro relevante para ajudá-lo com o processo de login fornecendo a eles o código de login e o link.</span><span class="sxs-lookup"><span data-stu-id="f9038-215">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="f9038-216">Falha no processo de registro usando o link fornecido na linha de comando no processo de registro</span><span class="sxs-lookup"><span data-stu-id="f9038-216">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="f9038-217">Experimente um navegador diferente ou copie o link de entrada e o código para um dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="f9038-217">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="f9038-218">Texto muito pequeno ou não pode copiar texto da linha de comando</span><span class="sxs-lookup"><span data-stu-id="f9038-218">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="f9038-219">Altere as configurações da linha de comando em seu dispositivo para permitir copiar e alterar o tamanho do texto.</span><span class="sxs-lookup"><span data-stu-id="f9038-219">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f9038-220">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="f9038-220">Related articles</span></span>

- [<span data-ttu-id="f9038-221">Inventário de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f9038-221">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="f9038-222">Configurar recursos avançados</span><span class="sxs-lookup"><span data-stu-id="f9038-222">Configure advanced features</span></span>](advanced-features.md)
