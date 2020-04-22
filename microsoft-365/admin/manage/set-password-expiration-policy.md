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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Saiba como definir uma política de expiração de senha para sua organização no centro de administração do Microsoft 365. '
ms.openlocfilehash: bcea72dadb6f10ac4ef80677f3def57eca2724cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628047"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>Definir a política de expiração de senha para sua organização

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos.  

Se é um usuário, você não tem as permissões para definir a senha para nunca expirar. Peça ao suporte técnico do seu trabalho ou da sua escola que faça isso para você. 

Como administrador, você pode fazer as senhas de usuário expirarem após um determinado número de dias ou definir as senhas para nunca expirarem. 

> [!Tip]
> Por padrão, as senhas estão definidas para expirar em 90 dias. A pesquisa atual indica que as alterações de senha obrigatórias são mais prejudicadas do que o recomendado. Eles direcionam os usuários a escolher senhas mais fracas, reutilizar senhas ou atualizar senhas antigas de maneiras que são facilmente adivinhadas pelos hackers. Se a senha for configurada para nunca expirar, recomendamos habilitar a [autenticação multifator](../security-and-compliance/set-up-multi-factor-authentication.md).

Siga as etapas abaixo se desejar definir as senhas dos usuários para expirarem após um período de tempo específico.
> [!IMPORTANT]
> Apenas os [administradores globais ](../add-users/about-admin-roles.md) podem executar essas etapas.
  
1. No centro de administração do, vá para **Configurações** \> **Configurações**.

2. Vá para a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">Segurança e privacidade</a>.
 Se você não for um administrador global, não verá a opção Segurança e privacidade.
  
3. Selecione **Política de expiração de senha**.
  
4. Se você não quiser que os usuários tenham que alterar as senhas, marque a caixa de seleção ao lado de **Definir senhas de usuário para expirar após um número de dias**.
  
5. Digite a frequência com que as senhas devem expirar. Escolha um número de dias entre 14 e 730.
  
6. Na segunda caixa, insira quando os usuários são notificados de que a senha expirará e, em seguida, selecione **Salvar**. Escolha um número de dias de 1 a 30.
    
7. Quando a senha do usuário expirar, ele receberá uma notificação que aparecerá no canto inferior direito da tela.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>Pontos importantes que você precisa saber sobre o recurso de expiração de senha

Vejamos alguns pontos que você precisa saber sobre como esse recurso funcionará a partir de janeiro de 2018:
  
- As pessoas que só usam o aplicativo do Outlook não terão de redefinir a senha do Microsoft 365 até que ela expire no cache. Isso pode levar vários dias após a data de validade real. Não há soluções alternativas para isso ao nível de administrador.
    
- Os usuários não receberão uma notificação por email informando que a senha expirará em um número X de dias. Quer esse recurso? **[Vote aqui!](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**
    
## <a name="prevent-last-password-from-being-used-again"></a>Impedir que a última senha seja utilizada novamente

Se quiser impedir que os usuários promovam a reciclagem de senhas antigas, use o Azure AD. Consulte [Definir a política de expiração da senha da sua organização](https://docs.microsoft.com/office365/admin/manage/set-password-expiration-policy?view=o365-worldwide).

Além disso, se um funcionário tiver usado um dispositivo móvel para acessar o Microsoft 365, você poderá apagá-lo a fim de garantir que a senha não seja armazenada e reciclada desse local. Para saber mais, confira [Apagar e bloquear o dispositivo móvel de um funcionário antigo](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device).


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>Sincronizar os hashes de senhas do usuário de um Active Directory local para o Azure AD (Microsoft 365)

Este artigo é para configurar a política de expiração para usuários somente na nuvem (Azure AD). Isso não se aplica a usuários de identidade híbrida que usam sincronização hash de senha, autenticação de passagem ou federação local como o ADFS.
  
Para saber como sincronizar hashes de senha de usuário do AD local para o Azure AD, confira [implementar a sincronização de hash de senha com a sincronização de Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).
