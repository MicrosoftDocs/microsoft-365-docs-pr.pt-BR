---
title: Migrar consultas de busca avançada do Microsoft defender ATP
description: Saiba como ajustar suas consultas ATP do Microsoft defender para que você possa usá-las na proteção contra ameaças da Microsoft
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, Microsoft defender ATP, mdatp, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, Microsoft 365, mapeamento
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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1738180e192baafa60f76fada1e433319922b91
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412677"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a>Migrar consultas de busca avançada do Microsoft defender ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Mova seus fluxos de trabalho de busca avançada do Microsoft defender ATP para procurar ameaças de forma proativa usando um conjunto mais amplo de dados. Na proteção contra ameaças da Microsoft, você tem acesso a dados de outras soluções de segurança da Microsoft 365, incluindo:

- Proteção avançada contra ameaças do Microsoft Defender
- Proteção Avançada contra Ameaças do Office 365
- Segurança no aplicativo na nuvem da Microsoft
- Proteção Avançada contra Ameaças do Azure

>[!NOTE]
>A maioria dos clientes do Microsoft defender ATP pode [usar a proteção contra ameaças da Microsoft sem licenças adicionais](prerequisites.md#licensing-requirements). Para começar a fazer a transição de seus fluxos de trabalho de busca avançada do Microsoft defender ATP, [ative a proteção contra ameaças da Microsoft](mtp-enable.md).

Você pode migrar sem afetar seus fluxos de trabalho ATP existentes do Microsoft defender. As consultas salvas permanecem intactas, e as regras de detecção personalizadas continuam a executar e gerar alertas. No entanto, eles estarão visíveis na proteção contra ameaças da Microsoft. 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a>Tabelas de esquema somente na proteção contra ameaças da Microsoft
O [esquema de busca avançada da proteção contra ameaças da Microsoft](advanced-hunting-schema-tables.md) fornece tabelas adicionais contendo dados de várias soluções de segurança da Microsoft 365. As tabelas a seguir estão disponíveis somente na proteção contra ameaças da Microsoft:

| Nome da tabela | Descrição |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas do Microsoft defender ATP, Office 365 ATP, Microsoft Cloud app Security e Azure ATP, incluindo informações de gravidade e categorias de ameaças  |
| [AppFileEvents](advanced-hunting-appfileevents-table.md) | Atividades relacionadas a arquivos em aplicativos e serviços em nuvem |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informações sobre arquivos anexados a emails |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Eventos de email da Microsoft 365, incluindo a entrega de email e eventos de bloqueio |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventos de segurança que ocorrem após a entrega após a Microsoft 365 ter entregue os emails para a caixa de correio de destinatário |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informações sobre URLs em emails |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventos envolvendo um controlador de domínio local executando o Active Directory (AD). Esta tabela abrange um intervalo de eventos relacionados à identidade e eventos do sistema no controlador de domínio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Informações de conta de várias fontes, incluindo o Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventos de autenticação no Active Directory e nos serviços online da Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios |

## <a name="map-devicealertevents-table"></a>Tabela de mapas DeviceAlertEvents
As `AlertInfo` `AlertEvidence` tabelas e substituem a `DeviceAlertEvents` tabela no esquema do Microsoft defender ATP. Além dos dados sobre os alertas de dispositivos, essas duas tabelas incluem dados sobre alertas para identidades, aplicativos e emails.

Use a tabela a seguir para verificar como as `DeviceAlertEvents` colunas são mapeadas para colunas nas `AlertInfo` `AlertEvidence` tabelas e.

>[!TIP]
>Além das colunas da tabela a seguir, a `AlertEvidence` tabela inclui muitas outras colunas que oferecem uma imagem mais holística dos alertas de várias fontes. [Ver todas as colunas AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Coluna DeviceAlertEvents | Onde encontrar os mesmos dados na proteção contra ameaças da Microsoft |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo``AlertEvidence`tabelas e |
| `Timestamp` | `AlertInfo``AlertEvidence`tabelas e |
| `DeviceId` | `AlertEvidence` configurável |
| `DeviceName` | `AlertEvidence` configurável |
| `Severity` | `AlertInfo` configurável |
| `Category` | `AlertInfo` configurável |
| `Title` | `AlertInfo` configurável |
| `FileName` | `AlertEvidence` configurável |
| `SHA1` | `AlertEvidence` configurável |
| `RemoteUrl` | `AlertEvidence` configurável |
| `RemoteIP` | `AlertEvidence` configurável |
| `AttackTechniques` | `AlertInfo` configurável |
| `ReportId` | Essa coluna é normalmente usada no Microsoft defender ATP para localizar registros relacionados em outras tabelas. Na proteção contra ameaças da Microsoft, você pode obter dados relacionados diretamente da `AlertEvidence` tabela. |
| `Table` | Essa coluna é normalmente usada no Microsoft defender ATP para obter informações adicionais sobre eventos em outras tabelas. Na proteção contra ameaças da Microsoft, você pode obter dados relacionados diretamente da `AlertEvidence` tabela. |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a>Ajustar as consultas ATP existentes do Microsoft defender
As consultas ATP do Microsoft defender funcionarão como estão, a menos que façam referência à `DeviceAlertEvents` tabela. Para usar essas consultas na proteção contra ameaças da Microsoft, aplique essas alterações:

- Substituir `DeviceAlertEvents` por `AlertInfo` .
- Ingresse no `AlertInfo` e nas `AlertEvidence` tabelas `AlertId` para obter os dados equivalentes.

### <a name="original-query"></a>Consulta original
A consulta a seguir usa o `DeviceAlertEvents` Microsoft defender ATP para obter os alertas que envolvem _powershell.exe_:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Consulta modificada
A seguinte consulta foi ajustada para uso na proteção contra ameaças da Microsoft. Em vez de verificar o nome do arquivo diretamente de `DeviceAlertEvents` , ele entra `AlertEvidence` e verifica o nome do arquivo nessa tabela.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a>Tópicos relacionados
- [Habilitar a Proteção contra Ameaças da Microsoft](advanced-hunting-query-language.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Busca avançada no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)