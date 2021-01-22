---
title: Definir a política de expiração de senha para sua organização
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Saiba como definir uma política de expiração de senha para sua organização no centro de administração do Microsoft 365.
ms.openlocfilehash: 471a881bd9808861b9fa2c67d007f1ebe1c10885
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926169"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Definir a política de expiração de senha para sua organização

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide).

::: moniker-end

## <a name="before-you-begin"></a>Antes de começar

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../admin-overview/admin-overview.md).

Você deve ser um [administrador de senha ou administrador global](../add-users/about-admin-roles.md) para realizar essas etapas. 

Se é um usuário, você não tem as permissões para definir a senha para nunca expirar. Peça ao suporte técnico do seu trabalho ou da sua escola que faça isso para você. 

Como administrador, você pode fazer as senhas de usuário expirarem após um determinado número de dias ou definir as senhas para nunca expirarem.

## <a name="set-password-expiration-policy"></a>Definir política de expiração de senha

> [!Tip]
> Por padrão, as senhas estão definidas para expirar em 90 dias. A pesquisa atual indica que as alterações de senha obrigatórias são mais prejudicadas do que o recomendado. Eles direcionam os usuários a escolher senhas mais fracas, reutilizar senhas ou atualizar senhas antigas de maneiras que são facilmente adivinhadas pelos hackers. Se a senha for configurada para nunca expirar, recomendamos habilitar a [autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md).

Siga as etapas abaixo se desejar definir as senhas dos usuários para expirarem após um período de tempo específico.
> [!IMPORTANT]
> Apenas os [administradores globais ](../add-users/about-admin-roles.md) podem executar essas etapas.
  
1. No centro de administração do, vá para **Configurações** \> **Configurações da Organização**.

2. Vá para a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Segurança e privacidade</a>.
 Se você não for um administrador global, não verá a opção Segurança e privacidade.
  
3. Selecione **Política de expiração de senha**.
  
4. Se você não deseja que os usuários alterem as senhas, desmarque a caixa ao lado de **Definir as senhas dos usuários para expirar após alguns dias**.
  
5. Digite a frequência com que as senhas devem expirar. Escolha um número de dias entre 14 e 730.
  
6. Na segunda caixa, insira quando os usuários são notificados de que a senha expirará e, em seguida, selecione **Salvar**. Escolha um número de dias de 1 a 30.

7. Quando a senha do usuário expirar, ele receberá uma notificação que aparecerá no canto inferior direito da tela.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Pontos importantes que você precisa saber sobre o recurso de expiração de senha
  
- As pessoas que só usam o aplicativo do Outlook não terão de redefinir a senha do Microsoft 365 até que ela expire no cache. Isso pode levar vários dias após a data de validade real. Não há soluções alternativas para isso ao nível de administrador.

## <a name="prevent-last-password-from-being-used-again"></a>Impedir que a última senha seja utilizada novamente

Se quiser impedir que seus usuários reciclem senhas antigas, você pode fazê-lo aplicando essa regra no histórico de senhas do Active Directory (AD) local. Confira [Criar uma política de senha personalizada](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy).

No Azure AD, a última senha não pode ser usada novamente quando o usuário altera uma senha. A política de senha é aplicada a todas as contas de usuário que são criadas e gerenciadas diretamente no Azure AD. Essa política de senhas não pode ser modificada. Confira [Políticas de senha do Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts).

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Sincronizar os hashes de senhas do usuário de um Active Directory local para o Azure AD (Microsoft 365)

Este artigo é para configurar a política de expiração para usuários somente na nuvem (Azure AD). Isto não se aplica a usuários de identidade híbrida que usam sincronização hash de senha, autenticação de passagem ou federação local como o ADFS.
  
Para saber como sincronizar hashes de senha de usuário do AD local para o Azure AD, confira [implementar a sincronização de hash de senha com a sincronização de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Confira as restrições de conta e políticas de senha no Azure Active Directory.

Você pode definir mais restrições e políticas de senha no Azure Active Directory. Confira as [restrições de conta e políticas de senha no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy) para mais informações.

## <a name="update-password-policy"></a>Atualizar a Política de senhas

O cmdlet Set-MsolPasswordPolicy atualiza a política de senhas de um determinado domínio ou locatário. Duas configurações são necessárias. a primeira é para indicar o período de tempo que uma senha permanece válida antes de ser alterada e a segunda é indicar o número de dias antes da data de vencimento da senha que será disparada quando os usuários receberem suas primeiras notificações de que a senha irá expirar em breve.

Para saber como atualizar a política de senha de um específico domínio ou locatário, confira [Set-MsolPasswordPolicy](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0).

## <a name="related-content"></a>Conteúdo relacionado

[Permitir que os usuários redefinam as próprias senhas](../add-users/let-users-reset-passwords.md)

[Redefinir senhas](../add-users/reset-passwords.md)
