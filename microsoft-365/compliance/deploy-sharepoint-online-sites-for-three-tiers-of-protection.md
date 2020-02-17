---
title: Implantar sites do SharePoint Online para três camadas de proteção
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: 'Resumo: Crie e configure sites de equipe do SharePoint Online para vários níveis de proteção de informações.'
ms.openlocfilehash: 1827c4a19cfd31a236dfbd58e454c610cae14477
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075501"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="e5354-103">Implantar sites do SharePoint Online para três camadas de proteção</span><span class="sxs-lookup"><span data-stu-id="e5354-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="e5354-p101">Use as etapas neste artigo para projetar e implantar sites de equipe do SharePoint Online de linha de base, confidenciais e altamente confidenciais. Para obter mais informações sobre essas três camadas de proteção, consulte [Arquivos e sites do SharePoint Online seguros](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="e5354-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="e5354-106">Sites de equipe do SharePoint Online de linha de base</span><span class="sxs-lookup"><span data-stu-id="e5354-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="e5354-p102">A proteção de linha de base inclui os sites de equipe públicos e privados. Os sites de equipe públicos podem ser descobertos e acessados por qualquer pessoa na organização. Os sites privados podem ser descobertos e acessados somente por membros do grupo do Office 365 associado ao site de equipe. Esses dois tipos de sites de equipe permitem que os membros compartilhem o site com outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="e5354-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="e5354-111">Público</span><span class="sxs-lookup"><span data-stu-id="e5354-111">Public</span></span>

<span data-ttu-id="e5354-112">Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso público, siga [essas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e5354-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e5354-113">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e5354-113">Here is your resulting configuration.</span></span>
  
![Proteção de nível de linha de base para um site de equipe do SharePoint Online público.](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="e5354-115">Privado</span><span class="sxs-lookup"><span data-stu-id="e5354-115">Private</span></span>

<span data-ttu-id="e5354-116">Para criar um site de equipe do SharePoint Online de linha de base com permissões e acesso privado, siga [essas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e5354-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="e5354-117">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e5354-117">Here is your resulting configuration.</span></span>
  
![Proteção de nível de linha de base para um site de equipe do SharePoint Online privado.](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="e5354-119">Sites confidenciais de equipe do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e5354-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="e5354-120">Sites de equipe Confidenciais do SharePoint Online são iniciados como um site de equipe privado.</span><span class="sxs-lookup"><span data-stu-id="e5354-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="e5354-121">Primeiro, crie o site de equipe do SharePoint Online privado com [estas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e5354-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e5354-122">Em seguida, no novo site de equipe do SharePoint Online, configure as permissões adicionais com estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e5354-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="e5354-123">Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="e5354-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="e5354-124">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="e5354-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="e5354-125">Em **Permissões de compartilhamento**, selecione **Somente proprietários do site podem compartilhar arquivos, pastas e o site** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e5354-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="e5354-126">Os resultados dessas configurações de permissão são:</span><span class="sxs-lookup"><span data-stu-id="e5354-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="e5354-127">A capacidade dos membros de compartilhar com outros membros está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e5354-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="e5354-128">A capacidade de não membros solicitarem o acesso está habilitada.</span><span class="sxs-lookup"><span data-stu-id="e5354-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="e5354-129">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e5354-129">Here is your resulting configuration.</span></span>
  
![Proteção de nível confidencial para um site de equipe isolado do SharePoint Online.](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="e5354-131">Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site.</span><span class="sxs-lookup"><span data-stu-id="e5354-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="e5354-132">Sites de equipe do SharePoint Online altamente confidenciais</span><span class="sxs-lookup"><span data-stu-id="e5354-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="e5354-133">Um site de equipe do SharePoint Online altamente confidencial é um site de equipe privado com configurações de permissões adicionais.</span><span class="sxs-lookup"><span data-stu-id="e5354-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="e5354-134">Primeiro, crie o site de equipe do SharePoint Online privado com [estas instruções](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span><span class="sxs-lookup"><span data-stu-id="e5354-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="e5354-135">Em seguida, no novo site de equipe do SharePoint Online, configure as permissões adicionais com estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e5354-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="e5354-136">Na barra de ferramentas do site de equipe do SharePoint, clique no ícone de configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="e5354-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="e5354-137">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="e5354-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="e5354-138">Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.</span><span class="sxs-lookup"><span data-stu-id="e5354-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="e5354-139">Desative **Permitir solicitações de acesso** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e5354-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="e5354-140">Os resultados dessas configurações de permissão são:</span><span class="sxs-lookup"><span data-stu-id="e5354-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="e5354-141">A capacidade dos membros de compartilhar com outros membros está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e5354-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="e5354-142">A capacidade de não membros solicitarem o acesso está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="e5354-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="e5354-143">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="e5354-143">Here is your resulting configuration.</span></span>
  
![Proteção com alto nível de confidencialidade para um site de equipe isolado do SharePoint Online.](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="e5354-145">Os membros do site, por meio da associação de grupo em um dos grupos de acesso, agora podem colaborar com segurança nos recursos do site.</span><span class="sxs-lookup"><span data-stu-id="e5354-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="e5354-146">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e5354-146">Next step</span></span>

[<span data-ttu-id="e5354-147">Proteger arquivos do SharePoint Online com DLP e rótulos do Office 365</span><span class="sxs-lookup"><span data-stu-id="e5354-147">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="e5354-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="e5354-148">See also</span></span>

[<span data-ttu-id="e5354-149">Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações do Agile</span><span class="sxs-lookup"><span data-stu-id="e5354-149">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="e5354-150">Adoção da nuvem e de soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="e5354-150">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
