---
title: Pré-requisitos para contas de convidados
description: Diretrizes de configuração para contas de convidados e como ajustá-las
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574602"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="7bce8-104">Pré-requisitos para contas de convidados</span><span class="sxs-lookup"><span data-stu-id="7bce8-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="7bce8-105">A Área de Trabalho Gerenciada da Microsoft requer as seguintes configurações em sua organização do Azure AD para acesso à conta de convidado.</span><span class="sxs-lookup"><span data-stu-id="7bce8-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="7bce8-106">Você pode ajustar essas configurações no [portal do Azure](https://portal.azure.com) em **Identidades Externas / Colaboração externa**:</span><span class="sxs-lookup"><span data-stu-id="7bce8-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration**:</span></span>

-   <span data-ttu-id="7bce8-107">**Administradores e usuários na função de convidado convidado podem convidar definido** como **Sim**</span><span class="sxs-lookup"><span data-stu-id="7bce8-107">**Admins and users in the guest inviter role can invite** set to **Yes**</span></span>
-   <span data-ttu-id="7bce8-108">Para **restrições de** colaboração, escolha qualquer uma dessas opções:</span><span class="sxs-lookup"><span data-stu-id="7bce8-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="7bce8-109">Se você selecionar Permitir que convites sejam enviados para **qualquer domínio (mais inclusivo),** nenhuma outra configuração será necessária.</span><span class="sxs-lookup"><span data-stu-id="7bce8-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="7bce8-110">Se você selecionar Negar convites para **os domínios especificados,** certifique-se de Microsoft.com não está listado nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="7bce8-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="7bce8-111">Se você selecionar Permitir convites somente para os **domínios especificados (mais restritivos),** certifique-se de Microsoft.com *está* listado nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="7bce8-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="7bce8-112">Se você definir restrições que interagem com essas configurações, certifique-se de excluir as Contas de Serviço de Local de Trabalho Modernas **do** Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7bce8-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="7bce8-113">Por exemplo, se você tiver uma política de acesso condicional que impeça que  contas de convidado acessem o portal do Intune, exclua o grupo Contas de Serviço de Trabalho Moderno dessa política.</span><span class="sxs-lookup"><span data-stu-id="7bce8-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="7bce8-114">Etapas para se preparar</span><span class="sxs-lookup"><span data-stu-id="7bce8-114">Steps to get ready</span></span>

1. <span data-ttu-id="7bce8-115">Revise [os pré-requisitos da Área de Trabalho Gerenciada da Microsoft.](prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="7bce8-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="7bce8-116">Use [ferramentas de avaliação de preparação.](readiness-assessment-tool.md)</span><span class="sxs-lookup"><span data-stu-id="7bce8-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="7bce8-117">[Pré-requisitos para contas de convidado](guest-accounts.md) (Este artigo)</span><span class="sxs-lookup"><span data-stu-id="7bce8-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="7bce8-118">Configuração de rede na Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bce8-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="7bce8-119">Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bce8-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="7bce8-120">Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bce8-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="7bce8-121">Aplicativos na Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bce8-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="7bce8-122">Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bce8-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="7bce8-123">Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7bce8-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)