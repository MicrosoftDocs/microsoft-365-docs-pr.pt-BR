---
title: Configurar exclusões para arquivos abertos por processos específicos
description: Você pode excluir arquivos de verificações se eles foram abertos por um processo específico.
keywords: Microsoft Defender Antivírus, processo, exclusão, arquivos, verificações
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
ms.openlocfilehash: 4a117d2743436381029d047693f81303e5908b2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689789"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>Configurar exclusões para arquivos abertos por processos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode excluir arquivos que foram abertos por processos específicos das verificações do Microsoft Defender Antivírus. Consulte [Recomendações para definir exclusões antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir suas listas de exclusão.

Este artigo descreve como configurar listas de exclusão. 

## <a name="examples-of-exclusions"></a>Exemplos de exclusões

|Exclusão | Exemplo |
|---|---|
|Qualquer arquivo no computador aberto por qualquer processo com um nome de arquivo específico | A `test.exe` especificação excluiria os arquivos abertos por: <br/>`c:\sample\test.exe`<br/>`d:\internal\files\test.exe` |  
|Qualquer arquivo no computador aberto por qualquer processo em uma pasta específica | A `c:\test\sample\*` especificação excluiria os arquivos abertos por:<br/>`c:\test\sample\test.exe`<br/>`c:\test\sample\test2.exe`<br/>`c:\test\sample\utility.exe` | 
|Qualquer arquivo no computador aberto por um processo específico em uma pasta específica | Especificar `c:\test\process.exe` excluiria arquivos abertos apenas por `c:\test\process.exe` |


