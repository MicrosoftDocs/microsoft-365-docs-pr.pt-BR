---
title: Detecção e resposta do ponto de extremidade no modo de bloqueio
description: Saiba mais sobre detecção e resposta de ponto de extremidade no modo de bloqueio
keywords: Microsoft Defender para Ponto de Extremidade, mde, EDR no modo de bloqueio, bloqueio de modo passivo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 06/11/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: ae170ecf0fc0f354c9975300e5f2f7cd014b0c47
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339678"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Detecção e resposta do ponto de extremidade (EDR) no modo de bloqueio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>O que EDR no modo de bloqueio?

[A detecção e](overview-endpoint-detection-response.md) a resposta do ponto de extremidade (EDR) no modo de bloqueio fornece proteção contra artefatos mal-intencionados, mesmo quando o Microsoft Defender Antivírus está sendo executado no modo passivo. Quando ligado, EDR no modo de bloqueio bloqueia artefatos mal-intencionados ou comportamentos detectados em um dispositivo. EDR no modo de bloqueio funciona nos bastidores para correção de artefatos mal-intencionados detectados após a violação. 

EDR no modo de bloqueio também é integrado com [ameaças & Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md). A equipe de segurança da [](tvm-security-recommendation.md) sua organização receberá uma recomendação de segurança para EDR ativar o modo de bloqueio se ainda não estiver habilitado. 

:::image type="content" source="images/enable-edr-in-block-mode.png" alt-text="recomendação para ativar o EDR no modo de bloqueio":::

