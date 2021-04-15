---
title: Configurar exclusões do Microsoft Defender Antivírus no Windows Server
ms.reviewer: ''
manager: dansimp
description: O Windows Server inclui exclusões automáticas, com base na função de servidor. Você também pode adicionar exclusões personalizadas.
keywords: exclusões, servidor, exclusões automáticas, automáticas, personalizadas, verificações, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.openlocfilehash: 507edb980f671b2f39403cc41e540150f5e82891
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764336"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="c5c9b-105">Configurar exclusões do Microsoft Defender Antivírus no Windows Server</span><span class="sxs-lookup"><span data-stu-id="c5c9b-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c5c9b-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c5c9b-106">**Applies to:**</span></span>

- [<span data-ttu-id="c5c9b-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c5c9b-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c5c9b-108">O Microsoft Defender Antivírus no Windows Server 2016 e no Windows Server 2019 registra automaticamente determinadas exclusões, conforme definido pela sua função de servidor especificada.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="c5c9b-109">Essas exclusões não aparecem nas listas de exclusão padrão mostradas no aplicativo [segurança do Windows](microsoft-defender-security-center-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="c5c9b-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c5c9b-110">As exclusões automáticas só se aplicam à verificação de proteção em tempo real (RTP).</span><span class="sxs-lookup"><span data-stu-id="c5c9b-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="c5c9b-111">As exclusões automáticas não são adutadas durante uma verificação completa/rápida ou sob demanda.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="c5c9b-112">Além das exclusões automáticas definidas pela função de servidor, você pode adicionar ou remover exclusões personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="c5c9b-113">Para fazer isso, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="c5c9b-114">Configurar e validar exclusões com base no nome do arquivo, extensão e local da pasta</span><span class="sxs-lookup"><span data-stu-id="c5c9b-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c5c9b-115">Configurar e validar exclusões para arquivos abertos por processos</span><span class="sxs-lookup"><span data-stu-id="c5c9b-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="c5c9b-116">Alguns pontos para ter em mente</span><span class="sxs-lookup"><span data-stu-id="c5c9b-116">A few points to keep in mind</span></span>

<span data-ttu-id="c5c9b-117">Lembre-se dos seguintes pontos importantes:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="c5c9b-118">As exclusões personalizadas têm precedência sobre exclusões automáticas.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="c5c9b-119">As exclusões automáticas só se aplicam à verificação de proteção em tempo real (RTP).</span><span class="sxs-lookup"><span data-stu-id="c5c9b-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="c5c9b-120">As exclusões automáticas não são adutadas durante uma verificação completa/rápida ou sob demanda.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="c5c9b-121">Exclusões personalizadas e duplicadas não conflitam com exclusões automáticas.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="c5c9b-122">O Microsoft Defender Antivírus usa as ferramentas de Manutenção e Gerenciamento de Imagens de Implantação (DISM) para determinar quais funções estão instaladas em seu computador.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="c5c9b-123">Excluir exclusões automáticas</span><span class="sxs-lookup"><span data-stu-id="c5c9b-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="c5c9b-124">No Windows Server 2016 e no Windows Server 2019, as exclusões predefinidas fornecidas pelas atualizações de inteligência de segurança apenas excluem os caminhos padrão de uma função ou recurso.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="c5c9b-125">Se você instalou uma função ou recurso em um caminho personalizado ou deseja controlar manualmente o conjunto de exclusões, certifique-se de não participar das exclusões automáticas entregues em atualizações de inteligência de segurança.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="c5c9b-126">Mas lembre-se de que as exclusões que são entregues automaticamente são otimizadas para funções do Windows Server 2016 e 2019.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="c5c9b-127">Consulte [Recomendações para definir exclusões antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir suas listas de exclusão.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="c5c9b-128">A exclusão automática pode afetar adversamente o desempenho ou resultar em corrupção de dados.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="c5c9b-129">As exclusões que são entregues automaticamente são otimizadas para funções do Windows Server 2016 e do Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="c5c9b-130">Como as exclusões predefinidas apenas excluem caminhos padrão **,** se você mover NTDS e SYSVOL para outra unidade ou caminho diferente do caminho *original*, você deve adicionar exclusões manualmente usando as informações [aqui](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span><span class="sxs-lookup"><span data-stu-id="c5c9b-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="c5c9b-131">Você pode desabilitar as listas de exclusão automáticas com Política de Grupo, cmdlets do PowerShell e WMI.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="c5c9b-132">Usar a Política de Grupo para desabilitar a lista de exclusões automáticas no Windows Server 2016 e no Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c5c9b-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="c5c9b-133">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política [de Grupo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="c5c9b-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="c5c9b-134">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="c5c9b-135">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do computador e clique em **Modelos Administrativos.**</span><span class="sxs-lookup"><span data-stu-id="c5c9b-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="c5c9b-136">Expanda a árvore para **componentes do Windows**  >  **Exclusões do Microsoft Defender**  >  **Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="c5c9b-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="c5c9b-137">Clique duas **vezes em Desativar Exclusões Automáticas** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="c5c9b-138">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="c5c9b-139">Usar cmdlets do PowerShell para desabilitar a lista de exclusões automáticas no Windows Server 2016 e 2019</span><span class="sxs-lookup"><span data-stu-id="c5c9b-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="c5c9b-140">Use os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="c5c9b-141">Para saber mais, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="c5c9b-142">[Use cmdlets do PowerShell para configurar e executar o Microsoft Defender Antivírus.](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c5c9b-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="c5c9b-143">[Use o PowerShell com o Microsoft Defender Antivírus.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="c5c9b-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="c5c9b-144">Use a Instrução de Gerenciamento do Windows (WMI) para desabilitar a lista de exclusões automáticas no Windows Server 2016 e no Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="c5c9b-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="c5c9b-145">Use o **método Set** da classe [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) para as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="c5c9b-146">Confira o seguinte para obter mais informações e parâmetros permitidos:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="c5c9b-147">Windows Defender WMIv2 APIs</span><span class="sxs-lookup"><span data-stu-id="c5c9b-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="c5c9b-148">Lista de exclusões automáticas</span><span class="sxs-lookup"><span data-stu-id="c5c9b-148">List of automatic exclusions</span></span>

<span data-ttu-id="c5c9b-149">As seções a seguir contêm as exclusões que são entregues com caminhos de arquivo de exclusões automáticas e tipos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="c5c9b-150">Exclusões padrão para todas as funções</span><span class="sxs-lookup"><span data-stu-id="c5c9b-150">Default exclusions for all roles</span></span>

<span data-ttu-id="c5c9b-151">Esta seção lista as exclusões padrão para todas as funções do Windows Server 2016 e 2019.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="c5c9b-152">Os locais padrão podem ser diferentes dos listados neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="c5c9b-153">Arquivos do Windows "temp.edb"</span><span class="sxs-lookup"><span data-stu-id="c5c9b-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="c5c9b-154">Arquivos do Windows Update ou arquivos de Atualização Automática</span><span class="sxs-lookup"><span data-stu-id="c5c9b-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="c5c9b-155">Arquivos de segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="c5c9b-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="c5c9b-156">Arquivos de Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="c5c9b-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="c5c9b-157">Arquivos WINS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="c5c9b-158">Exclusões do Serviço de Replicação de Arquivos (FRS)</span><span class="sxs-lookup"><span data-stu-id="c5c9b-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="c5c9b-159">Arquivos na pasta de trabalho serviço de replicação de arquivo (FRS).</span><span class="sxs-lookup"><span data-stu-id="c5c9b-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="c5c9b-160">A pasta de trabalho FRS é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="c5c9b-161">Arquivos de log do banco de dados FRS.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-161">FRS Database log files.</span></span> <span data-ttu-id="c5c9b-162">A pasta de arquivo de log do banco de dados FRS é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="c5c9b-163">A pasta de preparação frs.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-163">The FRS staging folder.</span></span> <span data-ttu-id="c5c9b-164">A pasta de preparação é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="c5c9b-165">A pasta de pré-instalação FRS.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-165">The FRS preinstall folder.</span></span> <span data-ttu-id="c5c9b-166">Essa pasta é especificada pela pasta `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="c5c9b-167">O banco de dados DFSR (Replicação do Sistema de Arquivos Distribuídos) e pastas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="c5c9b-168">Essas pastas são especificadas pela chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="c5c9b-169">Para locais personalizados, consulte [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="c5c9b-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="c5c9b-170">Exclusões de processos</span><span class="sxs-lookup"><span data-stu-id="c5c9b-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="c5c9b-171">Exclusões do Hyper-V</span><span class="sxs-lookup"><span data-stu-id="c5c9b-171">Hyper-V exclusions</span></span>

<span data-ttu-id="c5c9b-172">A tabela a seguir lista as exclusões de tipo de arquivo, exclusões de pasta e exclusões de processo que são entregues automaticamente quando você instala a função Hyper-V.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="c5c9b-173">Exclusões de tipo de arquivo</span><span class="sxs-lookup"><span data-stu-id="c5c9b-173">File type exclusions</span></span> |<span data-ttu-id="c5c9b-174">Exclusões de pastas</span><span class="sxs-lookup"><span data-stu-id="c5c9b-174">Folder exclusions</span></span>  | <span data-ttu-id="c5c9b-175">Exclusões de processos</span><span class="sxs-lookup"><span data-stu-id="c5c9b-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="c5c9b-176">Arquivos SYSVOL</span><span class="sxs-lookup"><span data-stu-id="c5c9b-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="c5c9b-177">Exclusões do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c5c9b-177">Active Directory exclusions</span></span>

<span data-ttu-id="c5c9b-178">Esta seção lista as exclusões que são entregues automaticamente quando você instala os Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="c5c9b-179">Arquivos de banco de dados NTDS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-179">NTDS database files</span></span>

<span data-ttu-id="c5c9b-180">Os arquivos de banco de dados são especificados na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="c5c9b-181">Os arquivos de log de transações do AD DS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-181">The AD DS transaction log files</span></span>

<span data-ttu-id="c5c9b-182">Os arquivos de log de transação são especificados na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="c5c9b-183">A pasta de trabalho do NTDS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-183">The NTDS working folder</span></span>

<span data-ttu-id="c5c9b-184">Essa pasta é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="c5c9b-185">Exclusões de processo para arquivos de suporte relacionados ao AD DS e ao AD DS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="c5c9b-186">Exclusões do Servidor DHCP</span><span class="sxs-lookup"><span data-stu-id="c5c9b-186">DHCP Server exclusions</span></span>

<span data-ttu-id="c5c9b-187">Esta seção lista as exclusões que são entregues automaticamente quando você instala a função de Servidor DHCP.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="c5c9b-188">Os locais de arquivo do Servidor DHCP são especificados pelos parâmetros *DatabasePath*, *DhcpLogFilePath* e *BackupDatabasePath* na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="c5c9b-189">Exclusões do Servidor DNS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-189">DNS Server exclusions</span></span>

<span data-ttu-id="c5c9b-190">Esta seção lista as exclusões de arquivo e pasta e as exclusões de processo que são entregues automaticamente quando você instala a função de Servidor DNS.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="c5c9b-191">Exclusões de arquivos e pastas para a função de Servidor DNS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="c5c9b-192">Exclusões de processo para a função de Servidor DNS</span><span class="sxs-lookup"><span data-stu-id="c5c9b-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="c5c9b-193">Exclusões de Serviços de Armazenamento e Arquivo</span><span class="sxs-lookup"><span data-stu-id="c5c9b-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="c5c9b-194">Esta seção lista as exclusões de arquivo e pasta que são entregues automaticamente quando você instala a função Serviços de Arquivo e Armazenamento.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="c5c9b-195">As exclusões listadas abaixo não incluem exclusões para a função clustering.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="c5c9b-196">Exclusões do Servidor de Impressão</span><span class="sxs-lookup"><span data-stu-id="c5c9b-196">Print Server exclusions</span></span>

<span data-ttu-id="c5c9b-197">Esta seção lista as exclusões de tipo de arquivo, exclusões de pastas e as exclusões de processo que são entregues automaticamente quando você instala a função de Servidor de Impressão.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="c5c9b-198">Exclusões de tipo de arquivo</span><span class="sxs-lookup"><span data-stu-id="c5c9b-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="c5c9b-199">Exclusões de pastas</span><span class="sxs-lookup"><span data-stu-id="c5c9b-199">Folder exclusions</span></span>

<span data-ttu-id="c5c9b-200">Essa pasta é especificada na chave do Registro `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="c5c9b-201">Exclusões de processos</span><span class="sxs-lookup"><span data-stu-id="c5c9b-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="c5c9b-202">Exclusões do Servidor Web</span><span class="sxs-lookup"><span data-stu-id="c5c9b-202">Web Server exclusions</span></span>

<span data-ttu-id="c5c9b-203">Esta seção lista as exclusões de pasta e as exclusões de processo que são entregues automaticamente quando você instala a função de Servidor Web.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="c5c9b-204">Exclusões de pastas</span><span class="sxs-lookup"><span data-stu-id="c5c9b-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="c5c9b-205">Exclusões de processos</span><span class="sxs-lookup"><span data-stu-id="c5c9b-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="c5c9b-206">Desligar a verificação de arquivos na pasta Sysvol\Sysvol ou na pasta SYSVOL_DFSR\Sysvol</span><span class="sxs-lookup"><span data-stu-id="c5c9b-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="c5c9b-207">O local atual da pasta ou e todas as subpastas é o destino de repare do sistema de arquivos `Sysvol\Sysvol` da raiz do conjunto de `SYSVOL_DFSR\Sysvol` réplicas.</span><span class="sxs-lookup"><span data-stu-id="c5c9b-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="c5c9b-208">As `Sysvol\Sysvol` pastas e usam os seguintes locais por `SYSVOL_DFSR\Sysvol` padrão:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="c5c9b-209">O caminho para o ativo no momento é referenciado pelo compartilhamento NETLOGON e pode ser determinado pelo nome do valor `SYSVOL` SysVol na seguinte sub-chave: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="c5c9b-210">Exclua os seguintes arquivos desta pasta e de todas as subpastas:</span><span class="sxs-lookup"><span data-stu-id="c5c9b-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="c5c9b-211">Exclusões do Windows Server Update Services</span><span class="sxs-lookup"><span data-stu-id="c5c9b-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="c5c9b-212">Esta seção lista as exclusões de pasta que são entregues automaticamente quando você instala a função WSUS (Windows Server Update Services).</span><span class="sxs-lookup"><span data-stu-id="c5c9b-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="c5c9b-213">A pasta WSUS é especificada na chave do Registro `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="c5c9b-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="c5c9b-214">Confira também</span><span class="sxs-lookup"><span data-stu-id="c5c9b-214">See also</span></span>

- [<span data-ttu-id="c5c9b-215">Configurar e validar exclusões para verificações do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="c5c9b-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c5c9b-216">Configurar e validar exclusões com base no nome do arquivo, extensão e local da pasta</span><span class="sxs-lookup"><span data-stu-id="c5c9b-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c5c9b-217">Configurar e validar exclusões para arquivos abertos por processos</span><span class="sxs-lookup"><span data-stu-id="c5c9b-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c5c9b-218">Erros comuns a evitar ao definir exclusões</span><span class="sxs-lookup"><span data-stu-id="c5c9b-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c5c9b-219">Personalizar, iniciar e revisar os resultados das verificações e correção do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="c5c9b-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="c5c9b-220">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="c5c9b-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)