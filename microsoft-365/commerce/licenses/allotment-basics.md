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
ms.openlocfilehash: fff63b3c61ad95696e7f7677a34154ad65e82259
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753570"
---
# <a name="allotment-basics"></a><span data-ttu-id="8269f-103">Noções básicas sobre alocação</span><span class="sxs-lookup"><span data-stu-id="8269f-103">Allotment basics</span></span>

<span data-ttu-id="8269f-104">As alocações de licença permitem definir limites de licença e delegar o gerenciamento da atribuição de licença somente para os produtos e limites de licença que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="8269f-104">License allotments let you set license limits and delegate management of license assignment to only the products and license limits that you select.</span></span>

<span data-ttu-id="8269f-105">As alocações usam o licenciamento baseado em grupo para atribuir licenças aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="8269f-105">Allotments use group-based licensing to assign licenses to your users.</span></span> <span data-ttu-id="8269f-106">Os limites de licença fornecem controle adicionado sobre quantas licenças são atribuídas aos usuários em seus grupos.</span><span class="sxs-lookup"><span data-stu-id="8269f-106">License limits provide added control over how many licenses are assigned to the users in your groups.</span></span> <span data-ttu-id="8269f-107">Assim, mesmo que o número de usuários nos seus grupos aumente, você pode se manter dentro do limite de licenças definido para a sua alocação.</span><span class="sxs-lookup"><span data-stu-id="8269f-107">So even as the number of users in your groups increases, you can ensure that you stay within the license limit that you have set for your allotment.</span></span>

<span data-ttu-id="8269f-108">Você também pode delegar o gerenciamento de suas alocações.</span><span class="sxs-lookup"><span data-stu-id="8269f-108">You can also delegate management of your allotments.</span></span> <span data-ttu-id="8269f-109">Os proprietários de alocação delegados obtêm acesso ao centro de administração, mas só podem ver e gerenciar as licenças nas alocações que possuem.</span><span class="sxs-lookup"><span data-stu-id="8269f-109">Delegated allotment owners gain access to the admin center, but can only see and manage the licenses in the allotments they own.</span></span> <span data-ttu-id="8269f-110">Isso fornece uma delegação mais granular do gerenciamento de licenças dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="8269f-110">This provides more granular delegation of license management within your organization.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8269f-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8269f-111">Prerequisites</span></span>

<span data-ttu-id="8269f-112">Você deve atender aos requisitos de licenciamento para [Licenciamento baseado em grupo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="8269f-112">You must meet the licensing requirements for [group-based licensing](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal#licensing-requirements).</span></span>

<span data-ttu-id="8269f-113">Você pode usar alocações com qualquer produto do Office 365 disponível para os usuários:</span><span class="sxs-lookup"><span data-stu-id="8269f-113">You can use allotments with any Office 365 product available to users:</span></span>

- <span data-ttu-id="8269f-114">Pacotes do Office e produtos autônomos</span><span class="sxs-lookup"><span data-stu-id="8269f-114">Office suites and standalone products</span></span>
- <span data-ttu-id="8269f-115">Produtos corporativos e de mobilidade</span><span class="sxs-lookup"><span data-stu-id="8269f-115">Enterprise and Mobility products</span></span>
- <span data-ttu-id="8269f-116">Produtos do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8269f-116">Dynamics 365 products</span></span>

<span data-ttu-id="8269f-117">Os seguintes produtos não podem ser usados com alocações:</span><span class="sxs-lookup"><span data-stu-id="8269f-117">The following products can’t be used with allotments:</span></span>

- <span data-ttu-id="8269f-118">Aplicativos da Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8269f-118">Microsoft Store apps</span></span>
- <span data-ttu-id="8269f-119">Software permanente ou software que é atribuído diretamente a um usuário se não houver licença envolvida.</span><span class="sxs-lookup"><span data-stu-id="8269f-119">Perpetual software, or software that is directly assigned to a user if there is no license involved.</span></span>
- <span data-ttu-id="8269f-120">Recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="8269f-120">Azure resources</span></span>

<span data-ttu-id="8269f-121">Você deve ser um administrador global ou de licença para começar a usar uma alocação.</span><span class="sxs-lookup"><span data-stu-id="8269f-121">You must be a global or license admin to get started with an allotment.</span></span>

## <a name="getting-started"></a><span data-ttu-id="8269f-122">Introdução</span><span class="sxs-lookup"><span data-stu-id="8269f-122">Getting started</span></span>

<span data-ttu-id="8269f-123">O recurso de alocações está disponível em uma visualização privada para apenas um pequeno número de clientes.</span><span class="sxs-lookup"><span data-stu-id="8269f-123">The allotments feature is available in a private preview to only a small number of customers.</span></span> <span data-ttu-id="8269f-124">Se você estiver interessado em ingressar, preencha este formulário: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span><span class="sxs-lookup"><span data-stu-id="8269f-124">If you're interested in joining, fill out this form: [https://aka.ms/allotment-pilot-signup](https://aka.ms/allotment-pilot-signup).</span></span>
