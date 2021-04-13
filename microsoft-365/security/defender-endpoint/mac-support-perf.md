---
title: Solucionar problemas de desempenho do Microsoft Defender para Ponto de Extremidade no macOS
description: Solucionar problemas de desempenho no Microsoft Defender para Ponto de Extremidade no macOS.
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
ms.openlocfilehash: 18bde560543fd1344a64cf1edd64f02f12831c25
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689093"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Solucionar problemas de desempenho do Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade no macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Este tópico fornece algumas etapas gerais que podem ser usadas para reduzir os problemas de desempenho relacionados ao Microsoft Defender para Ponto de Extremidade no macOS.

A proteção em tempo real (RTP) é um recurso do Microsoft Defender para Ponto de Extremidade no macOS que monitora e protege continuamente seu dispositivo contra ameaças. Ele consiste no monitoramento de arquivos e processos e outras heurísticas.

Dependendo dos aplicativos que você está executando e das características do dispositivo, você pode ter um desempenho suboptimal ao executar o Microsoft Defender para Ponto de Extremidade no macOS. Em particular, aplicativos ou processos do sistema que acessam muitos recursos em um curto período de tempo podem levar a problemas de desempenho no Microsoft Defender para Ponto de Extremidade no macOS.

As etapas a seguir podem ser usadas para solucionar problemas e atenuar esses problemas:

1. Desabilite a proteção em tempo real usando um dos métodos a seguir e observe se o desempenho melhora. Essa abordagem ajuda a restringir se o Microsoft Defender para Ponto de Extremidade no macOS está contribuindo para os problemas de desempenho.

      Se o dispositivo não for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada usando uma das seguintes opções:

    - Na interface do usuário. Abra o Microsoft Defender para Ponto de Extremidade no macOS e navegue até **Gerenciar configurações**.

      ![Gerenciar captura de tela de proteção em tempo real](images/mdatp-36-rtp.png)

    - Do Terminal. Para fins de segurança, essa operação requer elevação.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      Se seu dispositivo for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada pelo administrador usando as instruções em Definir preferências do Microsoft Defender para Ponto de Extremidade [no macOS](mac-preferences.md).
      
      Se o problema de desempenho persistir enquanto a proteção em tempo real estiver desligada, a origem do problema poderá ser o componente de detecção e resposta do ponto de extremidade. Nesse caso, entre em contato com o suporte do cliente para obter mais instruções e mitigação.

2. Abra o Finder e navegue até  >  **Utilitários de Aplicativos.** Abra **o Monitor de Atividades** e analise quais aplicativos estão usando os recursos em seu sistema. Exemplos típicos incluem atualizadores e compiladores de software.

1. Para encontrar os aplicativos que estão disparando a maioria das verificações, você pode usar estatísticas em tempo real coletadas pelo Defender para Ponto de Extremidade para Mac.

      > [!NOTE]
      > Esse recurso está disponível na versão 100.90.70 ou mais recente.
      Esse recurso é habilitado por padrão nos canais **Dogfood** e **InsiderFast.** Se você estiver usando um canal de atualização diferente, esse recurso poderá ser habilitado a partir da linha de comando:
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      Esse recurso requer proteção em tempo real para ser habilitado. Para verificar o status da proteção em tempo real, execute o seguinte comando:

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    Verifique se a **entrada real_time_protection_enabled** é verdadeira. Caso contrário, execute o seguinte comando para habilita-lo:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      Para coletar estatísticas atuais, execute:

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      > [!NOTE]
      > Usar **--output json** (observe o traço duplo) garante que o formato de saída esteja pronto para análise.
      A saída desse comando mostrará todos os processos e suas atividades de verificação associadas.

1. Em seu sistema Mac, baixe o analisador Python de exemplo high_cpu_parser.py usando o comando:

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    A saída deste comando deve ser semelhante ao seguinte:

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. Em seguida, digite os seguintes comandos:

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      A saída do acima é uma lista dos principais colaboradores para problemas de desempenho. A primeira coluna é o identificador de processo (PID), a segunda coluna é o nome do processo e a última coluna é o número de arquivos verificados, classificação por impacto.

      Por exemplo, a saída do comando será algo como o abaixo:

      ```output
        ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
        27432 None 76703
        73467 actool     1249
        73914 xcodebuild 1081
        73873 bash 1050
        27475 None 836
        1    launchd    407
        73468 ibtool     344
        549  telemetryd_v1   325
        4764 None 228
        125  CrashPlanService 164
      ```

      Para melhorar o desempenho do Defender para Ponto de Extremidade para Mac, localize o que tem o número mais alto na linha Total de arquivos verificados e adicione uma exclusão para ele. Para obter mais informações, [consulte Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).

      > [!NOTE]
      > O aplicativo armazena estatísticas na memória e só mantém o controle da atividade do arquivo desde que foi iniciado e a proteção em tempo real foi habilitada. Os processos que foram lançados antes ou durante períodos em que a proteção em tempo real estava desligada não são contados. Além disso, somente os eventos que dispararam verificações são contados.
      > 
1. Configure o Microsoft Defender para Ponto de Extremidade no macOS com exclusões para os processos ou locais de disco que contribuem para os problemas de desempenho e rehabilitam a proteção em tempo real.

     Consulte [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md) para obter detalhes.
