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
ms.openlocfilehash: 4ef4d4e9b8ab437c90aac434db158cfb40f066cb
ms.sourcegitcommit: 7ee256132358a86f8c6ad143816fcfdde011ca74
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "37628345"
---
# <a name="teams-for-highly-regulated-data"></a><span data-ttu-id="25ed4-103">Teams para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="25ed4-103">Microsoft Teams for highly regulated data</span></span>

<span data-ttu-id="25ed4-104">Este artigo fornece recomendações e passo a passo para configurar uma equipe privada no Microsoft Teams que bloqueia o acesso aos recursos do Teams, como chats, reuniões e arquivos, somente para membros e proprietários do grupo do Office 365 da equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams that locks down access to Teams features—such as chats, meetings, and files—to only members and owners of the Office 365 group for the team.</span></span> 

<span data-ttu-id="25ed4-105">Além do acesso privado baseado no grupo do Office 365, este artigo descreve como configurar o site de equipe particular e subjacente do SharePoint, que você pode na seção de **Arquivos** de um canal de equipe e obter a segurança adicional necessária para armazenar dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="25ed4-105">Beyond the private access based on the Office 365 group, this article describes how to configure the underlying private SharePoint team site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span> <span data-ttu-id="25ed4-106">Neste site de equipe do SharePoint, você pode armazenar e colaborar em arquivos, páginas, um calendário compartilhado, tarefas, um bloco de anotações e listas.</span><span class="sxs-lookup"><span data-stu-id="25ed4-106">On this SharePoint team site, you can store and collaborate on files, pages, a shared calendar, tasks, a notebook, and lists.</span></span>

<span data-ttu-id="25ed4-107">Os elementos de configuração de uma equipe para dados altamente regulamentados são:</span><span class="sxs-lookup"><span data-stu-id="25ed4-107">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="25ed4-108">Uma equipe privada com um grupo correspondente do Office 365 que tem contas de usuário de proprietário e membro.</span><span class="sxs-lookup"><span data-stu-id="25ed4-108">A private team with a corresponding Office 365 group that has owner and member user accounts.</span></span>
- <span data-ttu-id="25ed4-109">Segurança adicional no site subjacente do SharePoint para a equipe que:</span><span class="sxs-lookup"><span data-stu-id="25ed4-109">Additional security on the underlying SharePoint site for the team that:</span></span>
  - <span data-ttu-id="25ed4-110">Impede que membros do site concedam acesso a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="25ed4-110">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="25ed4-111">Impede que não membros do site solicitem acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="25ed4-111">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="25ed4-112">Um rótulo de retenção do Office 365 para o site do SharePoint subjacente que é aplicado automaticamente a novos arquivos no site como uma maneira padrão de definir políticas de retenção.</span><span class="sxs-lookup"><span data-stu-id="25ed4-112">An Office 365 retention label for the underlying SharePoint site that is automatically applied to new files on the site as a default way to define retention policies.</span></span>
- <span data-ttu-id="25ed4-113">Uma política de Prevenção contra Perda de Dados (DLP) que usa o rótulo de retenção e impede que os usuários compartilhem ou enviem arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="25ed4-113">A Data Loss Prevention (DLP) policy that uses the retention label and blocks users from sharing or sending files outside the organization.</span></span>
- <span data-ttu-id="25ed4-114">Um rótulo de confidencialidade do Office 365 de ou sub-rótulo de um rótulo altamente regulamentado com criptografia habilitada e permissões de Coautor para o grupo da equipe do Office 365.</span><span class="sxs-lookup"><span data-stu-id="25ed4-114">An Office 365 sensitivity label or a sublabel of a highly regulated label that has encryption enabled and Co-Author permissions for the Office 365 group of the team.</span></span> <span data-ttu-id="25ed4-115">Os usuários aplicam o rótulo ou sub-rótulo aos arquivos armazenados na seção de **Arquivos** da equipe na opção da barra de menus Confidencialidade do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="25ed4-115">Users apply the label or sublabel to files stored in **Files** section of the team from the Sensitivity menu bar option in Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="25ed4-116">Esta é a configuração resultante com um rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="25ed4-116">Here is the resulting configuration with a sensitivity label.</span></span>

