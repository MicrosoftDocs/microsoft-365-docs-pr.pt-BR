---
title: Investigação e resposta automatizadas no Microsoft 365 Defender
description: Obter uma visão geral dos recursos automatizados de investigação e resposta, também chamados de autorreeração, no Microsoft 365 Defender
keywords: automatizado, investigação, alerta, gatilho, ação, correção, autorreeração
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
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 905455e4cd70485e099f8005b5f8876b1a5d9caf
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930325"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Investigação e resposta automatizadas no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Deseja experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](https://aka.ms/mtp-trial-lab) ou executar seu projeto piloto em [produção.](https://aka.ms/m365d-pilotplaybook)
>

## <a name="how-automated-investigation-and-self-healing-works"></a>Como funciona a investigação automatizada e a autorrecumentação

À medida que os alertas de segurança são disparados, fica a sua equipe de operações de segurança procurar esses alertas e tomar medidas para proteger sua organização. Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento. As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas. Os recursos automatizados de investigação e resposta, com auto-recuperação, no Microsoft 365 Defender podem ajudar.

Assista ao vídeo a seguir para ver como funciona a autorrerecução:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

No Microsoft 365 Defender, a investigação e resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, emails & conteúdo e identidades.
 
> [!TIP]
> Este artigo descreve como funciona a investigação e resposta automatizadas. Para configurar esses recursos, consulte Configurar recursos automatizados de investigação [e resposta no Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>Seu próprio analista virtual

Imagine ter um analista virtual em sua equipe de operações de segurança do Nível 1 / Nível 2. O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças. O assistente virtual pode funcionar 24 horas e assumir uma carga significativa de investigações e correções de ameaças. Esse assistente virtual pode reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outros projetos estratégicos importantes. Se esse cenário parece uma história de ciência, não é! Esse analista virtual faz parte do seu pacote do Microsoft 365 Defender e seu nome é uma investigação e resposta *automatizadas.*

A investigação e resposta automatizadas permitem que sua equipe de operações de segurança aumente drasticamente a capacidade da sua organização de lidar com alertas e incidentes de segurança. Com a investigação e a resposta automatizadas, você pode reduzir o custo de lidar com atividades de investigação e correção e obter o máximo de seu pacote de proteção contra ameaças. a investigação e resposta automatizadas ajudam sua equipe de operações de segurança ao:

1. Determinar se uma ameaça requer ação;
2. Executar (ou recomendar) todas as ações de correção necessárias;
3. Determinar quais investigações adicionais devem ocorrer; e
4. Repetir o processo conforme necessário para outros alertas.

## <a name="the-automated-investigation-process"></a>O processo de investigação automatizada

**Alerta** > **incidente** > **investigação automatizada** > **veredito** > **ação de correção**

Um alerta disparado cria um incidente, que pode iniciar uma investigação automatizada. Essa investigação pode resultar em uma ou mais ações de correção. No Microsoft 365 Defender, cada investigação automatizada correlaciona sinais no Microsoft Defender for Identity, no Microsoft Defender for Endpoint e no Defender para Office 365, conforme resumido na tabela a seguir: 

|Entidades |Serviços de proteção contra ameaças  |
|---------|---------|
|Dispositivos (também chamados de pontos de extremidade)     |[Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Microsoft Defender para Identidade?](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Conteúdo de email (arquivos e mensagens nas caixas de correio)     |[Obter o Microsoft Defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Cada investigação gera vereditos (*mal-intencionados*, *suspeitos* ou nenhuma ameaça *encontrada*) para cada evidência investigada. Dependendo do tipo de ameaça e veredito resultante, as ações de correção ocorrem automaticamente ou mediante aprovação da equipe de operações de segurança da sua organização. As ações pendentes e concluídas estão listadas na [Central de ações](mtp-action-center.md).

Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída. Se uma entidade incriminada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade, e um manual geral de segurança será executado. 

> [!NOTE]
> Nem todos os alertas acionam uma investigação automatizada, e nem todas as investigações resulta em ações de correção automatizadas; tudo isso depende de como a investigação e resposta automatizadas são configuradas para sua organização. Consulte [Configurar recursos automatizados de investigação e resposta no Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md)


## <a name="next-steps"></a>Próximas etapas

- [Confira os pré-requisitos para investigação e resposta automatizadas no Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Configurar investigação e resposta automatizadas para sua organização](mtp-configure-auto-investigation-response.md)
- [Saiba mais sobre a Central de Ações](mtp-action-center.md)
