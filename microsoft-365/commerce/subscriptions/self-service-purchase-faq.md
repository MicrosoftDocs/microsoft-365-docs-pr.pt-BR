---
title: Perguntas frequentes sobre compra self-service
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
ms.custom:
- AdminSurgePortfolio
- aka.ms/self-service-purchase-faq
search.appverid:
- MET150
description: Encontre respostas para perguntas frequentes sobre compras self-service.
ms.date: 09/15/2020
ms.openlocfilehash: 81143dfe3794bc4f42bea879905bf08750f498b4
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816920"
---
# <a name="self-service-purchase-faq"></a>Perguntas frequentes sobre compra self-service

A compra self-service oferece aos usuários a oportunidade de experimentar novas tecnologias e desenvolver soluções que, em última análise, beneficiem suas organizações maiores. As compras centrais e as equipes de TI têm visibilidade para todos os usuários que compram e implantam soluções de compra de autoatendgosto por meio do centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">do Microsoft 365.</a> Os administradores podem desativar a compra por produto por produto por meio do PowerShell. Para saber mais, consulte [Usar AllowSelfServicePurchase para o módulo MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

A compra self-service está disponível para o Power Platform (Power BI, Power Apps e Power Automate), Project e Visio.

> [!NOTE]
> A compra self-service não está disponível na Índia, para clientes governamentais ou de educação. O Project e o Visio não estão disponíveis para compra self-service no Brasil e na República Democrática do Congo.

## <a name="making-a-self-service-purchase"></a>Fazendo uma compra self-service

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Como um cliente faz uma compra self-service?

Os clientes podem fazer uma compra self-service online nos sites do produto ou nos prompts de compra no aplicativo. Primeiro, os clientes são solicitados a inserir um endereço de email para garantir que eles sejam um usuário em um locatário existente do Azure Active Directory (AD). Em seguida, eles são direcionados para entrar usando suas credenciais do Azure AD. Depois de entrar, o cliente é solicitado a selecionar quantas assinaturas deseja comprar e fornecer o pagamento com cartão de crédito. Quando a compra for concluída, eles poderão começar a usar a assinatura. O comprador tem acesso a uma exibição limitada do centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365,</a> onde ele pode atribuir licenças ao produto a outras pessoas em sua organização.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Quais são as opções de pagamento para compras self-service?

Atualmente, o cartão de crédito é a única forma de pagamento disponível. Não há suporte para pagamento por meio de faturamento.

### <a name="who-can-buy-through-self-service-purchase"></a>Quem pode comprar por meio de compra self-service?

Qualquer usuário com uma conta de usuário não convidado em um locatário gerenciado do Azure AD pode fazer uma compra de autoatendido. A compra self-service não está disponível para locatários que são organizações governamentais ou de educação. Se isso se aplicar à sua organização, nenhuma ação adicional será necessária para controlar a compra self-service.

Os usuários em organizações ou mercados que não estão qualificados para compra self-service veem uma mensagem solicitando que eles contatem o administrador de IT.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Os usuários convidados podem comprar por meio de compra self-service?

Não, os usuários convidados não podem concluir uma compra de autoatend bem-estar em um locatário no qual eles são convidados.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Os usuários sincronizados de um Active Directory local podem comprar por meio de compra de autoatendido?

Se um usuário tiver uma conta de usuário ativa em um locatário qualificado do Azure AD, ele poderá concluir uma compra de autoatendado.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>A quem os compradores autônomos podem atribuir licenças?

Os compradores de autoatendados só podem atribuir licenças a usuários no mesmo locatário do Azure AD. O comprador tem acesso a uma exibição limitada do Centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365</a> para atribuir licenças. Os compradores podem atribuir licenças aos produtos que compraram por meio de compra self-service e só podem atribuir essas licenças a usuários no mesmo locatário do Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Onde o comprador de autoatend exatamente vê e gerencia suas compras?

Os compradores de autoatendir podem gerenciar suas compras na exibição limitada do centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administração do Microsoft 365.</a> Os compradores sempre podem acessar o  centro de administração a partir do painel Administrador no iniciador de aplicativos integrado a todos os aplicativos online do Microsoft 365 e do Dynamics. Os compradores podem exibir as compras que realizaram, comprar assinaturas adicionais para o mesmo serviço e atribuir licenças para essas assinaturas a outros usuários em sua organização. Além disso, os compradores podem exibir e pagar a fatura, atualizar a forma de pagamento e cancelar a assinatura.

## <a name="pricing"></a>Preços

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Qual é o preço para compras self-service?

