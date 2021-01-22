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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Saiba como você pode redefinir suas senhas usando a ferramenta de redefinição de senha de autoatendado.
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925549"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que os usuários redefinam as próprias senhas

Como administrador do Microsoft 365, você [](https://go.microsoft.com/fwlink/p/?LinkId=522677) pode permitir que as pessoas usem a ferramenta de redefinição de senha pessoal para que você não tenha que redefinir senhas para elas. Menos trabalho para você!
  
## <a name="before-you-begin"></a>Antes de começar
  
- Você pode obter a redefinição  de senha de autoatendente para usuários de nuvem gratuitamente com qualquer plano pago do Microsoft 365 para empresas, educação ou entidades sem fins lucrativos. Ele não funciona com a avaliação do Microsoft 365.

- Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure.

- **Se você estiver usando um Active Directory** local, os dois pontos acima não se aplicam. Em vez disso, você pode configurar isso, mas isso requer uma **assinatura paga do Azure AD Premium.**

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](../admin-overview/admin-overview.md)

Você deve ser um [administrador global ou administrador de senhas](about-admin-roles.md) para executar estas etapas.

## <a name="watch-let-users-reset-their-own-passwords"></a>Assista: Permitir que os usuários redefinir suas próprias senhas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="steps-let-people-reset-their-own-passwords"></a>Etapas: Permitir que as pessoas redefinir suas próprias senhas

Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.
  
::: moniker range="o365-worldwide"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administração,</a>vá para a página **configurações** > **da Organização de Configurações.**

::: moniker-end

::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Privacidade de** Segurança \> **de &amp; Configurações.**

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Privacidade de** \> **Configurações** \> **&amp; de** Segurança.

::: moniker-end

2. At the top of the **Org settings** page, select the **Security & Privacy** tab.
  
3. Selecione **Redefinição de Senha de Autoatendado.**

4. Em **Redefinição de senha de** autoatendado, selecione Ir para o portal do Azure para ativar a redefinição **de senha de autoatendado.**

5. No painel de navegação esquerdo, selecione **Usuários** e, em seguida, no **painel Usuários | Página Todos os usuários,** selecione **Redefinição de senha.**
  
6. Na página **Propriedades,** selecione **Tudo para** habilita-lo para todos em sua empresa e, em seguida, **selecione Salvar**.
  
7. Quando os usuários entrarem, eles serão solicitados a inserir informações de contato adicionais que os ajudarão a redefinir a senha no futuro.

## <a name="related-content"></a>Conteúdo relacionado

[Definir a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md)

[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md)

[Vídeos de treinamento do Microsoft 365 Business ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
