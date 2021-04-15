---
title: Configurar e validar exclusões com base em extensão, nome ou local
description: Exclua arquivos do Microsoft Defender Antivírus verifica com base em sua extensão de arquivo, nome de arquivo ou local.
keywords: exclusões, arquivos, extensão, tipo de arquivo, nome da pasta, nome do arquivo, verificações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 338dc249bcd4e092f5a2be39e3d045d094ed957a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765210"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>Configurar e validar exclusões com base na extensão de arquivo e no local da pasta

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> As exclusões do Microsoft Defender Antivírus não se aplicam a outros recursos do Microsoft Defender para Endpoint, incluindo a detecção e resposta do ponto de extremidade [(EDR),](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)regras de redução de superfície de ataque [(ASR)](/microsoft-365/security/defender-endpoint/attack-surface-reduction)e acesso controlado a pastas [.](/microsoft-365/security/defender-endpoint/controlled-folders) Os arquivos excluídos usando os métodos descritos neste artigo ainda podem disparar alertas de EDR e outras detecções. Para excluir arquivos amplamente, adicione-os aos indicadores personalizados do Microsoft Defender for [Endpoint.](/microsoft-365/security/defender-endpoint/manage-indicators)

## <a name="exclusion-lists"></a>Listas de exclusão

Você pode excluir determinados arquivos das verificações do Microsoft Defender Antivírus modificando listas de exclusão. **Geralmente, não é necessário aplicar exclusões.** O Microsoft Defender Antivírus inclui muitas exclusões automáticas com base em comportamentos conhecidos do sistema operacional e arquivos de gerenciamento típicos, como aqueles usados no gerenciamento empresarial, gerenciamento de banco de dados e outros cenários e situações empresariais.

> [!NOTE]
> As exclusões também se aplicam a detecções de Aplicativos Potencialmente Indesejados (PUA).

> [!NOTE]
> As exclusões automáticas aplicam-se somente ao Windows Server 2016 e acima. Essas exclusões não são visíveis no aplicativo segurança do Windows e no PowerShell.

Este artigo descreve como configurar listas de exclusão para os arquivos e pastas. Consulte [Recomendações para definir exclusões antes](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) de definir suas listas de exclusão.

| Exclusão | Exemplos | Lista de exclusões |
|:---|:---|:---|
|Qualquer arquivo com uma extensão específica | Todos os arquivos com a extensão especificada, em qualquer lugar no computador. <p> Sintaxe válida: `.test` e `test`  | Exclusões de extensão |
|Qualquer arquivo em uma pasta específica | Todos os arquivos na `c:\test\sample` pasta | Exclusões de arquivos e pastas |
| Um arquivo específico em uma pasta específica | Somente o `c:\sample\sample.test` arquivo | Exclusões de arquivos e pastas |
| Um processo específico | O arquivo executável `c:\test\process.exe` | Exclusões de arquivos e pastas |

As listas de exclusão têm as seguintes características:

- As exclusões de pastas se aplicam a todos os arquivos e pastas sob essa pasta, a menos que a subpasta seja um ponto de nova análise. As subpastas de ponto de repare devem ser excluídas separadamente.
- Extensões de arquivo se aplicam a qualquer nome de arquivo com a extensão definida se um caminho ou pasta não for definido.

> [!IMPORTANT]
> - O uso de caracteres curinga, como o asterisco ( ) alterará como as regras de \* exclusão são interpretadas. Consulte a [seção Usar curingas no nome](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) do arquivo e no caminho da pasta ou listas de exclusão de extensão para obter informações importantes sobre como os curingas funcionam.
> - Não é possível excluir unidades de rede mapeadas. Você deve especificar o caminho de rede real.
> - Pastas que são pontos de nova análise criados após o início do serviço Microsoft Defender Antivírus e que foram adicionadas à lista de exclusão não serão incluídas. Você deve reiniciar o serviço (reiniciando o Windows) para que novos pontos de nova análise sejam reconhecidos como um destino de exclusão válido.

