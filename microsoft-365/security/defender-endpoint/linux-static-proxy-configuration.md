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
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a>Configurar o Microsoft Defender para Ponto de Extremidade para Linux para descoberta de proxy estático

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

O Microsoft Defender ATP pode descobrir um servidor proxy usando a ```HTTPS_PROXY``` variável de ambiente. Essa configuração deve ser **configurada** no momento da instalação e após a instalação do produto.

## <a name="installation-time-configuration"></a>Configuração do tempo de instalação

Durante a instalação, ```HTTPS_PROXY``` a variável de ambiente deve ser passada para o gerenciador de pacotes. O gerenciador de pacotes pode ler essa variável de qualquer uma das seguintes maneiras:

- A ```HTTPS_PROXY``` variável é definida ```/etc/environment``` com a seguinte linha:

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- A `HTTPS_PROXY` variável é definida na configuração global do gerenciador de pacotes. Por exemplo, no Ubuntu 18.04, você pode adicionar a seguinte linha a `/etc/apt/apt.conf.d/proxy.conf` :
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > Observe que acima de dois métodos podem definir o proxy a ser usado para outros aplicativos em seu sistema. Use este método com cautela ou somente se isso for para ser uma configuração global geral.
  
- A `HTTPS_PROXY` variável é pré-anexada aos comandos de instalação ou desinstalação. Por exemplo, com o gerenciador de pacotes APT, prepare a variável da seguinte forma ao instalar o Microsoft Defender para o Ponto de Extremidade: 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > Não adicione sudo entre a definição de variável de ambiente e apt, caso contrário, a variável não será propagada.

A `HTTPS_PROXY` variável de ambiente pode ser definida de forma semelhante durante a desinstalação.

Observe que a instalação e a desinstalação não falharão necessariamente se um proxy for necessário, mas não configurado. No entanto, a telemetria não será enviada e a operação pode demorar muito mais devido aos tempos de tempo de rede.

## <a name="post-installation-configuration"></a>Configuração pós-instalação
  
Após a instalação, `HTTPS_PROXY` a variável de ambiente deve ser definida no arquivo de serviço Defender for Endpoint. Para fazer isso, abra `/lib/systemd/system/mdatp.service` em um editor de texto durante a execução como o usuário raiz. Em seguida, você pode propagar a variável para o serviço de duas maneiras:

- Descompacte a linha `#Environment="HTTPS_PROXY=http://address:port"` e especifique seu endereço de proxy estático.

- Adicione uma linha `EnvironmentFile=/path/to/env/file` . Esse caminho pode apontar para ou um arquivo personalizado, um `/etc/environment` dos quais precisa adicionar a seguinte linha:
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

Depois de modificar o `mdatp.service` arquivo, salve e feche-o. Reinicie o serviço para que as alterações possam ser aplicadas. No Ubuntu, isso envolve dois comandos:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
