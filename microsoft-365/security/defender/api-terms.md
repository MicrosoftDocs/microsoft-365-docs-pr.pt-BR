---
title: Microsoft 365 Licença e termos de uso das APIs do Defender
description: Descrição da licença e dos termos de uso para APIs no Microsoft 365 Defender
keywords: api, apis, licença, termos, apis, legal, avisos, código de conduta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 9b70311726b6c1c5bedf34a18ee1763255c93ba3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052842"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Microsoft 365 Licença e termos de uso das APIs do Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

## <a name="official-terms"></a>Termos oficiais

Microsoft 365 As APIs do Defender são governadas pela licença e pelos termos [de uso das APIs da Microsoft.](/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Avisos Legais

A Microsoft e quaisquer colaboradores concedem uma licença à documentação da Microsoft e a outros conteúdos neste [repositório,](https://github.com/MicrosoftDocs/microsoft-365-docs)sob a Licença Pública Internacional de Atribuição do Creative Commons 4.0. Para obter mais informações, consulte o [arquivo LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas comerciais ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países.

As licenças para este projeto não concedem direitos para usar nomes, logotipos ou marcas comerciais da Microsoft. As diretrizes gerais de marcas comerciais da Microsoft podem ser encontradas em [Marcas Comerciais da Microsoft.](https://go.microsoft.com/fwlink/?LinkID=254653)

Informações de privacidade podem ser encontradas [em Privacidade na Microsoft](https://privacy.microsoft.com).

A Microsoft e quaisquer colaboradores reservam todos os outros direitos, seja sob seus respectivos direitos autorais, patentes ou marcas comerciais, seja por implicação, estoppel ou não.

## <a name="other-restrictions"></a>Outras restrições

A API de busca avançada tem [algumas limitações](/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) sobre o número de resultados retornados e os dados que podem ser consultados.

1. Você só pode consultar dados dos últimos 30 dias.
1. Os resultados incluirão no máximo 100.000 linhas.

### <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

As MICROSOFT 365 do Defender têm limites de limite de limite.

- **API de Incidentes**: até 50 chamadas por minuto ou 1500 chamadas por hora.
- **API de Busca Avançada**: até 15 chamadas por minuto, 10 minutos de tempo de execução por hora e 4 horas de tempo de execução por dia.

O código de status de resposta HTTP que indica a throttling é `429` .

Se sua solicitação tiver sido acelerada, o corpo da resposta indicará a hora em que você poderá começar a fazer solicitações novamente.

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft 365 Visão geral das APIs do Defender](api-overview.md)
- [APIs com suporte do Microsoft 365 Defender](api-supported.md)
- [Acessar as APIs Microsoft 365 Defender](api-access.md)