---
title: Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no macOS
description: Este tópico descreve como solucionar problemas de conectividade de nuvem para o Microsoft Defender para Ponto de Extremidade no macOS
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 291cd3016dcb4e1a321f39b4d2731ce2068b6544
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935204"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="7f5a6-104">Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="7f5a6-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7f5a6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7f5a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="7f5a6-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7f5a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7f5a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f5a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="7f5a6-108">**Plataforma** macOS</span><span class="sxs-lookup"><span data-stu-id="7f5a6-108">**Platform** macOS</span></span>

<span data-ttu-id="7f5a6-109">Este tópico descreve como solucionar problemas de conectividade de nuvem para o Microsoft Defender para Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="7f5a6-110">Executar o teste de conectividade</span><span class="sxs-lookup"><span data-stu-id="7f5a6-110">Run the connectivity test</span></span>
<span data-ttu-id="7f5a6-111">Para testar se o Defender para Ponto de Extremidade no Mac pode se comunicar com a nuvem com as configurações de rede atuais, execute um teste de conectividade da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="7f5a6-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="7f5a6-112">saída esperada:</span><span class="sxs-lookup"><span data-stu-id="7f5a6-112">expected output:</span></span>
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="7f5a6-113">Se o teste de conectividade falhar, verifique se o dispositivo tem acesso à Internet e se algum dos pontos de extremidade exigidos pelo produto são [bloqueados](microsoft-defender-endpoint-mac.md#network-connections) por um proxy ou firewall.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="7f5a6-114">Falhas com o erro de curvamento 35 ou 60 indicam rejeição de pinamento de certificado, o que indica um possível problema com a inspeção SSL ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="7f5a6-115">Consulte instruções abaixo sobre a configuração de inspeção SSL.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="7f5a6-116">Etapas de solução de problemas para ambientes sem proxy ou com PAC (Configuração Automática de Proxy) ou com o Protocolo de Descoberta Automática de Proxy da Web (WPAD)</span><span class="sxs-lookup"><span data-stu-id="7f5a6-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="7f5a6-117">Use o procedimento a seguir para testar se uma conexão não está bloqueada em um ambiente sem um proxy ou com PAC (Autoconfig de Proxy) ou com o Protocolo de Descoberta Automática de Proxy da Web (WPAD).</span><span class="sxs-lookup"><span data-stu-id="7f5a6-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="7f5a6-118">Se um proxy ou firewall estiver bloqueando o tráfego anônimo, certifique-se de que o tráfego anônimo seja permitido nas URLs listadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="7f5a6-119">Proxies autenticados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="7f5a6-120">Verifique se apenas PAC, WPAD ou um proxy estático estão sendo usados.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="7f5a6-121">Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="7f5a6-122">Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Microsoft Defender para o Ponto de Extremidade no macOS para as URLs relevantes sem interceptação.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="7f5a6-123">Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.</span><span class="sxs-lookup"><span data-stu-id="7f5a6-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="7f5a6-124">Para testar se uma conexão não está bloqueada: em um navegador como o Microsoft Edge para Mac ou Safari aberto https://x.cp.wd.microsoft.com/api/report e https://cdn.x.cp.wd.microsoft.com/ping .</span><span class="sxs-lookup"><span data-stu-id="7f5a6-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="7f5a6-125">Opcionalmente, no Terminal, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7f5a6-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="7f5a6-126">A saída deste comando deve ser semelhante a:</span><span class="sxs-lookup"><span data-stu-id="7f5a6-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
