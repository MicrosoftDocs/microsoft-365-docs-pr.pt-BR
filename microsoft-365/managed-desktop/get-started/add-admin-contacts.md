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
ms.openlocfilehash: 8b287200b1c94ff350f7ba00cf0c4e6bc1b4a71f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289256"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a><span data-ttu-id="2c440-104">Adicione e verifique contatos do administrador no portal do Administrador</span><span class="sxs-lookup"><span data-stu-id="2c440-104">Add and verify admin contacts in the Admin portal</span></span>

<span data-ttu-id="2c440-105">Há várias maneiras de o serviço área de trabalho gerenciada da Microsoft se comunicar com os clientes.</span><span class="sxs-lookup"><span data-stu-id="2c440-105">There are several ways that Microsoft Managed Desktop service communicates with customers.</span></span> <span data-ttu-id="2c440-106">Para simplificar a comunicação e garantir que estamos verificando com as pessoas certas, você precisa fornecer um conjunto de contatos de administrador.</span><span class="sxs-lookup"><span data-stu-id="2c440-106">To streamline communication and ensure we’re checking with the right people, you need to provide a set of admin contacts.</span></span> <span data-ttu-id="2c440-107">As operações de IT da Área de Trabalho Gerenciada da Microsoft entrarão em contato com essas pessoas para ajudar na solução de problemas do seu locatário.</span><span class="sxs-lookup"><span data-stu-id="2c440-107">Microsoft Managed Desktop IT Operations will contact these people for assistance troubleshooting issues for your tenant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c440-108">Talvez você já tenha adicionado esses contatos no portal de administração.</span><span class="sxs-lookup"><span data-stu-id="2c440-108">You might have already added these contacts in the Admin portal.</span></span> <span data-ttu-id="2c440-109">Nesse caso, dê um tempo agora para verificar se a lista  de contatos está precisa, pois a Área de Trabalho Gerenciada da Microsoft deve ser capaz de entrar em contato com eles se ocorrer um incidente grave.</span><span class="sxs-lookup"><span data-stu-id="2c440-109">If so, take a moment now to double-check that the contact list is accurate, since Microsoft Managed Desktop **must** be able to reach them if a severe incident occurs.</span></span>

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a><span data-ttu-id="2c440-110">Acesso do Azure Active Directory ao Portal de Administração da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c440-110">Azure Active Directory access for Microsoft Managed Desktop Admin portal</span></span>

<span data-ttu-id="2c440-111">O Portal de Administração da Área de Trabalho Gerenciada da Microsoft exige que as pessoas que acessam o portal tenham uma destas funções do Azure Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="2c440-111">Microsoft Managed Desktop Admin portal requires that people accessing the portal have one of these Azure Active Directory (AD) roles:</span></span>
- <span data-ttu-id="2c440-112">Administrador Global</span><span class="sxs-lookup"><span data-stu-id="2c440-112">Global Administrator</span></span>
- <span data-ttu-id="2c440-113">Administrador de Serviços do Intune</span><span class="sxs-lookup"><span data-stu-id="2c440-113">Intune Service Administrator</span></span>
- <span data-ttu-id="2c440-114">Leitor global</span><span class="sxs-lookup"><span data-stu-id="2c440-114">Global Reader</span></span>
- <span data-ttu-id="2c440-115">Administrador de Suporte ao Serviço</span><span class="sxs-lookup"><span data-stu-id="2c440-115">Service Support Administrator</span></span>

<span data-ttu-id="2c440-116">O Administrador Global deve ser aquele que registrará sua organização na Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c440-116">The Global Administrator must be the one to enroll your organization in Microsoft Managed Desktop.</span></span> <span data-ttu-id="2c440-117">Todas as cinco funções têm o mesmo acesso no portal de administração para iniciar e exibir tarefas.</span><span class="sxs-lookup"><span data-stu-id="2c440-117">All five roles have the same access within the Admin portal to initiate and view tasks.</span></span> <span data-ttu-id="2c440-118">Para obter mais informações sobre como atribuir essas funções no Azure AD, consulte Permissões de função [de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)</span><span class="sxs-lookup"><span data-stu-id="2c440-118">For more information on assigning these roles in Azure AD, see [Administrator role permissions in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> 

## <a name="admin-contact-areas-of-focus"></a><span data-ttu-id="2c440-119">Áreas de contato de administrador de foco</span><span class="sxs-lookup"><span data-stu-id="2c440-119">Admin contact areas of focus</span></span>

<span data-ttu-id="2c440-120">Os contatos do administrador devem ser a melhor pessoa ou grupo que pode responder a perguntas e tomar decisões em diferentes áreas de foco.</span><span class="sxs-lookup"><span data-stu-id="2c440-120">Admin contacts should be the best person or group that can answer questions and make decisions for different areas of focus.</span></span> <span data-ttu-id="2c440-121">**As Operações da Área de Trabalho Gerenciada da Microsoft entrarão em contato com esses contatos do Administrador para perguntas envolvendo solicitações de suporte arquivadas pelo cliente.**</span><span class="sxs-lookup"><span data-stu-id="2c440-121">**Microsoft Managed Desktop Operations will contact these Admin contacts for questions involving support requests filed by the customer.**</span></span> <span data-ttu-id="2c440-122">Esses contatos do Administrador receberão notificações de atualizações de solicitação de suporte e novas mensagens.</span><span class="sxs-lookup"><span data-stu-id="2c440-122">These Admin contacts will receive notifications for support request updates and new messages.</span></span> <span data-ttu-id="2c440-123">Essas áreas incluem:</span><span class="sxs-lookup"><span data-stu-id="2c440-123">These areas include:</span></span>

