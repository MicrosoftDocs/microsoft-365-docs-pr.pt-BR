---
title: Perguntas frequentes de compras de autoatendimento
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
description: Encontre respostas para perguntas frequentes sobre compras de autoatendimento.
ms.date: 08/12/2020
ms.openlocfilehash: 78a7082a966a866f18ac2aa378198dbb33d8c158
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653696"
---
# <a name="self-service-purchase-faq"></a>Perguntas frequentes de compras de autoatendimento

A compra de autoatendimento oferece aos usuários a oportunidade de experimentar novas tecnologias e desenvolver soluções que eventualmente beneficiam suas organizações maiores. As equipes de compras centrais e de ti têm visibilidade para todos os usuários que compram e implantam soluções de compras de autoatendimento por meio do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Os administradores podem desativar compras de autoatendimento por produto através do PowerShell. Para saber mais, confira [usar o AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

A compra de autoatendimento está disponível para a plataforma de alimentação (Power BI, aplicativos de energia e automatização de energia), Project e Visio.

> [!NOTE]
> A compra de autoatendimento não está disponível na Índia e não está disponível para clientes governamentais ou de educação.

## <a name="making-a-self-service-purchase"></a>Fazendo uma compra de autoatendimento

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Como um cliente faz uma compra de autoatendimento?

Os clientes podem fazer compras de autoatendimento online nos sites de produtos ou nos prompts de compra no aplicativo. Primeiro, os clientes são solicitados a inserir um endereço de email para garantir que eles sejam um usuário em um locatário existente do Azure Active Directory (AD). Em seguida, eles são direcionados para entrar usando suas credenciais do Azure AD. Após entrar, o cliente é solicitado a selecionar quantas assinaturas desejadas comprar e para fornecer o pagamento de cartão de crédito. Quando a compra é concluída, elas podem começar a usar sua assinatura. O comprador tem acesso a um modo de exibição limitado do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a> , onde eles podem atribuir licenças ao produto para outras pessoas na organização.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Quais são as opções de pagamento para compras de autoatendimento?

No momento, o cartão de crédito é a única forma de pagamento disponível. Não há suporte para pagamento pelo faturamento.

### <a name="who-can-buy-through-self-service-purchase"></a>Quem pode comprar por meio de compras de autoatendimento?

Qualquer usuário com uma conta de usuário não convidado em um locatário do Azure AD gerenciado pode fazer uma compra de autoatendimento. A compra de autoatendimento não está disponível para locatários que são organizações governamentais ou de educação. Se isso se aplica à sua organização, nenhuma ação adicional é necessária para controlar a compra de autoatendimento.

Os usuários em organizações ou mercados que não estão qualificados para compra de autoatendimento confiram uma mensagem solicitando que entrem em contato com o administrador de ti.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Os usuários convidados podem comprar por meio de compras de autoatendimento?

Não, os usuários convidados não podem concluir uma compra de autoatendimento em um locatário em que eles sejam convidados.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Os usuários podem sincronizar a partir de um Active Directory local comprar por meio de compras de autoatendimento?

Se um usuário tiver uma conta de usuário ativa em um locatário do Azure AD qualificado, ele poderá concluir uma compra de autoatendimento.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Quem pode atribuir licenças a autoatendimento?

Os compradores de autoatendimento só podem atribuir licenças aos usuários no mesmo locatário do Azure AD. O comprador tem acesso a um modo de exibição limitado do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a> para atribuir licenças. Os compradores podem atribuir licenças para os produtos que compraram por meio de compras de autoatendimento e podem apenas atribuir essas licenças aos usuários no mesmo locatário do Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Onde o comprador de autoatendimento vê e gerencia suas compras?

Os compradores de autoatendimento podem gerenciar suas compras no modo de exibição limitado do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Os compradores podem sempre acessar o centro de administração do bloco de **Administração** no inicializador de aplicativos incorporado a todos os aplicativos do Microsoft 365 e do Dynamics online. Os compradores podem exibir as compras feitas, comprar assinaturas adicionais para o mesmo serviço e atribuir licenças para essas assinaturas a outros usuários em sua organização. Além disso, os compradores podem exibir e pagar suas faturas, atualizar a forma de pagamento e cancelar sua assinatura.

## <a name="pricing"></a>Preços

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Qual é o preço das compras de autoatendimento?

O preço de cada produto para compra de autoatendimento está disponível no site da Microsoft. Os preços também são exibidos como parte da experiência de verificação quando os usuários fazem uma compra de autoatendimento. Esses preços podem diferir dos preços que uma organização paga ao fazer compras centrais ou preços oferecidos por meio de um parceiro.

### <a name="who-is-responsible-for-payment"></a>Quem é responsável pelo pagamento?

A pessoa que compra a assinatura por meio de compras de autoatendimento é a pessoa cobrada e responsável pelo pagamento com base nos termos e preços da compra.

## <a name="admin-capabilities"></a>Recursos de administração

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Quais recursos um administrador tem para compras de autoatendimento?

Os administradores podem exibir todas as compras de autoatendimento feitas em sua organização no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Eles podem ver o produto, o nome do comprador, as assinaturas adquiridas, a data de vencimento, o histórico de pedidos, o preço de compra e os usuários atribuídos para cada compra de autoatendimento. No centro de administração da plataforma de energia, os administradores também podem exibir a capacidade de compras de autoatendimento. Se necessário para sua organização, os administradores podem desativar a compra de autoatendimento por produto através do PowerShell. Os administradores têm as mesmas políticas de gerenciamento de dados e acesso sobre os produtos comprados por meio de compras de autoatendimento ou de forma centralizada.

Os administradores também podem controlar se os usuários de sua organização podem fazer compras de autoatendimento. Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Como a Microsoft está respeitando a conformidade e o controle de dados habilitando a compra de autoatendimento?

Os administradores mantêm o controle sobre quais serviços e produtos estão disponíveis em seu locatário com base em seus requisitos de controle e conformidade de dados. Todas as políticas de acesso e gerenciamento de dados que sua organização ativou aplicam aos serviços de compra automática disponíveis.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Quem possui os dados de produto criados a partir de compras de autoatendimento?

Os dados criados a partir de produtos comprados por autoatendimento são proprietários e controlados pela organização.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Como centralizar as compras feitas por meio de compras de autoatendimento?

Os administradores podem atribuir licenças existentes ou comprar assinaturas adicionais de produtos de compras de autoatendimento por meio de contratos existentes e preços para usuários atribuídos a compras de autoatendimento. Depois de atribuir essas licenças de compra central, os administradores podem solicitar que os compradores cancelem suas assinaturas existentes.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Onde o administrador vê compras de autoatendimento?

Os administradores globais e de cobrança podem ver assinaturas compradas por meio de compras de autoatendimento na **cobrança**  >  **de seus produtos** no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Eles podem filtrar a lista de produtos para mostrar apenas as assinaturas adquiridas por meio da aquisição central ou incluir assinaturas adquiridas por meio de compras de autoatendimento.

Os administradores podem ver o produto, o nome do comprador, a assinatura adquirida, a data de vencimento, o histórico de pedidos, o preço de compra e os usuários atribuídos.

## <a name="support-and-training"></a>Suporte e treinamento

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Os departamentos de ti ou parceiros são esperados para o suporte de produtos comprados por autoatendimento?

Não é esperado que os departamentos de ti e os parceiros forneçam suporte para produtos comprados por autoatendimento. A Microsoft oferece suporte padrão para compradores de autoatendimento.

### <a name="if-a-self-service-purchaser-calls-support-does-that-use-the-customers-premier-support-incidents"></a>Se um comprador de autoatendimento chamar suporte, isso usará os incidentes de suporte Premier do cliente?

Os compradores de autoatendimento não usarão os incidentes de suporte Premier do cliente para receber suporte para suas compras de autoatendimento.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Como os usuários devem receber treinamento nos produtos que comprarem por meio de compras de autoatendimento?

O treinamento abrangente para os usuários é fornecido nos sites dos produtos. Os produtos têm aprendizado, documentação, exemplos e comunidades fortes orientadas para obter respostas e dicas diretamente de outros usuários.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>O que acontece com uma compra de autoatendimento se um usuário sair da organização?

Se a pessoa que comprou originalmente o produto de compra de autoatendimento deixa a organização, os usuários válidos continuam a ter o uso completo do produto pela duração da assinatura. A assinatura permanece ativa até que o comprador a cancele diretamente ou um cancelamento de solicitações de administração da assinatura por meio do suporte ao cliente. Os administradores também podem optar por atribuir uma licença de compra centralizada aos usuários da assinatura cancelada.

## <a name="partners"></a>Parceiros

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Qual é a função dos parceiros da Microsoft em compras de autoatendimento?

Parceiros com privilégios de administração delegada podem ver compras de autoatendimento no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>, assim como um administrador. Os parceiros podem ajudar a oferecer suporte a uma organização que deseja centralizar produtos comprados por compras de autoatendimento. Além disso, os parceiros podem oferecer soluções para estender os recursos de uma compra de autoatendimento.