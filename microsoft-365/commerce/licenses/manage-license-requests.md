---
title: Gerenciar solicitações de licença
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- MACBillingLicensesRequests
- AdminSurgePortfolio
- commerce_licensing
search.appverid: MET150
description: Saiba como revisar e aprovar ou negar solicitações de licença de usuários para sua assinatura Microsoft 365 para empresas.
ms.date: 08/07/2020
ms.openlocfilehash: 6cbfd81f4f6deba642729f1fef0b826b07a99f56
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535669"
---
# <a name="manage-license-requests"></a>Gerenciar solicitações de licença

> [!NOTE]
> As informações neste artigo só se aplica a produtos comprados por autoatendados. Para saber mais, confira Perguntas frequentes sobre [compra de autoatend.](../subscriptions/self-service-purchase-faq.yml)

Se você desabilitar as compras de autoatendito em sua organização, poderá usar solicitações de licença para gerenciar o processo de solicitação de licença para seus usuários. Quando um usuário tenta fazer uma compra de autoatendito para um produto que você bloqueou, ele pode enviar uma solicitação para uma licença para você, o administrador. Quando eles fazem uma solicitação, eles podem adicionar os nomes de outros usuários que também precisam de licenças para o produto.

> [!NOTE]
> Se você impedir que os usuários comprem autoatendam, a Microsoft não enviará emails de marketing para eles. Além disso, se eles estão usando uma versão de avaliação de um produto, eles não veem prompts para comprá-lo. Para saber mais, consulte [Manage self-service purchases (Admin)](../subscriptions/manage-self-service-purchases-admins.md).

Para ver e gerenciar solicitações de licença, o administrador usa a guia **Solicitações** na página **Licenciamento.** A lista mostra o nome do produto solicitado, o nome da pessoa que está solicitando uma licença, a data solicitada e o status da solicitação. Os administradores podem filtrar a lista para mostrar solicitações pendentes ou concluídas. As solicitações são mantidas por 30 dias.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global para executar as tarefas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Usar seu próprio processo de solicitação

Se sua organização tiver seu próprio processo de solicitação, você poderá usá-lo. Você cria uma mensagem que é exibida para os usuários quando eles solicitam uma licença.

> [!IMPORTANT]
> Se você usar seu próprio processo de solicitação, nenhuma solicitação será exibida na guia **Solicitações.** As solicitações existentes de antes de você adicionar sua mensagem continuam a aparecer até que você as aprove ou as decline.

1. No centro de administração, vá para a página **Licenças de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> e selecione a **guia Solicitações.**
2. Selecione **Usar seu processo de solicitação existente.**
3. No painel direito, na **caixa** Mensagem, digite a mensagem que você deseja que os usuários vejam quando solicitarem uma licença. Se você também quiser incluir um link para sua política de organizações ou outra documentação, insira a URL na caixa de texto **Link to documentation (opcional).**
4. Selecione **Salvar**.

Ao retornar à lista **Solicitações,** você verá a mensagem **Você está usando seu próprio processo de solicitação de licença.** Para fazer alterações na mensagem enviada aos usuários, selecione Usar seu processo de solicitação **existente.**

## <a name="stop-using-your-own-request-process"></a>Pare de usar seu próprio processo de solicitação

1. No centro de administração, vá para a página **Licenças de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> e selecione a **guia Solicitações.**
2. Selecione **Usar seu processo de solicitação existente.**
3. No painel direito, desimpe a caixa de seleção **Usar o processo de** solicitação da minha organização.
4. Selecione **Salvar**.

## <a name="approve-or-deny-a-license-request"></a>Aprovar ou negar uma solicitação de licença

1. No centro de administração, vá para a página **Licenças de** Cobrança  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"></a> e selecione a **guia Solicitações.**
2. Selecione a linha que contém a solicitação que você deseja revisar. O painel direito mostra detalhes sobre quais usuários querem licenças para o produto.
3. Para negar toda a solicitação, selecione **Não aprovar** e, na caixa de diálogo, selecione **Não aprovar**.
4. Para negar a solicitação a alguns usuários, mas aprovar outros, selecione o X pelo nome dos usuários que você deseja remover. Seus nomes são movidos em **Não atribuir a esses usuários**.
5. Se você tiver mais de um produto, em **Selecionar um** produto, selecione o que deseja usar para atribuir licenças.
6. Para negar aos usuários o acesso a determinados aplicativos e serviços, expanda **Ativar** ou desativar aplicativos e serviços e desempurar as caixas de seleção dos que você deseja excluir.
7. Na parte inferior do painel, digite uma mensagem opcional na caixa de texto.
8. Quando terminar, selecione **Aprovar**. O painel direito mostra os detalhes da solicitação.
9. Feche o painel direito.
    Os usuários recebem um email que diz que sua solicitação foi aprovada ou negada.

## <a name="related-content"></a>Conteúdo relacionado

[Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md) (artigo) \
[Mover usuários para uma assinatura diferente](../subscriptions/move-users-different-subscription.md) (artigo)\
[Comprar ou remover licenças de assinatura](buy-licenses.md) (artigo)
