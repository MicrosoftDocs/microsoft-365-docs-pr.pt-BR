---
title: Licença e termos de uso do Microsoft 365 defender APIs
description: Descrição da licença e dos termos de uso de APIs no Microsoft 365 defender
keywords: API, APIs, licença, termos, APIs, ofício, avisos, código de conduta
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: d9b3c48e4b9e89ef7648086b05c9fdd9f078f51e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719293"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licença e termos de uso do Microsoft 365 defender APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>Termos oficiais

As APIs do Microsoft 365 defender são regidas pelas [licenças e termos de uso da API da Microsoft](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use).

## <a name="legal-notices"></a>Avisos legais

A Microsoft e qualquer colaborador concedem a você uma licença para a documentação da Microsoft e outro conteúdo neste [repositório](https://github.com/MicrosoftDocs/microsoft-365-docs), sob a licença pública do Creative Commons requery 4,0 International Public. Para obter mais informações, consulte o arquivo de [licença](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) .

Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft mencionados na documentação podem ser marcas comerciais ou marcas registradas da Microsoft nos Estados Unidos e/ou outros países.

As licenças para este projeto não concedem direitos de uso de nomes, logotipos ou marcas da Microsoft. As diretrizes gerais de marca registrada da Microsoft podem ser encontradas nas [marcas comerciais da Microsoft](https://go.microsoft.com/fwlink/?LinkID=254653).

As informações de privacidade podem ser encontradas na [privacidade da Microsoft](https://privacy.microsoft.com).

A Microsoft e qualquer colaborador reservam todos os outros direitos, quer sob seus respectivos direitos autorais, patentes ou marcas registradas, seja por implicação, embargo ou de outra forma.

## <a name="other-restrictions"></a>Outras restrições

A API de busca avançada tem algumas [limitações](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) sobre o número de resultados retornados e os dados que podem ser consultados.

1. Você só pode consultar dados dos últimos 30 dias.
1. Os resultados incluirão um máximo de 100.000 linhas.

### <a name="quotas-and-resource-allocation"></a>Cotas e alocação de recursos

As APIs do Microsoft 365 defender têm limites de limitação.

- **API de incidentes**: até 50 chamadas por minuto ou 1500 de chamadas por hora.
- **API de busca avançada**: até 15 chamadas por minuto, 10 minutos de tempo de execução por hora e 4 horas de tempo de execução por dia.

O código de status de resposta HTTP que indica a limitação é `429` .

Se sua solicitação tiver sido limitada, o corpo da resposta indicará o horário em que você poderá começar a fazer as solicitações novamente.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 defender](api-overview.md)
- [APIs com suporte do Microsoft 365 Defender](api-supported.md)
- [Acessar as APIs do Microsoft 365 defender](api-access.md)
