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
description: Faça login com sua conta administradora Microsoft 365 para redefinir senhas para usuários em Microsoft 365 para assinatura de negócios.
ms.openlocfilehash: 8d4666eb70b1d5349f71c906f05510a8a54ded74
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571968"
---
# <a name="reset-passwords"></a>Redefinir senha

Este artigo explica como redefinir senhas para si mesmo e para seus usuários quando você tem uma Microsoft 365 para assinatura de negócios.

## <a name="before-you-begin"></a>Antes de começar

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../../business-video/admin-center-overview.md).

Você deve ser [um administrador global ou administrador de senhas](about-admin-roles.md) para executar essas etapas.

## <a name="watch-reset-a-business-password-for-a-user"></a>Assista: Redefinir uma senha de negócios para um usuário

Assista a um pequeno vídeo sobre a redefinição de senhas de usuário.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP]

Se você achou esse vídeo útil, confira as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).
  
## <a name="steps-reset-a-business-password-for-a-user"></a>Etapas: Redefinir uma senha de negócios para um usuário

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Na página **usuários ativos,** selecione o usuário e selecione **Redefinir senha**.

3. Siga as instruções na página **Redefinir senha** para gerar automaticamente uma nova senha para o usuário ou criar uma para elas e, em seguida, selecione **Redefinir**.  

4. Digite um endereço de e-mail que o usuário possa acessar para receber a nova senha e acompanhe-as para ter certeza de que a recebeu.

## <a name="let-users-reset-their-own-passwords"></a>Permitir que os usuários redefinam as próprias senhas

É altamente recomendado configurar o autoatendimento de redefinição de senha. Assim, você não precisa redefinir manualmente as senhas para os usuários. Para saber como, confira [Permitir que os usuários redefinam as próprias senhas no Office 365](let-users-reset-passwords.md).

## <a name="reset-my-admin-password"></a>Redefinir minha senha de administração

Use essas etapas se você esqueceu sua senha, mas você é capaz de fazer login para Microsoft 365 porque, por exemplo, sua senha é salva no seu navegador:

1. Selecione seu nome (ícone) no canto superior direito > **Minhas** Informações Pessoais da Conta  >  .

2. Em **detalhes de contato,** verifique duas vezes se seu **e-mail Alternativo** é preciso e que você forneceu um número de telefone celular. Se não, mude-os agora.

3. Saia: selecione seu nome no canto superior direito \> **Sign out**.

4. Agora faça login novamente: digite seu nome de usuário \> **Next** \> e selecione Senha **esquecida**.

5. Siga os passos do assistente para redefinir sua senha. Ele usa suas informações de contato alternativos para verificar se você é a pessoa certa para redefinir sua senha.

Se você esqueceu sua senha e não pode fazer login:

- Peça a outro administrador global em seu negócio para redefinir sua senha para você.

- Certifique-se de fornecer informações alternativas de contato, incluindo um número de telefone celular.

- Ou, [ligue para o Microsoft Support](../../business-video/get-help-support.md).

## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Redefinir todas as senhas de negócios para todos em sua organização ao mesmo tempo
<a name="bkmk_forgot"> </a>

Estas etapas funcionam para uma empresa com dezenas de usuários. Se você tiver centenas ou milhares de usuários, consulte a próxima seção sobre a redefinição de senhas em massa (máximo de 40 usuários por vez).
  
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

2. Selecione a opção ao lado **do nome Exibir** para selecionar todos em seu negócio. Desmarque a si mesmo. Você não pode redefinir sua senha ao mesmo tempo em que redefine a senha de outras pessoas.

3. Selecione **Redefinir senha**. 

4. Siga as instruções na página **Redefinir senha** e selecione **Redefinir**.  Se você optou por gerar automaticamente as senhas, as novas senhas temporárias serão exibidas.

5. Digite um endereço de e-mail onde você pode receber as senhas temporárias. Você precisará notificar seus usuários quais são suas senhas temporárias.
  
## <a name="reset-business-passwords-in-bulk"></a>Redefinir senhas de negócios em massa
<a name="bkmk_forgot"> </a>

Use o PowerShell! Confira esta postagem por Eyal Doron: [Gerenciamento de senhas com o PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
<!-- Here's a related article: [Set the passwords for multiple user accounts](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell). -->
  
Para obter informações sobre visão geral, consulte [Gerenciar Microsoft 365 com o PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forçar uma alteração de senha para todos os usuários da sua empresa

Confira esta excelente postagem no blog por Vasil Michev, MVP da Microsoft: [Force a alteração de senha para todos os usuários no Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="i-dont-have-a-microsoft-365-for-business-subscription"></a>Eu não tenho um Microsoft 365 para assinatura de negócios

Experimente os procedimentos deste artigo: [Eu esqueci o nome de usuário ou a senha da conta que uso com o Office.](https://support.microsoft.com/office/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-content"></a>Conteúdo relacionado
  
[Permitir aos usuários redefinir suas próprias senhas](../add-users/let-users-reset-passwords.md) (artigo)

[Redefinir senhas](../add-users/reset-passwords.md) (artigo)

[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md) (artigo)

[Defina a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md) (artigo)

[Microsoft 365 para vídeos de treinamento de negócios](../../business-video/index.yml) (página de link)