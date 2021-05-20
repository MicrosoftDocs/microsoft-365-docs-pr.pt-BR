---
title: Erros comuns a evitar ao definir exclusões
description: Evite erros comuns ao definir exclusões para Microsoft Defender Antivírus verificações.
keywords: exclusões, arquivos, extensão, tipo de arquivo, nome da pasta, nome do arquivo, verificações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/17/2021
ms.openlocfilehash: d10343538c995534878196cc57092c37fd2dcf7b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538058"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>Erros comuns a evitar ao definir exclusões

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Você pode definir uma lista de exclusão para itens que não deseja Microsoft Defender Antivírus examinar. Esses itens excluídos podem conter ameaças que torna seu dispositivo vulnerável. 

Este artigo descreve alguns erros comuns que você deve evitar ao definir exclusões. 

Antes de definir suas listas de exclusão, [consulte Recomendações para definir exclusões](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).

## <a name="excluding-certain-trusted-items"></a>Excluindo determinados itens confiáveis

Determinados arquivos, tipos de arquivo, pastas ou processos não devem ser excluídos da verificação, mesmo que você confie que eles não sejam mal-intencionados. 

Não defina exclusões para os locais de pasta, extensões de arquivo e processos listados nas seguintes seções:
- Localizações de pastas
- Extensões de arquivo
- Processos

### <a name="folder-locations"></a>Localizações de pastas

Em geral, não defina exclusões para os seguintes locais de pasta:

`%systemdrive%` 

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java` 

`%ProgramFiles%\Contoso\` 

`C:\Program Files\Contoso\` 

`%ProgramFiles(x86)%\Contoso\` 

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Observe a seguinte exceção para SharePoint:** Exclua quando você usa proteção antivírus no nível de arquivo `C:\Users\ServiceAccount\AppData\Local\Temp` em [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Observe a seguinte exceção para SharePoint:** Exclua quando você usa proteção antivírus no nível de arquivo `C:\Users\Default\AppData\Local\Temp` em [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

### <a name="file-extensions"></a>Extensões de arquivo

Em geral, não defina exclusões para as seguintes extensões de arquivo:

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com` 

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>Processos 

Em geral, não defina exclusões para os seguintes processos:

`AcroRd32.exe`  

`bitsadmin.exe`  

`excel.exe`  

`iexplore.exe`  

`java.exe`  

`outlook.exe`  

`psexec.exe`  

`powerpnt.exe`  

`powershell.exe`  

`schtasks.exe`

`svchost.exe` 

`wmic.exe`  

`winword.exe`  

`wuauclt.exe`  

`addinprocess.exe`  

`addinprocess32.exe`  

`addinutil.exe`  

`bash.exe`  

`bginfo.exe` 

`cdb.exe`  

`csi.exe`  

`dbghost.exe`  

`dbgsvc.exe`  

`dnx.exe`  

`fsi.exe`  

`fsiAnyCpu.exe`  

`kd.exe`  

`ntkd.exe`  

`lxssmanager.dll`  

`msbuild.exe` 

`mshta.exe`  

`ntsd.exe`  

`rcsi.exe`  

`system.management.automation.dll`  

`windbg.exe`

> [!NOTE]
> Você pode optar por excluir tipos de arquivo, como , , ou se seu ambiente tiver um software moderno e atualizado com uma política de atualização estrita para lidar com `.gif` `.jpg` quaisquer `.jpeg` `.png` vulnerabilidades.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>Usando apenas o nome do arquivo na lista de exclusão

Um malware pode ter o mesmo nome do arquivo em que você confia e deseja excluir da verificação. Portanto, para evitar excluir um malware em potencial da verificação, use um caminho totalmente qualificado para o arquivo que você deseja excluir em vez de usar apenas o nome do arquivo. Por exemplo, se você quiser excluir da verificação, use o `Filename.exe` caminho completo para o arquivo, como `C:\program files\contoso\Filename.exe` .

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>Usando uma única lista de exclusão para várias cargas de trabalho de servidor

Não use uma única lista de exclusão para definir exclusões para várias cargas de trabalho de servidor. Divida as exclusões de diferentes cargas de trabalho de aplicativo ou serviço em várias listas de exclusão. Por exemplo, a lista de exclusão para a carga de trabalho do servidor do IIS deve ser diferente da lista de exclusão para sua carga de trabalho SQL Server trabalho.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Usar variáveis de ambiente incorretas como curingas no nome do arquivo e no caminho da pasta ou listas de exclusão de extensão

Microsoft Defender Antivírus O serviço é executado no contexto do sistema usando a conta LocalSystem, o que significa que ele obtém informações da variável de ambiente do sistema e não da variável de ambiente do usuário. O uso de variáveis de ambiente como curinga em listas de exclusão está limitado a variáveis do sistema e às aplicáveis a processos em execução como uma conta NT AUTHORITY\SYSTEM. Portanto, não use variáveis de ambiente do usuário como caracteres curinga ao adicionar Microsoft Defender Antivírus exclusões de processo e pasta. Consulte a tabela em [variáveis de ambiente do sistema](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) para uma lista completa de variáveis de ambiente do sistema.

Consulte [Usar curingas no nome](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) do arquivo e no caminho da pasta ou listas de exclusão de extensão para obter informações sobre como usar curingas em listas de exclusão.

## <a name="related-articles"></a>Artigos relacionados

- [Configurar e validar exclusões em Microsoft Defender Antivírus verificações](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões com base na extensão de arquivo e no local da pasta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar Microsoft Defender Antivírus exclusões no Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