> [!NOTE]
> Para obter a melhor proteção, certifique-se de **[implantar o Microsoft Defender para linhas de base do Ponto de Extremidade.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>O que acontece quando algo é detectado?

Quando EDR no modo de bloqueio é ligado e um artefato mal-intencionado é detectado, o Microsoft Defender para Pontos de Extremidade bloqueia e correção desse artefato. Sua equipe de operações de segurança verá o status de detecção como **Bloqueado** ou **Impedido** no Centro de Ações [,](respond-machine-alerts.md#check-activity-details-in-action-center)listado como ações concluídas.

A imagem a seguir mostra uma instância de software indesejado que foi detectado e bloqueado EDR no modo de bloqueio:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR no modo de bloqueio detectou algo":::


## <a name="enable-edr-in-block-mode"></a>Habilitar EDR no modo de bloqueio

> [!IMPORTANT]
> Certifique-se [de que os](#requirements-for-edr-in-block-mode) requisitos sejam atendidos antes de EDR no modo de bloqueio.

1. Vá para o [portal Microsoft 365 Defender e](microsoft-defender-security-center.md) entre. 

2. Escolha **Configurações**  >  **recursos avançados**.

3. A EDR **no modo de bloqueio**.

> [!NOTE]
> EDR no modo de bloqueio só pode ser ligado no portal Microsoft 365 Defender. Não é possível usar as chaves do Registro, o Intune ou as políticas de grupo para habilitar ou desabilitar EDR no modo de bloqueio.

## <a name="requirements-for-edr-in-block-mode"></a>Requisitos para EDR no modo de bloqueio

|Requisito  |Detalhes  |
|---------|---------|
|Permissões |Função administrador global ou administrador de segurança atribuída [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Consulte [Permissões básicas](basic-permissions.md). |
|Sistema operacional     |Uma das seguintes versões: <br/>- Windows 10 (todas as versões) <br/>- Windows Server, versão 1803 ou mais recente <br/>- Windows Server 2019 <br/>- Windows Server 2016 (somente quando Microsoft Defender Antivírus está no modo ativo)     |
|Windows Registro no E5     |Windows O E5 está incluído nas seguintes assinaturas: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 com a oferta de Proteção contra Ameaças & Identidade <br/><br/>Consulte [Componentes](/microsoft-365/enterprise/microsoft-365-overview#components) [e recursos e recursos para cada plano](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).       |
|Microsoft Defender Antivírus  |Microsoft Defender Antivírus deve ser instalado e executado no modo ativo ou no modo passivo. (Você pode usar Microsoft Defender Antivírus uma solução antivírus que não seja da Microsoft.) [Confirme Microsoft Defender Antivírus está no modo ativo ou passivo](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode). |
|Proteção fornecida na nuvem |Certifique-Microsoft Defender Antivírus que a proteção entregue na nuvem está [habilitada.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender Antivírus cliente antimalware |Certifique-se de que seu cliente está atualizado. Usando o PowerShell, execute o cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. Na linha **AMProductVersion,** você deve ver **4.18.2001.10** ou superior. |
|Microsoft Defender Antivírus mecanismo |Certifique-se de que o mecanismo está atualizado. Usando o PowerShell, execute o cmdlet [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) como administrador. Na linha **AMEngineVersion,** você deve ver **1.1.16700.2** ou superior. |

> [!IMPORTANT]
> Para obter o melhor valor de proteção, certifique-se de que sua solução antivírus está configurada para receber atualizações regulares e recursos essenciais e que suas exclusões [estão configuradas](configure-exclusions-microsoft-defender-antivirus.md). EDR no modo de bloqueio respeita as exclusões definidas para Microsoft Defender Antivírus.

## <a name="frequently-asked-questions"></a>Perguntas frequentes 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Preciso ativar EDR modo de bloqueio mesmo quando tiver Microsoft Defender Antivírus em execução em dispositivos?

Recomendamos manter EDR no modo de bloqueio ativado, se Microsoft Defender Antivírus está sendo executado no modo passivo ou no modo ativo. EDR no modo de bloqueio fornece outra camada de defesa com o Microsoft Defender para Ponto de Extremidade. Ele permite que o Defender para o Ponto de Extremidade tome ações com base em detecções comportamentais pós-violação EDR detecções. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>O EDR no modo de bloqueio terá algum impacto na proteção antivírus de um usuário? 

EDR no modo de bloqueio não afeta a proteção antivírus de terceiros em execução nos dispositivos dos usuários. EDR no modo de bloqueio funciona se a solução antivírus primária falhar em algo ou se houver uma detecção pós-violação. EDR no modo de bloqueio funciona exatamente como Microsoft Defender Antivírus no modo passivo, exceto também bloqueia e remedia artefatos mal-intencionados ou comportamentos detectados.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Por que preciso manter a Microsoft Defender Antivírus atualizada? 

Como Microsoft Defender Antivírus detecta e correção de itens mal-intencionados, é importante mantê-los atualizados. Para EDR no modo de bloqueio seja eficaz, ele usa os modelos de aprendizado de dispositivo mais recentes, detecções comportamentais e heurísticas. A [pilha de recursos do Defender para Ponto](microsoft-defender-endpoint.md) de Extremidade funciona de maneira integrada. Para obter o melhor valor de proteção, você deve Microsoft Defender Antivírus atualizado. Consulte [Gerenciar Microsoft Defender Antivírus atualizações e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md). 

### <a name="why-do-we-need-cloud-protection-on"></a>Por que precisamos de proteção na nuvem? 

A proteção em nuvem é necessária para ativar o recurso no dispositivo. A proteção em nuvem permite que o [Defender para o Ponto](microsoft-defender-endpoint.md) de Extremidade entregue a mais recente e maior proteção com base em nossa amplitude e profundidade de inteligência de segurança, juntamente com modelos de aprendizado comportamental e de dispositivo.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Como definir Microsoft Defender Antivírus modo passivo?

Dependendo dos sistemas operacionais, quando os dispositivos que estão executando uma solução antimalware/antivírus não microsoft são integradas ao Defender para Ponto de Extremidade, o Microsoft Defender Antivírus pode entrar no modo passivo automaticamente. Para obter mais informações, [consulte How Microsoft Defender Antivírus affects Defender for Endpoint functionality](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality). 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Como confirmo se Microsoft Defender Antivírus está no modo ativo ou passivo?

Para confirmar se o Microsoft Defender Antivírus está sendo executado no modo ativo ou passivo, você pode usar o Prompt de Comando ou o PowerShell em um dispositivo que executa Windows.


|Método  |Procedimento  |
|---------|---------|
| Windows PowerShell     | 1. Selecione o menu Iniciar, comece a digitar e abra Windows PowerShell `PowerShell` nos resultados. <p>2. Digite `Get-MpComputerStatus` . <p>3. Na lista de resultados, na linha **AMRunningMode,** procure um dos seguintes valores: <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>Para saber mais, confira [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).        |
|Prompt de comando     | 1. Selecione o menu Iniciar, comece a digitar e abra Windows Prompt de `Command Prompt` Comando nos resultados. <p>2. Digite `sc query windefend` . <p>3. Na lista de resultados, na linha **STATE,** confirme se o serviço está em execução.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Quanto tempo leva para que EDR no modo de bloqueio seja desabilitado?

Se você optou por desabilitar EDR no modo de bloqueio, pode levar até 30 minutos para o sistema desabilitar esse recurso.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>O EDR no modo de bloqueio é suportado em Windows Server 2016?

Se Microsoft Defender Antivírus estiver sendo executado no modo ativo ou passivo, EDR no modo de bloqueio será suportado das seguintes versões do Windows:

- Windows 10 (todas as versões)
- Windows Servidor, versão 1803 ou mais recente 
- Windows Server 2019 

Se Windows Server 2016 tiver Microsoft Defender Antivírus em execução no modo ativo e o ponto de extremidade estiver integrado ao Defender para Ponto de Extremidade, EDR no modo de bloqueio será tecnicamente suportado. No entanto, EDR no modo de bloqueio destina-se a ser proteção extra quando Microsoft Defender Antivírus não é a solução antivírus principal em um ponto de extremidade. Nesses casos, o Microsoft Defender Antivírus é executado no modo passivo. Atualmente, a execução Microsoft Defender Antivírus no modo passivo não é suportada em Windows Server 2016. Para saber mais, confira Microsoft Defender Antivírus soluções de [antivírus/antimalware](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)que não são da Microsoft.

## <a name="see-also"></a>Confira também

- [Blog Community de tecnologia: apresentando EDR no modo de bloqueio: Interrompendo ataques em suas faixas](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Bloqueio e contenção comportamental](behavioral-blocking-containment.md)

