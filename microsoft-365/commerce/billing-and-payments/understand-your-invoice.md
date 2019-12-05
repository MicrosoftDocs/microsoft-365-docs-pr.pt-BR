---
title: Entender sua fatura
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
ms.custom: ''
search.appverid:
- MET150
description: Saiba como ler e entender sua fatura para produtos de negócios da Microsoft.
keywords: contas de cobrança, informações da organização, faturas
ms.openlocfilehash: 0319f8ce1cfc0fcfeec095e6dedccefdcb1a0a4d
ms.sourcegitcommit: 95a07b328166f637a481c8b5c53669eaf8ff0db8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39837375"
---
# <a name="understand-your-invoice"></a>Entender sua fatura

A fatura fornece um resumo de seus encargos e instruções para pagamento. Você pode [exibir sua fatura online](#view-your-online-invoice) no centro de administração do Microsoft 365. Você também pode baixá-lo no formato de documento portátil (. pdf) para enviar por email.

Se você tiver uma assinatura do Office 365, confira [exibir sua fatura do Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/view-your-bill-or-invoice).

## <a name="understand-the-invoice-header"></a>Entender o cabeçalho da fatura

A parte superior da primeira página identifica quem é responsável pelo pagamento, onde a cobrança é enviada e um resumo dos encargos.

| Termo | Descrição |
| --- | --- |
| Vendido para |A conta de cobrança que identifica o nome e o endereço da entidade legal responsável pelo pagamento. Essas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">contas de cobrança</a> , onde você pode encontrar o contrato de conta e gerenciar funções e permissões. |
| Faturar para |Identifica quem recebe a fatura. Essas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfis de cobrança</a> . O perfil de cobrança também é mostrado na página fatura online, na seção **Resumo da fatura** . Para saber mais sobre perfis de cobrança e como você pode usá-los para criar opções de cobrança mais flexíveis para sua organização, consulte [Manage Rebilling Profiles](manage-billing-profiles.md). |
| Perfil de cobrança |O nome do perfil de cobrança usado para definir as propriedades de fatura, como faturar, número da OC e condições de pagamento. Essas informações podem ser gerenciadas na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfis de cobrança</a> . Para obter mais informações sobre perfis de cobrança e como usá-los para criar opções de cobrança mais flexíveis para sua organização, consulte [Manage billing Profiles](manage-billing-profiles.md). |
| Número da fatura |Um número exclusivo de fatura gerado pela Microsoft usado para fins de acompanhamento. |
| Data da fatura |Data em que a fatura é gerada, geralmente cinco a 12 dias após o fim do ciclo de cobrança. Você pode verificar a data da fatura na página de detalhes do perfil de cobrança. Os encargos que ocorrem entre o final do período de cobrança e a data da fatura são incluídos na fatura do mês seguinte, pois estão no próximo período de cobrança. As datas de início e término do período de cobrança de cada fatura são listadas no Resumo de **cobrança**do PDF de fatura.|
| Condições de pagamento |Como você paga pelo Microsoft Bill. *30 dias líquidos* significa que você paga seguindo as instruções da fatura, dentro de 30 dias da data da fatura. |

## <a name="understand-the-billing-summary"></a>Entender o resumo de cobrança

O **Resumo de cobrança** mostra o resumo dos encargos desde o período de cobrança anterior, todos os créditos que foram aplicados, impostos e o valor total devido.

| Termo | Descrição |
| --- | --- |
| Encargos|Número total de produtos comprados para esse período de cobrança e seus impostos e taxas relacionados. As compras são agregadas para fornecer uma visão concisa da sua cobrança. |
| Créditos |Créditos recebidos de Devoluções |
| Créditos do Azure aplicados |Seus créditos do Azure aplicados automaticamente ao Azure cobram cada período de cobrança. Se você não tiver créditos do Azure, este campo ficará oculto. Para obter mais informações sobre os créditos do Azure, confira [acompanhar o saldo de crédito do Microsoft Customer Agreement](https://docs.microsoft.com/azure/billing/billing-mca-check-azure-credits-balance). |
| Subtotal |O valor de pré-imposto devido |
| Imposto |O tipo e a quantidade de impostos que você paga, dependendo do país do seu perfil de cobrança. Se você não tiver que pagar o imposto, nenhum imposto será exibido na fatura. |

### <a name="understand-your-charges"></a>Entender seus encargos

As páginas de encargos mostram o custo dividido por produto. Para clientes do Azure, os encargos podem ser organizados por seção de fatura. Para obter mais informações sobre como as seções de fatura são usadas com produtos do Azure, confira [seções de fatura](https://docs.microsoft.com/azure/billing/billing-mca-overview#invoice-sections) em introdução [à sua conta de cobrança de contrato de cliente da Microsoft](https://docs.microsoft.com/azure/billing/billing-mca-overview). Dentro de cada ordem de produto, o custo é dividido pela família de serviços.

| Termo |Descrição |
| --- | --- |
| Preço unitário | O preço unitário efetivo do serviço (em moeda de preço) que é usado para calcular o encargo. Este preço é exclusivo para um produto, uma família de serviços, um medidor e uma oferta. |
| Qtd | Quantidade comprada ou consumida durante o período de cobrança |
| Encargos/créditos | Valor líquido de encargos após a aplicação de créditos/reembolsos |
| Crédito do Azure | A quantidade de créditos do Azure aplicados aos encargos/créditos |
| Taxa de imposto | Taxa de imposto, dependendo do país |
| Valor do imposto | Quantidade de imposto aplicada à compra com base na taxa de imposto |
| Total | O valor total devido para a compra |

Os detalhes dos itens de linha variam dependendo do tipo de produto para o qual você está cobrado. Por exemplo, para produtos do Azure, a quantidade de créditos do Azure aplicados é mostrada. Os produtos baseados em assentos mostram o preço unitário e a quantidade. Os detalhes da fatura descrevem os produtos comprados, desconto ou créditos que foram aplicados, a taxa de impostos e o valor e os totais de itens de linha.

`Total = Charges - Azure Credit + Tax`

O valor total devido para cada família de serviços é calculado subtraindo créditos do Azure de créditos/cobranças e adicionando impostos:

`Total = Charges/Credits - Azure Credit + Tax`

Se houver encargos do Azure na fatura que você gostaria de obter mais detalhes, confira [entender os encargos em sua fatura de contrato de cliente da Microsoft](https://docs.microsoft.com/azure/billing/billing-mca-understand-your-bill).

## <a name="understand-the-last-invoice-page"></a>Entender a última página de fatura

### <a name="payment-instructions"></a>Instruções de pagamento

Na parte inferior da fatura estão instruções sobre como pagar sua cobrança. Você pode pagar por fio, verificar ou online.

### <a name="publisher-information"></a>Informações do fornecedor

Se você tiver serviços de terceiros em sua lista, o nome e o endereço de cada editor serão listados na parte inferior da fatura.

## <a name="view-your-online-invoice"></a>Exibir sua fatura online

As faturas estão disponíveis online. Um link para sua fatura online está disponível na sua fatura do PDF e a partir de uma notificação por email. A fatura online é expansível para que você possa exibir os encargos em sua fatura e ver mais detalhes de cada item. A fatura online inclui:

- **Detalhes** &mdash; de preços informações adicionais, incluindo detalhes sobre descontos e preços de produto.

- **Pagamento** &mdash; online você pode optar por fazer um pagamento online da fatura.

- **Azure cost Management** &mdash; for Azure clientes, faturas online incluem um link para o gerenciamento de custos do Azure.

### <a name="to-view-your-online-invoice"></a>Para exibir sua fatura online

1. No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faturas e pagamentos</a>.

2. Para baixar a versão. pdf da fatura, escolha **baixar nota fiscal PDF** na linha da fatura que você deseja ver.

3. Para exibir sua fatura online, escolha uma fatura na lista. Você também pode baixar o. pdf da página detalhes da fatura.

## <a name="need-help-contact-support"></a>Precisa de ajuda? Fale com o suporte.

Se você tiver dúvidas ou precisar de ajuda com seus créditos do Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crie uma solicitação de suporte com o suporte do Azure</a>.

Se você tiver dúvidas ou precisar de ajuda com sua fatura no centro de administração do Microsoft 365, [entre em contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).
