---
title: Tabela DeviceTvmSoftwareInventory no esquema de busca avançado
description: Saiba mais sobre o inventário de software em seus dispositivos na tabela DeviceTvmSoftwareInventory do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID da CVE, OS DeviceTvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: maccruz
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 5edb6205e0392441163060aa7181ca031e1fbb0d
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50416767"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

>[!IMPORTANT]
> Algumas informações se relacionam ao produto pré-lançamento, que pode ser substancialmente modificado antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


A tabela no esquema de busca avançada contém o inventário de Gerenciamento de Vulnerabilidades & Ameaças do software atualmente instalado em dispositivos em sua rede, incluindo informações de fim `DeviceTvmSoftwareInventory` do suporte. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) Você pode, por exemplo, procurar eventos envolvendo dispositivos instalados com uma versão de software vulnerável no momento. Use esta referência para criar consultas quer retiram informações desta tabela.

>[!NOTE]
> As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela. Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidade ou a procurar dispositivos vulneráveis.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `OSPlatform` | string | Plataforma do sistema operacional em execução no computador. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `OSVersion` | string | Versão do sistema operacional em execução no computador. |
| `OSArchitecture` | string | Arquitetura do sistema operacional em execução no computador. |
| `SoftwareVendor` | string | Nome do fornecedor de software |
| `SoftwareName` | string | Nome do produto de software |
| `SoftwareVersion` | string | Número da versão do produto software |
| `EndOfSupportStatus` | string | Indica o estágio de ciclo de vida do produto de software em relação à data especificada de fim de suporte (EOS) ou fim da vida útil (EOL) |
| `EndOfSupportDate` | string | Data de fim de suporte (EOS) ou fim da vida útil (EOL) do produto de software |



## <a name="related-topics"></a>Tópicos relacionados

- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral do Gerenciamento de Vulnerabilidades e Ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
