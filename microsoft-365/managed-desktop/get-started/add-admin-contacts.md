---
title: Adicione e verifique contatos do administrador no portal do Administrador
description: Diga-nos quem contatar para cada área de foco.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ba4f1b0e4b2e00334dbffb4bf0aa9edb1b8c5622
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286916"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="2fabd-104">Adicione e verifique contatos do administrador no portal do Administrador</span><span class="sxs-lookup"><span data-stu-id="2fabd-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="2fabd-105">Há várias maneiras de o Área de Trabalho Gerenciada da Microsoft se comunicar com os clientes.</span><span class="sxs-lookup"><span data-stu-id="2fabd-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="2fabd-106">Para simplificar a comunicação e garantir que estamos verificando com as pessoas certas, você precisa fornecer um conjunto de contatos de administrador.</span><span class="sxs-lookup"><span data-stu-id="2fabd-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="2fabd-107">Área de Trabalho Gerenciada da Microsoft As operações de IT entrarão em contato com essas pessoas para solucionar problemas de solução de problemas de assistência para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="2fabd-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fabd-108">Você pode já ter adicionado esses contatos no portal de administração.</span><span class="sxs-lookup"><span data-stu-id="2fabd-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="2fabd-109">Em caso afirmado, verifique se a lista de contatos está precisa, pois Área de Trabalho Gerenciada da Microsoft deve ser capaz de alcançá-los se ocorrer um incidente grave. </span><span class="sxs-lookup"><span data-stu-id="2fabd-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="2fabd-110">Azure Active Directory acesso para o Área de Trabalho Gerenciada da Microsoft Admin</span><span class="sxs-lookup"><span data-stu-id="2fabd-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="2fabd-111">Área de Trabalho Gerenciada da Microsoft O portal de administração exige que as pessoas que acessam o portal tenham uma dessas funções Azure Active Directory (AD) :</span><span class="sxs-lookup"><span data-stu-id="2fabd-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>

- <span data-ttu-id="2fabd-112">Administrador global</span><span class="sxs-lookup"><span data-stu-id="2fabd-112">Global Administrator</span></span>
- <span data-ttu-id="2fabd-113">Administrador de Serviço do Intune</span><span class="sxs-lookup"><span data-stu-id="2fabd-113">Intune Service Administrator</span></span>
- <span data-ttu-id="2fabd-114">Leitor global</span><span class="sxs-lookup"><span data-stu-id="2fabd-114">Global Reader</span></span>
- <span data-ttu-id="2fabd-115">Administrador de Suporte ao Serviço</span><span class="sxs-lookup"><span data-stu-id="2fabd-115">Service Support Administrator</span></span>

<span data-ttu-id="2fabd-116">O Administrador Global deve ser o único a registrar sua organização no Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fabd-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="2fabd-117">Todas as cinco funções têm o mesmo acesso no portal administrador para iniciar e exibir tarefas.</span><span class="sxs-lookup"><span data-stu-id="2fabd-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="2fabd-118">Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte Permissões de função [de administrador em Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="2fabd-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span>

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="2fabd-119">Áreas de foco de contato do administrador</span><span class="sxs-lookup"><span data-stu-id="2fabd-119">Admin contact areas of focus</span></span>

<span data-ttu-id="2fabd-120">Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões para diferentes áreas de foco.</span><span class="sxs-lookup"><span data-stu-id="2fabd-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="2fabd-121">**Área de Trabalho Gerenciada da Microsoft As operações entrarão em contato com esses contatos do Administrador para perguntas envolvendo solicitações de suporte arquivadas pelo cliente.**</span><span class="sxs-lookup"><span data-stu-id="2fabd-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="2fabd-122">Esses contatos do Administrador receberão notificações para atualizações de solicitação de suporte e novas mensagens.</span><span class="sxs-lookup"><span data-stu-id="2fabd-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="2fabd-123">Essas áreas incluem:</span><span class="sxs-lookup"><span data-stu-id="2fabd-123">These areas include:</span></span>

