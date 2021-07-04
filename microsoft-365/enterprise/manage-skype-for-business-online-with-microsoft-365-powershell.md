---
title: Gerenciar o Skype for Business Online com o Windows PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: Use o Windows PowerShell para Microsoft 365 para gerenciar as políticas do Skype for Business Online, políticas por usuário e configurações de reunião.
ms.openlocfilehash: 4ea4858e4ca334cdb0268312e69bef77bc9bbd86
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288978"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>Gerenciar o Skype for Business Online com o Windows PowerShell

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Os administradores do Skype for Business Online são responsáveis pelas políticas de gerenciamento. Embora você possa executar algumas dessas tarefas no Centro de administração do Microsoft 365, outras tarefas são mais fáceis no Windows PowerShell.

## <a name="before-you-start"></a>Antes de começar

> [!NOTE]
> O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, você não precisa instalar o Conector do Skype for Business Online.

Instale o [módulo PowerShell do Teams](/microsoftteams/teams-powershell-install).

## <a name="connect-using-admin-credentials"></a>Conecte-se usando as credenciais administrativas

1. Abra uma janela de prompt de comando do Windows PowerShell e execute os seguintes comandos:

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. Na caixa de diálogo **Solicitação de Credenciais do Windows PowerShell**, digite o nome e senha da sua conta de administrador, e então selecione **OK**.

## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>Conectar usando uma conta de administrador com a autenticação multifator

1. Abra uma janela de prompt de comando do Windows PowerShell e execute os seguintes comandos:

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. Quando solicitado, digite o nome da sua conta de administrador do Skype for Business Online.

3. Na caixa de diálogo **Entre em sua conta**, digite sua senha de administrador do Skype for Business Online e clique em **Entrar**.

4. Siga as instruções na caixa de diálogo **Entre em sua conta** para fornecer informações adicionais de autenticação, como um código de verificação, e clique em **Verificar**.

Para mais informações, confira:

- [Gerenciar as políticas do Skype for Business Online com o Windows PowerShell](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)

- [Atribuir políticas do Skype for Business online por usuário com o Windows PowerShell](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)

## <a name="see-also"></a>Confira também

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Introdução ao Windows PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

[Referências de cmdlet do Windows PowerShell do Skype for Business](/powershell/module/skype/)
