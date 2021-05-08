---
title: Visite o Centro de Ações para ver ações de correção
description: Use o centro de ações para exibir detalhes e resultados após uma investigação automatizada
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: e51cc1d613e6f9e7ab96653692362ed7fe239e3e
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274839"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a>Visite o Centro de Ações para ver ações de correção

Durante e após uma investigação automatizada, as ações de correção para detecções de ameaças são identificadas. Dependendo da ameaça específica e de como o [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) está configurado para sua organização, algumas ações de correção são tomadas automaticamente e outras exigem aprovação. Se você faz parte da equipe de operações de segurança da [](manage-auto-investigation.md#remediation-actions) sua organização, pode exibir ações pendentes e concluídas de correção no **Centro de Ações.** 


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a>(NEW!) Um centro de ação unificado


Temos o prazer de anunciar um novo Centro de Ações unificado ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Centro de ações no Centro de segurança do Microsoft 365":::

A tabela a seguir compara o novo centro de ações unificado com o centro de ações anterior.

|O novo centro de ações unificado  |O centro de ações anterior  |
|---------|---------|
|Lista ações pendentes e concluídas para dispositivos e emails em um único local <br/>([Microsoft Defender para Ponto de Extremidade mais](microsoft-defender-endpoint.md) Microsoft Defender para Office [365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp))|Lista ações pendentes e concluídas para dispositivos <br/> ([Microsoft Defender somente para Ponto de](microsoft-defender-endpoint.md) Extremidade)   |
|Está localizado em:<br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |Está localizado em:<br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| No centro de segurança do Microsoft 365, escolha **Centro de ações**. <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navegando até o Centro de Ações no centro de segurança do Microsoft 365"::: | No Centro de Segurança do Microsoft Defender, escolha **Centro de ações** de  >  **investigações automatizadas.** <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navegando até o Centro de Ações do Centro de Segurança do Microsoft Defender":::  |

O centro de ações unificado reúne ações de correção no Defender para Ponto de Extremidade e no Defender para Office 365. Ele define um idioma comum para todas as ações de correção e fornece uma experiência de investigação unificada. 

Você pode usar o Centro de Ações unificado se tiver permissões apropriadas e uma ou mais das seguintes assinaturas:
- [Defender para Ponto de Extremidade](microsoft-defender-endpoint.md)
- [Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> Para saber mais, confira [Requisitos](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).

## <a name="using-the-action-center"></a>Usando o Centro de Ações

Para chegar ao Centro de Ações unificado no centro de segurança do Microsoft 365 aprimorado:
1. Vá para o Centro de Segurança do Microsoft 365 ( [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, selecione **Centro de ações**. 

Ao visitar a Central de Ações, você verá duas guias: **Ações pendentes** e **Histórico**. A tabela a seguir resume o que você verá em cada guia:

|Guia  |Descrição  |
|---------|---------|
|**Pending**     | Exibe uma lista de ações que exigem atenção. Você pode aprovar ou rejeitar ações uma de cada vez ou selecionar várias ações se elas têm o mesmo tipo de ação (como arquivo **de quarentena).** <br/>**DICA**: Certifique-se de revisar e aprovar [(ou rejeitar)](manage-auto-investigation.md) ações pendentes assim que possível para que suas investigações automatizadas possam ser concluídas em tempo hábil. |
|**Histórico**     | Serve como um log de auditoria para ações que foram realizadas, como: <br/>- Ações de correção que foram tomadas como resultado de investigações automatizadas <br>- Ações de correção aprovadas pela sua equipe de operações de segurança  <br/>- Comandos executados e ações de correção que foram aplicadas durante as sessões de Resposta ao Vivo  <br/>- Ações de correção que foram tomadas pelos recursos de proteção contra ameaças no Microsoft Defender Antivírus  <p>Fornece uma maneira de desfazer determinadas ações (consulte [Desfazer ações concluídas](manage-auto-investigation.md#undo-completed-actions)).       |

Você pode personalizar, classificar, filtrar e exportar dados no Centro de Ações.

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Colunas e filtros no Centro de Ações":::

- Selecione um título de coluna para classificar itens em ordem crescente ou decrescente.
- Use o filtro de período de tempo para exibir dados do último dia, semana, 30 dias ou 6 meses.
- Escolha as colunas que você deseja exibir.
- Especifique quantos itens devem ser incluídos em cada página de dados.
- Use filtros para exibir apenas os itens que você deseja ver.
- Selecione **Exportar** para exportar resultados para um arquivo .csv. 

## <a name="next-steps"></a>Próximas etapas

- [Exibir e aprovar ações de correção](manage-auto-investigation.md)
- [Consulte o guia interativo: Investigar e correção de ameaças com o Microsoft Defender para Ponto de Extremidade](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a>Confira também

- [Endereços falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)
