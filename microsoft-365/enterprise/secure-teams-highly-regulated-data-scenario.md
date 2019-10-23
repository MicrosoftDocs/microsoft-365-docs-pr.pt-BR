---
title: Teams para dados altamente regulamentados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um site de equipe seguro para armazenar seus arquivos mais valiosos e confidenciais.
ms.openlocfilehash: 5117d310ccd877a7377e6e538e7fba13daaad4ef
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617259"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="7bfb4-103">Teams para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="7bfb4-103">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="7bfb4-104">Este artigo fornece recomendações e passo a passo para configurar uma equipe privada no Microsoft Teams que bloqueia o acesso aos recursos do Teams, como chats, reuniões e arquivos, somente para membros e proprietários do grupo do Office 365 da equipe.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="7bfb4-105">Além do acesso privado baseado no grupo do Office 365, este artigo descreve como configurar o site de equipe particular e subjacente do SharePoint, que você pode na seção de **Arquivos** de um canal de equipe e obter a segurança adicional necessária para armazenar dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="7bfb4-106">Neste site de equipe do SharePoint, você pode armazenar e colaborar em arquivos, páginas, um calendário compartilhado, tarefas, um bloco de anotações e listas.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="7bfb4-107">Os elementos de configuração de uma equipe para dados altamente regulamentados são:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="7bfb4-108">Uma equipe privada com um grupo correspondente do Office 365 que tem contas de usuário de proprietário e membro.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="7bfb4-109">Segurança adicional no site subjacente do SharePoint para a equipe que:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="7bfb4-110">Impede que membros do site concedam acesso a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="7bfb4-111">Impede que não membros do site solicitem acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="7bfb4-112">Um rótulo de retenção do Office 365 para o site do SharePoint subjacente que é aplicado automaticamente a novos arquivos no site como uma maneira padrão de definir políticas de retenção.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="7bfb4-113">Uma política de Prevenção contra Perda de Dados (DLP) que usa o rótulo de retenção e impede que os usuários compartilhem ou enviem arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="7bfb4-114">Um rótulo de confidencialidade do Office 365 de ou sub-rótulo de um rótulo altamente regulamentado com criptografia habilitada e permissões de Coautor para o grupo da equipe do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="7bfb4-115">Os usuários aplicam o rótulo ou sub-rótulo aos arquivos armazenados na seção de **Arquivos** da equipe na opção da barra de menus Confidencialidade do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="7bfb4-116">Esta é a configuração resultante com um rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-116">Here is the resulting configuration with a sensitivity label.</span></span>

