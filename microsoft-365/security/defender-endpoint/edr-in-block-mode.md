---
title: Detecção e resposta do ponto de extremidade no modo de bloqueio
description: Saiba mais sobre a detecção e a resposta do ponto de extremidade no modo de bloqueio
keywords: Microsoft Defender ATP, EDR no modo de bloqueio, bloqueio de modo passivo
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
ms.date: 01/26/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 7bee6c99d2c1c5ad3cec8f2e317b729a0a4e1f8b
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379473"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>Detecção e resposta do ponto de extremidade (EDR) no modo de bloqueio

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>O que é EDR no modo de bloqueio?

[A detecção e](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) a resposta do ponto de extremidade (EDR) no modo de bloqueio fornece proteção contra artefatos mal-intencionados, mesmo quando o Microsoft Defender Antivírus está em execução no modo passivo. Quando ligado, o EDR no modo de bloqueio bloqueia artefatos mal-intencionados ou comportamentos detectados em um dispositivo. A EDR no modo de bloqueio funciona nos bastidores para correção de artefatos mal-intencionados detectados após a violação. 

A EDR no modo de bloqueio também é integrada ao gerenciamento [de & de vulnerabilidades.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) A equipe de segurança da sua organização receberá uma recomendação [de](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation) segurança para ativar o EDR no modo de bloqueio se ainda não estiver habilitado. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="recomendação para ativar o EDR no modo de bloqueio":::

> [!NOTE]
> Para obter a melhor proteção, certifique-se de **[implantar o Microsoft Defender para linhas de base do Ponto de Extremidade.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)**

## <a name="what-happens-when-something-is-detected"></a>O que acontece quando algo é detectado?

