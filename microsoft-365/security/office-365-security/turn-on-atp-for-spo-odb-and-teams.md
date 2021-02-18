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
description: Os administradores podem aprender a ativar anexos seguros para o SharePoint, o OneDrive e o Microsoft Teams, incluindo como definir alertas para arquivos detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286364"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

O Microsoft Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertido de arquivos mal-intencionados. Para saber mais, confira [Anexos seguros para SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Este artigo contém as etapas de habilitação e configuração de Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com>. Para ir diretamente para a página Anexos Seguros da **ATP,** <https://protection.office.com/safeattachmentv2> abra.

- Para ativar anexos seguros para o SharePoint, o OneDrive e o  Microsoft  Teams &, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador de Segurança no Centro de Conformidade e Segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

- Para usar o PowerShell do SharePoint Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções Administrador [Global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou Administrador do [SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.

- Verifique se o log de auditoria está habilitado para sua organização. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

- Permita até 30 minutos para que as configurações entrem em vigor.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Etapa 1: Usar o Centro de Conformidade e Segurança & para ativar o Serviço de Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams

1. No Centro de Conformidade & Segurança,  vá para Anexos Seguros da ATP da Política de Gerenciamento de Ameaças e clique em \>  \>  **Configurações Globais.**

2. No menu **Configurações** globais exibido, vá para a configuração Ativar o Defender para **Office 365 para SharePoint, OneDrive** e Microsoft Teams. Mova o alternância para a direita para ativar Anexos Seguros para ![ ](../../media/scc-toggle-on.png) SharePoint, OneDrive e Microsoft Teams.

   Quando concluir, clique em **Salvar**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Usar o PowerShell do Exchange Online para ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams

Se você preferir usar o PowerShell para ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams, conecte-se ao [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Etapa 2: (Recomendado) Usar o PowerShell do SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados

Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos mal-intencionados detectados pela ATP. No entanto, eles podem excluir e baixar arquivos mal-intencionados.

Para impedir que os usuários baixem arquivos mal-intencionados, [conecte-se ao PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) do SharePoint Online e execute o seguinte comando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Observações**:

- Essa configuração afeta usuários e administradores.
- As pessoas ainda podem excluir arquivos mal-intencionados.

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Etapa 3 (Recomendado) Usar o Centro de Conformidade e Segurança & para criar uma política de alerta para arquivos detectados

Você pode criar uma política de alerta que notifica você e outros administradores quando o serviço Anexos Seguros do SharePoint, OneDrive e Microsoft Teams detecta um arquivo mal-intencionado. Para saber mais sobre alertas, consulte [Criar alertas de atividade no Centro de conformidade & segurança.](../../compliance/create-activity-alerts.md)

1. In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies> .

2. Na página **Políticas de alerta,** clique em **Nova política de alerta.**

3. O **assistente nova política de** alerta é aberto em um fly out. Na página **Nomear seu alerta,** de configure as seguintes configurações:

   - **Nome:** digite um nome exclusivo e descritivo. Por exemplo, arquivos mal-intencionados em bibliotecas.
   - **Descrição:** digite uma descrição opcional. Por exemplo, notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, No OneDrive ou no Microsoft Teams.
   - **Gravidade:** deixe o valor **padrão** Baixo selecionado ou selecione **Médio** ou **Alto.**
   - **Selecione uma categoria:** Selecione **Gerenciamento de ameaças.**

   Quando terminar, clique em **Avançar**.

4. Na página **Criar configurações de alerta,** de configure as seguintes configurações:

   - **O que você deseja alertar?: Atividade é:** Selecionar **malware detectado no arquivo.**
   - **Como você deseja que o alerta seja disparado?**: Deixe o valor padrão Sempre que uma **atividade corresponde à regra** selecionada.

   Quando terminar, clique em **Avançar**.

5. Na página **Definir seus destinatários,** de configure as seguintes configurações:

   - **Enviar notificações por email:** verifique se essa configuração está selecionada. Na caixa **Destinatários de email,** selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.
   - **Limite de notificação** diária: deixe o valor padrão **Sem limite** selecionado.

   Quando terminar, clique em **Avançar**.

6. Na página **Revisar suas configurações,** revise as configurações e clique em **Editar** em qualquer uma das seções para fazer alterações.

   Na seção Deseja ativar a política **imediatamente?** Deixe o valor padrão Sim, a ligue **imediatamente selecionado.**

   Quando terminar, clique em **Concluir.**

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Usar o PowerShell & segurança e conformidade para criar uma política de alerta para arquivos detectados

Se você preferir usar o PowerShell para criar a mesma política de alerta conforme descrito na seção anterior &, conecte-se ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) do Centro de Conformidade e Segurança e execute o seguinte comando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Observação:** o valor _de Severidade_ padrão é Baixo. Para especificar Médio ou Alto, inclua o parâmetro _severity_ e o valor no comando.

Para informações detalhadas de sintaxes e de parâmetros, [consulte New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

- Para verificar se você ativas com êxito os Anexos Seguros para o SharePoint, o OneDrive e o Microsoft Teams, use uma das seguintes etapas:

  - No Centro de Conformidade [&](https://protection.office.com)Segurança,  vá para Anexos Seguros da POLÍTICA de Gerenciamento de Ameaças da ATP, selecione Configurações Globais e verifique o valor da configuração Ativar o \>  \> Defender para **Office 365 para SharePoint, OneDrive** e Microsoft Teams.

  - No PowerShell do Exchange Online, execute o seguinte comando para verificar a configuração da propriedade:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Para verificar se você bloqueou com êxito as pessoas de baixar arquivos mal-intencionados, abra o PowerShell do SharePoint Online e execute o seguinte comando para verificar o valor da propriedade:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Para verificar se você configurou com êxito uma política de alerta para arquivos detectados, use uma das seguintes etapas:

  - No Centro de Conformidade & Segurança, vá para Políticas de **Alertas** e selecione a política de alerta e \>  \> verifique as configurações.

  - No PowerShell & Centro de Conformidade e Segurança, substitua pelo nome da política de alerta, execute o seguinte comando e \<AlertPolicyName\> verifique os valores de propriedade:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Use o [relatório de status de](view-email-security-reports.md#threat-protection-status-report) proteção contra ameaças para exibir informações sobre arquivos detectados no SharePoint, No OneDrive e no Microsoft Teams. Especificamente, você pode usar o **view data by: Content \> Malware** view.
