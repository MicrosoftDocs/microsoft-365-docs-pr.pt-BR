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
ms.openlocfilehash: 0b28cf2ce96e4c040fac0999d669623cef066fe4
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929487"
---
# <a name="understand-the-advanced-hunting-schema"></a>Compreender o esquema de busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



O [esquema de busca avançada](advanced-hunting-overview.md) é formado por várias tabelas que fornecem informações sobre o evento ou informações sobre computadores e entidades. Para criar efetivamente consultas que abrangem várias tabelas, é necessário entender as tabelas e as colunas no esquema de busca avançado.

## <a name="schema-tables"></a>Tabelas de esquema

A referência a seguir lista todas as tabelas no esquema. Cada nome de tabela se vincula a uma página que descreve os nomes das colunas da tabela. Os nomes de tabela e coluna também são listados no centro de segurança como parte da representação do esquema na tela de busca avançada.

| Nome da tabela | Descrição |
|------------|-------------|
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Alertas do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP, incluindo informações de gravidade e categorização de ameaças  |
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas |
| **[AccountInfo](advanced-hunting-accountinfo-table.md)** | Informações de conta de várias fontes, incluindo o Azure Active Directory |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de email do Office 365, incluindo a entrega de email e eventos de bloqueio |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informações sobre arquivos anexados a emails do Office 365 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informações sobre URLs nos emails do Office 365 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Informações do computador, incluindo informações do sistema operacional |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propriedades de rede das máquinas, incluindo os adaptadores, os endereços IP e MAC, bem como redes e domínios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Criação de processos e eventos relacionados |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexão de rede e eventos relacionados |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Criação de arquivos, modificação e outros eventos do sistema de arquivos |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Criação e modificação de entradas do registro |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Entradas e outros eventos de autenticação |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Carregamento de eventos DLL |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Vários tipos de evento, incluindo eventos disparados por controles de segurança como o Windows Defender Antivirus e proteção de exploração |
| **[DeviceFileCertificateInfoBeta](advanced-hunting-devicefilecertificateinfobeta-table.md)** | Informações de certificado de arquivos assinados obtidos de eventos de verificação de certificado em pontos de extremidade |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-tvm-softwareinventory-table.md)** | Inventário de software em dispositivos, bem como vulnerabilidades conhecidas nestes produtos de software |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-tvm-softwarevulnerability-table.md)** | Base de dados de conhecimento de vulnerabilidades divulgadas publicamente, incluindo se o código de exploração está disponível publicamente |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-tvm-configassessment-table.md)** | Eventos de avaliação do Gerenciamento de Vulnerabilidades e Ameaças, indicando o status de várias configurações de segurança em dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-tvm-secureconfigkb-table.md)** | Base de dados de conhecimento de várias configurações de segurança usadas pelo Gerenciamento de Vulnerabilidades e Ameaças para avaliar dispositivos; Inclui mapeamentos para vários padrões e benchmarks  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Atividades relacionadas a arquivos em aplicativos e serviços em nuvem |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventos de autenticação registrados pelo Active Directory e outros serviços online da Microsoft |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Atividades de consulta executadas em objetos do Active Directory, como usuários, grupos, dispositivos e domínios |


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
