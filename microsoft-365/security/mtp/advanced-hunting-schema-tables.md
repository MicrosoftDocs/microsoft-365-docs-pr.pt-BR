---
title: Tabelas de dados no esquema de busca avançada da Proteção Contra Ameaças da Microsoft
description: Aprenda sobre as tabelas no esquema de busca avançado para entender os dados nos quais você pode executar consultas de busca de ameaças.
keywords: caça avançada, caça de ameaças, caça de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 631b328168003668ed06e37d76177c327794ed18
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808656"
---
# <a name="understand-the-advanced-hunting-schema"></a>Compreender o esquema de busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

O [esquema de busca avançada](advanced-hunting-overview.md) é formado por várias tabelas que fornecem informações sobre o evento ou informações sobre computadores e entidades. Para criar efetivamente consultas que abrangem várias tabelas, é necessário entender as tabelas e as colunas no esquema de busca avançado.

## <a name="schema-tables"></a>Tabelas de esquema

A referência a seguir lista todas as tabelas no esquema. Cada nome de tabela se vincula a uma página que descreve os nomes das colunas da tabela. Os nomes de tabela e coluna também são listados no centro de segurança como parte da representação do esquema na tela de busca avançada.

| Nome da tabela | Descrição |
|------------|-------------|
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Informações do computador, incluindo informações do sistema operacional |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propriedades de rede das máquinas, incluindo os adaptadores, os endereços IP e MAC, bem como redes e domínios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Criação de processos e eventos relacionados |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexão de rede e eventos relacionados |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Criação de arquivos, modificação e outros eventos do sistema de arquivos |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Criação e modificação de entradas do registro |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Entradas e outros eventos de autenticação |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Carregamento de eventos DLL |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Vários tipos de evento, incluindo eventos disparados por controles de segurança como o Windows Defender Antivirus e proteção de exploração |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de email do Office 365, incluindo a entrega de email e eventos de bloqueio |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informações sobre arquivos anexados a emails do Office 365 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informações sobre URLs nos emails do Office 365 |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventário de software em dispositivos, bem como vulnerabilidades conhecidas nestes produtos de software |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | Base de dados de conhecimento de vulnerabilidades divulgadas publicamente, incluindo se o código de exploração está disponível publicamente |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | Eventos de avaliação do Gerenciamento de Vulnerabilidades e Ameaças, indicando o status de várias configurações de segurança em dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Base de dados de conhecimento de várias configurações de segurança usadas pelo Gerenciamento de Vulnerabilidades e Ameaças para avaliar dispositivos; Inclui mapeamentos para vários padrões e benchmarks  |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
