---
title: Visão geral-busca avançada
description: Saiba mais sobre as consultas avançadas de buscas no Microsoft 365 e sobre como usá-las para encontrar ameaças e deficiências na rede de forma proativa
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, Microsoft 365, proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 48850c76176d79e4f90581bfbab804f4649998cc
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049627"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos. Você pode inspecionar proativamente os eventos na sua rede para localizar indicadores e entidades interessantes. O acesso flexível aos dados facilita a busca irrestrita por ameaças potenciais e conhecidas.

Você pode usar as mesmas consultas de busca de ameaças para criar regras de detecção personalizadas. Essas regras são executadas automaticamente para verificar e responder a vários eventos e Estados do sistema, incluindo atividade de violação suspeita e máquinas configuradas incorretamente.

No centro de segurança do Microsoft 365, a busca avançada oferece suporte a consultas que procuram dados de vários espaços de trabalho, incluindo dados sobre dispositivos, emails, aplicativos e identidades do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP. Para usar a busca avançada, é necessário [habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introdução à busca avançada

Recomendamos que você execute várias etapas para começar a trabalhar rapidamente com a busca avançada.

| Meta de aprendizagem | Descrição | Recurso |
|--|--|--|
| **Ver qual seria a linguagem** | A busca avançada se baseia na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/), que oferece suporte à mesma sintaxe e operadores. Comece a aprender a linguagem de consulta executando a primeira consulta. | [Visão geral sobre a linguagem de consulta](advanced-hunting-query-language.md) |
| **Saiba como usar os resultados da consulta** | Saiba mais sobre gráficos e várias maneiras de exibir ou exportar os resultados. Explore como você pode ajustar rapidamente as consultas e aprofundar para obter informações mais ricas. | [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md) |
| **Compreender o esquema** | Obtenha uma compreensão de alto nível das tabelas no esquema e em suas colunas. Isso ajuda a determinar onde procurar dados e como construir suas consultas. | [Referência de esquema](advanced-hunting-schema-tables.md) |
| **Aproveitar consultas predefinidas** | Explore coleções de consultas predefinidas que abrangem diferentes cenários de exploração de ameaças. | - [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)<br>- [Busca de ir](advanced-hunting-go-hunt.md) |
| **Otimizar consultas** | Saiba como criar consultas eficientes e que combinem dados de emails e dispositivos. | - [Práticas recomendadas de consulta](advanced-hunting-shared-queries.md) <br>- [Procurar por dispositivos e emails](advanced-hunting-best-practices.md) |
| **Criar regras de detecção personalizadas** | Saiba como você pode usar consultas de busca avançada para disparar alertas e aplicar ações de resposta automaticamente. | - [Visão geral das detecções personalizadas](custom-detections-overview.md)<br>- [Regras de detecção personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obter acesso
Para usar a busca avançada ou outros recursos de [proteção contra ameaças da Microsoft](microsoft-threat-protection.md) , você precisa receber uma função apropriada no Azure AD. Observe que seu acesso aos dados do ponto de extremidade é influenciado pelas configurações de controle de acesso baseado em função no Microsoft defender ATP. [Ler sobre como gerenciar o acesso à proteção contra ameaças da Microsoft](mtp-permissions.md)


## <a name="related-topics"></a>Tópicos relacionados
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Entender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)
