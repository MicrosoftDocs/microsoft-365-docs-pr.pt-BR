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
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="7e3c4-104">Pré-requisitos para contas de convidados</span><span class="sxs-lookup"><span data-stu-id="7e3c4-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="7e3c4-105">A Área de Trabalho Gerenciada da Microsoft requer as seguintes configurações em sua organização do Azure AD para acesso à conta de convidado.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="7e3c4-106">Você pode ajustar essas configurações no [portal do Azure em](https://portal.azure.com) Identidades **Externas/Colaboração externa:**</span><span class="sxs-lookup"><span data-stu-id="7e3c4-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="7e3c4-107">**Administradores e usuários na função de convidado convidado podem convidar definido** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="7e3c4-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="7e3c4-108">Para **restrições de** colaboração, escolha qualquer uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="7e3c4-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="7e3c4-109">Se você selecionar Permitir que convites sejam enviados para qualquer domínio **(mais inclusivo),** nenhuma outra configuração é necessária.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="7e3c4-110">Se você selecionar Negar convites para os **domínios especificados,** certifique-se de Microsoft.com não está listado nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="7e3c4-111">Se você selecionar Permitir convites apenas para os  **domínios especificados (mais restritivos),** certifique-se de Microsoft.com listados nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="7e3c4-112">Se você definir restrições que interagem com essas configurações, certifique-se de excluir as contas do Serviço de Local de Trabalho **Moderno** do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="7e3c4-113">Por exemplo, se você tiver uma política de acesso condicional que impeça contas de convidado de acessar o portal do Intune, exclua o grupo Contas de Serviço do **Local** de Trabalho Moderno dessa política.</span><span class="sxs-lookup"><span data-stu-id="7e3c4-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

