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
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080730"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a>Migrar consultas de busca avançada do Microsoft Defender para o Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Mova seus fluxos de trabalho de busca avançada do Microsoft Defender para o Ponto de Extremidade para procurar proativamente por ameaças usando um conjunto mais amplo de dados. No Microsoft 365 Defender, você tem acesso aos dados de outras soluções de segurança do Microsoft 365, incluindo:

- Proteção Avançada contra Ameaças do Microsoft Defender
- Microsoft Defender para Office 365
- Segurança no aplicativo na nuvem da Microsoft
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

## <a name="migrate-custom-detection-rules"></a>Migrar regras de detecção personalizadas

Quando as regras do Microsoft Defender for Endpoint são editadas no Microsoft 365 Defender, elas continuam a funcionar como antes se a consulta resultante analisasse apenas as tabelas do dispositivo. Por exemplo, alertas gerados por regras de detecção personalizadas que consultam apenas tabelas de dispositivos continuarão a ser entregues ao SIEM e gerarão notificações por email, dependendo de como você as configurou no Microsoft Defender para o Ponto de Extremidade. Quaisquer regras de supressão existentes no Defender para Ponto de Extremidade também continuarão a ser aplicadas.

Depois de editar uma regra do Defender para Ponto de Extremidade para que ele consulte as tabelas de identidade e email, que só estão disponíveis no Microsoft 365 Defender, a regra é movida automaticamente para o Microsoft 365 Defender. 

Alertas gerados pela regra migrada:

- Não estão mais visíveis no portal do Defender para Ponto de Extremidade (Central de Segurança do Microsoft Defender)
- Pare de ser entregue ao SIEM ou gere notificações por email. Para resolver essa alteração, configure as notificações por meio do Microsoft 365 Defender para receber os alertas. Você pode usar a [API do Microsoft 365 Defender](api-incident.md) para receber notificações de alertas de detecção do cliente ou incidentes relacionados.
- Não será suprimido pelo Microsoft Defender para regras de supressão de ponto de extremidade. Para impedir que alertas são gerados para determinados usuários, dispositivos ou caixas de correio, modifique as consultas correspondentes para excluir essas entidades explicitamente.

Se editar uma regra dessa maneira, você será solicitado a confirmar antes que essas alterações sejam aplicadas.

Novos alertas gerados por regras de detecção personalizadas no portal do Microsoft 365 Defender são exibidos em uma página de alerta que fornece as seguintes informações:

- Título e descrição do alerta 
- Ativos afetados
- Ações tomadas em resposta ao alerta
- Resultados de consulta que dispararam o alerta 
- Informações sobre a regra de detecção personalizada 
 
![Imagem da nova página de alerta](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a>Gravar consultas sem DeviceAlertEvents

No esquema do Microsoft 365 Defender, as tabelas e as tabelas são fornecidas para acomodar o conjunto diversificado de informações que acompanham `AlertInfo` `AlertEvidence` alertas de várias fontes. 

Para obter as mesmas informações de alerta que você usou para obter da tabela no esquema do Microsoft Defender para Ponto de Extremidade, filtre a tabela e, em seguida, insinte cada ID exclusiva na tabela, que fornece informações detalhadas de evento e `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` entidade. 

Consulte a consulta de exemplo abaixo:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

Essa consulta gera muito mais colunas do que no `DeviceAlertEvents` esquema do Microsoft Defender para Ponto de Extremidade. Para manter os resultados gerenciáveis, use para obter apenas as `project` colunas em que você está interessado. O exemplo abaixo projeta colunas em que você pode estar interessado quando a investigação detectou a atividade do PowerShell:

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

Se você quiser filtrar entidades específicas envolvidas nos alertas, poderá fazer isso especificando o tipo de entidade e o valor que você gostaria de `EntityType` filtrar. O exemplo a seguir procura um endereço IP específico:

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
- [Busca avançada no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)