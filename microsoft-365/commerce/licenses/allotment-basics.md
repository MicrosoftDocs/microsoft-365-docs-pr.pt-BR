---
title: Noções básicas de loteamento
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
description: Saiba mais sobre o novo recurso de loteamentos.
ms.openlocfilehash: 62df346def3fd2577568916d2d668ca50542bdbd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911609"
---
# <a name="allotment-basics"></a><span data-ttu-id="62715-103">Noções básicas de loteamento</span><span class="sxs-lookup"><span data-stu-id="62715-103">Allotment basics</span></span>

<span data-ttu-id="62715-104">Os loteamentos de licença permitem definir limites de licença e delegar o gerenciamento da atribuição de licença apenas para os produtos e limites de licença selecionados.</span><span class="sxs-lookup"><span data-stu-id="62715-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="62715-105">Os loteamentos usam licenciamento baseado em grupo para atribuir licenças aos usuários.</span><span class="sxs-lookup"><span data-stu-id="62715-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="62715-106">Os limites de licença fornecem controle adicional sobre quantas licenças são atribuídas aos usuários em seus grupos.</span><span class="sxs-lookup"><span data-stu-id="62715-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="62715-107">Assim, mesmo à medida que o número de usuários em seus grupos aumenta, você pode garantir que você permaneça dentro do limite de licença definido para sua loteação.</span><span class="sxs-lookup"><span data-stu-id="62715-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="62715-108">Você também pode delegar o gerenciamento de suas loteamentos.</span><span class="sxs-lookup"><span data-stu-id="62715-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="62715-109">Os proprietários de loteamento delegados têm acesso ao centro de administração, mas só podem ver e gerenciar as licenças nos loteamentos que eles têm.</span><span class="sxs-lookup"><span data-stu-id="62715-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="62715-110">Isso fornece delegação mais granular do gerenciamento de licenças em sua organização.</span><span class="sxs-lookup"><span data-stu-id="62715-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="62715-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="62715-111">Prerequisites</span></span>

<span data-ttu-id="62715-112">Você deve atender aos requisitos de licenciamento para [licenciamento baseado em grupo.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="62715-112">You must meet the licensing requirements for [group-based licensing](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="62715-113">Você pode usar loteamentos com qualquer produto disponível para os usuários:</span><span class="sxs-lookup"><span data-stu-id="62715-113">You can use allotments with any product available to users:</span></span>

- <span data-ttu-id="62715-114">Pacote do Office e produtos autônomos</span><span class="sxs-lookup"><span data-stu-id="62715-114">Office suites and standalone products</span></span>
- <span data-ttu-id="62715-115">Produtos Enterprise e Mobility</span><span class="sxs-lookup"><span data-stu-id="62715-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="62715-116">Produtos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="62715-116">Dynamics 365 products</span></span>

<span data-ttu-id="62715-117">Os seguintes produtos não podem ser usados com loteamentos:</span><span class="sxs-lookup"><span data-stu-id="62715-117">The following products can't be used with allotments:</span></span>

- <span data-ttu-id="62715-118">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="62715-118">Microsoft Store apps</span></span>
- <span data-ttu-id="62715-119">Software perpétuo ou software que é atribuído diretamente a um usuário se não houver nenhuma licença envolvida.</span><span class="sxs-lookup"><span data-stu-id="62715-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="62715-120">Recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="62715-120">Azure resources</span></span>

<span data-ttu-id="62715-121">Você deve ser um administrador global ou de licença para começar com uma loteação.</span><span class="sxs-lookup"><span data-stu-id="62715-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="62715-122">Introdução</span><span class="sxs-lookup"><span data-stu-id="62715-122">Getting started</span></span>

<span data-ttu-id="62715-123">O recurso de loteamentos está disponível em uma visualização privada para apenas um pequeno número de clientes.</span><span class="sxs-lookup"><span data-stu-id="62715-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="62715-124">Se você estiver interessado em ingressar, preencha este formulário: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup) .</span><span class="sxs-lookup"><span data-stu-id="62715-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>