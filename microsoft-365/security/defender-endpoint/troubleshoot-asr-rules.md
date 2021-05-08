---
title: Relatar e solucionar problemas do Microsoft Defender para Regras ASR do Ponto de Extremidade
description: Este tópico descreve como relatar e solucionar problemas do Microsoft Defender for Endpoint ASR Rules
keywords: Regras de redução de superfície de ataque, asr, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, microsoft defender para ponto de extremidade
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245979"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>Relatar e solucionar problemas do Microsoft Defender para regras ASR atp

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

O Microsoft 365 de segurança é a nova interface para monitorar e gerenciar a segurança em suas identidades, dados, dispositivos, aplicativos e infraestrutura da Microsoft. Aqui você pode exibir facilmente a integridade de segurança da sua organização, configurar dispositivos, usuários e aplicativos e exibir alertas para atividades suspeitas. O centro de segurança do Microsoft 365 destina-se a administradores e equipes de operações de segurança para gerenciar e proteger melhor sua organização. Visite o Microsoft 365 de segurança em https://security.microsoft.com .
No Microsoft 365 de segurança, oferecemos uma olhada completa na configuração e eventos atuais das regras ASR em sua propriedade. Observe que seus dispositivos devem estar conectados ao serviço Microsoft Defender for Endpoint para que esses relatórios sejam preenchidos.
Aqui está uma captura de tela do centro de segurança Microsoft 365 (em **Report**  >  **Devices Attack** surface  >  **reduction**). No nível do dispositivo, selecione **Configuração** no painel Regras de redução de **superfície de** ataque. A tela a seguir é exibida, onde você pode selecionar um dispositivo específico e verificar sua configuração de regra ASR individual.

:::image type="content" source="images/asrrulesnew.png" alt-text="Tela de regras do ASR":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender para Ponto de Extremidade – Busca avançada

Um dos recursos mais avançados do Microsoft Defender para Ponto de Extremidade é a busca avançada. Se você não estiver familiarizado com a busca avançada, consulte [proativamente a busca de](advanced-hunting-overview.md)ameaças com a busca avançada.

A busca avançada é uma ferramenta de busca de ameaças baseada em consulta (Kusto Query Language) que permite explorar até 30 dias dos dados capturados (brutos), que a Detecção e Resposta do Ponto de Extremidade do MDE (EDR) coleta de todos os seus máquinas. Por meio da busca avançada, você pode inspecionar proativamente eventos para localizar indicadores e entidades interessantes. O acesso flexível aos dados ajuda a busca não restrita por ameaças conhecidas e potenciais.

Por meio da busca avançada, é possível extrair informações de regras ASR, criar relatórios e obter informações detalhadas sobre o contexto de uma determinada auditoria de regra ASR ou um evento de bloqueio.

Os eventos de regras ASR estão disponíveis para consulta na tabela DeviceEvents na seção de busca avançada do Central de Segurança do Microsoft Defender. Por exemplo, uma consulta simples como a abaixo pode relatar todos os eventos que têm regras ASR como fonte de dados, nos últimos 30 dias, e as resumirá pela contagem ActionType, que, nesse caso, será o nome de código real da regra ASR.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Consulta de busca avançada":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="tela de busca avançada":::

Com a busca avançada, você pode moldar as consultas ao seu gosto, para que você possa ver o que está acontecendo, independentemente de você querer identificar algo em uma máquina individual ou deseja extrair informações de todo o seu ambiente.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Linha do tempo do computador do Microsoft Defender para Endpoint

Uma alternativa à busca avançada, mas com um escopo mais estreito, é a linha do tempo do computador do Microsoft Defender for Endpoint. Você pode exibir todos os eventos coletados de um dispositivo, nos últimos seis meses, no Central de Segurança do Microsoft Defender, indo para a lista Máquinas, selecione um determinado computador e clique na guia Linha do Tempo.

A imagem abaixo é uma captura de tela da exibição Linha do Tempo desses eventos em um determinado ponto de extremidade.  Nesta exibição, você pode filtrar a lista de eventos com base em qualquer um dos Grupos de Eventos no painel direito. Você também pode habilitar ou desabilitar eventos Sinalizados e Detalhados durante a exibição de alertas e rolagem pela linha do tempo histórica.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Linha do tempo do Centro de Segurança do Microsoft Defender":::

## <a name="how-to-troubleshoot-asr-rules"></a>Como solucionar problemas de regras ASR?

A primeira e mais imediata maneira é verificar localmente, em um dispositivo Windows, quais regras ASR estão habilitadas (e sua configuração) usando os cmdlets do PowerShell.

Aqui estão algumas outras fontes de informações que Windows, para solucionar o impacto e a operação das regras ASR.

### <a name="querying-which-rules-are-active"></a>Consultando quais regras estão ativas
Uma das maneiras mais fáceis de determinar se as regras asR já estão habilitadas e, é por meio de um cmdlet do PowerShell, Get-MpPreference.
Veja um exemplo:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="obter script mppreference":::

Há várias regras ASR ativas, com ações configuradas diferentes.

Para expandir as informações acima sobre regras ASR, você pode usar as propriedades **AttackSurfaceReductionRules_Ids** e/ou **AttackSurfaceReductionRules_Actions**.

Exemplo:

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="obter exemplo de mpreferência":::

O acima mostra todas as IDs para regras ASR que têm uma configuração diferente de 0 (Não Configurado).

A próxima etapa é listar as ações reais (Bloqueio ou Auditoria) com as que cada regra está configurada. 

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="obter exemplo de mppreference2":::

### <a name="querying-blocking-and-auditing-events"></a>Eventos de bloqueio e auditoria de consulta
Os eventos de regra ASR podem ser exibidos no log Windows Defender log.

Para acessá-lo, abra Windows Visualizador de Eventos e navegue até **Aplicativos** e Serviços Logs  >  **microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operacional**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="scr do visualizador de eventos":::

## <a name="microsoft-defender-malware-protection-logs"></a>Logs de Proteção contra Malware do Microsoft Defender
Você também pode exibir eventos de regra por meio da Microsoft Defender Antivírus de linha de comando dedicada, chamada , que pode ser usada para gerenciar e configurar e automatizar tarefas, se `*mpcmdrun.exe*` necessário.

Você pode encontrar esse utilitário em *%ProgramFiles%\Windows Defender\MpCmdRun.exe*. Você deve executar a partir de um prompt de comando com privilégios elevados (ou seja, executar como Administrador).

Para gerar as informações de suporte, digite *MpCmdRun.exe -getfiles*. Após algum tempo, vários logs serão empacotados em um arquivo morto (MpSupportFiles.cab) e disponibilizados em *C:\ProgramData\Microsoft\Windows Defender\Support*.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="logs de proteção contra malware":::

Extraia esse arquivo morto e você terá muitos arquivos disponíveis para fins de solução de problemas.

Os arquivos mais relevantes são os seguinte:

- **MPOperationalEvents.txt** - Esse arquivo contém o mesmo nível de informações encontradas no Visualizador de Eventos Windows Defender log Operacional do Windows Defender.
- **MPRegistry.txt** – neste arquivo, você poderá analisar todas as configurações Windows Defender atuais, a partir do momento em que os logs de suporte foram capturados.
- **MPLog.txt** – Esse log contém informações mais detalhadas sobre todas as ações/operações do Windows Defender.
