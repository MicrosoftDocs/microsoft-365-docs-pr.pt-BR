---
title: Configurar usuários e casos na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: Saiba como configurar funções de usuário, criar ocorrências e atribuir usuários a casos na descoberta eletrônica avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e24354960b517815bef3cf498822d6ce9fd9dbe
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936738"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="e2df4-103">Configurar usuários e casos na descoberta eletrônica avançada (clássico)</span><span class="sxs-lookup"><span data-stu-id="e2df4-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="e2df4-104">Este tópico descreve como configurar usuários e casos para descoberta eletrônica avançada (clássica).</span><span class="sxs-lookup"><span data-stu-id="e2df4-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e2df4-105">À medida que continuamos investindo em versões mais recentes da Descoberta Eletrônica Avançada, anunciamos a retirada da Descoberta Eletrônica Avançada, também conhecida como *Descoberta Eletrônica Avançada (clássica)* ou *Descoberta Eletrônica Avançada v1.0*.</span><span class="sxs-lookup"><span data-stu-id="e2df4-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="e2df4-106">Se você ainda estiver usando a Descoberta Eletrônica Avançada v1.0, faça a transição para o [Descoberta Eletrônica Avançada v2.0](overview-ediscovery-20.md) (também conhecida como \* solução de Descoberta Eletrônica Avançada no Microsoft 365\*) o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="e2df4-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="e2df4-107">O Descoberta Eletrônica Avançada 2.0 contém funcionalidade semelhante encontrada na Descoberta Eletrônica Avançada v1.0, mas também oferece muitos recursos novos, como gerenciamento de custódia, gerenciamento de comunicações e conjuntos de revisão.</span><span class="sxs-lookup"><span data-stu-id="e2df4-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="e2df4-108">Para saber mais sobre a desativação da Descoberta Eletrônica Avançada v1.0, confira [Desativação de ferramentas legadas de Descoberta Eletrônica](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="e2df4-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="requirements-to-set-up-users-and-cases"></a><span data-ttu-id="e2df4-109">Requisitos para configurar usuários e casos</span><span class="sxs-lookup"><span data-stu-id="e2df4-109">Requirements to set up users and cases</span></span>

<span data-ttu-id="e2df4-110">Antes de configurar casos e usuários na descoberta eletrônica avançada, é necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e2df4-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="e2df4-111">Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="e2df4-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="e2df4-112">Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="e2df4-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="e2df4-113">Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5.</span><span class="sxs-lookup"><span data-stu-id="e2df4-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="e2df4-114">Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de &amp; conformidade de segurança para criar um caso de descoberta eletrônica e adicionar membros a ela.</span><span class="sxs-lookup"><span data-stu-id="e2df4-114">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="e2df4-115">Para se adicionar ao grupo de funções Gerenciador de descoberta eletrônica no centro de conformidade de segurança &amp; , você precisa ser um administrador global em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2df4-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your organization.</span></span> <span data-ttu-id="e2df4-116">Se você não for um administrador global, será necessário pedir a um administrador global para adicioná-lo ao grupo de funções Gerenciador de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="e2df4-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="e2df4-117">Para saber mais, veja:</span><span class="sxs-lookup"><span data-stu-id="e2df4-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="e2df4-118">Permissões no centro de conformidade de segurança do Microsoft 365 &amp;</span><span class="sxs-lookup"><span data-stu-id="e2df4-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="e2df4-119">Atribuir permissões de descoberta eletrônica no centro de conformidade de segurança do Microsoft 365 &amp;</span><span class="sxs-lookup"><span data-stu-id="e2df4-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="e2df4-120">Etapa 1: atribuir permissões de descoberta eletrônica de usuários</span><span class="sxs-lookup"><span data-stu-id="e2df4-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="e2df4-121">A primeira etapa é atribuir aos usuários as permissões de requisito no centro de conformidade de segurança &amp; para que eles possam ser adicionados como um membro de uma ocorrência de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="e2df4-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="e2df4-122">Após um usuário ser adicionado como um membro de um caso no centro de &amp; conformidade de segurança, ele poderá acessar o caso na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="e2df4-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="e2df4-123">Para atribuir a um usuário as permissões necessárias para que possam ser adicionadas como um membro de um caso de descoberta eletrônica, confira a etapa 1 em [casos de descoberta eletrônica no &amp; centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="e2df4-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="e2df4-124">Etapa 2: criar um caso de descoberta eletrônica e adicionar membros</span><span class="sxs-lookup"><span data-stu-id="e2df4-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="e2df4-125">A próxima etapa é criar uma nova ocorrência de descoberta eletrônica no centro de conformidade & segurança e adicionar membros.</span><span class="sxs-lookup"><span data-stu-id="e2df4-125">The next step is to create a new eDiscovery case in the Security & Compliance Center and add members.</span></span> <span data-ttu-id="e2df4-126">Os membros do caso serão capazes de acessar o caso na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="e2df4-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="e2df4-127">Para criar uma nova ocorrência de descoberta eletrônica, confira a etapa 3 em introdução [à descoberta eletrônica Core](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span><span class="sxs-lookup"><span data-stu-id="e2df4-127">To create a new eDiscovery case, see Step 3 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case).</span></span>

2. <span data-ttu-id="e2df4-128">Para adicionar membros a um caso de descoberta eletrônica, confira a etapa 4 em introdução [à descoberta eletrônica principal](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span><span class="sxs-lookup"><span data-stu-id="e2df4-128">To add members to an eDiscovery case, see Step 4 in [Get started with Core eDiscovery](get-started-core-ediscovery.md#step-4-optional-add-members-to-a-core-ediscovery-case)</span></span>

## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="e2df4-129">Etapa 3: usar uma descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="e2df4-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="e2df4-130">Após criar um caso de descoberta eletrônica e adicionar membros, você (ou qualquer membro do caso) pode acessar o caso correspondente na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="e2df4-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="e2df4-131">Para acessar um caso na descoberta eletrônica avançada, consulte [acessando um caso na descoberta eletrônica avançada](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="e2df4-131">To access a case in Advanced eDiscovery, see [Accessing a case in Advanced eDiscovery](quick-setup-for-advanced-ediscovery.md#accessing-a-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e2df4-132">Também consulte</span><span class="sxs-lookup"><span data-stu-id="e2df4-132">See also</span></span>

[<span data-ttu-id="e2df4-133">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="e2df4-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e2df4-134">Preparando dados para descoberta eletrônica avançada (clássico)</span><span class="sxs-lookup"><span data-stu-id="e2df4-134">Preparing data for Advanced eDiscovery (classic)</span></span>](prepare-data-for-advanced-ediscovery.md)
 
