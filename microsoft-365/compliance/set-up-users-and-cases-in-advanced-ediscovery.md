---
title: Configurar usuários e casos na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Saiba como configurar funções de usuário, criar ocorrências e atribuir usuários a casos na descoberta eletrônica avançada do Office 365.  '
ms.openlocfilehash: e53d304445aa7d171766d38496d95a0d6cb47792
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073110"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="eccea-103">Configurar usuários e casos na descoberta eletrônica avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="eccea-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="eccea-104">Este tópico descreve como configurar usuários e casos para a descoberta eletrônica avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="eccea-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eccea-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="eccea-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="eccea-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="eccea-107">Prerequisites</span></span>

<span data-ttu-id="eccea-108">Antes de configurar casos e usuários na descoberta eletrônica avançada, é necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eccea-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="eccea-109">Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="eccea-109">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license.</span></span> <span data-ttu-id="eccea-110">Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="eccea-110">Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license.</span></span> <span data-ttu-id="eccea-111">Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5.</span><span class="sxs-lookup"><span data-stu-id="eccea-111">Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="eccea-112">Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade de &amp; segurança do Office 365 para criar um caso de descoberta eletrônica e adicionar membros a ele.</span><span class="sxs-lookup"><span data-stu-id="eccea-112">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="eccea-113">Para se adicionar ao grupo de funções Gerenciador de descoberta eletrônica &amp; no centro de conformidade de segurança, você precisa ser um administrador global em sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="eccea-113">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="eccea-114">Se você não for um administrador global, será necessário pedir a um administrador global para adicioná-lo ao grupo de funções Gerenciador de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="eccea-114">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="eccea-115">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="eccea-115">For more information, see:</span></span>
    
  - [<span data-ttu-id="eccea-116">Permissões no centro de conformidade de &amp; segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eccea-116">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](/security/office-365-security/protect-against-threats.md)
    
  - [<span data-ttu-id="eccea-117">Atribuir permissões de descoberta eletrônica no centro de &amp; conformidade de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eccea-117">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="eccea-118">Etapa 1: atribuir permissões de descoberta eletrônica de usuários</span><span class="sxs-lookup"><span data-stu-id="eccea-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="eccea-119">A primeira etapa é atribuir aos usuários as permissões de requisito no centro &amp; de conformidade de segurança para que eles possam ser adicionados como um membro de uma ocorrência de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="eccea-119">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="eccea-120">Após um usuário ser adicionado como um membro de um caso no centro de &amp; conformidade de segurança, ele poderá acessar o caso na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="eccea-120">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="eccea-121">Para atribuir a um usuário as permissões necessárias para que possam ser adicionadas como um membro de um caso de descoberta eletrônica, confira a etapa 1 em [casos &amp; de descoberta eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span><span class="sxs-lookup"><span data-stu-id="eccea-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="eccea-122">Etapa 2: criar um caso de descoberta eletrônica e adicionar membros</span><span class="sxs-lookup"><span data-stu-id="eccea-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="eccea-123">A próxima etapa é criar uma nova ocorrência de descoberta eletrônica no centro &amp; de conformidade de segurança e adicionar membros.</span><span class="sxs-lookup"><span data-stu-id="eccea-123">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="eccea-124">Os membros do caso serão capazes de acessar o caso na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="eccea-124">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="eccea-125">Para criar uma nova ocorrência de descoberta eletrônica, confira a etapa 2 em [casos de descoberta &amp; eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-2-create-a-new-case).</span><span class="sxs-lookup"><span data-stu-id="eccea-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="eccea-126">Para adicionar membros a um caso de descoberta eletrônica, confira a etapa 3 em [casos de descoberta &amp; eletrônica no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="eccea-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="eccea-127">Etapa 3: usar uma descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="eccea-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="eccea-128">Após criar um caso de descoberta eletrônica e adicionar membros, você (ou qualquer membro do caso) pode acessar o caso correspondente na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="eccea-128">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="eccea-129">Para acessar um caso na descoberta eletrônica avançada, confira a etapa 8 em [casos de descoberta eletrônica &amp; no centro de conformidade de segurança do Microsoft 365](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span><span class="sxs-lookup"><span data-stu-id="eccea-129">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eccea-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="eccea-130">See also</span></span>

[<span data-ttu-id="eccea-131">Descoberta Eletrônica Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="eccea-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="eccea-132">Preparação de dados</span><span class="sxs-lookup"><span data-stu-id="eccea-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 
