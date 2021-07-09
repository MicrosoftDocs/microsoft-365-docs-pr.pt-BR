---
title: Configurar configurações de proxy de dispositivo e conexão com a Internet
description: Configure as configurações de proxy e internet do Microsoft Defender para Endpoint para habilitar a comunicação com o serviço de nuvem.
keywords: configurar, proxy, internet, conectividade com a Internet, configurações, configurações de proxy, netsh, winhttp, servidor proxy
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6a3bbc46bb5859743d5170451b0d1c68793f93bf
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338704"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="4abd8-104">Definir as configurações de proxy de dispositivo e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="4abd8-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4abd8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4abd8-105">**Applies to:**</span></span>
- [<span data-ttu-id="4abd8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4abd8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4abd8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4abd8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4abd8-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4abd8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4abd8-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4abd8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="4abd8-110">O sensor Defender para Ponto de Extremidade requer que a Microsoft Windows HTTP (WinHTTP) para relatar dados do sensor e se comunicar com o serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4abd8-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="4abd8-111">O sensor Defender para Ponto de Extremidade incorporado é executado no contexto do sistema usando a conta LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="4abd8-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="4abd8-112">O sensor usa o Microsoft Windows HTTP Services (WinHTTP) para habilitar a comunicação com o serviço de nuvem do Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="4abd8-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

> [!TIP]
> <span data-ttu-id="4abd8-113">Para organizações que usam proxies de envio como gateway para a Internet, você pode usar a proteção de rede para investigar por trás de um proxy.</span><span class="sxs-lookup"><span data-stu-id="4abd8-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="4abd8-114">Para saber mais, veja [Investigar eventos de conexão que ocorrem por meio de proxies de encaminhamento](investigate-behind-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="4abd8-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="4abd8-115">A configuração winhttp é independente das configurações de proxy de navegação na Internet (WinINet) Windows internet e só pode descobrir um servidor proxy usando os seguintes métodos de descoberta:</span><span class="sxs-lookup"><span data-stu-id="4abd8-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="4abd8-116">Métodos de descoberta automática:</span><span class="sxs-lookup"><span data-stu-id="4abd8-116">Auto-discovery methods:</span></span>

  - <span data-ttu-id="4abd8-117">Proxy transparente</span><span class="sxs-lookup"><span data-stu-id="4abd8-117">Transparent proxy</span></span>

  - <span data-ttu-id="4abd8-118">Protocolo de Descoberta Automática de Proxy da Web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="4abd8-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="4abd8-119">Se você estiver usando proxy transparente ou WPAD em sua topologia de rede, não precisará de configurações especiais.</span><span class="sxs-lookup"><span data-stu-id="4abd8-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="4abd8-120">Para obter mais informações sobre exclusões de URL do Defender para Ponto de Extremidade no proxy, consulte Enable access [to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="4abd8-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="4abd8-121">Configuração manual de proxy estático:</span><span class="sxs-lookup"><span data-stu-id="4abd8-121">Manual static proxy configuration:</span></span>

  - <span data-ttu-id="4abd8-122">Configuração baseada no registro</span><span class="sxs-lookup"><span data-stu-id="4abd8-122">Registry based configuration</span></span>

  - <span data-ttu-id="4abd8-123">WinHTTP configurado usando o comando netsh - Adequado apenas para desktops em uma topologia estável (por exemplo: um desktop em uma rede corporativa atrás do mesmo proxy)</span><span class="sxs-lookup"><span data-stu-id="4abd8-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="4abd8-124">Configure o servidor proxy manualmente usando um proxy estático baseado no registro</span><span class="sxs-lookup"><span data-stu-id="4abd8-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="4abd8-125">Configure um proxy estático baseado no Registro para permitir que apenas o sensor Defender for Endpoint reporte dados de diagnóstico e se comunique com o Defender para serviços de Ponto de Extremidade se um computador não tiver permissão para se conectar à Internet.</span><span class="sxs-lookup"><span data-stu-id="4abd8-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not permitted to connect to the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="4abd8-126">Ao usar essa opção no Windows 10 ou Windows Server 2019, é recomendável ter a seguinte com build (ou posterior) e acúmulo cumulativo de atualizações:</span><span class="sxs-lookup"><span data-stu-id="4abd8-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span>
>
> - <span data-ttu-id="4abd8-127">Windows 10, versão 1809 ou Windows Server 2019 -https://support.microsoft.com/kb/5001384</span><span class="sxs-lookup"><span data-stu-id="4abd8-127">Windows 10, version 1809 or Windows Server 2019 - https://support.microsoft.com/kb/5001384</span></span>
> - <span data-ttu-id="4abd8-128">Windows 10, versão 1909 -https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="4abd8-128">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span>
> - <span data-ttu-id="4abd8-129">Windows 10, versão 2004 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="4abd8-129">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span>
> - <span data-ttu-id="4abd8-130">Windows 10, versão 20H2 -https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="4abd8-130">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span>
>
> <span data-ttu-id="4abd8-131">Essas atualizações melhoram a conectividade e a confiabilidade do canal CnC (Comando e Controle).</span><span class="sxs-lookup"><span data-stu-id="4abd8-131">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span>

<span data-ttu-id="4abd8-132">O proxy estático é configurável por meio da Política de Grupo (GP).</span><span class="sxs-lookup"><span data-stu-id="4abd8-132">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="4abd8-133">A política do grupo pode ser encontrada em:</span><span class="sxs-lookup"><span data-stu-id="4abd8-133">The group policy can be found under:</span></span>

- <span data-ttu-id="4abd8-134">**Modelos Administrativos > Windows componentes > de dados e builds de visualização > configurar o uso de Proxy Autenticado para o Serviço de Telemetria e Experiência do Usuário Conectado**</span><span class="sxs-lookup"><span data-stu-id="4abd8-134">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

  <span data-ttu-id="4abd8-135">De defini-lo **como Habilitado e** selecione **Desabilitar o uso de Proxy Autenticado.**</span><span class="sxs-lookup"><span data-stu-id="4abd8-135">Set it to **Enabled** and select **Disable Authenticated Proxy usage**.</span></span>

  ![Imagem da configuração da Política de Grupo1](images/atp-gpo-proxy1.png)

- <span data-ttu-id="4abd8-137">**Modelos Administrativos > Windows componentes >** de dados e builds de visualização > Configurar experiências de usuário conectados e telemetria :</span><span class="sxs-lookup"><span data-stu-id="4abd8-137">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

  <span data-ttu-id="4abd8-138">Configurar o proxy</span><span class="sxs-lookup"><span data-stu-id="4abd8-138">Configure the proxy</span></span>

  ![Imagem da configuração da Política de Grupo2](images/atp-gpo-proxy2.png)

  <span data-ttu-id="4abd8-140">A política define dois valores do Registro, como REG_SZ e como `TelemetryProxyServer` `DisableEnterpriseAuthProxy` REG_DWORD, sob a chave do Registro `HKLM\Software\Policies\Microsoft\Windows\DataCollection` .</span><span class="sxs-lookup"><span data-stu-id="4abd8-140">The policy sets two registry values, `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD, under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

  <span data-ttu-id="4abd8-141">O valor do Registro `TelemetryProxyServer` assume o seguinte formato de cadeia de caracteres:</span><span class="sxs-lookup"><span data-stu-id="4abd8-141">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

  ```text
  <server name or ip>:<port>
  ```

  <span data-ttu-id="4abd8-142">Por exemplo: 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="4abd8-142">For example: 10.0.0.6:8080</span></span>

  <span data-ttu-id="4abd8-143">O valor de registro `DisableEnterpriseAuthProxy` deve ser definido como 1.</span><span class="sxs-lookup"><span data-stu-id="4abd8-143">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="4abd8-144">Configurar o servidor proxy manualmente usando o comando netsh</span><span class="sxs-lookup"><span data-stu-id="4abd8-144">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="4abd8-145">Use netsh para configurar um proxy estático de todo o sistema.</span><span class="sxs-lookup"><span data-stu-id="4abd8-145">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="4abd8-146">Isso afetará todos os aplicativos, incluindo serviços do Windows que usam WinHTTP com proxy padrão.</span><span class="sxs-lookup"><span data-stu-id="4abd8-146">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="4abd8-147">Laptops que estão alterando a topologia (por exemplo: do office para o home) não funcionarão com netsh.</span><span class="sxs-lookup"><span data-stu-id="4abd8-147">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="4abd8-148">Use a configuração de proxy estático com base no registro.</span><span class="sxs-lookup"><span data-stu-id="4abd8-148">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="4abd8-149">Abra uma linha de comando com privilégios elevados:</span><span class="sxs-lookup"><span data-stu-id="4abd8-149">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="4abd8-150">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="4abd8-150">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="4abd8-151">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4abd8-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="4abd8-152">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="4abd8-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="4abd8-153">Por exemplo: `netsh winhttp set proxy 10.0.0.6:8080`</span><span class="sxs-lookup"><span data-stu-id="4abd8-153">For example: `netsh winhttp set proxy 10.0.0.6:8080`</span></span>

<span data-ttu-id="4abd8-154">Para redefinir o proxy winhttp, insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="4abd8-154">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="4abd8-155">Para saber mais, veja [Sintaxe, Contextos e Formatação do Comando Netsh](/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="4abd8-155">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="4abd8-156">Habilitar o acesso a URLs de serviço do Microsoft Defender para Ponto de Extremidade no servidor proxy</span><span class="sxs-lookup"><span data-stu-id="4abd8-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="4abd8-157">Se um proxy ou firewall está bloqueando por padrão todo o tráfego e permitindo apenas a passagem de domínios específicos, adicione os domínios listados na planilha para download à lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="4abd8-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="4abd8-158">A planilha baixável a seguir lista os serviços e as URLs associadas às quais sua rede deve ser capaz de se conectar.</span><span class="sxs-lookup"><span data-stu-id="4abd8-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="4abd8-159">Você deve garantir que não haja regras de filtragem de rede ou firewall que neguem o acesso *a* essas URLs, ou talvez seja necessário criar uma regra de autorização especificamente para elas.</span><span class="sxs-lookup"><span data-stu-id="4abd8-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="4abd8-160">Planilha de lista de domínios</span><span class="sxs-lookup"><span data-stu-id="4abd8-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="4abd8-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="4abd8-161">Description</span></span> |
|:-----|:-----|
|![Imagem em miniatura da planilha URLs do Microsoft Defender para Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="4abd8-163">Planilha de registros DNS específicos para locais de serviço, localizações geográficas e sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4abd8-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="4abd8-164">Baixe a planilha aqui.</span><span class="sxs-lookup"><span data-stu-id="4abd8-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

<span data-ttu-id="4abd8-165">Se um proxy ou firewall tiver verificação HTTPS habilitada (inspeção SSL), exclua os domínios listados na tabela acima da verificação HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4abd8-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="4abd8-166">settings-win.data.microsoft.com só será necessário se você tiver Windows 10 dispositivos executando a versão 1803 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="4abd8-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>
>
> <span data-ttu-id="4abd8-167">URLs que incluem v20 neles são necessárias apenas se você tiver Windows 10 que executam a versão 1803 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4abd8-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="4abd8-168">Por exemplo, é necessário para um dispositivo Windows 10 que executa a versão 1803 ou posterior e está conectado à região `us-v20.events.data.microsoft.com` Armazenamento dados dos EUA.</span><span class="sxs-lookup"><span data-stu-id="4abd8-168">For example, `us-v20.events.data.microsoft.com` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>
>
> <span data-ttu-id="4abd8-169">Se você estiver usando Microsoft Defender Antivírus em seu ambiente, consulte [Configure network connections to the Microsoft Defender Antivírus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="4abd8-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="4abd8-170">Se um proxy ou firewall estiver bloqueando o tráfego anônimo, como o sensor Defender for Endpoint está se conectando do contexto do sistema, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4abd8-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="4abd8-171">Microsoft Monitoring Agent (MMA) - requisitos de proxy e firewall para versões mais antigas do cliente Windows ou Windows Server</span><span class="sxs-lookup"><span data-stu-id="4abd8-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="4abd8-172">As informações a seguir listam as informações de configuração de proxy e firewall necessárias para se comunicar com o agente do Log Analytics (geralmente chamado de Microsoft Monitoring Agent) para as versões anteriores do Windows, como Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="4abd8-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="4abd8-173">Recursos do agente</span><span class="sxs-lookup"><span data-stu-id="4abd8-173">Agent Resource</span></span>|<span data-ttu-id="4abd8-174">Portas</span><span class="sxs-lookup"><span data-stu-id="4abd8-174">Ports</span></span> |<span data-ttu-id="4abd8-175">Direção</span><span class="sxs-lookup"><span data-stu-id="4abd8-175">Direction</span></span> |<span data-ttu-id="4abd8-176">Evitar inspeção HTTPS</span><span class="sxs-lookup"><span data-stu-id="4abd8-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|
|<span data-ttu-id="4abd8-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="4abd8-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="4abd8-178">Porta 443</span><span class="sxs-lookup"><span data-stu-id="4abd8-178">Port 443</span></span> |<span data-ttu-id="4abd8-179">Saída</span><span class="sxs-lookup"><span data-stu-id="4abd8-179">Outbound</span></span>|<span data-ttu-id="4abd8-180">Sim</span><span class="sxs-lookup"><span data-stu-id="4abd8-180">Yes</span></span> |  
|<span data-ttu-id="4abd8-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="4abd8-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="4abd8-182">Porta 443</span><span class="sxs-lookup"><span data-stu-id="4abd8-182">Port 443</span></span> |<span data-ttu-id="4abd8-183">Saída</span><span class="sxs-lookup"><span data-stu-id="4abd8-183">Outbound</span></span>|<span data-ttu-id="4abd8-184">Sim</span><span class="sxs-lookup"><span data-stu-id="4abd8-184">Yes</span></span> |  
|<span data-ttu-id="4abd8-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="4abd8-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="4abd8-186">Porta 443</span><span class="sxs-lookup"><span data-stu-id="4abd8-186">Port 443</span></span> |<span data-ttu-id="4abd8-187">Saída</span><span class="sxs-lookup"><span data-stu-id="4abd8-187">Outbound</span></span>|<span data-ttu-id="4abd8-188">Sim</span><span class="sxs-lookup"><span data-stu-id="4abd8-188">Yes</span></span> |
|<span data-ttu-id="4abd8-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="4abd8-189">\*.azure-automation.net</span></span> |<span data-ttu-id="4abd8-190">Porta 443</span><span class="sxs-lookup"><span data-stu-id="4abd8-190">Port 443</span></span> |<span data-ttu-id="4abd8-191">Saída</span><span class="sxs-lookup"><span data-stu-id="4abd8-191">Outbound</span></span>|<span data-ttu-id="4abd8-192">Sim</span><span class="sxs-lookup"><span data-stu-id="4abd8-192">Yes</span></span> |  

> [!NOTE]
> <span data-ttu-id="4abd8-193">Como uma solução baseada em nuvem, o intervalo ip pode mudar.</span><span class="sxs-lookup"><span data-stu-id="4abd8-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="4abd8-194">É recomendável mover para a configuração de resolução de DNS.</span><span class="sxs-lookup"><span data-stu-id="4abd8-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="4abd8-195">Confirmar Microsoft Monitoring Agent de URL de serviço (MMA)</span><span class="sxs-lookup"><span data-stu-id="4abd8-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="4abd8-196">Consulte as seguintes diretrizes para eliminar o requisito curinga (\*) para seu ambiente específico ao usar o Microsoft Monitoring Agent (MMA) para versões anteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="4abd8-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1. <span data-ttu-id="4abd8-197">Integração de um sistema operacional anterior com o Microsoft Monitoring Agent (MMA) no Defender for Endpoint (para obter mais informações, consulte Onboard previous [versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and Onboard Windows [servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span><span class="sxs-lookup"><span data-stu-id="4abd8-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2. <span data-ttu-id="4abd8-198">Verifique se o computador está relatando com êxito no portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4abd8-198">Ensure the machine is successfully reporting into the Microsoft 365 Defender portal.</span></span>

3. <span data-ttu-id="4abd8-199">Execute a TestCloudConnection.exe de "C:\Program Files\Microsoft Monitoring Agent\Agent" para validar a conectividade e ver as URLs necessárias para seu espaço de trabalho específico.</span><span class="sxs-lookup"><span data-stu-id="4abd8-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4. <span data-ttu-id="4abd8-200">Verifique a lista URLs do Microsoft Defender para Pontos de Extremidade para a lista completa de requisitos para sua região (consulte a Planilha urls de [serviço](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span><span class="sxs-lookup"><span data-stu-id="4abd8-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

    ![Imagem do administrador no Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="4abd8-202">Os curingas ( ) usados em pontos de extremidade \* .ods.opinsights.azure.com, .oms.opinsights.azure.com e .agentsvc.azure-automation.net URL podem ser substituídos por sua ID de Espaço de \* \* Trabalho \* específica.</span><span class="sxs-lookup"><span data-stu-id="4abd8-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="4abd8-203">A ID do Espaço de Trabalho é específica para seu ambiente e espaço de trabalho e pode ser encontrada na seção Integração do seu locatário no portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4abd8-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft 365 Defender portal.</span></span>

<span data-ttu-id="4abd8-204">O ponto de extremidade .blob.core.windows.net URL pode ser substituído com as URLs mostradas na seção "Regra de \* Firewall: .blob.core.windows.net" dos resultados \* do teste.</span><span class="sxs-lookup"><span data-stu-id="4abd8-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the "Firewall Rule: \*.blob.core.windows.net" section of the test results.</span></span>

> [!NOTE]
> <span data-ttu-id="4abd8-205">No caso de integração por meio do Azure Defender, vários espaços de trabalho talvez usados.</span><span class="sxs-lookup"><span data-stu-id="4abd8-205">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="4abd8-206">Você precisará executar o procedimento TestCloudConnection.exe acima em uma máquina interna de cada espaço de trabalho (para determinar se há alterações nas URLs \*.blob.core.windows.net entre os espaços de trabalho).</span><span class="sxs-lookup"><span data-stu-id="4abd8-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="4abd8-207">Verificar a conectividade do cliente com o Microsoft Defender para URLs de serviço de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="4abd8-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="4abd8-208">Verifique se a configuração do proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para os URLs do serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4abd8-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="4abd8-209">Baixe a [ferramenta Analisador de Cliente MDATP](https://aka.ms/mdatpanalyzer) para o computador no qual o sensor defender for Endpoint está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="4abd8-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="4abd8-210">Extraia o conteúdo de MDATPClientAnalyzer.zip no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4abd8-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="4abd8-211">Abra uma linha de comando com privilégios elevados:</span><span class="sxs-lookup"><span data-stu-id="4abd8-211">Open an elevated command-line:</span></span>

   1. <span data-ttu-id="4abd8-212">Vá para **Iniciar** e digite **cmd**.</span><span class="sxs-lookup"><span data-stu-id="4abd8-212">Go to **Start** and type **cmd**.</span></span>

   1. <span data-ttu-id="4abd8-213">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="4abd8-213">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="4abd8-214">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="4abd8-214">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="4abd8-215">Substitua *HardDrivePath* pelo caminho para o qual a ferramenta MDATPClientAnalyzer foi baixada, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4abd8-215">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example:</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="4abd8-216">Extraia *oMDATPClientAnalyzerResult.zip* criado pela ferramenta na pasta usada no *HardDrivePath*.</span><span class="sxs-lookup"><span data-stu-id="4abd8-216">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="4abd8-217">Abra *MDATPClientAnalyzerResult.txt* e verifique se você executou as etapas de configuração do proxy para permitir a descoberta do servidor e o acesso às URLs de serviço.</span><span class="sxs-lookup"><span data-stu-id="4abd8-217">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>

   <span data-ttu-id="4abd8-218">A ferramenta verifica a conectividade dos URLs do serviço Defender para Ponto de Extremidade com os quais o Defender para ponto de extremidade do cliente está configurado para interagir.</span><span class="sxs-lookup"><span data-stu-id="4abd8-218">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="4abd8-219">Em seguida, ele imprime os resultados no arquivo *MDATPClientAnalyzerResult.txt* para cada URL que pode ser potencialmente usado para se comunicar com os serviços do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4abd8-219">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="4abd8-220">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4abd8-220">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="4abd8-221">Se pelo menos uma das opções de conectividade retornar um status (200), então o Defender para ponto de extremidade do cliente pode se comunicar corretamente com o URL testado usando este método de conectividade.</span><span class="sxs-lookup"><span data-stu-id="4abd8-221">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span>

<span data-ttu-id="4abd8-222">No entanto, se os resultados da verificação de conectividade indicarem uma falha, um erro HTTP será exibido (consulte Códigos de status HTTP).</span><span class="sxs-lookup"><span data-stu-id="4abd8-222">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="4abd8-223">Em seguida, você pode usar as URLs na tabela mostrada em Habilitar o acesso a [URLs](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)de serviço do Defender para Ponto de Extremidade no servidor proxy .</span><span class="sxs-lookup"><span data-stu-id="4abd8-223">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="4abd8-224">As URLs que você usará dependerão da região selecionada durante o procedimento de integração.</span><span class="sxs-lookup"><span data-stu-id="4abd8-224">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="4abd8-225">A ferramenta Connectivity Analyzer não é compatível com a regra ASR [Bloqueie as criações de processos originadas de comandos PSExec e WMI](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="4abd8-225">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="4abd8-226">Você precisará desativar temporariamente esta regra para executar a ferramenta de conectividade.</span><span class="sxs-lookup"><span data-stu-id="4abd8-226">You will need to temporarily disable this rule to run the connectivity tool.</span></span>
>
> <span data-ttu-id="4abd8-227">Quando o TelemetryProxyServer for definido, no Registro ou por meio da Política de Grupo, o Defender para Ponto de Extremidade retornará ao direto se não puder acessar o proxy definido.</span><span class="sxs-lookup"><span data-stu-id="4abd8-227">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4abd8-228">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4abd8-228">Related topics</span></span>

- [<span data-ttu-id="4abd8-229">Dispositivos integrados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="4abd8-229">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="4abd8-230">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="4abd8-230">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
