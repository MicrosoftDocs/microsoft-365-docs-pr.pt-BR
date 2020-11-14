---
title: Pré-requisitos para contas de convidados
description: Diretrizes de configuração para contas de convidado e como ajustá-las
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073184"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="0f9f9-104">Pré-requisitos para contas de convidados</span><span class="sxs-lookup"><span data-stu-id="0f9f9-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="0f9f9-105">A área de trabalho gerenciada da Microsoft exige as seguintes configurações na organização do Azure AD para acesso à conta de convidado.</span><span class="sxs-lookup"><span data-stu-id="0f9f9-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="0f9f9-106">Você pode ajustar essas configurações no [portal do Azure](https://portal.azure.com) em **identidades externas/colaboração externa** :</span><span class="sxs-lookup"><span data-stu-id="0f9f9-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration** :</span></span>

-   <span data-ttu-id="0f9f9-107">**Administradores e usuários na função convite de convidado podem convidar** definido como **Sim**</span><span class="sxs-lookup"><span data-stu-id="0f9f9-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="0f9f9-108">Para as **restrições de colaboração** , escolha uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="0f9f9-108">For **Collaboration restrictions** , choose any of these options:</span></span>
    -   <span data-ttu-id="0f9f9-109">Se você selecionar **permitir que os convites sejam enviados para qualquer domínio (mais inclusivo)** , nenhuma outra configuração necessária.</span><span class="sxs-lookup"><span data-stu-id="0f9f9-109">If you select **Allow invitations to be sent to any domain (most inclusive)** , no other configuration required.</span></span>
    -   <span data-ttu-id="0f9f9-110">Se você selecionar **negar convites para os domínios especificados** , certifique-se de que o Microsoft.com não esteja listado nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="0f9f9-110">If you select **Deny invitations to the specified domains** , make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="0f9f9-111">Se você selecionar **permitir convites somente para os domínios especificados (mais restritivo)** , certifique-se de que o Microsoft.com *está* listado nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="0f9f9-111">If you select **Allow invitations only to the specified domains (most restrictive)** , make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="0f9f9-112">Se você definir restrições que interagem com essas configurações, certifique-se de excluir as **contas do serviço de local de trabalho moderno** do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f9f9-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="0f9f9-113">Por exemplo, se você tem uma política de acesso condicional que impede que as contas de convidados acessem o portal do Intune, exclua o grupo de **contas de serviço de local de trabalho moderno** desta política.</span><span class="sxs-lookup"><span data-stu-id="0f9f9-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