Quando o EDR no modo de bloqueio é ligado e um artefato mal-intencionado é detectado, o Microsoft Defender para Ponto de Extremidade bloqueia e correção desse artefato. Você verá o status de detecção como **Bloqueado** ou **Impedido como** ações concluídas no Centro [de Ações.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#check-activity-details-in-action-center)

A imagem a seguir mostra uma instância de software indesejado que foi detectado e bloqueado por meio de EDR no modo de bloqueio:

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR no modo de bloqueio detectou algo":::


## <a name="enable-edr-in-block-mode"></a>Habilitar eDR no modo de bloqueio

> [!IMPORTANT]
> Certifique-se [de que os requisitos](#requirements-for-edr-in-block-mode) sejam atendidos antes de ligar o EDR no modo de bloqueio.

1. Vá para o Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre. 

2. Escolha **Configurações**  >  **Recursos avançados**.

3. Ativar **a EDR no modo de bloqueio**.

> [!NOTE]
> O EDR no modo de bloqueio só pode ser ligado no Centro de Segurança do Microsoft Defender. Não é possível usar as chaves do Registro, o Intune ou as políticas de grupo para habilitar ou desabilitar a EDR no modo de bloqueio.

## <a name="requirements-for-edr-in-block-mode"></a>Requisitos para EDR no modo de bloqueio

|Requisito  |Detalhes  |
|---------|---------|
|Permissões |Função administrador global ou administrador de segurança atribuída no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal). Consulte [Permissões básicas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/basic-permissions). |
|Sistema operacional     |Uma das seguintes versões: <br/>- Windows 10 (todas as versões) <br/>- Windows Server, versão 1803 ou mais recente <br/>- Windows Server 2019         |
|Registro do Windows E5     |O Windows E5 está incluído nas seguintes assinaturas: <br/>- Microsoft 365 E5 <br/>– Microsoft 365 E3 juntamente com a oferta de Proteção contra Ameaças & Identidade <br/><br/>Consulte [Componentes](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview?view=o365-worldwide&preserve-view=true#components) [e recursos e recursos para cada plano](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).       |
|Microsoft Defender Antivírus  |O Microsoft Defender Antivírus deve ser instalado e executado no modo ativo ou no modo passivo. (Você pode usar o Microsoft Defender Antivírus juntamente com uma solução antivírus não Microsoft.) [Confirme se o Microsoft Defender Antivírus está no modo ativo ou passivo.](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|Proteção entregue na nuvem |Certifique-se de que o Microsoft Defender Antivírus está configurado para que a proteção [entregue na nuvem seja habilitada.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) |
|Cliente antimalware do Microsoft Defender Antivírus |Certifique-se de que seu cliente está atualizado. Usando o PowerShell, execute o cmdlet [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) como administrador. Na linha **AMProductVersion,** você deve ver **4.18.2001.10** ou superior. |
|Mecanismo do Microsoft Defender Antivírus |Certifique-se de que o mecanismo está atualizado. Usando o PowerShell, execute o cmdlet [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus?view=win10-ps&preserve-view=true) como administrador. Na linha **AMEngineVersion,** você deve ver **1.1.16700.2** ou superior. |

> [!IMPORTANT]
> Para obter o melhor valor de proteção, certifique-se de que sua solução antivírus está configurada para receber atualizações regulares e recursos essenciais e que suas exclusões [estão configuradas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus). A EDR no modo de bloqueio respeita as exclusões definidas para o Microsoft Defender Antivírus.

## <a name="frequently-asked-questions"></a>Perguntas frequentes 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>Preciso ativar o EDR no modo de bloqueio mesmo quando tenho o Microsoft Defender Antivírus em execução em dispositivos?

Recomendamos manter o EDR no modo de bloqueio ativado, se o Microsoft Defender Antivírus está em execução no modo passivo ou no modo ativo. A EDR no modo de bloqueio fornece outra camada de defesa com o Microsoft Defender para Ponto de Extremidade. Ele permite que o Defender para o Ponto de Extremidade tome ações com base em detecções comportamentais de EDR pós-violação. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>A EDR no modo de bloqueio terá algum impacto na proteção antivírus de um usuário? 

A EDR no modo de bloqueio não afeta a proteção antivírus de terceiros em execução nos dispositivos dos usuários. A EDR no modo de bloqueio funciona se a solução antivírus primária falhar em algo ou se houver uma detecção pós-violação. A EDR no modo de bloqueio funciona da maneira como o [Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility#functionality-and-features-available-in-each-state)no modo passivo , exceto também bloqueia e correção de artefatos mal-intencionados ou comportamentos detectados. 

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>Por que preciso manter o Microsoft Defender Antivírus atualizado? 

Como o Microsoft Defender Antivírus detecta e correção de itens mal-intencionados, é importante mantê-los atualizados. Para que a EDR no modo de bloqueio seja eficaz, ela usa os modelos de aprendizado de dispositivo mais recentes, detecções comportamentais e heurísticas. A [pilha de recursos do Defender para Ponto](https://docs.microsoft.com/windows/security/threat-protection) de Extremidade funciona de maneira integrada. Para obter o melhor valor de proteção, você deve manter o Microsoft Defender Antivírus atualizado.  

### <a name="why-do-we-need-cloud-protection-on"></a>Por que precisamos de proteção na nuvem? 

A proteção em nuvem é necessária para ativar o recurso no dispositivo. A proteção em nuvem permite que o [Defender para o Ponto](https://docs.microsoft.com/windows/security/threat-protection) de Extremidade entregue a mais recente e maior proteção com base em nossa amplitude e profundidade de inteligência de segurança, juntamente com modelos de aprendizado comportamental e de dispositivo.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>Como definir o Microsoft Defender Antivírus como modo passivo?

Consulte [Habilitar o Microsoft Defender Antivírus e confirmar se ele está no modo passivo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/switch-to-microsoft-defender-setup#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>Como confirmar se o Microsoft Defender Antivírus está no modo ativo ou passivo?

Para confirmar se o Microsoft Defender Antivírus está em execução no modo ativo ou passivo, você pode usar o Prompt de Comando ou o PowerShell em um dispositivo que executa o Windows.

#### <a name="use-powershell"></a>Usar o Windows PowerShell!

1. Selecione o menu Iniciar, comece a digitar e abra Windows PowerShell `PowerShell` nos resultados.

2. Digite `Get-MpComputerStatus`.

3. Na lista de resultados, na linha **AMRunningMode,** procure um dos seguintes valores:   
   - `Normal`
   - `Passive Mode`  
   - `SxS Passive Mode`

Para saber mais, confira [Get-MpComputerStatus](https://docs.microsoft.com/powershell/module/defender/get-mpcomputerstatus).

#### <a name="use-command-prompt"></a>Usar prompt de comando

1. Selecione o menu Iniciar, comece a digitar e abra o Prompt de Comando do `Command Prompt` Windows nos resultados.

2. Digite `sc query windefend`.

3. Na lista de resultados, na linha **STATE,** confirme se o serviço está sendo executado.

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>Quanto tempo leva para que o EDR no modo de bloqueio seja desabilitado?
Se você optou por desabilitar o EDR no modo de bloqueio, pode levar até 30 minutos para o sistema desabilitar esse recurso.

## <a name="see-also"></a>Confira também

- [Blog da Comunidade Técnica: Introdução à EDR no modo de bloqueio: Interrompendo ataques em suas faixas](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [Bloqueio comportamental e contenção](behavioral-blocking-containment.md)
- [Melhor juntos: Microsoft Defender Antivírus e Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/why-use-microsoft-antivirus)

