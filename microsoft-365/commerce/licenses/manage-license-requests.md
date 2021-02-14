---
title: Gerenciar solicitações de licença
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- commerce
ms.custom: MACBillingLicensesRequests
search.appverid:
- MET150
description: Saiba como analisar e aprovar ou negar solicitações de licença de usuários para sua assinatura do Microsoft 365 para empresas.
ms.date: 08/07/2020
ms.openlocfilehash: cbcdc5550d404278832cc702560ac55f6ace8a44
ms.sourcegitcommit: 9550298946f8accb90cd59be7b46b71d4bf4f8cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2020
ms.locfileid: "46597646"
---
# <a name="manage-license-requests"></a>Gerenciar solicitações de licença

> [!NOTE]
> As informações neste artigo só se aplicarão a produtos comprados por autoatendados. Para saber mais, confira Perguntas [frequentes sobre compra de autoatend saiba](../subscriptions/self-service-purchase-faq.md)mais.

Se você desabilitar as compras self-service em sua organização, poderá usar solicitações de licenças para gerenciar o processo de solicitação de licença para seus usuários. Quando um usuário tenta fazer uma compra self-service para um produto que você bloqueou, ele pode enviar uma solicitação de licença para você, o administrador. Ao fazer uma solicitação, eles podem adicionar os nomes de outros usuários que também precisam de licenças para o produto.

> [!NOTE]
> Se você impedir que os usuários fazem compras de autoatend bem-vindo, a Microsoft não enviará emails de marketing para eles. Além disso, se eles estão usando uma versão de avaliação de um produto, eles não veem prompts para comprá-lo. Para saber mais, consulte [Gerenciar compras de autoatendir (Administrador).](../subscriptions/manage-self-service-purchases-admins.md)

Para ver e gerenciar solicitações de licença, o administrador usa a guia **Solicitações** na **página Licenciamento.** A lista mostra o nome do produto solicitado, o nome da pessoa que está solicitando uma licença, a data solicitada e o status da solicitação. Os administradores podem filtrar a lista para mostrar as solicitações pendentes ou concluídas. As solicitações são mantidas por 30 dias.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global para executar as tarefas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Usar seu próprio processo de solicitação

Se sua organização tiver seu próprio processo de solicitação, você poderá usá-lo em vez disso. Você cria uma mensagem que é exibida para os usuários quando eles solicitam uma licença.

> [!IMPORTANT]
> Se você usar seu próprio processo de solicitação, nenhuma solicitação será exibida na **guia Solicitações.** As solicitações existentes de antes de você adicionar a mensagem continuam aparecendo até que você as aprove ou reprove.

1. No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança e selecione a guia **Solicitações.**
2. Selecione **Usar seu processo de solicitação existente em vez disso.**
3. No painel direito, na **caixa** Mensagem, digite a mensagem que você deseja que os usuários vejam quando solicitarem uma licença. Se você também quiser incluir um link para a política da sua organização ou outra documentação, insira a URL na caixa de texto Link para documentação **(opcional).**
4. Selecione **Salvar**.

Ao retornar à lista **solicitações,** você verá a mensagem **que está usando seu próprio processo de solicitação de licença.** Para fazer alterações na mensagem enviada aos usuários, selecione **Usar seu processo de solicitação existente.**

## <a name="stop-using-your-own-request-process"></a>Parar de usar seu próprio processo de solicitação

1. No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança e selecione a guia **Solicitações.**
2. Selecione **Usar seu processo de solicitação existente em vez disso.**
3. No painel direito, des clear the **Use my organization's request process** check box.
4. Selecione **Salvar**.

## <a name="approve-or-deny-a-license-request"></a>Aprovar ou negar uma solicitação de licença

1. No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança e selecione a guia **Solicitações.**
2. Selecione a linha que contém a solicitação que você deseja analisar. O painel direito mostra detalhes sobre quais usuários querem licenças para o produto.
3. Para negar toda a solicitação, selecione **Não aprovar** e, na caixa de diálogo, selecione **Não aprovar.**
4. Para negar a solicitação a alguns usuários, mas aprovar outros, selecione o X pelo nome dos usuários que você deseja remover. Seus nomes são movidos para **Não atribuir a esses usuários.**
5. Se você tiver mais de um produto, em **Selecionar um** produto, selecione o que você deseja usar para atribuir licenças.
6. Para negar aos usuários o acesso a determinados aplicativos e serviços, **expanda** Ativar ou desativar aplicativos e serviços e des marque as caixas de seleção dos que você deseja excluir.
7. Na parte inferior do painel, digite uma mensagem opcional na caixa de texto.
8. Quando terminar, selecione **Aprovar**. O painel direito mostra os detalhes da solicitação.
9. Feche o painel direito.
    Os usuários recebem um email informando que a solicitação foi aprovada ou negada.

## <a name="related-content"></a>Conteúdo relacionado

[Atribuir licenças a usuários](../../admin/manage/assign-licenses-to-users.md) (artigo)\
[Mover usuários para uma assinatura diferente](../subscriptions/move-users-different-subscription.md) (artigo)\
[Comprar ou remover licenças de assinatura](buy-licenses.md) (artigo)