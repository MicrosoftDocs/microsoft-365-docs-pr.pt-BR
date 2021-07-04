---
title: Exemplos de comando de Resposta ao vivo
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
ms.openlocfilehash: 82052634b79bf433731d0afdab45e3d75e6497e0
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289326"
---
# <a name="live-response-command-examples"></a>Exemplos de comando de Resposta ao vivo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Saiba mais sobre comandos comuns usados na resposta ao vivo e veja exemplos sobre como eles são normalmente usados.

Dependendo da função que foi concedida a você, você pode executar comandos básicos ou avançados de resposta ao vivo. Para obter mais informações sobre comandos básicos e avançados, consulte [Investigar entidades em dispositivos usando a resposta ao vivo](live-response.md).

## <a name="analyze"></a>analyze

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a>connections

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a>dir

```console
# List files and sub-folders in the current folder
dir
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a>fileinfo

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a>findfile

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a>getfile

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> Os seguintes tipos de **arquivo não podem** ser baixados usando este comando de dentro do Live Response:
>
> - [Repare os arquivos de ponto](/windows/desktop/fileio/reparse-points/)
> - [Arquivos esparsos](/windows/desktop/fileio/sparse-files/)
> - Arquivos vazios
> - Arquivos virtuais ou arquivos que não estão totalmente presentes localmente
>
> Esses tipos de **arquivo são** suportados pelo [PowerShell](/powershell/scripting/overview).
>
> Use o PowerShell como uma alternativa, se você tiver problemas ao usar esse comando de dentro do Live Response.

## <a name="library"></a>library

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```

## <a name="processes"></a>processos

```console
# Show all processes
processes
```

```console
# Get process by pid
processes 123
```

```console
# Get process by pid with argument name
processes -pid 123
```

```console
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a>putfile

```console
# Upload file from library
putfile get-process-by-name.ps1
```

```console
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```console
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a>registro

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a>correção

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# See list of all remediated entities
remediate list
```

## <a name="run"></a>executar

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

>[!NOTE]
>
> Para comandos de execução longa, como '**run**' ou '**getfile**', talvez você queira usar o símbolo ' ' no final do comando para executar essa ação em **&** segundo plano.
> Isso permitirá que você continue investigando o computador e retorne ao comando em segundo plano quando terminar de usar o comando básico '**fg** ['](live-response.md#basic-commands).

## <a name="scheduledtask"></a>scheduledtask

```console
# Get all scheduled tasks
scheduledtasks
```

```console
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```

## <a name="undo"></a>undo

```console
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```console
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```
