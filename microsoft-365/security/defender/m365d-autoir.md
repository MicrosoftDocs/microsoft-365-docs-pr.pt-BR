---
title: Investigação e resposta automatizadas no Microsoft 365 Defender
description: Obter uma visão geral dos recursos automatizados de investigação e resposta, também chamados de auto-recuperação, Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-healing
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 976a79be98efcbb5d7fd3749ddb0cdb282b1e3e3
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274563"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigação e resposta automatizadas no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Se sua organização estiver usando [o Microsoft 365 Defender](microsoft-365-defender.md), sua equipe de operações de segurança receberá um alerta dentro do centro de segurança Microsoft 365 sempre que uma atividade ou artefato mal-intencionado ou suspeito for detectado. Devido ao fluxo aparentemente interminável de ameaças que podem entrar, as equipes de segurança geralmente enfrentam o desafio de lidar com o alto volume de alertas. Felizmente, o Microsoft 365 Defender inclui recursos automatizados de investigação e resposta (AIR) que podem ajudar sua equipe de operações de segurança a lidar com ameaças de forma mais eficiente e eficaz.

Este artigo fornece uma visão geral do AIR e inclui links para as próximas etapas e recursos adicionais.

> [!TIP]
> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Como funciona a investigação automatizada e a auto-recuperação

À medida que os alertas de segurança são disparados, a equipe de operações de segurança deve procurar esses alertas e tomar medidas para proteger sua organização. Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento. As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas. Recursos automatizados de investigação e resposta, com auto-recuperação, Microsoft 365 o Defender pode ajudar.

Assista ao vídeo a seguir para ver como funciona a auto-recuperação: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

No Microsoft 365 Defender, a investigação e a resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, emails & conteúdo e identidades.
 
> [!TIP]
> Este artigo descreve como funciona a investigação e a resposta automatizadas. Para configurar esses recursos, consulte [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Seu próprio analista virtual

Imagine ter um analista virtual em sua equipe de operações de segurança de Camada 1 ou Camada 2. O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças. O analista virtual poderia trabalhar 24x7, com capacidade ilimitada, e assumir uma carga significativa de investigações e correção de ameaças. Esse analista virtual poderia reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outras ameaças importantes ou projetos estratégicos. Se esse cenário parece com a ficção científica, não é! Esse analista virtual faz parte do seu pacote Microsoft 365 Defender, e seu nome é investigação e resposta *automatizadas.*

Os recursos automatizados de investigação e resposta permitem que sua equipe de operações de segurança aumente drasticamente a capacidade da sua organização de lidar com alertas e incidentes de segurança. Com a investigação e a resposta automatizadas, você pode reduzir o custo de lidar com atividades de investigação e resposta e obter o máximo de seu pacote de proteção contra ameaças. Os recursos automatizados de investigação e resposta ajudam sua equipe de operações de segurança:

1. Determinando se uma ameaça requer ação.
2. Tomar (ou recomendar) quaisquer ações de correção necessárias.
3. Determinando se e quais outras investigações devem ocorrer.
4. Repetir o processo conforme necessário para outros alertas.

## <a name="the-automated-investigation-process"></a>O processo de investigação automatizada

Um alerta cria um incidente, que pode iniciar uma investigação automatizada. A investigação automatizada resulta em um veredito para cada prova. Os vereditos podem ser:
- *Mal-intencionado*
- *Suspeito* 
- *Nenhuma ameaça encontrada* 

Ações de correção para entidades mal-intencionadas ou suspeitas são identificadas. Exemplos de ações de correção incluem:

- Enviando um arquivo para quarentena
- Interromper um processo
- Isolando um dispositivo
- Bloqueando uma URL 
- Outras ações

Para obter mais informações, consulte [Ações de correção no Microsoft 365 Defender](m365d-remediation-actions.md).

Dependendo de como [os](m365d-configure-auto-investigation-response.md) recursos automatizados de investigação e resposta são configurados para sua organização, as ações de correção são tomadas automaticamente ou somente após a aprovação pela sua equipe de operações de segurança. Todas as ações, pendentes ou concluídas, estão listadas no [Centro de Ações](m365d-action-center.md).

Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída. Se uma entidade afetada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade e o processo de investigação se repetirá. 

No Microsoft 365 Defender, cada investigação automatizada correlaciona sinais no Microsoft Defender for Identity, no Microsoft Defender para Ponto de Extremidade e no Microsoft Defender para Office 365, conforme resumido na tabela a seguir: 

|Entidades |Serviços de proteção contra ameaças  |
|:---------|:---------|
|Dispositivos (também chamados de pontos de extremidade ou máquinas) |[Defender para Ponto de Extremidade](../defender-endpoint/automated-investigations.md) |      
|Usuários locais do Active Directory, comportamento da entidade e atividades     |[Microsoft Defender para Identidade](/azure-advanced-threat-protection/what-is-atp) |      
|Conteúdo de email (mensagens de email que podem conter arquivos e URLs)     |[Defender para Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> Nem todos os alertas disparam uma investigação automatizada, e nem todas as investigações resulta em ações de correção automatizadas. Depende de como a investigação e a resposta automatizadas são configuradas para sua organização. Consulte [Configurar recursos automatizados de investigação e resposta.](m365d-configure-auto-investigation-response.md)

## <a name="viewing-a-list-of-investigations"></a>Exibindo uma lista de investigações

Para exibir investigações, vá para a **página Incidentes.** Selecione um incidente e selecione a guia **Investigações.** Para saber mais, confira [Detalhes e resultados de uma investigação automatizada.](m365d-autoir-results.md)


## <a name="next-steps"></a>Próximas etapas

- [Consulte os pré-requisitos para investigação e resposta automatizadas](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurar investigação e resposta automatizadas para sua organização](m365d-configure-auto-investigation-response.md)
- [Saiba mais sobre a Central de Ações](m365d-action-center.md)
