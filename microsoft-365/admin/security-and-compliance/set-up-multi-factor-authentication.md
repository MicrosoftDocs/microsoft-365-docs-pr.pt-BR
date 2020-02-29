---
title: Configurar a autenticação multifator para usuários do Office 365
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
description: Aprenda a usar padrões de segurança para configurar a autenticação multifator para usuários do Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: cb2205e5f5b7df4f6e7d8f7263a91fb2f0f4d3e2
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341253"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar a autenticação multifator
  
Todas as novas assinaturas do Office 365 para empresas ou do Microsoft 365 Business terão automaticamente os padrões de segurança ativados. Isso significa que todos os usuários terão que configurar a MFA (autenticação multifator) e instalar o aplicativo autenticador em seus dispositivos móveis. Para obter mais informações, confira [Configurar a verificação em duas etapas do Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

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

Todos os outros usuários serão solicitados a executar uma autenticação adicional quando necessário. Para saber mais, confira [Quais são os padrões de segurança?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> Você deve ser um administrador global do Office 365 para configurar ou modificar a autenticação multifator. <br><br>
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

Se você já configurou a MFA com políticas de linha de base, [será necessário desativá-las e habilitar o de padrões de segurança](#move-from-baseline-policies-to-security-defaults). No entanto, se você tiver o Microsoft 365 Business ou sua assinatura incluir o [do Azure Active Directory Premium 1 ou do Azure Active Directory Premium 2](https://azure.microsoft.com/pricing/details/active-directory/), também será possível configurar [as políticas de](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) acesso condicional. Para usar políticas de acesso condicional, você precisa ter certeza de que a [autenticação moderna está habilitada](#enable-multi-factor-authentication-for-your-organization).

## <a name="manage-security-defaults"></a>Gerenciar padrões de segurança.

1. Acesse o [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822) com credenciais de administrador global.
2. Vá para [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. Na parte inferior da página, clique em **Gerenciar padrões de segurança**.
4. Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Mover das políticas de linha de base para padrões de segurança

1. No [Centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Configuração**.

2. Ao lado de **Entrada e segurança**, em **Tornar a entrada mais segura**, selecione **Exibir**.

3. Em **Tornar a entrada mais segura**, selecione **Gerenciar**. 

4. Na página **de políticas de acesso condicional do portal do Azure** escolha cada política de linha de base que esta **ligada**, e configure-as para **desligada**.
5. Vá para a página [Azure Active Directory Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. Na parte inferior da página, escolha **gerenciar padrões de segurança**e, no painel **habilitar padrões de segurança**, defina **habilite o padrão de segurança** alterne para **Sim**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Habilitar a autenticação moderna para sua organização

Todos os aplicativos cliente do Office 2016 oferecem suporte à MFA por meio do uso da ADAL (Biblioteca de Autenticação do Active Directory). Isso significa que as senhas de aplicativo não são obrigatórias para os clientes do Office 2016. No entanto, você precisa verificar se a sua assinatura do Office 365 está habilitada para ADAL ou autenticação moderna.

1. Para habilitar a autenticação moderna, no [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **Configurações**\>**Configurações** e na guia **Serviços**, escolha **Autenticação moderna** na lista.

2. Marque a caixa **Habilitar autenticação moderna**, no painel da **Autenticação moderna**. 

    ![Painel de autenticação moderna com a caixa de seleção Habilitar marcada.](../media/enablemodernauth.png)
    
## <a name="enable-multi-factor-authentication-for-your-organization"></a>Ativar a autenticação multifator da sua organização
    
1. No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=834822), selecione **usuários** e **usuários ativos**.

2. Na seção **usuários ativos** , clique em **autenticação multifator**.

3. Na página **autenticação multifator** , selecione **usuário** se estiver habilitando-o para um usuário ou selecione **atualização em massa** para habilitar vários usuários.

4. Clique em **habilitar** em **etapas rápidas**.

5. Na janela pop-up, clique em **habilitar autenticação multifator**.

Após configurar a autenticação multifator da sua organização, os usuários precisarão configurar a verificação em duas etapas em seus dispositivos. Para obter mais informações, confira [Configurar a verificação em duas etapas do Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).
    
> [!TIP]
> Para explicar aos usuários como configurar o aplicativo autenticador, visite [Usar o Microsoft Authenticator com o Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).


> [!IMPORTANT]
> A partir de agosto de 2017, todos os novos locatários do Office 365, que inclui o Skype for Business e o Exchange Online, têm autenticação moderna habilitada por padrão. Para verificar o status de autenticação moderna do Skype for Business Online, você pode usar o Skype for Business via PowerShell com credenciais de administrador global. Execute Get-CsOAuthConfiguration para verificar o resultado de -ClientADALAuthOverride. Se -ClientADALAuthOverride for ‘Allowed’, a autenticação moderna está ativada.
Para verificar o status do seu MA no Exchange Online, visite [Habilitar a autenticação moderna no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Artigos relacionados

[10 principais formas de proteger planos corporativos do Office 365 e do Microsoft 365](secure-your-business-data.md)

[Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.](enable-modern-authentication.md)