Quando você adiciona um processo à lista de exclusão de processos, o Microsoft Defender Antivírus não examinará os arquivos abertos por esse processo, independentemente de onde os arquivos estão localizados. O processo em si, no entanto, será verificado, a menos que ele também tenha sido adicionado à lista [de exclusão de arquivo](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

As exclusões só se aplicam à proteção e ao monitoramento sempre em [tempo real.](configure-real-time-protection-microsoft-defender-antivirus.md) Eles não se aplicam a verificações agendadas ou sob demanda.

As alterações feitas com a Política de Grupo nas **listas** de exclusão serão mostrar nas listas no aplicativo segurança [do Windows](microsoft-defender-security-center-antivirus.md). No entanto, as alterações feitas no aplicativo de Segurança do Windows **não aparecerão** nas listas de Política de Grupo.

Você pode adicionar, remover e revisar as listas de exclusões na Política de Grupo, no Microsoft Endpoint Configuration Manager, no Microsoft Intune e no aplicativo de Segurança do Windows e pode usar curingas para personalizar ainda mais as listas.

Você também pode usar cmdlets do PowerShell e WMI para configurar as listas de exclusão, incluindo a revisão de suas listas.

Por padrão, as alterações locais feitas nas listas (por usuários com privilégios de administrador; alterações feitas com o PowerShell e o WMI) serão mescladas com as listas conforme definido (e implantado) pela Política de Grupo, Pelo Gerenciador de Configurações ou pelo Intune. As listas de Política de Grupo terão precedência no caso de conflitos.

Você pode [configurar como listas de exclusões definidas local](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) e globalmente são mescladas para permitir que as alterações locais substituam as configurações de implantação gerenciada.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>Configurar a lista de exclusões para arquivos abertos por processos especificados

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar o Microsoft Intune para excluir arquivos que foram abertos por processos especificados de verificações

Consulte [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure) and Microsoft Defender [Antivírus device restriction settings for Windows 10 in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) para obter mais detalhes.

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar o Microsoft Endpoint Manager para excluir arquivos que foram abertos por processos especificados de verificações

Consulte [Como criar e implantar políticas antimalware: Configurações de](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) exclusão para obter detalhes sobre como configurar o Microsoft Endpoint Manager (branch atual).

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar a Política de Grupo para excluir arquivos que foram abertos por processos especificados de verificações

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **administrativos.**

3. Expanda a árvore **para componentes do Windows > o Microsoft Defender Antivírus > Exclusões.**

4. Clique duas vezes **em Exclusões de Processo** e adicione as exclusões:

    1. De definir a opção como **Habilitado**.
    2. Na seção **Opções,** clique em **Mostrar...**.
    3. Insira cada processo em sua própria linha na coluna **Nome do** valor. Consulte a tabela de exemplo para os diferentes tipos de exclusões de processo.  Insira **0** na coluna **Valor** para todos os processos.

5. Clique em **OK**.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar cmdlets do PowerShell para excluir arquivos que foram abertos por processos especificados de verificações

Usar o PowerShell para adicionar ou remover exclusões para arquivos que foram abertos por processos requer o uso de uma combinação de três cmdlets com o `-ExclusionProcess` parâmetro. Os cmdlets estão todos no módulo [Defender](/powershell/module/defender/).

O formato dos cmdlets é:

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

Os seguintes são permitidos como \<cmdlet> :

|Ação de configuração | Cmdlet do PowerShell |
|---|---|
|Criar ou substituir a lista | `Set-MpPreference` |
|Adicionar à lista | `Add-MpPreference` |
|Remover itens da lista | `Remove-MpPreference` |

>[!IMPORTANT]
>Se você tiver criado uma lista, com ou , usando o cmdlet novamente substituirá `Set-MpPreference` `Add-MpPreference` a lista `Set-MpPreference` existente.

Por exemplo, o trecho de código a seguir faria com que as verificações do Microsoft Defender AV excluisse qualquer arquivo aberto pelo processo especificado:

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

Para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus, consulte Gerenciar antivírus com cmdlets do PowerShell e [cmdlets do Microsoft Defender Antivírus.](/powershell/module/defender)

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Use a Instrução de Gerenciamento do Windows (WMI) para excluir arquivos que foram abertos por processos especificados de verificações

Use os [ **métodos Definir,** **Adicionar** e **Remover** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ExclusionProcess
```

O uso de **Set,** **Add** e **Remove é** análogo a suas contrapartes no PowerShell: , `Set-MpPreference` e `Add-MpPreference` `Remove-MpPreference` .

Para obter mais informações e parâmetros permitidos,  [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>Usar o aplicativo segurança do Windows para excluir arquivos que foram abertos por processos especificados de verificações

Consulte [Adicionar exclusões no aplicativo segurança do Windows](microsoft-defender-security-center-antivirus.md) para obter instruções.

## <a name="use-wildcards-in-the-process-exclusion-list"></a>Usar caracteres curinga na lista de exclusão de processos

O uso de caracteres curinga na lista de exclusão de processos é diferente de seu uso em outras listas de exclusão.

Em particular, você não pode usar o caractere curinga do ponto de interrogação ( ) e o caractere curinga do asterisco ( ) só pode ser usado no final de um `?` `*` caminho completo. Você ainda pode usar variáveis de ambiente (como ) como curingas ao definir itens na lista de exclusão `%ALLUSERSPROFILE%` de processo.

A tabela a seguir descreve como os curingas podem ser usados na lista de exclusão de processos:

|Curinga | Exemplo de uso | Exemplo corresponde |
|:---|:---|:---|
|`*` (asterisco) <br/><br/> Substitui qualquer número de caracteres | `C:\MyData\*` | Qualquer arquivo aberto por `C:\MyData\file.exe` |
|Variáveis de ambiente <br/><br/> A variável definida é preenchida como um caminho quando a exclusão é avaliada | `%ALLUSERSPROFILE%\CustomLogFiles\file.exe` | Qualquer arquivo aberto por `C:\ProgramData\CustomLogFiles\file.exe` |

## <a name="review-the-list-of-exclusions"></a>Revisar a lista de exclusões

Você pode recuperar os itens na lista de exclusão com MpCmdRun, PowerShell, [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings), [Intune](/intune/device-restrictions-configure)ou o [aplicativo de Segurança do Windows](microsoft-defender-security-center-antivirus.md).

Se você usar o PowerShell, poderá recuperar a lista de duas maneiras:

- Recupere o status de todas as preferências do Microsoft Defender Antivírus. Cada uma das listas será exibida em linhas separadas, mas os itens dentro de cada lista serão combinados na mesma linha.
- Escreva o status de todas as preferências em uma variável e use essa variável para chamar apenas a lista específica em que você está interessado. Cada uso é `Add-MpPreference` gravado em uma nova linha.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Validar a lista de exclusão usando MpCmdRun

Para verificar exclusões com a ferramenta [de linha de ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)comando mpcmdrun.exe, use o seguinte comando:

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> Verificar exclusões com MpCmdRun requer o Microsoft Defender Antivírus CAMP versão 4.18.1812.3 (lançado em dezembro de 2018) ou posterior.


### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Revise a lista de exclusões juntamente com todas as outras preferências do Microsoft Defender Antivírus usando o PowerShell

Use o seguinte cmdlet:

```PowerShell
Get-MpPreference
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Recuperar uma lista de exclusões específica usando o PowerShell

Use o seguinte trecho de código (insira cada linha como um comando separado); substitua **WDAVprefs** por qualquer rótulo que você deseja nomear a variável:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

Consulte [Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar [cmdlets](/powershell/module/defender) do Microsoft Defender Antivírus e do Defender para obter mais informações sobre como usar o PowerShell com o Microsoft Defender Antivírus.

## <a name="related-articles"></a>Artigos relacionados

- [Configurar e validar exclusões em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões com base no nome do arquivo, extensão e local da pasta](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar exclusões do Microsoft Defender Antivírus no Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Erros comuns a evitar ao definir exclusões](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [Personalizar, iniciar e revisar os resultados das verificações e correção do Microsoft Defender Antivírus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)