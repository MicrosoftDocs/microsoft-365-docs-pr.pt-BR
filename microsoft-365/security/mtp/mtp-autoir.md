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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 199bc72e7a8e1e5783105b44de150368a41b872c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917077"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigação e resposta automatizadas no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Se sua organização estiver usando [o Microsoft 365 Defender](microsoft-threat-protection.md), sua equipe de operações de segurança receberá um alerta sempre que um artefato mal-intencionado ou suspeito for detectado. Devido ao fluxo aparentemente interminável de ameaças que chegam, as equipes de segurança geralmente enfrentam desafios para lidar com o alto volume de alertas. Felizmente, o Microsoft 365 Defender inclui recursos automatizados de investigação e correção (AIR) que podem ajudar sua equipe de operações de segurança a lidar com ameaças de forma mais eficiente e eficaz.

Este artigo fornece uma visão geral do AIR e inclui links para as próximas etapas e recursos adicionais.

> [!TIP]
> Deseja experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) ou executar seu projeto piloto em [produção](./mtp-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Como funciona a investigação automatizada e a auto-recuperação

À medida que os alertas de segurança são disparados, a equipe de operações de segurança deve procurar esses alertas e tomar medidas para proteger sua organização. Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento. As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas. Recursos automatizados de investigação e resposta, com auto-recuperação, no Microsoft 365 Defender podem ajudar.

Assista ao vídeo a seguir para ver como funciona a auto-recuperação: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

No Microsoft 365 Defender, a investigação e a resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, email & conteúdo e identidades.
 
> [!TIP]
> Este artigo descreve como funciona a investigação e a resposta automatizadas. Para configurar esses recursos, consulte [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).

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
- outras ações. (Consulte [Ações de correção no Microsoft 365 Defender](mtp-remediation-actions.md).)

Dependendo de como [os](mtp-configure-auto-investigation-response.md) recursos automatizados de investigação e resposta são configurados para sua organização, as ações de correção são tomadas automaticamente ou somente após a aprovação pela sua equipe de operações de segurança. Todas as ações, pendentes ou concluídas, estão listadas no [Centro de Ações](mtp-action-center.md).

Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída. Se uma entidade for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade e o processo de investigação se repetirá. 

No Microsoft 365 Defender, cada investigação automatizada correlaciona sinais no Microsoft Defender for Identity, no Microsoft Defender para Ponto de Extremidade e no Defender para Office 365, conforme resumido na tabela a seguir: 

|Entidades |Serviços de proteção contra ameaças  |
|:---------|:---------|
|Dispositivos (também chamados de pontos de extremidade e, às vezes, chamados de máquinas)     |[Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[O que é o Microsoft Defender para Identidade?](/azure-advanced-threat-protection/what-is-atp) |      
|Conteúdo de email (mensagens de email que podem conter arquivos e URLs)     |[Obter o Microsoft Defender para Office 365](../office-365-security/office-365-atp.md)         |

> [!NOTE]
> Nem todos os alertas disparam uma investigação automatizada, e nem todas as investigações resulta em ações de correção automatizadas; depende de como a investigação e a resposta automatizadas são configuradas para sua organização. Consulte [Configure automated investigation and response capabilities in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md).

## <a name="next-steps"></a>Próximas etapas

- [Consulte os pré-requisitos para investigação e resposta automatizadas no Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurar investigação e resposta automatizadas para sua organização](mtp-configure-auto-investigation-response.md)
- [Saiba mais sobre a Central de Ações](mtp-action-center.md)