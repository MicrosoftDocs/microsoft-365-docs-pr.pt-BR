---
title: Gerenciar contas de cobrança
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
ms.custom: ''
search.appverid:
- MET150
description: Saiba mais sobre contas de cobrança e como gerenciá-las.
ms.openlocfilehash: 37b9d8a9de8b187e5685f2b10fbb20d1589904b4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080398"
---
# <a name="manage-billing-accounts"></a>Gerenciar contas de cobrança

Uma conta de cobrança é criada quando você se inscreve para experimentar ou comprar produtos da Microsoft. Você usa sua conta de cobrança para gerenciar suas configurações de conta, faturas, métodos de pagamento e compras. Você pode ter acesso a várias contas de cobrança. Por exemplo, você se inscreveu no Microsoft 365 diretamente ou tem acesso ao contrato corporativo da sua organização, ao contrato de serviços de & de produtos da Microsoft ou ao contrato de cliente da Microsoft. Para cada um desses cenários, você teria uma conta de cobrança separada.

O centro de administração do Microsoft 365 atualmente oferece suporte ao seguinte tipo de contas de cobrança:

- Programa do Microsoft Online Services: essa conta de cobrança é criada quando você se inscreve para uma assinatura do Microsoft 365 diretamente.
- Programa Microsoft Products & Services Agreement (MPSA): esta conta de cobrança é criada quando sua organização assina um contrato de licenciamento por volume do MPSA para comprar software e serviços online.
- Contrato de cliente da Microsoft: essa conta de cobrança é criada quando sua organização trabalha com um representante da Microsoft, um parceiro autorizado ou compras independentemente.

A página <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">contas de cobrança</a> fornece uma visão das suas contas comerciais com a Microsoft. Por padrão, sua organização tem pelo menos uma conta de cobrança associada a um contrato que é aceito no momento de uma compra direta ou por meio de uma organização de licenciamento por volume.

## <a name="understand-billing-account-details"></a>Entender detalhes da conta de cobrança

A parte superior da página de detalhe de **contas de cobrança** é seu perfil de conta e contém informações legais e fiscais sobre sua organização. Você pode atualizar seu perfil para alterar seu endereço legal e número de telefone. Essa conta é a entidade legal que paga os produtos que você comprou.

A tabela a seguir lista os termos importantes exibidos na página de detalhes de **contas de cobrança** .

