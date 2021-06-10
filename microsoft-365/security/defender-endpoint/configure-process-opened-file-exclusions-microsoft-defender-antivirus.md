---
title: Configurar exclusões para arquivos abertos por processos específicos
description: Você pode excluir arquivos de verificações se eles foram abertos por um processo específico.
keywords: Microsoft Defender Antivírus, processo, exclusão, arquivos, verificações
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
ms.openlocfilehash: 2fdc646cf616ff6a6fa36a83be3d2b1dd0432fbe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274595"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a><span data-ttu-id="d0ba3-104">Configurar exclusões para arquivos abertos por processos</span><span class="sxs-lookup"><span data-stu-id="d0ba3-104">Configure exclusions for files opened by processes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d0ba3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d0ba3-105">**Applies to:**</span></span>

- [<span data-ttu-id="d0ba3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d0ba3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d0ba3-107">Você pode excluir arquivos que foram abertos por processos específicos Microsoft Defender Antivírus verificações.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-107">You can exclude files that have been opened by specific processes from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="d0ba3-108">Consulte [Recomendações para definir exclusões antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir suas listas de exclusão.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-108">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

<span data-ttu-id="d0ba3-109">Este artigo descreve como configurar listas de exclusão.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-109">This article describes how to configure exclusion lists.</span></span> 

## <a name="examples-of-exclusions"></a><span data-ttu-id="d0ba3-110">Exemplos de exclusões</span><span class="sxs-lookup"><span data-stu-id="d0ba3-110">Examples of exclusions</span></span>

|<span data-ttu-id="d0ba3-111">Exclusão</span><span class="sxs-lookup"><span data-stu-id="d0ba3-111">Exclusion</span></span> | <span data-ttu-id="d0ba3-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d0ba3-112">Example</span></span> |
|---|---|
|<span data-ttu-id="d0ba3-113">Qualquer arquivo no computador aberto por qualquer processo com um nome de arquivo específico</span><span class="sxs-lookup"><span data-stu-id="d0ba3-113">Any file on the machine that is opened by any process with a specific file name</span></span> | <span data-ttu-id="d0ba3-114">A `test.exe` especificação excluiria os arquivos abertos por:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-114">Specifying `test.exe` would exclude files opened by:</span></span> <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|<span data-ttu-id="d0ba3-115">Qualquer arquivo no computador aberto por qualquer processo em uma pasta específica</span><span class="sxs-lookup"><span data-stu-id="d0ba3-115">Any file on the machine that is opened by any process under a specific folder</span></span> | <span data-ttu-id="d0ba3-116">A `c:\test\sample\*` especificação excluiria os arquivos abertos por:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-116">Specifying `c:\test\sample\*` would exclude files opened by:</span></span><br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|<span data-ttu-id="d0ba3-117">Qualquer arquivo no computador aberto por um processo específico em uma pasta específica</span><span class="sxs-lookup"><span data-stu-id="d0ba3-117">Any file on the machine that is opened by a specific process in a specific folder</span></span> | <span data-ttu-id="d0ba3-118">Especificar `c:\test\process.exe` excluiria arquivos abertos apenas por `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="d0ba3-118">Specifying `c:\test\process.exe` would exclude files only opened by `c:\test\process.exe`</span></span> |


<span data-ttu-id="d0ba3-119">Quando você adiciona um processo à lista de exclusão de processo, Microsoft Defender Antivírus não examinará arquivos abertos por esse processo, independentemente de onde os arquivos estão localizados.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-119">When you add a process to the process exclusion list, Microsoft Defender Antivirus won't scan files opened by that process, no matter where the files are located.</span></span> <span data-ttu-id="d0ba3-120">O processo em si, no entanto, será verificado, a menos que ele também tenha sido adicionado à lista [de exclusão de arquivo](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d0ba3-120">The process itself, however, will be scanned unless it has also been added to the [file exclusion list](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="d0ba3-121">As exclusões só se aplicam à proteção e ao monitoramento sempre em [tempo real.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d0ba3-121">The exclusions only apply to [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="d0ba3-122">Eles não se aplicam a verificações agendadas ou sob demanda.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-122">They don't apply to scheduled or on-demand scans.</span></span>

<span data-ttu-id="d0ba3-123">As alterações feitas com a Política de Grupo nas listas de exclusão serão mostrar **nas** listas no Segurança do Windows [app](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d0ba3-123">Changes made with Group Policy to the exclusion lists **will show** in the lists in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="d0ba3-124">No entanto, as alterações feitas no aplicativo Segurança do Windows **não aparecerão** nas listas de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-124">However, changes made in the Windows Security app **will not show** in the Group Policy lists.</span></span>

<span data-ttu-id="d0ba3-125">Você pode adicionar, remover e revisar as listas para exclusões na Política de Grupo, Microsoft Endpoint Configuration Manager, Microsoft Intune e com o aplicativo Segurança do Windows, e você pode usar curingas para personalizar ainda mais as listas.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-125">You can add, remove, and review the lists for exclusions in Group Policy, Microsoft Endpoint Configuration Manager, Microsoft Intune, and with the Windows Security app, and you can use wildcards to further customize the lists.</span></span>

<span data-ttu-id="d0ba3-126">Você também pode usar cmdlets do PowerShell e WMI para configurar as listas de exclusão, incluindo a revisão de suas listas.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-126">You can also use PowerShell cmdlets and WMI to configure the exclusion lists, including reviewing your lists.</span></span>

<span data-ttu-id="d0ba3-127">Por padrão, as alterações locais feitas nas listas (por usuários com privilégios de administrador; alterações feitas com o PowerShell e o WMI) serão mescladas com as listas conforme definido (e implantado) pela Política de Grupo, Pelo Gerenciador de Configurações ou pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-127">By default, local changes made to the lists (by users with administrator privileges; changes made with PowerShell and WMI) will be merged with the lists as defined (and deployed) by Group Policy, Configuration Manager, or Intune.</span></span> <span data-ttu-id="d0ba3-128">As listas de Política de Grupo terão precedência no caso de conflitos.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-128">The Group Policy lists will take precedence in the case of conflicts.</span></span>

<span data-ttu-id="d0ba3-129">Você pode [configurar como listas de exclusões definidas local](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) e globalmente são mescladas para permitir que as alterações locais substituam as configurações de implantação gerenciada.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-129">You can [configure how locally and globally defined exclusions lists are merged](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) to allow local changes to override managed deployment settings.</span></span>

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a><span data-ttu-id="d0ba3-130">Configurar a lista de exclusões para arquivos abertos por processos especificados</span><span class="sxs-lookup"><span data-stu-id="d0ba3-130">Configure the list of exclusions for files opened by specified processes</span></span>

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="d0ba3-131">Use Microsoft Intune para excluir arquivos que foram abertos por processos especificados de verificações</span><span class="sxs-lookup"><span data-stu-id="d0ba3-131">Use Microsoft Intune to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="d0ba3-132">Confira [Definir as configurações de restrição de dispositivo no Microsoft Intune](/intune/device-restrictions-configure) e [Configurações de restrição de dispositivo do Microsoft Defender Antivírus para Windows 10 no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-132">See [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and [Microsoft Defender Antivirus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) for more details.</span></span>

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="d0ba3-133">Use Microsoft Endpoint Manager para excluir arquivos que foram abertos por processos especificados de verificações</span><span class="sxs-lookup"><span data-stu-id="d0ba3-133">Use Microsoft Endpoint Manager to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="d0ba3-134">Consulte [Como criar e implantar políticas antimalware: Configurações de](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) exclusão para obter detalhes sobre como configurar Microsoft Endpoint Manager (branch atual).</span><span class="sxs-lookup"><span data-stu-id="d0ba3-134">See [How to create and deploy antimalware policies: Exclusion settings](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) for details on configuring Microsoft Endpoint Manager (current branch).</span></span>

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="d0ba3-135">Usar a Política de Grupo para excluir arquivos que foram abertos por processos especificados de verificações</span><span class="sxs-lookup"><span data-stu-id="d0ba3-135">Use Group Policy to exclude files that have been opened by specified processes from scans</span></span>

1. <span data-ttu-id="d0ba3-136">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-136">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="d0ba3-137">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="d0ba3-137">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="d0ba3-138">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Exclusões**.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-138">Expand the tree to **Windows components > Microsoft Defender Antivirus > Exclusions**.</span></span>

4. <span data-ttu-id="d0ba3-139">Clique duas vezes **em Exclusões de Processo** e adicione as exclusões:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-139">Double-click **Process Exclusions** and add the exclusions:</span></span>

    1. <span data-ttu-id="d0ba3-140">De definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-140">Set the option to **Enabled**.</span></span>
    2. <span data-ttu-id="d0ba3-141">Na seção **Opções,** clique em **Mostrar...**.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-141">Under the **Options** section, click **Show...**.</span></span>
    3. <span data-ttu-id="d0ba3-142">Insira cada processo em sua própria linha na coluna **Nome do** valor.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-142">Enter each process on its own line under the **Value name** column.</span></span> <span data-ttu-id="d0ba3-143">Consulte a tabela de exemplo para os diferentes tipos de exclusões de processo.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-143">See the example table for the different types of process exclusions.</span></span>  <span data-ttu-id="d0ba3-144">Insira **0** na coluna **Valor** para todos os processos.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-144">Enter **0** in the **Value** column for all processes.</span></span>

5. <span data-ttu-id="d0ba3-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-145">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="d0ba3-146">Usar cmdlets do PowerShell para excluir arquivos que foram abertos por processos especificados de verificações</span><span class="sxs-lookup"><span data-stu-id="d0ba3-146">Use PowerShell cmdlets to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="d0ba3-147">Usar o PowerShell para adicionar ou remover exclusões para arquivos que foram abertos por processos requer o uso de uma combinação de três cmdlets com o `-ExclusionProcess` parâmetro.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-147">Using PowerShell to add or remove exclusions for files that have been opened by processes requires using a combination of three cmdlets with the `-ExclusionProcess` parameter.</span></span> <span data-ttu-id="d0ba3-148">Os cmdlets estão todos no módulo [Defender](/powershell/module/defender/).</span><span class="sxs-lookup"><span data-stu-id="d0ba3-148">The cmdlets are all in the [Defender module](/powershell/module/defender/).</span></span>

<span data-ttu-id="d0ba3-149">O formato dos cmdlets é:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-149">The format for the cmdlets is:</span></span>

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

<span data-ttu-id="d0ba3-150">Os seguintes são permitidos como \<cmdlet> :</span><span class="sxs-lookup"><span data-stu-id="d0ba3-150">The following are allowed as the \<cmdlet>:</span></span>

|<span data-ttu-id="d0ba3-151">Ação de configuração</span><span class="sxs-lookup"><span data-stu-id="d0ba3-151">Configuration action</span></span> | <span data-ttu-id="d0ba3-152">Cmdlet do PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0ba3-152">PowerShell cmdlet</span></span> |
|---|---|
|<span data-ttu-id="d0ba3-153">Criar ou substituir a lista</span><span class="sxs-lookup"><span data-stu-id="d0ba3-153">Create or overwrite the list</span></span> | `Set-MpPreference` |
|<span data-ttu-id="d0ba3-154">Adicionar à lista</span><span class="sxs-lookup"><span data-stu-id="d0ba3-154">Add to the list</span></span> | `Add-MpPreference` |
|<span data-ttu-id="d0ba3-155">Remover itens da lista</span><span class="sxs-lookup"><span data-stu-id="d0ba3-155">Remove items from the list</span></span> | `Remove-MpPreference` |

>[!IMPORTANT]
><span data-ttu-id="d0ba3-156">Se você tiver criado uma lista, com ou , usando o cmdlet novamente substituirá `Set-MpPreference` `Add-MpPreference` a lista `Set-MpPreference` existente.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-156">If you have created a list, either with `Set-MpPreference` or `Add-MpPreference`, using the `Set-MpPreference` cmdlet again will overwrite the existing list.</span></span>

<span data-ttu-id="d0ba3-157">Por exemplo, o trecho de código a seguir faria com que as verificações do Microsoft Defender AV excluisse qualquer arquivo aberto pelo processo especificado:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-157">For example, the following code snippet would cause Microsoft Defender AV scans to exclude any file that is opened by the specified process:</span></span>

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

<span data-ttu-id="d0ba3-158">Para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus, consulte Manage antivírus with PowerShell [cmdlets and Microsoft Defender Antivírus cmdlets](/powershell/module/defender).</span><span class="sxs-lookup"><span data-stu-id="d0ba3-158">For more information on how to use PowerShell with Microsoft Defender Antivirus, see Manage antivirus with PowerShell cmdlets and [Microsoft Defender Antivirus cmdlets](/powershell/module/defender).</span></span>

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="d0ba3-159">Use Windows Instrução de Gerenciamento (WMI) para excluir arquivos que foram abertos por processos especificados de verificações</span><span class="sxs-lookup"><span data-stu-id="d0ba3-159">Use Windows Management Instruction (WMI) to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="d0ba3-160">Use os [ **métodos Definir,** **Adicionar** e **Remover** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-160">Use the [**Set**, **Add**, and **Remove** methods of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ExclusionProcess
```

<span data-ttu-id="d0ba3-161">O uso de **Set,** **Add** e **Remove é** análogo a suas contrapartes no PowerShell: , `Set-MpPreference` e `Add-MpPreference` `Remove-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="d0ba3-161">The use of **Set**, **Add**, and **Remove** is analogous to their counterparts in PowerShell: `Set-MpPreference`, `Add-MpPreference`, and `Remove-MpPreference`.</span></span>

<span data-ttu-id="d0ba3-162">Para obter mais informações e parâmetros permitidos, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="d0ba3-162">For more information and allowed parameters, see  [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a><span data-ttu-id="d0ba3-163">Use o Segurança do Windows para excluir arquivos que foram abertos por processos especificados de verificações</span><span class="sxs-lookup"><span data-stu-id="d0ba3-163">Use the Windows Security app to exclude files that have been opened by specified processes from scans</span></span>

<span data-ttu-id="d0ba3-164">Consulte [Adicionar exclusões no aplicativo Segurança do Windows para](microsoft-defender-security-center-antivirus.md) obter instruções.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-164">See [Add exclusions in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions.</span></span>

## <a name="use-wildcards-in-the-process-exclusion-list"></a><span data-ttu-id="d0ba3-165">Usar caracteres curinga na lista de exclusão de processos</span><span class="sxs-lookup"><span data-stu-id="d0ba3-165">Use wildcards in the process exclusion list</span></span>

<span data-ttu-id="d0ba3-166">O uso de caracteres curinga na lista de exclusão de processos é diferente de seu uso em outras listas de exclusão.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-166">The use of wildcards in the process exclusion list is different from their use in other exclusion lists.</span></span>

<span data-ttu-id="d0ba3-167">Em particular, você não pode usar o caractere curinga do ponto de interrogação ( ) e o caractere curinga do asterisco ( ) só pode ser usado no final de um `?` `*` caminho completo.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-167">In particular, you cannot use the question mark (`?`) wildcard, and the asterisk (`*`) wildcard can only be used at the end of a complete path.</span></span> <span data-ttu-id="d0ba3-168">Você ainda pode usar variáveis de ambiente (como ) como curingas ao definir itens na lista de exclusão `%ALLUSERSPROFILE%` de processo.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-168">You can still use environment variables (such as `%ALLUSERSPROFILE%`) as wildcards when defining items in the process exclusion list.</span></span>

<span data-ttu-id="d0ba3-169">A tabela a seguir descreve como os curingas podem ser usados na lista de exclusão de processos:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-169">The following table describes how the wildcards can be used in the process exclusion list:</span></span>

|<span data-ttu-id="d0ba3-170">Curinga</span><span class="sxs-lookup"><span data-stu-id="d0ba3-170">Wildcard</span></span> | <span data-ttu-id="d0ba3-171">Exemplo de uso</span><span class="sxs-lookup"><span data-stu-id="d0ba3-171">Example use</span></span> | <span data-ttu-id="d0ba3-172">Exemplo corresponde</span><span class="sxs-lookup"><span data-stu-id="d0ba3-172">Example matches</span></span> |
|:---|:---|:---|
|<span data-ttu-id="d0ba3-173">`*` (asterisco)</span><span class="sxs-lookup"><span data-stu-id="d0ba3-173">`*` (asterisk)</span></span> <br/><br/> <span data-ttu-id="d0ba3-174">Substitui qualquer número de caracteres</span><span class="sxs-lookup"><span data-stu-id="d0ba3-174">Replaces any number of characters</span></span> | `C:\MyData\*` | <span data-ttu-id="d0ba3-175">Qualquer arquivo aberto por `C:\MyData\file.exe`</span><span class="sxs-lookup"><span data-stu-id="d0ba3-175">Any file opened by `C:\MyData\file.exe`</span></span> |
|<span data-ttu-id="d0ba3-176">Variáveis de ambiente</span><span class="sxs-lookup"><span data-stu-id="d0ba3-176">Environment variables</span></span> <br/><br/> <span data-ttu-id="d0ba3-177">A variável definida é preenchida como um caminho quando a exclusão é avaliada</span><span class="sxs-lookup"><span data-stu-id="d0ba3-177">The defined variable is populated as a path when the exclusion is evaluated</span></span> | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | <span data-ttu-id="d0ba3-178">Qualquer arquivo aberto por `C:\ProgramData\CustomLogFiles\file.exe`</span><span class="sxs-lookup"><span data-stu-id="d0ba3-178">Any file opened by `C:\ProgramData\CustomLogFiles\file.exe`</span></span> |

## <a name="review-the-list-of-exclusions"></a><span data-ttu-id="d0ba3-179">Revisar a lista de exclusões</span><span class="sxs-lookup"><span data-stu-id="d0ba3-179">Review the list of exclusions</span></span>

<span data-ttu-id="d0ba3-180">Você pode recuperar os itens na lista de exclusão com MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)ou o [Segurança do Windows app](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d0ba3-180">You can retrieve the items in the exclusion list with MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure), or the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

<span data-ttu-id="d0ba3-181">Se você usar o PowerShell, poderá recuperar a lista de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-181">If you use PowerShell, you can retrieve the list in two ways:</span></span>

- <span data-ttu-id="d0ba3-182">Recupere o status de todas as Microsoft Defender Antivírus preferências.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-182">Retrieve the status of all Microsoft Defender Antivirus preferences.</span></span> <span data-ttu-id="d0ba3-183">Cada uma das listas será exibida em linhas separadas, mas os itens dentro de cada lista serão combinados na mesma linha.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-183">Each of the lists will be displayed on separate lines, but the items within each list will be combined into the same line.</span></span>
- <span data-ttu-id="d0ba3-184">Escreva o status de todas as preferências em uma variável e use essa variável para chamar apenas a lista específica em que você está interessado.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-184">Write the status of all preferences to a variable, and use that variable to only call the specific list you are interested in.</span></span> <span data-ttu-id="d0ba3-185">Cada uso é `Add-MpPreference` gravado em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-185">Each use of `Add-MpPreference` is written to a new line.</span></span>

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a><span data-ttu-id="d0ba3-186">Validar a lista de exclusão usando MpCmdRun</span><span class="sxs-lookup"><span data-stu-id="d0ba3-186">Validate the exclusion list by using MpCmdRun</span></span>

<span data-ttu-id="d0ba3-187">Para verificar exclusões com a ferramenta [de linha de ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)comando mpcmdrun.exe, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-187">To check exclusions with the dedicated [command-line tool mpcmdrun.exe](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options), use the following command:</span></span>

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> <span data-ttu-id="d0ba3-188">Verificar exclusões com MpCmdRun requer Microsoft Defender Antivírus CAMP versão 4.18.1812.3 (lançada em dezembro de 2018) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-188">Checking exclusions with MpCmdRun requires Microsoft Defender Antivirus CAMP version 4.18.1812.3 (released in December 2018) or later.</span></span>


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a><span data-ttu-id="d0ba3-189">Revise a lista de exclusões juntamente com todas as outras preferências Microsoft Defender Antivírus usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0ba3-189">Review the list of exclusions alongside all other Microsoft Defender Antivirus preferences by using PowerShell</span></span>

<span data-ttu-id="d0ba3-190">Use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-190">Use the following cmdlet:</span></span>

```PowerShell
Get-MpPreference
```

<span data-ttu-id="d0ba3-191">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-191">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a><span data-ttu-id="d0ba3-192">Recuperar uma lista de exclusões específica usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d0ba3-192">Retrieve a specific exclusions list by using PowerShell</span></span>

<span data-ttu-id="d0ba3-193">Use o seguinte trecho de código (insira cada linha como um comando separado); substitua **WDAVprefs** por qualquer rótulo que você deseja nomear a variável:</span><span class="sxs-lookup"><span data-stu-id="d0ba3-193">Use the following code snippet (enter each line as a separate command); replace **WDAVprefs** with whatever label you want to name the variable:</span></span>

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

<span data-ttu-id="d0ba3-194">Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender) Microsoft Defender Antivírus e Defender para obter mais informações sobre como usar o PowerShell com Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="d0ba3-194">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d0ba3-195">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d0ba3-195">Related articles</span></span>

- [<span data-ttu-id="d0ba3-196">Configurar e validar exclusões em Microsoft Defender Antivírus verificações</span><span class="sxs-lookup"><span data-stu-id="d0ba3-196">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d0ba3-197">Configurar e validar exclusões com base no nome do arquivo, extensão e local da pasta</span><span class="sxs-lookup"><span data-stu-id="d0ba3-197">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d0ba3-198">Configurar Microsoft Defender Antivírus exclusões no Windows Server</span><span class="sxs-lookup"><span data-stu-id="d0ba3-198">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d0ba3-199">Erros comuns a evitar ao definir exclusões</span><span class="sxs-lookup"><span data-stu-id="d0ba3-199">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d0ba3-200">Personalizar, iniciar e revisar os resultados de Microsoft Defender Antivírus e correção</span><span class="sxs-lookup"><span data-stu-id="d0ba3-200">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d0ba3-201">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="d0ba3-201">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)