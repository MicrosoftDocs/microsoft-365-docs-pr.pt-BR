---
title: Permitir que os usuários redefinam as próprias senhas no Office 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: Saiba como você pode redefinir suas senhas usando a ferramenta de redefinição de senha autoatendimento.
ms.openlocfilehash: 87accc393d08b922ebc3f75ef1aa5ddb2d0b2955
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237130"
---
# <a name="let-users-reset-their-own-passwords"></a>Permitir que os usuários redefinam as próprias senhas

Obter Crushed com pessoas solicitando que você redefina suas senhas? Como o Microsoft 365 admin, você pode permitir que as pessoas usem a [ferramenta de redefinição de senha de autoatendimento](https://go.microsoft.com/fwlink/p/?LinkId=522677) para que você não precise redefinir senhas para elas. Menos trabalho para você! 
  
Aqui estão algumas coisas que você precisa saber:
  
- Você obtém a redefinição de senhas de autoatendimento para usuários de nuvem **gratuitamente** com qualquer plano pago do Office 365 para empresas, educação ou instituições sem fins lucrativos. Ela não funciona com a avaliação do Office 365. 
    
- Ela usa o Azure. Você obterá automaticamente esse recurso no Azure **gratuitamente** quando realizar essas etapas. Não haverá custos para habilitar a redefinição de senha de autoatendimento se você não usar outros recursos do Azure. 
    
- **Se você estiver usando um Active Directory local**, os dois pontos acima não se aplicam. Em vez disso, você pode configurar isso, mas **requer uma assinatura paga do Azure ad Premium**. 

Assista a um pequeno vídeo sobre como permitir que os usuários redefinam suas próprias senhas. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="let-people-reset-their-own-passwords"></a>Permitir que as pessoas redefinam suas próprias senhas 

Estas etapas habilitam a redefinição de senhas de autoatendimento para todas as pessoas da empresa.
  
::: moniker range="o365-worldwide"
1.  No centro de administração, vá para a página **configurações** \> de <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">segurança & privacidade</a> .

::: moniker-end

::: moniker range="o365-germany"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">centro de administração</a>, vá para a página **configurações** \> de privacidade de **segurança &amp; ** .

::: moniker-end

::: moniker range="o365-21vianet"

1. No <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">centro de administração</a>, vá para a página **configurações** \> de privacidade de **segurança &amp; ** .

::: moniker-end

   
2. Em **permitir que as pessoas redefinam suas próprias senhas**, selecione o link para o **centro de administração do Azure ad**. Você receberá o Azure gratuitamente!
  
3. Selecione **usuários** na navegação à esquerda e, em seguida, selecione **Redefinir senha**.
  
4. Na página Propriedades, selecione **tudo** para habilitá-lo para todas as pessoas em sua empresa e, em seguida, selecione **salvar**.
  
5. Quando os usuários entram no Office 365, devem inserir informações de contato adicionais que ajudarão a redefinir a senha deles no futuro.

## <a name="related-articles"></a>Artigos relacionados

[Definir a política de expiração de senha para sua organização](../manage/set-password-expiration-policy.md)
  
[Definir a senha de um usuário individual para nunca expirar](set-password-to-never-expire.md)

[Vídeos de treinamento do Microsoft 365 Business ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
