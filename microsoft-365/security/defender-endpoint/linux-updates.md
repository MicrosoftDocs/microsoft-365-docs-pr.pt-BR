---
title: Implantar atualizações para o Microsoft Defender ATP para Linux
ms.reviewer: ''
description: Descreve como implantar atualizações do Microsoft Defender ATP para Linux em ambientes corporativos.
keywords: microsoft, defender, atp, linux, atualizações, implantar
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: adc19192764e8c57a20f14cc908be23e8d9bdbc8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052947"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="506d9-104">Implantar atualizações do Microsoft Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="506d9-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="506d9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="506d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="506d9-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="506d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="506d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="506d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="506d9-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="506d9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="506d9-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="506d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="506d9-110">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="506d9-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="506d9-111">Cada versão do Defender para Ponto de Extremidade para Linux tem uma data de expiração, após a qual ela não continuará mais a proteger seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="506d9-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="506d9-112">Você deve atualizar o produto antes dessa data.</span><span class="sxs-lookup"><span data-stu-id="506d9-112">You must update the product prior to this date.</span></span> <span data-ttu-id="506d9-113">Para verificar a data de expiração, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="506d9-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="506d9-114">Para atualizar o Defender para Ponto de Extremidade para Linux manualmente, execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="506d9-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="506d9-115">RHEL e variantes (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="506d9-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="506d9-116">SLES e variantes</span><span class="sxs-lookup"><span data-stu-id="506d9-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="506d9-117">Sistemas Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="506d9-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
