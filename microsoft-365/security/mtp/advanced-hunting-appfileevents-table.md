---
title: Tabela AppFileEvents no esquema de busca avançada
description: Saiba mais sobre eventos relacionados a arquivos associados a serviços e aplicativos em nuvem na tabela AppFileEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, busca de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, AppFileEvents, segurança do aplicativo em nuvem, MCAS
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
ms.openlocfilehash: da3b331d4f607aa0961e275db9444aadbec4fcf2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899334"
---
# <a name="appfileevents"></a>AppFileEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `AppFileEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre atividades relacionadas a arquivos em aplicativos de nuvem e serviços monitorados pelo Microsoft Cloud app Security. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | string | Tipo de atividade que disparou o evento |
| `Application` | string | Aplicativo que executou a ação gravada |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | string | Pasta que contém o arquivo para o qual a ação registrada foi aplicada |
| `PreviousFileName` | string | O nome original do arquivo que foi renomeado como resultado da ação |
| `AccountName` | string | Nome de usuário da conta |
| `AccountDomain` | string | Domínio da conta |
| `AccountUpn` | string | Nome principal do usuário (UPN) da conta |
| `AccountObjectId` | string | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | string | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas |
| `Location` | string | Cidade, país ou outra localização geográfica associada ao evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
