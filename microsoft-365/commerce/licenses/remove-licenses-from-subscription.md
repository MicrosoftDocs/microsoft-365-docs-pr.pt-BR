---
title: Remover licenças da assinatura do Office 365 para empresas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 9c64d127-e2dd-4ecc-81f5-2f87e5a74803
description: Saiba como remover uma licença da sua assinatura do Office 365 for Business quando a licença já estiver atribuída a alguém.
ms.openlocfilehash: d1af1b5696d359daf6578e090180b79587952106
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237349"
---
# <a name="remove-licenses-from-your-office-365-for-business-subscription"></a>Remover licenças da assinatura do Office 365 para empresas

Você não pode remover uma licença de uma assinatura se ela estiver atribuída a um usuário. Se você deseja remover uma licença atualmente atribuída a alguém, será necessário [remover-licenses-from-Users](../../admin/manage/remove-licenses-from-users.md), antes de poder remover a licença da assinatura.

::: moniker range="o365-worldwide"

> [!NOTE]
> Se não estiver usando o novo centro de administração do Microsoft 365, você poderá ativá-lo selecionando a alternância **Experimentar o novo centro de administração** localizado na parte superior da Home Page.

## <a name="remove-licenses"></a>Remove licenses

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Produtos e serviços</a>.

2. Na página **produtos & serviços** , localize a assinatura da qual você deseja remover licenças e, em seguida, selecione **Adicionar/remover licenças**.

    [Não está vendo o link para Adicionar/Remover licenças?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Na caixa **total de licenças** , insira o número total de licenças necessárias para esta assinatura e selecione **Enviar alteração**. Por exemplo, se você tiver 110 licenças e quiser remover 5 delas, digite 105.

::: moniker-end

::: moniker range="o365-germany"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Assinaturas</a>.

2. Na página **assinaturas** , selecione a assinatura da qual você deseja remover licenças e, em seguida, selecione **Adicionar/remover licenças**.

    [Não está vendo o link para Adicionar/Remover licenças?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Na caixa **Total de licenças**, insira o número total de licenças necessárias para esta assinatura e, em seguida, selecione **Enviar**. Por exemplo, se você tiver 110 licenças e quiser remover 5 delas, digite 105.


::: moniker-end

::: moniker range="o365-21vianet"

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Assinaturas</a>.

2. Na página **assinaturas** , selecione a assinatura da qual você deseja remover licenças e, em seguida, selecione **Adicionar/remover licenças**.

    [Não está vendo o link para Adicionar/Remover licenças?](#what-if-i-dont-see-the-addremove-licenses-link)

3. Na caixa **Total de licenças**, insira o número total de licenças necessárias para esta assinatura e, em seguida, selecione **Enviar**. Por exemplo, se você tiver 110 licenças e quiser remover 5 delas, digite 105.

::: moniker-end

## <a name="what-if-i-dont-see-the-addremove-licenses-link"></a>Não está vendo o link para Adicionar/Remover licenças?

Esta seção descreve os motivos pelos quais o link **Adicionar/Remover licenças** pode não estar disponível e o que você pode fazer.
  
### <a name="a-credit-check-is-pending"></a>Uma verificação de crédito está pendente

Se uma verificação de crédito estiver pendente, você verá a mensagem "Verificação de crédito pendente" e não poderá remover licenças até que ela seja concluída. Se a verificação de crédito estiver pendente, confira mais tarde se a verificação foi concluída. Geralmente, as verificações de crédito levam até dois dias úteis para serem concluídas.
  
Depois que a verificação de crédito for concluída, você deverá conferir o link **Adicionar/Remover licenças** na seção **Usuários**. Em caso afirmativo, vá para [remover licenças da sua assinatura do Office 365 for Business](#remove-licenses-from-your-office-365-for-business-subscription).
  
### <a name="you-activated-the-subscription-using-a-product-key"></a>Você ativou a assinatura com uma chave do produto (Product Key)

Se a assinatura foi adquirida e ativada usando uma chave do produto (Product Key) de 25 caracteres, você verá o texto "Pré-paga". Se a assinatura foi pré-paga usando uma chave do produto (Product Key), você não poderá remover licenças, pois elas já estão pagas. No entanto, é possível remover as licenças adicionais quando renovar a assinatura.
  
### <a name="you-bought-your-subscription-through-a-partner"></a>Você adquiriu sua assinatura por meio de um parceiro

Se sua assinatura foi adquirida por meio de um CSP ou parceiro, você não pode remover licenças. Entre em contato com o CSP ou use o link centro de serviços de licenciamento por volume (VLSC) para entrar em contato com seu parceiro para obter ajuda.
  
## <a name="what-you-need-to-know-about-removing-licenses-from-users-in-office-365-for-business"></a>O que você precisa saber sobre a remoção de licenças de usuários no Office 365 para empresas

- Você precisa ser um administrador global ou um administrador de gerenciamento de usuários. Para obter mais informações, consulte [sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

- Siga estas etapas para adicionar uma licença a uma conta de usuário existente. [Saiba como adicionar uma conta de usuário e atribuir uma licença ao mesmo tempo](../../admin/add-users/add-users.md).

## <a name="articles-about-managing-licenses-for-your-subscription"></a>Artigos sobre como gerenciar licenças para sua assinatura

- [Entenda as assinaturas e licenças](subscriptions-and-licenses.md)

- [Remover licenças de usuários](../../admin/manage/remove-licenses-from-users.md)

- [Atribuir licenças a usuários](../../admin/manage/assign-licenses-to-users.md)

- [Comprar licenças para sua assinatura](buy-licenses.md)

- [Comprar outra assinatura](../buy-another-subscription.md)

- [Comprar ou editar um suplemento](../buy-or-edit-an-add-on.md)

- [Gerenciar licenças de usuário do Yammer](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-licenses-in-office-365)

## <a name="related-links"></a>Links relacionados

[Cancelar sua assinatura](../subscriptions/cancel-your-subscription.md)
