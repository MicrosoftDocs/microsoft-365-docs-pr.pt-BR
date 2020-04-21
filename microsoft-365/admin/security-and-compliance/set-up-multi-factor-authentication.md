---
title: Configurar a autenticação multifator para usuários
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Saiba como usar os padrões de segurança para configurar a autenticação multifator para os usuários.
monikerRange: o365-worldwide
ms.openlocfilehash: 4a829aa597596564b9c2f468e72f3a766b198372
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627675"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar a autenticação multifator
  
> [!IMPORTANT]
> Se você comprou sua assinatura ou avaliação após 21 de outubro de 2019, e se você for solicitado inesperadamente pela MFA, [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para sua assinatura.

Todas as novas assinaturas do Microsoft 365 terão automaticamente os padrões de segurança ativados. Isso significa que todos os usuários terão que configurar a MFA (autenticação multifator) e instalar o aplicativo autenticador em seus dispositivos móveis. Para obter mais informações, consulte [Configurar a verificação em duas etapas para o Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

As nove funções de administrador a seguir serão necessárias para executar uma autenticação adicional sempre que entrarem:

- Administrador global
- Administrador do SharePoint
- Administrador do Exchange
- Administrador de acesso condicional
- Administrador de segurança
- Administrador de assistência técnica ou administrador de senha
- Administrador de cobrança
- Administrador de usuários
- Administrador de Autenticação

Todos os outros usuários serão solicitados a executar uma autenticação adicional quando necessário. Para obter mais informações, confira [O que são padrões de segurança?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

> [!NOTE]
> Você deve ser um administrador global para configurar ou modificar a autenticação multifator. <br><br>
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

Se você já configurou a MFA com políticas de linha de base, [será necessário desativá-las e habilitar o de padrões de segurança](#move-from-baseline-policies-to-security-defaults). No entanto, se você tiver o Microsoft 365 Business ou sua assinatura incluir o [do Azure Active Directory Premium 1 ou do Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), também será possível configurar [as políticas de](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) acesso condicional. Para usar as políticas de acesso condicional, você precisa certificar-se de que a [autenticação moderna](#enable-modern-authentication-for-your-organization) está habilitada.

> [!TIP]
> Para explicar aos usuários como configurar o aplicativo autenticador, visite [Usar o Microsoft Authenticator com o Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).

## <a name="manage-security-defaults"></a>Gerenciar padrões de segurança.

1. Entre no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822) com as suas credenciais de administrador global.
2. Vá para [Propriedades do Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3. Na parte inferior da página, clique em **Gerenciar padrões de segurança**.
4. Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Mover das políticas de linha de base para padrões de segurança

1. No [Centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Configuração**.

2. Ao lado de **Entrada e segurança**, em **Tornar a entrada mais segura**, selecione **Exibir**.

3. Em **Tornar a entrada mais segura**, selecione **Gerenciar**. 

4. Na página **acesso condicional-diretivas** , escolha cada diretiva de linha de base que está **ativada**e defina-as como **desativado**.
5. Vá para a página [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. Na parte inferior da página, escolha **gerenciar padrões de segurança**e, no painel **habilitar padrões de segurança** , defina **habilitar padrões de segurança** alterne para **Sim**e, em seguida, escolha **salvar**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Habilitar a autenticação moderna para sua organização

Todos os aplicativos cliente do Office 2016 oferecem suporte à MFA por meio do uso da ADAL (Biblioteca de Autenticação do Active Directory). Isso significa que as senhas de aplicativo não são obrigatórias para os clientes do Office 2016. No entanto, você precisa certificar-se de que sua assinatura do Microsoft 365 está habilitada para ADAL ou autenticação moderna.

1. Para habilitar a autenticação moderna, no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Configurações**\>**Configurações** e na guia **Serviços**, escolha **Autenticação moderna** na lista.

2. Marque a caixa **habilitar autenticação moderna (recomendada)** no painel **autenticação moderna** e, em seguida, escolha **salvar alterações**. 

    ![Painel de autenticação moderna com a caixa de seleção Habilitar marcada.](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> A partir de agosto de 2017, todas as novas assinaturas do Microsoft 365 que incluem o Skype for Business Online e o Exchange Online têm a autenticação moderna habilitada por padrão. Para verificar o status de autenticação moderna do Skype for Business Online, você pode usar o Skype for Business via PowerShell com credenciais de administrador global. Execute Get-CsOAuthConfiguration para verificar o resultado de -ClientADALAuthOverride. Se -ClientADALAuthOverride for ‘Allowed’, a autenticação moderna está ativada.
Para verificar o status do seu MA no Exchange Online, visite [Habilitar a autenticação moderna no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Artigos relacionados

[As 10 maneiras principais de proteger os planos do Microsoft 365 for Business](secure-your-business-data.md)

[Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.](enable-modern-authentication.md)