Para excluir arquivos abertos por um processo específico, consulte [Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).

As exclusões se aplicam a [verificações agendadas,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)verificações [sob demanda](run-scan-microsoft-defender-antivirus.md)e proteção em [tempo real.](configure-real-time-protection-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> As alterações de lista de exclusão feitas com a Política de **Grupo** serão mostrar nas listas no aplicativo [segurança do Windows](microsoft-defender-security-center-antivirus.md).
> As alterações feitas no aplicativo de Segurança do Windows **não aparecerão** nas listas de Política de Grupo.

Por padrão, as alterações locais feitas nas listas (por usuários com privilégios de administrador, incluindo as alterações feitas com o PowerShell e o WMI) serão mescladas com as listas como definidas (e implantadas) pela Política de Grupo, Pelo Configuration Manager ou pelo Intune. As listas de Política de Grupo têm precedência quando há conflitos.

Você pode [configurar como listas de exclusões definidas local](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) e globalmente são mescladas para permitir que as alterações locais substituam as configurações de implantação gerenciada.

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>Configurar a lista de exclusões com base no nome da pasta ou extensão de arquivo

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usar o Intune para configurar exclusões de nome de arquivo, pasta ou extensão de arquivo

Confira os seguintes artigos:
- [Configurar configurações de restrição de dispositivo no Microsoft Intune](/intune/device-restrictions-configure)
- [Configurações de restrição de dispositivo do Microsoft Defender Antivírus para Windows 10 no Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>Use o Configuration Manager para configurar exclusões de nome de arquivo, pasta ou extensão de arquivo

Consulte [Como criar e implantar políticas antimalware: Configurações de](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) exclusão para obter detalhes sobre como configurar o Microsoft Endpoint Manager (branch atual).

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>Usar a Política de Grupo para configurar exclusões de pasta ou extensão de arquivo

>[!NOTE]
>Se você especificar um caminho totalmente qualificado para um arquivo, somente esse arquivo será excluído. Se uma pasta for definida na exclusão, todos os arquivos e subdireções sob essa pasta serão excluídos.

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**

3. Expanda a árvore para **componentes do Windows**  >  **Exclusões do Microsoft Defender**  >  **Antivírus.**

4. Abra a **configuração Exclusões de** Caminho para edição e adicione suas exclusões.

    1. De definir a opção como **Habilitado**.
    1. Na seção **Opções,** clique em **Mostrar**.
    1. Especifique cada pasta em sua própria linha na **coluna Nome do** valor.
    1. Se você estiver especificando um arquivo, certifique-se de inserir um caminho totalmente qualificado para o arquivo, incluindo a letra da unidade, o caminho da pasta, o nome do arquivo e a extensão. Insira **0** na coluna **Valor.**

5. Escolha **OK**.

6. Abra a **configuração Exclusões de** Extensão para edição e adicione suas exclusões.

    1. De definir a opção como **Habilitado**.
    1. Na seção **Opções,** selecione **Mostrar**.
    1. Insira cada extensão de arquivo em sua própria linha na **coluna Nome do** valor.  Insira **0** na coluna **Valor.**

7. Escolha **OK**.

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>Usar cmdlets do PowerShell para configurar exclusões de nome de arquivo, pasta ou extensão de arquivo

Usar o PowerShell para adicionar ou remover exclusões para arquivos com base na extensão, local ou nome do arquivo requer o uso de uma combinação de três cmdlets e o parâmetro de lista de exclusão apropriado. Os cmdlets estão todos no módulo [Defender](/powershell/module/defender/).

O formato dos cmdlets é o seguinte:

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

Os seguintes são permitidos como `<cmdlet>` :

| Ação de configuração | Cmdlet do PowerShell |
|:---|:---|
|Criar ou substituir a lista | `Set-MpPreference` |
|Adicionar à lista | `Add-MpPreference` |
|Remover item da lista | `Remove-MpPreference` |

Os seguintes são permitidos como `<exclusion list>` :

| Tipo de exclusão | Parâmetro PowerShell |
|:---|:---|
| Todos os arquivos com uma extensão de arquivo especificada | `-ExclusionExtension` |
| Todos os arquivos em uma pasta (incluindo arquivos em subdireções) ou um arquivo específico | `-ExclusionPath` |

> [!IMPORTANT]
> Se você tiver criado uma lista, com ou , usando o cmdlet novamente substituirá `Set-MpPreference` `Add-MpPreference` a lista `Set-MpPreference` existente.

Por exemplo, o trecho de código a seguir faria com que as verificações do Microsoft Defender Antivírus excluisse qualquer arquivo com a `.test` extensão de arquivo:

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

Para obter mais informações, [consulte Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar os [cmdlets](/powershell/module/defender/)do Microsoft Defender Antivírus e do Defender.

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>Use a Instrução de Gerenciamento do Windows (WMI) para configurar exclusões de nome de arquivo, pasta ou extensão de arquivo

Use os [ **métodos Definir,** **Adicionar** e **Remover** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
ExclusionExtension
ExclusionPath
```

O uso de **Set,** **Add** e **Remove é** análogo a suas contrapartes no PowerShell: , `Set-MpPreference` e `Add-MpPreference` `Remove-MpPreference` .

Para obter mais informações, [consulte Windows Defender APIs WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>Use o aplicativo segurança do Windows para configurar exclusões de nome de arquivo, pasta ou extensão de arquivo

Consulte [Adicionar exclusões no aplicativo segurança do Windows](microsoft-defender-security-center-antivirus.md) para obter instruções.

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>Usar caracteres curinga nas listas de exclusão de nome de arquivo e de pasta ou extensão

Você pode usar o asterisco , o ponto de interrogação ou as variáveis de ambiente (como ) como `*` `?` caracteres curinga ao definir itens na lista de exclusão de nome de arquivo ou caminho `%ALLUSERSPROFILE%` da pasta. A maneira como esses caracteres curinga são interpretados difere do uso normal em outros aplicativos e idiomas. Leia esta seção para entender suas limitações específicas.

> [!IMPORTANT]
> Há limitações principais e cenários de uso para esses caracteres curinga:
> - O uso de variáveis de ambiente é limitado a variáveis de máquina e a processos em execução como uma conta NT AUTHORITY\SYSTEM.
> - Não é possível usar um curinga no lugar de uma letra de unidade.
> - Um asterisco em uma exclusão de pasta `*` permanece no local para uma única pasta. Use várias instâncias de para indicar várias pastas `\*\` aninhadas com nomes não especificados.

A tabela a seguir descreve como os curingas podem ser usados e fornece alguns exemplos.


|Curinga  |Exemplos  |
|:---------|:---------|
|`*` (asterisco) <p> Em **inclusões** de nome de arquivo e extensão de arquivo, o asterisco substitui qualquer número de caracteres e só se aplica a arquivos na última pasta definida no argumento. <p> Em **exclusões de pastas,** o asterisco substitui uma única pasta. Use vários `*` com barras de pasta para indicar várias pastas `\` aninhadas. Depois de corresponder ao número de pastas nomeadas e com cartão curinga, todas as subpastas também são incluídas.   | `C:\MyData\*.txt` inclui `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` inclui qualquer arquivo em `C:\somepath\Archives\Data` e suas subpastas e `C:\somepath\Authorized\Data` suas subpastas <p> `C:\Serv\*\*\Backup` inclui qualquer arquivo em `C:\Serv\Primary\Denied\Backup` e suas subpastas `C:\Serv\Secondary\Allowed\Backup` e suas subpastas     |
|`?` (ponto de interrogação)  <p> Em **inclusões de nome** de arquivo e extensão de arquivo, o ponto de interrogação substitui um único caractere e só se aplica a arquivos na última pasta definida no argumento. <p> Nas **exclusões de pastas,** o ponto de interrogação substitui um único caractere em um nome de pasta. Depois de corresponder ao número de pastas nomeadas e com cartão curinga, todas as subpastas também são incluídas.   |`C:\MyData\my?.zip` inclui `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` inclui qualquer arquivo em `C:\somepath\P\Data` e suas subpastas  <p> `C:\somepath\test0?\Data` incluiria qualquer arquivo em `C:\somepath\test01\Data` e suas subpastas          |
|Variáveis de ambiente <p> A variável definida é preenchida como um caminho quando a exclusão é avaliada.          |`%ALLUSERSPROFILE%\CustomLogFiles` incluiria `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`         |
        

> [!IMPORTANT]
> Se você misturar um argumento de exclusão de arquivo com um argumento de exclusão de pasta, as regras serão paradas na combinação de argumentos de arquivo na pasta coincidente e não procurarão por combinações de arquivo em subpastas.
> Por exemplo, você pode excluir todos os arquivos que começam com "date" nas pastas `c:\data\final\marked` e usando o argumento rule `c:\data\review\marked` `c:\data\*\marked\date*` .
> Esse argumento, no entanto, não corresponderá a nenhum arquivo em subpastas em `c:\data\final\marked` ou `c:\data\review\marked` .

<a id="review"></a>

### <a name="system-environment-variables"></a>Variáveis de ambiente do sistema

A tabela a seguir lista e descreve as variáveis do ambiente de conta do sistema. 

| Esta variável de ambiente do sistema... | Redirecionamentos para isso |
|:--|:--|
| `%APPDATA%`| `C:\Users\UserName.DomainName\AppData\Roaming` |
| `%APPDATA%\Microsoft\Internet Explorer\Quick Launch` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch` |
| `%APPDATA%\Microsoft\Windows\Start Menu` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu` |
| `%APPDATA%\Microsoft\Windows\Start Menu\Programs` | `C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs` |
| `%LOCALAPPDATA%` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%ProgramData%` | `C:\ProgramData` |
| `%ProgramFiles%` | `C:\Program Files` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles%\Windows Sidebar\Gadgets` | `C:\Program Files\Windows Sidebar\Gadgets` |
| `%ProgramFiles%\Common Files` | `C:\Program Files\Common Files` |
| `%ProgramFiles(x86)%` | `C:\Program Files (x86)` |
| `%ProgramFiles(x86)%\Common Files` | `C:\Program Files (x86)\Common Files` |
| `%SystemDrive%` | `C:` |
| `%SystemDrive%\Program Files` | `C:\Program Files` |
| `%SystemDrive%\Program Files (x86)` | `C:\Program Files (x86)` |
| `%SystemDrive%\Users` | `C:\Users` |
| `%SystemDrive%\Users\Public` | `C:\Users\Public` |
| `%SystemRoot%` | `C:\Windows` |
| `%windir%` | `C:\Windows` |
| `%windir%\Fonts` | `C:\Windows\Fonts` |
| `%windir%\Resources` | `C:\Windows\Resources` |
| `%windir%\resources\0409` | `C:\Windows\resources\0409` |
| `%windir%\system32` | `C:\Windows\System32` |
| `%ALLUSERSPROFILE%` | `C:\ProgramData` |
| `%ALLUSERSPROFILE%\Application Data` | `C:\ProgramData\Application Data` |
| `%ALLUSERSPROFILE%\Documents` | `C:\ProgramData\Documents` |
| `%ALLUSERSPROFILE%\Documents\My Music\Sample Music` | `C:\ProgramData\Documents\My Music\Sample Music` |
| `%ALLUSERSPROFILE%\Documents\My Music` | `C:\ProgramData\Documents\My Music` |
| `%ALLUSERSPROFILE%\Documents\My Pictures` | `C:\ProgramData\Documents\My Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures` | `C:\ProgramData\Documents\My Pictures\Sample Pictures` |
| `%ALLUSERSPROFILE%\Documents\My Videos` | `C:\ProgramData\Documents\My Videos` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore` | `C:\ProgramData\Microsoft\Windows\DeviceMetadataStore` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer` | `C:\ProgramData\Microsoft\Windows\GameExplorer` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones` | `C:\ProgramData\Microsoft\Windows\Ringtones` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu` | `C:\ProgramData\Microsoft\Windows\Start Menu` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp` | `C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp` |
| `%ALLUSERSPROFILE%\Microsoft\Windows\Templates` | `C:\ProgramData\Microsoft\Windows\Templates` |
| `%ALLUSERSPROFILE%\Start Menu` | `C:\ProgramData\Start Menu` |
| `%ALLUSERSPROFILE%\Start Menu\Programs` | C:\ProgramData\Menu Iniciar\Programas |
| `%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools` | `C:\ProgramData\Start Menu\Programs\Administrative Tools` | 
| `%ALLUSERSPROFILE%\Templates` | `C:\ProgramData\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates` |
| `%LOCALAPPDATA%\Microsoft\Windows\History` | `C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History` |
| `%PUBLIC%` | `C:\Users\Public` |
| `%PUBLIC%\AccountPictures` | `C:\Users\Public\AccountPictures` |
| `%PUBLIC%\Desktop` | `C:\Users\Public\Desktop` |
| `%PUBLIC%\Documents` | `C:\Users\Public\Documents` |
| `%PUBLIC%\Downloads` | `C:\Users\Public\Downloads` |
| `%PUBLIC%\Music\Sample Music` | `C:\Users\Public\Music\Sample Music` |
| `%PUBLIC%\Music\Sample Playlists` | `C:\Users\Public\Music\Sample Playlists` |
| `%PUBLIC%\Pictures\Sample Pictures` | `C:\Users\Public\Pictures\Sample Pictures` |
| `%PUBLIC%\RecordedTV.library-ms` | `C:\Users\Public\RecordedTV.library-ms` |
| `%PUBLIC%\Videos` | `C:\Users\Public\Videos` |
| `%PUBLIC%\Videos\Sample Videos` | `C:\Users\Public\Videos\Sample Videos` | 
| `%USERPROFILE%` | `C:\Windows\System32\config\systemprofile` |
| `%USERPROFILE%\AppData\Local` | `C:\Windows\System32\config\systemprofile\AppData\Local` |
| `%USERPROFILE%\AppData\LocalLow` | `C:\Windows\System32\config\systemprofile\AppData\LocalLow` |
| `%USERPROFILE%\AppData\Roaming` | `C:\Windows\System32\config\systemprofile\AppData\Roaming` |


## <a name="review-the-list-of-exclusions"></a>Revisar a lista de exclusões

Você pode recuperar os itens na lista de exclusão usando um dos seguintes métodos:
- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Gerenciador de Configuração do Microsoft Endpoint](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [Aplicativo de Segurança do Windows](microsoft-defender-security-center-antivirus.md)

>[!IMPORTANT]
>As alterações de lista de exclusão feitas com a Política de **Grupo** serão mostrar nas listas no aplicativo [segurança do Windows](microsoft-defender-security-center-antivirus.md).
>
>As alterações feitas no aplicativo de Segurança do Windows **não aparecerão** nas listas de Política de Grupo.

Se você usar o PowerShell, poderá recuperar a lista de duas maneiras:

- Recupere o status de todas as preferências do Microsoft Defender Antivírus. Cada lista é exibida em linhas separadas, mas os itens em cada lista são combinados na mesma linha.
- Escreva o status de todas as preferências em uma variável e use essa variável para chamar apenas a lista específica em que você está interessado. Cada uso é `Add-MpPreference` gravado em uma nova linha.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>Validar a lista de exclusão usando MpCmdRun

Para verificar exclusões com a ferramenta [de linha de ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)comando mpcmdrun.exe, use o seguinte comando:

```DOS
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.1812.3 (Where 4.18.1812.3 is this month's MDAV "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

>[!NOTE]
>Verificar exclusões com MpCmdRun requer o Microsoft Defender Antivírus CAMP versão 4.18.1812.3 (lançado em dezembro de 2018) ou posterior.

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>Revise a lista de exclusões juntamente com todas as outras preferências do Microsoft Defender Antivírus usando o PowerShell

Use o seguinte cmdlet:

```PowerShell
Get-MpPreference
```

No exemplo a seguir, os itens contidos na `ExclusionExtension` lista são realçados:

![Saída do PowerShell para Get-MpPreference mostrando a lista de exclusão juntamente com outras preferências](images/defender/wdav-powershell-get-exclusions-all.png)

Para obter mais informações, [consulte Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar os [cmdlets](/powershell/module/defender/)do Microsoft Defender Antivírus e do Defender.

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>Recuperar uma lista de exclusões específica usando o PowerShell

Use o seguinte trecho de código (insira cada linha como um comando separado); substitua **WDAVprefs** por qualquer rótulo que você deseja nomear a variável:

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

No exemplo a seguir, a lista é dividida em novas linhas para cada uso do `Add-MpPreference` cmdlet:

![Saída do PowerShell mostrando apenas as entradas na lista de exclusão](images/defender/wdav-powershell-get-exclusions-variable.png)

Para obter mais informações, [consulte Usar cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) do PowerShell para configurar e executar os [cmdlets](/powershell/module/defender/)do Microsoft Defender Antivírus e do Defender.

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Validar listas de exclusões com o arquivo de teste EICAR

Você pode validar que suas listas de exclusão estão funcionando usando o PowerShell com `Invoke-WebRequest` o cmdlet ou a classe .NET WebClient para baixar um arquivo de teste.

No trecho a seguir do PowerShell, *substitua* test.txtpor um arquivo que esteja em conformidade com suas regras de exclusão. Por exemplo, se você excluiu a `.testing` extensão, substitua `test.txt` por `test.testing` . Se você estiver testando um caminho, certifique-se de executar o cmdlet nesse caminho.

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

Se o Microsoft Defender Antivírus relata malware, a regra não está funcionando. Se não houver nenhum relatório de malware e o arquivo baixado existir, a exclusão está funcionando. Você pode abrir o arquivo para confirmar que o conteúdo é igual ao descrito no site do arquivo de teste [EICAR.](http://www.eicar.org/86-0-Intended-use.html)

Você também pode usar o código do PowerShell a seguir, que chama a classe .NET WebClient para baixar o arquivo de teste - como com o cmdlet; substitua oc:\test.txtpor um arquivo que esteja em conformidade com a regra que você está `Invoke-WebRequest` validando: 

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

Se você não tiver acesso à Internet, poderá criar seu próprio arquivo de teste EICAR escrevendo a cadeia de caracteres EICAR em um novo arquivo de texto com o seguinte comando do PowerShell:

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

Você também pode copiar a cadeia de caracteres em um arquivo de texto em branco e tentar salvá-la com o nome do arquivo ou na pasta que você está tentando excluir.

## <a name="related-topics"></a>Tópicos relacionados

- [Configurar e validar exclusões em verificações do Microsoft Defender Antivírus](configure-exclusions-microsoft-defender-antivirus.md)
- [Configurar e validar exclusões para arquivos abertos por processos](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Configurar exclusões do Microsoft Defender Antivírus no Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Erros comuns a evitar ao definir exclusões](common-exclusion-mistakes-microsoft-defender-antivirus.md)
