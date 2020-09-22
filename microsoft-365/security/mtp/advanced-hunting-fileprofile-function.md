---
title: Função fileprofile () em busca avançada para a proteção contra ameaças da Microsoft
description: Saiba como usar o fileprofile () para enriquecer informações sobre arquivos em seus resultados de consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, fileprofile, perfil de arquivo, função, enriquecimento
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
ms.openlocfilehash: 3fc563c762e7cd00888665b63e66159e4d3d9612
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196972"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `FileProfile()` função é uma função de enriquecimento em [busca avançada](advanced-hunting-overview.md) que adiciona os dados a seguir a arquivos encontrados pela consulta.

| Coluna | Tipo de dados | Descrição |
|------------|-------------|-------------|
| SHA1 | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| SHA256 | string | SHA-256 do arquivo ao qual a ação registrada foi aplicada |
| MD5 | string | Hash MD5 do arquivo ao qual a ação registrada foi aplicada |
| FileSize | int | Tamanho do arquivo em bytes |
| GlobalPrevalence | int | Número de instâncias da entidade observadas pela Microsoft globalmente |
| GlobalFirstSeen | datetime | Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente |
| GlobalLastSeen | datetime | Data e hora da última vez em que a entidade foi observada pela Microsoft globalmente |
| Signatário | string | Informações sobre o signatário do arquivo |
| Emissor | string | Informações sobre a CA (autoridade de certificação emissora) |
| SignerHash | string | Valor de hash exclusivo que identifica o signatário |
| IsCertificateValid | booliano | Se o certificado usado para assinar o arquivo é válido |
| IsRootSignerMicrosoft | booliano | Indica se o signatário do certificado raiz é o Microsoft |
| IsExecutable | booliano | Se o arquivo é um arquivo executável portátil (PE) |
| Threatname | string | Nome da detecção de qualquer malware ou outra ameaça encontrada |
| Publisher | string | Nome da organização que publicou o arquivo |
| SoftwareName | string | Nome do produto de software |

## <a name="syntax"></a>Sintaxe

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x** — coluna de ID de arquivo para usar: `SHA1` , `SHA256` , `InitiatingProcessSHA1` ou `InitiatingProcessSHA256` ; função usa `SHA1` se não especificado
- **y** – limitar o número de registros a enriquecer, 1-1000; função usa 100 se não especificado

## <a name="examples"></a>Exemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projetar somente a coluna SHA1 e enriquecer

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>Enriquecer os primeiros 500 registros e listar os arquivos de prevalência de baixa

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
