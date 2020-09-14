---
title: Gerenciar políticas de retenção de log de auditoria
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: As políticas de retenção de log de auditoria fazem parte dos novos recursos Avançados de Auditoria no Microsoft 365. Uma política de retenção de log de auditoria permite especificar por quanto tempo reter os logs de auditoria em sua organização.
ms.openlocfilehash: a657e3cac4c6b0620d7c5c69247154776ce60ffe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547015"
---
# <a name="manage-audit-log-retention-policies"></a>Gerenciar políticas de retenção de log de auditoria

Você pode criar e gerenciar políticas de retenção de log de auditoria no Centro de Conformidade e Segurança. As políticas de retenção de log de auditoria fazem parte dos novos recursos Avançados de Auditoria no Microsoft 365. Uma política de retenção de log de auditoria permite especificar por quanto tempo reter os logs de auditoria em sua organização. Você pode manter os logs de auditoria por até um ano. Você pode criar políticas com base nos critérios a seguir:

- Todas as atividades em um ou mais serviços do Microsoft 365

- As atividades específicas (em um serviço específico) executadas por todos os usuários ou por usuários específicos

- Um nível de prioridade que especifica qual política tem precedência se você tiver várias políticas em sua organização

## <a name="default-audit-log-retention-policy"></a>Política de retenção de log de auditoria padrão

