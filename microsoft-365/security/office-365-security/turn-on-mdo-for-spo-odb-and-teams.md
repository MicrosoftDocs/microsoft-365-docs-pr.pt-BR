---
title: Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Os administradores podem aprender a ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams, incluindo como definir alertas para arquivos detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 07aea9551faa280cd51bda1d57f017e0a24028ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203124"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

O Microsoft Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertida de arquivos mal-intencionados. Para obter mais informações, [consulte Cofre Attachments for SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Este artigo contém as etapas para habilenciar e configurar Cofre anexos para SharePoint, OneDrive e Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com>. Para ir diretamente para a **página anexos Cofre ATP,** abra <https://protection.office.com/safeattachmentv2> .

- Para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams, você precisa ser membro dos grupos  de função  Gerenciamento da Organização ou Administrador de Segurança no Centro de Conformidade & Segurança. Para saber mais, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

- Para usar SharePoint PowerShell Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções Administrador [Global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou SharePoint [Administrador](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.

- Verifique se o log de auditoria está habilitado para sua organização. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

- Permitir até 30 minutos para que as configurações entre em vigor.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Etapa 1: Usar o Centro de Conformidade & segurança para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams

1. No Centro de Conformidade & segurança, vá para **Política** de Gerenciamento de Ameaças ATP Cofre Anexos e clique em \>  \>  **Configurações Globais**.

2. Na **configuração Global** que aparece, vá para a configuração Ativar o Defender para Office 365 **para SharePoint, OneDrive e Microsoft Teams.** Mova a alternância para a direita Para ativar a Cofre anexos para ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive e Microsoft Teams.

   Quando concluir, clique em **Salvar**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Use Exchange Online PowerShell para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams

Se você preferir usar o PowerShell para ativar o Cofre Attachments para SharePoint, OneDrive e Microsoft Teams, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Etapa 2: (Recomendado) Use SharePoint PowerShell Online para impedir que os usuários baixem arquivos mal-intencionados

Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos mal-intencionados detectados pela ATP. No entanto, eles podem excluir e baixar arquivos mal-intencionados.

Para impedir que os usuários baixem arquivos mal-intencionados, [conecte-se SharePoint PowerShell Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) e execute o seguinte comando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Observações**:

- Essa configuração afeta usuários e administradores.
- As pessoas ainda podem excluir arquivos mal-intencionados.

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Etapa 3 (Recomendado) Use o Centro de Conformidade & segurança para criar uma política de alerta para arquivos detectados

Você pode criar uma política de alerta que notifica você e outros administradores quando Cofre anexos para SharePoint, OneDrive e Microsoft Teams detecta um arquivo mal-intencionado. Para saber mais sobre alertas, consulte [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).

1. No Centro [de Conformidade & segurança,](https://protection.office.com)acesse **Políticas de** \> **Alertas ou** abra <https://protection.office.com/alertpolicies> .

2. Na página **Políticas de alerta,** clique em **Nova política de alerta.**

3. O **assistente nova política de alerta** é aberto em uma saída de emergência. Na página **Nomear seu alerta,** configure as seguintes configurações:

   - **Nome**: Digite um nome exclusivo e descritivo. Por exemplo, Arquivos Mal-intencionados em bibliotecas.
   - **Descrição**: digite uma descrição opcional. Por exemplo, Notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, OneDrive ou Microsoft Teams.
   - **Severidade**: deixe o valor padrão **Baixo** selecionado ou selecione **Médio** ou **Alto**.
   - **Selecione uma categoria**: Selecionar **Gerenciamento de ameaças.**

   Ao terminar, clique em **Avançar**.

4. Na página **Criar configurações de** alerta, configure as seguintes configurações:

   - **O que você deseja alertar?: Atividade é**: Selecionar **malware detectado no arquivo**.
   - **Como deseja que o alerta seja acionado?**: Deixar o valor padrão Sempre que uma atividade **corresponde à regra** selecionada.

   Ao terminar, clique em **Avançar**.

5. Na página **Definir seus destinatários,** configure as seguintes configurações:

   - **Enviar notificações por email**: Verifique se essa configuração está selecionada. Na caixa **Destinatários de** email, selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.
   - **Limite de notificação diário**: Deixar o valor padrão **Nenhum limite** selecionado.

   Ao terminar, clique em **Avançar**.

6. Na página **Revisar suas configurações,** revise as configurações e clique em **Editar** em qualquer uma das seções para fazer alterações.

   Na seção Deseja ativar a política **imediatamente?** Deixe o valor padrão Sim, a a ligue **imediatamente selecionada.**

   Quando terminar, clique em **Concluir**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Usar o & de Conformidade do PowerShell para criar uma política de alerta para arquivos detectados

Se você preferir usar o PowerShell para criar a mesma política de alerta conforme descrito na seção anterior &, conecte-se ao Centro de Conformidade e Segurança do [PowerShell](/powershell/exchange/connect-to-scc-powershell) e execute o seguinte comando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Observação**: o valor _padrão severity_ é Low. Para especificar Médio ou Alto, inclua o parâmetro _Severity_ e o valor no comando.

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-ActivityAlert](/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

- Para verificar se você a Cofre anexos para SharePoint, OneDrive e Microsoft Teams, use uma das seguintes etapas:

  - No Centro de Conformidade & [Segurança,](https://protection.office.com)vá para Política de Gerenciamento de Ameaças  \>  \> **Atp Cofre Anexos,** selecione Configurações globais e verifique o valor da configuração Ativar o Defender para Office 365 para **SharePoint, OneDrive** e Microsoft Teams.

  - No Exchange Online PowerShell, execute o seguinte comando para verificar a configuração da propriedade:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).

- Para verificar se você bloqueou com êxito as pessoas de baixar arquivos mal-intencionados, abra SharePoint PowerShell Online e execute o seguinte comando para verificar o valor da propriedade:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

- Para verificar se você configurou com êxito uma política de alerta para arquivos detectados, use qualquer uma das seguintes etapas:

  - No Centro de Conformidade & segurança, acesse Políticas de **Alertas** De alerta selecione a política de alerta e \>  \> verifique as configurações.

  - No Centro de Conformidade & segurança do PowerShell, substitua pelo nome da política de alerta, execute o seguinte comando e \<AlertPolicyName\> verifique os valores da propriedade:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).

- Use o [relatório de status de proteção](view-email-security-reports.md#threat-protection-status-report) contra ameaças para exibir informações sobre arquivos detectados em SharePoint, OneDrive e Microsoft Teams. Especificamente, você pode usar o **view data by: Content \> Malware** view.