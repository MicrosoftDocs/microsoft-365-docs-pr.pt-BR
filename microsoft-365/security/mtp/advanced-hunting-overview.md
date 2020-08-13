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
ms.openlocfilehash: a1fa80d79c1802d96fc755def3b8ec15af13b0c9
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649398"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos. Você pode inspecionar proativamente os eventos na sua rede para localizar indicadores e entidades interessantes. O acesso flexível aos dados facilita a busca irrestrita por ameaças potenciais e conhecidas.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Você pode usar as mesmas consultas de busca de ameaças para criar regras de detecção personalizadas. Essas regras são executadas automaticamente para verificar e responder a vários eventos e estados do sistema, incluindo uma atividade suspeita de violação e máquinas configuradas incorretamente.

O recurso é semelhante à [busca avançada no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview), exceto pelo fato de que, no centro de segurança do Microsoft 365, a busca avançada oferece suporte a consultas que procuram dados de vários espaços de trabalho, incluindo dados sobre dispositivos, emails, aplicativos e identidades do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP. Para usar a busca avançada, é necessário [habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introdução à busca avançada

Recomendamos que você execute várias etapas para começar a trabalhar rapidamente com a busca avançada.

| Meta de aprendizagem | Descrição | Recurso |
|--|--|--|
| **Ver qual seria a linguagem** | A busca avançada é baseada na [linguagem de consulta do Kusto](https://docs.microsoft.com/azure/kusto/query/), com suporte para a mesma sintaxe e operadores. Comece a aprender a linguagem de consulta executando a primeira consulta. | [Visão geral sobre a linguagem de consulta](advanced-hunting-query-language.md) |
| **Saiba como usar os resultados da consulta** | Saiba mais sobre gráficos e várias maneiras de exibir ou exportar os resultados. Explore como você pode ajustar as consultas rapidamente, faça uma busca detalhada para obter informações mais ricas e execute ações de resposta. | - [Trabalhar com resultados de consulta](advanced-hunting-query-results.md)<br>- [Executar ação nos resultados da consulta](advanced-hunting-take-action.md) |
| **Compreender o esquema** | Obtenha uma compreensão de alto nível das tabelas no esquema e em suas colunas. Isso ajuda a determinar onde procurar dados e como construir suas consultas. | [Referência de esquema](advanced-hunting-schema-tables.md) |
| **Aproveitar consultas predefinidas** | Explore coleções de consultas predefinidas que abrangem diferentes cenários de exploração de ameaças. | - [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)<br>- [Busca de ir](advanced-hunting-go-hunt.md) |
| **Otimizar consultas** | Saiba como criar consultas eficientes e que combinem dados de emails e dispositivos. | - [Práticas recomendadas de consulta](advanced-hunting-shared-queries.md) <br>- [Procurar por dispositivos e emails](advanced-hunting-best-practices.md) |
| **Criar regras de detecção personalizadas** | Saiba como você pode usar consultas de busca avançada para disparar alertas e aplicar ações de resposta automaticamente. | - [Visão geral das detecções personalizadas](custom-detections-overview.md)<br>- [Regras de detecção personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obter acesso
Para usar a busca avançada ou outros recursos de [proteção contra ameaças da Microsoft](microsoft-threat-protection.md) , você precisa receber uma função apropriada no Azure AD. Observe que seu acesso aos dados do ponto de extremidade é influenciado pelas configurações de controle de acesso baseado em função no Microsoft defender ATP. [Ler sobre como gerenciar o acesso à proteção contra ameaças da Microsoft](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Atualização de dados e frequência de atualização
Dados de busca avançada podem ser categorizados em dois tipos distintos, cada um consolidado de forma diferente.

- **Dados de evento ou atividade** — preenche tabelas sobre alertas, eventos de segurança, eventos do sistema e avaliações de rotina. A busca avançada recebe esses dados quase imediatamente após os sensores que os coletam com êxito para transmiti-los para os serviços de nuvem correspondentes. Por exemplo, você pode começar a consultar dados de eventos de sensores saudáveis em estações de trabalho ou controladores de domínio quase imediatamente após estarem disponíveis no Microsoft defender ATP e no Azure ATP.
- **Dados da entidade** — preenche tabelas com informações consolidadas sobre usuários e dispositivos. Esses dados são provenientes de fontes de dados relativamente estáticas, como entradas do Active Directory e fontes dinâmicas, como logs de eventos. Para fornecer dados atualizados, as tabelas são atualizadas a cada 15 minutos com qualquer informação nova, adicionando linhas que podem não estar totalmente preenchidas. A cada 24 horas, os dados são consolidados para inserir um registro que contém o conjunto de dados mais recente e mais abrangente sobre cada entidade.

## <a name="related-topics"></a>Tópicos relacionados
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Tomar providências sobre os resultados de consulta](advanced-hunting-take-action.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procurar por dispositivos, emails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)
