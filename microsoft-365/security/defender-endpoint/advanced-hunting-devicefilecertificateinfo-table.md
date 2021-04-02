---
title: Tabela DeviceFileCertificateInfo no esquema de busca avançado
description: Saiba mais sobre informações de assinatura de arquivo na tabela DeviceFileCertificateInfo do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, assinatura digital, certificado, assinatura de arquivo, DeviceFileCertificateInfo
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
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499175"
---
# <a name="devicefilecertificateinfo"></a>DeviceFileCertificateInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

A `DeviceFileCertificateInfo` tabela no esquema de busca [avançada](advanced-hunting-overview.md) contém informações sobre certificados de assinatura de arquivo. Esta tabela usa dados obtidos de atividades de verificação de certificado regularmente executadas em arquivos nos pontos de extremidade.

Para obter informações sobre outras tabelas no esquema de busca avançado, consulte [a referência avançada do esquema de busca](advanced-hunting-schema-reference.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `DeviceId` | string | Identificador exclusivo do dispositivo no serviço |
| `DeviceName` | string | FQDN (nome de domínio totalmente qualificado) do dispositivo |
| `SHA1` | cadeia de caracteres | SHA-1 do arquivo ao qual a ação gravada foi aplicada |
| `IsSigned` | booliano | Indica se o arquivo está assinado |
| `SignatureType` | string | Indica se as informações de assinatura foram lidas como conteúdo incorporado no próprio arquivo ou leitura de um arquivo de catálogo externo |
| `Signer` | string | Informações sobre o signante do arquivo |
| `SignerHash` | string | Valor de hash exclusivo que identifica o signante |
| `Issuer` | string | Informações sobre a autoridade de certificação de emissão (CA) |
| `IssuerHash` | string | Valor de hash exclusivo identificando a autoridade de certificação de emissão (CA) |
| `CertificateSerialNumber` | string | Identificador do certificado exclusivo da autoridade de certificação de emissão (CA) |
| `CrlDistributionPointUrls` | string |  Matriz JSON listando as URLs de compartilhamentos de rede que contêm certificados e listas de revogação de certificados (CRLs) |
| `CertificateCreationTime` | datetime | Data e hora em que o certificado foi criado |
| `CertificateExpirationTime` | datetime | Data e hora em que o certificado está definido para expirar |
| `CertificateCountersignatureTime` | datetime | Data e hora em que o certificado foi contra-assinado |
| `IsTrusted` | booliano | Indica se o arquivo é confiável com base nos resultados da função WinVerifyTrust, que verifica se há informações de certificado raiz desconhecidas, assinaturas inválidas, certificados revogados e outros atributos questionáveis |
| `IsRootSignerMicrosoft` | booliano | Indica se o signante do certificado raiz é a Microsoft |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp. |


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
