---
title: Gerenciar contas de cobrança
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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
- PPM_jmueller
ms.reviewer: tugu
search.appverid:
- MET150
description: Saiba mais sobre contas de cobrança e como gerenciá-las.
ms.date: 03/17/2021
ms.openlocfilehash: ecac005b8b49739cb74efc4ca2fae44667f37bad
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293638"
---
# <a name="manage-billing-accounts"></a>Gerenciar contas de cobrança

Uma conta de cobrança é criada ao se inscrever para tentar ou comprar produtos da Microsoft. Use sua conta de cobrança para gerenciar suas configurações de conta, faturas, métodos de pagamento e compras. Você pode ter acesso a várias contas de cobrança. Por exemplo, você se inscreveu Microsoft 365 diretamente, ou tem acesso ao contrato de Enterprise Agreement da sua organização, ao Contrato de Serviços de & produtos da Microsoft ou ao Contrato de Cliente da Microsoft. Para cada um desses cenários, você teria uma conta de cobrança separada.

O Microsoft 365 de administração atualmente dá suporte ao seguinte tipo de contas de cobrança:

- Microsoft Online Services Programa: essa conta de cobrança é criada quando você se ins inscrever para uma assinatura Microsoft 365 diretamente.
- Programa MpSA (Contrato de Serviços de &) da Microsoft Products: essa conta de cobrança é criada quando sua organização assina um contrato de Licenciamento por Volume MPSA para comprar software e serviços online.
- Contrato de Cliente da Microsoft: essa conta de cobrança é criada quando sua organização trabalha com um representante da Microsoft, um parceiro autorizado ou compras independentemente.

A <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">página Contas de cobrança</a> fornece uma exibição de suas contas comerciais com a Microsoft. Por padrão, sua organização tem pelo menos uma conta de cobrança associada a um contrato aceito no momento de uma compra direta ou por meio de um acordo de Licenciamento por Volume.

## <a name="understand-billing-account-details"></a>Compreender detalhes da conta de cobrança

A parte superior da **página de detalhes de contas** de cobrança é seu perfil de conta e contém informações legais e fiscais sobre sua organização. Você pode atualizar seu perfil para alterar seu endereço legal e número de telefone. Essa conta é a entidade jurídica que paga pelos produtos que você compra.

A tabela a seguir lista os termos importantes que você vê na página de detalhes **de contas de** cobrança.

| Nome do campo | Descrição |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Endereço vendido | A entidade jurídica responsável pelo pagamento e identificada na fatura. O endereço fornecido aqui é usado para determinar sua taxa de imposto, a menos que você opte por fornecer um endereço de entrega alternativo durante a compra. Para mais informações, consulte [Informações sobre impostos](billing-and-payments/tax-information.md). |
| Segmento | Um campo somente leitura que identifica o segmento de negócios da sua organização (Comercial, Educação, Governo ou Sem fins lucrativos). |
| Status da conta | Um campo somente leitura que especifica o status da sua conta comercial com a Microsoft. |
| ID de imposto | Se você estiver fora dos Estados Unidos, deverá fornecer um IVA ou equivalente local. Para mais informações, consulte [Informações sobre impostos](billing-and-payments/tax-information.md). |
| Contrato | Quando uma conta de cobrança é criada, por meio de uma compra direta ou de um acordo de Licenciamento por Volume, um signatário da organização aceita ou assina um contrato que descreve os termos & condições da conta. Se aplicável, essa exibição lista um histórico de contratos. Se for necessário aceitar termos atualizados, um link para Aprovar **contrato** será exibido. |
| Perfis de cobrança | Um perfil de cobrança define propriedades da fatura, como quem recebe a fatura, como a fatura é entregue, os termos de pagamento e um número de PO. Para distribuir a cobrança em toda a sua organização, você pode criar vários perfis de cobrança e identificar o perfil de cobrança apropriado no momento da compra. Para obter mais informações sobre perfis de cobrança e como você pode usá-los para criar opções de cobrança mais flexíveis para sua organização, [Entenda os perfis de cobrança.](billing-and-payments/manage-billing-profiles.md) |

> [!NOTE]
> Se você precisar alterar o **nome ou** o endereço Vendido para, mas não vir um link **Editar,** entre em contato com o suporte [para](../business-video/get-help-support.md) alterá-lo. Solicitações para uma **alteração de nome** vendido exigirão uma verificação de crédito. Preencha [este formulário](https://www.microsoft.com/download/details.aspx?id=102732)e esteja pronto para compartilhar um dos seguintes documentos com a Microsoft quando entrar em contato com o suporte:
>
> - Documento emitido pelo governo ou carta de registro
> - Imprimir o registro da empresa local
>
> O suporte pode ajudar com alterações de nome e endereço em que somente o nome do cliente muda, mas a entidade permanece a mesma. A documentação fornecida deve mostrar claramente que apenas o nome da entidade foi alterado. Se a alteração for o resultado de uma transação, incluindo a venda de negócios, uma alteração de controles ou um desempregada ou "spinoff" de uma Afiliada do Cliente, entre em contato com o Microsoft Seller.

## <a name="shipping-addresses"></a>Endereços de envio

Esta seção lista os endereços de envio associados à sua conta de cobrança. Ao fazer uma compra, você pode usar esse endereço para identificar onde sua compra é enviada ou usada. O endereço de envio é editável. Você pode adicionar um endereço de envio ou atualizar o endereço existente. Esse endereço é usado para determinar a taxa de imposto para sua compra.

## <a name="understand-access-to-billing-accounts"></a>Entender o acesso a contas de cobrança

Você pode fornecer a outras pessoas acesso à conta de cobrança no centro de administração Microsoft 365 por meio de funções e permissões. Somente um proprietário de conta de cobrança pode conceder acesso a uma conta de cobrança. Você pode atribuir uma das seguintes funções aos usuários:

- **Proprietário da conta de cobrança** &mdash; Pode atribuir permissões, editar contas, assinar contratos e exibir contas.
- **Colaborador da conta de cobrança** &mdash; Pode editar contas, assinar contratos e exibir contas.
- **Leitor de contas de cobrança** &mdash; Pode exibir contas.

> [!Note]
> As funções de conta de cobrança só se aplicam a contas de cobrança e não se aplicam a outros cenários Microsoft 365 centro de administração.

## <a name="related-content"></a>Conteúdo relacionado

[Informações fiscais](billing-and-payments/tax-information.md) (artigo) \
[Compreender perfis de cobrança](billing-and-payments/manage-billing-profiles.md) (artigo)