A Auditoria Avançada no Microsoft 365 fornece uma política de retenção de log de auditoria padrão para todas as organizações. Essa política mantém todos os registros de auditoria do Exchange, do SharePoint e do Azure Active Directory por um ano. Essa política padrão mantém registros de auditoria que contêm o valor do **AzureActiveDirectory**, **Exchange** ou **SharePoint** para a propriedade **Carga de trabalho** (que é o serviço em que a atividade ocorreu). A política padrão não pode ser modificada. Confira a seção [Mais informações](#more-information) neste artigo para obter uma lista de tipos de registro para cada carga de trabalho inclusa na política padrão.

> [!NOTE]
> A política de retenção do log de auditoria padrão aplica-se somente a registros de auditoria para atividades executadas por usuários que receberam uma licença do Office 365 ou Microsoft 365 E5 ou têm uma licença complementar da Conformidade do Microsoft 365 E5. Se você tiver usuários que não têm o E5 em sua organização, seus registros de auditoria correspondentes serão mantidos por 90 dias.

## <a name="before-you-create-an-audit-log-retention-policy"></a>Antes de você criar uma política de retenção de log de auditoria

- É preciso estar na função de Configuração da Organização no Centro de Conformidade e Segurança para criar ou modificar uma política de retenção de auditoria.

- Você pode ter até 50 políticas de retenção de log de auditoria em sua organização.

- Para manter um log de auditoria por mais de 90 dias, o usuário que gerou o log de auditoria deve ter uma licença do Office 365 E5 ou do Microsoft 365 E5, ou ter uma licença complementar do Microsoft 365 E5 Compliance ou do E5 eDiscovery.

- Todas as políticas de retenção de log de auditoria personalizadas (criadas por sua organização) têm prioridade sobre a política de retenção padrão. Por exemplo, se você criar uma política de retenção de log de auditoria para a atividade de caixa de correio do Exchange que tenha um período de retenção menor que um ano, os registros de auditoria para as atividades de caixa de correio serão mantidos por um período menor especificado pela política personalizada.

## <a name="create-an-audit-log-retention-policy-in-the-compliance-center"></a>Criar uma política de retenção de log de auditoria no Centro de Conformidade

1. Vá para [https://protection.office.com](https://protection.office.com) e entre com a conta de usuário a qual a função de Configuração da Organização foi atribuída no Centro de Conformidade e Segurança.

2. No painel esquerdo do Centro de Conformidade e Segurança, clique em **Pesquisar** > **Pesquisa de log de auditoria**.

    É exibida a página **Pesquisa de log de auditoria**.

    ![A página de pesquisa de log de auditoria](../media/AuditLogRetentionPolicy1.png)

3. Clique em **Nova política de retenção de auditoria** e preencha os seguintes campos na página do submenu:

    ![Página do submenu da política de retenção de auditoria](../media/AuditLogRetentionPolicy2.png)

   a. **Nome:** o nome da política de retenção de log de auditoria.  Este nome deve ser exclusivo em sua organização.

   b. **Descrição:** opcional, mas útil para fornecer informações sobre a política, como o tipo de registro ou a carga de trabalho, os usuários especificados na política e a duração.

   c. **Tipos de registro:** o tipo de registro de auditoria ao qual a política se aplica. Se você selecionar mais de um tipo de registro, não será possível selecionar atividades porque a política será aplicada a todas as atividades para os tipos de registro selecionados. Além disso, se você deixar essa propriedade em branco, deve selecionar um usuário na caixa **Usuários**. 

   d. **Atividades:** use essa caixa para selecionar atividades do tipo de registro selecionado. Você pode escolher atividades específicas nas quais aplicar a política. Se você não consegue selecionar especificas, a política será aplicada a todas as atividades do tipo de registro selecionado.

   e. **Usuários:** selecione um ou mais usuários aos quais aplicar a política. Se você deixar essa caixa em branco, a política será aplicada a todos os usuários. Se você deixar os **Tipos de registro** em branco, deve selecionar um usuário.

   f. **Duração:** o tempo necessário para manter os logs de auditoria que atendem aos critérios da política.

   g. **Prioridade:** esse valor determinar a ordem na qual as políticas de retenção de log de auditoria são processadas na sua organização. Um valor mais alto indica uma prioridade mais alta. Por exemplo, uma política com um valor de prioridade de **5** teria prioridade sobre uma política com um valor de prioridade **0**. Como explicado anteriormente, qualquer política de retenção de log de auditoria personalizada tem prioridade sobre a política padrão da sua organização.

4. Clique em **Salvar** para criar a nova política de retenção.

Neste momento, não há nenhuma indicação de que a política de retenção foi criada com êxito. Confira a próxima seção sobre como visualizar as propriedades das políticas de retenção de log de auditoria.

## <a name="create-an-audit-log-retention-policy-in-powershell"></a>Criar uma política de retenção de log de auditoria no PowerShell

Você também pode usar o PowerShell do Centro de conformidade e segurança para criar políticas de retenção de log de auditoria. 

1. [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Execute o seguinte comando para criar uma política de retenção de log de auditoria. 

   ```powershell
   New-UnifiedAuditLogRetentionPolicy -Name "Microsoft Teams Audit Policy" -Description "One year retention policy for all Microsoft Teams activities" -RecordTypes MicrosoftTeams -RetentionDuration TwelveMonths -Priority 100
   ```

    Este exemplo cria uma política de retenção de log de auditoria chamada “Política de Auditoria do Microsoft Teams” com as seguintes configurações:

   - Uma descrição da política.

   - Retém todas as atividades do Microsoft Teams (conforme definido pelo parâmetro *RecordType*).

   - Retém os logs de auditoria do Microsoft Teams por um ano.

   - Prioridade de 100.

Veja outro exemplo de como criar uma política de retenção de log de auditoria. Essa política mantém os logs de auditoria para a atividade “Usuário conectado” por seis meses para o usuário admin@contoso.onmicrosoft.com.

```powershell
New-UnifiedAuditLogRetentionPolicy -Name "SixMonth retention for admin logons" -RecordTypes AzureActiveDirectoryStsLogon -Operations UserLoggedIn -UserIds admin@contoso.onmicrosoft.com -RetentionDuration SixMonths -Priority 25
```

Para saber mais, confira [New-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/new-unifiedauditlogretentionpolicy).

## <a name="view-audit-log-retention-policies"></a>Visualizar as políticas de retenção de log de auditoria

No momento, a única maneira de visualizar as políticas de retenção de log de auditoria personalizadas é usar o cmdlet **Get-UnifiedAuditRetentionPolicy** no PowerShell do Centro de Conformidade e Segurança. Veja um comando de exemplo para exibir as configurações (que você configurou na etapa anterior) para as políticas de retenção de log de auditoria em sua organização. Esse comando classifica as políticas da prioridade mais alta para a mais baixa.

```powershell
Get-UnifiedAuditLogRetentionPolicy | Sort-Object -Property Priority -Descending | FL Priority,Name,Description,RecordTypes,Operations,UserIds,RetentionDuration
```

> [!NOTE]
> No momento, o cmdlet **Get-UnifiedAuditLogRetentionPolicy** não retorna a política de log de auditoria padrão da sua organização.

Para saber mais, confira [Get-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-unifiedauditlogretentionpolicy).

## <a name="more-information"></a>Mais informações

- Use o cmdlet **Set-UnifiedAuditLogRetentionPolicy** no PowerShell do Centro de Conformidade e Segurança para modificar uma política de retenção de log de auditoria existente. Para saber mais, confira [Set-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-unifiedauditlogretentionpolicy).

- Use o cmdlet **Remove-UnifiedAuditLogRetentionPolicy** no PowerShell do Centro de Conformidade e Segurança para excluir uma política de retenção de log de auditoria. Pode levar até 30 minutos para a política ser removida. Para saber mais, confira [Remove-UnifiedAuditLogRetentionPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-unifiedauditlogretentionpolicy).

- Conforme dito anteriormente, os registros de auditoria para operações no Azure Active Directory, no Exchange e no SharePoint são mantidos por um ano. A seguinte tabela lista todos os tipos de registro (para cada um desses serviços) incluídos na política de retenção de log de auditoria padrão. Isso significa que os logs de auditoria para qualquer operação com esse tipo de registro são mantidos por um ano, a menos que uma política de retenção de log de auditoria personalizada tenha precedência sobre um tipo específico de registro, uma operação ou usuário. O valor de enumeração (que é exibido como o valor da propriedade RecordType em um registro de auditoria) para cada tipo de registro é mostrado entre parênteses.

   |AzureActiveDirectory |Exchange  |SharePoint|
   |:---------|:---------|:---------|
   |AzureActiveDirectory (8)|ExchangeAdmin (1)|ComplianceDLPSharePoint (11)|
   |AzureActiveDirectoryAccountLogon (9)|ExchangeItem (2)|ComplianceDLPSharePointClassification (33)|
   |AzureActiveDirectoryStsLogon (15)|Campaign (62)|Project (35)|
   ||ComplianceDLPExchange (13)|SharePoint (4)|
   ||ComplianceSupervisionExchange (68)|SharePointCommentOperation (37)|
   ||CustomerKeyServiceEncryption (69)|SharePointContentTypeOperation (55)|
   ||ExchangeAggregatedOperation (19)|SharePointFieldOperation (56)|
   ||ExchangeItemAggregated (50)|SharePointFileOperation (6)|
   ||ExchangeItemGroup (3)|SharePointListOperation (36)|
   ||InformationBarrierPolicyApplication (53)|SharePointSharingOperation (14)|
   ||||
