---
title: Tabela DeviceFileCertificateInfo no esquema de busca avançada
description: Saiba mais sobre informações de assinatura de arquivo na tabela DeviceFileCertificateInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, assinatura digital, certificado, assinatura de arquivos, DeviceFileCertificateInfo
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
ms.openlocfilehash: cba27b5b43141c8c90f9a8bc7f70c55aabc1979d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899310"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `DeviceFileCertificateInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre certificados de assinatura de arquivo. Esta tabela usa dados obtidos de atividades de verificação de certificado realizadas regularmente em arquivos de pontos de extremidade.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo da máquina no serviço |
| `DeviceName` | string | Nome de domínio totalmente qualificado (FQDN) da máquina |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `IsSigned` | booliano | Indica se o arquivo está assinado |
| `SignatureType` | string | Indica se as informações de assinatura foram lidas como conteúdo incorporado no próprio arquivo ou lidas de um arquivo de catálogo externo |
| `Signer` | string | Informações sobre o signatário do arquivo |
| `SignerHash` | string | Valor de hash exclusivo que identifica o signatário |
| `Issuer` | string | Informações sobre a CA (autoridade de certificação emissora) |
| `IssuerHash` | string | Valor de hash exclusivo que identifica a CA (autoridade de certificação) de emissão |
| `CertificateSerialNumber` | string | Identificador para o certificado que é exclusivo da autoridade de certificação (CA) de emissão |
| `CrlDistributionPointUrls` | string |  Matriz JSON que lista as URLs de compartilhamentos de rede que contêm certificados e CRLs (listas de certificados revogados) |
| `CertificateCreationTime` | datetime | Data e hora em que o certificado foi criado |
| `CertificateExpirationTime` | datetime | Data e hora em que o certificado está definido para expirar |
| `CertificateCountersignatureTime` | datetime | Data e hora em que o certificado foi assinado por ocasião |
| `IsTrusted` | booliano | Indica se o arquivo é confiável com base nos resultados da função WinVerifyTrust, que verifica informações de certificado raiz desconhecidas, assinaturas inválidas, certificados revogados e outros atributos questionáveis |
| `IsRootSignerMicrosoft` | booliano | Indica se o signatário do certificado raiz é o Microsoft |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e timestamp. | 

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
