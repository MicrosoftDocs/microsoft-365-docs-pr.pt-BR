---
title: Visão geral da busca avançada no Microsoft Defender para Ponto de Extremidade
description: Usar recursos de busca de ameaças no Microsoft Defender para Ponto de Extremidade para criar consultas que encontrem ameaças e pontos fracos em sua rede
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft Defender para Ponto de Extremidade, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, fuso horário, UTC
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 114c0192f77411016fcb13ec2b912f4440ffa6e0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934352"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting"></a>Busca proativamente por ameaças com busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos. Você pode inspecionar proativamente eventos em sua rede para localizar indicadores e entidades de ameaça. O acesso flexível aos dados permite a busca não restrita por ameaças conhecidas e potenciais.

Assista a este vídeo para obter uma visão geral rápida da busca avançada e um breve tutorial que o fará começar rapidamente.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqo]

Você pode usar as mesmas consultas de busca de ameaças para criar regras de detecção personalizadas. Essas regras são executados automaticamente para verificar e responder a atividades suspeitas de violação, máquinas mal configuradas e outras descobertas.

>[!TIP]
>Use a busca avançada no [Microsoft 365 Defender](/microsoft-365/security/defender/advanced-hunting-overview) para procurar ameaças usando dados do Defender para Ponto de Extremidade, do Microsoft Defender para Office 365, do Microsoft Cloud App Security e do Microsoft Defender para Identidade. [A turn on Microsoft 365 Defender](/microsoft-365/security/defender/m365d-enable).<br><br>
Saiba mais sobre como mover seus fluxos de trabalho de busca avançados do Microsoft Defender para o Endpoint para o Microsoft 365 Defender em [Migrar](/microsoft-365/security/defender/advanced-hunting-migrate-from-mde)consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade .

## <a name="get-started-with-advanced-hunting"></a>Introdução à busca avançada

Vá pelas etapas a seguir para aumentar seu conhecimento avançado de busca.

Recomendamos que você execute várias etapas para começar a trabalhar rapidamente com a busca avançada.

| Meta de aprendizagem | Descrição | Recurso |
|--|--|--|
| **Aprenda o idioma** | A busca avançada baseia-se [na linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/), suportando a mesma sintaxe e operadores. Comece a aprender a linguagem de consulta executando a primeira consulta. | [Visão geral sobre a linguagem de consulta](advanced-hunting-query-language.md) |
| **Saiba como usar os resultados da consulta** | Saiba mais sobre gráficos e várias maneiras de exibir ou exportar seus resultados. Explore como você pode ajustar rapidamente consultas e detalhar para obter informações mais ricas. | [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md) |
| **Compreender o esquema** | Obtenha uma compreensão de alto nível das tabelas no esquema e em suas colunas. Saiba onde procurar dados ao construir suas consultas. | [Referência de esquema](advanced-hunting-schema-reference.md) |
| **Usar consultas predefinidas** | Explore coleções de consultas predefinidas que abrangem diferentes cenários de exploração de ameaças. | [Consultas compartilhadas](advanced-hunting-shared-queries.md) |
| **Otimizar consultas e manipular erros** | Entenda como criar consultas eficientes e sem erros. | - [Práticas recomendadas de consulta](advanced-hunting-best-practices.md)<br>- [Manipular erros](advanced-hunting-errors.md) |
| **Obter a cobertura mais completa** | Use as configurações de auditoria para fornecer uma melhor cobertura de dados para sua organização. | - [Estender a cobertura de busca avançada](advanced-hunting-extend-data.md) |
| **Executar uma investigação rápida** | Execute rapidamente uma consulta de busca avançada para investigar atividades suspeitas. | - [Busca rápida por informações de entidade ou evento com *a busca de ida e volta*](advanced-hunting-go-hunt.md) |
| **Conter ameaças e comprometimentos de endereço** | Responder a ataques por meio de arquivos de quarentena, restrição da execução de aplicativos e outras ações | - [Tomar medidas nos resultados avançados da consulta de busca](advanced-hunting-take-action.md) |
| **Criar regras de detecção personalizadas** | Entenda como você pode usar consultas de busca avançadas para disparar alertas e tomar ações de resposta automaticamente. | - [Visão geral de detecções personalizadas](overview-custom-detections.md)<br>- [Regras de detecção personalizadas](custom-detection-rules.md) |

## <a name="data-freshness-and-update-frequency"></a>Atualização de dados e frequência de atualização

Os dados de busca avançada podem ser categorizados em dois tipos distintos, cada um consolidado de forma diferente.

- **Dados de eventos ou atividades**— preenche tabelas sobre alertas, eventos de segurança, eventos do sistema e avaliações de rotina. A busca avançada recebe esses dados quase imediatamente após os sensores que os coletam transmiti-los com êxito para o Defender para o Ponto de Extremidade.
- **Dados de entidade**— preenche tabelas com informações consolidadas sobre usuários e dispositivos. Esses dados vêm de fontes de dados relativamente estáticas e fontes dinâmicas, como entradas do Active Directory e logs de eventos. Para fornecer dados atualizados, as tabelas são atualizadas com novas informações a cada 15 minutos, adicionando linhas que podem não ser totalmente preenchidas. A cada 24 horas, os dados são consolidados para inserir um registro que contém o conjunto de dados mais recente e mais abrangente sobre cada entidade.

## <a name="time-zone"></a>Fuso horário

As informações de tempo na busca avançada estão no fuso horário UTC.

## <a name="related-topics"></a>Tópicos relacionados

- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Entender o esquema](advanced-hunting-schema-reference.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](overview-custom-detections.md)
