---
title: Tabela CloudAppEvents no esquema de busca avançado
description: Saiba mais sobre eventos de aplicativos e serviços de nuvem na tabela CloudAppEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, CloudAppEvents, Cloud App Security, MCAS
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a8ba1f94bc704a5fe99d54b77aa6570c5e43d3f7
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712481"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A tabela no esquema de busca avançada contém informações sobre atividades em vários aplicativos e serviços de nuvem cobertos pelo Microsoft Cloud App Security, especificamente `CloudAppEvents` Dropbox, Exchange Online, OneDrive, Microsoft Teams e SharePoint. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!IMPORTANT]
>Esta tabela inclui informações que costumavam estar disponíveis na `AppFileEvents` tabela. A partir de 7 de março de 2021, os usuários que pesquisam atividades relacionadas a arquivos em serviços de nuvem dentro e fora dessa data devem usar a `CloudAppEvents` tabela. <br><br>Procure por consultas e regras de detecção personalizadas que ainda usem a tabela e `AppFileEvents` edite-as para usar a `CloudAppEvents` tabela. Mais orientações sobre a conversão de consultas afetadas podem ser encontradas em [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).


Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento |
| `Application` | cadeia de caracteres | Aplicativo que realizou a ação gravada |
| `ApplicationId` | cadeia de caracteres | Identificador exclusivo do aplicativo |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure Active Directory |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome. |
| `IsAdminOperation` | cadeia de caracteres | Indica se a atividade foi executada por um administrador |
| `DeviceType` | cadeia de caracteres | Tipo de dispositivo com base na finalidade e funcionalidade, como "Dispositivo de rede", "Estação de Trabalho", "Servidor", "Mobile", "Console de Jogos" ou "Impressora" | 
| `OSPlatform` | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Esta coluna indica sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | cadeia de caracteres | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas |
| `IsAnonymousProxy` | cadeia de caracteres | Indica se o endereço IP pertence a um proxy anônimo conhecido |
| `CountryCode` | cadeia de caracteres | Código de duas letras indicando o país onde o endereço IP do cliente está geolocado |
| `City` | cadeia de caracteres | Cidade onde o endereço IP do cliente está geolocado |
| `Isp` | cadeia de caracteres | Provedor de serviços de Internet (ISP) associado ao endereço IP |
| `UserAgent` | cadeia de caracteres | Informações do agente do usuário do navegador da Web ou de outro aplicativo cliente |
| `ActivityType` | cadeia de caracteres | Tipo de atividade que disparou o evento |
| `ActivityObjects` | cadeia de caracteres | Lista de objetos, como arquivos ou pastas, que estavam envolvidos na atividade gravada |
| `ObjectName` | cadeia de caracteres | Nome do objeto ao que a ação gravada foi aplicada |
| `ObjectType` | cadeia de caracteres | Tipo de objeto, como um arquivo ou uma pasta, ao qual a ação gravada foi aplicada |
| `ObjectId` | cadeia de caracteres | Identificador exclusivo do objeto ao que a ação gravada foi aplicada |
| `ReportId` | cadeia de caracteres | Identificador exclusivo do evento |
| `RawEventData` | cadeia de caracteres | Informações de evento brutos do aplicativo ou serviço de origem no formato JSON |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou evento |


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
