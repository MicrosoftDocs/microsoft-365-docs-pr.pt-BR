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
ms.date: 06/15/2021
ms.openlocfilehash: f9ca83fcfba4b79898a0fed527e38947a4c230d6
ms.sourcegitcommit: 959c3c3633e40b7b0f5e2c8372409778005a24db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52950126"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="c9a57-104">Erros comuns a evitar ao definir exclusões</span><span class="sxs-lookup"><span data-stu-id="c9a57-104">Common mistakes to avoid when defining exclusions</span></span>

<span data-ttu-id="c9a57-105">Você pode definir uma lista de exclusão para itens que não deseja Microsoft Defender Antivírus examinar.</span><span class="sxs-lookup"><span data-stu-id="c9a57-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="c9a57-106">Esses itens excluídos podem conter ameaças que torna seu dispositivo vulnerável.</span><span class="sxs-lookup"><span data-stu-id="c9a57-106">Such excluded items could contain threats that make your device vulnerable.</span></span> <span data-ttu-id="c9a57-107">Este artigo descreve alguns erros comuns que você deve evitar ao definir exclusões.</span><span class="sxs-lookup"><span data-stu-id="c9a57-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="c9a57-108">Antes de definir suas listas de exclusão, [consulte Recomendações para definir exclusões](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span><span class="sxs-lookup"><span data-stu-id="c9a57-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="c9a57-109">Excluindo determinados itens confiáveis</span><span class="sxs-lookup"><span data-stu-id="c9a57-109">Excluding certain trusted items</span></span>

<span data-ttu-id="c9a57-110">Determinados arquivos, tipos de arquivo, pastas ou processos não devem ser excluídos da verificação, mesmo que você confie que eles não sejam mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="c9a57-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="c9a57-111">Não defina exclusões para os locais de pasta, extensões de arquivo e processos listados nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="c9a57-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following sections:</span></span>
- <span data-ttu-id="c9a57-112">Localizações de pastas</span><span class="sxs-lookup"><span data-stu-id="c9a57-112">Folder locations</span></span>
- <span data-ttu-id="c9a57-113">Extensões de arquivo</span><span class="sxs-lookup"><span data-stu-id="c9a57-113">File extensions</span></span>
- <span data-ttu-id="c9a57-114">Processos</span><span class="sxs-lookup"><span data-stu-id="c9a57-114">Processes</span></span>

### <a name="folder-locations"></a><span data-ttu-id="c9a57-115">Localizações de pastas</span><span class="sxs-lookup"><span data-stu-id="c9a57-115">Folder locations</span></span>

<span data-ttu-id="c9a57-116">Em geral, não defina exclusões para os seguintes locais de pasta:</span><span class="sxs-lookup"><span data-stu-id="c9a57-116">In general, do not define exclusions for the following folder locations:</span></span>

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

<span data-ttu-id="c9a57-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\`**Observe a seguinte exceção para SharePoint:** Exclua quando você usa proteção antivírus no nível de arquivo `C:\Users\ServiceAccount\AppData\Local\Temp` em [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="c9a57-117">`C:\Users\<UserProfileName>\AppData\Local\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\ServiceAccount\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

<span data-ttu-id="c9a57-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**Observe a seguinte exceção para SharePoint:** Exclua quando você usa proteção antivírus no nível de arquivo `C:\Users\Default\AppData\Local\Temp` em [SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span><span class="sxs-lookup"><span data-stu-id="c9a57-118">`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` **Note the following exception for SharePoint**: Do exclude `C:\Users\Default\AppData\Local\Temp` when you use [file-level antivirus protection in SharePoint](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9).</span></span>

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

### <a name="file-extensions"></a><span data-ttu-id="c9a57-119">Extensões de arquivo</span><span class="sxs-lookup"><span data-stu-id="c9a57-119">File extensions</span></span>

<span data-ttu-id="c9a57-120">Em geral, não defina exclusões para as seguintes extensões de arquivo:</span><span class="sxs-lookup"><span data-stu-id="c9a57-120">In general, do not define exclusions for the following file extensions:</span></span>

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

### <a name="processes"></a><span data-ttu-id="c9a57-121">Processos</span><span class="sxs-lookup"><span data-stu-id="c9a57-121">Processes</span></span> 

<span data-ttu-id="c9a57-122">Em geral, não defina exclusões para os seguintes processos:</span><span class="sxs-lookup"><span data-stu-id="c9a57-122">In general, do not define exclusions for the following processes:</span></span>

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

`dotnet.exe`

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
> <span data-ttu-id="c9a57-123">Você pode optar por excluir tipos de arquivo, como , , ou se seu ambiente tiver um software moderno e atualizado com uma política de atualização estrita para lidar com `.gif` `.jpg` quaisquer `.jpeg` `.png` vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="c9a57-123">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="c9a57-124">Usando apenas o nome do arquivo na lista de exclusão</span><span class="sxs-lookup"><span data-stu-id="c9a57-124">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="c9a57-125">Um malware pode ter o mesmo nome do arquivo em que você confia e deseja excluir da verificação.</span><span class="sxs-lookup"><span data-stu-id="c9a57-125">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="c9a57-126">Portanto, para evitar excluir um malware em potencial da verificação, use um caminho totalmente qualificado para o arquivo que você deseja excluir em vez de usar apenas o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c9a57-126">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="c9a57-127">Por exemplo, se você quiser excluir da verificação, use o `Filename.exe` caminho completo para o arquivo, como `C:\program files\contoso\Filename.exe` .</span><span class="sxs-lookup"><span data-stu-id="c9a57-127">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="c9a57-128">Usando uma única lista de exclusão para várias cargas de trabalho de servidor</span><span class="sxs-lookup"><span data-stu-id="c9a57-128">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="c9a57-129">Não use uma única lista de exclusão para definir exclusões para várias cargas de trabalho de servidor.</span><span class="sxs-lookup"><span data-stu-id="c9a57-129">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="c9a57-130">Divida as exclusões de diferentes cargas de trabalho de aplicativo ou serviço em várias listas de exclusão.</span><span class="sxs-lookup"><span data-stu-id="c9a57-130">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="c9a57-131">Por exemplo, a lista de exclusão para a carga de trabalho do servidor do IIS deve ser diferente da lista de exclusão para sua carga de trabalho SQL Server trabalho.</span><span class="sxs-lookup"><span data-stu-id="c9a57-131">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="c9a57-132">Usar variáveis de ambiente incorretas como curingas no nome do arquivo e no caminho da pasta ou listas de exclusão de extensão</span><span class="sxs-lookup"><span data-stu-id="c9a57-132">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="c9a57-133">Microsoft Defender Antivírus O serviço é executado no contexto do sistema usando a conta LocalSystem, o que significa que ele obtém informações da variável de ambiente do sistema e não da variável de ambiente do usuário.</span><span class="sxs-lookup"><span data-stu-id="c9a57-133">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="c9a57-134">O uso de variáveis de ambiente como curinga em listas de exclusão está limitado a variáveis do sistema e às aplicáveis a processos em execução como uma conta NT AUTHORITY\SYSTEM.</span><span class="sxs-lookup"><span data-stu-id="c9a57-134">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="c9a57-135">Portanto, não use variáveis de ambiente do usuário como caracteres curinga ao adicionar Microsoft Defender Antivírus exclusões de processo e pasta.</span><span class="sxs-lookup"><span data-stu-id="c9a57-135">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="c9a57-136">Consulte a tabela em [variáveis de ambiente do sistema](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) para uma lista completa de variáveis de ambiente do sistema.</span><span class="sxs-lookup"><span data-stu-id="c9a57-136">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="c9a57-137">Consulte [Usar curingas no nome](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) do arquivo e no caminho da pasta ou listas de exclusão de extensão para obter informações sobre como usar curingas em listas de exclusão.</span><span class="sxs-lookup"><span data-stu-id="c9a57-137">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