<span data-ttu-id="2c440-124">Área de foco</span><span class="sxs-lookup"><span data-stu-id="2c440-124">Area of focus</span></span> | <span data-ttu-id="2c440-125">Para perguntas sobre</span><span class="sxs-lookup"><span data-stu-id="2c440-125">For questions about</span></span>
--- | ---
<span data-ttu-id="2c440-126">Empacotamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2c440-126">App packaging</span></span> | <span data-ttu-id="2c440-127">Solução de problemas de empacotamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2c440-127">Troubleshooting app packaging</span></span>
<span data-ttu-id="2c440-128">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="2c440-128">Devices</span></span> | <span data-ttu-id="2c440-129">Saúde do dispositivo, solução de problemas com dispositivos da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c440-129">Device health, troubleshooting with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2c440-130">Segurança</span><span class="sxs-lookup"><span data-stu-id="2c440-130">Security</span></span> | <span data-ttu-id="2c440-131">Solução de problemas de segurança com dispositivos da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c440-131">Troubleshooting security issues with Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="2c440-132">Help desk de IT</span><span class="sxs-lookup"><span data-stu-id="2c440-132">IT help desk</span></span> | <span data-ttu-id="2c440-133">nos casos em que nossa equipe de Suporte entrega tíquetes de usuário fora das áreas de suporte da Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c440-133">in cases where our Support staff hands over user tickets outside of Microsoft Managed Desktop support areas</span></span> 
<span data-ttu-id="2c440-134">Outros</span><span class="sxs-lookup"><span data-stu-id="2c440-134">Other</span></span> | <span data-ttu-id="2c440-135">Para problemas não cobertos por outras áreas</span><span class="sxs-lookup"><span data-stu-id="2c440-135">For issues not covered by other areas</span></span>

<span data-ttu-id="2c440-136">**Quem escolher para esses contatos precisa ter conhecimento e autoridade para tomar decisões em seu ambiente de Área de Trabalho Gerenciada da Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="2c440-136">**Whoever you choose for these contacts needs to have the knowledge and authority to make decisions for your Microsoft Managed Desktop environment.**</span></span> <span data-ttu-id="2c440-137">Quando você integra seu ambiente de Área de Trabalho Gerenciada da Microsoft, é solicitado a adicionar contatos para a Helpdesk e a Segurança locais.</span><span class="sxs-lookup"><span data-stu-id="2c440-137">When you onboard your Microsoft Managed Desktop environment, you’re prompted to add contacts for your local Helpdesk and Security.</span></span> 

<span data-ttu-id="2c440-138">Os contatos do administrador são necessários quando você [envia uma solicitação de suporte.](../service-description/support.md)</span><span class="sxs-lookup"><span data-stu-id="2c440-138">Admin contacts are required when you [submit a Support request](../service-description/support.md).</span></span> <span data-ttu-id="2c440-139">Você precisará ter um contato de administrador para a área de foco da solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="2c440-139">You’ll need to have an admin contact for the focus area of the Support request.</span></span> 

<span data-ttu-id="2c440-140">**Para adicionar contatos de administrador**</span><span class="sxs-lookup"><span data-stu-id="2c440-140">**To add admin contacts**</span></span>

1.  <span data-ttu-id="2c440-141">Entre no [portal de administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="2c440-141">Sign in to [Microsoft Managed Desktop admin portal](https://aka.ms/mwaasportal).</span></span> 

2.  <span data-ttu-id="2c440-142">Em **Suporte,** selecione **Contatos do administrador.**</span><span class="sxs-lookup"><span data-stu-id="2c440-142">Under **Support**, select **Admin contacts**.</span></span> 

    ![Menu de suporte, contatos do administrador próximo à parte superior selecionada](../../media/admincontacts.png)

3. <span data-ttu-id="2c440-144">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2c440-144">Select **Add**.</span></span>

    ![Portal de administração, botão Adicionar à esquerda de Exportar e Atualizar](../../media/adminadd.png)

4.  <span data-ttu-id="2c440-146">Selecione uma **área de foco** e insira as informações do contato.</span><span class="sxs-lookup"><span data-stu-id="2c440-146">Select an **Area of focus** and enter the info for the contact.</span></span> 

    ![a lista de áreas de foco, como Outros, Aplicativos e Segurança](../../media/areaoffocus.png)

5. <span data-ttu-id="2c440-148">Repita para cada área de foco.</span><span class="sxs-lookup"><span data-stu-id="2c440-148">Repeat for each area of focus.</span></span> 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="2c440-149">Etapas para começar a trabalhar com a Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c440-149">Steps to get started with Microsoft Managed Desktop</span></span>

1. <span data-ttu-id="2c440-150">Adicionar e verificar contatos de administrador no portal de administração (este tópico)</span><span class="sxs-lookup"><span data-stu-id="2c440-150">Add and verify admin contacts in the Admin portal (this topic)</span></span>
2. [<span data-ttu-id="2c440-151">Ajustar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2c440-151">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="2c440-152">Atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="2c440-152">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="2c440-153">Instalar o Portal da Empresa do Intune em dispositivos</span><span class="sxs-lookup"><span data-stu-id="2c440-153">Install Intune Company Portal on on devices</span></span>](company-portal.md)
5. [<span data-ttu-id="2c440-154">Habilitar Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="2c440-154">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="2c440-155">Configurar dispositivos de Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c440-155">Set up Microsoft Managed Desktop devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="2c440-156">Preparar usuários para o uso dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="2c440-156">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="2c440-157">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="2c440-157">Deploy apps to devices</span></span>](deploy-apps.md)
