---
title: Tabela DeviceTvmSoftwareInventory no esquema de busca avançado
description: Saiba mais sobre o inventário de software em seus dispositivos na tabela DeviceTvmSoftwareInventory do esquema de busca avançado.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, gerenciamento de vulnerabilidades & ameaça, TVM, gerenciamento de dispositivos, software, inventário, vulnerabilidades, ID de CVE, DEVICETvmSoftwareInventoryVulnerabilities
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 18e43d8e38c24a8aa28c6455dc1a769b8da0df2b
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408618"
---
# <a name="devicetvmsoftwareinventory"></a>DeviceTvmSoftwareInventory

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

A tabela no esquema de busca avançada contém o inventário de gerenciamento de ameaças e vulnerabilidades do software atualmente instalado em dispositivos em sua rede, incluindo informações de `DeviceTvmSoftwareInventory` fim de suporte. [](next-gen-threat-and-vuln-mgt.md) Você pode, por exemplo, procurar eventos envolvendo dispositivos instalados com uma versão de software vulnerável no momento. Use esta referência para criar consultas quer retiram informações desta tabela.

DeviceTVMSoftwareInventory contém todo o software que o gerenciamento de ameaças e vulnerabilidades conseguiu corresponder a uma Enumeração de Plataforma Comum (CPE) – se está vulnerável ou não.

>[!NOTE]
>As `DeviceTvmSoftwareInventory` `DeviceTvmSoftwareVulnerabilities` tabelas e substituíram a `DeviceTvmSoftwareInventoryVulnerabilities` tabela. Juntas, as duas primeiras tabelas incluem mais colunas que você pode usar para ajudar a informar suas atividades de gerenciamento de vulnerabilidades.

Para obter informações sobre outras tabelas no esquema de busca avançada, confira [a referência de busca avançada](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `DeviceId` | string | Identificador exclusivo do dispositivo no serviço. |
| `DeviceName` | cadeia de caracteres | Nome de domínio totalmente qualificado (FQDN) do dispositivo. |
| `OSPlatform` | cadeia de caracteres | Plataforma do sistema operacional em execução no dispositivo. Isso indica os sistemas operacionais específicos, incluindo variações na mesma família, como o Windows 10 e o Windows 7. |
| `OSVersion` | string | Versão do sistema operacional em execução no dispositivo. |
| `OSArchitecture` | cadeia de caracteres | Arquitetura do sistema operacional em execução no dispositivo. |
| `SoftwareVendor` | cadeia de caracteres | Nome do fornecedor de software. |
| `SoftwareName` | cadeia de caracteres | Nome do produto de software. |
| `SoftwareVersion` | cadeia de caracteres | Número da versão do produto de software. |
| `EndOfSupportStatus` | cadeia de caracteres | Indica o estágio de ciclo de vida do produto de software em relação à data especificada de fim de suporte (EOS) ou fim de vida útil (EOL). |
| `EndOfSupportDate` | cadeia de caracteres | Data de fim de suporte (EOS) ou fim da vida útil (EOL) do produto de software. |

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
- [Visão geral do Gerenciamento de Vulnerabilidades e Ameaças](next-gen-threat-and-vuln-mgt.md)
