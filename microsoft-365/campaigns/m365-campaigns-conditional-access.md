---
title: Ativar padrões de segurança
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como os padrões de segurança podem ajudar a proteger sua organização contra ataques relacionados à identidade fornecendo configurações de segurança pré-configuradas.
ms.openlocfilehash: ea36ba45af26a767b08ee1e75931dca54dacea64
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398284"
---
# <a name="turn-on-security-defaults"></a>Ativar padrões de segurança

Os padrões de segurança ajudam a proteger sua organização contra ataques relacionados à identidade fornecendo configurações de segurança pré-configuradas que a Microsoft gerencia em nome da sua organização. Essas configurações incluem a habilitação da autenticação multifafação (MFA) para todos os administradores e contas de usuário. Para a maioria das organizações, os padrões de segurança oferecem um bom nível de segurança de login adicional.

Para obter mais informações sobre os padrões de segurança e as políticas que eles impõem, consulte [O que são padrões de segurança?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Se sua assinatura foi criada em ou após 22 de outubro de 2019, os padrões de segurança podem ter sido habilitados automaticamente para você, você deve verificar suas configurações para &mdash; confirmar.

Para habilitar os padrões de segurança no Azure Active Directory (Azure AD) ou para verificar se eles já estão habilitados:

1. Entre no Centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> com credenciais de administrador global.

2. No painel esquerdo, selecione **Mostrar Tudo e,** em Centros **de administração,** selecione **Azure Active Directory**.

3. No painel esquerdo do centro de administração do **Azure Active Directory,** selecione **Azure Active Directory**.

4. No menu esquerdo do Painel, na seção **Gerenciar,** selecione **Propriedades**.

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="Captura de tela do centro de administração do Azure Active Directory mostrando o local do item de menu Propriedades.":::

5. Na parte inferior da página **Propriedades,** selecione **Gerenciar padrões de segurança**.

6. No painel direito, você verá a configuração **Habilitar padrões de** segurança. Se **Sim** estiver selecionado, os padrões de segurança já estão habilitados e nenhuma ação é necessária. Se os padrões de segurança não estão habilitados no momento, selecione **Sim** para habilita-los e selecione **Salvar**.

> [!NOTE]
> Se você estiver usando políticas de Acesso Condicional, precisará afuní-las antes de usar os padrões de segurança.
>
> Você pode usar os padrões de segurança ou políticas de Acesso Condicional, mas não pode usar ambos ao mesmo tempo.

## <a name="consider-using-conditional-access"></a>Considere usar o Acesso Condicional

Se sua organização tiver requisitos complexos de segurança ou precisar de controle mais granular sobre suas políticas de segurança, considere usar o Acesso Condicional em vez de padrões de segurança para obter uma postura de segurança semelhante ou superior. 

O Acesso Condicional permite criar e definir políticas que reagem a eventos de entrada e solicitam ações adicionais antes que um usuário tenha acesso a um aplicativo ou serviço. As políticas de Acesso Condicional podem ser granulares e específicas, capacitando os usuários a serem produtivos sempre e sempre, mas também protegendo sua organização.

Os padrões de segurança estão disponíveis para todos os clientes, enquanto o Acesso Condicional requer uma licença para um dos seguintes planos:

- Azure Active Directory Premium P1 ou P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 ou E5
- Enterprise Mobility & Segurança E3 ou E5

Se você quiser usar o Acesso Condicional para configurar políticas equivalentes às habilitadas por padrões de segurança, confira os seguintes guias passo a passo:

- [Exigir MFA para administradores](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Exigir MFA para gerenciamento do Azure](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [Bloquear autenticação herdda](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [Exigir MFA para todos os usuários](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Exigir o registro MFA do Azure AD](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) - Requer a Proteção de Identidade do Azure AD, que faz parte do Azure Active Directory Premium P2

Para saber mais sobre o Acesso Condicional, consulte [O que é o Acesso Condicional?](/azure/active-directory/conditional-access/overview) Para obter mais informações sobre como criar políticas de Acesso Condicional, consulte [Create a Conditional Access policy](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy).

> [!NOTE]
> Se você tiver um plano ou licença que fornece Acesso Condicional, mas ainda não criou nenhuma política de Acesso Condicional, você pode usar os padrões de segurança. No entanto, você precisará desativar os padrões de segurança antes de poder usar as políticas de Acesso Condicional.
