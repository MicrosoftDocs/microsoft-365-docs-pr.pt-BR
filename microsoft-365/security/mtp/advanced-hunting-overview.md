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
ms.openlocfilehash: 8e586050465464def02c7787a5fb218b0b6071c7
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338456"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos. Você pode inspecionar eventos de forma proativa em sua rede para localizar indicadores de ameaça e entidades. O acesso flexível aos dados permite uma busca irrestrita para ameaças conhecidas e potenciais.
<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]

Você pode usar as mesmas consultas de busca de ameaças para criar regras de detecção personalizadas. Essas regras são executadas automaticamente para verificar e, em seguida, responder à suspeita de atividade de violação, máquinas configuradas incorretamente e outras descobertas.

Esse recurso é semelhante à [busca avançada no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview). Disponível na central de segurança do Microsoft 365, esse recurso oferece suporte a consultas que verificam um conjunto de dados mais amplo de:

- Proteção avançada contra ameaças do Microsoft Defender
- Proteção Avançada contra Ameaças do Office 365
- Segurança no aplicativo na nuvem da Microsoft
- Proteção Avançada contra Ameaças do Azure

Para usar a busca avançada, é necessário [habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introdução à busca avançada

Recomendamos passar por várias etapas para começar a usar rapidamente a busca avançada.

| Meta de aprendizagem | Descrição | Recurso |
|--|--|--|
| **Saiba mais sobre o idioma** | A busca avançada é baseada na [linguagem de consulta do Kusto](https://docs.microsoft.com/azure/kusto/query/), com suporte para a mesma sintaxe e operadores. Comece a aprender a linguagem de consulta executando a primeira consulta. | [Visão geral sobre a linguagem de consulta](advanced-hunting-query-language.md) |
| **Saiba como usar os resultados da consulta** | Saiba mais sobre gráficos e várias maneiras de exibir ou exportar os resultados. Explore como você pode ajustar as consultas rapidamente, faça uma busca detalhada para obter informações mais ricas e execute ações de resposta. | - [Trabalhar com resultados de consulta](advanced-hunting-query-results.md)<br>- [Executar ação nos resultados da consulta](advanced-hunting-take-action.md) |
| **Compreender o esquema** | Obtenha uma compreensão de alto nível das tabelas no esquema e em suas colunas. Saiba onde procurar dados ao criar suas consultas. | - [Referência de esquema](advanced-hunting-schema-tables.md)<br>- [Transição do Microsoft defender ATP](advanced-hunting-migrate-from-mdatp.md) |
| **Obter dicas e exemplos de especialistas** | Treine gratuitamente com guias de especialistas da Microsoft. Explore coleções de consultas predefinidas que abrangem diferentes cenários de exploração de ameaças. | - [Obter treinamento especializado](advanced-hunting-expert-training.md)<br>- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)<br>- [Busca de ir](advanced-hunting-go-hunt.md)<br>- [Busca de ameaças em dispositivos, emails, aplicativos e identidades](advanced-hunting-query-emails-devices.md) |
| **Otimizar consultas e lidar com erros** | Saiba como criar consultas eficientes e livres de erros. | - [Práticas recomendadas de consulta](advanced-hunting-best-practices.md)<br>- [Manipular erros](advanced-hunting-errors.md) |
| **Criar regras de detecção personalizadas** | Saiba como você pode usar consultas de busca avançada para disparar alertas e realizar ações de resposta automaticamente. | - [Visão geral das detecções personalizadas](custom-detections-overview.md)<br>- [Regras de detecção personalizadas](custom-detection-rules.md) |

## <a name="get-access"></a>Obter acesso
Para usar a busca avançada ou outros recursos de [proteção contra ameaças da Microsoft](microsoft-threat-protection.md) , você precisa de uma função apropriada no Azure Active Directory. Além disso, seu acesso aos dados do ponto de extremidade é determinado pelas configurações do controle de acesso baseado em função (RBAC) no Microsoft defender ATP. [Ler sobre como gerenciar o acesso à proteção contra ameaças da Microsoft](mtp-permissions.md)

## <a name="data-freshness-and-update-frequency"></a>Atualização de dados e frequência de atualização
Dados de busca avançada podem ser categorizados em dois tipos distintos, cada um consolidado de forma diferente.

- **Dados de evento ou atividade**— preenche tabelas sobre alertas, eventos de segurança, eventos do sistema e avaliações de rotina. A busca avançada recebe esses dados quase imediatamente após os sensores que os coletam com êxito para transmiti-los para os serviços de nuvem correspondentes. Por exemplo, você pode consultar dados de eventos de sensores saudáveis em estações de trabalho ou controladores de domínio quase imediatamente após estarem disponíveis no Microsoft defender ATP e no Azure ATP.
- **Dados da entidade**— preenche tabelas com informações sobre usuários e dispositivos. Esses dados são provenientes de fontes de dados relativamente estáticas e fontes dinâmicas, como entradas do Active Directory e logs de eventos. Para fornecer dados atualizados, as tabelas são atualizadas com qualquer informação nova a cada 15 minutos, adicionando linhas que podem não estar totalmente preenchidas. A cada 24 horas, os dados são consolidados para inserir um registro que contém o conjunto de dados mais recente e mais abrangente sobre cada entidade.

## <a name="time-zone"></a>Fuso horário
As informações de tempo em busca avançada estão no fuso horário UTC.

## <a name="related-topics"></a>Tópicos relacionados
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Obtenha treinamento especializado](advanced-hunting-expert-training.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Entender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](custom-detections-overview.md)

