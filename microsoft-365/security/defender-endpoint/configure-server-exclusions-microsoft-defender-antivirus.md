---
title: Configurar Microsoft Defender Antivírus exclusões no Windows Server
ms.reviewer: ''
manager: dansimp
description: Windows O servidor inclui exclusões automáticas, com base na função de servidor. Você também pode adicionar exclusões personalizadas.
keywords: exclusões, servidor, exclusões automáticas, automáticas, personalizadas, verificações, Microsoft Defender Antivírus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 02/10/2021
ms.topic: article
ms.openlocfilehash: f82da8eb0dcba39404c2b7f191e166aa78357cee
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274755"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Configurar Microsoft Defender Antivírus exclusões no Windows Server

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivírus no Windows Server 2016 e Windows Server 2019 registra automaticamente você em determinadas exclusões, conforme definido pela sua função de servidor especificada. Essas exclusões não aparecem nas listas de exclusão padrão mostradas no Segurança do Windows [app](microsoft-defender-security-center-antivirus.md).

> [!NOTE]
> As exclusões automáticas só se aplicam à verificação de proteção em tempo real (RTP). As exclusões automáticas não são adutadas durante uma verificação completa/rápida ou sob demanda.

Além das exclusões automáticas definidas pela função de servidor, você pode adicionar ou remover exclusões personalizadas. Para fazer isso, consulte estes artigos:
- [Configurar e validar exclusões com base no nome do arquivo, extensão e local da pasta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a>Alguns pontos para ter em mente

Lembre-se dos seguintes pontos importantes:

- As exclusões personalizadas têm precedência sobre exclusões automáticas.
- As exclusões automáticas só se aplicam à verificação de proteção em tempo real (RTP). As exclusões automáticas não são adutadas durante uma verificação completa/rápida ou sob demanda.
- Exclusões personalizadas e duplicadas não conflitam com exclusões automáticas.
- Microsoft Defender Antivírus usa as ferramentas de Manutenção e Gerenciamento de Imagens de Implantação (DISM) para determinar quais funções estão instaladas em seu computador.

## <a name="opt-out-of-automatic-exclusions"></a>Excluir exclusões automáticas

No Windows Server 2016 e no Windows Server 2019, as exclusões predefinidos fornecidas pelas atualizações de inteligência de segurança apenas excluem os caminhos padrão de uma função ou recurso. Se você instalou uma função ou recurso em um caminho personalizado ou deseja controlar manualmente o conjunto de exclusões, certifique-se de não participar das exclusões automáticas entregues em atualizações de inteligência de segurança. Mas lembre-se de que as exclusões que são entregues automaticamente são otimizadas para funções Windows Server 2016 e 2019. Consulte [Recomendações para definir exclusões antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir suas listas de exclusão.

> [!WARNING]
> A exclusão automática pode afetar adversamente o desempenho ou resultar em corrupção de dados. As exclusões que são entregues automaticamente são otimizadas para funções Windows Server 2016 e Windows Server 2019.

Como as exclusões predefinidas apenas excluem caminhos padrão **,** se você mover NTDS e SYSVOL para outra unidade ou caminho diferente do caminho *original*, você deve adicionar exclusões manualmente usando as informações [aqui](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .

Você pode desabilitar as listas de exclusão automáticas com Política de Grupo, cmdlets do PowerShell e WMI.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Usar a Política de Grupo para desabilitar a lista de exclusões automáticas no Windows Server 2016 e Windows Server 2019

1. No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)). Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.
2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração** do computador e clique em **Modelos Administrativos.**
3. Expanda a árvore para **Windows componentes**  >  **Microsoft Defender Antivírus**  >  **Exclusões**.
4. Clique duas **vezes em Desativar Exclusões Automáticas** e de definir a opção como **Habilitado**. Clique em **OK**. 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a>Usar cmdlets do PowerShell para desabilitar a lista de exclusões automáticas no Windows Server 2016 e 2019

Use os seguintes cmdlets:

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

Para saber mais, confira os seguintes recursos:

- [Use cmdlets do PowerShell para configurar e executar Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md).
- [Use o PowerShell com Microsoft Defender Antivírus](/powershell/module/defender/).

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>Use Windows Instrução de Gerenciamento (WMI) para desabilitar a lista de exclusões automáticas no Windows Server 2016 e Windows Server 2019

Use o **método Set** da classe [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) para as seguintes propriedades:

```WMI
DisableAutoExclusions
```

Confira o seguinte para obter mais informações e parâmetros permitidos:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a>Lista de exclusões automáticas

As seções a seguir contêm as exclusões que são entregues com caminhos de arquivo de exclusões automáticas e tipos de arquivo.

### <a name="default-exclusions-for-all-roles"></a>Exclusões padrão para todas as funções

Esta seção lista as exclusões padrão para todas as Windows Server 2016 e 2019.

> [!NOTE]
> Os locais padrão podem ser diferentes dos listados neste artigo.

#### <a name="windows-tempedb-files"></a>Windows Arquivos "temp.edb"

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a>Windows Atualizar arquivos ou arquivos de Atualização Automática

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a>Segurança do Windows arquivos

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a>Arquivos de Política de Grupo

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a>Arquivos WINS

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a>Exclusões do Serviço de Replicação de Arquivos (FRS)

- Arquivos na pasta de trabalho serviço de replicação de arquivo (FRS). A pasta de trabalho FRS é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- Arquivos de log do banco de dados FRS. A pasta de arquivo de log do banco de dados FRS é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- A pasta de preparação frs. A pasta de preparação é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- A pasta de pré-instalação FRS. Essa pasta é especificada pela pasta `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- O banco de dados DFSR (Replicação do Sistema de Arquivos Distribuídos) e pastas de trabalho. Essas pastas são especificadas pela chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > Para locais personalizados, consulte [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).

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

#### <a name="process-exclusions"></a>Exclusões de processos

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a>Exclusões do Hyper-V

A tabela a seguir lista as exclusões de tipo de arquivo, exclusões de pasta e exclusões de processo que são entregues automaticamente quando você instala a função Hyper-V.

|Exclusões de tipo de arquivo |Exclusões de pastas  | Exclusões de processos |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a>Arquivos SYSVOL

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a>Exclusões do Active Directory

Esta seção lista as exclusões que são entregues automaticamente quando você instala os Serviços de Domínio do Active Directory.

#### <a name="ntds-database-files"></a>Arquivos de banco de dados NTDS

Os arquivos de banco de dados são especificados na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a>Os arquivos de log de transações do AD DS

Os arquivos de log de transação são especificados na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a>A pasta de trabalho do NTDS

Essa pasta é especificada na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>Exclusões de processo para arquivos de suporte relacionados ao AD DS e ao AD DS

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a>Exclusões do Servidor DHCP

Esta seção lista as exclusões que são entregues automaticamente quando você instala a função de Servidor DHCP. Os locais de arquivo do Servidor DHCP são especificados pelos parâmetros *DatabasePath*, *DhcpLogFilePath* e *BackupDatabasePath* na chave do Registro `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a>Exclusões do Servidor DNS

Esta seção lista as exclusões de arquivo e pasta e as exclusões de processo que são entregues automaticamente quando você instala a função de Servidor DNS.

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>Exclusões de arquivos e pastas para a função de Servidor DNS

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a>Exclusões de processo para a função de Servidor DNS

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a>Exclusões de Armazenamento De arquivos e serviços

Esta seção lista as exclusões de arquivo e pasta que são entregues automaticamente quando você instala a função Arquivo e Armazenamento Serviços. As exclusões listadas abaixo não incluem exclusões para a função clustering.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a>Exclusões do Servidor de Impressão

Esta seção lista as exclusões de tipo de arquivo, exclusões de pastas e as exclusões de processo que são entregues automaticamente quando você instala a função de Servidor de Impressão.

#### <a name="file-type-exclusions"></a>Exclusões de tipo de arquivo

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a>Exclusões de pastas

Essa pasta é especificada na chave do Registro `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a>Exclusões de processos

- `spoolsv.exe`

### <a name="web-server-exclusions"></a>Exclusões do Servidor Web

Esta seção lista as exclusões de pasta e as exclusões de processo que são entregues automaticamente quando você instala a função de Servidor Web.

#### <a name="folder-exclusions"></a>Exclusões de pastas

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a>Exclusões de processos

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Desligar a verificação de arquivos na pasta Sysvol\Sysvol ou na pasta SYSVOL_DFSR\Sysvol

O local atual da pasta ou e todas as subpastas é o destino de repare do sistema de arquivos `Sysvol\Sysvol` da raiz do conjunto de `SYSVOL_DFSR\Sysvol` réplicas. As `Sysvol\Sysvol` pastas e usam os seguintes locais por `SYSVOL_DFSR\Sysvol` padrão:

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

O caminho para o ativo no momento é referenciado pelo compartilhamento NETLOGON e pode ser determinado pelo nome do valor `SYSVOL` SysVol na seguinte sub-chave: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

Exclua os seguintes arquivos desta pasta e de todas as subpastas:

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

### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services exclusões

Esta seção lista as exclusões de pasta que são entregues automaticamente quando você instala a função Windows Server Update Services (WSUS). A pasta WSUS é especificada na chave do Registro `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a>Confira também

- [Configurar e validar exclusões para Microsoft Defender Antivírus verificações](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões com base no nome do arquivo, extensão e local da pasta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Erros comuns a evitar ao definir exclusões](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Personalizar, iniciar e revisar os resultados de Microsoft Defender Antivírus e correção](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)