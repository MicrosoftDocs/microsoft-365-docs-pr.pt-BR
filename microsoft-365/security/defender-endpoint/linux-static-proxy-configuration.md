---
title: Descoberta de proxy estático do Microsoft Defender ATP para Linux
ms.reviewer: ''
description: Descreve como configurar o Microsoft Defender ATP para descoberta de proxy estático.
keywords: microsoft, defender, atp, linux, instalação, proxy
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
ms.openlocfilehash: b96f49d6c4744eae987393c17792c4f566d98997
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587054"
---
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a><span data-ttu-id="2c227-104">Configurar o Microsoft Defender para Ponto de Extremidade para Linux para descoberta de proxy estático</span><span class="sxs-lookup"><span data-stu-id="2c227-104">Configure Microsoft Defender for Endpoint for Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2c227-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2c227-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c227-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2c227-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c227-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c227-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2c227-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2c227-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2c227-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2c227-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="2c227-110">O Microsoft Defender ATP pode descobrir um servidor proxy usando a ```HTTPS_PROXY``` variável de ambiente.</span><span class="sxs-lookup"><span data-stu-id="2c227-110">Microsoft Defender ATP can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="2c227-111">Essa configuração deve ser **configurada** no momento da instalação e após a instalação do produto.</span><span class="sxs-lookup"><span data-stu-id="2c227-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="2c227-112">Configuração do tempo de instalação</span><span class="sxs-lookup"><span data-stu-id="2c227-112">Installation time configuration</span></span>

<span data-ttu-id="2c227-113">Durante a instalação, ```HTTPS_PROXY``` a variável de ambiente deve ser passada para o gerenciador de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2c227-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="2c227-114">O gerenciador de pacotes pode ler essa variável de qualquer uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="2c227-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="2c227-115">A ```HTTPS_PROXY``` variável é definida ```/etc/environment``` com a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="2c227-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="2c227-116">A `HTTPS_PROXY` variável é definida na configuração global do gerenciador de pacotes.</span><span class="sxs-lookup"><span data-stu-id="2c227-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="2c227-117">Por exemplo, no Ubuntu 18.04, você pode adicionar a seguinte linha a `/etc/apt/apt.conf.d/proxy.conf` :</span><span class="sxs-lookup"><span data-stu-id="2c227-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="2c227-118">Observe que acima de dois métodos podem definir o proxy a ser usado para outros aplicativos em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="2c227-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="2c227-119">Use este método com cautela ou somente se isso for para ser uma configuração global geral.</span><span class="sxs-lookup"><span data-stu-id="2c227-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="2c227-120">A `HTTPS_PROXY` variável é pré-anexada aos comandos de instalação ou desinstalação.</span><span class="sxs-lookup"><span data-stu-id="2c227-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="2c227-121">Por exemplo, com o gerenciador de pacotes APT, prepare a variável da seguinte forma ao instalar o Microsoft Defender para o Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="2c227-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="2c227-122">Não adicione sudo entre a definição de variável de ambiente e apt, caso contrário, a variável não será propagada.</span><span class="sxs-lookup"><span data-stu-id="2c227-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="2c227-123">A `HTTPS_PROXY` variável de ambiente pode ser definida de forma semelhante durante a desinstalação.</span><span class="sxs-lookup"><span data-stu-id="2c227-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="2c227-124">Observe que a instalação e a desinstalação não falharão necessariamente se um proxy for necessário, mas não configurado.</span><span class="sxs-lookup"><span data-stu-id="2c227-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="2c227-125">No entanto, a telemetria não será enviada e a operação pode demorar muito mais devido aos tempos de tempo de rede.</span><span class="sxs-lookup"><span data-stu-id="2c227-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="2c227-126">Configuração pós-instalação</span><span class="sxs-lookup"><span data-stu-id="2c227-126">Post installation configuration</span></span>
  
<span data-ttu-id="2c227-127">Após a instalação, `HTTPS_PROXY` a variável de ambiente deve ser definida no arquivo de serviço Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2c227-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="2c227-128">Para fazer isso, abra `/lib/systemd/system/mdatp.service` em um editor de texto durante a execução como o usuário raiz.</span><span class="sxs-lookup"><span data-stu-id="2c227-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="2c227-129">Em seguida, você pode propagar a variável para o serviço de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="2c227-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="2c227-130">Descompacte a linha `#Environment="HTTPS_PROXY=http://address:port"` e especifique seu endereço de proxy estático.</span><span class="sxs-lookup"><span data-stu-id="2c227-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="2c227-131">Adicione uma linha `EnvironmentFile=/path/to/env/file` .</span><span class="sxs-lookup"><span data-stu-id="2c227-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="2c227-132">Esse caminho pode apontar para ou um arquivo personalizado, um `/etc/environment` dos quais precisa adicionar a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="2c227-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="2c227-133">Depois de modificar o `mdatp.service` arquivo, salve e feche-o.</span><span class="sxs-lookup"><span data-stu-id="2c227-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="2c227-134">Reinicie o serviço para que as alterações possam ser aplicadas.</span><span class="sxs-lookup"><span data-stu-id="2c227-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="2c227-135">No Ubuntu, isso envolve dois comandos:</span><span class="sxs-lookup"><span data-stu-id="2c227-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
