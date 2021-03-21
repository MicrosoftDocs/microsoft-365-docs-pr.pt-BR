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
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925887"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="508c6-104">Adicione e verifique contatos do administrador no portal do Administrador</span><span class="sxs-lookup"><span data-stu-id="508c6-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="508c6-105">Há várias maneiras de o serviço da Área de Trabalho Gerenciada da Microsoft se comunicar com os clientes.</span><span class="sxs-lookup"><span data-stu-id="508c6-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="508c6-106">Para simplificar a comunicação e garantir que estamos verificando com as pessoas certas, você precisa fornecer um conjunto de contatos de administrador.</span><span class="sxs-lookup"><span data-stu-id="508c6-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="508c6-107">As Operações de IT da Área de Trabalho Gerenciada da Microsoft entrarão em contato com essas pessoas para problemas de solução de problemas de assistência para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="508c6-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="508c6-108">Você pode já ter adicionado esses contatos no portal de administração.</span><span class="sxs-lookup"><span data-stu-id="508c6-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="508c6-109">Em caso afirmado, verifique se a lista de contatos está  precisa, pois a Área de Trabalho Gerenciada da Microsoft deve ser capaz de alcançá-los se ocorrer um incidente grave.</span><span class="sxs-lookup"><span data-stu-id="508c6-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="508c6-110">Acesso do Azure Active Directory para o portal de Administração da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="508c6-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="508c6-111">O portal de Administração da Área de Trabalho Gerenciada da Microsoft exige que as pessoas que acessam o portal tenham uma dessas funções do Azure Active Directory (AD):</span><span class="sxs-lookup"><span data-stu-id="508c6-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="508c6-112">Administrador Global</span><span class="sxs-lookup"><span data-stu-id="508c6-112">Global Administrator</span></span>
- <span data-ttu-id="508c6-113">Administrador de Serviço do Intune</span><span class="sxs-lookup"><span data-stu-id="508c6-113">Intune Service Administrator</span></span>
- <span data-ttu-id="508c6-114">Leitor Global</span><span class="sxs-lookup"><span data-stu-id="508c6-114">Global Reader</span></span>
- <span data-ttu-id="508c6-115">Administrador de Suporte ao Serviço</span><span class="sxs-lookup"><span data-stu-id="508c6-115">Service Support Administrator</span></span>