O preço de cada um dos produtos para compra self-service está disponível no site da Microsoft. Os preços também são exibidos como parte da experiência de check-out quando os usuários fazem uma compra de autoatendido. Esses preços podem ser diferentes dos preços que uma organização paga ao fazer compras centrais ou preços oferecidos por meio de um parceiro.

### <a name="who-is-responsible-for-payment"></a>Quem é responsável pelo pagamento?

A pessoa que compra a assinatura por meio da compra de autoatendido é a pessoa cobrada e responsável pelo pagamento com base nos termos e preço da compra.

## <a name="admin-capabilities"></a>Recursos de administração

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Quais recursos um administrador tem para compras self-service?

Os administradores podem exibir todas as compras self-service feitas em sua organização no centro <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">de administração do Microsoft 365.</a> Eles podem ver o produto, o nome do comprador, as assinaturas adquiridas, a data de vencimento, o histórico de pedido, o preço da compra e os usuários atribuídos para cada compra de autoatendido. No Centro de Administração da Plataforma Power, os administradores também podem exibir a capacidade de compras self-service. Se necessário para sua organização, os administradores podem desativar a compra por produto por produto por meio do PowerShell. Os administradores têm as mesmas políticas de acesso e gerenciamento de dados sobre produtos comprados por meio de compra de autoatendínio ou centralmente.

Os administradores também podem controlar se os usuários em sua organização podem fazer compras de autoatendado. Para obter mais informações, [consulte Usar AllowSelfServicePurchase para o módulo MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Como a Microsoft está respeitando a conformidade e a governança de dados habilitando a compra de autoatendência?

Os administradores mantêm controle sobre quais serviços e produtos estão disponíveis em seu locatário com base em seus requisitos de conformidade e governança de dados. Todas as políticas de gerenciamento e acesso de dados que sua organização ativas aplicam-se aos serviços comprados por autoatendidas disponíveis.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Quem é o proprietário dos dados de produto criados a partir de compras self-service?

Os dados criados a partir de produtos comprados por meio de compra de autoatendida são de propriedade e controlados pela organização.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Como centralizo as compras feitas por meio da compra self-service?

Os administradores podem atribuir licenças existentes ou comprar assinaturas adicionais de produtos de compra de autoatendido por meio de contratos e preços existentes para usuários atribuídos a compras de autoatendido. Depois de atribuir essas licenças adquiridas centralmente, os administradores podem solicitar que os compradores cancelem suas assinaturas existentes.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Onde o administrador vê as compras self-service?

Os administradores globais e de cobrança podem ver assinaturas compradas por meio de compra self-service na cobrança seus produtos no centro de administração  >   do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365.</a> Eles podem filtrar a lista de produtos para mostrar apenas as assinaturas adquiridas por meio de compras centrais ou para incluir assinaturas compradas por meio de compra de autoatendínio.

Os administradores podem ver o produto, o nome do comprador, a assinatura adquirida, a data de vencimento, o histórico de pedido, o preço da compra e os usuários atribuídos.

## <a name="support-and-training"></a>Suporte e treinamento

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Espera-se que os departamentos de IT ou parceiros dos clientes deem suporte a produtos comprados por meio de compra self-service?

Não se espera que os departamentos e parceiros de IT forneçam suporte para produtos comprados por meio de compra de autoatendínio. A Microsoft fornece suporte padrão para os compradores de autoatend nível.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Se um comprador autônomo ligar para o suporte, isso usará os incidentes de Suporte Premier do cliente?

Os compradores de autoatend pois não usarão os incidentes de Suporte Premier do cliente para receber suporte para suas compras de autoatendê.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Como espera-se que os usuários recebam treinamento sobre os produtos que compram por meio de compra self-service?

O treinamento extensivo para usuários é fornecido nos sites do produto. Os produtos orientaram o aprendizado, documentação, exemplos e comunidades fortes para obter respostas e dicas diretamente de outros usuários.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>O que acontece com uma compra self-service se um usuário deixar a organização?

Se a pessoa que originalmente comprou o produto de autoatendência deixar a organização, os usuários válidos continuarão a ter o uso completo do produto pela duração da assinatura. A assinatura permanece ativa até que o comprador a cancele diretamente ou um administrador solicita o cancelamento da assinatura por meio do suporte ao cliente. Os administradores também podem optar por atribuir uma licença comprada centralmente aos usuários da assinatura cancelada.

## <a name="partners"></a>Parceiros

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Qual é o papel dos parceiros da Microsoft em compras de autoatend exatamente?

Os parceiros que têm privilégios de administração delegados podem ver compras de autoatendido no centro de administração do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365,</a>assim como um administrador. Os parceiros podem ajudar a dar suporte a uma organização que deseja centralizar produtos comprados por meio de compras self-service. Além disso, os parceiros podem oferecer soluções para estender os recursos de uma compra self-service.