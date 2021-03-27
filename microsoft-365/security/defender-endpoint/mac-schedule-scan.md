---
title: Como agendar verificações com o MDATP para macOS
description: Saiba como agendar um tempo de verificação automática para o Microsoft Defender ATP no macOS para proteger melhor os ativos da sua organização.
keywords: microsoft, defender, atp, mac, scans, antivírus
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
ms.openlocfilehash: 4694ff0c0d0892b9261e61683654dfb58dfd724b
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394753"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a>Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Embora você possa iniciar uma verificação de ameaças a qualquer momento com o Microsoft Defender para Ponto de Extremidade, sua empresa pode se beneficiar de verificações agendadas ou com tempo. Por exemplo, você pode agendar uma verificação para ser executado no início de cada dia útil ou semana. 

## <a name="schedule-a-scan-with-launchd"></a>Agendar uma verificação *com o lançamento*

Você pode criar uma agenda de verificação usando *o* daemon lançado em um dispositivo macOS.

1. O código a seguir mostra o esquema que você precisa usar para agendar uma verificação. Abra um editor de texto e use este exemplo como um guia para seu próprio arquivo de verificação agendado.

    Para obter mais informações sobre o formato de arquivo *.plist* usado aqui, consulte [Sobre Arquivos](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) de Lista de Propriedades de Informações no site oficial do desenvolvedor da Apple.

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. Salve o arquivo *como com.microsoft.wdav.schedquickscan.plist*.

    > [!TIP]
    > Para executar uma verificação completa em vez de uma verificação rápida, altere a linha 12, , para usar a opção em vez de (ou seja, ) e salve o arquivo como `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* em vez *de com.microsoft.wdav.sched **quick** scan.plist*.

3. Abrir **Terminal**.
4. Insira os seguintes comandos para carregar o arquivo:

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. Sua verificação agendada será executado na data, hora e frequência que você definiu em sua lista p. No exemplo, a verificação é executado às 2:00 todas as sextas-feiras. 

    O `Weekday` valor de usa um inteiro para indicar o quinto dia da semana ou `StartCalendarInterval` sexta-feira.

 > [!IMPORTANT]
 > Os agentes *executados com o lançamento* não serão executados no horário agendado enquanto o dispositivo estiver adormecida. Em vez disso, eles serão executados depois que o dispositivo é retomado do modo de sono.
 >
 > Se o dispositivo estiver desligado, a verificação será executado no próximo tempo de verificação agendado.

## <a name="schedule-a-scan-with-intune"></a>Agendar uma verificação com o Intune

Você também pode agendar verificações com o Microsoft Intune. O [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) de shell disponível em [Scripts do Microsoft Defender para Ponto](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) de Extremidade persistirá quando o dispositivo for retomado do modo de sono. 

Consulte [Usar scripts de shell em dispositivos macOS no Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) para obter instruções mais detalhadas sobre como usar esse script em sua empresa.
