---
title: Adicionar e verificar contatos do administrador no portal de Administração
description: Diga-nos quem entrar em contato para cada área de foco.
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9233118a2112aae33a5b784b6495709cbd3345f5
ms.sourcegitcommit: ef658406da9d081e5e7a5f3aac8290c2f03f7aff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41004916"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="1a5f8-104">Adicionar e verificar contatos do administrador no portal de Administração</span><span class="sxs-lookup"><span data-stu-id="1a5f8-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="1a5f8-105">Há várias maneiras de o serviço Microsoft Managed desktop se comunicar com os clientes.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="1a5f8-106">Para simplificar a comunicação e garantir que estamos verificando com as pessoas certas, você precisa fornecer um conjunto de contatos de administração.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="1a5f8-107">As operações de ti de área de trabalho gerenciada da Microsoft contatarão essas pessoas para resolver problemas de solução de problemas para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a5f8-108">Você pode já ter adicionado esses contatos no portal de administração.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="1a5f8-109">Em caso afirmativo, Reserve um momento para verificar se a lista de contatos é precisa, pois a área de trabalho gerenciada da Microsoft **deve** ser capaz de encontrá-las se ocorrer um incidente grave.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="1a5f8-110">Acesso do Azure Active Directory para o portal de administração de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a5f8-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="1a5f8-111">O portal de administração de área de trabalho gerenciada da Microsoft exige que as pessoas que acessam o portal tenham uma destas funções do Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="1a5f8-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="1a5f8-112">Administrador global</span><span class="sxs-lookup"><span data-stu-id="1a5f8-112">Global Administrator</span></span>
- <span data-ttu-id="1a5f8-113">Administrador de serviço do Intune</span><span class="sxs-lookup"><span data-stu-id="1a5f8-113">Intune Service Administrator</span></span>
- <span data-ttu-id="1a5f8-114">Leitor global</span><span class="sxs-lookup"><span data-stu-id="1a5f8-114">Global Reader</span></span>
- <span data-ttu-id="1a5f8-115">Administrador de suporte de serviço</span><span class="sxs-lookup"><span data-stu-id="1a5f8-115">Service Support Administrator</span></span>

<span data-ttu-id="1a5f8-116">O administrador global deve ser o para inscrever sua organização na área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="1a5f8-117">Todas as cinco funções têm o mesmo acesso dentro do portal de administração para iniciar e exibir tarefas.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="1a5f8-118">Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte [permissões de função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="1a5f8-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="1a5f8-119">Áreas de contato do administrador de foco</span><span class="sxs-lookup"><span data-stu-id="1a5f8-119">Admin contact areas of focus</span></span>

<span data-ttu-id="1a5f8-120">Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões para diferentes áreas de foco.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="1a5f8-121">**As operações de área de trabalho gerenciada da Microsoft contatarão esses contatos de administração para questões envolvendo solicitações de suporte arquivadas pelo cliente.**</span><span class="sxs-lookup"><span data-stu-id="1a5f8-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="1a5f8-122">Esses contatos do administrador receberão notificações para atualizações de solicitação de suporte e novas mensagens.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="1a5f8-123">Essas áreas incluem:</span><span class="sxs-lookup"><span data-stu-id="1a5f8-123">These areas include:</span></span>

<span data-ttu-id="1a5f8-124">Área de foco</span><span class="sxs-lookup"><span data-stu-id="1a5f8-124">Area of focus</span></span> | <span data-ttu-id="1a5f8-125">Para perguntas sobre</span><span class="sxs-lookup"><span data-stu-id="1a5f8-125">For questions about</span></span>
--- | ---
<span data-ttu-id="1a5f8-126">Pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1a5f8-126">App packaging</span></span> | <span data-ttu-id="1a5f8-127">Solucionando problemas de pacotes de aplicativos</span><span class="sxs-lookup"><span data-stu-id="1a5f8-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="1a5f8-128">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="1a5f8-128">Devices</span></span> | <span data-ttu-id="1a5f8-129">Integridade do dispositivo, Solucionando problemas com dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a5f8-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="1a5f8-130">Segurança</span><span class="sxs-lookup"><span data-stu-id="1a5f8-130">Security</span></span> | <span data-ttu-id="1a5f8-131">Solucionando problemas de segurança com dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a5f8-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="1a5f8-132">Assistência técnica de ti</span><span class="sxs-lookup"><span data-stu-id="1a5f8-132">IT help desk</span></span> | <span data-ttu-id="1a5f8-133">nos casos em que nossa equipe de suporte passa as permissões do usuário final para fora das áreas de suporte da área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a5f8-133">in cases where our Support staff hands over end-user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="1a5f8-134">Outros</span><span class="sxs-lookup"><span data-stu-id="1a5f8-134">Other</span></span> | <span data-ttu-id="1a5f8-135">Para problemas não cobertos por outras áreas</span><span class="sxs-lookup"><span data-stu-id="1a5f8-135">For issues not covered by other areas</span></span>

<span data-ttu-id="1a5f8-136">**Quem escolher para esses contatos precisa ter o conhecimento e a autoridade para tomar decisões para seu ambiente de área de trabalho gerenciada da Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="1a5f8-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="1a5f8-137">Quando você integra seu ambiente de área de trabalho gerenciada da Microsoft, você é solicitado a adicionar contatos para sua assistência técnica e segurança local.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="1a5f8-138">Os contatos do administrador são necessários ao [Enviar uma solicitação de suporte](../service-description/support.md).</span><span class="sxs-lookup"><span data-stu-id="1a5f8-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="1a5f8-139">Você precisará ter um contato de administrador para a área de foco da solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="1a5f8-140">**Para adicionar contatos do administrador**</span><span class="sxs-lookup"><span data-stu-id="1a5f8-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="1a5f8-141">Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="1a5f8-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="1a5f8-142">Em **suporte**, selecione **contatos do administrador**.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menu de suporte, contatos do administrador próximo à parte superior selecionada](images/admincontacts.png)

3. <span data-ttu-id="1a5f8-144">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-144">Select **Add**.</span></span>

    ![Portal de administração, botão Adicionar, à esquerda de exportar e atualizar](images/adminadd.png)

4.  <span data-ttu-id="1a5f8-146">Selecione uma **área de foco** e insira as informações do contato.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![a lista de áreas de foco, como outros, aplicativos e segurança](images/areaoffocus.png)

5. <span data-ttu-id="1a5f8-148">Repita para cada área de foco.</span><span class="sxs-lookup"><span data-stu-id="1a5f8-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="1a5f8-149">Etapas para começar a usar a área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a5f8-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="1a5f8-150">Adicionar e verificar contatos de administrador no portal de administração (este tópico)</span><span class="sxs-lookup"><span data-stu-id="1a5f8-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="1a5f8-151">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="1a5f8-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="1a5f8-152">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="1a5f8-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="1a5f8-153">Instalar o portal da empresa do Intune em dispositivos</span><span class="sxs-lookup"><span data-stu-id="1a5f8-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="1a5f8-154">Habilitar Roaming de Estado da Empresa</span><span class="sxs-lookup"><span data-stu-id="1a5f8-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="1a5f8-155">Configurar dispositivos de área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a5f8-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="1a5f8-156">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="1a5f8-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="1a5f8-157">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="1a5f8-157">Deploy apps to devices</span></span>](deploy-apps.md)
