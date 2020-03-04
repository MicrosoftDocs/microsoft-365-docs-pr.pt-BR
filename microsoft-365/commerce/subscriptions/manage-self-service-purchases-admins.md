---
title: Gerenciar compras de autoatendimento (administradores)
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
- commerce
search.appverid:
- MET150
description: Os administradores podem aprender a gerenciar compras de autoatendimento feitas por usuários em sua organização.
ms.openlocfilehash: ab0e98963e1274925fcf678307907a93eafc9663
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2020
ms.locfileid: "42409626"
---
# <a name="manage-self-service-purchases-admin"></a>Gerenciar compras de autoatendimento (Administrador)

Como administrador, você pode ver compras de autoatendimento feitas por pessoas em sua organização. Você pode ver o produto, o nome do comprador, as assinaturas adquiridas, a data de vencimento, o preço de compra e os usuários atribuídos para cada compra de autoatendimento. Se for necessário para sua organização, você poderá desativar a compras de autoatendimento por produto através do PowerShell. Você tem as mesmas políticas de gerenciamento e de acesso a dados sobre produtos comprados por autoatendimento ou de forma centralizada.

Você também pode controlar se os usuários da sua organização podem fazer compras de autoatendimento. Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

## <a name="view-self-service-subscriptions"></a>Exibir assinaturas de autoatendimento

1. No centro de administração, vá para a página de serviços de **cobrança** > de<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">produtos &</a> .

2. Ao lado de **refinar resultados**, no menu suspenso **tipo de conta** , escolha **autoatendimento**.

3. Para exibir mais detalhes sobre uma assinatura, escolha uma na lista.

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a>Exibir quem possui licenças para uma assinatura de compra de autoatendimento

1. No centro de administração, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .

2. Escolha o ícone de filtro e, em seguida, escolha **autoatendimento**.

3. Selecione um produto para ver licenças atribuídas a pessoas.

    > [!NOTE]
    > Se houver várias compras para um produto, esse produto será listado apenas uma vez, e a coluna **quantidade disponível** mostrará o total de todas as assinaturas compradas para o produto.

4. A lista de **usuários** é agrupada por nomes de pessoas que fizeram compras de autoatendimento.

5. Para exportar uma lista de usuários com licenças para essas assinaturas, escolha as assinaturas que você deseja exportar e, em seguida, escolha **exportar usuários**.

## <a name="disable-or-enable-self-service-purchases"></a>Desabilitar ou habilitar compras de autoatendimento

Você pode desabilitar ou habilitar compras de autoatendimento para usuários em sua organização. O módulo **MSCommerce** do PowerShell inclui um valor de parâmetro **PolicyId** para **AllowSelfServicePurchase** que permite controlar se os usuários da sua organização podem fazer compras de autoatendimento e para quais produtos.

Você pode usar o módulo do PowerShell do **MSCommerce** para:

- Exibir o estado padrão do valor **** &mdash; do parâmetro AllowSelfServicePurchase se ele está habilitado ou desabilitado por produto
- Exibir uma lista de produtos aplicáveis e se a compra de autoatendimento está habilitada ou desabilitada
- Exibir ou modificar a configuração atual de um produto específico para habilitá-lo ou desabilitá-lo

Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

## <a name="centralize-licenses-under-a-single-subscription"></a>Centralizar licenças sob uma única assinatura

Você pode atribuir licenças existentes ou comprar assinaturas adicionais por meio de acordos existentes para usuários atribuídos a compras de autoatendimento. Depois de atribuir essas licenças de compra central, você pode solicitar que os compradores cancelem as assinaturas existentes.

1. Entre no centro de <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Administração</a> com sua conta de administrador global ou de cobrança.

2. Vá para a página de<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">serviços de compra</a> de **cobrança** > .

3. Localize e escolha o produto que você deseja comprar e escolha **comprar**.

4. Conclua as etapas restantes para concluir sua compra.

5. Siga as etapas em [Exibir quem possui licenças para uma assinatura adquirida por autoatendimento](#view-who-has-licenses-for-a-self-service-purchase-subscription) para exportar uma lista de usuários para referência na etapa 6.

6. Atribuir licenças a todas as pessoas que têm uma licença na outra assinatura. Para ver as etapas completas, confira [atribuir licenças aos usuários](../../admin/manage/assign-licenses-to-users.md).

7. Entre em contato com a pessoa que comprou a assinatura de compras de autoatendimento e peça que ela seja cancelada.

## <a name="need-help-contact-us"></a>Precisa de ajuda? Entre em contato conosco.

Para perguntas comuns sobre compras de autoatendimento, consulte [perguntas frequentes sobre compras de autoatendimento](self-service-purchase-faq.md).

Se você tiver dúvidas ou precisar de ajuda com compras de autoatendimento, [entre em contato com o suporte](../../admin/contact-support-for-business-products.md).
