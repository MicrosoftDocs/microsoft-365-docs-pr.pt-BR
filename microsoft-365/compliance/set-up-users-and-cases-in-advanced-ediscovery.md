---
title: Configurar usuários e casos na descoberta eletrônica avançada do Office 365
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
description: 'Saiba como configurar funções de usuário, criar ocorrências e atribuir usuários a casos na descoberta eletrônica avançada do Office 365.  '
ms.openlocfilehash: 76d5e6ab503cc053e31811cc06ac12545a9eeb7e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557733"
---
# <a name="set-up-users-and-cases-in-advanced-ediscovery-classic"></a><span data-ttu-id="031f7-103">Configurar usuários e casos na descoberta eletrônica avançada (clássico)</span><span class="sxs-lookup"><span data-stu-id="031f7-103">Set up users and cases in Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="031f7-104">Este tópico descreve como configurar usuários e casos para descoberta eletrônica avançada (clássica).</span><span class="sxs-lookup"><span data-stu-id="031f7-104">This topic describes how to set up users and cases for Advanced eDiscovery (classic).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="031f7-105">Como continuamos a investir em versões mais recentes da descoberta eletrônica avançada, anunciamos a desativação da descoberta eletrônica avançada do Office 365, também conhecida como *descoberta eletrônica avançada (clássica)* ou *descoberta eletrônica avançada v 1.0*.</span><span class="sxs-lookup"><span data-stu-id="031f7-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Office 365 Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="031f7-106">Se você ainda estiver usando a Descoberta Eletrônica Avançada v1.0, faça a transição para o [Descoberta Eletrônica Avançada v2.0](overview-ediscovery-20.md) (também conhecida como \* solução de Descoberta Eletrônica Avançada no Microsoft 365\*) o mais rápido possível.</span><span class="sxs-lookup"><span data-stu-id="031f7-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="031f7-107">O Descoberta Eletrônica Avançada 2.0 contém funcionalidade semelhante encontrada na Descoberta Eletrônica Avançada v1.0, mas também oferece muitos recursos novos, como gerenciamento de custódia, gerenciamento de comunicações e conjuntos de revisão.</span><span class="sxs-lookup"><span data-stu-id="031f7-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="031f7-108">Para saber mais sobre a desativação da Descoberta Eletrônica Avançada v1.0, confira [Desativação de ferramentas legadas de Descoberta Eletrônica](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span><span class="sxs-lookup"><span data-stu-id="031f7-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="031f7-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="031f7-109">Prerequisites</span></span>

<span data-ttu-id="031f7-110">Antes de configurar casos e usuários na descoberta eletrônica avançada, é necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="031f7-110">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="031f7-111">Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="031f7-111">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="031f7-112">Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="031f7-112">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="031f7-113">Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5.</span><span class="sxs-lookup"><span data-stu-id="031f7-113">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="031f7-114">Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade de &amp; segurança do Office 365 para criar um caso de descoberta eletrônica e adicionar membros a ele.</span><span class="sxs-lookup"><span data-stu-id="031f7-114">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="031f7-115">Para se adicionar ao grupo de funções Gerenciador de descoberta eletrônica &amp; no centro de conformidade de segurança, você precisa ser um administrador global em sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="031f7-115">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="031f7-116">Se você não for um administrador global, será necessário pedir a um administrador global para adicioná-lo ao grupo de funções Gerenciador de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="031f7-116">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="031f7-117">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="031f7-117">For more information, see:</span></span>
    
  - [<span data-ttu-id="031f7-118">Permissões no centro de conformidade de &amp; segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="031f7-118">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](~/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="031f7-119">Atribuir permissões de descoberta eletrônica no centro de &amp; conformidade de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="031f7-119">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="031f7-120">Etapa 1: atribuir permissões de descoberta eletrônica de usuários</span><span class="sxs-lookup"><span data-stu-id="031f7-120">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="031f7-121">A primeira etapa é atribuir aos usuários as permissões de requisito no centro &amp; de conformidade de segurança para que eles possam ser adicionados como um membro de uma ocorrência de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="031f7-121">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="031f7-122">Após um usuário ser adicionado como um membro de um caso no centro de &amp; conformidade de segurança, ele poderá acessar o caso na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="031f7-122">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="031f7-123">Para atribuir a um usuário as permissões necessárias para que possam ser adicionadas como um membro de um caso de descoberta eletrônica, confira a etapa 1 em [casos &amp; de descoberta eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="031f7-123">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="031f7-124">Etapa 2: criar um caso de descoberta eletrônica e adicionar membros</span><span class="sxs-lookup"><span data-stu-id="031f7-124">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="031f7-125">A próxima etapa é criar uma nova ocorrência de descoberta eletrônica no centro &amp; de conformidade de segurança e adicionar membros.</span><span class="sxs-lookup"><span data-stu-id="031f7-125">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="031f7-126">Os membros do caso serão capazes de acessar o caso na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="031f7-126">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="031f7-127">Para criar uma nova ocorrência de descoberta eletrônica, confira a etapa 2 em [casos de descoberta &amp; eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="031f7-127">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="031f7-128">Para adicionar membros a um caso de descoberta eletrônica, confira a etapa 3 em [casos de descoberta &amp; eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="031f7-128">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="031f7-129">Etapa 3: usar uma descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="031f7-129">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="031f7-130">Após criar um caso de descoberta eletrônica e adicionar membros, você (ou qualquer membro do caso) pode acessar o caso correspondente na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="031f7-130">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="031f7-131">Para acessar um caso na descoberta eletrônica avançada, confira a etapa 8 em [casos de descoberta eletrônica &amp; no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="031f7-131">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="031f7-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="031f7-132">See also</span></span>

[<span data-ttu-id="031f7-133">Descoberta eletrônica avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="031f7-133">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="031f7-134">Preparação de dados</span><span class="sxs-lookup"><span data-stu-id="031f7-134">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
