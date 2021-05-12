---
title: Perguntas frequentes sobre compra de autoatend
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
- commerce_ssp
search.appverid:
- MET150
description: Encontre respostas para perguntas frequentes sobre compras de autoatendados.
ms.date: 09/15/2020
ms.openlocfilehash: 964eca8e94f64fd2f212745abfff0cf25d45bfca
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333189"
---
# <a name="self-service-purchase-faq"></a>Perguntas frequentes sobre compra de autoatend

A compra self-service oferece aos usuários a chance de experimentar novas tecnologias e desenvolver soluções que, em última análise, beneficiam suas organizações maiores. As equipes de TI e compras centrais têm visibilidade para todos os usuários que compram e implantam soluções de compra de autoatendito por meio do Centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">do Microsoft 365.</a> Os administradores podem desativar a compra por produto por produto por meio do PowerShell. Para saber mais, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

A compra de autoatendício está disponível para a Plataforma Power (Power BI, Power Apps e Power Automate), Project e Visio.

> [!NOTE]
> A compra de autoatendam não está disponível na Índia ou para clientes governamentais ou de educação. O Project e o Visio não estão disponíveis para compra de autoatendício no Brasil e na República Democrática do Congo.

## <a name="making-a-self-service-purchase"></a>Fazendo uma compra self-service

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Como um cliente faz uma compra self-service?

Os clientes podem fazer uma compra por conta própria online a partir dos sites do produto ou de prompts de compra no aplicativo. Primeiro, os clientes são solicitados a inserir um endereço de email para garantir que eles sejam um usuário em um locatário existente do Azure Active Directory (AD). Em seguida, eles são direcionados para entrar usando suas credenciais do Azure AD. Depois de entrar, o cliente é solicitado a selecionar quantas assinaturas deseja comprar e fornecer pagamento com cartão de crédito. Quando a compra for concluída, eles poderão começar a usar sua assinatura. O comprador tem acesso a uma exibição limitada do Centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365,</a> onde ele pode atribuir licenças ao produto a outras pessoas em sua organização.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Quais são as opções de pagamento para compras self-service?

Atualmente, o cartão de crédito é o único método de pagamento disponível. Não há suporte para pagamento por meio de faturamento.

### <a name="who-can-buy-through-self-service-purchase"></a>Quem pode comprar por meio da compra de autoatend.?

Qualquer usuário com uma conta de usuário não convidado em um locatário gerenciado do Azure AD pode fazer uma compra de autoatendido. A compra por conta própria não está disponível para locatários que são organizações governamentais ou de educação. Se isso se aplicar à sua organização, nenhuma ação adicional será necessária para controlar a compra de autoatendados.

Os usuários em organizações ou mercados que não estão qualificados para compra de autoatendam veem uma mensagem solicitando que eles contatem o administrador de IT.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Os usuários convidados podem comprar por meio da compra de autoatend.?

Não, os usuários convidados não podem concluir uma compra de autoatend responsabilidade em um locatário no qual são convidados.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Os usuários sincronizados de um Active Directory local podem comprar por meio da compra de autoatendido?

Se um usuário tiver uma conta de usuário ativa em um locatário qualificado do Azure AD, ele poderá concluir uma compra de autoatenduro.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Para quem os compradores de autoatendam podem atribuir licenças?

Os compradores de autoatendados só podem atribuir licenças a usuários no mesmo locatário do Azure AD. O comprador tem acesso a uma exibição limitada do Centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> para atribuir licenças. Os compradores podem atribuir licenças aos produtos que compraram por meio da compra de autoatendados e só podem atribuir essas licenças aos usuários no mesmo locatário do Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Onde o comprador de autoatendir vê e gerencia suas compras?

Os compradores de autoatendir podem gerenciar suas compras na exibição limitada do Centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">do Microsoft 365.</a> Os compradores sempre podem acessar o  centro de administração a partir do painel Administrador no launcher de aplicativos integrado a todos os aplicativos online do Microsoft 365 e do Dynamics. Os compradores podem exibir as compras feitas, comprar assinaturas adicionais para o mesmo serviço e atribuir licenças para essas assinaturas a outros usuários em sua organização. Além disso, os compradores podem exibir e pagar suas contas, atualizar seu método de pagamento e cancelar sua assinatura.

## <a name="pricing"></a>Preços

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Qual é o preço das compras de autoatendificação?

O preço de cada um dos produtos para compra de autoatendados está disponível no site da Microsoft. Os preços também são exibidos como parte da experiência de check-in quando os usuários fazem uma compra de autoatendência. Esses preços podem diferir dos preços que uma organização paga ao fazer compras centrais ou preços oferecidos por meio de um parceiro.

