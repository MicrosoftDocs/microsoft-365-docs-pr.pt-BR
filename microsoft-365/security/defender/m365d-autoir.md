---
title: Investigação e resposta automatizadas no Microsoft 365 Defender
description: Obter uma visão geral dos recursos automatizados de investigação e resposta, também chamados de auto-recuperação, no Microsoft 365 Defender
keywords: automated, investigation, alert, trigger, action, remediation, self-healing
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.openlocfilehash: be0423b0af8251347420d9e970dcfe10db0bb72b
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591918"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigação e resposta automatizadas no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Se sua organização estiver usando [o Microsoft 365 Defender](microsoft-365-defender.md), sua equipe de operações de segurança receberá um alerta sempre que um artefato mal-intencionado ou suspeito for detectado. Devido ao fluxo aparentemente interminável de ameaças que chegam, as equipes de segurança geralmente enfrentam desafios para lidar com o alto volume de alertas. Felizmente, o Microsoft 365 Defender inclui recursos automatizados de investigação e correção (AIR) que podem ajudar sua equipe de operações de segurança a lidar com ameaças de forma mais eficiente e eficaz.

Este artigo fornece uma visão geral do AIR e inclui links para as próximas etapas e recursos adicionais.

> [!TIP]
> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Como funciona a investigação automatizada e a auto-recuperação

À medida que os alertas de segurança são disparados, a equipe de operações de segurança deve procurar esses alertas e tomar medidas para proteger sua organização. Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento. As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas. Recursos automatizados de investigação e resposta, com auto-recuperação, no Microsoft 365 Defender podem ajudar.

Assista ao vídeo a seguir para ver como funciona a auto-recuperação: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

No Microsoft 365 Defender, a investigação e a resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, email & conteúdo e identidades.
 
> [!TIP]
> Este artigo descreve como funciona a investigação e a resposta automatizadas. Para configurar esses recursos, consulte [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="your-own-virtual-analyst"></a>Seu próprio analista virtual

Imagine ter um analista virtual em sua equipe de operações de segurança de Camada 1 ou Camada 2. O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças. O assistente virtual pode funcionar 24 horas e assumir uma carga significativa de investigações e correções de ameaças. Esse assistente virtual pode reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outros projetos estratégicos importantes. Se esse cenário parece com a ficção científica, não é! Esse analista virtual faz parte do pacote do Microsoft 365 Defender e seu nome é investigação e resposta *automatizadas.*

Os recursos automatizados de investigação e resposta permitem que sua equipe de operações de segurança aumente drasticamente a capacidade da sua organização de lidar com alertas e incidentes de segurança. Com a investigação e a resposta automatizadas, você pode reduzir o custo de lidar com atividades de investigação e correção e tirar o máximo do pacote de proteção contra ameaças. Os recursos automatizados de investigação e resposta ajudam sua equipe de operações de segurança:

1. Determinar se uma ameaça requer ação;
2. Tomar (ou recomendar) quaisquer ações de correção necessárias;
3. Determinando se e quais outras investigações devem ocorrer; e
4. Repetir o processo conforme necessário para outros alertas.

## <a name="the-automated-investigation-process"></a>O processo de investigação automatizada

Um alerta cria um incidente, que pode iniciar uma investigação automatizada. A investigação automatizada resulta em um veredito para cada prova. Os vereditos podem ser:
- *Mal-intencionado;*
- *Suspeito;* ou 
- *Nenhuma ameaça encontrada*. 

Ações de correção para entidades mal-intencionadas ou suspeitas são identificadas. Exemplos de ações de correção incluem:
- Enviando um arquivo para quarentena;
- Interrompendo um processo;
- Isolando um dispositivo;
- Bloqueando uma URL; e 
- outras ações. (Consulte [Ações de correção no Microsoft 365 Defender](m365d-remediation-actions.md).)

Dependendo de como [os](m365d-configure-auto-investigation-response.md) recursos automatizados de investigação e resposta são configurados para sua organização, as ações de correção são tomadas automaticamente ou somente após a aprovação pela sua equipe de operações de segurança. Todas as ações, pendentes ou concluídas, estão listadas no [Centro de Ações](m365d-action-center.md).

Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída. Se uma entidade for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade e o processo de investigação se repetirá. 

No Microsoft 365 Defender, cada investigação automatizada correlaciona sinais no Microsoft Defender for Identity, no Microsoft Defender para Ponto de Extremidade e no Defender para Office 365, conforme resumido na tabela a seguir: 

|Entidades |Serviços de proteção contra ameaças  |
|:---------|:---------|
|Dispositivos (também chamados de pontos de extremidade e, às vezes, chamados de máquinas)     |[Microsoft Defender para Ponto de Extremidade](../defender-endpoint/automated-investigations.md)<br/>[Microsoft Defender para Identidade?](/azure-advanced-threat-protection/what-is-atp) |      
|Conteúdo de email (mensagens de email que podem conter arquivos e URLs)     |[Obter o Microsoft Defender para Office 365](../office-365-security/defender-for-office-365.md)         |

> [!NOTE]
> Nem todos os alertas disparam uma investigação automatizada, e nem todas as investigações resulta em ações de correção automatizadas; depende de como a investigação e a resposta automatizadas são configuradas para sua organização. Consulte [Configure automated investigation and response capabilities in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md).

## <a name="viewing-a-list-of-investigations"></a>Exibindo uma lista de investigações

Para exibir investigações, vá para a **página Incidentes.** Selecione um incidente e selecione a guia **Investigações.** Para saber mais, confira [Detalhes e resultados de uma investigação automatizada.](m365d-autoir-results.md)


## <a name="next-steps"></a>Próximas etapas

- [Consulte os pré-requisitos para investigação e resposta automatizadas no Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurar investigação e resposta automatizadas para sua organização](m365d-configure-auto-investigation-response.md)
- [Saiba mais sobre a Central de Ações](m365d-action-center.md)
