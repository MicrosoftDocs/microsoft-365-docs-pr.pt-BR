---
title: Gerenciar compras de autoatendimento (administradores)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Os administradores podem aprender a gerenciar compras de autoatendimento feitas por usuários em sua organização.
ms.openlocfilehash: ca25bf0c3e3539196e81dcc289592028cc4dfa47
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546669"
---
# <a name="manage-self-service-purchases-admin"></a>Gerenciar compras de autoatendimento (Administrador)

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Como administrador, você pode ver compras de autoatendimento feitas por pessoas em sua organização. Você vê o nome do produto, o nome do comprador, as assinaturas adquiridas, a data de vencimento, o preço de compra e os usuários atribuídos para cada compra de autoatendimento. Se for necessário para sua organização, você poderá desativar a compras de autoatendimento por produto através do PowerShell. Você tem as mesmas políticas de gerenciamento e de acesso a dados sobre produtos comprados por autoatendimento ou de forma centralizada.

Você também pode controlar se os usuários da sua organização podem fazer compras de autoatendimento. Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Exibir assinaturas de autoatendimento

1. No centro de administração, vá para a página **cobrança**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de seus produtos</a> .
2. Na guia **produtos** , selecione o ícone de filtro e, em seguida, selecione **autoatendimento**.
3. Para exibir mais detalhes sobre uma assinatura, escolha uma na lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Exibir quem possui licenças para uma assinatura de compra de autoatendimento

1. No centro de administração, vá para a **Billing**  >  página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de cobrança.
2. Selecione o ícone de filtro e, em seguida, escolha **autoatendimento**.
3. Selecione um produto para ver licenças atribuídas a pessoas.
    > [!NOTE]
    > Se houver várias compras para um produto, esse produto será listado apenas uma vez, e a coluna **quantidade disponível** mostrará o total de todas as assinaturas compradas para o produto.
4. A lista de **usuários** é agrupada por nomes de pessoas que fizeram compras de autoatendimento.
5. Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e, em seguida, escolha **exportar usuários**.

## <a name="disable-or-enable-self-service-purchases"></a>Desabilitar ou habilitar compras de autoatendimento

Você pode desabilitar ou habilitar compras de autoatendimento para usuários em sua organização. O módulo **MSCommerce** do PowerShell inclui um valor de parâmetro **PolicyId** para **AllowSelfServicePurchase** que permite controlar se os usuários da sua organização podem fazer compras de autoatendimento e para quais produtos.

Você pode usar o módulo do PowerShell do **MSCommerce** para:

- Exibir o estado padrão do valor do parâmetro **AllowSelfServicePurchase** — se ele está habilitado ou desabilitado por produto
- Exibir uma lista de produtos aplicáveis e se a compra de autoatendimento está habilitada ou desabilitada
- Exibir ou modificar a configuração atual de um produto específico para habilitá-lo ou desabilitá-lo

Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizar licenças sob uma única assinatura

Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de acordos existentes para usuários atribuídos a compras de autoatendimento. Depois de atribuir essas licenças de compra central, você pode solicitar que os compradores cancelem as assinaturas existentes.

1. No centro de administração, vá para **Billing** a \> página serviços de <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">compra</a> de cobrança.
2. Localize e escolha o produto que você deseja comprar e escolha **comprar**.
3. Conclua as etapas restantes para concluir sua compra.
4. Siga as etapas em [Exibir quem possui licenças para uma assinatura adquirida por autoatendimento](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar uma lista de usuários para referência na próxima etapa.
5. Atribuir licenças a todas as pessoas que têm uma licença na outra assinatura. Para ver as etapas completas, confira [atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md).
6. Entre em contato com a pessoa que comprou a assinatura de compras de autoatendimento e peça que [ela seja cancelada](manage-self-service-purchases-users.md#cancel-a-subscription).

## <a name="take-over-a-self-service-purchase-subscription"></a>Assumir uma assinatura de compra de autoatendimento

Você pode assumir uma assinatura de compra de autoatendimento feita por um usuário em sua organização. Ao assumir uma assinatura de compra de autoatendimento, você tem duas opções:

1. Mova os usuários para uma assinatura diferente e cancele a assinatura original.
2. Cancele a assinatura de compra de autoatendimento e remova as licenças dos usuários atribuídos.

### <a name="move-users-to-a-different-subscription"></a>Migrar usuários para uma assinatura diferente

Quando você move usuários para uma assinatura diferente, a assinatura antiga é automaticamente cancelada. O usuário que comprou originalmente a assinatura de compra de autoatendimento recebe um email que diz que a assinatura foi cancelada.

> [!NOTE]
> Você deve ter uma licença disponível para cada usuário que estiver movendo na assinatura à qual você está migrando os usuários.

1. No centro de administração, vá para a página **cobrança**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de seus produtos</a> .
2. Na guia **produtos** , selecione o ícone de filtro e, em seguida, selecione **autoatendimento**.
3. Selecione a assinatura que você deseja assumir.
4. Na página detalhes da assinatura, na seção **assinaturas e configurações** , selecione **assumir controle dessa assinatura**.
5. No painel direito, selecione **mover usuários**.
6. Selecione o produto para o qual você deseja mover os usuários e, em seguida, selecione **mover usuários**.
7. Na caixa **mover usuários para** , selecione **mover usuários**. O processo de movimentação pode levar alguns minutos. Não feche o navegador enquanto o processo é executado.
8. Quando o processo de movimentação estiver concluído, feche o **painel mover concluído**.
9. Na página detalhes da assinatura, o **status da assinatura** para a assinatura adquirida por autoatendimento é mostrado como **excluído**.

### <a name="cancel-a-self-service-purchase-subscription"></a>Cancelar uma assinatura de compra de autoatendimento

Quando você opta por cancelar uma assinatura de compra de autoatendimento, os usuários com licenças perdem o acesso ao produto. O usuário que comprou originalmente a assinatura de compra de autoatendimento recebe um email que diz que a assinatura foi cancelada.

1. No centro de administração, vá para a página **cobrança**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de seus produtos</a> .
2. Na guia **produtos** , selecione o ícone de filtro e, em seguida, selecione **autoatendimento**.
3. Selecione a assinatura que você deseja cancelar.
4. Na página detalhes da assinatura, na seção **assinaturas e configurações** , selecione **assumir controle dessa assinatura**.
5. No painel direito, selecione **cancelar assinatura**.
6. Selecione um motivo para o cancelamento na lista suspensa e selecione **cancelar assinatura**.
7. Na caixa **tem certeza de que deseja cancelar?** , selecione **cancelar assinatura**.
8. Feche o painel direito.
9. Na página detalhes da assinatura, o **status da assinatura** é mostrado como **excluído**.

## <a name="need-help-contact-us"></a>Precisa de ajuda? Entre em contato conosco.

Para perguntas comuns sobre compras de autoatendimento, consulte [perguntas frequentes sobre compras de autoatendimento](self-service-purchase-faq.md).

Se você tiver dúvidas ou precisar de ajuda com compras de autoatendimento, [entre em contato com o suporte](../../admin/contact-support-for-business-products.md).