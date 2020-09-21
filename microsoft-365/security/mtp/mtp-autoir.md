---
title: Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft
description: Obtenha uma visão geral dos recursos de investigação e resposta automatizados, também chamados de auto-recuperação, na proteção contra ameaças da Microsoft
keywords: automatizado, investigação, alerta, gatilho, ação, correção, auto-recuperação
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: f2a0a439996f13cea3823815aceb9dd1c235e2f2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962660"
---
# <a name="automated-investigation-and-response-in-microsoft-threat-protection"></a>Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Como os alertas de segurança são disparados, a equipe de operações de segurança pode examinar os alertas e realizar etapas para proteger sua organização. Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento. As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas. Os recursos de investigação e resposta automatizados, com auto-recuperação, na proteção contra ameaças da Microsoft podem ajudar.

Assista ao vídeo a seguir para ver como a auto-recuperação funciona:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Na proteção contra ameaças da Microsoft, a investigação e a resposta automatizadas com recursos de auto-recuperação funcionam em seus dispositivos, email & conteúdo e identidades. A proteção contra ameaças da Microsoft reúne recursos de: 
- [Investigação e correção automatizadas no Microsoft defender proteção avançada contra ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Investigação e resposta automatizadas no Office 365 proteção avançada contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Detecção avançada de ameaças do Azure](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
 
Este artigo descreve como funciona a investigação e a resposta automatizadas. Para configurar esses recursos, consulte [configurar os recursos de investigação e resposta automatizados no Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).

## <a name="your-virtual-analyst"></a>Seu analista virtual

Imagine ter um analista virtual em sua equipe de operações de segurança do Nível 1 / Nível 2. O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças. O assistente virtual pode funcionar 24 horas e assumir uma carga significativa de investigações e correções de ameaças. Esse assistente virtual pode reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outros projetos estratégicos importantes. Se este cenário soa como ficção científica, não é! Esse analista virtual faz parte do seu pacote de proteção contra ameaças da Microsoft, e seu nome é *investigação e resposta automatizadas*.

A investigação e a resposta automatizadas permitem que a equipe de operações de segurança aumente drasticamente a capacidade da sua organização para lidar com incidentes e alertas de segurança. Com a investigação e a resposta automatizadas, você pode reduzir o custo de lidar com as atividades de investigação e correção e obter o máximo do seu pacote de proteção contra ameaças. a investigação e a resposta automatizadas ajudam a equipe de operações de segurança:

1. Determinar se uma ameaça requer ação;
2. Executar (ou recomendar) todas as ações de correção necessárias;
3. Determinar quais investigações adicionais devem ocorrer; e
4. Repetir o processo conforme necessário para outros alertas.

## <a name="the-automated-investigation-process"></a>O processo de investigação automatizada

**Alerta** > **incidente** > **investigação automatizada** > **veredito** > **ação de correção**

Um alerta disparado cria um incidente, que pode iniciar uma investigação automatizada. Essa investigação pode resultar em uma ou mais ações de correção. Na Proteção contra Ameaças da Microsoft, cada investigação automatizada correlaciona sinais entre a Proteção Avançada contra Ameaças do Azure (Azure ATP), a Proteção Avançada contra Ameaças do Microsoft Defender (Microsoft Defender ATP) e a Proteção Avançada contra Ameaças do Office 365 (Office 365 ATP), conforme resumido na tabela a seguir: 

|Entidades |Serviços de proteção contra ameaças  |
|---------|---------|
|Dispositivos (também chamados de pontos de extremidade)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Conteúdo de email (arquivos e mensagens nas caixas de correio)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Cada investigação gera verdicts (*mal-intencionado*, *suspeito*ou *nenhuma ameaça encontrada*) para cada evidência investigada. Dependendo do tipo de ameaça e veredicto resultante, as ações de correção ocorrerão automaticamente ou após a aprovação da equipe de operações de segurança da sua organização. As ações pendentes e concluídas estão listadas na [Central de ações](mtp-action-center.md).

Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída. Se uma entidade incriminada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade, e um manual geral de segurança será executado. 

> [!NOTE]
> Nem todos os alertas disparam uma investigação automatizada, e nem todas as investigações resultam em ações de correção automatizadas; Isso depende de como a investigação e a resposta automáticas são configuradas para sua organização. Confira [configurar os recursos de investigação e resposta automatizados no Microsoft Threat Protection](mtp-configure-auto-investigation-response.md).


## <a name="next-steps"></a>Próximas etapas

- [Consulte os pré-requisitos para investigação e resposta automatizadas no Microsoft Threat Protection](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)
- [Configurar investigação e resposta automatizadas para sua organização](mtp-configure-auto-investigation-response.md)
- [Saiba mais sobre a Central de Ações](mtp-action-center.md)