![A configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)
 
## <a name="phase-1-configure-a-team-for-highly-regulated-data"></a><span data-ttu-id="25ed4-118">Fase 1: Configurar uma equipe para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="25ed4-118">Phase 1: Configure a team for highly regulated data</span></span>

<span data-ttu-id="25ed4-119">A configuração de ponta a ponta consiste nas seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="25ed4-119">The end-to-end configuration consists of these steps:</span></span>

1. <span data-ttu-id="25ed4-120">Configurações de identidade e acesso a dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-120">Configure identity and device access.</span></span>
2. <span data-ttu-id="25ed4-121">Criação de uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="25ed4-121">Create a team</span></span>
3. <span data-ttu-id="25ed4-122">Configuração de site do SharePoint subjacente para segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="25ed4-122">Configure the underlying SharePoint site for additional security.</span></span>
4. <span data-ttu-id="25ed4-123">Criação de um rótulo de retenção e uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="25ed4-123">Create a retention label and DLP policy.</span></span>
5. <span data-ttu-id="25ed4-124">Criação de rótulo ou sub-rótulo de rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="25ed4-124">Create the label or sublabel of the highly regulated label.</span></span>

### <a name="step-1-configure-identity-and-device-access"></a><span data-ttu-id="25ed4-125">Etapa 1: configurações de identidade e acesso a dispositivo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-125">Step 1: Configure identity and device access</span></span>

