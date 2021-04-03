---
title: Visão geral - Busca avançada
description: Saiba mais sobre as consultas avançadas de buscas no Microsoft 365 e sobre como usá-las para encontrar ameaças e deficiências na rede de forma proativa
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, microsoft 365, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 3aa964f8e213d64f583738d8957899c1b7b5146c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501096"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Busca proativamente por ameaças com busca avançada no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).
>

A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos. Você pode inspecionar proativamente eventos em sua rede para localizar indicadores e entidades de ameaça. O acesso flexível aos dados permite a busca não restrita por ameaças conhecidas e potenciais.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Você pode usar as mesmas consultas de busca de ameaças para criar regras de detecção personalizadas. Essas regras são executados automaticamente para verificar e responder a atividades suspeitas de violação, máquinas mal configuradas e outras descobertas.

Esse recurso é semelhante à busca [avançada no Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) Disponível no Centro de segurança do Microsoft 365, esse recurso oferece suporte a consultas que verificam um conjunto de dados mais amplo de:

- Microsoft Defender para Ponto de Extremidade
- Obter o Microsoft Defender para Office 365
- Microsoft Cloud App Security
- Microsoft Defender para Identidade?

Para usar a busca avançada, [a ligue o Microsoft 365 Defender](m365d-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introdução à busca avançada

Recomendamos passar por várias etapas para começar rapidamente com a busca avançada.

| Meta de aprendizagem | Descrição | Recurso |
|--|--|--|
| **Aprenda o idioma** | A busca avançada baseia-se [na linguagem de consulta Kusto](/azure/kusto/query/), suportando a mesma sintaxe e operadores. Comece a aprender a linguagem de consulta executando a primeira consulta. | [Visão geral sobre a linguagem de consulta](advanced-hunting-query-language.md) |
| **Saiba como usar os resultados da consulta** | Saiba mais sobre gráficos e várias maneiras de exibir ou exportar seus resultados. Explore como você pode ajustar rapidamente as consultas, fazer uma análise mais profunda para obter informações mais ricas e tomar ações de resposta. | - [Trabalhar com resultados de consulta](advanced-hunting-query-results.md)<br>- [Tomar medidas sobre os resultados da consulta](advanced-hunting-take-action.md) |
| **Compreender o esquema** | Obtenha uma compreensão de alto nível das tabelas no esquema e em suas colunas. Saiba onde procurar dados ao construir suas consultas. | - [Referência de esquema](advanced-hunting-schema-tables.md)<br>- [Transição do Microsoft Defender para o Ponto de Extremidade](advanced-hunting-migrate-from-mde.md) |
| **Obter dicas e exemplos de especialistas** | Treine gratuitamente com guias de especialistas da Microsoft. Explore coleções de consultas predefinidas que abrangem diferentes cenários de exploração de ameaças. | - [Obter treinamento especializado](advanced-hunting-expert-training.md)<br>- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)<br>- [Ir procurar](advanced-hunting-go-hunt.md)<br>- [Procurar ameaças em dispositivos, emails, aplicativos e identidades](advanced-hunting-query-emails-devices.md) |
| **Otimizar consultas e manipular erros** | Entenda como criar consultas eficientes e sem erros. | - [Práticas recomendadas de consulta](advanced-hunting-best-practices.md)<br>- [Manipular erros](advanced-hunting-errors.md) |
| **Criar regras de detecção personalizadas** | Entenda como você pode usar consultas de busca avançadas para disparar alertas e tomar ações de resposta automaticamente. | - [Visão geral de detecções personalizadas](custom-detections-overview.md)<br>- [Regras de detecção personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obter acesso
Para usar a busca avançada ou outros recursos do [Microsoft 365 Defender,](microsoft-365-defender.md) você precisa de uma função apropriada no Azure Active Directory. Além disso, o acesso aos dados do ponto de extremidade é determinado pelas configurações de controle de acesso baseado em função (RBAC) no Microsoft Defender para Ponto de Extremidade. [Ler sobre como gerenciar o acesso ao Microsoft 365 Defender](m365d-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Atualização de dados e frequência de atualização
Os dados de busca avançada podem ser categorizados em dois tipos distintos, cada um consolidado de forma diferente.

- **Dados de eventos ou atividades**— preenche tabelas sobre alertas, eventos de segurança, eventos do sistema e avaliações de rotina. A busca avançada recebe esses dados quase imediatamente após os sensores que os coletam transmiti-los com êxito para os serviços de nuvem correspondentes. Por exemplo, você pode consultar dados de eventos de sensores saudáveis em estações de trabalho ou controladores de domínio quase imediatamente depois que eles estão disponíveis no Microsoft Defender para Ponto de Extremidade e no Microsoft Defender para Identidade.
- **Dados de entidade**— preenche tabelas com informações sobre usuários e dispositivos. Esses dados vêm de fontes de dados relativamente estáticas e fontes dinâmicas, como entradas do Active Directory e logs de eventos. Para fornecer dados atualizados, as tabelas são atualizadas com novas informações a cada 15 minutos, adicionando linhas que podem não ser totalmente preenchidas. A cada 24 horas, os dados são consolidados para inserir um registro que contém o conjunto de dados mais recente e mais abrangente sobre cada entidade.

## <a name="time-zone"></a>Fuso horário
As informações de tempo na busca avançada estão no fuso horário UTC.

## <a name="related-topics"></a>Tópicos relacionados
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Obtenha treinamento especializado](advanced-hunting-expert-training.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Entender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)