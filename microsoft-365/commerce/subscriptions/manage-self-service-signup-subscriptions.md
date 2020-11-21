---
title: Gerenciar assinaturas de inscrição de autoatendimento
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
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Saiba como gerenciar assinaturas gratuitas de inscrição de autoatendimento para sua organização.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376300"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Gerenciar assinaturas de inscrição de autoatendimento

## <a name="what-are-self-service-sign-up-subscriptions"></a>O que são assinaturas de inscrição de autoatendimento?

Há um número limitado de assinaturas gratuitas de inscrição de autoatendimento disponíveis para que os usuários da sua organização se inscrevam. Um usuário só pode se inscrever para e usar uma assinatura de inscrição autoatendimento por conta própria. Você gerencia as assinaturas de inscrição de autoatendimento, bloqueando os usuários de inscrever-se e excluindo assinaturas gratuitas das quais os usuários se inscreveram. Para obter mais informações sobre a inscrição de autoatendimento e as assinaturas disponíveis, consulte usar a inscrição de autoatendimento [em sua organização](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Exibir uma lista de assinaturas de inscrição de autoatendimento

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **produtos** , selecione o ícone de filtro e, em seguida, selecione **gratuito**. É exibida uma lista de todas as assinaturas de inscrição de autoatendimento.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>Como essas assinaturas são diferentes das assinaturas de compras de autoatendimento?

As assinaturas de inscrição de autoatendimento são gratuitas e estão disponíveis para uma lista maior de produtos do que as assinaturas de compras de autoatendimento. Quando um usuário se inscreve em uma assinatura de compra de autoatendimento, ele é responsável por pagar por ela. As assinaturas de compras de autoatendimento estão disponíveis apenas para produtos de plataforma de alimentação (Power BI, aplicativos de energia e automatização de energia), Project e Visio. Para obter mais informações, consulte [perguntas frequentes sobre compras de autoatendimento](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Bloquear a inscrição de usuários

Use o cmdlet [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) com o parâmetro **AllowAdHocSubscriptions** para controlar se os usuários podem se inscrever em assinaturas de inscrição de autoatendimento. Para obter mais informações, consulte [como controlar as configurações de autoatendimento?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Excluir uma assinatura de inscrição de autoatendimento

> [!IMPORTANT]
> Quando você exclui uma assinatura de inscrição de autoatendimento, impede que todos os usuários acessem seus dados e emails e exclua todos os dados e email.

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **produtos** , selecione o ícone de filtro e, em seguida, selecione **gratuito**.
3. Selecione a assinatura de inscrição de autoatendimento que você deseja excluir. 
4. Na página detalhes da assinatura, na seção **definições de pagamento e assinaturas** , selecione **excluir assinatura**.
5. No painel **excluir assinatura** , marque a caixa de seleção e, em seguida, selecione **excluir assinatura**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Tenho uma assinatura de inscrição de autoatendimento que bloqueia a exclusão de diretórios

Os produtos de inscrição de autoatendimento que os usuários individuais podem se inscrever para também criar um usuário convidado para autenticação no seu diretório do Azure AD. Para evitar a perda de dados, esses produtos de autoatendimento bloqueiam exclusões de diretório até que sejam totalmente excluídos do diretório. Eles só podem ser excluídos pelo administrador do Azure AD. Para obter mais informações, consulte [excluir um diretório no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).