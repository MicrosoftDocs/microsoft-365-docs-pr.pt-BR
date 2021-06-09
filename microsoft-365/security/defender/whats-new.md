---
title: Novidades no Microsoft 365 Defender
description: Lista os novos recursos e funcionalidades no Microsoft 365 Defender
keywords: novidades no Defender Microsoft 365, ga, geralmente disponíveis, recursos, disponíveis, novos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c974701b83fbb6dbcac1cc597578a97144b2b482
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845589"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novidades no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Quer experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) ou [executar seu projeto piloto em produção](m365d-pilot.md?ocid=cx-evalpilot).
>

Os seguintes recursos geralmente estão disponíveis (GA) na versão mais recente do Microsoft 365 Defender.

RSS feed: seja notificado quando esta página for atualizada copiando e colar a SEGUINTE URL no leitor de feeds:
```http
/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="april-2021"></a>Abril de 2021
- Centro de Microsoft 365 de segurança aprimorado <br> O aperfeiçoado[Centro de segurança do Microsoft 365](https://security.microsoft.com) está agora disponível em pré-visualização pública. Esta nova experiência traz o Defender para Ponto de Extremidade, Defender para Office 365, Microsoft 365 Defender e muito mais para o Centro de segurança do Microsoft 365. Esta é a nova casa para gerenciar seus controles de segurança. [Conheça as novidades](./overview-security-center.md).

- [Microsoft 365 Relatório de análise de ameaças do Defender](threat-analytics.md)<br>
 A análise de ameaças ajuda você a responder e minimizar o impacto de ataques ativos. Você também pode aprender sobre tentativas de ataque bloqueadas pelas soluções do Defender Microsoft 365 e tomar ações preventivas que reduzam o risco de exposição e aumentam a resiliência. Como parte da experiência de segurança unificada, a análise de ameaças agora está disponível para o Microsoft Defender para Ponto de Extremidade e o Microsoft Defender para Office proprietários de licença do E5.

## <a name="march-2021"></a>Março de 2021
- [Tabela CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Encontre informações sobre eventos em vários aplicativos e serviços de nuvem cobertos por Microsoft Cloud App Security. Esta tabela também inclui informações disponíveis anteriormente em `AppFileEvents` .
## <a name="february-2021"></a>Fevereiro de 2021
- (Visualização) O centro de [Microsoft 365 de https://security.microsoft.com) segurança aprimorado (](https://security.microsoft.com) agora está disponível na visualização pública. Essa nova experiência traz o Defender para o Ponto de Extremidade e o Defender Office 365 para o centro. [Saiba mais sobre o que mudou](./overview-security-center.md).

## <a name="september-2020"></a>Setembro de 2020
- [Tabela IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) <br> Encontre eventos envolvendo um controlador de domínio local executando o Active Directory (AD). Esta [tabela de](advanced-hunting-overview.md) esquema de busca avançada abrange um intervalo de eventos relacionados à identidade e eventos do sistema no controlador de domínio.
- [Função AssignedIPAddresses()](advanced-hunting-assignedipaddresses-function.md) <br> Use essa função em suas consultas de busca avançadas para obter rapidamente os endereços IP mais recentes atribuídos a um dispositivo ou aos endereços IP mais recentes de uma hora específica.

## <a name="july-2020"></a>Julho de 2020
- [Função FileProfile()](advanced-hunting-fileprofile-function.md) <br> Use essa função em suas consultas de busca avançadas para enriquecer resultados com informações abrangentes de arquivo.
- [Identidades e tabelas de aplicativos](advanced-hunting-schema-tables.md)<br> Obter visibilidade de eventos de autenticação, consultas do Active Directory e atividades relacionadas ao aplicativo com as [tabelas IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) no esquema de busca avançado.
- [Ir à caça](advanced-hunting-go-hunt.md)<br> Pivot rapidamente da investigação de um incidente para inspecionar um evento específico, um usuário, um dispositivo ou outros tipos de entidade em busca avançada.

## <a name="june-2020"></a>Junho de 2020
- Feed do Twitter <br> Obter a pesquisa de segurança mais recente, inteligência contra ameaças, notícias do produto e muito mais - dentro do painel.
- [Tabela de esquema EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) <br> Incorpore informações sobre ações pós-entrega realizadas em mensagens de email em suas consultas de busca avançadas.
- [Inspecionar registros em busca avançada](advanced-hunting-query-results.md#drill-down-from-query-results) <br> Inspecione rapidamente os registros nos resultados da consulta com o novo painel de detalhes.

## <a name="may-2020"></a>Maio de 2020
- [Detecções personalizadas](custom-detections-overview.md) <br> Use consultas de busca avançadas para criar regras de detecção personalizadas que monitoram automaticamente e respondem a eventos de segurança e estados do sistema.

## <a name="february-2020"></a>Fevereiro de 2020
- [Incidentes](incidents-overview.md) <br> Saiba exatamente onde um ataque foi iniciado e outros detalhes para ajudá-lo a ver a extensão do ataque.
- [Resposta e investigação automatizadas](m365d-autoir.md) <br> O AIR permite à sua equipe de operações de segurança aumentar drasticamente a capacidade da sua organização para lidar com alertas e incidentes de segurança.
- [Aprimoramentos avançados de busca](advanced-hunting-overview.md) <br> Busca proativamente por ameaças em todo o espaço de trabalho moderno com a Linguagem de Consulta kusto e um esquema otimizado para segurança.

## <a name="march-2019"></a>Março de 2019
- Busca avançada <br> Página inicial para vários recursos de busca que permitem que você encontre proativamente ameaças que afetam emails e dados, dispositivos e identidades.
- [Classificação de Segurança da Microsoft](microsoft-secure-score.md) <br> Medida da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria tomadas. Seguir as recomendações do Secure Score pode proteger sua organização contra ameaças. 
- [Relatórios](overview-security-center.md) <br>  Apresenta uma série de cartões que abrangem uma variedade de áreas que os analistas de segurança e administradores acompanham como parte de suas operações diárias.
