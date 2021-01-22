---
title: Função FileProfile() em busca avançada do Microsoft 365 Defender
description: Saiba como usar o FileProfile() para enriquecer informações sobre arquivos em seus resultados de consulta de busca avançada
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929545"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A função é uma função de enriquecimento na busca avançada que adiciona os `FileProfile()` seguintes dados aos arquivos encontrados pela consulta. [](advanced-hunting-overview.md)

| Coluna | Tipo de dados | Descrição |
|------------|-------------|-------------|
| SHA1 | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| SHA256 | string | SHA-256 do arquivo ao que a ação gravada foi aplicada |
| MD5 | string | Hash MD5 do arquivo ao que a ação gravada foi aplicada |
| FileSize | int | Tamanho do arquivo em bytes |
| GlobalPrevalence | int | Número de instâncias da entidade observada pela Microsoft globalmente |
| GlobalFirstSeen | datetime | Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente |
| GlobalLastSeen | datetime | Data e hora em que a entidade foi observada pela última vez pela Microsoft globalmente |
| Signante | string | Informações sobre o signante do arquivo |
| Emissor | string | Informações sobre a autoridade de certificação (CA) de emissão |
| SignerHash | string | Valor de hash exclusivo que identifica o signante |
| IsCertificateValid | booliano | Se o certificado usado para assinar o arquivo é válido |
| IsRootSignerMicrosoft | booliano | Indica se o signante do certificado raiz é a Microsoft |
| IsExecutable | booliano | Se o arquivo é um arquivo PE (Portable Executable) |
| ThreatName | string | Nome da detecção de qualquer malware ou outras ameaças encontradas |
| Publisher | string | Nome da organização que publicou o arquivo |
| SoftwareName | string | Nome do produto de software |

## <a name="syntax"></a>Sintaxe

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x**— coluna de ID do arquivo a ser usada: , ou ; a função usa `SHA1` se não `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especificada
- **y**— limite ao número de registros a enriquecer, 1 a 1000; função usa 100 se não especificado

## <a name="examples"></a>Exemplos

### <a name="project-only-the-sha1-column-and-enrich-it"></a>Projetar somente a coluna SHA1 e enriqueci-la

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
