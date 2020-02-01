---
title: Perguntas frequentes de compras de autoatendimento
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
description: Encontre respostas para perguntas frequentes sobre compras de autoatendimento.
ms.custom: aka.ms/self-service-purchase-faq
ms.openlocfilehash: 9f456c992cda6fcfafd1a0d5faa68dba42a894d8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594095"
---
# <a name="self-service-purchase-faq"></a>Perguntas frequentes de compras de autoatendimento

> [!NOTE]
> As informações neste artigo aplicam-se apenas às assinaturas da plataforma de alimentação da Microsoft (Power BI, aplicativos de energia e automatização de energia).

As compras de autoatendimento estão agora disponíveis para a plataforma de energia nos Estados Unidos.

## <a name="general"></a>Geral

### <a name="what-changes-did-microsoft-announce-around-self-service-purchases-for-the-power-platform-products"></a>Quais alterações a Microsoft anunciou em compras de autoatendimento para os produtos da plataforma de energia?

Em 19 de novembro de, fornecemos aos administradores de ti uma maneira de desativar a compras de autoatendimento por produto através do PowerShell. Para saber como usá-la, confira [usar o AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

Para dar mais tempo para se preparar para essa mudança, estamos atualizando o lançamento para recursos de compra de autoatendimento para os produtos de plataforma de alimentação para iniciar com o Power BI em 14 de Janeiro para todos os clientes de nuvem comercial.  

Desde 14 de janeiro de 2020, a aquisição de autoatendimento, assinatura e recursos de gerenciamento de licença para produtos de plataforma de alimentação (Power BI, aplicativos de energia e automatização de energia) estarão disponíveis para clientes em nuvem comercial nos Estados Unidos. A compra de autoatendimento oferece aos usuários a oportunidade de experimentar novas tecnologias e permitir que elas desenvolvam soluções que irão beneficiar suas organizações maiores. Esse recurso não estará disponível para locatários nos EUA que sejam governamentais, sem fins lucrativos ou educacionais, neste momento. As equipes de compras centrais e de ti terão visibilidade para todos os usuários que compram e implantam soluções de compras de autoatendimento por meio do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>e poderão desativar a compras de autoatendimento por produto por meio do PowerShell.

### <a name="why-is-microsoft-adding-a-self-service-purchase-option-for-the-power-platform-products"></a>Por que a Microsoft está adicionando uma opção de compra de autoatendimento para os produtos da plataforma de alimentação?

No mundo de hoje, os usuários finais e departamentos estão cada vez mais procurando e comprando soluções de tecnologia por conta própria. Recebemos várias solicitações desses clientes para habilitar a compra de autoatendimento de produtos de plataforma de energia. Estamos respondendo a essa necessidade do cliente, além de equilibrar as necessidades dos administradores de ti, que geralmente perdem a visibilidade e o controle quando as pessoas de sua organização adotam soluções de terceiros sem o seu conhecimento. Com o futuro recurso de autoatendimento para os produtos de plataforma de alimentação, os administradores de ti terão visibilidade completa de todas as compras de autoatendimento em sua organização, e as políticas de governança de dados definidas no nível organizacional serão acumuladas para assinaturas adquiridas por meio de autoatendimento. Os administradores também podem atribuir licenças existentes ou comprar assinaturas adicionais, de produtos de plataforma de energia através de contratos e preços existentes para usuários atribuídos a compras de autoatendimento. Depois de atribuir essas licenças de compra central, os administradores podem solicitar que os compradores cancelem suas assinaturas existentes. A Microsoft está explorando maneiras de simplificar e simplificar esse processo para administradores no futuro.

### <a name="which-power-platform-products-are-available-for-self-service-purchase"></a>Quais produtos de plataforma de alimentação estão disponíveis para compra de autoatendimento?

A Microsoft lançou a compra de autoatendimento para a plataforma de alimentação (Power BI, aplicativos de energia e automatização de energia) para os clientes nos Estados Unidos, com mercados adicionais se tornarem disponíveis nos próximos meses. Esse recurso não estará disponível para locatários nos EUA que sejam governamentais, sem fins lucrativos ou educacionais, neste momento.

### <a name="will-self-service-purchase-be-enabled-for-services-beyond-the-power-platform-products"></a>A compra de autoatendimento será habilitada para serviços além dos produtos de plataforma de energia?

No momento, apenas os produtos da família de plataformas de alimentação estão sendo oferecidos por meio de compras de autoatendimento.

## <a name="making-a-self-service-purchase"></a>Fazendo uma compra de autoatendimento

### <a name="how-does-a-customer-make-a-self-service-purchase"></a>Como um cliente faz uma compra de autoatendimento?

Os clientes poderão fazer compras de autoatendimento online no Microsoft Power BI, aplicativos de energia e sites de energia automatizados. Primeiro, os clientes serão solicitados a inserir um endereço de email para garantir que eles sejam um usuário em um locatário existente do Azure Active Directory (AD). Em seguida, eles serão direcionados para fazer logon usando suas credenciais do Azure AD. Depois de entrar, o cliente receberá uma solicitação para selecionar quantas assinaturas eles desejam comprar e fornecer o pagamento do cartão de crédito. Quando a compra estiver concluída, será possível começar a usar sua assinatura. O comprador também poderá acessar um modo de exibição limitado do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a> , onde poderá permitir que outras pessoas em sua organização usem o produto.

### <a name="what-are-the-payment-options-for-self-service-purchases"></a>Quais são as opções de pagamento para compras de autoatendimento?

No momento, o cartão de crédito é a única forma de pagamento disponível. Não há suporte para o pagamento através de faturamento.

### <a name="who-can-buy-through-self-service-purchase"></a>Quem pode comprar por meio de compras de autoatendimento?

Qualquer usuário com uma conta de usuário não convidado em um locatário do Azure AD gerenciado pode comprar. Esse recurso não estará disponível para locatários que sejam governamentais, sem fins lucrativos ou de educação, neste momento. Se isso se aplica à sua organização, nenhuma ação adicional é necessária para controlar a compra de autoatendimento, neste momento.

Os usuários em organizações ou mercados que não estão qualificados para compras de autoatendimento verão uma mensagem solicitando que entrem em contato com seu administrador de ti como fazem hoje.

### <a name="can-guest-users-buy-through-self-service-purchase"></a>Os usuários convidados podem comprar por meio de compras de autoatendimento?

Não, os usuários convidados não podem concluir uma compra de autoatendimento em um locatário em que eles são convidados.

### <a name="can-users-synced-from-an-on-premises-active-directory-buy-through-self-service-purchase"></a>Os usuários podem sincronizar a partir de um Active Directory local comprar por meio de compras de autoatendimento?

Se um usuário tiver uma conta de usuário ativa em um locatário do Azure AD qualificado, ele poderá concluir uma compra de autoatendimento.

### <a name="who-can-self-service-purchasers-assign-licenses-to"></a>Quem pode atribuir licenças a autoatendimento?

Os compradores de autoatendimento só poderão atribuir licenças aos usuários no mesmo locatário do Azure AD. O comprador poderá acessar um modo de exibição limitado do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a> para atribuir licenças. Eles só terão visibilidade e poderão atribuir licenças para os produtos que eles compraram por meio de compras de autoatendimento e poderão apenas atribuir essas licenças aos usuários no mesmo locatário do Azure AD.

### <a name="where-does-the-self-service-purchaser-see-and-manage-their-purchases"></a>Onde o comprador de autoatendimento vê e gerencia suas compras?

Os compradores de autoatendimento podem gerenciar suas compras no modo de exibição limitado do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Os compradores sempre podem acessar o centro de administração do bloco de **Administração** no inicializador de aplicativos do Office 365, em todos os aplicativos do Office 365 e Dynamics online. Eles podem exibir as compras feitas, comprar assinaturas adicionais para o mesmo serviço e atribuir licenças para essas assinaturas a outros usuários em sua organização. Além disso, os compradores podem exibir e pagar suas faturas, atualizar a forma de pagamento e cancelar sua assinatura.

**Veja o centro de administração do Microsoft 365 limitado para compradores de autoatendimento:**

![Captura de tela do centro de administração do Microsoft 365.](../media/MACBillingProductsServicesSelfServicePurchaseIW.png)

## <a name="pricing"></a>Preços

### <a name="what-is-the-pricing-for-self-service-purchases"></a>Qual é o preço das compras de autoatendimento?

O preço de cada um dos produtos de plataforma de energia para compras de autoatendimento estará disponível no site da Microsoft e também será exibido como parte da experiência de check-out ao fazer uma compra de autoatendimento. Esses preços podem diferir dos preços que uma organização paga ao fazer compras centrais ou preços oferecidos por meio de um parceiro.

### <a name="who-is-responsible-for-payment"></a>Quem é responsável pelo pagamento?

A pessoa que comprar a assinatura por meio de compras de autoatendimento será cobrada e responsável pelo pagamento com base nos termos e preços da compra.

## <a name="admin-capabilities"></a>Recursos de administração

### <a name="what-capabilities-does-an-admin-have-for-self-service-purchases"></a>Quais recursos um administrador tem para compras de autoatendimento?

Os administradores podem exibir todas as compras de autoatendimento feitas em sua organização no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>. Eles podem ver o produto, o nome do comprador, as assinaturas adquiridas, a data de vencimento, o histórico de pedidos, o preço de compra e os usuários atribuídos para cada compra de autoatendimento. Se for necessário para sua organização, os administradores poderão desativar a compra de autoatendimento por produto através do PowerShell. Os administradores têm as mesmas políticas de gerenciamento de dados e acesso sobre os produtos comprados por meio de compras de autoatendimento ou de forma centralizada.

Os administradores também podem controlar se os usuários de sua organização podem fazer compras de autoatendimento. Para obter mais informações, consulte [usar AllowSelfServicePurchase para o módulo do MSCommerce PowerShell](allowselfservicepurchase-powershell.md).

### <a name="how-is-microsoft-respecting-data-governance-and-compliance-by-enabling-self-service-purchase"></a>Como a Microsoft está respeitando a conformidade e o controle de dados habilitando a compra de autoatendimento?

Os administradores mantêm o controle sobre quais serviços e produtos estão habilitados em seus locatários com base em seus requisitos de conformidade e controle de dados. Além disso, todas as políticas de gerenciamento e acesso de dados, que sua organização tenha habilitado, serão aplicadas a serviços habilitados para autoatendimento.

### <a name="who-owns-the-product-data-created-from-self-service-purchases"></a>Quem possui os dados de produto criados a partir de compras de autoatendimento?

Os dados criados a partir de produtos comprados por autoatendimento são proprietários e controlados pela organização.

### <a name="how-do-i-centralize-the-purchases-made-through-self-service-purchase"></a>Como centralizar as compras feitas por meio de compras de autoatendimento?

Os administradores podem atribuir licenças existentes ou comprar assinaturas adicionais de produtos de plataforma de alimentação (Power BI, aplicativos de energia e automatização de energia) por meio de acordos e preços existentes para usuários atribuídos a compras de autoatendimento. Depois de atribuir essas licenças de compra central, os administradores podem solicitar que os compradores cancelem suas assinaturas existentes. A Microsoft está explorando maneiras de simplificar e simplificar esse processo para administradores no futuro.

### <a name="where-does-the-admin-see-self-service-purchases"></a>Onde o administrador vê compras de autoatendimento?

Os administradores globais e de cobrança podem ver assinaturas compradas por meio de compras de autoatendimento em produtos de **cobrança** > **& serviços** no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a> junto com todas as outras assinaturas adquiridas por meio da aquisição central. Eles podem filtrar a lista apenas com as assinaturas adquiridas por meio da aquisição central ou incluir assinaturas compradas por meio de compras de autoatendimento.

Os administradores podem ver o produto, o nome do comprador, a assinatura adquirida, a data de vencimento, o histórico de pedidos, o preço de compra e os usuários atribuídos.

## <a name="support-and-training"></a>Suporte e treinamento

### <a name="are-customers-it-departments-or-partners-expected-to-support-products-bought-through-self-service-purchase"></a>Os departamentos de ti ou parceiros são esperados para o suporte de produtos comprados por autoatendimento?

Não é esperado que os departamentos de ti e os parceiros forneçam suporte para produtos comprados por autoatendimento. A Microsoft fornecerá suporte padrão para compradores de autoatendimento.

### <a name="if-a-self-service-purchaser-calls-support-will-they-use-the-customers-premier-support-incidents"></a>Se um comprador de autoatendimento ligar para o suporte, eles usarão os incidentes de suporte Premier do cliente?

Os compradores de autoatendimento não usarão os incidentes de suporte Premier do cliente para receber suporte para suas compras de autoatendimento.

### <a name="how-are-users-expected-to-receive-training-on-the-products-they-buy-through-self-service-purchase"></a>Como os usuários devem receber treinamento nos produtos que comprarem por meio de compras de autoatendimento?

O treinamento abrangente para os usuários é fornecido no Microsoft Power BI, aplicativos de energia e sites de automatização de energia. Os produtos têm aprendizado, documentação, exemplos e comunidades fortes orientadas para obter respostas e dicas diretamente de outros usuários.

### <a name="what-happens-to-a-self-service-purchase-if-a-user-leaves-the-organization"></a>O que acontece com uma compra de autoatendimento se um usuário sair da organização?

Os usuários válidos continuarão a ter o uso completo da compra de autoatendimento durante a vigência da assinatura. A assinatura permanece ativa até que o comprador a cancele diretamente ou um administrador solicita que a assinatura seja cancelada por meio do suporte ao cliente. Os administradores também podem optar por atribuir uma licença de compra centralizada aos usuários da assinatura cancelada.

## <a name="partners"></a>Parceiros

### <a name="whats-the-role-of-microsofts-partners-in-self-service-purchases"></a>Qual é a função dos parceiros da Microsoft em compras de autoatendimento?

Parceiros com privilégios de administração delegada podem ver compras de autoatendimento no <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do Microsoft 365</a>, assim como um administrador. Os parceiros podem ajudar a oferecer suporte a uma organização que deseja centralizar produtos comprados por compras de autoatendimento. Além disso, os parceiros podem oferecer soluções para estender os recursos de uma compra de autoatendimento.