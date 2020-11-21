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
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376312"
---
# <a name="close-your-account"></a>Fechar sua conta

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Quando você fecha a sua conta do Microsoft, todas as informações relacionadas à sua conta são excluídas. Essas informações incluem assinaturas, licenças, métodos de pagamento, usuários e dados do usuário.

## <a name="before-you-begin"></a>Antes de começar

Antes de iniciar esse processo, faça backup dos dados que queira preservar.

Você deve ser um administrador global ou de cobrança para realizar as tarefas neste artigo. Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).

## <a name="step-1-delete-users"></a>Etapa 1: excluir usuários

Exclua todos os usuários, exceto um administrador global. O administrador global conclui as etapas para fechar a conta. Para poder excluir o diretório no final desse processo, você deve excluir todos os outros usuários.

Se os usuários forem sincronizados no local, primeiro desative a sincronização e exclua os usuários no diretório de nuvem usando o portal do Azure ou cmdlets do Azure PowerShell.

Para excluir usuários, consulte <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">administrador de gerenciamento de usuário: excluir um ou mais usuários</a>.

Você também pode usar o cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> do PowerShell para excluir usuários em massa.

Se sua organização usa o Active Directory que sincroniza com o Active Directory do Microsoft Azure (Azure AD), exclua a conta de usuário do Active Directory. Para obter instruções, consulte <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">exclusão em massa de usuários no Azure Active Directory</a>.

## <a name="step-2-cancel-all-active-subscriptions"></a>Etapa 2: cancelar todas as assinaturas ativas

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **produtos** , encontre uma assinatura ativa. Selecione **Mais ações** (três pontos) e, em seguida, selecione **Cancelar assinatura**.
3. No painel **Cancelar assinatura**, escolha um motivo pelo qual você está cancelando. Opcionalmente, forneça qualquer comentário.
4. Selecione **Salvar**.
5. Repita as etapas 1 a 4 para cancelar todas as assinaturas ativas.

## <a name="step-3-delete-all-disabled-subscriptions"></a>Etapa 3: excluir todas as assinaturas desabilitadas

1. No centro de administração, acesse a página **Cobrança de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">seus produtos</a>.
2. Na guia **produtos** , selecione uma assinatura desabilitada.
3. Na página detalhes da assinatura, na seção **configurações de assinatura e pagamento** , selecione **excluir assinatura**.
4. No painel **excluir assinatura** , selecione **excluir assinatura**.
5. Na caixa de diálogo **excluir inscrição** , selecione **Sim**.
6. Para cada assinatura desabilitada, repita as etapas de 3 a 5 até que todas as assinaturas sejam excluídas.

> [!NOTE]
> Se não for possível excluir imediatamente uma assinatura desabilitada, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contate o suporte</a>

## <a name="step-4-disable-multi-factor-authentication"></a>Etapa 4: desabilitar a autenticação multifator

1. Entre no centro de administração com uma conta de administrador global. Para verificar quais funções você tem, confira [verificar funções de administrador em sua organização](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).
2. Vá para a **Users**  >  página <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">usuários ativos</a> do usuário.
3. Escolha a **autenticação multifator**.
4. Na página autenticação multifator, desabilite todas as contas, exceto para a conta de administrador global que você está usando no momento.

Você também pode <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">usar o PowerShell para desabilitar a autenticação multifator para vários usuários</a>.

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a>Etapa 5: excluir o diretório no Azure Active Directory

1. Entre no centro de <a href="https://aad.portal.azure.com/" target="_blank">Administração do Azure ad</a> com uma conta de administrador global.
2. Selecione **Azure Active Directory**.
3. Alterne para a organização que você deseja excluir.
4. Selecione **excluir locatário**.
5. Se sua organização falhar em uma ou mais verificações, você verá um link para obter mais informações sobre como passar as verificações. Depois de passar em todas as verificações, selecione **excluir** para concluir o processo.

Após concluir esta etapa final, sua conta com a Microsoft será fechada e excluída.