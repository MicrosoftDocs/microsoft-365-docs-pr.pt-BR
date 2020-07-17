---
title: Tabelas de dados no esquema de busca avançada da Proteção Contra Ameaças da Microsoft
description: Aprenda sobre as tabelas no esquema de busca avançado para entender os dados nos quais você pode executar consultas de busca de ameaças.
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, dados
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
ms.openlocfilehash: 0cb275584acfc2ea0d2a2969694ee189f48a875d
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2020
ms.locfileid: "45046035"
---
# <a name="understand-the-advanced-hunting-schema"></a>Compreender o esquema de busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

O esquema de [busca avançada](advanced-hunting-overview.md) é composto por várias tabelas que fornecem informações de eventos ou informações sobre dispositivos, alertas, identidades e outros tipos de entidade. Para criar efetivamente consultas que abrangem várias tabelas, é necessário entender as tabelas e as colunas no esquema de busca avançado.

## <a name="get-schema-information-in-the-security-center"></a>Obter informações de esquema na central de segurança
Ao criar consultas, use a referência de esquema interna para obter rapidamente as seguintes informações sobre cada tabela no esquema:

- **Descrição das tabelas** — tipo de dados contido na tabela e a fonte desses dados.
- **Colunas** — todas as colunas da tabela.
- **Tipos de ação** — possíveis valores na `ActionType` coluna que representam os tipos de eventos suportados pela tabela. Isso é fornecido apenas para tabelas que contenham informações de eventos.
- **Consulta** de exemplo — exemplos de consultas que apresentam como a tabela pode ser utilizada.

### <a name="access-the-schema-reference"></a>Acessar a referência de esquema
Para acessar rapidamente a referência do esquema, selecione a ação **Exibir referência** ao lado do nome da tabela na representação do esquema. Você também pode selecionar **referência de esquema** para pesquisar uma tabela.   

![Imagem mostrando como acessar a referência de esquema no portal ](../../media/mtp-ah/ah-reference.png) 

## <a name="schema-tables"></a>Tabelas de esquema
A referência a seguir lista todas as tabelas no esquema. Cada nome de tabela se vincula a uma página que descreve os nomes das colunas da tabela. Os nomes de tabela e coluna também são listados no centro de segurança como parte da representação do esquema na tela de busca avançada.

| Nome da tabela | Descrição |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Alertas do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP, incluindo informações de gravidade e categorização de ameaças  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Atividades relacionadas a arquivos em aplicativos e serviços em nuvem |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Vários tipos de evento, incluindo eventos disparados por controles de segurança como o Windows Defender Antivirus e proteção de exploração |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Informações de certificado de arquivos assinados obtidos de eventos de verificação de certificado em pontos de extremidade |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Criação de arquivos, modificação e outros eventos do sistema de arquivos |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Carregamento de eventos DLL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Informações do computador, incluindo informações do sistema operacional |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Entradas e outros eventos de autenticação em dispositivos |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexão de rede e eventos relacionados |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propriedades de rede das máquinas, incluindo os adaptadores, os endereços IP e MAC, bem como redes e domínios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Criação de processos e eventos relacionados |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Criação e modificação de entradas do registro |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Eventos de avaliação do Gerenciamento de Vulnerabilidades e Ameaças, indicando o status de várias configurações de segurança em dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Base de dados de conhecimento de várias configurações de segurança usadas pelo Gerenciamento de Vulnerabilidades e Ameaças para avaliar dispositivos; Inclui mapeamentos para vários padrões e benchmarks  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | Inventário de software em dispositivos, bem como vulnerabilidades conhecidas nestes produtos de software |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Base de dados de conhecimento de vulnerabilidades divulgadas publicamente, incluindo se o código de exploração está disponível publicamente |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informações sobre arquivos anexados a emails |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de email da Microsoft 365, incluindo a entrega de email e eventos de bloqueio |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Eventos de segurança que ocorrem após a entrega após a Microsoft 365 ter entregue os emails para a caixa de correio de destinatário |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informações sobre URLs em emails |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Informações de conta de várias fontes, incluindo o Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventos de autenticação no Active Directory e nos serviços online da Microsoft |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Atividades de consulta executadas em objetos do Active Directory, como usuários, grupos, dispositivos e domínios |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
