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
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694240"
---
# <a name="prerequisites-for-guest-accounts"></a><span data-ttu-id="1be0a-104">Pré-requisitos para contas de convidados</span><span class="sxs-lookup"><span data-stu-id="1be0a-104">Prerequisites for guest accounts</span></span>

<span data-ttu-id="1be0a-105">Área de Trabalho Gerenciada da Microsoft requer as seguintes configurações em sua organização do Azure AD para acesso à conta de convidado.</span><span class="sxs-lookup"><span data-stu-id="1be0a-105">Microsoft Managed Desktop requires the following settings in your Azure AD organization for guest account access.</span></span> <span data-ttu-id="1be0a-106">Você pode ajustar essas configurações no [portal do Azure](https://portal.azure.com) em **Identidades Externas / Configurações de colaboração externa:**</span><span class="sxs-lookup"><span data-stu-id="1be0a-106">You can adjust these settings at the [Azure portal](https://portal.azure.com) under **External Identities / External collaboration settings**:</span></span>

-   <span data-ttu-id="1be0a-107">Para **restrições de convite de** convidado definidas para usuários membros e usuários atribuídos a funções de administrador específicas podem convidar usuários **convidados,** incluindo convidados com permissões de membro</span><span class="sxs-lookup"><span data-stu-id="1be0a-107">For **Guest invite restrictions** set to **Member users and users assigned to specific admin roles can invite guest users including guests with member permissions**</span></span>
-   <span data-ttu-id="1be0a-108">Para **restrições de** colaboração, escolha qualquer uma dessas opções:</span><span class="sxs-lookup"><span data-stu-id="1be0a-108">For **Collaboration restrictions**, choose any of these options:</span></span>
    -   <span data-ttu-id="1be0a-109">Se você selecionar Permitir que convites sejam enviados para **qualquer domínio (mais inclusivo),** nenhuma outra configuração será necessária.</span><span class="sxs-lookup"><span data-stu-id="1be0a-109">If you select **Allow invitations to be sent to any domain (most inclusive)**, no other configuration required.</span></span>
    -   <span data-ttu-id="1be0a-110">Se você selecionar Negar convites para **os domínios especificados,** certifique-se de Microsoft.com não está listado nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="1be0a-110">If you select **Deny invitations to the specified domains**, make sure that Microsoft.com isn’t listed in the target domains.</span></span>
    -   <span data-ttu-id="1be0a-111">Se você selecionar Permitir convites somente para os **domínios especificados (mais restritivos),** certifique-se de Microsoft.com *está* listado nos domínios de destino.</span><span class="sxs-lookup"><span data-stu-id="1be0a-111">If you select **Allow invitations only to the specified domains (most restrictive)**, make sure that Microsoft.com *is* listed in the target domains.</span></span>

<span data-ttu-id="1be0a-112">Se você definir restrições que interagem com essas configurações, certifique-se de excluir as Azure Active Directory Contas de Serviço de Local de **Trabalho Modernas.**</span><span class="sxs-lookup"><span data-stu-id="1be0a-112">If you set restrictions that interact with these settings, make sure to exclude the Azure Active Directory **Modern Workplace Service Accounts**.</span></span> <span data-ttu-id="1be0a-113">Por exemplo, se você tiver uma política de acesso condicional que impeça que  contas de convidado acessem o portal do Intune, exclua o grupo Contas de Serviço de Trabalho Moderno dessa política.</span><span class="sxs-lookup"><span data-stu-id="1be0a-113">For example, if you have a conditional access policy that prevents guest accounts from accessing the Intune portal, exclude the **Modern Workplace Service Accounts** group from this policy.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="1be0a-114">Etapas para se preparar</span><span class="sxs-lookup"><span data-stu-id="1be0a-114">Steps to get ready</span></span>

1. <span data-ttu-id="1be0a-115">Revise [pré-requisitos da Área de Trabalho Gerenciada da Microsoft](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="1be0a-115">Review [prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="1be0a-116">Use [de avaliação de preparação](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="1be0a-116">Use [readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. <span data-ttu-id="1be0a-117">[Pré-requisitos para contas de convidado](guest-accounts.md) (Este artigo)</span><span class="sxs-lookup"><span data-stu-id="1be0a-117">[Prerequisites for guest accounts](guest-accounts.md) (This article)</span></span>
4. [<span data-ttu-id="1be0a-118">Configuração de rede na Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1be0a-118">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="1be0a-119">Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1be0a-119">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="1be0a-120">Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1be0a-120">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="1be0a-121">Aplicativos na Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1be0a-121">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="1be0a-122">Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1be0a-122">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="1be0a-123">Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1be0a-123">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
