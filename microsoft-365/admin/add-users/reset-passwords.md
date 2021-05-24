---
title: Redefinir senha
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: Entre com sua conta de administrador Microsoft 365 para redefinir senhas para usuários em Microsoft 365 assinatura para empresas.
ms.openlocfilehash: 0cec6c7874b51c76fca60c6c237395c940c47bbe
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635565"
---
# <a name="reset-passwords"></a>Redefinir senha

Este artigo explica como redefinir senhas para você e para seus usuários quando você tiver uma assinatura Microsoft 365 para empresas.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../../business-video/admin-center-overview.md).

Você deve ser um [administrador global ou administrador de senha](about-admin-roles.md) para executar essas etapas.

## <a name="watch-reset-a-business-password-for-a-user"></a>Assistir: redefinir uma senha comercial para um usuário

Assista a um breve vídeo sobre como redefinir senhas de usuário.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP]

Se você achou esse vídeo útil, confira as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).
  
## <a name="steps-reset-a-business-password-for-a-user"></a>Etapas: Redefinir uma senha comercial para um usuário

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **Usuários ativos,** selecione o usuário e selecione **Redefinir senha**.

3. Siga as instruções na página **Redefinir** senha para gerar automaticamente uma nova senha para o usuário ou criar uma para eles e selecione **Redefinir**.  

4. Insira um endereço de email que o usuário possa obter para que ele receba a nova senha e acompanhe-os para garantir que a tenha recebido.

## <a name="let-users-reset-their-own-passwords"></a>Permitir que os usuários redefinam as próprias senhas

É altamente recomendado configurar o autoatendimento de redefinição de senha. Assim, você não precisa redefinir manualmente as senhas para os usuários. Para saber como, confira [Permitir que os usuários redefinam as próprias senhas no Office 365](let-users-reset-passwords.md).

## <a name="reset-my-admin-password"></a>Redefinir minha senha de administrador

Use estas etapas se você esqueceu sua senha, mas pode entrar no Microsoft 365 porque, por exemplo, sua senha é salva no navegador:

1. Selecione seu nome (ícone) no canto superior direito > Informações Pessoais da **Minha**  >  **Conta.**

2. Em **Detalhes de contato,** verifique se seu **email** alternativo é preciso e se você forneceu um número de telefone celular. Caso não seja, altere-os agora.

3. Sair: selecione seu nome no canto superior direito \> **Sair**.

4. Agora entre novamente: digite seu nome de usuário \> **Next** \> e selecione Esqueceu a **senha**.

5. Siga as etapas no assistente para redefinir sua senha. Ele usa suas informações de contato alternativas para verificar se você é a pessoa certa para redefinir sua senha.

Se você esqueceu sua senha e não pode entrar:

- Peça a outro administrador global em sua empresa para redefinir sua senha para você.

- Certifique-se de ter fornecido informações de contato alternativas, incluindo um número de telefone celular.

- Ou, [chame o Suporte da Microsoft.](../../business-video/get-help-support.md)

## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Redefinir todas as senhas comerciais para todos na sua organização ao mesmo tempo
<a name="bkmk_forgot"> </a>

Estas etapas funcionam para uma empresa com dezenas de usuários. Se você tiver centenas ou milhares de usuários, consulte a próxima seção sobre como redefinir senhas em massa (máximo de 40 usuários por vez).
  
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione a opção ao lado de **Exibir nome** para selecionar todos em sua empresa. Desmarque a si mesmo. Você não pode redefinir sua senha ao mesmo tempo em que redefine a senha de outras pessoas.

3. Selecione **Redefinir senha**. 

4. Siga as instruções na página **Redefinir senha** e selecione **Redefinir**.  Se você optou por gerar automaticamente as senhas, as novas senhas temporárias serão exibidas.

5. Insira um endereço de email onde você pode receber as senhas temporárias. Você precisará notificar seus usuários quais são suas senhas temporárias.
  
## <a name="reset-business-passwords-in-bulk"></a>Redefinir senhas comerciais em massa
<a name="bkmk_forgot"> </a>

Use o PowerShell! Confira esta postagem por Eyal Doron: [Gerenciamento de senhas com o PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
<!-- Here's a related article: [Set the passwords for multiple user accounts](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). -->
  
Para obter informações de visão geral, [consulte Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forçar uma alteração de senha para todos os usuários da sua empresa

Confira esta excelente postagem no blog por Vasil Michev, MVP da Microsoft: [Force a alteração de senha para todos os usuários no Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="i-dont-have-a-microsoft-365-for-business-subscription"></a>Não tenho uma assinatura de Microsoft 365 para empresas

Experimente os procedimentos deste artigo: [Eu esqueci o nome de usuário ou a senha da conta que uso com o Office.](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-content"></a>Conteúdo relacionado
  
[Permitir que os usuários redefinir suas próprias senhas](../add-users/let-users-reset-passwords.md) (artigo)\
[Redefinir senhas](../add-users/reset-passwords.md) (artigo)\
[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md) (artigo)\
[Definir a política de expiração de senha para sua](../manage/set-password-expiration-policy.md) organização (artigo)\
[Microsoft 365 para vídeos de treinamento empresarial](../../business-video/index.yml) (página de link)