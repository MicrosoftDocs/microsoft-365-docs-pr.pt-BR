---
title: Erros comuns a evitar ao definir exclusões
description: Evite erros comuns ao definir exclusões para verificações do Microsoft Defender Antivírus.
keywords: exclusões, arquivos, extensão, tipo de arquivo, nome da pasta, nome do arquivo, verificações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d14e37c8f3cfdfe8d88bfd4e255a431fbb8d6d41
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689827"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Erros comuns a evitar ao definir exclusões

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Você pode definir uma lista de exclusão para itens que não deseja que o Microsoft Defender Antivírus digitalizar. Esses itens excluídos podem conter ameaças que torna seu dispositivo vulnerável. 

Este artigo descreve alguns erros comuns que você deve evitar ao definir exclusões. 

Antes de definir suas listas de exclusão, consulte [Recomendações para definir exclusões](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Excluindo determinados itens confiáveis

Determinados arquivos, tipos de arquivo, pastas ou processos não devem ser excluídos da verificação, mesmo que você confie que eles não sejam mal-intencionados. 

Não defina exclusões para os locais de pasta, extensões de arquivo e processos listados na tabela a seguir:

| Localizações de pastas | Extensões de arquivo | Processos |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> Você pode optar por excluir tipos de arquivo, como , , ou se seu ambiente tiver um software moderno e atualizado com uma política de atualização estrita para lidar com `.gif` `.jpg` quaisquer `.jpeg` `.png` vulnerabilidades.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Usando apenas o nome do arquivo na lista de exclusão

Um malware pode ter o mesmo nome do arquivo em que você confia e deseja excluir da verificação. Portanto, para evitar excluir um malware em potencial da verificação, use um caminho totalmente qualificado para o arquivo que você deseja excluir em vez de usar apenas o nome do arquivo. Por exemplo, se você quiser excluir da verificação, use o `Filename.exe` caminho completo para o arquivo, como `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Usando uma única lista de exclusão para várias cargas de trabalho de servidor

Não use uma única lista de exclusão para definir exclusões para várias cargas de trabalho de servidor. Divida as exclusões de diferentes cargas de trabalho de aplicativo ou serviço em várias listas de exclusão. Por exemplo, a lista de exclusão para a carga de trabalho do Servidor do IIS deve ser diferente da lista de exclusão para sua SQL Server de trabalho.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Usar variáveis de ambiente incorretas como curingas no nome do arquivo e no caminho da pasta ou listas de exclusão de extensão

O Serviço Antivírus do Microsoft Defender é executado no contexto do sistema usando a conta LocalSystem, o que significa que ele obtém informações da variável do ambiente do sistema e não da variável de ambiente do usuário. O uso de variáveis de ambiente como curinga em listas de exclusão está limitado a variáveis do sistema e às aplicáveis a processos em execução como uma conta NT AUTHORITY\SYSTEM. Portanto, não use variáveis de ambiente do usuário como curingas ao adicionar a pasta do Microsoft Defender Antivírus e exclusões de processo. Consulte a tabela em [variáveis de ambiente do sistema](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) para uma lista completa de variáveis de ambiente do sistema.

Consulte [Usar curingas no nome](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) do arquivo e no caminho da pasta ou listas de exclusão de extensão para obter informações sobre como usar curingas em listas de exclusão.

## <a name="related-articles"></a>Artigos relacionados

- [Configurar e validar exclusões em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões com base na extensão de arquivo e no local da pasta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar exclusões do Microsoft Defender Antivírus no Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
