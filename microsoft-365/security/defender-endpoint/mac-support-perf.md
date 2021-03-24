---
title: Solucionar problemas de desempenho do Microsoft Defender ATP para Mac
description: Solucionar problemas de desempenho no Microsoft Defender ATP para Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052889"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Solucionar problemas de desempenho do Microsoft Defender para Ponto de Extremidade para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade para Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este tópico fornece algumas etapas gerais que podem ser usadas para reduzir os problemas de desempenho relacionados ao Microsoft Defender para Ponto de Extremidade para Mac.

A proteção em tempo real (RTP) é um recurso do Microsoft Defender para Ponto de Extremidade para Mac que monitora e protege continuamente seu dispositivo contra ameaças. Ele consiste no monitoramento de arquivos e processos e outras heurísticas.

Dependendo dos aplicativos que você está executando e suas características de dispositivo, você pode ter um desempenho suboptimal ao executar o Microsoft Defender para Ponto de Extremidade para Mac. Em particular, aplicativos ou processos do sistema que acessam muitos recursos em um curto período de tempo podem levar a problemas de desempenho no Microsoft Defender para Ponto de Extremidade para Mac.

As etapas a seguir podem ser usadas para solucionar problemas e atenuar esses problemas:

1. Desabilite a proteção em tempo real usando um dos métodos a seguir e observe se o desempenho melhora. Essa abordagem ajuda a restringir se o Microsoft Defender para Ponto de Extremidade para Mac está contribuindo para os problemas de desempenho.

    Se o dispositivo não for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada usando uma das seguintes opções:

    - Na interface do usuário. Abra o Microsoft Defender para Ponto de Extremidade para Mac e navegue até **Gerenciar configurações**.

      ![Gerenciar captura de tela de proteção em tempo real](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - Do Terminal. Para fins de segurança, essa operação requer elevação.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    Se seu dispositivo for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada pelo administrador usando as instruções em Definir [preferências](mac-preferences.md)do Microsoft Defender para Ponto de Extremidade para Mac .

2. Abra o Finder e navegue até  >  **Utilitários de Aplicativos.** Abra **o Monitor de Atividades** e analise quais aplicativos estão usando os recursos em seu sistema. Exemplos típicos incluem atualizadores e compiladores de software.

3. Configure o Microsoft Defender para Ponto de Extremidade para Mac com exclusões para os processos ou locais de disco que contribuem para os problemas de desempenho e rehabilitam a proteção em tempo real.

    Consulte [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac para](mac-exclusions.md) obter detalhes.
