---
title: Fechar sua conta
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
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Saiba como fechar sua conta com a Microsoft.
ms.openlocfilehash: 19e9a92a90f7c88cc150844ab451bc71d63e4c4a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911657"
---
# <a name="close-your-account"></a>Fechar sua conta

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

Quando você fecha a sua conta do Microsoft, todas as informações relacionadas à sua conta são excluídas. Essas informações incluem assinaturas, licenças, métodos de pagamento, usuários e dados do usuário.

## <a name="before-you-begin"></a>Antes de começar

Antes de iniciar esse processo, faça backup dos dados que queira preservar.

Você deve ser um administrador Global ou de Cobrança para realizar as etapas descritas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Etapa 1: Excluir usuários

Exclua todos os usuários, exceto um administrador global. O administrador global conclui as etapas para fechar a conta. Antes de poder excluir o diretório no final deste processo, você deve excluir todos os outros usuários.

Se os usuários estiverem sincronizados no local, primeiro desligue a sincronização e exclua os usuários no diretório de nuvem usando o portal do Azure ou os cmdlets do Azure PowerShell.

Para excluir usuários, consulte <a href="/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.

Você também pode usar o cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell para excluir usuários em massa.

Se sua organização usa o Active Directory que se sincroniza com o Microsoft Azure Active Directory (Azure AD), exclua a conta de usuário do Active Directory, em vez disso. Para obter instruções, consulte <a href="/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Etapa 2: Cancelar todas as assinaturas ativas

1. No centro de administração, acesse a página **Cobrança** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus produtos</a>.
2. Na guia **Produtos,** encontre uma assinatura ativa. Selecione **Mais ações** (três pontos) e, em seguida, selecione **Cancelar assinatura**.
3. No painel **Cancelar assinatura**, escolha um motivo pelo qual você está cancelando. Opcionalmente, forneça qualquer comentário.
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
> Se você não puder excluir imediatamente uma assinatura desabilitada, <a href="/microsoft-365/Admin/contact-support-for-business-products" target="_blank">contate o suporte</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Etapa 4: Desabilitar a autenticação multifa factor

1. Entre no centro de administração com uma conta de administrador global. Para verificar quais funções você tem, consulte [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Vá para a **página Usuários**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">ativos.</a>
3. Escolha **Autenticação multifa factor**.
4. Na página de autenticação multifação, desabilite todas as contas, exceto a conta de administrador global que você está usando no momento.

Você também pode <a href="/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">usar o PowerShell para desabilitar a autenticação multifa factor para vários usuários</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Etapa 5: Excluir o diretório no Azure Active Directory

1. Entre no centro de <a href="https://aad.portal.azure.com/" target="_blank">administração do Azure AD</a> com uma conta de administrador global.
2. Selecione **Azure Active Directory**.
3. Alternar para a organização que você deseja excluir.
4. Selecione **Excluir locatário**.
5. Se sua organização falhar em uma ou mais verificações, você verá um link para mais informações sobre como passar as verificações. Depois de passar todas as verificações, selecione **Excluir** para concluir o processo.

Depois de concluir essa etapa final, sua conta com a Microsoft será fechada e excluída.