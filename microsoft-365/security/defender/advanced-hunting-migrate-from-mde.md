---
title: Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade
description: Saiba como ajustar suas consultas do Microsoft Defender para Pontos de Extremidade para que você possa usá-las no Microsoft 365 Defender
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender para Ponto de Extremidade, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, mapeamento
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470683"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Mova seus fluxos de trabalho de busca avançados do Microsoft Defender para o Ponto de Extremidade para procurar proativamente ameaças usando um conjunto mais amplo de dados. No Microsoft 365 Defender, você tem acesso aos dados de outras soluções Microsoft 365 segurança, incluindo:

- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Office 365
- Microsoft Cloud App Security
- Microsoft Defender para Identidade?

>[!NOTE]
>A maioria dos clientes do Microsoft Defender para Ponto de Extremidade pode [usar o Microsoft 365 Defender sem licenças adicionais.](prerequisites.md#licensing-requirements) Para começar a fazer a transição dos fluxos de trabalho de busca avançada do Defender para o Ponto de Extremidade, a [Microsoft 365 Defender](m365d-enable.md).

Você pode fazer a transição sem afetar seus fluxos de trabalho existentes do Defender para Pontos de Extremidade. As consultas salvas permanecem intactas e as regras de detecção personalizadas continuam a ser executados e geram alertas. No entanto, eles estarão visíveis no Microsoft 365 Defender. 

## <a name="schema-tables-in-microsoft-365-defender-only"></a>Tabelas de esquema somente Microsoft 365 Defender
O [Microsoft 365 esquema](advanced-hunting-schema-tables.md) de busca avançada do Defender fornece tabelas adicionais que contêm dados de várias Microsoft 365 de segurança. As tabelas a seguir estão disponíveis apenas no Microsoft 365 Defender:

| Nome da tabela | Descrição |
|------------|-------------|
| [AlertEvidence](advanced-hunting-alertevidence-table.md) | Arquivos, endereços IP, URLs, usuários ou dispositivos associados a alertas |
| [AlertInfo](advanced-hunting-alertinfo-table.md) | Alertas do Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Office 365, Microsoft Cloud App Security e Microsoft Defender para Identidade, incluindo informações de gravidade e categorias de ameaças  |
| [EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md) | Informações sobre arquivos anexados a emails |
| [EmailEvents](advanced-hunting-emailevents-table.md) | Microsoft 365 de email, incluindo eventos de entrega de email e bloqueio |
| [EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md) | Eventos de segurança que ocorrem após a entrega, Microsoft 365 entregar os emails à caixa de correio do destinatário |
| [EmailUrlInfo](advanced-hunting-emailurlinfo-table.md) | Informações sobre URLs em emails |
| [IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md) | Eventos envolvendo um controlador de domínio local executando o Active Directory (AD). Esta tabela abrange um intervalo de eventos relacionados à identidade e eventos do sistema no controlador de domínio. |
| [IdentityInfo](advanced-hunting-identityinfo-table.md) | Informações da conta de várias fontes, incluindo Azure Active Directory |
| [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md) | Eventos de autenticação no Active Directory e serviços online da Microsoft |
| [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md) | Consultas para objetos do Active Directory, como usuários, grupos, dispositivos e domínios |

>[!IMPORTANT]
> Consultas e detecções personalizadas que usam tabelas de esquema disponíveis apenas no Microsoft 365 Defender só podem ser exibidas no Microsoft 365 Defender.

## <a name="map-devicealertevents-table"></a>Tabela Mapear DeviceAlertEvents
As `AlertInfo` `AlertEvidence` tabelas e substituem `DeviceAlertEvents` a tabela no esquema do Microsoft Defender para Ponto de Extremidade. Além dos dados sobre alertas de dispositivo, essas duas tabelas incluem dados sobre alertas para identidades, aplicativos e emails.

Use a tabela a seguir para verificar como `DeviceAlertEvents` as colunas são mapeadas para colunas `AlertInfo` nas `AlertEvidence` tabelas e.

>[!TIP]
>Além das colunas na tabela a seguir, a tabela inclui muitas outras colunas que fornecem uma imagem mais holística de `AlertEvidence` alertas de várias fontes. [Consulte todas as colunas AlertEvidence](advanced-hunting-alertevidence-table.md) 

| Coluna DeviceAlertEvents | Onde encontrar os mesmos dados no Microsoft 365 Defender |
|-------------|-----------|-------------|-------------|
| `AlertId` | `AlertInfo` e  `AlertEvidence` tabelas |
| `Timestamp` | `AlertInfo` e  `AlertEvidence` tabelas |
| `DeviceId` | `AlertEvidence` table |
| `DeviceName` | `AlertEvidence` table |
| `Severity` | `AlertInfo` table |
| `Category` | `AlertInfo` table |
| `Title` | `AlertInfo` table |
| `FileName` | `AlertEvidence` table |
| `SHA1` | `AlertEvidence` table |
| `RemoteUrl` | `AlertEvidence` table |
| `RemoteIP` | `AlertEvidence` table |
| `AttackTechniques` | `AlertInfo` table |
| `ReportId` | Esta coluna normalmente é usada no Microsoft Defender para Endpoint para localizar registros relacionados em outras tabelas. No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela. |
| `Table` | Esta coluna geralmente é usada no Microsoft Defender para Endpoint para obter informações adicionais de eventos em outras tabelas. No Microsoft 365 Defender, você pode obter dados relacionados diretamente da `AlertEvidence` tabela. |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a>Ajustar consultas existentes do Microsoft Defender para Pontos de Extremidade
As consultas do Microsoft Defender para Ponto de Extremidade funcionarão como estão, a menos que faça referência à `DeviceAlertEvents` tabela. Para usar essas consultas no Microsoft 365 Defender, aplique estas alterações:

- Substitua `DeviceAlertEvents` por `AlertInfo` .
- Participe e `AlertInfo` as `AlertEvidence` tabelas em `AlertId` para obter dados equivalentes.

### <a name="original-query"></a>Consulta original
A consulta a seguir usa o Microsoft Defender para Ponto de Extremidade para `DeviceAlertEvents` obter os alertas que envolvem _powershell.exe_:

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a>Consulta modificada
A consulta a seguir foi ajustada para uso no Microsoft 365 Defender. Em vez de verificar o nome do arquivo diretamente de , ele junta e verifica o nome do arquivo `DeviceAlertEvents` `AlertEvidence` nessa tabela.

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a>Migrar regras de detecção personalizadas

Quando as regras do Microsoft Defender para Ponto de Extremidade são editadas no Microsoft 365 Defender, elas continuam a funcionar como antes se a consulta resultante olhar apenas para tabelas de dispositivos. 

Por exemplo, alertas gerados por regras de detecção personalizadas que consultam apenas tabelas de dispositivo continuarão a ser entregues ao SIEM e gerarão notificações de email, dependendo de como você configurou isso no Microsoft Defender para Ponto de Extremidade. Quaisquer regras de supressão existentes no Defender para Ponto de Extremidade também continuarão a ser aplicadas.

Depois de editar uma regra do Defender para Ponto de Extremidade para que ela consulte as tabelas de identidade e email, que estão disponíveis apenas no Microsoft 365 Defender, a regra é movida automaticamente para o Microsoft 365 Defender. 

Alertas gerados pela regra migrada:

- Não estão mais visíveis no portal defender para ponto de extremidade (Central de Segurança do Microsoft Defender)
- Pare de ser entregue ao SIEM ou gere notificações por email. Para resolver essa alteração, configure as notificações por meio Microsoft 365 Defender para obter os alertas. Você pode usar a [API Microsoft 365 Defender](api-incident.md) para receber notificações para alertas de detecção do cliente ou incidentes relacionados.
- Não será suprimido pelo Microsoft Defender para regras de supressão de ponto de extremidade. Para evitar que alertas são gerados para determinados usuários, dispositivos ou caixas de correio, modifique as consultas correspondentes para excluir essas entidades explicitamente.

Se você editar uma regra dessa forma, será solicitado a confirmar antes que essas alterações sejam aplicadas.

Novos alertas gerados por regras de detecção personalizadas no Microsoft 365 portal do Defender são exibidos em uma página de alerta que fornece as seguintes informações:

- Título e descrição do alerta 
- Ativos afetados
- Ações tomadas em resposta ao alerta
- Resultados da consulta que dispararam o alerta 
- Informações sobre a regra de detecção personalizada 
 
> [!div class="mx-imgBorder"]
> ![Imagem da nova página de alerta](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a>Gravar consultas sem DeviceAlertEvents

No esquema Microsoft 365 Defender, as tabelas e são fornecidas para acomodar o conjunto diversificado de informações que acompanham `AlertInfo` `AlertEvidence` alertas de várias fontes. 

Para obter as mesmas informações de alerta que você usou para obter da tabela no esquema do Microsoft Defender para Ponto de Extremidade, filtre a tabela e, em seguida, participe de cada ID exclusiva com a tabela, que fornece informações detalhadas sobre eventos e `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidades. 

Consulte a consulta de exemplo abaixo:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Essa consulta gera muito mais colunas do que `DeviceAlertEvents` no esquema do Microsoft Defender para Ponto de Extremidade. Para manter os resultados gerenciáveis, use para obter apenas as colunas em `project` que você está interessado. O exemplo abaixo projeta colunas em que você pode estar interessado quando a investigação detectou a atividade do PowerShell:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Se quiser filtrar entidades específicas envolvidas nos alertas, especifique o tipo de entidade e o valor que você gostaria `EntityType` de filtrar. O exemplo a seguir procura um endereço IP específico:

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a>Confira também
- [Ativar o Microsoft 365 Defender](advanced-hunting-query-language.md)
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Busca avançada no Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)