<span data-ttu-id="508c6-116">O Administrador Global deve ser o único a registrar sua organização na Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="508c6-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="508c6-117">Todas as cinco funções têm o mesmo acesso no portal administrador para iniciar e exibir tarefas.</span><span class="sxs-lookup"><span data-stu-id="508c6-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="508c6-118">Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte Permissões de função de administrador [no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="508c6-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="508c6-119">Áreas de foco de contato do administrador</span><span class="sxs-lookup"><span data-stu-id="508c6-119">Admin contact areas of focus</span></span>

<span data-ttu-id="508c6-120">Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões para diferentes áreas de foco.</span><span class="sxs-lookup"><span data-stu-id="508c6-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="508c6-121">**As Operações de Área de Trabalho Gerenciada da Microsoft entrarão em contato com esses contatos do Administrador para perguntas envolvendo solicitações de suporte arquivadas pelo cliente.**</span><span class="sxs-lookup"><span data-stu-id="508c6-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="508c6-122">Esses contatos do Administrador receberão notificações para atualizações de solicitação de suporte e novas mensagens.</span><span class="sxs-lookup"><span data-stu-id="508c6-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="508c6-123">Essas áreas incluem:</span><span class="sxs-lookup"><span data-stu-id="508c6-123">These areas include:</span></span>

<span data-ttu-id="508c6-124">Área de foco</span><span class="sxs-lookup"><span data-stu-id="508c6-124">Area of focus</span></span> | <span data-ttu-id="508c6-125">Para perguntas sobre</span><span class="sxs-lookup"><span data-stu-id="508c6-125">For questions about</span></span>
--- | ---
<span data-ttu-id="508c6-126">Empacotamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="508c6-126">App packaging</span></span> | <span data-ttu-id="508c6-127">Solução de problemas de empacotamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="508c6-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="508c6-128">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="508c6-128">Devices</span></span> | <span data-ttu-id="508c6-129">Saúde do dispositivo, solução de problemas com dispositivos da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="508c6-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="508c6-130">Segurança</span><span class="sxs-lookup"><span data-stu-id="508c6-130">Security</span></span> | <span data-ttu-id="508c6-131">Solução de problemas de segurança com dispositivos da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="508c6-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="508c6-132">Help Desk de IT</span><span class="sxs-lookup"><span data-stu-id="508c6-132">IT help desk</span></span> | <span data-ttu-id="508c6-133">nos casos em que nossa equipe de Suporte entrega tíquetes de usuário fora das áreas de suporte da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="508c6-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="508c6-134">Outros</span><span class="sxs-lookup"><span data-stu-id="508c6-134">Other</span></span> | <span data-ttu-id="508c6-135">Para problemas não abordados por outras áreas</span><span class="sxs-lookup"><span data-stu-id="508c6-135">For issues not covered by other areas</span></span>

<span data-ttu-id="508c6-136">**Quem você escolher para esses contatos precisa ter o conhecimento e a autoridade para tomar decisões para seu ambiente de Área de Trabalho Gerenciada da Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="508c6-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="508c6-137">Quando você integra seu ambiente de Área de Trabalho Gerenciada da Microsoft, você é solicitado a adicionar contatos para seu Helpdesk e Security local.</span><span class="sxs-lookup"><span data-stu-id="508c6-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="508c6-138">Os contatos do administrador são necessários ao [enviar uma solicitação de Suporte.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="508c6-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="508c6-139">Você precisará ter um contato de administrador para a área de foco da solicitação de Suporte.</span><span class="sxs-lookup"><span data-stu-id="508c6-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="508c6-140">**Para adicionar contatos de administrador**</span><span class="sxs-lookup"><span data-stu-id="508c6-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="508c6-141">Entre no portal de [administração da Área de Trabalho Gerenciada da Microsoft](https://aka.ms/mwaasportal).</span><span class="sxs-lookup"><span data-stu-id="508c6-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="508c6-142">Em **Suporte,** selecione **Contatos de administrador.**</span><span class="sxs-lookup"><span data-stu-id="508c6-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menu de suporte, contatos de administrador próximos à parte superior selecionada](../../media/admincontacts.png)

3. <span data-ttu-id="508c6-144">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="508c6-144">Select **Add**.</span></span>

    ![Portal de administração, botão Adicionar, à esquerda de Exportar e Atualizar](../../media/adminadd.png)

4.  <span data-ttu-id="508c6-146">Selecione uma **Área de foco** e insira as informações do contato.</span><span class="sxs-lookup"><span data-stu-id="508c6-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![a lista de áreas de foco, como Outros, Aplicativos e Segurança](../../media/areaoffocus.png)

5. <span data-ttu-id="508c6-148">Repita para cada área de foco.</span><span class="sxs-lookup"><span data-stu-id="508c6-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="508c6-149">Etapas para começar com a Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="508c6-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="508c6-150">Adicionar e verificar contatos de administrador no portal de administração (este tópico)</span><span class="sxs-lookup"><span data-stu-id="508c6-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="508c6-151">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="508c6-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="508c6-152">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="508c6-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="508c6-153">Instalar o Portal da Empresa do Intune em dispositivos</span><span class="sxs-lookup"><span data-stu-id="508c6-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="508c6-154">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="508c6-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="508c6-155">Configurar dispositivos de Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="508c6-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="508c6-156">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="508c6-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="508c6-157">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="508c6-157">Deploy apps to devices</span></span>](deploy-apps.md)