![A configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="configuration"></a><span data-ttu-id="7bfb4-118">Configuração</span><span class="sxs-lookup"><span data-stu-id="7bfb4-118">Configuration</span></span>

<span data-ttu-id="7bfb4-119">A configuração ponta a ponta de uma equipe segura consiste destas etapas:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-119">The end-to-end configuration of a secure team consists of these steps:</span></span>

1. <span data-ttu-id="7bfb4-120">Configurações de identidade e acesso a dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="7bfb4-121">Criação de uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-121">Create a team</span></span>
3. <span data-ttu-id="7bfb4-122">Configuração de site do SharePoint subjacente para segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="7bfb4-123">Criação de um rótulo de retenção e uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="7bfb4-124">Criação de rótulo ou sub-rótulo de rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="7bfb4-125">Etapa 1: configurações de identidade e acesso a dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="7bfb4-126">Para proteger o acesso à equipe e ao site do SharePoint subjacente, assegure-se de ter configurado as[políticas de identidade e acesso a dispositivo](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) e as [políticas de acesso do SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) recomendadas.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="7bfb4-127">Etapa 2: criação de uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-127">Step 2: Create a private team</span></span>

<span data-ttu-id="7bfb4-128">Use [essas instruções](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) para criar uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="7bfb4-129">Ao criar uma equipe privada, estas são as permissões padrão:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="7bfb4-130">O grupo do Office 365 para a equipe (o Grupo da Equipe) tem proprietários e membros do grupo</span><span class="sxs-lookup"><span data-stu-id="7bfb4-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="7bfb4-131">Do site do SharePoint subjacente para a equipe (o Site da Equipe):</span><span class="sxs-lookup"><span data-stu-id="7bfb4-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="7bfb4-132">Os Administradores de Conjunto de Sites estão configurados para os proprietários de Grupo de Equipe</span><span class="sxs-lookup"><span data-stu-id="7bfb4-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="7bfb4-133">Para o Site de Equipe:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-133">For the Team Site:</span></span> 
    - <span data-ttu-id="7bfb4-134">O grupo do SharePoint de Proprietários de Site de Equipe, com o nível de permissão Controle Total, está definido para os proprietários de Grupo de Equipe</span><span class="sxs-lookup"><span data-stu-id="7bfb4-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="7bfb4-135">O grupo do SharePoint de Proprietários de Site de Equipe, com o nível de permissão Editar, está definido para os proprietários de Grupo de Equipe</span><span class="sxs-lookup"><span data-stu-id="7bfb4-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="7bfb4-136">O grupo do SharePoint de Visitantes de Site de Equipe, com o nível de permissão de Leitura, não tem grupos ou contas de usuários</span><span class="sxs-lookup"><span data-stu-id="7bfb4-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="7bfb4-137">Estas são as permissões padrão para o Site de Equipe.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-137">Here are the default permissions for the Team Site.</span></span>

![As permissões padrão de um Site de Equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="7bfb4-139">Se você visualizar o grupo do SharePoint de Proprietários de \<nome da equipe> para o nível de permissão Editar, ele não exibirá os Proprietários de \<nome da equipe>.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="7bfb4-140">As permissões resultantes permitem:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="7bfb4-141">Proprietários de Grupo de Equipe para administrar o site e ter controle total sobre o conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="7bfb4-142">Membros de Grupo de Equipe para criar e editar arquivos no site.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="7bfb4-143">A manutenção de permissões é igual para manutenção de proprietário e membro de equipe.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="7bfb4-144">Esta é a configuração resultante até o momento.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-144">Here’s the resulting configuration so far.</span></span>

![Etapa 2 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="7bfb4-146">Etapa 3: Configuração do site subjacente do SharePoint para segurança adicional</span><span class="sxs-lookup"><span data-stu-id="7bfb4-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="7bfb4-147">No Site da Equipe, defina estas configurações de permissão.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="7bfb4-148">Na barra de ferramentas, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="7bfb4-149">No painel de **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-149">In the **Site permissions** pane,, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="7bfb4-150">Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="7bfb4-151">Desabilite **Permitir solicitações de acesso** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="7bfb4-152">Com essas configurações, a capacidade de membros do Grupo de Equipe compartilharem o Site da Equipe com outros membros ou para que não membros possam solicitar acesso ao site é desabilitada.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="7bfb4-153">Esta é a configuração resultante até o momento.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-153">Here’s the resulting configuration so far.</span></span>

![Etapa 3 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="7bfb4-155">Etapa 4: Criação de um rótulo de retenção e uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="7bfb4-156">Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="7bfb4-157">Crie e publique um rótulo de retenção para dados altamente regulamentados (se necessário).</span><span class="sxs-lookup"><span data-stu-id="7bfb4-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="7bfb4-158">Configure o Site de Equipe para o rótulo de retenção criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="7bfb4-159">Crie uma política DLP para dados altamente regulamentados que usam o rótulo de retenção criado na etapa 2 e impede que os usuários enviem arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="7bfb4-160">Você também pode configurar a política para requisitos adicionais, como os de regulamentos do setor financeiro e de saúde, com base nos [modelos de política DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="7bfb4-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="7bfb4-161">Esta é a configuração resultante até o momento.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-161">Here’s the resulting configuration so far.</span></span>

![Etapa 4 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="7bfb4-163">Etapa 5: criação de rótulo ou sub-rótulo de rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="7bfb4-164">Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, uma equipe segura precisa de seu próprio rótulo ou sub-rótulo, assim os arquivos atribuídos:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="7bfb4-165">São criptografados e a criptografia acompanha o arquivo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="7bfb4-166">Contêm permissões personalizadas para que somente os membros do grupo de sites possam abri-lo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="7bfb4-167">Para atingir esse nível adicional de segurança para os arquivos armazenados no Site de Equipe, você deve configurar um novo rótulo de confidencialidade, que é um sub-rótulo do rótulo geral para arquivos altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="7bfb4-168">Somente os membros do Grupo de Equipe vão vê-los na lista de rótulos.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="7bfb4-169">Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para de uso global e equipes privadas individuais.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-169">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="7bfb4-170">Use um sub-rótulo de confidencialidade quando você tiver um grande número de rótulos ou quiser organizar rótulos para equipes privadas sob o rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="7bfb4-171">[Use estas instruçõess](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo separado ou um sub-rótulo com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="7bfb4-172">O nome do rótulo contém o nome da equipe</span><span class="sxs-lookup"><span data-stu-id="7bfb4-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="7bfb4-173">A criptografia está ativada</span><span class="sxs-lookup"><span data-stu-id="7bfb4-173">Encryption is enabled.</span></span>
- <span data-ttu-id="7bfb4-174">O Grupo de Equipe tem permissões de Coautoria</span><span class="sxs-lookup"><span data-stu-id="7bfb4-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="7bfb4-175">Esta é a configuração resultante com o novo rótulo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-175">Here’s the resulting configuration with the new label.</span></span>

![Etapa 5 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="7bfb4-177">Esta é a relação entre o rótulo de confidencialidade e o Grupo de Equipe.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Relação entre o Grupo de Equipe e as permissões de rótulo](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="7bfb4-179">Se você configurar o rótulo ou sub-rótulo de confidencialidade para permissões definidas pelo usuário ou com uma data de vencimento, não poderá abrir o arquivo no Teams ou no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint Online.</span></span> <span data-ttu-id="7bfb4-180">Você deve usar um aplicativo do Office.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-180">You must use an Office app.</span></span>
>

## <a name="using-the-team-and-a-sensitivity-label"></a><span data-ttu-id="7bfb4-181">Usando a equipe e um rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="7bfb4-181">Using the team and a sensitivity label</span></span>

<span data-ttu-id="7bfb4-182">Os membros do Grupo de Equipe podem acessar a equipe e todos os seus recursos, incluindo chats, reuniões e outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-182">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="7bfb4-183">Ao trabalhar com arquivos da seção de **Arquivos** de um canal, os membros do Grupo de Equipe devem atribuir o rótulo ou sub-rótulo de confidencialidade aos arquivos criados para a equipe segura.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-183">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="7bfb4-184">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-184">Here’s an example.</span></span>

![Exemplo de um rótulo aplicado a um arquivo em uma equipe segura](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="7bfb4-186">Quando o rótulo for aplicado ao arquivo, ele será protegido.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-186">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="7bfb4-187">Os membros do Grupo de Equipe podem abri-lo no Teams e colaborar em tempo real.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-187">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="7bfb4-188">Ele é criptografado e inclui as permissões de Coautor definidas para os membros do Grupo de Equipe.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-188">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="7bfb4-189">Se o arquivo sair do site e for encaminhado para um usuário mal-intencionado, eles terão que fornecer as credenciais de uma conta de usuário que seja membro do Grupo de Equipe para abrir o arquivo e exibir seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-189">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="7bfb4-190">Você pode ver quais arquivos têm um rótulo atribuído exibindo uma pasta no SharePoint Online e adicionando a coluna **Confidencialidade**através da opção **Mostrar/ocultar** colunas de **Adicionar coluna**.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-190">You can see which files have a label assigned by viewing a folder in SharePoint Online and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

## <a name="custom-permissions"></a><span data-ttu-id="7bfb4-191">Permissões personalizadas</span><span class="sxs-lookup"><span data-stu-id="7bfb4-191">Custom permissions</span></span>

<span data-ttu-id="7bfb4-192">Você também pode configurar permissões de site do SharePoint personalizadas para o Site da Equipe e, se necessário, seu rótulo de confidencialidade correspondente.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-192">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="7bfb4-193">Veja dois exemplos.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-193">Here are two examples based on SQL:</span></span>

### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="7bfb4-194">Exemplo 1: delegar a administração de sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="7bfb4-194">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="7bfb4-195">Se o proprietário da equipe não tiver experiência em administração do SharePoint ou desejar delegar a administração do Site de Equipe, ele poderá adicionar a conta de usuário de um administrador do SharePoint à lista de proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-195">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="7bfb4-196">No entanto, o administrador do SharePoint teria acesso total à equipe e a todos os seus recursos e poderia abrir um arquivo com o rótulo de confidencialidade aplicado.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-196">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="7bfb4-197">Para evitar essa concessão excessiva de privilégios, adicione a conta de usuário do administrador do SharePoint ao grupo de Proprietários do SharePoint de Site de Equipe nas configurações de permissões avançadas do site.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-197">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="7bfb4-198">O administrador do SharePoint pode administrar o site, mas não poderá acessar a equipe e nenhum de seus recursos ou abrir os arquivos com o rótulo de confidencialidade atribuído.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-198">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="7bfb4-199">Exemplo 2: permitir acesso somente de exibição a arquivos rotulados</span><span class="sxs-lookup"><span data-stu-id="7bfb4-199">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="7bfb4-200">Se algum membro da equipe precisar visualizar somente o conteúdo dos arquivos rotulados no Site da Equipe, adicione suas contas de usuário individuais ao:</span><span class="sxs-lookup"><span data-stu-id="7bfb4-200">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="7bfb4-201">Grupo do SharePoint de Visitantes de \<nome da equipe>, que por padrão tem o nível de permissão de Leitura.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-201">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="7bfb4-202">O rótulo de confidencialidade com as permissões de Visualizador.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-202">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="7bfb4-203">Estas são as permissões resultantes do rótulo.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-203">Here are the resulting permissions on the label.</span></span>

![Exemplo de permissões personalizadas para exibir arquivos rotulados](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="7bfb4-205">Os visitantes do site poderão acessar o Site da Equipe diretamente e visualizar o conteúdo dos arquivos aos quais o sub-rótulo foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-205">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="7bfb4-206">No entanto, como eles não são membros do Grupo de Equipe, não poderão acessar a equipe ou nenhum de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="7bfb4-206">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="7bfb4-207">Confira também</span><span class="sxs-lookup"><span data-stu-id="7bfb4-207">See also</span></span>

[<span data-ttu-id="7bfb4-208">Sites do SharePoint para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="7bfb4-208">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="7bfb4-209">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="7bfb4-209">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
