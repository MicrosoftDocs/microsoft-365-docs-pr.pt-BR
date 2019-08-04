---
title: Adicionar contatos do administrador no portal de administração de área de trabalho gerenciada da Microsoft
description: Diga-nos quem entrar em contato para cada área de foco.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 68f5d5cb46d4aa643b1b09f9204b24dea3d77eb1
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390528"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="9422e-104">Adicionar contatos do administrador no portal de administração de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9422e-104">Add Admin contacts in Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="9422e-105">Há várias maneiras de o serviço Microsoft Managed desktop se comunicar com os clientes.</span><span class="sxs-lookup"><span data-stu-id="9422e-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="9422e-106">Para simplificar a comunicação e garantir que estamos verificando os melhores contatos, você precisa fornecer um conjunto de contatos de administração.</span><span class="sxs-lookup"><span data-stu-id="9422e-106">To streamline communication and ensure we’re checking with the best contacts, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="9422e-107">As operações de ti de área de trabalho gerenciada da Microsoft contatarão essas pessoas para resolver problemas de solução de problemas para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9422e-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span> 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="9422e-108">Acesso do Azure Active Directory para o portal de administração de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9422e-108">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="9422e-109">O portal de administração de área de trabalho gerenciada da Microsoft exige que as pessoas que acessam o portal tenham uma destas funções do Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="9422e-109">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="9422e-110">Administrador global</span><span class="sxs-lookup"><span data-stu-id="9422e-110">Global Administrator</span></span>
- <span data-ttu-id="9422e-111">Administrador de serviço do Intune</span><span class="sxs-lookup"><span data-stu-id="9422e-111">Intune Service Administrator</span></span>
- <span data-ttu-id="9422e-112">Administrador de cobrança</span><span class="sxs-lookup"><span data-stu-id="9422e-112">Billing Administrator</span></span>
- <span data-ttu-id="9422e-113">Administrador de suporte de serviço</span><span class="sxs-lookup"><span data-stu-id="9422e-113">Service Support Administrator</span></span>

<span data-ttu-id="9422e-114">O administrador global deve ser um para inscrever o cliente na área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9422e-114">The Global Administrator must be the one to enroll the customer in Microsoft Managed Desktop.</span></span> <span data-ttu-id="9422e-115">Todas as cinco funções têm o mesmo acesso dentro do portal de administração para iniciar e exibir tarefas.</span><span class="sxs-lookup"><span data-stu-id="9422e-115">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="9422e-116">Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="9422e-116">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-focus-areas"></a><span data-ttu-id="9422e-117">Áreas de foco de contato do administrador</span><span class="sxs-lookup"><span data-stu-id="9422e-117">Admin contact focus areas</span></span>

<span data-ttu-id="9422e-118">Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões para diferentes áreas de foco.</span><span class="sxs-lookup"><span data-stu-id="9422e-118">Admin contacts should be the best person or group that can answer questions and make decisions for different focus areas.</span></span> <span data-ttu-id="9422e-119">As operações de área de trabalho gerenciada da Microsoft contatarão esses contatos de administração para questões envolvendo solicitações de suporte arquivadas pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="9422e-119">Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.</span></span> <span data-ttu-id="9422e-120">Esses contatos do administrador receberão notificações para atualizações de solicitação de suporte e novas mensagens.</span><span class="sxs-lookup"><span data-stu-id="9422e-120">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="9422e-121">Essas áreas incluem:</span><span class="sxs-lookup"><span data-stu-id="9422e-121">These areas include:</span></span>

<span data-ttu-id="9422e-122">Área de foco</span><span class="sxs-lookup"><span data-stu-id="9422e-122">Focus area</span></span> | <span data-ttu-id="9422e-123">Para perguntas sobre</span><span class="sxs-lookup"><span data-stu-id="9422e-123">For questions about</span></span>
--- | ---
<span data-ttu-id="9422e-124">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="9422e-124">Apps</span></span> | <span data-ttu-id="9422e-125">Solucionando problemas de pacotes de aplicativos</span><span class="sxs-lookup"><span data-stu-id="9422e-125">Troubleshooting App Packaging</span></span>
<span data-ttu-id="9422e-126">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="9422e-126">Devices</span></span> | <span data-ttu-id="9422e-127">Integridade do dispositivo, Solucionando problemas com dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9422e-127">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="9422e-128">Segurança</span><span class="sxs-lookup"><span data-stu-id="9422e-128">Security</span></span> | <span data-ttu-id="9422e-129">Solucionando problemas de segurança com dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9422e-129">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="9422e-130">Assistência técnica de ti</span><span class="sxs-lookup"><span data-stu-id="9422e-130">IT Help desk</span></span> | <span data-ttu-id="9422e-131">nos casos em que o suporte de área de trabalho gerenciada da Microsoft focaliza as permissões do usuário final fora das áreas de suporte do MMD</span><span class="sxs-lookup"><span data-stu-id="9422e-131">in cases where Microsoft Managed Desktop Support hands over end user tickets outside of MMD support areas</span></span> 
<span data-ttu-id="9422e-132">Other</span><span class="sxs-lookup"><span data-stu-id="9422e-132">Other</span></span> | <span data-ttu-id="9422e-133">Para problemas não cobertos por outras áreas</span><span class="sxs-lookup"><span data-stu-id="9422e-133">For issues not covered by other areas</span></span>

<span data-ttu-id="9422e-134">Quem escolher para esses contatos precisa ter o conhecimento e a autoridade para tomar decisões para seu ambiente de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9422e-134">Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.</span></span> <span data-ttu-id="9422e-135">Quando você integra seu ambiente de área de trabalho gerenciada da Microsoft, você é solicitado a adicionar contatos para sua assistência técnica e segurança local.</span><span class="sxs-lookup"><span data-stu-id="9422e-135">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="9422e-136">Os contatos do administrador são necessários ao [Enviar uma solicitação de suporte](../working-with-managed-desktop/support.md).</span><span class="sxs-lookup"><span data-stu-id="9422e-136">Admin contacts are required when you [submit a Support request](../working-with-managed-desktop/support.md).</span></span> <span data-ttu-id="9422e-137">Você precisará ter um contato de administrador para a área de foco da solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="9422e-137">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="9422e-138">**Para adicionar contatos do administrador**</span><span class="sxs-lookup"><span data-stu-id="9422e-138">**To add admin contacts**</span></span>

1.  <span data-ttu-id="9422e-139">Entre no [portal de administração de área de trabalho gerenciada da Microsoft](http://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="9422e-139">Sign in to [Microsoft Managed Desktop admin portal](http://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="9422e-140">Em **suporte**, selecione **contatos do administrador**.</span><span class="sxs-lookup"><span data-stu-id="9422e-140">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menu de suporte, contatos do administrador](images/admincontacts.png)

3. <span data-ttu-id="9422e-142">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9422e-142">Select **Add**.</span></span>

    ![Botão Adicionar do portal de administração](images/adminadd.png)

4.  <span data-ttu-id="9422e-144">Selecione uma **área de foco** e insira as informações do contato.</span><span class="sxs-lookup"><span data-stu-id="9422e-144">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![a lista de áreas de foco](images/areaoffocus.png)

5. <span data-ttu-id="9422e-146">Repita para cada área de foco.</span><span class="sxs-lookup"><span data-stu-id="9422e-146">Repeat for each area of focus.</span></span> 