### <a name="who-is-responsible-for-payment"></a>Quem é responsável pelo pagamento?

A pessoa que compra a assinatura por meio da compra autoatendida é a pessoa que é cobrada e responsável pelo pagamento com base nos termos e preços da compra.

## <a name="admin-capabilities"></a>Recursos de administrador

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Quais recursos um administrador tem para compras de autoatendições?

Os administradores podem exibir todas as compras de autoatend nome feitas em sua organização no Centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">do Microsoft 365.</a> Eles podem ver o produto, o nome do comprador, as assinaturas compradas, a data de expiração, o histórico do pedido, o preço de compra e os usuários atribuídos para cada compra de autoatendido. No Centro de Administração da Plataforma Power, os administradores também podem exibir a capacidade de compras de autoatend.. Se necessário para sua organização, os administradores podem desativar a compra de autoatendados por produto por meio do PowerShell. Os administradores têm as mesmas políticas de gerenciamento e acesso de dados sobre produtos comprados por meio da compra de autoatendados ou centralmente.

Os administradores também podem controlar se os usuários em sua organização podem fazer compras de autoatendado. Para obter mais informações, [consulte Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Como a Microsoft respeita a governança e a conformidade de dados habilitando a compra de autoatendados?

Os administradores mantêm o controle sobre quais serviços e produtos estão disponíveis em seu locatário com base em seus requisitos de conformidade e governança de dados. Todas as políticas de gerenciamento e acesso de dados que sua organização adere se aplicam aos serviços disponíveis de autoatend log comprados.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Quem é o proprietário dos dados do produto criados a partir de compras de autoatendam?

Os dados criados a partir de produtos comprados por meio da compra de autoatendados são de propriedade e controlados pela organização.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Como centralizar as compras feitas por meio da compra de autoatendença?

Os administradores podem atribuir licenças existentes ou comprar assinaturas adicionais de produtos de compra de autoatendência por meio de contratos e preços existentes para usuários atribuídos a compras de autoatendência. Depois de atribuir essas licenças compradas centralmente, os administradores podem solicitar que os compradores cancelem suas assinaturas existentes.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Onde o administrador vê compras self-service?

Os administradores globais e de cobrança podem ver assinaturas compradas por meio da compra de autoatendados em **Cobrança** seus produtos no Centro de administração  >   do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Eles podem filtrar a lista de produtos para mostrar apenas as assinaturas compradas por meio de compras centrais ou para incluir assinaturas compradas por meio da compra de autoatendados.

Os administradores podem ver o produto, o nome do comprador, a assinatura comprada, a data de expiração, o histórico do pedido, o preço de compra e os usuários atribuídos.

## <a name="support-and-training"></a>Suporte e treinamento

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Os departamentos de IT ou parceiros dos clientes devem dar suporte a produtos comprados por meio da compra de autoatendados?

Não é esperado que os departamentos e parceiros de IT forneçam suporte para produtos comprados por meio da compra de autoatendados. A Microsoft oferece suporte padrão para compradores de autoatend..

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Se um comprador autônomo chamar suporte, isso usará os incidentes de Suporte Premier do cliente?

Os compradores de autoatendê não usarão os incidentes de Suporte Premier de um cliente para receber suporte para suas compras de autoatendê.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Como os usuários devem receber treinamento sobre os produtos que compram por meio da compra de autoatendados?

Treinamento extensivo para usuários é fornecido nos sites do produto. Os produtos têm aprendizado orientado, documentação, exemplos e comunidades fortes para obter respostas e dicas diretamente de outros usuários.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>O que acontece com uma compra de autoatendado se um usuário sair da organização?

Se a pessoa que comprou originalmente o produto de compra de autoatendência sair da organização, os usuários válidos continuarão a ter uso total do produto durante a assinatura. A assinatura permanece ativa até que o comprador cancele diretamente ou um administrador solicita o cancelamento da assinatura por meio do suporte ao cliente. Os administradores também podem optar por atribuir uma licença comprada centralmente aos usuários da assinatura cancelada.

## <a name="partners"></a>Parceiros

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Qual é a função dos parceiros da Microsoft nas compras de autoatendam?

Os parceiros que têm privilégios de administração delegados podem ver compras de autoatendido no centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a>, assim como um administrador. Os parceiros podem ajudar a dar suporte a uma organização que deseja centralizar produtos comprados por meio de compras de autoatendados. Além disso, os parceiros podem oferecer soluções para estender os recursos de uma compra de autoatendereço.