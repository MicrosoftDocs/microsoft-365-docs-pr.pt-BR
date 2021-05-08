---
title: Implantar atualizações do Microsoft Defender para Ponto de Extremidade no Linux
ms.reviewer: ''
description: Descreve como implantar atualizações do Microsoft Defender para Ponto de Extremidade no Linux em ambientes corporativos.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, atualizações, deploy
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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274719"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="6fed5-104">Implantar atualizações do Microsoft Defender para Ponto de Extremidade no Linux</span><span class="sxs-lookup"><span data-stu-id="6fed5-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6fed5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6fed5-105">**Applies to:**</span></span>
- [<span data-ttu-id="6fed5-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6fed5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6fed5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fed5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6fed5-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6fed5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6fed5-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6fed5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6fed5-110">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="6fed5-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="6fed5-111">Cada versão do Defender para Ponto de Extremidade no Linux tem uma data de expiração, após a qual ele não continuará mais a proteger seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6fed5-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="6fed5-112">Você deve atualizar o produto antes dessa data.</span><span class="sxs-lookup"><span data-stu-id="6fed5-112">You must update the product prior to this date.</span></span> <span data-ttu-id="6fed5-113">Para verificar a data de expiração, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6fed5-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="6fed5-114">Geralmente, os recursos disponíveis do Microsoft Defender para o Ponto de Extremidade são equivalentes, independentemente do canal de atualização usado para uma implantação (Insider), Visualização (Externa), Atual (Produção)).</span><span class="sxs-lookup"><span data-stu-id="6fed5-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="6fed5-115">Para atualizar o Defender para Ponto de Extremidade no Linux manualmente, execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="6fed5-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="6fed5-116">RHEL e variantes (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="6fed5-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="6fed5-117">SLES e variantes</span><span class="sxs-lookup"><span data-stu-id="6fed5-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="6fed5-118">Sistemas Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="6fed5-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