| Nome do campo | Descrição |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Endereço vendido para | A entidade legal responsável pelo pagamento e identificada na fatura. O endereço fornecido aqui é usado para determinar sua taxa de imposto, a menos que você opte por fornecer um endereço de envio alternativo durante sua compra. Para obter mais informações, consulte [Tax Information](#tax-information). |
| Segmento | Um campo somente leitura que identifica o segmento comercial de sua organização (comercial, educação, governo ou sem fins lucrativos). |
| Status da conta | Um campo somente leitura que especifica o status de sua conta comercial com a Microsoft. |
| ID de imposto | Se você estiver fora dos Estados Unidos, você deve fornecer um VAT ou equivalente local. Para obter mais informações, consulte [Tax Information](#tax-information). |
| Contrato | Quando uma conta de cobrança é criada, seja por meio de uma compra direta ou de uma organização de licenciamento por volume, um signatário para a organização aceita ou assina um contrato que descreve os termos & condições da conta. Se aplicável, este modo de exibição lista o histórico de contratos. Se for necessário aceitar termos atualizados, um link para **aprovar contrato** será exibido. |
| Perfis de cobrança | Um perfil de cobrança define as propriedades de sua fatura, como quem recebe a lista, como a cobrança é entregue, as condições de pagamento e um número de OC. Para distribuir cobrança em toda a sua organização, você pode criar vários perfis de cobrança e identificar o perfil de cobrança apropriado no momento da compra. Para obter mais informações sobre perfis de cobrança e como você pode usá-los para criar opções de cobrança mais flexíveis para sua organização, [gerencie perfis de cobrança](../billing-and-payments/manage-billing-profiles.md). |

> [!NOTE] 
> Se você quiser alterar o nome ou endereço de **vendido para** , mas não vir um link de **edição** , você deve [entrar em contato](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) com o suporte para alterá-lo. As solicitações para uma alteração de nome **vendidas** exigirão uma verificação de crédito. Ao entrar em contato com o suporte, tenha um dos seguintes documentos prontos:
>
> - Documento de anúncio externo que indica qualquer alteração no nome da empresa ou na estrutura corporativa
> - Documento emitido pelo governo ou carta de registro
> - Imprimir fora do registro da empresa local
>
> O suporte pode ajudar nas alterações de nome e endereço onde apenas o nome do cliente é alterado, mas a entidade permanece a mesma. A documentação fornecida deve indicar claramente que apenas o nome da entidade foi alterado. Se a alteração estiver relacionada a qualquer transação, como uma venda de negócios ou um divestiture ou "spinoff" de um cliente associado, entre em contato com o seu vendedor da Microsoft.

## <a name="shipping-addresses"></a>Endereços de envio

Esta seção lista os endereços de envio associados à sua conta de cobrança. Ao fazer uma compra, você pode usar esse endereço para identificar onde sua compra será entregue ou usada. O endereço de entrega é editável. Você pode adicionar um endereço de remessa ou atualizar o endereço existente. Esse endereço é usado para determinar a taxa de imposto de sua compra.

## <a name="understand-access-to-billing-accounts"></a>Entender o acesso às contas de cobrança

Você pode fornecer a outras pessoas acesso à conta de cobrança no centro de administração do Microsoft 365 por meio de funções e permissões. Somente um proprietário de conta de cobrança pode conceder acesso a uma conta de cobrança. Você pode atribuir uma das seguintes funções aos usuários:

- O **proprietário** &mdash; da conta de cobrança pode atribuir permissões, editar contas, assinar contratos e exibir contas.
- O **colaborador** &mdash; da conta de cobrança pode editar contas, assinar contratos e exibir contas.
- O **leitor** &mdash; de conta de cobrança pode exibir contas.

> [!Note]
> As funções de conta de cobrança só se aplicam às contas de cobrança e não se aplicam a outros cenários do centro de administração do Microsoft 365.

## <a name="tax-information"></a>Informações sobre impostos

Os impostos para compras do centro de administração do Microsoft 365 que você faz através da Microsoft são determinados pelo endereço comercial ou, se for diferente, pelo seu endereço de entrega. Se estiver nos Estados Unidos, você deve fornecer um número de identificação de empregador Federal (FEIN).

As empresas nesses países podem fornecer o número de IVA:

:::row:::
    :::column:::
- Áustria
- Bélgica
- Bulgária
- Croácia
- Chipre
- República Tcheca
- Dinamarca
- Estônia
- Finlândia
- França
- Alemanha
- Grécia
- Hungria
- Irlanda
- Itália
- Letônia
    :::column-end:::
    :::column:::
- Liechtenstein
- Lituânia
- Luxemburgo
- Malta
- Mônaco 
- Países Baixos
- Noruega
- Polônia
- Portugal
- Romênia
- Eslováquia
- África do Sul
- Espanha
- Suécia
- Suíça
- Reino Unido
    :::column-end:::
:::row-end:::

Esses países podem fornecer o número de IVA ou o equivalente local em suas informações de conta de cobrança.

|Comercial| Identificador de imposto |
|------|----------------|
| Austrália | ABN (opcional) |
| Brasil | CNPJ (obrigatório) |
| Índia | GSTIN (opcional), ID de panorâmica (obrigatório) |
| Ilha de Man | ID de IVA (opcional) |
| JPRatingExplicitAllowed | Número de registro de GST (opcional) |
| Mônaco  | ID de IVA (opcional) |
| Taiwan | ID de IVA (opcional) |

> [!Note]
> Se você precisar entrar em contato com o suporte, peça que o FEIN, o número de IVA ou o equivalente local estejam prontos para dar ao agente de suporte.

## <a name="tax-exempt-status"></a>Status de isenção de imposto

Se você estiver qualificado para status de isenção de impostos em seu mercado, [inicie uma solicitação de serviço](https://docs.microsoft.com/office365/admin/contact-support-for-business-products) para estabelecer o status de isenção de imposto para sua organização.

Prepare a seguinte documentação:

|País ou localidade | Documentação |
|------------------|----------------|
| Estados Unidos | Certificado de isenção de impostos sobre vendas |
| Canadá | Certificado de isenção (ou carta equivalente de autorização) |
| Irlanda | Certificado de isenção de imposto 13B/56A|
| Organizações internacionais que mantêm a isenção de impostos | Confirmação de carta/certificação de autoridades fiscais locais |
| Porto Rico | Certificado de compras exentas |

## <a name="calculate-taxes"></a>Calcular impostos

Os impostos sobre vendas são calculados em relação ao preço unitário e, em seguida, agregados.

Por exemplo:

>*(preço unitário X taxa de imposto) X quantidade = total de imposto sobre vendas*

- ou -

>($1.29 X 0, 95) X 100 = $12.25
