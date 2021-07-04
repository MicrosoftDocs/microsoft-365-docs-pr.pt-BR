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
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: efeb49b2741bdc45f7924032c2deb8a27458ca29
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289410"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>Configurar e gerenciar Microsoft Defender Antivírus com a mpcmdrun.exe de linha de comando

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Você pode executar várias funções no Microsoft Defender Antivírus usando a ferramenta de linha de **comando dedicadampcmdrun.exe**. Esse utilitário é útil quando você deseja automatizar Microsoft Defender Antivírus tarefas. Você pode encontrar o utilitário em `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Execute-o de um prompt de comando.

> [!TIP]
> Talvez seja necessário abrir uma versão de nível de administrador do prompt de comando. Ao pesquisar o **Prompt de Comando** no menu Iniciar, escolha Executar como **administrador**. Se você estiver executando uma versão atualizada da Plataforma do Microsoft Defender, execute `MpCmdRun` a partir do seguinte local: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` . Para obter mais informações sobre a plataforma antimalware, [consulte Microsoft Defender Antivírus atualizações e linhas de base.](manage-updates-baselines-microsoft-defender-antivirus.md)

O utilitário MpCmdRun usa a seguinte sintaxe:

```console
MpCmdRun.exe [command] [-options]
```

Veja um exemplo:

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

No nosso exemplo, o utilitário MpCmdRun inicia uma verificação antivírus completa no dispositivo.

## <a name="commands"></a>Comandos

| Comando  | Descrição   |
|:----|:----|
| `-?` **ou** `-h`   | Exibe todas as opções disponíveis para a ferramenta MpCmdRun |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | Verifica se há software mal-intencionado. Os valores **para ScanType** são:<p>**0** Padrão, de acordo com sua configuração<p>**1** Verificação rápida<p>**2** Verificação completa<p>**3** Verificação personalizada de arquivo e diretório.<p>CpuThrottling é executado de acordo com as configurações de política |
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

A tabela a seguir lista erros comuns que podem ocorrer ao usar a ferramenta MpCmdRun.

|Mensagem de erro | Possível motivo |
|:----|:----|
| **Falha em ValidateMapsConnection (800106BA)** **ou 0x800106BA** | O Microsoft Defender Antivírus está desabilitado. Habilita o serviço e tente novamente. Se você precisar de ajuda para reabilitar Microsoft Defender Antivírus, consulte [Reinstalar/habilitar](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)Microsoft Defender Antivírus em seus pontos de extremidade.<p> **DICA**: no Windows 10 1909 ou mais antigo, e Windows Server 2019 ou mais antigo, o serviço era anteriormente *chamado Windows Defender Antivírus*. |
| **0x80070667** | Você está executando o comando de um computador que Windows 10 versão 1607 ou mais antiga, ou Windows Server 2016 `-ValidateMapsConnection` ou mais antigo. Execute o comando de um computador Windows 10 versão 1703 ou mais recente ou Windows Server 2019 ou mais recente.|
| **MpCmdRun não é reconhecido como um comando interno ou externo, programa operável ou arquivo em lotes.** | A ferramenta deve ser executado de um ou (onde pode ser diferente, pois as atualizações da plataforma são `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` mensais, exceto para março)|
| **ValidateMapsConnection falhou ao estabelecer uma conexão com MAPS (hr=80070005 httpcode=450)** | O comando foi tentado usando privilégios insuficientes. Use o prompt de comando (cmd.exe) como administrador.|
| **ValidateMapsConnection falhou ao estabelecer uma conexão com o MAPS (hr=80070006 httpcode=451)** | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| **ValidateMapsConnection falhou ao estabelecer uma conexão com o MAPS (hr=80004005 httpcode=450)** | Possíveis problemas relacionados à rede, como problemas de resolução de nomes|
| **ValidateMapsConnection falhou ao estabelecer uma conexão com MAPS (hr=0x80508015** | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| **ValidateMapsConnection falhou ao estabelecer uma conexão com o MAPS (hr=800722F0D** | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |
| **ValidateMapsConnection falhou ao estabelecer uma conexão com o MAPS (hr=80072EE7 httpcode=451)** | O firewall está bloqueando a conexão ou realizando a inspeção SSL. |

## <a name="see-also"></a>Confira também

- [Configurar recursos do Microsoft Defender Antivírus](configure-microsoft-defender-antivirus-features.md)
- [Configurar e validar as conexões de rede do Microsoft Defender Antivírus](configure-network-connections-microsoft-defender-antivirus.md)
- [Tópicos de referência para ferramentas de gerenciamento e configuração](configuration-management-reference-microsoft-defender-antivirus.md)
