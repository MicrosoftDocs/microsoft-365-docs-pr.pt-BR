---
title: Princípios básicos da Microsoft 365 sobre defesa contra ataques de negação de serviço
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Como a Microsoft utiliza os princípios fundamentais de absorção, detecção e atenuação em sua defesa contra ataques de negação de serviço (DoS).
ms.openlocfilehash: b04ec717f7c97e44c6ed4011156666e8c27f06c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687121"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>Principais princípios de defesa contra ataques de negação de serviço

Os três princípios fundamentais ao se defender contra ataques de DoS baseados em rede são absorção, detecção e mitigação. A absorção ocorre antes da detecção e a detecção ocorre antes da redução. O absorção é a melhor defesa contra um ataque de DoS. Se não for possível detectar o ataque, não será possível diminuí-lo. Mas, se mesmo o menor ataque de DoS não puder ser absorvido, os serviços não ficarão sobreviventes o suficiente para que o ataque seja detectado.

Não é economicamente viável para a maioria das organizações comprar capacidade em excesso para absorver ataques de DoS, já que isso requer um investimento considerável em tecnologia e habilidades técnicas. Isso realça um dos benefícios de segurança do uso dos serviços de nuvem da Microsoft. A escalabilidade dos serviços Microsoft oferece uma forte proteção de rede para os clientes da nuvem de forma econômica. Mas mesmo em uma escala grande, deve haver um equilíbrio entre absorção, detecção e mitigação. Para encontrar esse saldo, a Microsoft estuda as taxas de crescimento de ataques para estimar a quantidade de necessidade de absorver a Microsoft.

A detecção é um jogo de gato e mouse. Você deve procurar constantemente por novas maneiras pelas quais as pessoas são atacadas e tentar derrotar seus sistemas. Detect-> mitigate-> Detect-> mitigate, etc., é um estado permanente e persistente que continua indefinidamente.

## <a name="defending-against-dos-attacks"></a>Como se proteger contra ataques de DoS

Para se defender com êxito contra ataques de DoS, a detecção antecipada é essencial. Ao detectar um ataque antes que o sistema fique sobrecarregado, os defensores podem executar um plano de resposta.

A fórmula a seguir ajuda a aproximar o tempo de impacto de um ataque de DoS:

   **Capacidade máxima (em bytes/seg)/taxa de crescimento (em bytes/seg) = tempo de impacto (em segundos)**

Se o tempo de detecção ocorrer após o tempo de impacto, é provável que o ataque de DoS seja bem-sucedido. Se o tempo de detecção ocorrer antes do tempo de impacto, os serviços atacados deverão permanecer online e acessíveis se as estratégias de mitigação forem usadas. Portanto, há apenas duas coisas que podem ser realizadas para se defender contra ataques de DoS:

- Aumente a capacidade para elevar o teto da capacidade máxima (que, por sua vez, fornece mais tempo para detectar um ataque); ou
- Diminuir o tempo para detectar.

O aumento da capacidade tem um impacto fiscal direto. A Microsoft recomenda que os clientes desenvolvam pelo menos a capacidade básica de absorção para garantir que eles possam sobreviver a algum nível de ataque de DoS. A capacidade de absorção real varia de cliente para cliente, uma vez que cada cliente tem seus próprios limites de exposição, risco e outlay financeiro. Por motivos econômicos, os investimentos em pesquisa e tempo para reduzir o tempo de detecção costumam ser a defesa mais econômica.
