---
title: Noções básicas de loteamento
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: micurn, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
description: Saiba mais sobre o novo recurso de loteamentos.
ms.date: 03/17/2021
ms.openlocfilehash: 0910673ce54f3f977ed8ecbc3d6c77ac2ebad0cc
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331689"
---
# <a name="allotment-basics"></a><span data-ttu-id="b7a41-103">Noções básicas de loteamento</span><span class="sxs-lookup"><span data-stu-id="b7a41-103">Allotment basics</span></span>

<span data-ttu-id="b7a41-104">Os loteamentos de licença permitem definir limites de licença e delegar o gerenciamento da atribuição de licença apenas para os produtos e limites de licença selecionados.</span><span class="sxs-lookup"><span data-stu-id="b7a41-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="b7a41-105">Os loteamentos usam licenciamento baseado em grupo para atribuir licenças aos usuários.</span><span class="sxs-lookup"><span data-stu-id="b7a41-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="b7a41-106">Os limites de licença fornecem controle adicional sobre quantas licenças são atribuídas aos usuários em seus grupos.</span><span class="sxs-lookup"><span data-stu-id="b7a41-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="b7a41-107">Assim, mesmo à medida que o número de usuários em seus grupos aumenta, você pode garantir que você permaneça dentro do limite de licença definido para sua loteação.</span><span class="sxs-lookup"><span data-stu-id="b7a41-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="b7a41-108">Você também pode delegar o gerenciamento de suas loteamentos.</span><span class="sxs-lookup"><span data-stu-id="b7a41-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="b7a41-109">Os proprietários de loteamento delegados têm acesso ao centro de administração, mas só podem ver e gerenciar as licenças nos loteamentos que eles têm.</span><span class="sxs-lookup"><span data-stu-id="b7a41-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="b7a41-110">Isso fornece delegação mais granular do gerenciamento de licenças em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b7a41-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b7a41-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b7a41-111">Prerequisites</span></span>

<span data-ttu-id="b7a41-112">Você deve atender aos requisitos de licenciamento para [licenciamento baseado em grupo.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="b7a41-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="b7a41-113">Você pode usar loteamentos com qualquer produto disponível para os usuários:</span><span class="sxs-lookup"><span data-stu-id="b7a41-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="b7a41-114">Office e produtos autônomos</span><span class="sxs-lookup"><span data-stu-id="b7a41-114">Office suites and standalone products</span></span>
- <span data-ttu-id="b7a41-115">Enterprise e produtos Mobility</span><span class="sxs-lookup"><span data-stu-id="b7a41-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="b7a41-116">Produtos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b7a41-116">Dynamics 365 products</span></span>

<span data-ttu-id="b7a41-117">Os seguintes produtos não podem ser usados com loteamentos:</span><span class="sxs-lookup"><span data-stu-id="b7a41-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="b7a41-118">Microsoft Store aplicativos</span><span class="sxs-lookup"><span data-stu-id="b7a41-118">Microsoft Store apps</span></span>
- <span data-ttu-id="b7a41-119">Software perpétuo ou software que é atribuído diretamente a um usuário se não houver nenhuma licença envolvida.</span><span class="sxs-lookup"><span data-stu-id="b7a41-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="b7a41-120">Recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="b7a41-120">Azure resources</span></span>

<span data-ttu-id="b7a41-121">Você deve ser um administrador global ou de licença para começar com uma loteação.</span><span class="sxs-lookup"><span data-stu-id="b7a41-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="b7a41-122">Introdução</span><span class="sxs-lookup"><span data-stu-id="b7a41-122">Getting started</span></span>

<span data-ttu-id="b7a41-123">O recurso de loteamentos está disponível em uma visualização privada para apenas um pequeno número de clientes.</span><span class="sxs-lookup"><span data-stu-id="b7a41-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="b7a41-124">Se você estiver interessado em ingressar, preencha este formulário: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="b7a41-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>