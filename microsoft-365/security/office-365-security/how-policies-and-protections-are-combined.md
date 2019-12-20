---
title: Como as políticas e proteções são combinadas quando os emails são sinalizados em vermelho
description: Descreve quais políticas e proteções se aplicam quando o email encontra várias proteções e é verificado por várias formas de detecção. Quais políticas se aplicam e quais ações tomar, quando o email está marcado como malware, spam, spam de alta confiança, phishing e massa por EOP e/ou ATP.
keywords: segurança, malware, Microsoft 365, M365, central de segurança, ATP, Microsoft defender ATP, Office 365 ATP, Azure ATP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 03/26/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 4ca5333f4b07878f8c7d206b78cf884f4e4eec82
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40807977"
---
# <a name="what-policy-applies-when-multiple-protection-methods-and-detection-scans-run-on-your-email"></a>Qual política se aplica quando vários métodos de proteção e verificações de detecção são executados em seu email

Provavelmente, seus emails de entrada podem ser sinalizados por várias formas de proteção (por exemplo, EOP *e* ATP) e várias verificações de detecção (como spam *e* phishing). Isso é possível porque há políticas anti-phishing de ATP para clientes ATP e políticas anti-phishing do EOP para clientes do EOP. Isso também significa que a mensagem pode navegar por várias verificações de detecção de malware, phishing e representação de usuário, por exemplo. Dada a todas essas atividades, pode haver uma certa confusão à qual a política se aplica.

Em geral, uma política aplicada a uma mensagem é identificada no cabeçalho **X-Forefront-antispam-Report** na propriedade **Cat (categoria)** . Se você tiver várias políticas anti-phishing, o que será aplicado com a prioridade mais alta.

As políticas abaixo se aplicam a _todas as organizações_.

|Prioridade |Política  |Categoria  |Onde gerenciado |
|---------|---------|---------|---------|
|1     | Malware      | MALW      | Política de malware   |
|duas     | Phishing     | PHSH     | Configurar suas políticas de filtro de spam     |
|3D     | Spam de alta confiança      | HSPM        | Configurar suas políticas de filtro de spam        |
|quatro     | Spoofing        | SPOOF        | Política anti-phishing, inteligência de falsificação        |
|0,5     | Spam         | SPM         | Configurar suas políticas de filtro de spam         |
|6      | Em massa         | BULK        | Configurar suas políticas de filtro de spam         |

Além disso, essas políticas se aplicam a _organizações com ATP_.

|Prioridade |Política  |Categoria  |Onde gerenciado |
|---------|---------|---------|---------|
|7      | Representação de domínio         | DIMP         |  Configurar políticas antiphishing e antiphishing da ATP do Office 365        |
|8      | Representação de usuário        | UIMP         |  Configurar políticas antiphishing e antiphishing da ATP do Office 365         |

Por exemplo, se você tiver duas políticas com suas respectivas prioridades:

|Política  |Prioridade  |Representação de Usuário/Domínio  |Antifalsificação  |
|---------|---------|---------|---------|
|A     | 1        | Ativada        |Desabilitado         |
|B     | duas        | Desativada        | Ativada        |

Se uma mensagem for identificada como _representação de usuário_ e _falsificação_ (consulte anti-falsificação na tabela acima), e o mesmo conjunto de usuários com escopo de política a estiver no escopo da política B, a mensagem será sinalizada e tratada como uma _falsificação_. No entanto, nenhuma ação é aplicada porque, embora a falsificação seja executada em uma prioridade mais alta (4) que a representação de usuário (8), a antifalsificação está desativada.

Tenha em mente, os administradores podem criar uma lista priorizada de políticas (consulte o campo prioridade acima), mas apenas uma política será executada e aplicará suas ações. Isso significa que um usuário em ambas as políticas A e B terá a política de prioridade mais alta (A é #1), e a mensagem não será filtrada por outras políticas. Se o anti-spoofiing estiver desativado, nenhuma ação será executada.

Como há um potencial para ter muitos grupos de usuários em muitas políticas, pode ser behoove que os administradores considerem usar menos políticas com mais recursos. Também é importante ter certeza de que todos os usuários estão cobertos por uma política abrangente.

Para fazer com que outros tipos de política de phishing se apliquem, será necessário ajustar as configurações das quais as várias políticas se aplicam.



