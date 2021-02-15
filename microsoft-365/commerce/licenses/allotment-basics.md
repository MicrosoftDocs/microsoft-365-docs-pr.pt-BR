---
title: Noções básicas sobre a adoção
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
description: Saiba mais sobre o novo recurso de allotments.
ms.openlocfilehash: 2ab8efd637bb278faf6065559cab26cb7016975b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638226"
---
# <a name="allotment-basics"></a><span data-ttu-id="0712b-103">Noções básicas sobre a adoção</span><span class="sxs-lookup"><span data-stu-id="0712b-103">Allotment basics</span></span>

<span data-ttu-id="0712b-104">As licenças permitem definir limites de licença e delegar o gerenciamento da atribuição de licença apenas para os produtos e limites de licença selecionados.</span><span class="sxs-lookup"><span data-stu-id="0712b-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="0712b-105">As atribuição usam licenciamento baseado em grupo para atribuir licenças a seus usuários.</span><span class="sxs-lookup"><span data-stu-id="0712b-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="0712b-106">Os limites de licença fornecem controle adicional sobre quantas licenças são atribuídas aos usuários em seus grupos.</span><span class="sxs-lookup"><span data-stu-id="0712b-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="0712b-107">Portanto, mesmo à medida que o número de usuários em seus grupos aumenta, você pode garantir que permaneça dentro do limite de licença definido para sua adoção.</span><span class="sxs-lookup"><span data-stu-id="0712b-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="0712b-108">Você também pode delegar o gerenciamento de suas a allotments.</span><span class="sxs-lookup"><span data-stu-id="0712b-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="0712b-109">Os proprietários de loteamento delegados têm acesso ao centro de administração, mas só podem ver e gerenciar as licenças nas suas próprias licenças.</span><span class="sxs-lookup"><span data-stu-id="0712b-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="0712b-110">Isso fornece delegação mais granular do gerenciamento de licenças em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0712b-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0712b-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0712b-111">Prerequisites</span></span>

<span data-ttu-id="0712b-112">Você deve atender aos requisitos de licenciamento para [licenciamento baseado em grupo.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="0712b-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="0712b-113">Você pode usar a allotments com qualquer produto disponível para os usuários:</span><span class="sxs-lookup"><span data-stu-id="0712b-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="0712b-114">Office suites and standalone products</span><span class="sxs-lookup"><span data-stu-id="0712b-114">Office suites and standalone products</span></span>
- <span data-ttu-id="0712b-115">Produtos Enterprise e Mobility</span><span class="sxs-lookup"><span data-stu-id="0712b-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="0712b-116">Produtos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0712b-116">Dynamics 365 products</span></span>

<span data-ttu-id="0712b-117">Os produtos a seguir não podem ser usados com a allotments:</span><span class="sxs-lookup"><span data-stu-id="0712b-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="0712b-118">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="0712b-118">Microsoft Store apps</span></span>
- <span data-ttu-id="0712b-119">Software permanente ou software que é atribuído diretamente a um usuário se não houver nenhuma licença envolvida.</span><span class="sxs-lookup"><span data-stu-id="0712b-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="0712b-120">Recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="0712b-120">Azure resources</span></span>

<span data-ttu-id="0712b-121">Você deve ser um administrador global ou de licença para começar a trabalhar com uma adoção.</span><span class="sxs-lookup"><span data-stu-id="0712b-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="0712b-122">Introdução</span><span class="sxs-lookup"><span data-stu-id="0712b-122">Getting started</span></span>

<span data-ttu-id="0712b-123">O recurso de allotments está disponível em uma visualização privada para apenas um pequeno número de clientes.</span><span class="sxs-lookup"><span data-stu-id="0712b-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="0712b-124">Se você estiver interessado em ingressar, preencha este formulário: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="0712b-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
