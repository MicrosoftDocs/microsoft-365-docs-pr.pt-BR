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
description: Saiba como revisar e aprovar ou negar solicitações de licença de usuários para sua assinatura do Microsoft 365 for Business.
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
> As informações neste artigo se aplicam somente a produtos comprados por autoatendimento. Para saber mais, confira [perguntas frequentes sobre compras de autoatendimento](../subscriptions/self-service-purchase-faq.md).

Se você desabilitar compras de autoatendimento em sua organização, poderá usar solicitações de licenças para gerenciar o processo de solicitação de licença para seus usuários. Quando um usuário tenta fazer uma compra de autoatendimento para um produto que você bloqueou, ele pode enviar uma solicitação de licença para você, o administrador. Ao fazer uma solicitação, eles podem adicionar os nomes de outros usuários que também precisam de licenças para o produto.

> [!NOTE]
> Se você impede que os usuários façam compras de autoatendimento, a Microsoft não envia emails de marketing. Além disso, se ele estiver usando uma versão de avaliação de um produto, ele não verá prompts para comprá-lo. Para saber mais, confira [gerenciar compras de autoatendimento (administrador)](../subscriptions/manage-self-service-purchases-admins.md).

Para ver e gerenciar solicitações de licença, o administrador usa a guia **solicitações** na página **Licenciamento** . A lista mostra o nome do produto solicitado, o nome da pessoa que está solicitando uma licença, uma data solicitada e o status da solicitação. Os administradores podem filtrar a lista para mostrar as solicitações pendentes ou concluídas. As solicitações são mantidas por 30 dias.

## <a name="before-you-begin"></a>Antes de começar

Você deve ser um administrador global para executar as tarefas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-your-own-request-process"></a>Usar seu próprio processo de solicitação

Se sua organização tiver seu próprio processo de solicitação, você poderá usá-lo. Você cria uma mensagem que é exibida aos usuários quando eles solicitam uma licença.

> [!IMPORTANT]
> Se você usar seu próprio processo de solicitação, nenhuma solicitação será exibida na guia **solicitações** . as solicitações existentes de antes da adição da mensagem continuarão a aparecer até que você as aprove ou recuse.

1. No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança e, em seguida, selecione a guia **solicitações** .
2. Selecione **usar seu processo de solicitação existente**.
3. No painel direito, na caixa **mensagem** , digite a mensagem que você deseja que os usuários vejam quando solicitarem uma licença. Se você também quiser incluir um link para a política de suas organizações ou outra documentação, digite a URL na caixa de texto **vincular à documentação (opcional)** .
4. Selecione **Salvar**.

Ao retornar à lista de **solicitações** , você vê a mensagem **que está usando seu próprio processo de solicitação de licença**. Para fazer alterações na mensagem que é enviada aos usuários, selecione **usar o processo de solicitação existente**.

## <a name="stop-using-your-own-request-process"></a>Parar de usar seu próprio processo de solicitação

1. No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança e, em seguida, selecione a guia **solicitações** .
2. Selecione **usar seu processo de solicitação existente**.
3. No painel direito, desmarque a caixa de seleção **usar o processo de solicitação da minha organização** .
4. Selecione **Salvar**.

## <a name="approve-or-deny-a-license-request"></a>Aprovar ou negar uma solicitação de licença

1. No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança e, em seguida, selecione a guia **solicitações** .
2. Selecione a linha que contém a solicitação que você deseja revisar. O painel direito mostra detalhes sobre quais usuários desejam licenças para o produto.
3. Para negar a solicitação inteira, selecione **não aprovar**e, na caixa de diálogo, selecione **não aprovar**.
4. Para negar alguns usuários para a solicitação, mas aprovar outros, selecione o X pelo nome dos usuários que você deseja remover. Seus nomes são movidos em **não atribuir a estes usuários**.
5. Se você tiver mais de um produto, em **selecionar um produto**, selecione aquele que você deseja usar para atribuir licenças para o.
6. Para negar o acesso dos usuários a determinados aplicativos e serviços, expanda **Ativar ou desativar os aplicativos e serviços e**desmarque as caixas de seleção para aqueles que você deseja excluir.
7. Na parte inferior do painel, digite uma mensagem opcional na caixa de texto.
8. Quando tiver terminado, selecione **aprovar**. O painel direito mostra os detalhes da solicitação.
9. Feche o painel direito.
    Os usuários recebem um email que diz que sua solicitação foi aprovada ou negada.

## <a name="related-content"></a>Conteúdo relacionado

[Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md) (artigo) \
[Mover usuários para uma assinatura diferente](../subscriptions/move-users-different-subscription.md) (artigo) \
[Comprar ou remover licenças de assinatura](buy-licenses.md) (artigo)