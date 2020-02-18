---
title: Implantar equipes para três camadas de proteção para arquivos
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Crie e configure equipes com o Microsoft Teams para vários níveis de proteção de informações para arquivos.
ms.openlocfilehash: 63a4b6763165f38e1de5331324e5a7b3573ea0f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083314"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="7bca2-103">Implantar equipes para três camadas de proteção para arquivos</span><span class="sxs-lookup"><span data-stu-id="7bca2-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="7bca2-104">Use as etapas neste artigo para projetar e implantar equipes de linha de base, confidenciais e altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="7bca2-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="7bca2-105">Para obter mais informações sobre essas três camadas de proteção, confira [Proteção de arquivos no Microsoft Teams](secure-files-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7bca2-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="7bca2-106">Equipes de linha de base</span><span class="sxs-lookup"><span data-stu-id="7bca2-106">Baseline teams</span></span>

<span data-ttu-id="7bca2-107">A proteção de linha de base inclui as equipes públicas e privadas.</span><span class="sxs-lookup"><span data-stu-id="7bca2-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="7bca2-108">As equipes públicas podem ser descobertas e acessadas por qualquer pessoa na organização.</span><span class="sxs-lookup"><span data-stu-id="7bca2-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="7bca2-109">Os sites privados podem ser descobertos e acessados somente por membros do grupo do Office 365 associado à equipe.</span><span class="sxs-lookup"><span data-stu-id="7bca2-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="7bca2-110">Ambos os tipos de equipes permitem aos membros compartilhar o site com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="7bca2-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="7bca2-111">Público</span><span class="sxs-lookup"><span data-stu-id="7bca2-111">Public</span></span>

<span data-ttu-id="7bca2-112">Siga as instruções [neste artigo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) para criar uma equipe de base com acesso e permissões públicas.</span><span class="sxs-lookup"><span data-stu-id="7bca2-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with public access and permissions.</span></span>

<span data-ttu-id="7bca2-113">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="7bca2-113">Here is your resulting configuration.</span></span>

![Proteção de nível de linha de base para uma equipe pública.](../../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="7bca2-115">Privado</span><span class="sxs-lookup"><span data-stu-id="7bca2-115">Private</span></span>

<span data-ttu-id="7bca2-116">Siga as instruções [neste artigo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) para criar uma equipe de base com acesso e permissões privadas.</span><span class="sxs-lookup"><span data-stu-id="7bca2-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline Team with private access and permissions.</span></span>

<span data-ttu-id="7bca2-117">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="7bca2-117">Here is your resulting configuration.</span></span>

![Proteção de nível de linha de base para uma equipe privada.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="7bca2-119">Dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="7bca2-119">Sensitive teams</span></span>

<span data-ttu-id="7bca2-120">Para uma equipe confidencial, comece [criando uma equipe privada](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="7bca2-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="7bca2-121">Em seguida, configure o site subjacente do SharePoint para evitar o compartilhamento por membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="7bca2-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="7bca2-122">Na barra de ferramentas da equipe, clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="7bca2-123">Clique nas reticências e em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="7bca2-124">Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="7bca2-125">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="7bca2-126">Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="7bca2-127">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="7bca2-127">Here is your resulting configuration.</span></span>

![Proteção confidencial para uma equipe.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="7bca2-129">Equipes altamente confidenciais</span><span class="sxs-lookup"><span data-stu-id="7bca2-129">Highly confidential teams</span></span>

<span data-ttu-id="7bca2-130">Com uma equipe altamente confidencial, comece [criando uma equipe privada](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span><span class="sxs-lookup"><span data-stu-id="7bca2-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="7bca2-131">Em seguida, configure o site subjacente do SharePoint para evitar compartilhamentos por membros da equipe e solicitações de acesso por não membros da equipe.</span><span class="sxs-lookup"><span data-stu-id="7bca2-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="7bca2-132">Na barra de ferramentas da equipe, clique em **Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="7bca2-133">Clique nas reticências e em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="7bca2-134">Na barra de ferramentas do site do SharePoint subjacente, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="7bca2-135">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="7bca2-136">Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="7bca2-137">Desative **Permitir solicitações de acesso** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7bca2-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="7bca2-138">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="7bca2-138">Here is your resulting configuration.</span></span>

![Proteção altamente confidencial para uma equipe.](../../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="7bca2-140">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7bca2-140">Next step</span></span>

[<span data-ttu-id="7bca2-141">Proteger arquivos em equipes com rótulos de retenção e DLP</span><span class="sxs-lookup"><span data-stu-id="7bca2-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="7bca2-142">Confira também</span><span class="sxs-lookup"><span data-stu-id="7bca2-142">See also</span></span>

[<span data-ttu-id="7bca2-143">Proteger arquivos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7bca2-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="7bca2-144">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="7bca2-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
