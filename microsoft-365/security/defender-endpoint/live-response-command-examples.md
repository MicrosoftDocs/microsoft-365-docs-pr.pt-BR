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
ms.openlocfilehash: 0e00464b5d5dcf348fcc76a3f093ac8bac373627
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187704"
---
# <a name="live-response-command-examples"></a>Exemplos de comando de resposta ao vivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Saiba mais sobre comandos comuns usados na resposta ao vivo e veja exemplos sobre como eles são normalmente usados.

Dependendo da função que foi concedida a você, você pode executar comandos básicos ou avançados de resposta ao vivo. Para obter mais informações sobre comandos básicos e avançados, consulte [Investigar entidades em dispositivos usando a resposta ao vivo](live-response.md).


## <a name="analyze"></a>analyze 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a>connections

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a>dir

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

## <a name="fileinfo"></a>fileinfo

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a>findfile

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a>getfile

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
> Os seguintes tipos de **arquivo não podem** ser baixados usando este comando de dentro do Live Response:
>
> * [Repare os arquivos de ponto](/windows/desktop/fileio/reparse-points/)
> * [Arquivos esparsos](/windows/desktop/fileio/sparse-files/)
> * Arquivos vazios
> * Arquivos virtuais ou arquivos que não estão totalmente presentes localmente
>
> Esses tipos de **arquivo são** suportados pelo [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).
>
> Use o PowerShell como uma alternativa, se você tiver problemas ao usar esse comando de dentro do Live Response.

## <a name="processes"></a>processos
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

## <a name="putfile"></a>putfile

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

## <a name="registry"></a>registro

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a>correção

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

## <a name="run"></a>executar

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

## <a name="scheduledtask"></a>scheduledtask

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


## <a name="undo"></a>undo

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

