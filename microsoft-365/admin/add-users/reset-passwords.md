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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 7a5d073b-7fae-4aa5-8f96-9ecd041aba9c
description: 'Saiba como redefinir a senha de um usuário na assinatura do Microsoft 365 for Business. '
ms.openlocfilehash: 0d8a68edb0b85094b271712f018eea79ca9f0aee
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626941"
---
# <a name="reset-passwords"></a>Redefinir senha

Assista a um pequeno vídeo sobre como redefinir senhas de usuário.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FVVP] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="let-users-reset-their-own-passwords"></a>Permitir que os usuários redefinam as próprias senhas

É altamente recomendado configurar o autoatendimento de redefinição de senha. Assim, você não precisa redefinir manualmente as senhas para os usuários. Para saber como, confira [Permitir que os usuários redefinam as próprias senhas no Office 365](let-users-reset-passwords.md).
  
## <a name="reset-a-business-password-for-someone-else"></a>Redefinir uma senha de negócios para outra pessoa

Estas etapas são apenas para pessoas que usam um plano Microsoft 365 para empresas. Para fazer isso, você precisa entrar com sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../admin-overview/admin-overview.md)

 
::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

2. Na página **usuários ativos** , selecione o usuário e, em seguida, selecione **Redefinir senha**.
    
3. Siga as instruções na página **Redefinir senha** para gerar automaticamente uma nova senha para o usuário ou criar uma para elas e, em seguida, selecione **Redefinir**.  
    
4. Insira um endereço de email que o usuário possa acessar para que recebam a nova senha e acompanhe com eles para garantir que eles o tenham.
 
  
## <a name="reset-my-admin-password"></a>Redefinir minha senha de administrador

Use estas etapas se você esqueceu sua senha, mas consegue entrar no Microsoft 365 porque, por exemplo, sua senha é salva no navegador: 
    
1. No Microsoft 365, selecione **configurações** \> **informações pessoais** **do Office 365** \> . 
          
2. Verifique se os detalhes de **contato** e o **email alternativo** estão corretos. Caso contrário, altere-as agora. 
        
3. Sair do Office 365: Selecione seu nome no canto superior direito (na imagem acima, mostrado como **Diane**) \> **sair**. 
        
4. Agora entre novamente: digite \> **seu nome de** \> usuário e, em seguida, selecione **esqueceu a senha**. 
    
5. Siga as etapas no Assistente para redefinir sua senha. Ele usa suas informações de contato alternativas para confirmar que você é a pessoa certa para redefinir sua senha. 
    
Se você esqueceu a senha e não consegue entrar: 
    
- Peça a outro administrador global em sua empresa para redefinir sua senha.
    
- Ou, [ligue para o suporte da Microsoft](https://support.office.com/article/contact-support-for-business-products-admin-help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b?ui=en-US&amp;rs=en-US&amp;ad=US#ID0EAADAAA=Phone_support_). 
    
## <a name="reset-all-business-passwords-for-everyone-in-your-organization-at-the-same-time"></a>Redefinir todas as senhas de negócios para todas as pessoas em sua organização ao mesmo tempo
<a name="bkmk_forgot"> </a>

Estas etapas funcionam para uma empresa com dezenas de usuários. Se você tiver centenas ou milhares de usuários, confira a próxima seção sobre redefinições de senha em massa.
  
1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
    
2. Selecione a opção ao lado de **exibir nome** para selecionar todos em sua empresa. Desmarque a si mesmo. Você não pode redefinir sua senha ao mesmo tempo em que redefine a senha de outras pessoas.
    
3. Selecione **Redefinir senha**. 

4. Siga as instruções na página **Redefinir senha** e selecione **Redefinir**.  Se você optou por gerar automaticamente as senhas, as novas senhas temporárias serão exibidas.   
    
5. Insira um endereço de email onde você pode receber as senhas temporárias. Você precisará notificar seus usuários quais são suas senhas temporárias.
    

  
## <a name="reset-business-passwords-in-bulk"></a>Redefinir senhas de negócios em massa
<a name="bkmk_forgot"> </a>

Use o PowerShell! Confira esta postagem por Eyal Doron: [Gerenciamento de senhas com o PowerShell](https://go.microsoft.com/fwlink/?linkid=853696).
  
Veja um artigo relacionado: [Definir senhas de várias contas de usuário](https://support.office.com/article/014fc912-bee1-461d-ad00-56b80428b907.aspx#bkmk_password).
  
Para obter informações gerais, consulte [PowerShell for Microsoft 365 Administrators](https://support.office.com/article/40fdcbd4-c34f-42ab-8678-8b3751137ef1.aspx).
  
## <a name="force-a-password-change-for-all-users-in-your-business"></a>Forçar uma alteração de senha para todos os usuários da sua empresa
<a name="bkmk_forgot"> </a>

Confira esta excelente postagem no blog por Vasil Michev, MVP da Microsoft: [Force a alteração de senha para todos os usuários no Office 365](https://go.microsoft.com/fwlink/?linkid=853693).
  
## <a name="im-lost"></a>Estou perdido!
<a name="bkmk_forgot"> </a>

Experimente os procedimentos deste artigo: [Eu esqueci o nome de usuário ou a senha da conta que uso com o Office.](https://support.office.com/article/eba0b4a2-c0ae-472c-99f6-bc63ee2425a8?wt.mc_id=SCL_reset-passwords_AdmHlp)
  
## <a name="related-articles"></a>Artigos relacionados
<a name="bkmk_forgot"> </a>
  
[Permitir que os usuários redefinam suas próprias senhas](let-users-reset-passwords.md)

[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md)

[Definir a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md)

[Restaurar um usuário](restore-user.md)

[Remover um ex-funcionário](remove-former-employee.md)

[Vídeos de treinamento do Microsoft 365 for Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)