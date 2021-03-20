---
title: Configurar as configurações de proxy e conexão com a Internet do dispositivo para ponto de extremidade DLP
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Saiba como configurar as configurações de proxy e conexão com a Internet do dispositivo para ponto de extremidade DLP.
ms.openlocfilehash: 3b8ebdbb08a6a866cc84df2031e77378925eaa0e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907001"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="7780a-103">Configurar as configurações de proxy e conexão com a Internet do dispositivo para ponto de extremidade DLP</span><span class="sxs-lookup"><span data-stu-id="7780a-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="7780a-104">O ponto de extremidade DLP da Microsoft usa o Microsoft Windows HTTP (WinHTTP) para relatar dados e se comunicar com o serviço em nuvem do ponto de extremidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7780a-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="7780a-105">O ponto de extremidade DLP integrado é executado no contexto do sistema usando a conta LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="7780a-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="7780a-106">Para organizações que usam proxies de envio como gateway para a Internet, você pode usar a proteção de rede para investigar por trás de um proxy.</span><span class="sxs-lookup"><span data-stu-id="7780a-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="7780a-107">Para saber mais, veja [Investigar eventos de conexão que ocorrem por meio de proxies de encaminhamento](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span><span class="sxs-lookup"><span data-stu-id="7780a-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="7780a-108">A definição da configuração do WinHTTP é independente das configurações de proxy de navegação da Internet do Windows (WinINet) e só pode descobrir um servidor proxy usando os seguintes métodos de descoberta automática:</span><span class="sxs-lookup"><span data-stu-id="7780a-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="7780a-109">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="7780a-109">Transparent proxy</span></span>
- <span data-ttu-id="7780a-110">Protocolo de Descoberta Automática de Proxy da Web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="7780a-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="7780a-111">Se estiver usando proxy transparente ou WPAD na topologia de rede, você não precisa de configurações especiais.</span><span class="sxs-lookup"><span data-stu-id="7780a-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="7780a-112">Para saber mais sobre o sobre o Defender para exclusões de URL do ponto de extremidade no proxy, veja [Habilitar acesso para URLs do serviço em nuvem do ponto de extremidade DLP no servidor proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="7780a-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="7780a-113">Configuração manual de proxy estático:</span><span class="sxs-lookup"><span data-stu-id="7780a-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="7780a-114">Configuração baseada no registro</span><span class="sxs-lookup"><span data-stu-id="7780a-114">Registry based configuration</span></span>
    - <span data-ttu-id="7780a-115">WinHTTP configurado usando o comando netsh - Adequado apenas para desktops em uma topologia estável (por exemplo: um desktop em uma rede corporativa atrás do mesmo proxy)</span><span class="sxs-lookup"><span data-stu-id="7780a-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="7780a-116">Configure o servidor proxy manualmente usando um proxy estático baseado no registro</span><span class="sxs-lookup"><span data-stu-id="7780a-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="7780a-117">Para dispositivos de ponto de extremidade sem permissão para se conectar à Internet, você precisa configurar um proxy estático baseado no registro.</span><span class="sxs-lookup"><span data-stu-id="7780a-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="7780a-118">Você precisa configurar isso para permitir que apenas o ponto de extremidade DLP da Microsoft relate dados de diagnóstico e se comunique com o serviço em nuvem do ponto de extremidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7780a-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="7780a-119">O proxy estático é configurável por meio da Política de Grupo (GP).</span><span class="sxs-lookup"><span data-stu-id="7780a-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="7780a-120">A política do grupo pode ser encontrada em:</span><span class="sxs-lookup"><span data-stu-id="7780a-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="7780a-121">Abra **Modelos Administrativos > Componentes do Windows > Coleta de Dados e Compilações de Visualização > Configurar o uso de proxy autenticado para a experiência do usuário conectado e serviço de telemetria**</span><span class="sxs-lookup"><span data-stu-id="7780a-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="7780a-122">Selecione para **Habilitado** e selecione **Desabilitar uso de proxy autenticado**:</span><span class="sxs-lookup"><span data-stu-id="7780a-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![Imagem das configurações da Política de Grupo 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="7780a-124">Abra **Modelos Administrativos > Componentes do Windows > Coleta de Dados e Compilações de Visualização > Configurar experiências de usuário conectado e telemetria**:</span><span class="sxs-lookup"><span data-stu-id="7780a-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="7780a-125">Configurar o proxy</span><span class="sxs-lookup"><span data-stu-id="7780a-125">Configure the proxy</span></span>

![Imagem das configurações da Política de Grupo 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="7780a-127">A política define dois valores de registro `TelemetryProxyServer` como REG_SZ e `DisableEnterpriseAuthProxy` como REG_DWORD na chave de registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="7780a-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="7780a-128">O valor de registro TelemetryProxyServer está neste formato \<server name or ip\>:\<port\>.</span><span class="sxs-lookup"><span data-stu-id="7780a-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="7780a-129">Por exemplo: **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="7780a-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="7780a-130">O valor de registro `DisableEnterpriseAuthProxy` deve ser definido como 1.</span><span class="sxs-lookup"><span data-stu-id="7780a-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="7780a-131">Configure o servidor proxy manualmente usando o comando "netsh"</span><span class="sxs-lookup"><span data-stu-id="7780a-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="7780a-132">Use netsh para configurar um proxy estático de todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="7780a-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="7780a-133">Isso afetará todos os aplicativos, incluindo serviços do Windows que usam WinHTTP com proxy padrão.</span><span class="sxs-lookup"><span data-stu-id="7780a-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="7780a-134">- Laptops que estão mudando de topologia (por exemplo: do escritório para casa) terão mau funcionamento com o netsh.</span><span class="sxs-lookup"><span data-stu-id="7780a-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="7780a-135">Use a configuração de proxy estático com base no registro.</span><span class="sxs-lookup"><span data-stu-id="7780a-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="7780a-136">Abra uma linha de comando com privilégios elevados:</span><span class="sxs-lookup"><span data-stu-id="7780a-136">Open an elevated command-line:</span></span>
    1. <span data-ttu-id="7780a-137">Vá para **Iniciar** e digite **cmd**</span><span class="sxs-lookup"><span data-stu-id="7780a-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="7780a-138">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="7780a-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="7780a-139">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="7780a-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="7780a-140">Por exemplo: **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="7780a-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="7780a-141">Para redefinir o proxy winhttp, insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="7780a-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="7780a-142">Para saber mais, veja [Sintaxe, Contextos e Formatação do Comando Netsh](/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="7780a-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="7780a-143">Habilitar acesso para URLs do serviço em nuvem do ponto de extremidade DLP no servidor proxy</span><span class="sxs-lookup"><span data-stu-id="7780a-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="7780a-144">Se um proxy ou firewall está bloqueando por padrão todo o tráfego e permitindo apenas a passagem de domínios específicos, adicione os domínios listados na planilha para download à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="7780a-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="7780a-145">Esta [planilha para download](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/security/threat-protection/microsoft-defender-atp/downloads/mdatp-urls.xlsx) lista os serviços e os seus URLs associados que a sua rede deve ser capaz de se conectar.</span><span class="sxs-lookup"><span data-stu-id="7780a-145">This [downloadable spreadsheet](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/security/threat-protection/microsoft-defender-atp/downloads/mdatp-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="7780a-146">Você deve garantir que não hajam regras de firewall ou de filtragem de rede que neguem o acesso a esses URLs, ou pode ser necessário criar uma regra de permissão especificamente para eles.</span><span class="sxs-lookup"><span data-stu-id="7780a-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="7780a-147">Se um proxy ou firewall tiver verificação HTTPS habilitada (inspeção SSL), exclua os domínios listados na tabela acima da verificação HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7780a-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="7780a-148">Se um proxy ou firewall estiver bloqueando o tráfego anônimo, como o ponto de extremidade DLP está se conectando a partir do contexto do sistema, certifique-se de que o tráfego anônimo seja permitido nos URLs listados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7780a-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="7780a-149">Verifique a conectividade do cliente com os URLs do serviço de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7780a-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="7780a-150">Verifique se a configuração do proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para os URLs do serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="7780a-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="7780a-151">Baixe a [ferramenta MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) para o PC onde o ponto de extremidade DLP está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="7780a-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="7780a-152">Extraia o conteúdo de MDATPClientAnalyzer.zip no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7780a-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="7780a-153">Abra uma linha de comando com privilégios elevados:</span><span class="sxs-lookup"><span data-stu-id="7780a-153">Open an elevated command-line:</span></span>
    1. <span data-ttu-id="7780a-154">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="7780a-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="7780a-155">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="7780a-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="7780a-156">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="7780a-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="7780a-157">Substitua *HardDrivePath* pelo caminho para onde a ferramenta MDATPClientAnalyzer foi baixada, por exemplo</span><span class="sxs-lookup"><span data-stu-id="7780a-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="7780a-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="7780a-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="7780a-159">Extraia o **MDATPClientAnalyzerResult.zip** _ criado pela ferramenta na pasta usada no _HardDrivePath \*.</span><span class="sxs-lookup"><span data-stu-id="7780a-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="7780a-160">Abra **MDATPClientAnalyzerResult.txt** e verifique se você executou as etapas de configuração do proxy para permitir a descoberta do servidor e o acesso às URLs de serviço.</span><span class="sxs-lookup"><span data-stu-id="7780a-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="7780a-161">A ferramenta verifica a conectividade dos URLs do serviço Defender para Ponto de Extremidade com os quais o Defender para ponto de extremidade do cliente está configurado para interagir.</span><span class="sxs-lookup"><span data-stu-id="7780a-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="7780a-162">Em seguida, ele imprime os resultados no arquivo **MDATPClientAnalyzerResult.txt** para cada URL que pode ser potencialmente usado para se comunicar com os serviços do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="7780a-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="7780a-163">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7780a-163">For example:</span></span>

    <span data-ttu-id="7780a-164">**Testing URL : https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command line proxy: Doesn't exist**</span><span class="sxs-lookup"><span data-stu-id="7780a-164">**Testing URL : https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="7780a-165">Se pelo menos uma das opções de conectividade retornar um status (200), então o Defender para ponto de extremidade do cliente pode se comunicar corretamente com o URL testado usando este método de conectividade.</span><span class="sxs-lookup"><span data-stu-id="7780a-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="7780a-166">No entanto, se os resultados da verificação de conectividade indicarem uma falha, um erro HTTP será exibido (consulte Códigos de status HTTP).</span><span class="sxs-lookup"><span data-stu-id="7780a-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="7780a-167">Você pode então usar os URLs na tabela mostrada em[Habilitar acesso para URLs do serviço em nuvem do ponto de extremidade DLP no servidor proxy](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="7780a-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="7780a-168">Os URLs que você usará dependerão da região selecionada durante o procedimento de integração.</span><span class="sxs-lookup"><span data-stu-id="7780a-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="7780a-169"> A ferramenta Connectivity Analyzer não é compatível com a regra ASR [Bloqueie as criações de processos originadas de comandos PSExec e WMI](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="7780a-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="7780a-170">Você precisará desativar temporariamente esta regra para executar a ferramenta de conectividade.</span><span class="sxs-lookup"><span data-stu-id="7780a-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="7780a-171">Quando o TelemetryProxyServer é definido, no Registro ou via Política de Grupo, o Defender para Ponto de Extremidade voltará a ser direto se não puder acessar o proxy definido.</span><span class="sxs-lookup"><span data-stu-id="7780a-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="7780a-172">Tópicos relacionados •   Dispositivos Windows 10 integrados •   Solucionar problemas de integração do  de extremidade DLP da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7780a-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="7780a-173">Confira também</span><span class="sxs-lookup"><span data-stu-id="7780a-173">See also</span></span>

- [<span data-ttu-id="7780a-174">Saiba mais sobre a Prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7780a-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="7780a-175">Usando a prevenção contra perda de dados do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="7780a-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="7780a-176">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="7780a-176">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="7780a-177">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="7780a-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="7780a-178">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="7780a-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="7780a-179">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7780a-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="7780a-180">Ferramentas e métodos de integração para computadores Windows 10</span><span class="sxs-lookup"><span data-stu-id="7780a-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="7780a-181">Assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7780a-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="7780a-182">Dispositivos associados ao Microsoft Azure AD</span><span class="sxs-lookup"><span data-stu-id="7780a-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="7780a-183">Baixar o novo Microsoft Edge baseado em Chromium</span><span class="sxs-lookup"><span data-stu-id="7780a-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)