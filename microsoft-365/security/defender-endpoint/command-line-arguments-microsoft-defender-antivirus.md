---
title: Use a linha de comando para gerenciar Microsoft Defender Antivírus
description: Execute Microsoft Defender Antivírus e configure a proteção de última geração com um utilitário de linha de comando dedicado.
keywords: executar a verificação do Windows Defender, executar a verificação antivírus da linha de comando, executar a verificação do Windows Defender da linha de comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 85fb60d8d4504ba3a4aa8744c1183d094da01a9b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274743"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="2e68c-104">Configurar e gerenciar Microsoft Defender Antivírus com a mpcmdrun.exe de linha de comando</span><span class="sxs-lookup"><span data-stu-id="2e68c-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2e68c-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2e68c-105">**Applies to:**</span></span>

- [<span data-ttu-id="2e68c-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2e68c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2e68c-107">Você pode executar várias Microsoft Defender Antivírus com a ferramenta de linha de **comando dedicadampcmdrun.exe**.</span><span class="sxs-lookup"><span data-stu-id="2e68c-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="2e68c-108">Esse utilitário é útil quando você deseja automatizar Microsoft Defender Antivírus uso.</span><span class="sxs-lookup"><span data-stu-id="2e68c-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="2e68c-109">Você pode encontrar o utilitário em `%ProgramFiles%\Windows Defender\MpCmdRun.exe` .</span><span class="sxs-lookup"><span data-stu-id="2e68c-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="2e68c-110">Você deve executar a partir de um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2e68c-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="2e68c-111">Talvez seja necessário abrir uma versão de nível de administrador do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="2e68c-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="2e68c-112">Ao pesquisar o **Prompt de Comando no** menu Iniciar, escolha Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="2e68c-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="2e68c-113">Se você estiver executando uma versão atualizada da Plataforma do Microsoft Defender, execute `**MpCmdRun**` a partir do seguinte local: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .</span><span class="sxs-lookup"><span data-stu-id="2e68c-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="2e68c-114">O utilitário tem os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="2e68c-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="2e68c-115">Veja um exemplo:</span><span class="sxs-lookup"><span data-stu-id="2e68c-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="2e68c-116">Comando</span><span class="sxs-lookup"><span data-stu-id="2e68c-116">Command</span></span>  | <span data-ttu-id="2e68c-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="2e68c-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="2e68c-118">`-?`**ou**`-h`</span><span class="sxs-lookup"><span data-stu-id="2e68c-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="2e68c-119">Exibe todas as opções disponíveis para esta ferramenta</span><span class="sxs-lookup"><span data-stu-id="2e68c-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="2e68c-120">Verifica se há software mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="2e68c-120">Scans for malicious software.</span></span> <span data-ttu-id="2e68c-121">Os valores **para ScanType** são: **0** Padrão, de acordo com sua configuração, **-1** Verificação rápida, **-2** Verificação completa, **-3** Verificação personalizada de arquivo e diretório.</span><span class="sxs-lookup"><span data-stu-id="2e68c-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="2e68c-122">CpuThrottling irá honrar a throttling de CPU configurada da política</span><span class="sxs-lookup"><span data-stu-id="2e68c-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="2e68c-123">Inicia o rastreamento de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="2e68c-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="2e68c-124">Coleta informações de suporte.</span><span class="sxs-lookup"><span data-stu-id="2e68c-124">Collects support information.</span></span> <span data-ttu-id="2e68c-125">Consulte '[coletando dados de diagnóstico](collect-diagnostic-data.md)'</span><span class="sxs-lookup"><span data-stu-id="2e68c-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="2e68c-126">O mesmo que `-GetFiles` , mas saídas para a pasta DiagTrack temporária</span><span class="sxs-lookup"><span data-stu-id="2e68c-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="2e68c-127">Restaura a inteligência de segurança instalada para uma cópia de backup anterior ou para o conjunto padrão original</span><span class="sxs-lookup"><span data-stu-id="2e68c-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="2e68c-128">Remove apenas a inteligência de segurança baixada dinamicamente</span><span class="sxs-lookup"><span data-stu-id="2e68c-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="2e68c-129">Restaura o mecanismo instalado anteriormente</span><span class="sxs-lookup"><span data-stu-id="2e68c-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="2e68c-130">Verifica se há novas atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="2e68c-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="2e68c-131">Restaura ou lista itens em quarentena</span><span class="sxs-lookup"><span data-stu-id="2e68c-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="2e68c-132">Carrega inteligência de segurança dinâmica</span><span class="sxs-lookup"><span data-stu-id="2e68c-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="2e68c-133">Lista a inteligência de segurança dinâmica carregada</span><span class="sxs-lookup"><span data-stu-id="2e68c-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="2e68c-134">Remove a inteligência de segurança dinâmica</span><span class="sxs-lookup"><span data-stu-id="2e68c-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="2e68c-135">Verifica se um caminho é excluído</span><span class="sxs-lookup"><span data-stu-id="2e68c-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="2e68c-136">Verifica se sua rede pode se comunicar com o serviço Microsoft Defender Antivírus nuvem.</span><span class="sxs-lookup"><span data-stu-id="2e68c-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="2e68c-137">Esse comando funcionará apenas Windows 10 versão 1703 ou superior.</span><span class="sxs-lookup"><span data-stu-id="2e68c-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="2e68c-138">Erros comuns na execução de comandos por mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="2e68c-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="2e68c-139">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="2e68c-139">Error message</span></span> | <span data-ttu-id="2e68c-140">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="2e68c-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="2e68c-141">O Microsoft Defender Antivírus está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="2e68c-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="2e68c-142">Habilita o serviço e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="2e68c-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="2e68c-143">**Observação:**  No Windows 10 1909 ou mais antigo, e Windows Server 2019 ou mais antigo, o serviço era chamado de serviço "Windows Defender Antivírus".</span><span class="sxs-lookup"><span data-stu-id="2e68c-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="2e68c-144">Você está executando o comando de um computador que Windows 10 versão 1607 ou mais antiga, ou Windows Server 2016 `-ValidateMapsConnection` ou mais antigo.</span><span class="sxs-lookup"><span data-stu-id="2e68c-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="2e68c-145">Execute o comando de um computador Windows 10 versão 1703 ou mais recente ou Windows Server 2019 ou mais recente.</span><span class="sxs-lookup"><span data-stu-id="2e68c-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="2e68c-146">A ferramenta precisa ser executado de: ou (onde pode ser diferente, já que as atualizações da plataforma são `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` mensais, exceto para março)</span><span class="sxs-lookup"><span data-stu-id="2e68c-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="2e68c-147">Não há privilégios suficientes.</span><span class="sxs-lookup"><span data-stu-id="2e68c-147">Not enough privileges.</span></span> <span data-ttu-id="2e68c-148">Use o prompt de comando (cmd.exe) como administrador.</span><span class="sxs-lookup"><span data-stu-id="2e68c-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="2e68c-149">O firewall está bloqueando a conexão ou realizando a inspeção SSL.</span><span class="sxs-lookup"><span data-stu-id="2e68c-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="2e68c-150">Possíveis problemas relacionados à rede, como problemas de resolução de nomes</span><span class="sxs-lookup"><span data-stu-id="2e68c-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="2e68c-151">O firewall está bloqueando a conexão ou realizando a inspeção SSL.</span><span class="sxs-lookup"><span data-stu-id="2e68c-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="2e68c-152">O firewall está bloqueando a conexão ou realizando a inspeção SSL.</span><span class="sxs-lookup"><span data-stu-id="2e68c-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="2e68c-153">O firewall está bloqueando a conexão ou realizando a inspeção SSL.</span><span class="sxs-lookup"><span data-stu-id="2e68c-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="2e68c-154">Confira também</span><span class="sxs-lookup"><span data-stu-id="2e68c-154">See also</span></span>

- [<span data-ttu-id="2e68c-155">Configurar recursos do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="2e68c-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="2e68c-156">Gerenciar Microsoft Defender Antivírus em sua empresa</span><span class="sxs-lookup"><span data-stu-id="2e68c-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2e68c-157">Tópicos de referência para ferramentas de gerenciamento e configuração</span><span class="sxs-lookup"><span data-stu-id="2e68c-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="2e68c-158">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="2e68c-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)