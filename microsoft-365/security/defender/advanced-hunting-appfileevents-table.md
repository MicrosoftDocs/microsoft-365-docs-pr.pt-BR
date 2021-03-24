---
title: Tabela AppFileEvents no esquema de busca avançado
description: Saiba mais sobre eventos relacionados a arquivos associados a aplicativos e serviços de nuvem na tabela AppFileEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, AppFileEvents, Cloud App Security, MCAS
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f25570916692c4568a6d09d92faaf57b0c155029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053234"
---
# <a name="appfileevents"></a>AppFileEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançado contém informações sobre atividades relacionadas a arquivos em aplicativos e serviços de nuvem `AppFileEvents` monitorados pelo Microsoft Cloud App Security. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!WARNING]
>Esta tabela será retirada em breve. A partir de 7 de março de 2021, a `AppFileEvents` tabela não é mais registro em log. Os usuários que pesquisam atividades relacionadas a arquivos em serviços de nuvem, em vez disso, devem usar a tabela [CloudAppEvents.](advanced-hunting-cloudappevents-table.md) <br><br>Procure por consultas e regras de detecção personalizadas que ainda usem a tabela e `AppFileEvents` edite-as para usar a `CloudAppEvents` tabela. Mais orientações sobre a conversão de consultas afetadas podem ser encontradas em [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).


Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento. Consulte a [referência de esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) no portal para obter detalhes |
| `Application` | cadeia de caracteres | Aplicativo que realizou a ação gravada |
| `FileName` | cadeia de caracteres | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FolderPath` | cadeia de caracteres | Pasta que contém o arquivo ao que a ação gravada foi aplicada |
| `PreviousFileName` | cadeia de caracteres | Nome original do arquivo que foi renomeado como resultado da ação |
| `PreviousFolderPath` | cadeia de caracteres | Pasta original que contém o arquivo antes da ação gravada ser aplicada |
| `Protocol` | cadeia de caracteres | Protocolo de rede usado |
| `AccountName` | cadeia de caracteres | Nome de usuário da conta |
| `AccountDomain` | cadeia de caracteres | Domínio da conta |
| `AccountSid` | cadeia de caracteres | Identificador de Segurança (SID) da conta |
| `AccountUpn` | cadeia de caracteres | Nome principal do usuário (UPN) da conta |
| `AccountObjectId` | cadeia de caracteres | Identificador exclusivo da conta no Azure AD |
| `AccountDisplayName` | cadeia de caracteres | Nome do usuário da conta exibido no livro de endereços. Normalmente, uma combinação de um nome ou nome determinado, uma iniciação intermediária e um sobrenome ou sobrenome. |
| `DeviceName` | cadeia de caracteres | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `DeviceType` | cadeia de caracteres | Tipo de dispositivo | 
| `OSPlatform` | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `IPAddress` | string | Endereço IP atribuído ao ponto de extremidade e usado durante comunicações de rede relacionadas |
| `Port` | cadeia de caracteres | Porta TCP usada durante a comunicação  |
| `DestinationDeviceName` | cadeia de caracteres | Nome do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationIPAddress` | cadeia de caracteres | Endereço IP do dispositivo que executa o aplicativo de servidor que processou a ação gravada |
| `DestinationPort` | cadeia de caracteres | Porta de destino de comunicações de rede relacionadas |
| `Location` | cadeia de caracteres | Cidade, país ou outra localização geográfica associada ao evento |
| `Isp` | cadeia de caracteres | Provedor de serviços de Internet (ISP) associado ao endereço IP do ponto de extremidade |
| `ReportId` | long | Identificador exclusivo do evento |
| `AdditionalFields` | cadeia de caracteres | Informações adicionais sobre a entidade ou evento |

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
