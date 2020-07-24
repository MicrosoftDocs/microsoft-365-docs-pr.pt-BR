---
title: Entenda sua conta ou fatura
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsInvoices
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como ler e entender sua cobrança ou fatura para produtos de negócios da Microsoft.
keywords: contas de cobrança, informações da organização, faturas
ms.openlocfilehash: f0575683cdcaf0ac76de80c93e0d7573e8c63bae
ms.sourcegitcommit: 41eb898143286755cd36df9f7e769de641263d73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45391513"
---
# <a name="understand-your-bill-or-invoice"></a>Entenda sua conta ou fatura

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

A fatura fornece um resumo de seus encargos e instruções para pagamento. Você pode [exibir sua fatura online](#view-your-online-invoice) no centro de administração do Microsoft 365. Você também pode baixá-lo no formato de documento portátil (. pdf) para enviar por email.

Se você tiver apenas uma assinatura do Microsoft 365, confira [entender sua cobrança ou fatura para a Microsoft 365 para empresas](understand-your-invoice2.md).

## <a name="understand-the-invoice-header"></a>Entender o cabeçalho da fatura

A parte superior da primeira página identifica quem é responsável pelo pagamento, onde a cobrança é enviada e um resumo dos encargos.

| Term | Descrição |
| --- | --- |
| Vendido para |A conta de cobrança que identifica o nome e o endereço da entidade legal responsável pelo pagamento. Essas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">contas de cobrança</a> , onde você pode encontrar o contrato de conta e gerenciar funções e permissões. |
| Faturar para |Identifica quem recebe a fatura. Essas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfis de cobrança</a> . O perfil de cobrança também é mostrado na página fatura online, na seção **Resumo da fatura** . Para saber mais sobre perfis de cobrança e como você pode usá-los para criar opções de cobrança mais flexíveis para sua organização, consulte [Manage Rebilling Profiles](manage-billing-profiles.md). |
| Perfil de cobrança |O nome do perfil de cobrança usado para definir as propriedades de fatura, como **faturar**, **número da OC**e condições de pagamento. Essas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfis de cobrança</a> . Para obter mais informações sobre perfis de cobrança e como usá-los para criar opções de cobrança mais flexíveis para sua organização, consulte [Manage billing Profiles](manage-billing-profiles.md). |
| Número da fatura |Um número exclusivo de fatura gerado pela Microsoft usado para fins de acompanhamento. |
| Data da fatura |Data em que a fatura é gerada, geralmente cinco a 12 dias após o fim do ciclo de cobrança. Você pode verificar a data da fatura na página de detalhes do perfil de cobrança. Os encargos que ocorrem entre o final do período de cobrança e a data da fatura são incluídos na fatura do mês seguinte, pois estão no próximo período de cobrança. As datas de início e término do período de cobrança de cada fatura são listadas no Resumo de **cobrança**do PDF de fatura.|
| Condições de pagamento |Como você paga pelo Microsoft Bill. *30 dias líquidos* significa que você paga seguindo as instruções da fatura, dentro de 30 dias da data da fatura. |

## <a name="understand-the-billing-summary"></a>Entender o resumo de cobrança

O **Resumo de cobrança** mostra o resumo dos encargos desde o período de cobrança anterior, todos os créditos que foram aplicados, impostos e o valor total devido.

| Term | Descrição |
| --- | --- |
| Encargos|Número total de produtos comprados para esse período de cobrança e seus impostos e taxas relacionados. As compras são agregadas para fornecer uma visão concisa da sua cobrança. |
| Créditos |Créditos recebidos de Devoluções |
| Créditos do Azure aplicados |Seus créditos do Azure aplicados automaticamente ao Azure cobram cada período de cobrança. Se você não tiver créditos do Azure, este campo ficará oculto. Para obter mais informações sobre os créditos do Azure, confira [acompanhar o saldo de crédito do Microsoft Customer Agreement](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotal |O valor de pré-imposto devido |
| Imposto |O tipo e a quantidade de impostos que você paga, dependendo do país do seu perfil de cobrança. Se você não tiver que pagar o imposto, nenhum imposto será exibido na fatura. |

### <a name="understand-your-charges"></a>Entender seus encargos

As páginas de encargos mostram o custo dividido por produto. Para clientes do Azure, os encargos podem ser organizados por seção de fatura. Para obter mais informações sobre como as seções de fatura são usadas com produtos do Azure, confira [seções de fatura](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) em introdução [à sua conta de cobrança de contrato de cliente da Microsoft](https://docs.microsoft.com/azure/billing/billing-mca-overview). Dentro de cada ordem de produto, o custo é dividido pela família de serviços.

| Term |Descrição |
| --- | --- |
| Preço unitário | O preço unitário efetivo do serviço (em moeda de preço) que é usado para calcular o encargo. Este preço é exclusivo para um produto, uma família de serviços, um medidor e uma oferta. |
| Qtd | Quantidade comprada ou consumida durante o período de cobrança |
| Encargos/créditos | Valor líquido de encargos após a aplicação de créditos/reembolsos |
| Crédito do Azure | A quantidade de créditos do Azure aplicados aos encargos/créditos |
| Taxa de imposto | Taxa de imposto, dependendo do país |
| Valor do imposto | Quantidade de imposto aplicada à compra com base na taxa de imposto |
| Total | O valor total devido para a compra |

Os detalhes dos itens de linha variam dependendo do tipo de produto para o qual você está cobrado. Por exemplo, para produtos do Azure, a quantidade de créditos do Azure aplicados é mostrada. Os produtos baseados em assentos mostram o preço unitário e a quantidade. Os detalhes da fatura mostram os produtos comprados, desconto ou créditos que foram aplicados, a taxa de impostos e o valor e os totais de itens de linha.

> Total = encargos-crédito do Azure + imposto

O valor total devido para cada família de serviços é calculado subtraindo créditos do Azure de créditos/cobranças e adicionando impostos:

> Total = encargos/créditos-crédito do Azure + imposto

Se houver encargos do Azure na fatura que você gostaria de obter mais detalhes, consulte [revisar sua fatura de contrato de cliente da Microsoft](https://docs.microsoft.com/azure/cost-management-billing/understand/review-customer-agreement-bill).

## <a name="understand-the-last-invoice-page"></a>Entender a última página de fatura

### <a name="payment-instructions"></a>Instruções de pagamento

Na parte inferior da fatura estão instruções sobre como pagar sua cobrança. Você pode pagar por fio, verificar ou online.

### <a name="publisher-information"></a>Informações do fornecedor

Se você tiver serviços de terceiros em sua lista, o nome e o endereço de cada editor serão listados na parte inferior da fatura.

## <a name="view-your-online-invoice"></a>Exibir sua fatura online

As faturas estão disponíveis online. Um link para sua fatura online está disponível na sua fatura do PDF e a partir de uma notificação por email. A fatura online é expansível para que você possa exibir os encargos em sua fatura e ver mais detalhes de cada item. A fatura online inclui:

- **Detalhes** &mdash; de preços Informações adicionais, incluindo detalhes sobre descontos e preços de produto.

- **Pagamento online** &mdash; Você pode optar por fazer um pagamento online da fatura.

- Gerenciamento de custos **do Azure** &mdash; Para clientes do Azure, faturas online incluem um link para o gerenciamento de custos do Azure.

### <a name="to-view-your-online-invoice"></a>Para exibir sua fatura online

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faturas e pagamentos</a>.

2. Para baixar a versão. pdf da fatura, escolha **baixar nota fiscal PDF** na linha da fatura que você deseja ver.

3. Para exibir sua fatura online, escolha uma fatura na lista. Você também pode baixar o. pdf da página detalhes da fatura.

## <a name="invoice-faq"></a>Perguntas frequentes de fatura

### <a name="when-is-my-invoice-available"></a>Quando está minha fatura disponível?

Algumas faturas são geradas dentro de 24 horas da compra. Outras faturas são geradas no final do período de cobrança e incluem todos os itens desse período.

### <a name="how-do-i-pay-the-amount-due-on-my-invoice"></a>Como pagar o valor devido na minha fatura?

As instruções de pagamento dependem da forma de pagamento e são fornecidas na parte inferior do PDF da fatura. Se sua forma de pagamento for um cartão de crédito, ela será automaticamente carregada dentro de 10 dias da data da fatura. Se sua forma de pagamento for por cheque ou transferência por fio, Confira as informações em **instruções de pagamento** no PDF.

### <a name="whats-the-difference-between-sold-to-and-bill-to-addresses"></a>Qual é a diferença entre "vendido a" e "endereços de cobrança"?

- **Vendido para:** A entidade legal responsável pelo pagamento e identificada na fatura. O endereço fornecido aqui é usado para determinar sua taxa de imposto, a menos que você opte por fornecer um endereço de envio alternativo durante sua compra. Para obter mais informações, consulte [Tax Information](tax-information.md).
- **Faturar para:** O endereço onde a fatura física é enviada, se aplicável. Pode haver vários endereços **de cobrança** por entidade legal, mas apenas um endereço **de** cobrança por perfil de cobrança.

### <a name="what-are-billed-amount-and-amount-due"></a>O que são "quantia cobrada" e "valor devido?"

- **Valor cobrado:** O valor total da compra que você fez.
- **Valor devido:** O saldo restante para o que você deve ter.

### <a name="what-is-the-difference-between-service-period-and-billing-period"></a>Qual é a diferença entre "período de serviço" e "período de cobrança?"

- **Período de serviço:** O período de tempo durante o qual você está cobrado para usar o serviço.
- **Período de cobrança:** O período de tempo desde a última data de fatura.

### <a name="how-do-i-view-and-print-my-bill"></a>Como exibir e imprimir minha lista?

1. Na página **faturas**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& pagamentos</a> , selecione um intervalo de datas da fatura.
2. Para imprimir ou salvar uma cópia em PDF da lista, selecione **baixar PDF de fatura**e, em seguida, imprimir o PDF.

Para saber mais, confira [exibir sua cobrança ou fatura](view-your-bill-or-invoice.md).

### <a name="why-dont-i-see-azure-prepayment-as-a-payment-method"></a>Por que não vejo o pagamento antecipado do Azure como um método de pagamento?

O pagamento antecipado do Azure está disponível como um método de pagamento somente para produtos e serviços do Azure qualificados.

## <a name="need-help-contact-support"></a>Precisa de ajuda? Fale com o suporte.

Se você tiver dúvidas ou precisar de ajuda com seus créditos do Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crie uma solicitação de suporte com o suporte do Azure</a>.

Se você tiver dúvidas ou precisar de ajuda com sua fatura no centro de administração do Microsoft 365, [entre em contato com o suporte para produtos de negócios](../../admin/contact-support-for-business-products.md).