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
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204750"
---
# <a name="appfileevents"></a>AppFileEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `AppFileEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre atividades relacionadas a arquivos em aplicativos de nuvem e serviços monitorados pelo Microsoft Cloud app Security. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento |
| `Application` | cadeia de caracteres | Aplicativo que executou a ação gravada |
| `FileName` | cadeia de caracteres | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | cadeia de caracteres | Pasta que contém o arquivo para o qual a ação registrada foi aplicada |
| `PreviousFileName` | cadeia de caracteres | O nome original do arquivo que foi renomeado como resultado da ação |
| `PreviousFolderPath` | cadeia de caracteres | Pasta original contendo o arquivo antes da aplicação da ação gravada |
| `Protocol` | cadeia de caracteres | Protocolo de rede usado |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no catálogo de endereços. Normalmente, uma combinação de um determinado nome ou primeiro, um início do meio e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `DeviceType` | cadeia de caracteres | Tipo de dispositivo | 
| `OSPlatform` | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | cadeia de caracteres | Endereço IP atribuído ao ponto de extremidade e usado durante as comunicações de rede relacionadas |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo que executa o aplicativo de servidor que processou a ação registrada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo que está executando o aplicativo de servidor que processou a ação registrada |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | cadeia de caracteres | Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou o evento |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
