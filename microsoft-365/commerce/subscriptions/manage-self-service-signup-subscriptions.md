---
title: Gerenciar assinaturas de inscrição de autoatend
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Saiba como gerenciar assinaturas de inscrição gratuitas de autoatendir para sua organização.
ms.date: 03/17/2021
ms.openlocfilehash: 741c9e0b45f127ffc0753b34982073f90c525d5b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536065"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Gerenciar assinaturas de inscrição de autoatend

## <a name="what-are-self-service-sign-up-subscriptions"></a>O que são assinaturas de inscrição de autoatendidores?

Há um número limitado de assinaturas de inscrição gratuitas de autoatend., disponíveis para os usuários em sua organização se inscreverem. Um usuário só pode se inscrever e usar uma assinatura de inscrição de autoatend nome. Você gerencia assinaturas de inscrição de autoatendados bloqueando os usuários de se inscreverem e excluindo assinaturas gratuitas para as que os usuários se inscreveram. Para obter mais informações sobre a inscrição no autoatendado e as assinaturas disponíveis, consulte Usando o [autoatendino inscreva-se em sua organização](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Exibir uma lista de assinaturas de inscrição de autoatend

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.
2. Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre**. Uma lista de todas as assinaturas de inscrição de autoatendido é exibida.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Como essas assinaturas são diferentes das assinaturas de compra de autoatendidores?

As assinaturas de inscrição de autoatendados são gratuitas e estão disponíveis para uma lista maior de produtos do que assinaturas de compra de autoatendados. Quando um usuário se insinuou em uma assinatura de compra de autoatendam, ele é responsável por pagar por ela. As assinaturas de compra de autoatendados estão disponíveis apenas para produtos da Plataforma Power (Power BI, Power Apps e Power Automate), Project e Visio. Para obter mais informações, consulte Perguntas frequentes sobre [compra de autoatend.](self-service-purchase-faq.yml)

## <a name="block-users-from-signing-up"></a>Impedir que os usuários se insuem

Você usa o cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) com o **parâmetro AllowAdHocSubscriptions** para controlar se os usuários podem se inscrever para assinaturas de inscrição de autoatendência. Para obter mais informações, consulte [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Excluir uma assinatura de inscrição de autoatendado

> [!IMPORTANT]
> Ao excluir uma assinatura de inscrição de autoatendado, você bloqueia todos os usuários de acessar seus dados e emails e excluir todos os dados e emails.

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.
2. Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre**.
3. Selecione a assinatura de inscrição de autoatendado que você deseja excluir. 
4. Na página detalhes da assinatura, na seção **Assinaturas e configurações de** pagamento, selecione **Excluir assinatura**.
5. No painel **Excluir assinatura,** marque a caixa de seleção e selecione **Excluir assinatura**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Tenho uma assinatura de inscrição de autoatendados que bloqueia a exclusão de diretórios

Os produtos de assinatura de autoatendados que os usuários individuais podem inscrever também criam um usuário convidado para autenticação no diretório do Azure AD. Para evitar a perda de dados, esses produtos autoatendados bloqueiam exclusões de diretório até que eles são totalmente excluídos do diretório. Eles só podem ser excluídos pelo administrador do Azure AD. Para obter mais informações, [consulte Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).
