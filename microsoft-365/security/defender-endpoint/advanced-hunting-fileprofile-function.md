---
title: Função FileProfile() em busca avançada do Microsoft Defender para Ponto de Extremidade
description: Saiba como usar o FileProfile() para enriquecer informações sobre arquivos nos resultados avançados da consulta de busca
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, Microsoft Defender ATP, Microsoft Defender para Ponto de Extremidade, Windows Defender, Windows Defender ATP, Windows Defender proteção avançada contra ameaças, pesquisa, consulta, telemetria, referência de esquema, kusto, FileProfile, perfil de arquivo, função, enriquecimento
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 6c828418d27db24cbd6e87f040486b3abc45e6c6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499550"
---
# <a name="fileprofile"></a>FileProfile()

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

A função é uma função de enriquecimento na busca avançada que adiciona os seguintes dados aos `FileProfile()` arquivos encontrados pela consulta. [](advanced-hunting-overview.md)

Coluna | Tipo de dados | Descrição
-|-|-
SHA1 | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada
SHA256 | string | SHA-256 do arquivo ao que a ação gravada foi aplicada
MD5 | string | Hash MD5 do arquivo ao que a ação gravada foi aplicada
FileSize | int | Tamanho do arquivo em bytes
GlobalPrevalence | int | Número de instâncias da entidade observadas globalmente pela Microsoft
GlobalFirstSeen | datetime | Data e hora em que a entidade foi observada pela primeira vez pela Microsoft globalmente
GlobalLastSeen | datetime | Data e hora em que a entidade foi observada pela última vez pela Microsoft globalmente
Signer | string | Informações sobre o signante do arquivo
Emissor | string | Informações sobre a autoridade de certificação de emissão (CA)
SignerHash | string | Valor de hash exclusivo que identifica o signante
IsCertificateValid | booliano | Se o certificado usado para assinar o arquivo é válido
IsRootSignerMicrosoft | booliano | Indica se o signante do certificado raiz é a Microsoft
IsExecutable | booliano | Se o arquivo é um arquivo Executável Portátil (PE)
ThreatName | string | Nome da detecção de qualquer malware ou outras ameaças encontradas
Publisher | string | Nome da organização que publicou o arquivo
SoftwareName | string | Nome do produto de software

## <a name="syntax"></a>Sintaxe

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>Argumentos

- **x** — coluna de ID de arquivo a ser usada: `SHA1` , ou ; a função usa se não `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` especificada
- **y** — limite para o número de registros a enriquecer, 1-1000; function usa 100 se não especificado

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
- [Compreender o esquema](advanced-hunting-schema-reference.md)
