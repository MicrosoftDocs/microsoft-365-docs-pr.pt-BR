---
title: Remover licença de caixa de correio compartilhada
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Remova a licença de uma caixa de correio compartilhada para atribuí-la a outro usuário. '
ms.openlocfilehash: d552cfb77ff0ab2853939c6cb25fd4737f8c17d3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537578"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Remover uma licença de uma caixa de correio compartilhada

As caixas de correio compartilhadas geralmente não exigem uma licença. Siga estas instruções para remover uma licença de uma caixa de correio compartilhada para que você possa atribuí-la a um usuário ou retornar a licença para que você não está pagando por uma licença que não precisa.

> [!NOTE]
>
> Uma licença é necessária nos seguintes cenários:
>
> 1. A caixa de correio compartilhada tem mais de 50 GB de armazenamento em uso.
> 2. A caixa de correio compartilhada usa o arquivamento local.
> 3. A caixa de correio compartilhada é colocada em contencioso.
> 4. A caixa de correio compartilhada tem uma licença do Microsoft Defender atribuída.

## <a name="remove-the-license"></a>Remover a licença

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>.

::: moniker-end

   > [!NOTE]
   > Você precisa remover a licença da página Usuários ativos. Você não pode remover a licença da página Caixa de Correio Compartilhada porque as licenças são configurações do usuário.
  
2. Selecione a caixa de correio compartilhada.

3. Uma guia **Licenças e Aplicativos,** **expanda Licenças** e desmarque a caixa para a licença que você deseja remover.

4. Selecione **Salvar alterações**.

5. Quando você retornar à página **Usuários ativos,** o status da caixa de correio compartilhada será **Não-licença**.

6. Você ainda está pagando pela licença. Para parar de pagar por ela, [remova a licença de sua assinatura](../../commerce/licenses/buy-licenses.md).

## <a name="related-articles"></a>Artigos relacionados

[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md)

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)
