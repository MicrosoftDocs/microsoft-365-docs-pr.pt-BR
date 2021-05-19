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
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538898"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configurar e gerenciar Microsoft Defender Antivírus com a mpcmdrun.exe de linha de comando

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode executar várias Microsoft Defender Antivírus com a ferramenta de linha de **comando dedicadampcmdrun.exe**. Esse utilitário é útil quando você deseja automatizar Microsoft Defender Antivírus uso. Você pode encontrar o utilitário em `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Você deve executar a partir de um prompt de comando.

> [!NOTE]
> Talvez seja necessário abrir uma versão de nível de administrador do prompt de comando. Ao pesquisar o **Prompt de Comando no** menu Iniciar, escolha Executar como **administrador**.
> Se você estiver executando uma versão atualizada da Plataforma do Microsoft Defender, execute `**MpCmdRun**` a partir do seguinte local: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` .
> Para obter mais informações sobre a plataforma antimalware, [consulte Microsoft Defender Antivírus atualizações e linhas de base.](manage-updates-baselines-microsoft-defender-antivirus.md)

O utilitário MpCmdRun usa a seguinte sintaxe:

```console
MpCmdRun.exe [command] [-options]
```

Veja um exemplo:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| Comando  | Descrição   |
|:----|:----|
| `-?` **ou** `-h`   | Exibe todas as opções disponíveis para esta ferramenta |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Verifica se há software mal-intencionado. Os valores **para ScanType** são:<p>**0** Padrão, de acordo com sua configuração<p>**-1** Verificação rápida<p>**-2** Verificação completa<p>**-3** Verificação personalizada de arquivo e diretório.<p>CpuThrottling irá honrar a throttling de CPU configurada da política |
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
| `-ValidateMapsConnection` | Verifica se sua rede pode se comunicar com o serviço Microsoft Defender Antivírus nuvem. Esse comando funcionará apenas Windows 10 versão 1703 ou superior.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>Erros comuns na execução de comandos por mpcmdrun.exe 

|Mensagem de erro | Possível motivo
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | O Microsoft Defender Antivírus está desabilitado. Habilita o serviço e tente novamente. <br>   **Observação:**  No Windows 10 1909 ou mais antigo, e Windows Server 2019 ou mais antigo, o serviço costumava ser chamado de serviço *Windows Defender Antivírus.*|
| `0x80070667` | Você está executando o comando de um computador que Windows 10 versão 1607 ou mais antiga, ou Windows Server 2016 `-ValidateMapsConnection` ou mais antigo. Execute o comando de um computador Windows 10 versão 1703 ou mais recente ou Windows Server 2019 ou mais recente.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | A ferramenta precisa ser executado de: ou (onde pode ser diferente, já que as atualizações da plataforma são `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` mensais, exceto para março)|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | Não há privilégios suficientes. Use o prompt de comando (cmd.exe) como administrador.|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | Possíveis problemas relacionados à rede, como problemas de resolução de nomes|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |

## <a name="see-also"></a>Confira também

- [Configurar recursos do Microsoft Defender Antivírus](configure-microsoft-defender-antivirus-features.md)
- [Gerenciar Microsoft Defender Antivírus em sua empresa](configuration-management-reference-microsoft-defender-antivirus.md)
- [Tópicos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)