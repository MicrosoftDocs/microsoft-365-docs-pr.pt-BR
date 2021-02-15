---
title: Gerenciar assinaturas de inscrição de autoatendir
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
description: Saiba como gerenciar assinaturas de inscrição de autoatendir gratuitas para sua organização.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376300"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Gerenciar assinaturas de inscrição de autoatendir

## <a name="what-are-self-service-sign-up-subscriptions"></a>O que são assinaturas de inscrição self-service?

Há um número limitado de assinaturas gratuitas de inscrição de autoatend sorte disponíveis para os usuários em sua organização se inscreverem. Um usuário só pode se inscrever e usar uma assinatura de inscrição self-service para si mesmo. Você gerencia assinaturas de inscrição de autoatendida, impedindo que os usuários se inscrevam e excluindo assinaturas gratuitas para as que os usuários se inscreveram. Para obter mais informações sobre a inscrição de autoatendado e as assinaturas disponíveis, consulte Usando a inscrição de [autoatendado em sua organização.](../../admin/misc/self-service-sign-up.md)

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Exibir uma lista de assinaturas de inscrição self-service

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre.** Uma lista de todas as assinaturas de inscrição de autoatendido é exibida.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>De que forma essas assinaturas são diferentes das assinaturas de compra self-service?

As assinaturas de inscrição de autoatendínio são gratuitas e estão disponíveis para uma lista maior de produtos do que as assinaturas de compra de autoatendínio. Quando um usuário se instrua para uma assinatura de compra de autoatend pena, ele é responsável por pagar por ela. Assinaturas de compra de autoatendínio só estão disponíveis para produtos da Plataforma Power (Power BI, Power Apps e Power Automate), Project e Visio. Para obter mais informações, consulte [Perguntas frequentes sobre compra de autoatend saiba](self-service-purchase-faq.md)mais.

## <a name="block-users-from-signing-up"></a>Impedir que os usuários se insuem

Use o cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) com o parâmetro **AllowAdHocSubscriptions** para controlar se os usuários podem se inscrever para assinaturas de inscrição de autoatendente. Para obter mais informações, [consulte Como faço para controlar as configurações de autoatend site?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Excluir uma assinatura de inscrição de autoatendado

> [!IMPORTANT]
> Ao excluir uma assinatura de inscrição self-service, você bloqueia todos os usuários de acessar seus dados e emails e excluir todos os dados e emails.

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **Produtos,** selecione o ícone de filtro e selecione **Livre.**
3. Selecione a assinatura de inscrição self-service que você deseja excluir. 
4. Na página de detalhes da assinatura, na seção Assinaturas e **configurações de pagamento,** selecione **Excluir assinatura.**
5. No painel **Excluir assinatura,** marque a caixa de seleção e selecione **Excluir assinatura.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Eu tenho uma assinatura de inscrição de autoatendário que bloqueia a exclusão de diretórios

Os produtos de assinatura self-service que usuários individuais podem se inscrever também criam um usuário convidado para autenticação em seu diretório do Azure AD. Para evitar a perda de dados, esses produtos pessoais bloqueiam exclusões de diretórios até que eles são totalmente excluídos do diretório. Eles só podem ser excluídos pelo administrador do Azure AD. Para saber mais, confira [Excluir um diretório no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)