---
title: Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no Linux
ms.reviewer: ''
description: Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no Linux
keywords: microsoft, defender, Microsoft Defender para Endpoint, linux, nuvem, conectividade, comunicação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933104"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="2b961-104">Solucionar problemas de conectividade na nuvem para o Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="2b961-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2b961-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2b961-105">**Applies to:**</span></span>
- [<span data-ttu-id="2b961-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2b961-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2b961-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b961-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2b961-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2b961-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2b961-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2b961-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="2b961-110">Executar o teste de conectividade</span><span class="sxs-lookup"><span data-stu-id="2b961-110">Run the connectivity test</span></span>

<span data-ttu-id="2b961-111">Para testar se o Defender para Ponto de Extremidade no Linux pode se comunicar com a nuvem com as configurações de rede atuais, execute um teste de conectividade da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="2b961-111">To test if Defender for Endpoint on Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="2b961-112">saída esperada:</span><span class="sxs-lookup"><span data-stu-id="2b961-112">expected output:</span></span>

```output
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

<span data-ttu-id="2b961-113">Se o teste de conectividade falhar, verifique se o dispositivo tem acesso à Internet e se algum dos pontos de extremidade exigidos pelo produto são [bloqueados](microsoft-defender-endpoint-linux.md#network-connections) por um proxy ou firewall.</span><span class="sxs-lookup"><span data-stu-id="2b961-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="2b961-114">Falhas com erro de curvaagem 35 ou 60 indicam rejeição de pinamento de certificado.</span><span class="sxs-lookup"><span data-stu-id="2b961-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="2b961-115">Verifique se a conexão está em inspeção SSL ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2b961-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="2b961-116">Em caso afirmado, adicione o Microsoft Defender para Ponto de Extremidade à lista de permitir.</span><span class="sxs-lookup"><span data-stu-id="2b961-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="2b961-117">Etapas de solução de problemas para ambientes sem proxy ou com proxy transparente</span><span class="sxs-lookup"><span data-stu-id="2b961-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="2b961-118">Para testar se uma conexão não está bloqueada em um ambiente sem um proxy ou com um proxy transparente, execute o seguinte comando no terminal:</span><span class="sxs-lookup"><span data-stu-id="2b961-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="2b961-119">A saída deste comando deve ser semelhante a:</span><span class="sxs-lookup"><span data-stu-id="2b961-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="2b961-120">Etapas de solução de problemas para ambientes com proxy estático</span><span class="sxs-lookup"><span data-stu-id="2b961-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="2b961-121">Pac, WPAD e proxies autenticados não são suportados.</span><span class="sxs-lookup"><span data-stu-id="2b961-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="2b961-122">Verifique se apenas um proxy estático ou um proxy transparente está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="2b961-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="2b961-123">Os proxies de inspeção e interceptação de SSL também não são suportados por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="2b961-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="2b961-124">Configure uma exceção para a inspeção SSL e seu servidor proxy passar diretamente os dados do Defender para o Ponto de Extremidade no Linux para as URLs relevantes sem interceptação.</span><span class="sxs-lookup"><span data-stu-id="2b961-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="2b961-125">Adicionar seu certificado de interceptação ao armazenamento global não permitirá interceptação.</span><span class="sxs-lookup"><span data-stu-id="2b961-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="2b961-126">Se for necessário um proxy estático, adicione um parâmetro proxy ao comando acima, onde corresponde `proxy_address:port` ao endereço de proxy e à porta:</span><span class="sxs-lookup"><span data-stu-id="2b961-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="2b961-127">Certifique-se de usar o mesmo endereço proxy e porta configurados no `/lib/system/system/mdatp.service` arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b961-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="2b961-128">Verifique sua configuração de proxy se houver erros nos comandos acima.</span><span class="sxs-lookup"><span data-stu-id="2b961-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="2b961-129">O proxy estático não pode ser configurado por meio de uma variável de ambiente em todo `HTTPS_PROXY` o sistema.</span><span class="sxs-lookup"><span data-stu-id="2b961-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="2b961-130">Em vez disso, `HTTPS_PROXY` certifique-se de que está corretamente definido no `/lib/system/system/mdatp.service` arquivo.</span><span class="sxs-lookup"><span data-stu-id="2b961-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="2b961-131">Para usar um proxy estático, `mdatp.service` o arquivo deve ser modificado.</span><span class="sxs-lookup"><span data-stu-id="2b961-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="2b961-132">Certifique-se de que a parte de frente foi removida `#` para descompactar a seguinte linha de `/lib/systemd/system/mdatp.service` :</span><span class="sxs-lookup"><span data-stu-id="2b961-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="2b961-133">Certifique-se também de que o endereço proxy estático correto seja preenchido para substituir `address:port` .</span><span class="sxs-lookup"><span data-stu-id="2b961-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="2b961-134">Se esse arquivo estiver correto, tente executar o seguinte comando no terminal para recarregar o Defender para Ponto de Extremidade no Linux e propagar a configuração:</span><span class="sxs-lookup"><span data-stu-id="2b961-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint on Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="2b961-135">Após o sucesso, tente outro teste de conectividade da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="2b961-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="2b961-136">Se o problema persistir, contate o suporte ao cliente.</span><span class="sxs-lookup"><span data-stu-id="2b961-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="2b961-137">Recursos</span><span class="sxs-lookup"><span data-stu-id="2b961-137">Resources</span></span>

- <span data-ttu-id="2b961-138">Para obter mais informações sobre como configurar o produto para usar um proxy estático, consulte [Configure Microsoft Defender for Endpoint for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="2b961-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
