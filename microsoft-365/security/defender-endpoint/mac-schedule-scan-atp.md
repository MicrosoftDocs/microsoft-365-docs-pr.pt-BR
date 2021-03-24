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
ms.openlocfilehash: 4151513874d295e3033b1ed365f10fb576c4ac18
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053953"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="b422a-104">Agendar verificações com o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="b422a-104">Schedule scans with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b422a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b422a-105">**Applies to:**</span></span>
- [<span data-ttu-id="b422a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b422a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b422a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b422a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b422a-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b422a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b422a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b422a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b422a-110">Embora você possa iniciar uma verificação de ameaças a qualquer momento com o Microsoft Defender para Ponto de Extremidade, sua empresa pode se beneficiar de verificações agendadas ou com tempo.</span><span class="sxs-lookup"><span data-stu-id="b422a-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="b422a-111">Por exemplo, você pode agendar uma verificação para ser executado no início de cada dia útil ou semana.</span><span class="sxs-lookup"><span data-stu-id="b422a-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="b422a-112">Agendar uma verificação *com o lançamento*</span><span class="sxs-lookup"><span data-stu-id="b422a-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="b422a-113">Você pode criar uma agenda de verificação usando *o* daemon lançado em um dispositivo macOS.</span><span class="sxs-lookup"><span data-stu-id="b422a-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="b422a-114">O código a seguir mostra o esquema que você precisa usar para agendar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="b422a-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="b422a-115">Abra um editor de texto e use este exemplo como um guia para seu próprio arquivo de verificação agendado.</span><span class="sxs-lookup"><span data-stu-id="b422a-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="b422a-116">Para obter mais informações sobre o formato de arquivo *.plist* usado aqui, consulte [Sobre Arquivos](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) de Lista de Propriedades de Informações no site oficial do desenvolvedor da Apple.</span><span class="sxs-lookup"><span data-stu-id="b422a-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

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

2. <span data-ttu-id="b422a-117">Salve o arquivo *como com.microsoft.wdav.schedquickscan.plist*.</span><span class="sxs-lookup"><span data-stu-id="b422a-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="b422a-118">Para executar uma verificação completa em vez de uma verificação rápida, altere a linha 12, , para usar a opção em vez de (ou seja, ) e salve o arquivo como `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched **full** scan.plist* em vez *de com.microsoft.wdav.sched **quick** scan.plist*.</span><span class="sxs-lookup"><span data-stu-id="b422a-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="b422a-119">Abrir **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="b422a-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="b422a-120">Insira os seguintes comandos para carregar o arquivo:</span><span class="sxs-lookup"><span data-stu-id="b422a-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="b422a-121">Sua verificação agendada será executado na data, hora e frequência que você definiu em sua lista p.</span><span class="sxs-lookup"><span data-stu-id="b422a-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="b422a-122">No exemplo, a verificação é executado às 2:00 todas as sextas-feiras.</span><span class="sxs-lookup"><span data-stu-id="b422a-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="b422a-123">O `Weekday` valor de usa um inteiro para indicar o quinto dia da semana ou `StartCalendarInterval` sexta-feira.</span><span class="sxs-lookup"><span data-stu-id="b422a-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="b422a-124">Os agentes *executados com o lançamento* não serão executados no horário agendado enquanto o dispositivo estiver adormecida.</span><span class="sxs-lookup"><span data-stu-id="b422a-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="b422a-125">Em vez disso, eles serão executados depois que o dispositivo é retomado do modo de sono.</span><span class="sxs-lookup"><span data-stu-id="b422a-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="b422a-126">Se o dispositivo estiver desligado, a verificação será executado no próximo tempo de verificação agendado.</span><span class="sxs-lookup"><span data-stu-id="b422a-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="b422a-127">Agendar uma verificação com o Intune</span><span class="sxs-lookup"><span data-stu-id="b422a-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="b422a-128">Você também pode agendar verificações com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b422a-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="b422a-129">O [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) de shell disponível em [Scripts do Microsoft Defender para Ponto](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) de Extremidade persistirá quando o dispositivo for retomado do modo de sono.</span><span class="sxs-lookup"><span data-stu-id="b422a-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="b422a-130">Consulte [Usar scripts de shell em dispositivos macOS no Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) para obter instruções mais detalhadas sobre como usar esse script em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="b422a-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
