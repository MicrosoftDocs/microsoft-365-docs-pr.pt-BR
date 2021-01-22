---
title: Migrar consultas de busca avançada do Microsoft Defender para o Ponto de Extremidade
description: Saiba como ajustar o Microsoft Defender para consultas de ponto de extremidade para que você possa usá-las no Microsoft 365 Defender
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, microsoft defender atp, mdatp, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, microsoft 365, mapeamento
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 08bdd1e22040166bb3becac32580a185c74f34a0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932294"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrar consultas de busca avançada do Microsoft Defender para o Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Mova seus fluxos de trabalho de busca avançada do Microsoft Defender para o Ponto de Extremidade para procurar proativamente por ameaças usando um conjunto mais amplo de dados. No Microsoft 365 Defender, você tem acesso a dados de outras soluções de segurança do Microsoft 365, incluindo:

- Microsoft Defender para Ponto de Extremidade
- Obter o Microsoft Defender para Office 365
- Microsoft Cloud App Security
- Microsoft Defender para Identidade?

>[!NOTE]
>A maioria dos clientes do Microsoft Defender para Pontos de Extremidade [pode usar o Microsoft 365 Defender sem licenças adicionais.](prerequisites.md#licensing-requirements) Para começar a fazer a transição de seus fluxos de trabalho de busca avançada do Defender para o Ponto de Extremidade, [a ligue o Microsoft 365 Defender.](mtp-enable.md)

Você pode fazer a transição sem afetar o Defender existente para fluxos de trabalho do Ponto de Extremidade. As consultas salvas permanecem intactas, e as regras de detecção personalizadas continuam a ser executados e geram alertas. No entanto, eles estarão visíveis no Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tabelas de esquema somente no Microsoft 365 Defender
O [esquema de busca avançada do Microsoft 365 Defender](advanced-hunting-schema-tables.md) fornece tabelas adicionais contendo dados de várias soluções de segurança do Microsoft 365. As tabelas a seguir estão disponíveis apenas no Microsoft 365 Defender:

| Nome da tabela | Descrição |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade, incluindo informações de gravidade e categorias de ameaças  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Atividades relacionadas a arquivos em aplicativos e serviços em nuvem |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informações sobre arquivos anexados a emails |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventos de email do Microsoft 365, incluindo eventos de entrega e bloqueio de email |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventos de segurança que ocorrem após a entrega, depois que o Microsoft 365 entrega os emails para a caixa de correio do destinatário |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informações sobre URLs em emails |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventos envolvendo um controlador de domínio local executando o Active Directory (AD). Esta tabela abrange uma variedade de eventos relacionados à identidade e eventos do sistema no controlador de domínio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Informações da conta de várias fontes, incluindo o Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventos de autenticação no Active Directory e nos serviços online da Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios |

## <a name="map-devicealertevents-table"></a>Tabela Mapear DeviceAlertEvents
The `AlertInfo` and tables replace the table in the Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint schema. Além dos dados sobre alertas de dispositivo, essas duas tabelas incluem dados sobre alertas de identidades, aplicativos e emails.

Use a tabela a seguir para verificar como `DeviceAlertEvents` as colunas são mapeadas para colunas nas `AlertInfo` tabelas e `AlertEvidence` tabelas.

>[!TIP]
>Além das colunas da tabela a seguir, a tabela inclui muitas outras colunas que fornecem uma imagem mais holística dos `AlertEvidence` alertas de várias fontes. [Ver todas as colunas AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Coluna DeviceAlertEvents | Onde encontrar os mesmos dados no Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` e  `AlertEvidence` tabelas |
| `Timestamp` | `AlertInfo` e  `AlertEvidence` tabelas |
| `DeviceId` | `AlertEvidence` tabela |
| `DeviceName` | `AlertEvidence` tabela |
| `Severity` | `AlertInfo` tabela |
| `Category` | `AlertInfo` tabela |
| `Title` | `AlertInfo` tabela |
| `FileName` | `AlertEvidence` tabela |
| `SHA1` | `AlertEvidence` tabela |
| `RemoteUrl` | `AlertEvidence` tabela |
| `RemoteIP` | `AlertEvidence` tabela |
| `AttackTechniques` | `AlertInfo` tabela |
| `ReportId` | Essa coluna é normalmente usada no Microsoft Defender para o Ponto de Extremidade para localizar registros relacionados em outras tabelas. No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela. |
| `Table` | Essa coluna é normalmente usada no Microsoft Defender para o Ponto de Extremidade para obter informações adicionais sobre o evento em outras tabelas. No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Ajustar o Microsoft Defender existente para consultas de ponto de extremidade
As consultas do Microsoft Defender para Pontos de Extremidade funcionarão como estão, a menos que elas faça referência à `DeviceAlertEvents` tabela. Para usar essas consultas no Microsoft 365 Defender, aplique estas alterações:

- Substitua `DeviceAlertEvents` por `AlertInfo` .
- `AlertInfo`Junte-se a e às `AlertEvidence` tabelas para obter dados `AlertId` equivalentes.

### <a name="original-query"></a>Consulta original
A consulta a seguir `DeviceAlertEvents` usa no Microsoft Defender for Endpoint para obter os alertas que envolvem _powershell.exe:_

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Consulta modificada
A consulta a seguir foi ajustada para uso no Microsoft 365 Defender. Em vez de verificar o nome do arquivo diretamente de , ele `DeviceAlertEvents` se une e verifica o nome do arquivo nessa `AlertEvidence` tabela.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Tópicos relacionados
- [Ativar o Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Busca avançada no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)