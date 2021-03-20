---
title: Entenda sua cobrança ou fatura
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como ler e entender sua fatura ou cobrança de produtos comerciais da Microsoft.
keywords: contas de cobrança, informações sobre a organização, fatura
ms.openlocfilehash: 2b11cca810b17ae2dacc3ddab723725608ffceb5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911693"
---
# <a name="understand-your-bill-or-invoice"></a>Entenda sua cobrança ou fatura

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

A fatura fornece um resumo dos seus encargos e instruções de pagamento. Você pode [visualizar sua fatura online](#view-your-online-invoice) no Centro de administração do Microsoft 365. Você também pode baixá-lo no formato de Documento Portátil (.pdf) para enviar por email.

Se você tiver apenas uma assinatura do Microsoft 365, consulte [Entenda sua cobrança ou fatura do Microsoft 365 para empresas](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Entenda o cabeçalho da fatura

O topo da primeira página identifica quem é responsável pelo pagamento, para onde a cobrança é enviada e um resumo dos encargos.

| Termo | Descrição |
| --- | --- |
| Vendido para |A conta de cobrança que identifica o nome e o endereço da pessoa jurídica responsável pelo pagamento. Essas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">Conta de cobrança</a>, onde você pode encontrar o contrato da conta e gerenciar funções e permissões. |
| Cobrar em |Identifica quem recebe a fatura. Estas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfis de cobrança</a>. O perfil de cobrança também é mostrado na página online da fatura, na seção **Resumo da fatura**. Para saber mais sobre perfis de cobrança e como usá-los para criar opções de cobrança mais flexíveis para sua organização, consulte [Gerenciar perfis de cobrança](manage-billing-profiles.md). |
| Perfil de cobrança |O nome do perfil de cobrança usado para definir as propriedades da fatura como **Cobrar em**, **Número do PO** e condições de pagamento. Estas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfis de cobrança</a>. Para obter mais informações sobre perfis de cobrança e como você pode usá-los para criar opções de cobrança mais flexíveis para sua organização, consulte [Gerenciar perfis de cobrança](manage-billing-profiles.md). |
| Número da fatura |Um número de cobrança único, gerado pela Microsoft, utilizado para fins de rastreamento. |
| Data da fatura |Data em que a fatura foi gerada, normalmente cinco a 12 dias após o final do ciclo de cobrança. Você pode verificar a data da fatura na página de detalhes do perfil de cobrança. Os encargos que ocorrem entre o final do período de cobrança e a data da fatura são incluídos na fatura do próximo mês, uma vez que estão no próximo período de cobrança. As datas de início e término do período de cobrança para cada fatura estão listadas no PDF da fatura acima de **Resumo da Cobrança**.|
| Condições de pagamento |Como você paga sua cobrança da Microsoft. *30 dias corridos* Significa que você paga seguindo as instruções em sua fatura, dentro de 30 dias a partir da data da fatura. |

## <a name="understand-the-billing-summary"></a>Entenda o resumo de cobrança

O **Resumo da cobrança** mostra o resumo dos encargos desde o período de cobrança anterior, todos os créditos aplicados, impostos e o valor total devido.

| Termo | Descrição |
| --- | --- |
| Encargos|Número total de produtos adquiridos para este período de cobrança e seus encargos e impostos relacionados. As compras são agregadas para fornecer uma visão concisa de sua cobrança. |
| Créditos |Créditos que você recebeu de devoluções |
| Créditos Azure aplicados |Seus créditos Azure são aplicados automaticamente aos encargos do Azure a cada período de cobrança. Se você não tiver nenhum crédito do Azure, este campo ficará oculto. Para obter mais informações sobre os créditos do Azure, consulte [Acompanhamento do saldo de crédito Azure no Contrato de Cliente da Microsoft](/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotal |O valor devido antes dos impostos |
| Imposto |O tipo e o valor do imposto que você paga, dependendo do país/região de seu perfil de cobrança. Se você não tiver que pagar impostos, nenhum imposto será mostrado na sua fatura. |

### <a name="understand-your-charges"></a>Entenda seus encargos

As páginas de encargos mostram o custo discriminado por produto. Para os clientes do Azure, os encargos podem ser organizadas por seção da fatura. Para obter mais informações sobre como as seções da fatura são usadas com produtos Azure, consulte [Seções da fatura](/azure/billing/billing-mca-overview#invoice-sections) em [Comece com sua conta de cobrança do Contrato de Cliente da Microsoft](/azure/billing/billing-mca-overview). Em cada pedido de produto, o custo é dividido por família de serviço.

| Termo |Descrição |
| --- | --- |
| Preço unitário | O preço unitário efetivo do serviço (em moeda de preço) que é usado para calcular a cobrança. Este preço é exclusivo para um produto, família de serviços, medidor e oferta. |
| Qtd. | Quantidade comprada ou consumida durante o período de cobrança |
| Encargos/Créditos | Valor líquido dos encargos após a aplicação dos créditos/reembolsos |
| Crédito Azure | A quantidade de crédito Azure aplicada às Encargos/Créditos |
| Taxa de imposto | Taxa de imposto, dependendo do país/região |
| Valor do imposto | Valor do imposto aplicado à compra com base na taxa de imposto |
| Total | O valor total devido pela compra |

Os detalhes dos itens de linha variam de acordo com o tipo de produto pelo qual você é cobrado. Por exemplo, para produtos Azure, é mostrada a quantidade de créditos Azure aplicados. Os produtos baseados em licença mostram um preço unitário e uma quantidade. Os detalhes da fatura mostram os produtos comprados, desconto ou créditos que foram aplicados, taxa e valor do imposto e os totais dos itens da linha.

> Total = Encargos - Crédito Azure + Impostos

O valor total devido para cada família de serviço é calculado subtraindo os créditos Azure dos créditos/encargos e adicionando o imposto:

> Total = Encargos/Créditos - Crédito Azure + Impostos

Se houver encargos do Azure em sua fatura sobre as quais você deseja obter mais detalhes, consulte [Revisar sua fatura do Contrato de Cliente da Microsoft](/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Entenda a última página da fatura

### <a name="payment-instructions"></a>Instruções de Pagamento

Na parte inferior da fatura há instruções sobre como pagar sua conta. Você pode pagar por transferência bancária, cheque ou online.

### <a name="publisher-information"></a>Informações do fornecedor

Se você tiver serviços de terceiros em sua cobrança, o nome e o endereço de cada editor estará listado na parte inferior da fatura.

## <a name="view-your-online-invoice"></a>Veja sua fatura online

As notas fiscais estão disponíveis online. Um link para sua fatura online está disponível em sua fatura em PDF e em uma notificação por email. A fatura online é expansível para que você possa visualizar os encargos em sua fatura e ver mais detalhes de cada item. A fatura online inclui:

- **Detalhes de preços**&mdash; Informações adicionais, incluindo detalhes sobre descontos e preços de produtos.

- **Pagamento online**&mdash; Você pode optar por fazer um pagamento online a partir da fatura.

- **Gerenciamento de custos do Azure**&mdash;Para clientes do Azure, as notas fiscais online incluem um link para o gerenciamento de custos do Azure.

### <a name="to-view-your-online-invoice"></a>Para visualizar sua fatura online

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Cobranças e pagamentos</a>.

2. Para baixar a versão .pdf da sua fatura, escolha **Baixar fatura em PDF** na linha da fatura que deseja ver.

3. Para visualizar sua fatura online, escolha uma fatura da lista. Você também pode baixar o .pdf na página de detalhes da fatura.

## <a name="invoice-faq"></a>Perguntas Frequentes sobre a fatura

### <a name="when-is-my-invoice-available"></a>Quando minha fatura estará disponível?

Algumas notas fiscais são geradas dentro de 24 horas após a compra. Outras notas fiscais são geradas no final do período de cobrança e incluem todos os itens desse período.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Como faço para pagar o valor devido na minha fatura?

As instruções de pagamento dependem do seu método de pagamento e são fornecidas na parte inferior do PDF da fatura. Se o seu método de pagamento for um cartão de crédito, a cobrança será feita automaticamente em até 10 dias a partir da data da fatura. Se seu método de pagamento for por cheque ou transferência bancária, consulte as informações em **Instruções de pagamento** no PDF.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Qual é a diferença entre endereços "Vendido para" e "Cobrar em"?

- **Vendido para:** É a entidade legal responsável pelo pagamento e identificada na fatura. O endereço fornecido aqui é usado para determinar sua taxa de imposto, a menos que você opte por fornecer um endereço de entrega alternativo durante a compra. Para mais informações, consulte [Informações sobre impostos](tax-information.md).
- **Cobrar em:** É o endereço para onde a fatura física é enviada, se aplicável. Pode haver vários endereços de **Cobrança** por pessoa jurídica, mas apenas um endereço de **Cobrança** por perfil de cobrança.

### <a name="what-are-billed-amount-and-amount-due"></a>O que são "Valor cobrado" e "Valor devido?"

- **Valor cobrado:** É o valor total da compra que você fez.
- **Valor devido:** É o saldo restante para o que você deve.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Qual é a diferença entre "'Período de serviço" e "Período de cobrança"?

- **Período de serviço:** É o período de tempo durante o qual você é cobrado para usar o serviço.
- **Período de cobrança:** É o período de tempo desde a data da última fatura.

### <a name="how-do-i-view-and-print-my-bill"></a>Como faço para visualizar e imprimir minha cobrança?

1. Na página **cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Cobranças e pagamentos</a>, selecione um intervalo de datas de notas fiscais.
2. Para imprimir ou salvar uma cópia em PDF da cobrança, selecione **Baixar fatura em PDF**, e então imprima o PDF.

Para saber mais, consulte [Veja sua cobrança ou fatura](view-your-bill-or-invoice.md).

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Por que eu não vejo o pagamento antecipado do Azure como um método de pagamento?

O pagamento antecipado do Azure está disponível como forma de pagamento somente para produtos e serviços Azure elegíveis.

## <a name="need-help-contact-support"></a>Precisa de ajuda? Fale com o suporte.

Se você tiver dúvidas ou precisar de ajuda com seus créditos Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crie uma solicitação de suporte com o Suporte do Azure</a>.

Se você tiver dúvidas ou precisar de ajuda com sua fatura no Centro de administração do Microsoft 365, [entre em contato com o suporte para produtos comerciais](../../admin/contact-support-for-business-products.md).