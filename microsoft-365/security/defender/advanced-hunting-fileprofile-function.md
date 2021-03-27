---
title: Função FileProfile() em busca avançada do Microsoft 365 Defender
description: Saiba como usar o FileProfile() para enriquecer informações sobre arquivos nos resultados avançados da consulta de busca
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, FileProfile, perfil de arquivo, função, enriquecimento
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
ms.openlocfilehash: a9ca0af0c522205309ffdcbfd1ac28638bd197c7
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382788"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A função é uma função de enriquecimento na busca avançada que adiciona os seguintes dados aos `FileProfile()` arquivos encontrados pela consulta. [](advanced-hunting-overview.md)

| Coluna | Tipo de dados | Descrição |
|------------|---------------|-------------|
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `SHA256` | cadeia de caracteres | SHA-256 do arquivo ao que a ação gravada foi aplicada |
| `MD5` | cadeia de caracteres | Hash MD5 do arquivo ao que a ação gravada foi aplicada |
| `FileSize` | int | Tamanho do arquivo em bytes |
| `GlobalPrevalence` | int | Número de instâncias da entidade observadas globalmente pela Microsoft |
| `GlobalFirstSeen` | datetime | Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente |
| `GlobalLastSeen` | datetime | Data e hora em que a entidade foi observada pela última vez pela Microsoft globalmente |
| `Signer` | cadeia de caracteres | Informações sobre o signante do arquivo |
| `Issuer` | cadeia de caracteres | Informações sobre a autoridade de certificação de emissão (CA) |
| `SignerHash` | cadeia de caracteres | Valor de hash exclusivo que identifica o signante |
| `IsCertificateValid` | booliano | Se o certificado usado para assinar o arquivo é válido |
| `IsRootSignerMicrosoft` | booliano | Indica se o signante do certificado raiz é a Microsoft |
| `SignatureState` | cadeia de caracteres | Estado da assinatura do arquivo: SignedValid - o arquivo é assinado com uma assinatura válida, SignedInvalid - o arquivo é assinado, mas o certificado é inválido, não assinado - o arquivo não está assinado, Unknown - as informações sobre o arquivo não podem ser recuperadas
| `IsExecutable` | booliano | Se o arquivo é um arquivo Executável Portátil (PE) |
| `ThreatName` | cadeia de caracteres | Nome da detecção de qualquer malware ou outras ameaças encontradas |
| `Publisher` | cadeia de caracteres | Nome da organização que publicou o arquivo |
| `SoftwareName` | string | Nome do produto de software |

## <a name="syntax"></a>Sintaxe

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x**— coluna ID de arquivo a ser usada: `SHA1` , , ou ; a função usa se não `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especificado
- **y**— limite para o número de registros a enriquecer, 1-1000; function usa 100 se não especificado


>[!TIP]
> As funções de enriquecimento mostrarão informações complementares somente quando elas estão disponíveis. A disponibilidade de informações é variada e depende de muitos fatores. Considere isso ao usar FileProfile() em suas consultas ou na criação de detecções personalizadas. Para melhores resultados, recomendamos usar a função FileProfile() com SHA1.

## <a name="examples"></a>Exemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projetar apenas a coluna SHA1 e a enriquecer

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Enriquecer os primeiros 500 registros e listar arquivos de baixa prevalência

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Obter mais exemplos de consulta](advanced-hunting-shared-queries.md)
