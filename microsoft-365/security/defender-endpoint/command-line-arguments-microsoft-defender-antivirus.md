---
title: Usar a linha de comando para gerenciar o Microsoft Defender Antivírus
description: Execute as verificações do Microsoft Defender Antivírus e configure a proteção de última geração com um utilitário de linha de comando dedicado.
keywords: executar a verificação do Windows Defender, executar a verificação antivírus da linha de comando, executar a verificação do Windows Defender da linha de comando, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 1b357f7c1e02211f3949383a380666cb7444f814
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764622"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configurar e gerenciar o Microsoft Defender Antivírus com a mpcmdrun.exe de linha de comando

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode executar várias funções do Microsoft Defender Antivírus com a ferramenta de linha de **comando dedicadampcmdrun.exe**. Esse utilitário é útil quando você deseja automatizar o uso do Microsoft Defender Antivírus. Você pode encontrar o utilitário em `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Você deve executar a partir de um prompt de comando.

> [!NOTE]
> Talvez seja necessário abrir uma versão de nível de administrador do prompt de comando. Ao pesquisar o **Prompt de Comando no** menu Iniciar, escolha Executar como **administrador**.
> Se você estiver executando uma versão atualizada da Plataforma do Microsoft Defender, execute `**MpCmdRun**` a partir do seguinte local: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` .

O utilitário tem os seguintes comandos:

```console
MpCmdRun.exe [command] [-options]
```
Exemplo:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Comando  | Descrição   |
|:----|:----|
| `-?`**ou**`-h`   | Exibe todas as opções disponíveis para esta ferramenta |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Verifica se há software mal-intencionado. Os valores **para ScanType** são: **0** Padrão, de acordo com sua configuração, **-1** Verificação rápida, **-2** Verificação completa, **-3** Verificação personalizada de arquivo e diretório.  CpuThrottling irá honrar a throttling de CPU configurada da política |
| `-Trace [-Grouping #] [-Level #]` | Inicia o rastreamento de diagnóstico |
| `-GetFiles [-SupportLogLocation <path>]` | Coleta informações de suporte. Consulte '[coletando dados de diagnóstico](collect-diagnostic-data.md)'  |
| `-GetFilesDiagTrack`  | O mesmo que `-GetFiles` , mas saídas para a pasta DiagTrack temporária |
| `-RemoveDefinitions [-All]` | Restaura a inteligência de segurança instalada para uma cópia de backup anterior ou para o conjunto padrão original |
| `-RemoveDefinitions [-DynamicSignatures]` | Remove apenas a inteligência de segurança baixada dinamicamente |
| `-RemoveDefinitions [-Engine]` | Restaura o mecanismo instalado anteriormente |
| `-SignatureUpdate [-UNC \| -MMPC]` | Verifica se há novas atualizações de inteligência de segurança |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | Restaura ou lista itens em quarentena |
| `-AddDynamicSignature [-Path]` | Carrega inteligência de segurança dinâmica |
| `-ListAllDynamicSignatures` | Lista a inteligência de segurança dinâmica carregada |
| `-RemoveDynamicSignature [-SignatureSetID]` | Remove a inteligência de segurança dinâmica |
| `-CheckExclusion -path <path>` | Verifica se um caminho é excluído |
| `-ValidateMapsConnection` | Verifica se sua rede pode se comunicar com o serviço de nuvem do Microsoft Defender Antivírus. Esse comando funcionará apenas no Windows 10, versão 1703 ou superior.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Erros comuns na execução de comandos por mpcmdrun.exe 

|Mensagem de erro | Possível motivo
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | O serviço Microsoft Defender Antivírus está desabilitado. Habilita o serviço e tente novamente. <br>   **Observação:**  No Windows 10 1909 ou mais antigo, e no Windows Server 2019 ou mais antigo, o serviço era chamado de serviço "Windows Defender Antivírus".|
| `0x80070667` | Você está executando o comando de um computador que é `-ValidateMapsConnection` o Windows 10 versão 1607 ou mais antiga, ou do Windows Server 2016 ou mais antigo. Execute o comando de um computador que seja o Windows 10 versão 1703 ou mais recente, ou do Windows Server 2019 ou mais recente.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | A ferramenta precisa ser executado de: ou (onde pode ser diferente, já que as atualizações da plataforma são `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` mensais, exceto para março)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Não há privilégios suficientes. Use o prompt de comando (cmd.exe) como administrador.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Possíveis problemas relacionados à rede, como problemas de resolução de nomes|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |

## <a name="see-also"></a>Confira também

- [Configurar recursos do Microsoft Defender Antivírus](configure-microsoft-defender-antivirus-features.md)
- [Gerenciar o Microsoft Defender Antivírus em sua empresa](configuration-management-reference-microsoft-defender-antivirus.md)
- [Tópicos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivírus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)