---
title: Exemplos de comando de resposta ao vivo
description: Aprenda a executar comandos de resposta ao vivo básicos ou avançados do Microsoft Defender para Endpoint e veja exemplos sobre como ele é usado.
keywords: exemplo, comando, cli, remoto, shell, conexão, ao vivo, resposta, em tempo real, comando, script, correção, busca, exportação, log, soltar, baixar, arquivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b25712e331597dc38d3f1cf98fdf70886406432e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054071"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="25217-104">Exemplos de comando de resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="25217-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25217-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="25217-105">**Applies to:**</span></span>
- [<span data-ttu-id="25217-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="25217-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="25217-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25217-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="25217-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="25217-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25217-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="25217-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="25217-110">Saiba mais sobre comandos comuns usados na resposta ao vivo e veja exemplos sobre como eles são normalmente usados.</span><span class="sxs-lookup"><span data-stu-id="25217-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="25217-111">Dependendo da função que foi concedida a você, você pode executar comandos básicos ou avançados de resposta ao vivo.</span><span class="sxs-lookup"><span data-stu-id="25217-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="25217-112">Para obter mais informações sobre comandos básicos e avançados, consulte [Investigar entidades em dispositivos usando a resposta ao vivo](live-response.md).</span><span class="sxs-lookup"><span data-stu-id="25217-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="25217-113">analyze</span><span class="sxs-lookup"><span data-stu-id="25217-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="25217-114">connections</span><span class="sxs-lookup"><span data-stu-id="25217-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="25217-115">dir</span><span class="sxs-lookup"><span data-stu-id="25217-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="25217-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="25217-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="25217-117">findfile</span><span class="sxs-lookup"><span data-stu-id="25217-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="25217-118">getfile</span><span class="sxs-lookup"><span data-stu-id="25217-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="25217-119">Os seguintes tipos de **arquivo não podem** ser baixados usando este comando de dentro do Live Response:</span><span class="sxs-lookup"><span data-stu-id="25217-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="25217-120">Repare os arquivos de ponto</span><span class="sxs-lookup"><span data-stu-id="25217-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="25217-121">Arquivos esparsos</span><span class="sxs-lookup"><span data-stu-id="25217-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="25217-122">Arquivos vazios</span><span class="sxs-lookup"><span data-stu-id="25217-122">Empty files</span></span>
> * <span data-ttu-id="25217-123">Arquivos virtuais ou arquivos que não estão totalmente presentes localmente</span><span class="sxs-lookup"><span data-stu-id="25217-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="25217-124">Esses tipos de **arquivo são** suportados pelo [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="25217-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="25217-125">Use o PowerShell como uma alternativa, se você tiver problemas ao usar esse comando de dentro do Live Response.</span><span class="sxs-lookup"><span data-stu-id="25217-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="25217-126">processos</span><span class="sxs-lookup"><span data-stu-id="25217-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="25217-127">putfile</span><span class="sxs-lookup"><span data-stu-id="25217-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="25217-128">registro</span><span class="sxs-lookup"><span data-stu-id="25217-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="25217-129">correção</span><span class="sxs-lookup"><span data-stu-id="25217-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="25217-130">executar</span><span class="sxs-lookup"><span data-stu-id="25217-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

## <a name="scheduledtask"></a><span data-ttu-id="25217-131">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="25217-131">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="25217-132">undo</span><span class="sxs-lookup"><span data-stu-id="25217-132">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

