---
title: Permitir que os usuários redefinam as próprias senhas
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
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Saiba como você pode redefinir suas senhas usando a ferramenta de redefinição de senha autoatendimento.
ms.openlocfilehash: bbde517858186d844412aca21f231620ed76496a
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551915"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que os usuários redefinam as próprias senhas

Como o Microsoft 365 admin, você pode permitir que as pessoas usem a [ferramenta de redefinição de senha de autoatendimento](https://go.microsoft.com/fwlink/p/?LinkId=522677) para que você não precise redefinir senhas para elas. Menos trabalho para você!
  
## <a name="before-you-begin"></a>Antes de começar
  
- Você obtém redefinição de senha de autoatendimento para usuários em nuvem **gratuitamente** com qualquer plano pago de negócios, educação ou sem fins lucrativos da Microsoft 365. Ele não funciona com a avaliação da Microsoft 365.

- Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure.

- **Se você estiver usando um Active Directory local**, os dois pontos acima não se aplicam. Em vez disso, você pode configurar isso, mas **requer uma assinatura paga do Azure ad Premium**.

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../admin-overview/admin-overview.md)

Você deve ser um [administrador de administrador ou de senha global](about-admin-roles.md) para executar estas etapas.

## <a name="watch-let-users-reset-their-own-passwords"></a>Watch: permitir que os usuários redefinam suas próprias senhas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="steps-let-people-reset-their-own-passwords"></a>Etapas: permitir que as pessoas redefinam suas próprias senhas

Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.
  
::: moniker range="o365-worldwide"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração</a>, vá para a página Configurações da organização de **configurações** > **Org settings** .

::: moniker-end

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para a página **configurações** de \> **&amp; privacidade de segurança** .

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para a **Settings** \> página de privacidade de segurança **das configurações** de configurações \> **&amp;** .

::: moniker-end

2. Na parte superior da página **configurações da organização** , selecione a guia **privacidade & segurança** .
  
3. Selecione **redefinição de senha de autoatendimento**.

4. Em **redefinição de senha de autoatendimento**, selecione **ir para o portal do Azure para ativar a redefinição de senha de autoatendimento**.

5. No painel de navegação esquerdo, selecione **usuários** e, em seguida, em **usuários | Página todos os usuários** , selecione **redefinição de senha**.
  
6. Na página **Propriedades** , selecione **tudo** para habilitá-lo para todas as pessoas em sua empresa e, em seguida, selecione **salvar**.
  
7. Quando seus usuários entrarem, eles serão solicitados a inserir informações de contato adicionais que os ajudarão a redefinir sua senha no futuro.

## <a name="related-content"></a>Conteúdo relacionado

[Definir a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md)

[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md)

[Vídeos de treinamento do Microsoft 365 Business ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
