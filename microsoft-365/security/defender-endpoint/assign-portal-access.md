---
title: Atribuir acesso do usuário ao Centro de Segurança do Microsoft Defender
description: Atribua acesso somente leitura e gravação ou leitura ao portal do Microsoft Defender para Ponto de Extremidade.
keywords: atribuir funções de usuário, atribuir acesso de leitura e gravação, atribuir acesso somente leitura, usuário, funções de usuário, funções
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164741"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a><span data-ttu-id="4ec59-104">Atribuir acesso do usuário ao Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ec59-104">Assign user access to Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4ec59-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4ec59-105">**Applies to:**</span></span>
- <span data-ttu-id="4ec59-106">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4ec59-106">Azure Active Directory</span></span>
- <span data-ttu-id="4ec59-107">Office 365</span><span class="sxs-lookup"><span data-stu-id="4ec59-107">Office 365</span></span>
- [<span data-ttu-id="4ec59-108">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4ec59-108">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4ec59-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4ec59-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="4ec59-110">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4ec59-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4ec59-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4ec59-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="4ec59-112">O Defender para Ponto de Extremidade oferece suporte a duas maneiras de gerenciar permissões:</span><span class="sxs-lookup"><span data-stu-id="4ec59-112">Defender for Endpoint supports two ways to manage permissions:</span></span>

- <span data-ttu-id="4ec59-113">**Gerenciamento de permissões básicas**: definir permissões para acesso total ou somente leitura.</span><span class="sxs-lookup"><span data-stu-id="4ec59-113">**Basic permissions management**: Set permissions to either full access or read-only.</span></span>
- <span data-ttu-id="4ec59-114">Controle de acesso baseado em função **(RBAC)**: definir permissões granulares definindo funções, atribuindo grupos de usuários do Azure AD às funções e concedendo aos grupos de usuários acesso a grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4ec59-114">**Role-based access control (RBAC)**: Set granular permissions by defining roles, assigning Azure AD user groups to the roles, and granting the user groups access to device groups.</span></span> <span data-ttu-id="4ec59-115">Para obter mais informações sobre o RBAC, consulte [Manage portal access using role-based access control](rbac.md).</span><span class="sxs-lookup"><span data-stu-id="4ec59-115">For more information on RBAC, see [Manage portal access using role-based access control](rbac.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4ec59-116">Se você já tiver atribuído permissões básicas, poderá alternar para o RBAC a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="4ec59-116">If you have already assigned basic permissions, you may switch to RBAC anytime.</span></span> <span data-ttu-id="4ec59-117">Considere o seguinte antes de fazer a opção:</span><span class="sxs-lookup"><span data-stu-id="4ec59-117">Consider the following before making the switch:</span></span>
> 
> - <span data-ttu-id="4ec59-118">Os usuários com acesso total (usuários atribuídos à função de diretório Administrador Global ou Administrador de Segurança no Azure AD) são atribuídos automaticamente à função de administrador padrão do Defender para Ponto de Extremidade, que também tem acesso total.</span><span class="sxs-lookup"><span data-stu-id="4ec59-118">Users with full access (users that are assigned the Global Administrator or Security Administrator directory role in Azure AD), are automatically assigned the default Defender for Endpoint administrator role, which also has full access.</span></span> <span data-ttu-id="4ec59-119">Grupos de usuários adicionais do Azure AD podem ser atribuídos à função de administrador do Defender for Endpoint após alternar para RBAC.</span><span class="sxs-lookup"><span data-stu-id="4ec59-119">Additional Azure AD user groups can be assigned to the Defender for Endpoint administrator role after switching to RBAC.</span></span>  <span data-ttu-id="4ec59-120">Somente os usuários atribuídos à função de administrador do Defender for Endpoint podem gerenciar permissões usando o RBAC.</span><span class="sxs-lookup"><span data-stu-id="4ec59-120">Only users assigned to the Defender for Endpoint administrator role can manage permissions using RBAC.</span></span> 
> - <span data-ttu-id="4ec59-121">Os usuários que têm acesso somente leitura (Leitores de Segurança) perderão acesso ao portal até receberem uma função.</span><span class="sxs-lookup"><span data-stu-id="4ec59-121">Users that have read-only access (Security Readers) will lose access to the portal until they are assigned a role.</span></span> <span data-ttu-id="4ec59-122">Observe que somente grupos de usuários do Azure AD podem ser atribuídos a uma função em RBAC.</span><span class="sxs-lookup"><span data-stu-id="4ec59-122">Note that only Azure AD user groups can be assigned a role under RBAC.</span></span>
> - <span data-ttu-id="4ec59-123">Depois de alternar para o RBAC, você não poderá voltar a usar o gerenciamento de permissões básicas.</span><span class="sxs-lookup"><span data-stu-id="4ec59-123">After switching to RBAC, you will not be able to switch back to using basic permissions management.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4ec59-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4ec59-124">Related topics</span></span>

- [<span data-ttu-id="4ec59-125">Usar permissões básicas para acessar o portal</span><span class="sxs-lookup"><span data-stu-id="4ec59-125">Use basic permissions to access the portal</span></span>](basic-permissions.md)
- [<span data-ttu-id="4ec59-126">Gerenciar o acesso ao portal usando o RBAC</span><span class="sxs-lookup"><span data-stu-id="4ec59-126">Manage portal access using RBAC</span></span>](rbac.md)
