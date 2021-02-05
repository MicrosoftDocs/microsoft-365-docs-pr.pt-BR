---
title: Gerenciar compras self-service (Administradores)
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
description: Os administradores podem aprender a gerenciar compras de autoatendida feitas por usuários em sua organização.
ms.openlocfilehash: 3e04f58c10b14aca8b356c064106b7107f144d91
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114688"
---
# <a name="manage-self-service-purchases-admin"></a>Gerenciar compras de autoatendimento (Administrador)

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Como administrador, você pode ver compras self-service feitas por pessoas em sua organização. Você vê o nome do produto, o nome do comprador, as assinaturas adquiridas, a data de expiração, o preço da compra e os usuários atribuídos para cada compra de autoatendido. Se exigido pela sua organização, você pode desativar a compra por produto por meio do PowerShell. Você tem as mesmas políticas de gerenciamento e acesso de dados sobre produtos comprados por meio de compra de autoatendínio ou centralmente.

Você também pode controlar se os usuários em sua organização podem fazer compras de autoatendado. Para obter mais informações, [consulte Usar AllowSelfServicePurchase para o módulo MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Exibir assinaturas self-service

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **Produtos,** selecione o ícone de filtro e selecione **Autoatendínio.**
3. Para exibir mais detalhes sobre uma assinatura, escolha uma na lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Exibir quem tem licenças para uma assinatura de compra self-service

1. No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.
2. Selecione o ícone de filtro e, em **seguida, escolha Autoatend site.**
3. Selecione um produto para ver as licenças atribuídas às pessoas.
    > [!NOTE]
    > Se houver várias compras para um produto, esse produto só será listado uma vez, e **a** coluna Quantidade disponível mostrará o total de todas as assinaturas compradas para esse produto.
4. A **lista** Usuários é agrupada pelos nomes das pessoas que realizaram compras de autoatendido.
5. Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e escolha **Exportar usuários.**

## <a name="disable-or-enable-self-service-purchases"></a>Desabilitar ou habilitar compras self-service

Você pode desabilitar ou habilitar compras de autoatendencial para usuários em sua organização. O módulo **MSCommerce** PowerShell inclui um valor de parâmetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar se os usuários em sua organização podem fazer compras de autoatendente e para quais produtos.

Você pode usar o **módulo MSCommerce** PowerShell para:

- Exibir o estado padrão do valor do parâmetro **AllowSelfServicePurchase** — se ele está habilitado ou desabilitado por produto
- Exibir uma lista de produtos aplicáveis e se a compra self-service está habilitada ou desabilitada
- Exibir ou modificar a configuração atual de um produto específico para habilita-lo ou desabilitá-lo

Para obter mais informações, [consulte Usar AllowSelfServicePurchase para o módulo MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizar licenças em uma única assinatura

Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de contratos existentes para usuários atribuídos a compras de autoatendido. Depois de atribuir essas licenças adquiridas centralmente, você pode solicitar que os compradores cancelem suas assinaturas existentes.

1. No centro de administração, vá para a página **De compra** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">de</a> cobrança.
2. Encontre e escolha o produto que você deseja comprar e escolha **Comprar**.
3. Conclua as etapas restantes para concluir a compra.
4. Siga as etapas em Exibir quem tem licenças para uma assinatura adquirida por [autoatendado](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar uma lista de usuários para fazer referência na próxima etapa.
5. Atribua licenças a todos que têm uma licença na outra assinatura. Para ver as etapas completas, [confira Atribuir licenças aos usuários.](../../admin/manage/assign-licenses-to-users.md)
6. Entre em contato com a pessoa que comprou a assinatura de compra self-service e peça para [cancelá-la.](manage-self-service-purchases-users.md#cancel-a-subscription)

## <a name="take-over-a-self-service-purchase-subscription"></a>Assumir uma assinatura de compra self-service

Você pode assumir uma assinatura de compra de autoatendida feita por um usuário em sua organização. Ao assumir uma assinatura de compra self-service, você tem duas opções:

1. Mova os usuários para uma assinatura diferente e cancele a assinatura original.
2. Cancele a assinatura de compra de autoatendido e remova licenças de usuários atribuídos.

### <a name="move-users-to-a-different-subscription"></a>Migrar usuários para uma assinatura diferente

Quando você move usuários para uma assinatura diferente, a assinatura antiga é cancelada automaticamente. O usuário que originalmente comprou a assinatura de compra self-service recebe um email informando que a assinatura foi cancelada.

> [!NOTE]
> Você deve ter uma licença disponível para cada usuário que está movendo na assinatura para a sua mudança de usuário.

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **Produtos,** selecione o ícone de filtro e selecione **Autoatendínio.**
3. Selecione a assinatura que você deseja assumir.
4. Na página de detalhes da assinatura, na **seção Assinaturas** e configurações, selecione **Assumir o controle dessa assinatura.**
5. No painel direito, selecione **Mover usuários.**
6. Selecione o produto para o que você deseja mover os usuários e, em seguida, **selecione Mover usuários.**
7. Na caixa **Mover usuários para,** selecione **Mover usuários**. O processo de movimentação pode levar vários minutos. Não feche o navegador enquanto o processo é executado.
8. Quando o processo de movimentação for concluído, feche o **painel Mover concluído.**
9. Na página de detalhes da assinatura, o **status da Assinatura** para a assinatura adquirida por autoatendado aparece como **Excluído.**

### <a name="cancel-a-self-service-purchase-subscription"></a>Cancelar uma assinatura de compra self-service

Quando você opta por cancelar uma assinatura de compra de autoatendado, os usuários com licenças perdem o acesso ao produto. O usuário que originalmente comprou a assinatura de compra de autoatendido recebe um email informando que a assinatura foi cancelada.

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **Produtos,** selecione o ícone de filtro e selecione **Autoatendínio.**
3. Selecione a assinatura que você deseja cancelar.
4. Na página de detalhes da assinatura, na **seção Assinaturas** e configurações, selecione **Assumir o controle dessa assinatura.**
5. No painel direito, selecione **Cancelar assinatura.**
6. Selecione um motivo para o cancelamento na lista drop-down e, em seguida, **selecione Cancelar assinatura.**
7. In the **Are you sure you want to cancel?** box, select Cancel **subscription**.
8. Feche o painel direito.
9. Na página de detalhes da assinatura, o **status da assinatura** aparece como **Excluído.**

## <a name="need-help-contact-us"></a>Precisa de ajuda? Fale conosco.

Para perguntas comuns sobre compras self-service, consulte Perguntas frequentes sobre [compras de autoatendado.](self-service-purchase-faq.md)

Se você tiver dúvidas ou precisar de ajuda com compras self-service, entre em contato [com o suporte.](../../admin/contact-support-for-business-products.md)