<span data-ttu-id="25ed4-126">Para proteger o acesso à equipe e ao site do SharePoint subjacente, assegure-se de ter configurado as[políticas de identidade e acesso a dispositivo](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) e as [políticas de acesso do SharePoint Online](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies) recomendadas.</span><span class="sxs-lookup"><span data-stu-id="25ed4-126">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies) and the [recommended SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>

### <a name="step-2-create-a-private-team"></a><span data-ttu-id="25ed4-127">Etapa 2: criação de uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="25ed4-127">Step 2: Create a private team</span></span>

<span data-ttu-id="25ed4-128">Use [essas instruções](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) para criar uma equipe privada.</span><span class="sxs-lookup"><span data-stu-id="25ed4-128">Follow [these instructions](https://support.office.com/article/create-a-team-from-scratch-174adf5f-846b-4780-b765-de1a0a737e2b) to create a private SharePoint team site.</span></span>

<span data-ttu-id="25ed4-129">Ao criar uma equipe privada, estas são as permissões padrão:</span><span class="sxs-lookup"><span data-stu-id="25ed4-129">When you create a private team, here are the default permissions:</span></span>

- <span data-ttu-id="25ed4-130">O grupo do Office 365 para a equipe (o Grupo da Equipe) tem proprietários e membros do grupo</span><span class="sxs-lookup"><span data-stu-id="25ed4-130">The Office 365 group for the team (the Team Group) has group owners and group members</span></span>
- <span data-ttu-id="25ed4-131">Do site do SharePoint subjacente para a equipe (o Site da Equipe):</span><span class="sxs-lookup"><span data-stu-id="25ed4-131">For the underlying SharePoint site for the team (the Team Site):</span></span>
  - <span data-ttu-id="25ed4-132">Os Administradores de Conjunto de Sites estão configurados para os proprietários de Grupo de Equipe</span><span class="sxs-lookup"><span data-stu-id="25ed4-132">The Site Collection Administrators is configured for the Team Group owners</span></span>
  - <span data-ttu-id="25ed4-133">Para o Site de Equipe:</span><span class="sxs-lookup"><span data-stu-id="25ed4-133">For the Team Site:</span></span> 
    - <span data-ttu-id="25ed4-134">O grupo do SharePoint de Proprietários de Site de Equipe, com o nível de permissão Controle Total, está definido para os proprietários de Grupo de Equipe</span><span class="sxs-lookup"><span data-stu-id="25ed4-134">The Team Site Owners SharePoint group—with the Full Control permission level—is set to the Team Group owners</span></span>
    - <span data-ttu-id="25ed4-135">O grupo do SharePoint de Proprietários de Site de Equipe, com o nível de permissão Editar, está definido para os proprietários de Grupo de Equipe</span><span class="sxs-lookup"><span data-stu-id="25ed4-135">The Team Site Members SharePoint group—with the Edit permission level—is set to the Team Group members</span></span>
    - <span data-ttu-id="25ed4-136">O grupo do SharePoint de Visitantes de Site de Equipe, com o nível de permissão de Leitura, não tem grupos ou contas de usuários</span><span class="sxs-lookup"><span data-stu-id="25ed4-136">The Team Site Visitors SharePoint group—with the Read permission level—has no groups or user accounts</span></span>

<span data-ttu-id="25ed4-137">Estas são as permissões padrão para o Site de Equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-137">Here are the default permissions for the Team Site.</span></span>

![As permissões padrão de um Site de Equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-default-site-permissions.png)
 
>[!Note]
><span data-ttu-id="25ed4-139">Se você visualizar o grupo do SharePoint de Proprietários de \<nome da equipe> para o nível de permissão Editar, ele não exibirá os Proprietários de \<nome da equipe>.</span><span class="sxs-lookup"><span data-stu-id="25ed4-139">If you view the \<team name> Owners SharePoint group for the Edit permission level, it does not display \<team name> Owners.</span></span>
>

<span data-ttu-id="25ed4-140">As permissões resultantes permitem:</span><span class="sxs-lookup"><span data-stu-id="25ed4-140">The resulting permissions allow:</span></span>

- <span data-ttu-id="25ed4-141">Proprietários de Grupo de Equipe para administrar o site e ter controle total sobre o conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="25ed4-141">Team Group owners to administer the site and have full control over the site contents.</span></span>
- <span data-ttu-id="25ed4-142">Membros de Grupo de Equipe para criar e editar arquivos no site.</span><span class="sxs-lookup"><span data-stu-id="25ed4-142">Team Group members to create and edit files on the site.</span></span> 

<span data-ttu-id="25ed4-143">A manutenção de permissões é igual para manutenção de proprietário e membro de equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-143">Permissions maintenance is the same as team member and owner maintenance.</span></span>

<span data-ttu-id="25ed4-144">Esta é a configuração resultante até o momento.</span><span class="sxs-lookup"><span data-stu-id="25ed4-144">Here’s the resulting configuration so far.</span></span>

![Etapa 2 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step2.png)
 
### <a name="step-3-configure-the-underlying-sharepoint-site-for-additional-security"></a><span data-ttu-id="25ed4-146">Etapa 3: Configuração do site subjacente do SharePoint para segurança adicional</span><span class="sxs-lookup"><span data-stu-id="25ed4-146">Step 3: Configure the underlying SharePoint site for additional security</span></span>

<span data-ttu-id="25ed4-147">No Site da Equipe, defina estas configurações de permissão.</span><span class="sxs-lookup"><span data-stu-id="25ed4-147">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="25ed4-148">Na barra de ferramentas, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="25ed4-148">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="25ed4-149">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="25ed4-149">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="25ed4-150">Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.</span><span class="sxs-lookup"><span data-stu-id="25ed4-150">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="25ed4-151">Desabilite **Permitir solicitações de acesso** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="25ed4-151">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="25ed4-152">Com essas configurações, a capacidade de membros do Grupo de Equipe compartilharem o Site da Equipe com outros membros ou para que não membros possam solicitar acesso ao site é desabilitada.</span><span class="sxs-lookup"><span data-stu-id="25ed4-152">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

<span data-ttu-id="25ed4-153">Esta é a configuração resultante até o momento.</span><span class="sxs-lookup"><span data-stu-id="25ed4-153">Here’s the resulting configuration so far.</span></span>

![Etapa 3 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step3.png)

 
### <a name="step-4-create-a-retention-label-and-dlp-policy"></a><span data-ttu-id="25ed4-155">Etapa 4: Criação de um rótulo de retenção e uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="25ed4-155">Step 4: Create a retention label and DLP policy</span></span>

<span data-ttu-id="25ed4-156">Use [estas instruções](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="25ed4-156">Use [these instructions](https://docs.microsoft.com/microsoft-365/compliance/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="25ed4-157">Crie e publique um rótulo de retenção para dados altamente regulamentados (se necessário).</span><span class="sxs-lookup"><span data-stu-id="25ed4-157">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="25ed4-158">Configure o Site de Equipe para o rótulo de retenção criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="25ed4-158">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="25ed4-159">Crie uma política DLP para dados altamente regulamentados que usam o rótulo de retenção criado na etapa 2 e impede que os usuários enviem arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="25ed4-159">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span> <span data-ttu-id="25ed4-160">Você também pode configurar a política para requisitos adicionais, como os de regulamentos do setor financeiro e de saúde, com base nos [modelos de política DLP](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="25ed4-160">You can also configure the policy for additional requirements, such as those for health and financial industry regulations, based on [DLP policy templates](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies#dlp-policy-templates).</span></span>

<span data-ttu-id="25ed4-161">Esta é a configuração resultante até o momento.</span><span class="sxs-lookup"><span data-stu-id="25ed4-161">Here’s the resulting configuration so far.</span></span>

![Etapa 4 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-step4.png)
 
### <a name="step-5-create-the-label-or-a-sublabel-of-the-highly-regulated-label"></a><span data-ttu-id="25ed4-163">Etapa 5: criação de rótulo ou sub-rótulo de rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="25ed4-163">Step 5: Create the label or a sublabel of the highly regulated label</span></span>

<span data-ttu-id="25ed4-164">Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, uma equipe segura precisa de seu próprio rótulo ou sub-rótulo, assim os arquivos atribuídos:</span><span class="sxs-lookup"><span data-stu-id="25ed4-164">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="25ed4-165">São criptografados e a criptografia acompanha o arquivo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-165">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="25ed4-166">Contêm permissões personalizadas para que somente os membros do grupo de sites possam abri-lo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-166">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="25ed4-167">Para atingir esse nível adicional de segurança para os arquivos armazenados no Site de Equipe, você deve configurar um novo rótulo de confidencialidade, que é um sub-rótulo do rótulo geral para arquivos altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="25ed4-167">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="25ed4-168">Somente os membros do Grupo de Equipe vão vê-los na lista de rótulos.</span><span class="sxs-lookup"><span data-stu-id="25ed4-168">Only Team Group members will see it in their list of labels.</span></span>

<span data-ttu-id="25ed4-169">Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para uso global e equipes privadas individuais.</span><span class="sxs-lookup"><span data-stu-id="25ed4-169">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="25ed4-170">Use um sub-rótulo de confidencialidade quando você tiver um grande número de rótulos ou quiser organizar rótulos para equipes privadas sob o rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="25ed4-170">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams the under the highly regulated label.</span></span>

<span data-ttu-id="25ed4-171">[Use estas instruçõess](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo separado ou um sub-rótulo com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="25ed4-171">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="25ed4-172">O nome do rótulo contém o nome da equipe</span><span class="sxs-lookup"><span data-stu-id="25ed4-172">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="25ed4-173">A criptografia está ativada</span><span class="sxs-lookup"><span data-stu-id="25ed4-173">Encryption is enabled.</span></span>
- <span data-ttu-id="25ed4-174">O Grupo de Equipe tem permissões de Coautoria</span><span class="sxs-lookup"><span data-stu-id="25ed4-174">The Team Group has Co-Author permissions</span></span>

<span data-ttu-id="25ed4-175">Esta é a configuração resultante com o novo rótulo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-175">Here’s the resulting configuration with the new label.</span></span>

![Etapa 5 da configuração segura do cenário de equipe](./media/secure-teams-highly-regulated-data-scenario/secure-team-final.png)

<span data-ttu-id="25ed4-177">Esta é a relação entre o rótulo de confidencialidade e o Grupo de Equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-177">Here’s the relationship between the sensitivity label and the Team Group.</span></span>

![Relação entre o Grupo de Equipe e as permissões de rótulo](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-permissions.png)


>[!Note]
><span data-ttu-id="25ed4-179">Se você configurar o rótulo ou sub-rótulo de confidencialidade para permissões definidas pelo usuário ou com uma data de validade, não poderá abrir o arquivo no Teams ou no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="25ed4-179">If you configure the sensitivity label or sublabel for user-defined permissions or with an expiration date, you cannot open the file from Teams or SharePoint.</span></span> <span data-ttu-id="25ed4-180">Você deve usar um aplicativo do Office.</span><span class="sxs-lookup"><span data-stu-id="25ed4-180">You must use an Office app.</span></span>
>

### <a name="custom-permissions"></a><span data-ttu-id="25ed4-181">Permissões personalizadas</span><span class="sxs-lookup"><span data-stu-id="25ed4-181">Custom permissions</span></span>

<span data-ttu-id="25ed4-182">Você também pode configurar permissões de site do SharePoint personalizadas para o Site da Equipe e, se necessário, seu rótulo de confidencialidade correspondente.</span><span class="sxs-lookup"><span data-stu-id="25ed4-182">You can also configure custom SharePoint site permissions for the Team Site and, if needed, its corresponding sensitivity label.</span></span> <span data-ttu-id="25ed4-183">Veja dois exemplos.</span><span class="sxs-lookup"><span data-stu-id="25ed4-183">Here are two examples based on SQL:</span></span>

#### <a name="example-1-delegating-sharepoint-site-administration"></a><span data-ttu-id="25ed4-184">Exemplo 1: delegar a administração de sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="25ed4-184">Example 1: Delegating SharePoint site administration</span></span>

<span data-ttu-id="25ed4-185">Se o proprietário da equipe não tiver experiência em administração do SharePoint ou desejar delegar a administração do Site de Equipe, ele poderá adicionar a conta de usuário de um administrador do SharePoint à lista de proprietários da equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-185">If the team owner does not have SharePoint administration experience or wants to delegate administration of the Team Site, they could add the user account of a SharePoint administrator to the list of team owners.</span></span> <span data-ttu-id="25ed4-186">No entanto, o administrador do SharePoint teria acesso total à equipe e a todos os seus recursos e poderia abrir um arquivo com o rótulo de confidencialidade aplicado.</span><span class="sxs-lookup"><span data-stu-id="25ed4-186">But then the SharePoint administrator would have full access to the team and all its resources and would be able to open a file with the sensitivity label applied.</span></span> 

<span data-ttu-id="25ed4-187">Para evitar essa concessão excessiva de privilégios, adicione a conta de usuário do administrador do SharePoint ao grupo de Proprietários do SharePoint de Site de Equipe nas configurações de permissões avançadas do site.</span><span class="sxs-lookup"><span data-stu-id="25ed4-187">To prevent this over-granting of privileges, add the user account of the SharePoint administrator to the Team Site Owners SharePoint group in the advanced permissions settings of the site.</span></span> <span data-ttu-id="25ed4-188">O administrador do SharePoint pode administrar o site, mas não poderá acessar a equipe e nenhum de seus recursos ou abrir os arquivos com o rótulo de confidencialidade atribuído.</span><span class="sxs-lookup"><span data-stu-id="25ed4-188">The SharePoint administrator can administer the site but will not be able to access the team and any of its resources or open the files with the sensitivity label assigned.</span></span>

#### <a name="example-2-allowing-view-only-access-to-labeled-files"></a><span data-ttu-id="25ed4-189">Exemplo 2: permitir acesso somente de exibição a arquivos rotulados</span><span class="sxs-lookup"><span data-stu-id="25ed4-189">Example 2: Allowing view-only access to labeled files</span></span>

<span data-ttu-id="25ed4-190">Se algum membro da equipe precisar visualizar somente o conteúdo dos arquivos rotulados no Site da Equipe, adicione suas contas de usuário individuais ao:</span><span class="sxs-lookup"><span data-stu-id="25ed4-190">If some staff only need to view the contents of labeled files in the Team Site, add their individual user accounts to the:</span></span>

- <span data-ttu-id="25ed4-191">Grupo do SharePoint de Visitantes de \<nome da equipe>, que por padrão tem o nível de permissão de Leitura.</span><span class="sxs-lookup"><span data-stu-id="25ed4-191">\<team name> Visitors SharePoint group, which by default has the Read permission level.</span></span> 
- <span data-ttu-id="25ed4-192">O rótulo de confidencialidade com as permissões de Visualizador.</span><span class="sxs-lookup"><span data-stu-id="25ed4-192">The sensitivity label with the Viewer permissions.</span></span>

<span data-ttu-id="25ed4-193">Estas são as permissões resultantes do rótulo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-193">Here are the resulting permissions on the label.</span></span>

![Exemplo de permissões personalizadas para exibir arquivos rotulados](./media/secure-teams-highly-regulated-data-scenario/secure-team-custom-view-permissions.png)
 
<span data-ttu-id="25ed4-195">Os visitantes do site poderão acessar o Site da Equipe diretamente e visualizar o conteúdo dos arquivos aos quais o sub-rótulo foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="25ed4-195">The site visitors will be able to access the Team Site directly and view the contents of files that have the sublabel applied.</span></span> <span data-ttu-id="25ed4-196">No entanto, como eles não são membros do Grupo de Equipe, não poderão acessar a equipe ou nenhum de seus recursos.</span><span class="sxs-lookup"><span data-stu-id="25ed4-196">But because they are not members of the Team Group, they will not be able to access the team or any of its resources.</span></span>


## <a name="phase-2-drive-user-adoption-for-team-members"></a><span data-ttu-id="25ed4-197">Fase 2: Impulsionar a adoção do usuário para membros da equipe</span><span class="sxs-lookup"><span data-stu-id="25ed4-197">Phase 2: Drive user adoption for remote workers</span></span>

<span data-ttu-id="25ed4-198">Com a equipe no local, é hora de impulsionar a adoção dessa equipe e sua segurança adicional aos membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-198">With the team in place, it’s time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="25ed4-199">Etapa 1: treinar os usuários</span><span class="sxs-lookup"><span data-stu-id="25ed4-199">Step 1: Train your users</span></span>

<span data-ttu-id="25ed4-200">Os membros do Grupo de Equipe podem acessar a equipe e todos os seus recursos, incluindo chats, reuniões e outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="25ed4-200">Members of the Team Group can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="25ed4-201">Ao trabalhar com arquivos da seção de **Arquivos** de um canal, os membros do Grupo de Equipe devem atribuir o rótulo ou sub-rótulo de confidencialidade aos arquivos criados para a equipe segura.</span><span class="sxs-lookup"><span data-stu-id="25ed4-201">When working with files from the **Files** section of a channel, members of the Team Group must assign the sensitivity label or sublabel to files created for the secure team.</span></span> <span data-ttu-id="25ed4-202">Veja um exemplo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-202">Here’s an example.</span></span>

![Exemplo de um rótulo aplicado a um arquivo em uma equipe segura](./media/secure-teams-highly-regulated-data-scenario/secure-team-label-applied.png)
 
<span data-ttu-id="25ed4-204">Quando o rótulo for aplicado ao arquivo, ele será protegido.</span><span class="sxs-lookup"><span data-stu-id="25ed4-204">When the label gets applied to the file it is secured.</span></span> <span data-ttu-id="25ed4-205">Os membros do Grupo de Equipe podem abri-lo no Teams e colaborar em tempo real.</span><span class="sxs-lookup"><span data-stu-id="25ed4-205">Members of the Team Group can open it in Teams and collaborate in real time.</span></span> <span data-ttu-id="25ed4-206">Ele é criptografado e inclui as permissões de Coautor definidas para os membros do Grupo de Equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-206">It is encrypted and includes the Co-Author permissions set to the Team Group members.</span></span> <span data-ttu-id="25ed4-207">Se o arquivo sair do site e for encaminhado para um usuário mal-intencionado, eles terão que fornecer as credenciais de uma conta de usuário que seja membro do Grupo de Equipe para abrir o arquivo e exibir seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="25ed4-207">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the Team Group to open the file and view its contents.</span></span> 

<span data-ttu-id="25ed4-208">Treine os membros da sua equipe:</span><span class="sxs-lookup"><span data-stu-id="25ed4-208">Train your team members:</span></span>

- <span data-ttu-id="25ed4-209">Sobre a importância de usar a nova equipe para bate-papos, reuniões, arquivos e outros recursos do Site da Equipe e as consequências de um vazamento de dados altamente regulamentados, como ramificações legais, multas regulatórias, ransomware ou perda de vantagem competitiva.</span><span class="sxs-lookup"><span data-stu-id="25ed4-209">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="25ed4-210">Como acessar a equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-210">How to access the team.</span></span>
- <span data-ttu-id="25ed4-211">Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="25ed4-211">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="25ed4-212">Como a política DLP bloqueia o compartilhamento de arquivos externamente por parte do usuário.</span><span class="sxs-lookup"><span data-stu-id="25ed4-212">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="25ed4-213">Como rotular arquivos com o rótulo personalizado ou sub-rótulo da equipe.</span><span class="sxs-lookup"><span data-stu-id="25ed4-213">How to label files with the custom label or sublabel for the team.</span></span>
- <span data-ttu-id="25ed4-214">Como o rótulo ou o sub-rótulo protege os arquivos, mesmo quando vazam do site.</span><span class="sxs-lookup"><span data-stu-id="25ed4-214">How the label or sublabel protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="25ed4-215">Esse treinamento deve incluir exercícios práticos para que os membros da sua equipe possam experimentar esses recursos e seus resultados.</span><span class="sxs-lookup"><span data-stu-id="25ed4-215">This training should include hands-on exercises so that your students can experience these capabilities and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="25ed4-216">Etapa 2: Realize análises de uso periódicas e gerencie os comentários dos membros da equipe</span><span class="sxs-lookup"><span data-stu-id="25ed4-216">Step 2: Conduct periodic reviews of usage and address worker feedback</span></span>

<span data-ttu-id="25ed4-217">Nas semanas após o treinamento:</span><span class="sxs-lookup"><span data-stu-id="25ed4-217">In the weeks after training:</span></span>

- <span data-ttu-id="25ed4-218">Aborde rapidamente os comentários dos membros da equipe e ajuste as políticas e configurações.</span><span class="sxs-lookup"><span data-stu-id="25ed4-218">Quickly address remote worker feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="25ed4-219">Analise o uso da equipe e compare-o com as expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="25ed4-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="25ed4-220">Verifique se os arquivos altamente regulamentados foram rotulados corretamente com o rótulo ou sub-rótulo de confidencialidade personalizado.</span><span class="sxs-lookup"><span data-stu-id="25ed4-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

  <span data-ttu-id="25ed4-221">Você pode verificar quais arquivos têm um rótulo atribuído exibindo uma pasta no SharePoint e adicionando a coluna **Confidencialidade** por meio da opção **Mostrar/ocultar colunas** da **coluna Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="25ed4-221">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="25ed4-222">Repita o treinamento dos usuários conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="25ed4-222">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="25ed4-223">Confira também</span><span class="sxs-lookup"><span data-stu-id="25ed4-223">See also</span></span>

[<span data-ttu-id="25ed4-224">Sites do SharePoint para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="25ed4-224">SharePoint sites for highly regulated data</span></span>](teams-sharepoint-online-sites-highly-regulated-data.md)

[<span data-ttu-id="25ed4-225">Cargas de trabalho e cenários do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="25ed4-225">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="25ed4-226">[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="25ed4-226">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="25ed4-227">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="25ed4-227">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
