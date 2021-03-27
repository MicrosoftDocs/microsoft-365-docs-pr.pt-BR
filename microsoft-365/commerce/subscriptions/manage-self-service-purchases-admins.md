---
title: Gerenciar compras de autoatendir (Administradores)
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce
search.appverid:
- MET150
description: Os administradores podem aprender a gerenciar compras de autoatendados feitas pelos usuários em sua organização.
ms.openlocfilehash: febf0ee470e735a454dc7a9e747de5025c7a4a51
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398163"
---
# <a name="manage-self-service-purchases-admin"></a>Gerenciar compras de autoatendimento (Administrador)

Como administrador, você pode ver compras autoatendadas feitas por pessoas em sua organização. Você vê o nome do produto, o nome do comprador, as assinaturas compradas, a data de expiração, o preço de compra e os usuários atribuídos para cada compra de autoatendido. Se necessário pela sua organização, você pode desativar a compra de autoatendados por produto por meio do PowerShell. Você tem as mesmas políticas de gerenciamento e acesso de dados sobre produtos comprados por meio da compra de autoatendados ou centralmente.

Você também pode controlar se os usuários em sua organização podem fazer compras de autoatendado. Para obter mais informações, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Exibir assinaturas de autoatend

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.

::: moniker-end

2. Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.
3. Para exibir mais detalhes sobre uma assinatura, escolha um na lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Exibir quem tem licenças para uma assinatura de compra de autoatend

> [!NOTE]
> Como administrador, você não pode atribuir ou desatribuição de licenças para uma assinatura de compra de autoatendados comprada por um usuário em sua organização. Você pode assumir uma assinatura de compra [autoatendente](#take-over-a-self-service-purchase-subscription)e, em seguida, atribuir ou desatribuição de licenças.

::: moniker range="o365-worldwide"

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página  > **Licenças de** Cobrança.
::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página  > **Licenças de** Cobrança.

::: moniker-end

2. Selecione o ícone de filtro e escolha **Autoatendado**.
3. Selecione um produto para ver licenças atribuídas às pessoas.
    > [!NOTE]
    > Se houver várias compras para um produto, esse produto será listado apenas uma vez, e **a** coluna Quantidade Disponível mostrará o total de todas as assinaturas compradas para esse produto.
4. A **lista** Usuários é agrupada pelos nomes de pessoas que fizeram compras de autoatendido.
5. Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e escolha **Exportar usuários**.

## <a name="disable-or-enable-self-service-purchases"></a>Desabilitar ou habilitar compras autoatendenciadas

Você pode desabilitar ou habilitar compras de autoatendencia para usuários em sua organização. O **módulo MSCommerce** PowerShell inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendiço e para quais produtos.

Você pode usar o **módulo MSCommerce** PowerShell para:

- Exibir o estado padrão do **valor do parâmetro AllowSelfServicePurchase,** seja ele habilitado ou desabilitado pelo produto
- Exibir uma lista de produtos aplicáveis e se a compra de autoatendados está habilitada ou desabilitada
- Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo

Para obter mais informações, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizar licenças em uma única assinatura

Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de contratos existentes para usuários atribuídos a compras de autoatendência. Depois de atribuir essas licenças compradas centralmente, você pode solicitar que os compradores cancelem suas assinaturas existentes.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Serviços de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Compra de</a> Cobrança.

::: moniker-end

::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Serviços de** Compra > **de** Cobrança.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Serviços de** Compra > **de** Cobrança.

::: moniker-end

2. Encontre e escolha o produto que você deseja comprar e escolha **Comprar**.
3. Conclua as etapas restantes para concluir sua compra.
4. Siga as etapas em [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.
5. Atribua licenças a todos os que têm uma licença na outra assinatura. Para etapas completas, [consulte Atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md).
6. Entre em contato com a pessoa que comprou a assinatura de compra de autoatend.0 e peça que [ela cancele.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Assumir uma assinatura de compra de autoatend

Você pode assumir uma assinatura de compra autoatendida feita por um usuário em sua organização. Ao assumir uma assinatura de compra de autoatendados, você tem duas opções:

1. Mova os usuários para uma assinatura diferente e cancele a assinatura original.
2. Cancele a assinatura de compra de autoatendido e remova licenças de usuários atribuídos.

### <a name="move-users-to-a-different-subscription"></a>Migrar usuários para uma assinatura diferente

Quando você move usuários para uma assinatura diferente, a assinatura antiga é automaticamente cancelada. O usuário que comprou originalmente a assinatura de compra de autoatendido recebe um email informando que a assinatura foi cancelada.

> [!NOTE]
> Você deve ter uma licença disponível para cada usuário que está movendo na assinatura para a que você está movendo os usuários.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.

::: moniker-end

2. Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.
3. Selecione a assinatura que você deseja assumir.
4. Na página detalhes da assinatura, na seção **Assinaturas e** configurações, selecione **Assumir o controle dessa assinatura**.
5. No painel direito, selecione **Mover usuários**.
6. Selecione o produto para o que você deseja mover os usuários e, em seguida, **selecione Mover usuários**.
7. Na caixa **Mover usuários para,** selecione **Mover usuários**. O processo de movimentação pode levar vários minutos. Não feche o navegador enquanto o processo é executado.
8. Quando o processo de movimentação for concluído, feche o **painel Mover concluído.**
9. Na página detalhes da assinatura, o **status de assinatura** da assinatura adquirida por autoatendados mostra como **Excluído**.

### <a name="cancel-a-self-service-purchase-subscription"></a>Cancelar uma assinatura de compra de autoatend

Quando você opta por cancelar uma assinatura de compra de autoatendado, os usuários com licenças perdem acesso ao produto. O usuário que comprou originalmente a assinatura de compra de autoatendido recebe um email informando que a assinatura foi cancelada.

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.

::: moniker-end

::: moniker range="o365-germany"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.

::: moniker-end

::: moniker range="o365-21vianet"

1. No centro <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">de administração,</a>vá para a página **Cobrança** > **seus** produtos.

::: moniker-end

2. Na guia **Produtos,** selecione o ícone de filtro e, em seguida, **selecione Autoatendados**.
3. Selecione a assinatura que você deseja cancelar.
4. Na página detalhes da assinatura, na seção **Assinaturas e** configurações, selecione **Assumir o controle dessa assinatura**.
5. No painel direito, selecione **Cancelar assinatura**.
6. Selecione um motivo para o cancelamento na listada e selecione **Cancelar assinatura**.
7. Na caixa **Tem certeza de que deseja cancelar?** Selecione Cancelar **assinatura**.
8. Feche o painel direito.
9. Na página detalhes da assinatura, o **status da assinatura** é como **Excluído**.

## <a name="need-help-contact-us"></a>Precisa de ajuda? Entre em contato conosco.

Para perguntas comuns sobre compras de autoatend pois, consulte Perguntas frequentes sobre compras de [autoatend nome.](self-service-purchase-faq.md)

Se você tiver dúvidas ou precisar de ajuda com compras de [autoatendém, entre em contato com o suporte](../../admin/contact-support-for-business-products.md).