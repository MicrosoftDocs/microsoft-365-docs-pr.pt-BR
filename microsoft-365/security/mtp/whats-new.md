---
title: Novidades no Microsoft 365 Defender
description: Lista os novos recursos e funcionalidades no Microsoft 365 Defender
keywords: novidades na proteção contra ameaças da Microsoft, ga, geralmente disponíveis, recursos, disponíveis, novos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 5de805784b2772b0169b2ad2a503e9378b82fda7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927091"
---
# <a name="whats-new-in-microsoft-365-defender"></a>Novidades no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> Deseja experimentar o Microsoft 365 Defender? Você pode [avaliá-lo em um ambiente de laboratório](./mtp-evaluation.md?ocid=cx-docs-MTPtriallab) ou executar seu projeto piloto em [produção](./mtp-pilot.md?ocid=cx-evalpilot).
>

Os seguintes recursos geralmente estão disponíveis (GA) na versão mais recente do Microsoft 365 Defender.

RSS feed: seja notificado quando esta página for atualizada copiando e colar a SEGUINTE URL no leitor de feeds:
```http
https://docs.microsoft.com/api/search/rss?search=%22Lists+the+new+features+and+functionality+in+Microsoft+365+defender%22&locale=en-us
```

## <a name="march-2021"></a>Março de 2021
- [Tabela CloudAppEvents](advanced-hunting-cloudappevents-table.md) <br>Encontre informações sobre eventos em vários aplicativos e serviços de nuvem cobertos pelo Microsoft Cloud App Security. Esta tabela também inclui informações disponíveis anteriormente em `AppFileEvents` .
## <a name="february-2021"></a>Fevereiro de 2021
- (Visualização) O centro de segurança [do Microsoft https://security.microsoft.com) 365 aprimorado (](https://security.microsoft.com) agora está disponível na visualização pública. Essa nova experiência traz o Defender para o Ponto de Extremidade e o Defender para Office 365 para o centro. [Saiba mais sobre o que mudou.](./overview-security-center.md)

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
- [Resposta e investigação automatizadas](mtp-autoir.md) <br> O AIR permite à sua equipe de operações de segurança aumentar drasticamente a capacidade da sua organização para lidar com alertas e incidentes de segurança.
- [Aprimoramentos avançados de busca](advanced-hunting-overview.md) <br> Busca proativamente por ameaças em todo o espaço de trabalho moderno com a Linguagem de Consulta kusto e um esquema otimizado para segurança.

## <a name="march-2019"></a>Março de 2019
- Busca avançada <br> Página inicial para vários recursos de busca que permitem que você encontre proativamente ameaças que afetam emails e dados, dispositivos e identidades.
- [Classificação de Segurança da Microsoft](microsoft-secure-score.md) <br> Medida da postura de segurança de uma organização, com um número maior indicando mais ações de melhoria tomadas. Seguir as recomendações de Pontuação de Segurança pode proteger sua organização contra ameaças. 
- [Relatórios](./overview-security-center.md) <br>  Apresenta uma série de cartões que abrangem uma variedade de áreas que os analistas de segurança e administradores acompanham como parte de suas operações diárias.