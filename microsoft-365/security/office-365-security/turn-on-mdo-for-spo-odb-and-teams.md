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
ms.openlocfilehash: a654db40e5dec8d23d07ec7455216fe4e0a8c0e7
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933006"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

O Microsoft Defender para Office 365 para SharePoint, OneDrive e Microsoft Teams protege sua organização contra o compartilhamento inadvertida de arquivos mal-intencionados. Para obter mais informações, [consulte Cofre Attachments for SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Este artigo contém as etapas para habilenciar e configurar Cofre anexos para SharePoint, OneDrive e Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente para a página **Cofre Anexos,** abra <https://security.microsoft.com/safeattachmentv2> .

- Para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams, você precisa ser membro dos grupos  de função  Gerenciamento da Organização ou Administrador de Segurança no portal do Microsoft 365 Defender. Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).

- Para usar SharePoint PowerShell Online para impedir que as pessoas baixem arquivos mal-intencionados, você precisa ser membro das funções Administrador [Global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) ou SharePoint [Administrador](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) no Azure AD.

- Verifique se o log de auditoria está habilitado para sua organização. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

- Permitir até 30 minutos para que as configurações entre em vigor.

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Etapa 1: use o portal Microsoft 365 Defender para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams

1. No portal Microsoft 365 Defender, vá para **Políticas** & políticas políticas de ameaça \>  \>  seção \> **Cofre Anexos**.

2. Na página **Cofre Anexos,** clique em **Configurações globais**.

3. Na seção **Configurações globais** que aparecem, vá para a seção Proteger arquivos **SharePoint, OneDrive e Microsoft Teams.**

   Mova Office 365 Ativar o Defender para **SharePoint, OneDrive** e Microsoft Teams alternar para a Microsoft Teams direita para ativar o Cofre Attachments para SharePoint, OneDrive e ![ ](../../media/scc-toggle-on.png) Microsoft Teams.

   Quando concluir, clique em **Salvar**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Use Exchange Online PowerShell para ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams

Se você preferir usar o PowerShell para ativar o Cofre Attachments para SharePoint, OneDrive e Microsoft Teams, conecte-se ao [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) e execute o seguinte comando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Etapa 2: (Recomendado) Use SharePoint PowerShell Online para impedir que os usuários baixem arquivos mal-intencionados

Por padrão, os usuários não podem abrir, mover, copiar ou compartilhar arquivos <sup>\*</sup> mal-intencionados detectados pelo Cofre Attachments para SharePoint, OneDrive e Microsoft Teams. No entanto, eles podem excluir e baixar arquivos mal-intencionados.

<sup>\*</sup> Se os usuários **acessam Gerenciar acesso,** a opção **Compartilhar** ainda estará disponível.

Para impedir que os usuários baixem arquivos mal-intencionados, [conecte-se SharePoint PowerShell Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) e execute o seguinte comando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Observações**:

- Essa configuração afeta usuários e administradores.
- As pessoas ainda podem excluir arquivos mal-intencionados.

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>Etapa 3 (Recomendado) Use o portal Microsoft 365 Defender para criar uma política de alerta para arquivos detectados

Você pode criar uma política de alerta que notifica você e outros administradores quando Cofre anexos para SharePoint, OneDrive e Microsoft Teams detecta um arquivo mal-intencionado. Para saber mais sobre alertas, consulte [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).

1. No portal Microsoft 365 Defender, acesse **Políticas** & \> **política de alerta** ou abra <https://security.microsoft.com/alertpolicies> .

2. Na página **Política de alerta,** clique em **Nova política de alerta.**

3. O **assistente nova política de alerta** é aberto em uma saída de emergência. Na página **Nomear seu alerta,** configure as seguintes configurações:
   - **Nome**: Digite um nome exclusivo e descritivo. Por exemplo, Arquivos Mal-intencionados em bibliotecas.
   - **Descrição**: digite uma descrição opcional. Por exemplo, Notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, OneDrive ou Microsoft Teams.
   - **Severidade**: Selecione **Baixo,** **Médio** ou **Alto** na listada.
   - **Categoria**: Selecione **Gerenciamento de ameaças** na lista lista listada.

   Ao terminar, clique em **Avançar**.

4. Na página **Criar configurações de** alerta, configure as seguintes configurações:
   - **O que você deseja alertar?** section \> **Activity is** \> Select **Detected malware in file** from the drop down list.
   - **Como deseja que o alerta seja acionado?** seção: Deixe o valor padrão **Sempre que uma atividade corresponde à regra** selecionada.

   Ao terminar, clique em **Avançar**.

5. Na página **Definir seus destinatários,** configure as seguintes configurações:
   - Verifique **se As notificações de email de** envio estão selecionadas. Na caixa **Destinatários de** email, selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.
   - **Limite de notificação diário**: Deixar o valor padrão **Nenhum limite** selecionado.

   Ao terminar, clique em **Avançar**.

6. Na página **Revisar suas configurações,** revise suas configurações. Você pode selecionar **Editar** em cada seção para modificar as configurações da seção. Ou você pode clicar em **Voltar** ou selecionar a página específica no assistente.

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

  - No portal do Microsoft 365 Defender,  vá até Políticas & políticas políticas de ameaças seção Cofre Anexos , selecione Configurações globais e verifique o valor da configuração Ativar o Defender para Office 365 para \>  \>  \>  **SharePoint, OneDrive e Microsoft Teams.** 

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
  - No portal Microsoft 365 Defender, acesse **Políticas** & Política de alerta selecione a política de alerta e \>  \> verifique as configurações.
  - No Microsoft 365 portal do Defender PowerShell, substitua pelo nome da política de alerta, execute o seguinte comando e \<AlertPolicyName\> verifique os valores da propriedade:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).

- Use o [relatório de status de proteção](view-email-security-reports.md#threat-protection-status-report) contra ameaças para exibir informações sobre arquivos detectados em SharePoint, OneDrive e Microsoft Teams. Especificamente, você pode usar o **view data by: Content \> Malware** view.
