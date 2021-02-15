---
title: Licença e termos de uso das APIs do Microsoft 365 Defender
description: Descrição da licença e dos termos de uso para APIs no Microsoft 365 Defender
keywords: api, apis, licença, termos, apis, jurídico, avisos, código de conduta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 82f31c449ae2e102ac7464e0fef75277660844d1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930949"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licença e termos de uso das APIs do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>Termos oficiais

As APIs do Microsoft 365 Defender são governadas pela licença e pelos termos de uso das [APIs da Microsoft.](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use)

## <a name="legal-notices"></a>Avisos legais

A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste [repositório,](https://github.com/MicrosoftDocs/microsoft-365-docs)sob a Licença Pública Internacional creative Commons Attribution 4.0. Para obter mais informações, consulte o [arquivo LICENSE.](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE)

Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas comerciais ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países.

As licenças para este projeto não lhe concedem direitos para usar quaisquer nomes, logotipos ou marcas comerciais da Microsoft. As diretrizes gerais de marcas comerciais da Microsoft podem ser encontradas em [Marcas Registradas da Microsoft.](https://go.microsoft.com/fwlink/?LinkID=254653)

As informações de privacidade podem ser encontradas [em Privacidade na Microsoft.](https://privacy.microsoft.com)

A Microsoft e quaisquer colaboradores reservam todos os outros direitos, seja sob seus respectivos direitos autorais, patentes ou marcas comerciais, seja por implicação, estoppel ou de outra forma.

## <a name="other-restrictions"></a>Outras restrições

A API de busca avançada tem [algumas limitações sobre](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) o número de resultados retornados e os dados que podem ser consultados.

1. Você só pode consultar dados dos últimos 30 dias.
1. Os resultados incluirão um máximo de 100.000 linhas.

### <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

As APIs do Microsoft 365 Defender têm limites de limite.

- **API de Incidentes:** até 50 chamadas por minuto ou 1500 chamadas por hora.
- **API de Busca** Avançada: até 15 chamadas por minuto, 10 minutos de tempo de execução por hora e 4 horas de tempo de execução por dia.

O código de status de resposta HTTP indicando que a throttling é `429` .

Se sua solicitação tiver sido acelerada, o corpo da resposta indicará a hora em que você poderá começar a fazer solicitações novamente.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [APIs com suporte do Microsoft 365 Defender](api-supported.md)
- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
