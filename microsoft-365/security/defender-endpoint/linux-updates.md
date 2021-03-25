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
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187716"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a>Implantar atualizações do Microsoft Defender para Ponto de Extremidade para Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.

> [!WARNING]
> Cada versão do Defender para Ponto de Extremidade para Linux tem uma data de expiração, após a qual ela não continuará mais a proteger seu dispositivo. Você deve atualizar o produto antes dessa data. Para verificar a data de expiração, execute o seguinte comando:
> ```bash
> mdatp health --field product_expiration
> ```

Para atualizar o Defender para Ponto de Extremidade para Linux manualmente, execute um dos seguintes comandos:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL e variantes (CentOS e Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES e variantes

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Sistemas Ubuntu e Debian

```bash
sudo apt-get install --only-upgrade mdatp
```
