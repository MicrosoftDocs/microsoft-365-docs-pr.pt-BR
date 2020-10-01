---
title: Ativar o Office 365 ATP-SharePoint, OneDrive & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Saiba como ativar a ATP para SharePoint, OneDrive e Teams, incluindo como definir alertas para arquivos detectados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326896"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Ative a ATP para SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

A proteção avançada contra ameaças do Office 365 (ATP) para o SharePoint, o OneDrive e o Microsoft Teams protege sua organização contra o compartilhamento inadvertidamente de arquivos mal-intencionados. Para obter mais informações, consulte [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).

Este artigo contém as etapas para habilitar e configurar a ATP para SharePoint, OneDrive e Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com>. Para ir diretamente para a página de **anexos seguros de ATP** , abra <https://protection.office.com/safeattachmentv2> .

- Para ativar a ATP para SharePoint, OneDrive e Microsoft Teams, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de administrador de **segurança** no centro de conformidade de & de segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

- Para usar o PowerShell do SharePoint Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções administrador [global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou [administrador do SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.

- Verifique se o log de auditoria está habilitado para sua organização. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

- Aguarde até 30 minutos para que as configurações entrem em vigor.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Etapa 1: usar o centro de conformidade de & de segurança para ativar a ATP para SharePoint, OneDrive e Microsoft Teams

1. No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** \> **Policy** \> e **anexos seguros de ATP**e clique em **configurações globais**.

2. Nas **configurações globais** que aparecem, vá para a configuração ativar a **ATP para SharePoint, onedrive e Microsoft Teams** . Mova o botão de alternância para a direita ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) para ativar a ATP para SharePoint, onedrive e Microsoft Teams.

   Quando concluir, clique em **Salvar**.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Usar o PowerShell do Exchange Online para ativar a ATP para SharePoint, OneDrive e Microsoft Teams

Se preferir usar o PowerShell para ativar a ATP para SharePoint, OneDrive e Microsoft Teams, [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Etapa 2: (recomendado) usar o SharePoint Online PowerShell para impedir que os usuários baixem arquivos mal-intencionados

Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos mal-intencionados detectados pela ATP. No entanto, eles podem excluir e baixar arquivos mal-intencionados.

Para impedir que os usuários baixem arquivos mal-intencionados, [Conecte-se ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) e execute o seguinte comando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Observações**:

- Essa configuração afeta tanto usuários quanto administradores.
- As pessoas ainda podem excluir arquivos mal-intencionados.

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Etapa 3 (recomendado) usar o centro de conformidade de & de segurança para criar uma política de alerta para arquivos detectados

Você pode criar uma política de alerta que notifique você e outros administradores quando a ATP para SharePoint, OneDrive e Microsoft Teams detectar um arquivo mal-intencionado. Para saber mais sobre alertas, confira [criar alertas de atividade no centro de conformidade de & de segurança](../../compliance/create-activity-alerts.md).

1. No [centro de conformidade & segurança](https://protection.office.com), vá para **Alerts** \> **políticas de alerta** de alertas ou abrir <https://protection.office.com/alertpolicies> .

2. Na página **políticas de alerta** , clique em **nova política de alerta**.

3. O **novo** assistente de política de alerta é aberto em uma saída. Na página **nomear o alerta** , defina as seguintes configurações:

   - **Name**: digite um nome exclusivo e descritivo. Por exemplo, arquivos mal-intencionados em bibliotecas.
   - **Descrição**: digite uma descrição opcional. Por exemplo, notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, no OneDrive ou no Microsoft Teams.
   - **Severidade**: Deixe o valor padrão **baixo** selecionado ou selecione **médio** ou **alto**.
   - **Selecione uma categoria**: selecione **Gerenciamento de ameaças**.

   Quando terminar, clique em **Avançar**.

4. Na página **criar configurações de alerta** , defina as seguintes configurações:

   - **O que você deseja alertar?: a atividade é**: selecione **malware detectado no arquivo**.
   - **Como você deseja que o alerta seja disparado?**: Deixe o valor padrão **sempre que uma atividade corresponder à regra** selecionada.

   Quando terminar, clique em **Avançar**.

5. Na página **definir seus destinatários** , defina as seguintes configurações:

   - **Enviar notificações por email**: Verifique se essa configuração está selecionada. Na caixa **destinatários de email** , selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificações quando um arquivo mal-intencionado for detectado.
   - **Limite diário de notificação**: Deixe o valor padrão **sem limite** selecionado.

   Quando terminar, clique em **Avançar**.

6. Na página **revise Your Settings** , revise as configurações e clique em **Editar** em qualquer uma das seções para fazer alterações.

   Na seção **você deseja ativar a política imediatamente?** , deixe o valor padrão **Sim, ative-o ao lado direito** .

   Quando tiver concluído, clique em **concluir**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Usar o Security & Compliance PowerShell para criar uma política de alerta para arquivos detectados

Se preferir usar o PowerShell para criar a mesma política de alerta, conforme descrito na seção anterior, [Conecte-se ao PowerShell do centro de conformidade de segurança &](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Observação**: o valor padrão de _severidade_ é baixo. Para especificar médio ou alto, inclua o parâmetro e o valor de _gravidade_ no comando.

Para informações detalhadas de sintaxes e de parâmetros, consulte [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

- Para verificar se você ativou com êxito a ATP para SharePoint, OneDrive e Microsoft Teams, use uma das seguintes etapas:

  - No [centro de conformidade & segurança](https://protection.office.com), vá para política de **Gerenciamento de ameaças** de \> **Policy** \> **anexos seguros de ATP**, selecione **configurações globais**e verifique o valor da configuração **Ativar ATP para SharePoint, onedrive e Microsoft Teams** .

  - No PowerShell do Exchange Online, execute o seguinte comando para verificar a configuração da propriedade:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Para verificar se você bloqueou com êxito as pessoas de baixar arquivos mal-intencionados, abra o PowerShell do SharePoint Online e execute o seguinte comando para verificar o valor da propriedade:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Para verificar se você configurou com êxito uma política de alerta para arquivos detectados, use qualquer uma das seguintes etapas:

  - No centro de conformidade & segurança, vá para **alertas** \> **regras** \> de alerta selecione a política de alerta e verifique as configurações.

  - Em segurança & o PowerShell do centro de conformidade, substitua o \<AlertPolicyName\> nome da política de alerta, execute o seguinte comando e verifique os valores de propriedade:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Use o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report) para exibir informações sobre arquivos detectados no SharePoint, no onedrive e no Microsoft Teams. Especificamente, você pode usar o modo de exibição **exibir dados por: conteúdo de \> malware** .
