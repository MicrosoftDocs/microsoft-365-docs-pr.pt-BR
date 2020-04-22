---
title: Encontrar ameaças em dispositivos e emails usando a busca avançada
description: Estude cenários comuns de busca e consultas de exemplo que abrangem dispositivos e emails.
keywords: busca avançada, dados do Office365, dispositivos Windows, normalização de emails do Office365, emails, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, Microsoft 365, Proteção contra Ameaças da Microsoft
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
ms.openlocfilehash: ec7f9083401fdf7a2114d99ddd2dcc009411e34b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633502"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>Busca por ameaças em dispositivos e emails

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



A [busca avançada](advanced-hunting-overview.md) no Microsoft Threat Protection permite que você Cole de forma proativa por ameaças nos seus dispositivos Windows e emails da Microsoft. Aqui estão alguns cenários de busca e exemplos de consultas que podem ajudá-lo a explorar como é possível criar consultas que abrangem dispositivos e emails.

## <a name="obtain-user-accounts-from-email-addresses"></a>Adicionar contas de usuário a partir de endereços de email
Ao criar consultas em [tabelas que abrangem dispositivos e emails](advanced-hunting-schema-tables.md), provavelmente será necessário obter nomes de contas de usuário dos endereços de email de remetentes ou destinatários. Para fazer isso, use o *host local* no endereço de email:

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

Essa técnica de normalização é usada nos seguintes cenários.

## <a name="hunting-scenarios"></a>Cenários de busca

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Verificar se os arquivos de um remetente mal-intencionado conhecido estão nos seus dispositivos
Supondo que você saiba de um endereço de email que envia arquivos mal-intencionados, é possível executar essa consulta para determinar se os arquivos desse remetente existem nos seus dispositivos. Por exemplo, você pode usar essa consulta para determinar o número de dispositivos afetados por uma campanha de distribuição de malware.

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Analisar as tentativas de logon após o recebimento de emails mal-intencionados
Essa consulta localiza os 10 logons mais recentes executados pelos destinatários de email em 30 minutos depois do recebimento de emails mal-intencionados conhecidos. Você pode usar essa consulta para verificar se as contas dos destinatários de email foram comprometidas.

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Analisar as atividades do PowerShell após o recebimento de emails mal-intencionados de remetentes conhecidos
Os emails mal-intencionados geralmente contêm documentos e outros anexos especialmente criados que executam comandos do PowerShell para fornecer cargas adicionais. Se você estiver ciente de emails recebidos de um remetente mal-intencionado conhecido, poderá usar essa consulta para listar e revisar as atividades do PowerShell que ocorreram dentro de 30 minutos após o recebimento de um email do remetente.  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Entender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
