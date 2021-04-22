---
title: Tabelas de dados no esquema de busca avançada do Microsoft 365 Defender
description: Aprenda sobre as tabelas no esquema de busca avançado para entender os dados nos quais você pode executar consultas de busca de ameaças.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, dados
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0313d1e95682d52e44cf90360c8ef322f0cad5db
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932912"
---
# <a name="understand-the-advanced-hunting-schema"></a>Compreender o esquema de busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

O [esquema de busca](advanced-hunting-overview.md) avançado é feito de várias tabelas que fornecem informações de eventos ou informações sobre dispositivos, alertas, identidades e outros tipos de entidade. Para criar efetivamente consultas que abrangem várias tabelas, é necessário entender as tabelas e as colunas no esquema de busca avançado.

## <a name="get-schema-information-in-the-security-center"></a>Obter informações de esquema no centro de segurança
Durante a construção de consultas, use a referência de esquema integrado para obter rapidamente as seguintes informações sobre cada tabela no esquema:

- **Descrição de** tabelas — tipo de dados contidos na tabela e a origem desses dados.
- **Colunas**— todas as colunas na tabela.
- **Tipos de** ação — valores possíveis na coluna `ActionType` que representam os tipos de evento suportados pela tabela. Essas informações são fornecidas apenas para tabelas que contêm informações de evento.
- **Consulta de exemplo**— consultas de exemplo que apresentam como a tabela pode ser usada.

### <a name="access-the-schema-reference"></a>Acessar a referência de esquema
Para acessar rapidamente a referência de esquema, selecione a ação **Exibir referência** ao lado do nome da tabela na representação do esquema. Você também pode selecionar **Referência de esquema** para pesquisar uma tabela.   

![Imagem mostrando como acessar a referência de esquema no portal ](../../media/mtp-ah/ah-reference.png) 

## <a name="learn-the-schema-tables"></a>Saiba as tabelas de esquema
A referência a seguir lista todas as tabelas no esquema. Cada nome de tabela se vincula a uma página que descreve os nomes das colunas da tabela. Os nomes de tabela e coluna também são listados no centro de segurança como parte da representação de esquema na tela de busca avançada.

| Nome da tabela | Descrição |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | Alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade, incluindo informações de gravidade e categorização de ameaças  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | Atividades relacionadas a arquivos em aplicativos e serviços na nuvem |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Eventos envolvendo contas e objetos no Office 365 e outros aplicativos e serviços na nuvem |
| **[Eventos do dispositivo](advanced-hunting-deviceevents-table.md)** | Vários tipos de evento, incluindo eventos disparados por controles de segurança como o Windows Defender Antivirus e proteção de exploração |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | Informações de certificado de arquivos assinados obtidos de eventos de verificação de certificado em pontos de extremidade |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | Criação de arquivos, modificação e outros eventos do sistema de arquivos |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | Carregamento de eventos DLL |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | Informações do computador, incluindo informações do sistema operacional |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | Entrar e outros eventos de autenticação em dispositivos |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | Conexão de rede e eventos relacionados |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | Propriedades de rede de dispositivos, incluindo adaptadores físicos, endereços IP e MAC, bem como redes e domínios conectados |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | Criação de processos e eventos relacionados |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | Criação e modificação de entradas do registro |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | Eventos de avaliação do Gerenciamento de Vulnerabilidades e Ameaças, indicando o status de várias configurações de segurança em dispositivos |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | Base de dados de conhecimento de várias configurações de segurança usadas pelo Gerenciamento de Vulnerabilidades e Ameaças para avaliar dispositivos; Inclui mapeamentos para vários padrões e benchmarks  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | Inventário de software instalado em dispositivos, incluindo suas informações de versão e status de fim de suporte |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | Vulnerabilidades de software encontradas em dispositivos e a lista de atualizações de segurança disponíveis que abordam cada vulnerabilidade |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | Base de dados de conhecimento de vulnerabilidades divulgadas publicamente, incluindo se o código de exploração está disponível publicamente |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | Informações sobre arquivos anexados a emails |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | Eventos de email do Microsoft 365, incluindo eventos de entrega de email e bloqueio |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Eventos de segurança que ocorrem após a entrega, após o Microsoft 365 ter entregue os emails à caixa de correio do destinatário |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | Informações sobre URLs em emails |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Eventos envolvendo um controlador de domínio local executando o Active Directory (AD). Esta tabela abrange um intervalo de eventos relacionados à identidade e eventos do sistema no controlador de domínio. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Informações da conta de várias fontes, incluindo o Azure Active Directory |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Eventos de autenticação no Active Directory e serviços online da Microsoft |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
