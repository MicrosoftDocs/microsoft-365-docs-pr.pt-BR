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
description: Saiba como você pode redefinir suas senhas usando a ferramenta de redefinição de senha de autoatendados.
ms.openlocfilehash: 0842430eda8c96647dd12d0da6d0c9e0481346dc
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023756"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que os usuários redefinam as próprias senhas

Como administrador do Microsoft 365, você [](https://go.microsoft.com/fwlink/p/?LinkId=522677) pode permitir que as pessoas usem a ferramenta de redefinição de senha de autoatendados para que você não tenha que redefinir senhas para elas. Menos trabalho para você!
  
## <a name="before-you-begin"></a>Antes de começar
  
- Você tem redefinição de senha  de autoatendados para usuários de nuvem gratuitamente com qualquer plano pago do Microsoft 365 business, education ou nonprofit. Ele não funciona com a avaliação do Microsoft 365.

- Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure.

- **Se você estiver usando um Active Directory local,** os dois pontos acima não se aplicam. Em vez disso, você pode configurar isso, **mas exige uma assinatura paga do Azure AD Premium**.

Este artigo é destinado às pessoas que definem a política de expiração de senhas para uma empresa, escola ou entidade sem fins lucrativos. Para concluir essas etapas, você precisa entrar com a sua conta de administrador do Microsoft 365. [O que é uma conta de administrador?](https://docs.microsoft.com/microsoft-365/business-video/admin-center-overview)

Você deve ser um [administrador global ou administrador de senha](about-admin-roles.md) para executar essas etapas.

## <a name="watch-let-users-reset-their-own-passwords"></a>Assista: permitir que os usuários redefinir suas próprias senhas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](../../business-video/index.yml).

## <a name="steps-let-people-reset-their-own-passwords"></a>Etapas: Permitir que as pessoas redefinir suas próprias senhas

Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.
  
::: moniker range="o365-worldwide"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administração,</a>vá para a página **Configurações** > **da Organização.**

::: moniker-end

::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Configurações** \> **Privacidade &amp; de** segurança.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração</a>, vá para a página **Configurações** \> **Configurações** \> **Privacidade &amp; de** segurança.

::: moniker-end

2. Na parte superior da página **Configurações da Organização,** selecione a guia **Segurança & Privacidade.**
  
3. Selecione **Redefinição de Senha de Autoatendados**.

4. Em **Redefinição de senha de** autoatenduro, selecione Ir para o portal do Azure para ativar a redefinição de senha de **autoatendados.**

5. No painel de navegação esquerdo, selecione **Usuários** e, em seguida, no **painel Usuários | Página Todos os** usuários, selecione **Redefinição de senha**.
  
6. Na página **Propriedades,** selecione **Tudo para** habilita-lo para todos em sua empresa e selecione **Salvar**.
  
7. Quando seus usuários entrarem, eles serão solicitados a inserir informações de contato adicionais que os ajudarão a redefinir sua senha no futuro.

## <a name="related-content"></a>Conteúdo relacionado

[Definir a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md)

[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md)

[Vídeos de treinamento do Microsoft 365 Business ](../../business-video/index.yml)
