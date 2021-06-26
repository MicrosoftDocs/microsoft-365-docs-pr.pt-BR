---
title: Saiba mais sobre a política padrão de prevenção contra perda de dados no Microsoft Teams (visualização)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Saiba mais sobre a política de prevenção de perda de dados padrão Microsoft Teams
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149113"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a><span data-ttu-id="5680b-103">Saiba mais sobre a política padrão de prevenção contra perda de dados no Microsoft Teams (visualização)</span><span class="sxs-lookup"><span data-stu-id="5680b-103">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>

<span data-ttu-id="5680b-104">[Os recursos de prevenção](dlp-learn-about-dlp.md) contra perda de dados foram estendidos para incluir Microsoft Teams de chat e de canal, incluindo mensagens de canal privado.</span><span class="sxs-lookup"><span data-stu-id="5680b-104">[Data loss prevention](dlp-learn-about-dlp.md) capabilities have been extended to include Microsoft Teams chat and channel messages, including private channel messages.</span></span> <span data-ttu-id="5680b-105">Como parte dessa versão, criamos uma política de DLP padrão para Microsoft Teams clientes de primeira vez para o Centro de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="5680b-105">As a part of this release, we created a default DLP policy for Microsoft Teams for first-time customers to Compliance center.</span></span>

## <a name="applies-to"></a><span data-ttu-id="5680b-106">Aplicável a</span><span class="sxs-lookup"><span data-stu-id="5680b-106">Applies to</span></span>

<span data-ttu-id="5680b-107">Qualquer locatário licenciado com uma ou mais das licenças abaixo e que tenha usuários Teams ativos</span><span class="sxs-lookup"><span data-stu-id="5680b-107">Any tenant who is licensed with one or more of the below licenses and have active Teams users</span></span>
 
- <span data-ttu-id="5680b-108">ME5,</span><span class="sxs-lookup"><span data-stu-id="5680b-108">ME5,</span></span> 
- <span data-ttu-id="5680b-109">MA5,</span><span class="sxs-lookup"><span data-stu-id="5680b-109">MA5,</span></span> 
- <span data-ttu-id="5680b-110">Conformidade com e5/A5,</span><span class="sxs-lookup"><span data-stu-id="5680b-110">E5/A5 Compliance,</span></span> 
- <span data-ttu-id="5680b-111">IP+G,</span><span class="sxs-lookup"><span data-stu-id="5680b-111">IP+G,</span></span> 
- <span data-ttu-id="5680b-112">OE5,</span><span class="sxs-lookup"><span data-stu-id="5680b-112">OE5,</span></span> 
- <span data-ttu-id="5680b-113">Conformidade avançada do O365</span><span class="sxs-lookup"><span data-stu-id="5680b-113">O365 Advanced Compliance</span></span> 
- <span data-ttu-id="5680b-114">EMS E5</span><span class="sxs-lookup"><span data-stu-id="5680b-114">EMS E5</span></span>


## <a name="what-does-the-default-policy-do"></a><span data-ttu-id="5680b-115">O que a política padrão faz?</span><span class="sxs-lookup"><span data-stu-id="5680b-115">What does the default policy do?</span></span>

<span data-ttu-id="5680b-116">A política de DLP padrão para Teams rastreia todos os números de cartão de crédito compartilhados interna e externamente para a organização.</span><span class="sxs-lookup"><span data-stu-id="5680b-116">The default DLP policy for Teams tracks all the credit card numbers shared internally and externally to the organization.</span></span> <span data-ttu-id="5680b-117">Essa política está em uso por padrão para todos os usuários do locatário.</span><span class="sxs-lookup"><span data-stu-id="5680b-117">This policy is on by default for all users of the tenant.</span></span> <span data-ttu-id="5680b-118">Ele não gera dicas de política para usuários finais, mas gera um evento Alert e também dispara um email de baixa gravidade para o administrador (adicionado na política).</span><span class="sxs-lookup"><span data-stu-id="5680b-118">It does not generate any policy tips for end users but does generate an Alert event and also triggers a low severity email to the admin (added in the policy).</span></span> <span data-ttu-id="5680b-119">O administrador pode exibir as atividades e editar os detalhes das políticas fazendo logo em log no Centro de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="5680b-119">Administrator can view the activities and edit the policies details by logging into the Compliance center.</span></span>

<span data-ttu-id="5680b-120">Os administradores podem exibir essa política na página Centro de [Conformidade >](https://compliance.microsoft.com/compliancesettings) políticas de prevenção contra perda de dados.</span><span class="sxs-lookup"><span data-stu-id="5680b-120">Admins can view this policy in the [Compliance center](https://compliance.microsoft.com/compliancesettings) > Data Loss prevention policies page.</span></span>


> [!div class="mx-imgBorder"]
> <span data-ttu-id="5680b-121">![política Teams DLP padrão](../media/default-teams-dlp-policy.png)</span><span class="sxs-lookup"><span data-stu-id="5680b-121">![default Teams DLP policy](../media/default-teams-dlp-policy.png)</span></span>

## <a name="edit-or-delete-the-default-policy"></a><span data-ttu-id="5680b-122">Editar ou excluir a política padrão</span><span class="sxs-lookup"><span data-stu-id="5680b-122">Edit or delete the default policy</span></span>

<span data-ttu-id="5680b-123">Para editar a política padrão para melhorar o desempenho ou [excluí-la,](create-test-tune-dlp-policy.md#tune-a-dlp-policy)basta usar uma conta com permissões de Gerenciamento de Conformidade de **DLP.**</span><span class="sxs-lookup"><span data-stu-id="5680b-123">To [edit the default policy for better performance or to delete it](create-test-tune-dlp-policy.md#tune-a-dlp-policy), just use an account with **DLP Compliance Management** permissions.</span></span> <span data-ttu-id="5680b-124">Para obter mais informações, consulte [Permissões](create-test-tune-dlp-policy.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="5680b-124">For more information, see, [Permissions](create-test-tune-dlp-policy.md#permissions).</span></span>