<span data-ttu-id="2fabd-124">Área de foco</span><span class="sxs-lookup"><span data-stu-id="2fabd-124">Area of focus</span></span> | <span data-ttu-id="2fabd-125">Para perguntas sobre</span><span class="sxs-lookup"><span data-stu-id="2fabd-125">For questions about</span></span>
--- | ---
<span data-ttu-id="2fabd-126">Empacotamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2fabd-126">App packaging</span></span> | <span data-ttu-id="2fabd-127">Solução de problemas de empacotamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2fabd-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="2fabd-128">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="2fabd-128">Devices</span></span> | <span data-ttu-id="2fabd-129">Saúde do dispositivo, solução de problemas com Área de Trabalho Gerenciada da Microsoft dispositivos</span><span class="sxs-lookup"><span data-stu-id="2fabd-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2fabd-130">Segurança</span><span class="sxs-lookup"><span data-stu-id="2fabd-130">Security</span></span> | <span data-ttu-id="2fabd-131">Solução de problemas de segurança com Área de Trabalho Gerenciada da Microsoft dispositivos</span><span class="sxs-lookup"><span data-stu-id="2fabd-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2fabd-132">Help Desk de IT</span><span class="sxs-lookup"><span data-stu-id="2fabd-132">IT help desk</span></span> | <span data-ttu-id="2fabd-133">nos casos em que nossa equipe de Suporte entrega tíquetes de usuário fora Área de Trabalho Gerenciada da Microsoft áreas de suporte</span><span class="sxs-lookup"><span data-stu-id="2fabd-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="2fabd-134">Outros</span><span class="sxs-lookup"><span data-stu-id="2fabd-134">Other</span></span> | <span data-ttu-id="2fabd-135">Para problemas não abordados por outras áreas</span><span class="sxs-lookup"><span data-stu-id="2fabd-135">For issues not covered by other areas</span></span>

<span data-ttu-id="2fabd-136">**Quem você escolher para esses contatos precisa ter o conhecimento e a autoridade para tomar decisões para seu Área de Trabalho Gerenciada da Microsoft ambiente.**</span><span class="sxs-lookup"><span data-stu-id="2fabd-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="2fabd-137">Quando você integra seu Área de Trabalho Gerenciada da Microsoft ambiente de Área de Trabalho Gerenciada da Microsoft, é solicitado a adicionar contatos para seu Helpdesk e Security local.</span><span class="sxs-lookup"><span data-stu-id="2fabd-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="2fabd-138">Os contatos do administrador são necessários ao [enviar uma solicitação de Suporte.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="2fabd-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="2fabd-139">Você precisará ter um contato de administrador para a área de foco da solicitação de Suporte.</span><span class="sxs-lookup"><span data-stu-id="2fabd-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span>

<span data-ttu-id="2fabd-140">**Para adicionar contatos de administrador**</span><span class="sxs-lookup"><span data-stu-id="2fabd-140">**To add admin contacts**</span></span>

1. <span data-ttu-id="2fabd-141">Entre [no](https://endpoint.microsoft.com)Microsoft Endpoint Manager .</span><span class="sxs-lookup"><span data-stu-id="2fabd-141">Sign in to [Microsoft Endpoint Manager](https://endpoint.microsoft.com).</span></span>

2. <span data-ttu-id="2fabd-142">Em **Administração de locatários,** procure a seção **Área de Trabalho Gerenciada da Microsoft** em seguida, selecione Contatos **de administrador**.</span><span class="sxs-lookup"><span data-stu-id="2fabd-142">Under **Tenant administration**, look for the **Microsoft Managed Desktop** section then select **Admin contacts**.</span></span>

3. <span data-ttu-id="2fabd-143">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2fabd-143">Select **Add**.</span></span>

4. <span data-ttu-id="2fabd-144">Selecione uma **Área de foco** e insira as informações do contato.</span><span class="sxs-lookup"><span data-stu-id="2fabd-144">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![a lista de áreas de foco, como Outros, Aplicativos e Segurança](../../media/areaoffocus.png)

5. <span data-ttu-id="2fabd-146">Repita para cada área de foco.</span><span class="sxs-lookup"><span data-stu-id="2fabd-146">Repeat for each area of focus.</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="2fabd-147">Etapas para começar a Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2fabd-147">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="2fabd-148">Adicionar e verificar contatos de administrador no portal de administração (este tópico)</span><span class="sxs-lookup"><span data-stu-id="2fabd-148">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="2fabd-149">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2fabd-149">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="2fabd-150">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="2fabd-150">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="2fabd-151">Instalar o Portal da Empresa do Intune em dispositivos</span><span class="sxs-lookup"><span data-stu-id="2fabd-151">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="2fabd-152">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="2fabd-152">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="2fabd-153">Configurar dispositivos de Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2fabd-153">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="2fabd-154">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="2fabd-154">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="2fabd-155">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="2fabd-155">Deploy apps to devices</span></span>](deploy-apps.md)
