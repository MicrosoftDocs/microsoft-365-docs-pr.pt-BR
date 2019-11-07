---
title: Noções básicas sobre alocação
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- commerce
ms.custom: ''
description: Saiba mais sobre o novo recurso de alocações.
ms.openlocfilehash: 3414fce02844629826edc6d9474f746aa27cfa2e
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012438"
---
# <a name="allotment-basics"></a><span data-ttu-id="bf3aa-103">Noções básicas sobre alocação</span><span class="sxs-lookup"><span data-stu-id="bf3aa-103">Allotment basics</span></span>

<span data-ttu-id="bf3aa-104">As alocações de licença permitem definir limites de licença e delegar o gerenciamento da atribuição de licença somente para os produtos e limites de licença que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="bf3aa-105">As alocações usam o licenciamento baseado em grupo para atribuir licenças aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="bf3aa-106">Os limites de licença fornecem controle adicionado sobre quantas licenças são atribuídas aos usuários em seus grupos.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="bf3aa-107">Assim, mesmo que o número de usuários nos seus grupos aumente, você pode se manter dentro do limite de licenças definido para a sua alocação.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="bf3aa-108">Você também pode delegar o gerenciamento de suas alocações.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="bf3aa-109">Os proprietários de alocação delegados obtêm acesso ao centro de administração, mas só podem ver e gerenciar as licenças nas alocações que possuem.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="bf3aa-110">Isso fornece uma delegação mais granular do gerenciamento de licenças dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf3aa-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bf3aa-111">Prerequisites</span></span>

<span data-ttu-id="bf3aa-112">Você deve atender aos requisitos de licenciamento para [Licenciamento baseado em grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="bf3aa-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="bf3aa-113">Você pode usar alocações com qualquer produto do Office 365 disponível para os usuários:</span><span class="sxs-lookup"><span data-stu-id="bf3aa-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="bf3aa-114">Pacotes do Office e produtos autônomos</span><span class="sxs-lookup"><span data-stu-id="bf3aa-114">Office suites and standalone products</span></span>
- <span data-ttu-id="bf3aa-115">Produtos corporativos e de mobilidade</span><span class="sxs-lookup"><span data-stu-id="bf3aa-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="bf3aa-116">Produtos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bf3aa-116">Dynamics 365 products</span></span>

<span data-ttu-id="bf3aa-117">Os seguintes produtos não podem ser usados com alocações:</span><span class="sxs-lookup"><span data-stu-id="bf3aa-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="bf3aa-118">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="bf3aa-118">Microsoft Store apps</span></span>
- <span data-ttu-id="bf3aa-119">Software permanente ou software que é atribuído diretamente a um usuário se não houver licença envolvida.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="bf3aa-120">Recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="bf3aa-120">Azure resources</span></span>

<span data-ttu-id="bf3aa-121">Você deve ser um administrador global ou de licença para começar a usar uma alocação.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="bf3aa-122">Introdução</span><span class="sxs-lookup"><span data-stu-id="bf3aa-122">Getting started</span></span>

<span data-ttu-id="bf3aa-123">O recurso de alocações está disponível em uma visualização privada para apenas um pequeno número de clientes.</span><span class="sxs-lookup"><span data-stu-id="bf3aa-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="bf3aa-124">Se você estiver interessado em ingressar, preencha este formulário:[https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)</span><span class="sxs-lookup"><span data-stu-id="bf3aa-124">If you are interested in joining, please fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup)</span></span>