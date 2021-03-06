---
title: Configurar a autenticação multifator para usuários
f1.keywords:
- NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Saiba como configurar a autenticação multifator para a sua organização.
monikerRange: o365-worldwide
ms.openlocfilehash: 480e09e42ea53cc78cd738a6e0650feae7a9f8c8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635945"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar a autenticação multifator

Com base no seu conhecimento de [MFA (autenticação multifator) e seu suporte no Microsoft 365](multi-factor-authentication-microsoft-365.md), é hora de configurá-la e distribuí-la para a organização.

> [!IMPORTANT]
> Se você comprou a sua assinatura ou a versão de avaliação após 21 de outubro de 2019 e for solicitado a executar a MFA ao entrar, [os padrões de segurança](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para a sua assinatura.

## <a name="before-you-begin"></a>Antes de começar

- Você deve ser um administrador Global para gerenciar a MFA. Para obter mais informações, confira o artigo [Sobre funções de administrador](../add-users/about-admin-roles.md).
- Se você tiver a MFA herdada por usuário, [Desative a MFA herdada por usuário](#turn-off-legacy-per-user-mfa).
- Se você tem clientes do Office 2013 em dispositivos Windows, [ative a Autenticação moderna para clientes do Office 2013](./enable-modern-authentication.md).
- Avançado: se você tiver serviços de diretório de terceiros com o AD FS (Serviços de Federação do Active Directory), configure o Servidor do Azure MFA. Confira [cenários avançados com a Autenticação Multifator do Microsoft Azure Active Directory e soluções VPN de terceiros](/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter mais informações.

## <a name="turn-security-defaults-on-or-off"></a>Ativar ou desativar o padrão de Segurança

Para a maioria das organizações, os padrões de segurança oferecem um bom nível de segurança adicional de entrada. Para saber mais, confira [Quais são os padrões de segurança?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Se a sua assinatura for nova, os padrões de Segurança já poderão estar habilitados para você automaticamente.

Habilite ou desabilite as opções de segurança no painel de **Propriedades** para o Azure Active Directory (Azure AD) no portal do Azure.

1. Acessar o [Centro de administração do Microsoft 365](https://admin.microsoft.com) com credenciais de administrador global.
2. Na barra de navegação à esquerda, escolha **Mostrar Tudo** e em **Centro de administração**, escolha **Azure Active Directory**.
3. No **centro de administração do Azure Active Directory** escolha **Azure Active Directory** \> **Propriedades**.
4. Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.
5. Clique em **Sim** para habilitar os padrões de segurança ou **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.

Se você estiver usando [políticas de Acesso Condicional da linha de base](/azure/active-directory/conditional-access/concept-baseline-protection), você será instruído a desativá-las antes de mover para usar os padrões de segurança.

1. Vá para a página [Acesso Condicional - página Políticas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Escolha cada política de linha de base que esteja **Ativada** e defina **Permitir que a política** seja **Desativada**.
3. Vá para [Azure Active Directory - Página Propriedades](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.
5. Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.

## <a name="use-conditional-access-policies"></a>Usar políticas de Acesso Condicional

Se a sua organização tiver necessidades de segurança de entrada mais granulares, as políticas de acesso condicional poderão oferecer mais controle. O Acesso Condicional permite que você crie e define políticas que reagem a eventos de entrada e solicite ações adicionais antes que um usuário receba acesso a um aplicativo ou serviço.

> [!IMPORTANT]
> Desabilite tanto a MFA por usuário quanto os padrões de Segurança antes de habilitar as políticas de Acesso Condicional.

O Acesso Condicional está disponível para clientes que compraram o Azure Active Directory Premium P1 ou licenças que incluem isso, como o Microsoft 365 Business Premium e o Microsoft 365 E3. Para obter mais informações, confira [criar uma política de Acesso Condicional](/azure/active-directory/authentication/tutorial-enable-azure-mfa).

O acesso condicional baseado em risco está disponível por meio da licença do Azure AD Premium P2 ou de licenças que incluem isso, como o Microsoft 365 E5. Para mais informações, confira [Acesso Condicional baseado em risco](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).

Para obter mais informações sobre o Azure Active Directory P1 e P2, confira [Preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="turn-on-modern-authentication-for-your-organization"></a>Habilitar a autenticação moderna para a sua organização

Para a maioria das assinaturas, a autenticação moderna é ativada automaticamente, mas se você adquiriu sua assinatura antes de agosto de 2017, é provável que precise ativar a Autenticação Moderna para que recursos como a Autenticação Multifator funcionem em clientes Windows como o Outlook.


1. No centro de administração do Microsoft 365, no painel de navegação esquerdo, escolha **Configurações** \> **Configurações da organização**.
2. Debaixo de **Serviços** guia, escolher **Autenticação Moderna**, e no **Autenticação Moderna** painel, certifique-se **Habilitar Autenticação Moderna** é selecionado. Escolha **Salvar alterações**.

### <a name="turn-off-legacy-per-user-mfa"></a>Desabilitar a MFA herdada por usuário

Se você já habilitou a MFA por usuário, é necessário desabilitá-lo antes de habilitar o padrão de segurança.

1. No Centro de administração do Microsoft 365, na barra de navegação esquerda, escolha **Usuários** \> **Usuários ativos**.
1. Na página **Usuários ativos**, escolha **Autenticação multifator**.
1. Na página da autenticação multifator, selecione cada usuário e defina o status de autenticação multifator como **Desabilitado**.

## <a name="next-steps"></a>Próximas etapas

- [Como se inscrever para obter o método de verificação adicional](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [O que é: Autenticação Multifator](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [Como entrar após o registro](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Como alterar o método de verificação adicional](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a>Conteúdo relacionado

[Ativar a autenticação multifator](../../business-video/turn-on-mfa.md) (vídeo)\
[Ativar a autenticação multifator para seu telefone](../../business-video/set-up-mfa.md) (vídeo)