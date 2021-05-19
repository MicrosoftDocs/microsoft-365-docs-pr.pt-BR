---
title: Compreender os perfis de cobrança
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Saiba como os perfis de cobrança suportam faturas.
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537326"
---
# <a name="understand-billing-profiles"></a>Compreender os perfis de cobrança

Um perfil de cobrança contém um método de pagamento, informações de cobrança e outras configurações de fatura, como o número do pedido de compra e a preferência da fatura de email. Você usa um perfil de cobrança para pagar os produtos que você compra da Microsoft. Um perfil de cobrança é criado automaticamente quando um usuário faz uma compra self-service. Cada perfil de cobrança é faturado separadamente.

> [!NOTE]
>
> Os perfis de cobrança não estão disponíveis para clientes que compram  produtos e serviços da Microsoft.com ou na página Serviços de Compra do centro de administração Microsoft 365.

## <a name="what-are-billing-profile-roles"></a>O que são funções de perfil de cobrança?

Funções nos perfis de cobrança têm permissões para controlar compras e exibir e gerenciar faturas. Atribua essas funções aos usuários que rastreiam, organizam e pagam faturas. Por exemplo, membros da equipe de compras em sua organização.

| Função                         | Descrição                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Proprietário do perfil de cobrança        | Gerenciar tudo para um perfil de cobrança                                          |
| Colaborador de perfil de cobrança  | Gerenciar tudo, exceto permissões em um perfil de cobrança                        |
| Leitor de perfil de cobrança       | Exibição somente leitura de tudo em um perfil de cobrança                                |
| Gerenciador de faturas              | Exibir e pagar contas e tem uma exibição somente leitura de tudo em um perfil de cobrança  |

## <a name="view-my-billing-profiles"></a>Exibir meus perfis de cobrança

> [!NOTE]
>
> Se você seguir estas etapas e a lista de perfis de cobrança estiver vazia, isso significa que você não tem um perfil de cobrança e não pode usar esse recurso.

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faturas e pagamentos</a>.
2. Selecione a **guia Perfil de cobrança** e selecione um perfil de cobrança na lista.

Cada perfil de cobrança inclui as seguintes informações:

- **Nome e status do perfil de cobrança** &ndash; O nome exclusivo do perfil de cobrança e se o perfil de cobrança está ativo ou desabilitado para compra.
- **Configurações de fatura** &ndash; Conversor de Moedas com base no país da conta de cobrança, informações sobre a frequência e a data da fatura, a opção de receber faturas como anexos de email e um campo opcional de número de PO
- **Métodos de pagamento** &ndash; Mostra o método de pagamento principal e de backup, se for o caso, para o perfil
- **Conta de cobrança** &ndash; Nome da conta de cobrança à que o perfil está relacionado. Para obter mais informações sobre contas de cobrança, consulte [Understand billing accounts](../manage-billing-accounts.md).
- **Informações de contato** &ndash; Endereço de cobrança, nome de contato e endereço de email
- **Funções de perfil de cobrança** &ndash; Uma lista de pessoas que são atribuídas a uma das funções de perfil de cobrança para fazer coisas para esse perfil. Por exemplo, pagar contas, adicionar um número de PO ou substituir o método de pagamento usado para fazer compras.

> [!NOTE]
>
> Você só pode atribuir funções de perfil de cobrança aos usuários em sua organização.

## <a name="need-help-contact-support"></a>Precisa de ajuda? Contatar o suporte

Se você tiver dúvidas ou precisar de ajuda com suas cobranças do Azure, crie uma solicitação de suporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">com o suporte do Azure.</a>

Se você tiver dúvidas ou precisar de ajuda com seu perfil de cobrança no Microsoft 365 de administração, [contate o suporte](../../business-video/get-help-support.md).

## <a name="related-content"></a>Conteúdo relacionado

[Como pagar sua assinatura com um perfil de cobrança](pay-for-subscription-billing-profile.md) (artigo)\
[Compreender contas de cobrança](../manage-billing-accounts.md) (artigo)\
[Gerenciar métodos de pagamento](manage-payment-methods.md) (artigo)
