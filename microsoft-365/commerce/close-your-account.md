---
title: Fechar sua conta
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
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Quando você fecha sua conta com a Microsoft, todas as informações relacionadas à sua conta são excluídas, incluindo licenças, usuários e dados do usuário.
ms.date: 04/02/2021
ms.openlocfilehash: b212911707b5d6a967ab833a5a06bc76f5ceeb3b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624320"
---
# <a name="close-your-account"></a>Fechar sua conta

Quando você fecha a sua conta do Microsoft, todas as informações relacionadas à sua conta são excluídas. Essas informações incluem assinaturas, licenças, métodos de pagamento, usuários e dados do usuário.

## <a name="before-you-begin"></a>Antes de começar

Antes de iniciar esse processo, faça backup dos dados que queira preservar.

Você deve ser um administrador Global ou de Cobrança para realizar as etapas descritas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Etapa 1: Excluir usuários

Exclua todos os usuários, exceto um administrador global. O administrador global conclui as etapas para fechar a conta. Antes de poder excluir o diretório no final deste processo, você deve excluir todos os outros usuários.

Se os usuários estiverem sincronizados no local, primeiro desligue a sincronização e exclua os usuários no diretório de nuvem usando o portal do Azure ou Azure PowerShell cmdlets.

Para excluir usuários, consulte [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).

Você também pode usar o cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell para excluir usuários em massa.

Se sua organização usa o Active Directory que sincroniza com o Microsoft Azure Active Directory (Azure AD), exclua a conta de usuário do Active Directory, em vez disso. Para obter instruções, consulte [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).

## <a name="step-2-cancel-all-active-subscriptions"></a>Etapa 2: Cancelar todas as assinaturas ativas

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.
2. Na guia **Produtos,** encontre uma assinatura ativa. Selecione os três pontos (mais ações) e selecione **Cancelar assinatura**.
3. No painel **Cancelar assinatura**, escolha um motivo pelo qual você está cancelando. Se optar, forneça comentários.
4. Selecione **Salvar**.
5. Repita as etapas de 1 a 4 para cancelar todas as assinaturas ativas.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Etapa 3: Excluir todas as assinaturas desabilitadas

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.
2. Na guia **Produtos,** selecione uma assinatura desabilitada.
3. Na página detalhes da assinatura, na seção **Configurações de assinatura e** pagamento, selecione **Excluir assinatura**.
4. No painel **Excluir assinatura,** selecione **Excluir assinatura**.
5. Na caixa **de diálogo Excluir assinatura,** selecione **Sim**.
6. Para cada assinatura desabilitada, repita as etapas de 3 a 5 até que todas as assinaturas sejam excluídas.

> [!NOTE]
> Se você não puder excluir imediatamente uma assinatura desabilitada, [contate o suporte](../business-video/get-help-support.md).

## <a name="step-4-disable-multi-factor-authentication"></a>Etapa 4: Desabilitar a autenticação multifa factor

1. Entre no centro de administração com uma conta de administrador global. Para verificar quais funções você tem, consulte [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Vá para a **página Usuários**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">ativos.</a>
3. Escolha **Autenticação multifa factor**.
4. Na página de autenticação multifação, desabilite todas as contas, exceto a conta de administrador global que você está usando no momento.

Você também pode [usar o PowerShell para desabilitar a autenticação multifa factor para vários usuários](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Etapa 5: Excluir o diretório no Azure Active Directory

1. Entre no centro de <a href="https://aad.portal.azure.com/" target="_blank">administração do Azure AD</a> com uma conta de administrador global.
2. Selecione **Azure Active Directory**.
3. Alternar para a organização que você deseja excluir.
4. Selecione **Excluir locatário**.
5. Se sua organização falhar em uma ou mais verificações, você verá um link para mais informações sobre como passar as verificações. Depois de passar todas as verificações, selecione **Excluir** para concluir o processo.

Depois de concluir essa etapa final, sua conta com a Microsoft será fechada e excluída.

## <a name="related-content"></a>Conteúdo relacionado 

[Entenda sua fatura ou fatura para Microsoft 365 para empresas](./billing-and-payments/understand-your-invoice2.md) (artigo)\
[Cancelar sua assinatura](./subscriptions/cancel-your-subscription.md) (artigo)

