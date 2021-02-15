---
title: Equipe isolada para um projeto secreto da Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: como a Contoso usou uma equipe com isolamento de segurança para um projeto secreto para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: b8794502afcb77a8e597a1b05dfc92acd093f23a
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656058"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="e67db-103">Equipe isolada para um projeto secreto da Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="e67db-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="e67db-104">Após um executivo externo, o CEO da Contoso solicitou o desenvolvimento de um novo pacote de produtos e serviços que poderia duplicar os lucros da Contoso nos próximos cinco anos.</span><span class="sxs-lookup"><span data-stu-id="e67db-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="e67db-105">O projeto secreto para desenvolver o plano comercial, de engenharia e de mercado foi denominado **Projeto 2X** e a equipe principal em toda a empresa foi recrutada.</span><span class="sxs-lookup"><span data-stu-id="e67db-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="e67db-106">Os cronogramas de pesquisa e desenvolvimento estavam rígidos, o que significa que a colaboração precisava ser eficiente e fornecer reuniões seguras, conversas contínuas e armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e67db-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="e67db-107">Os produtos resultantes do Project 2X foram planos de negócios, especificações de produto e engenharia e materiais de marketing e agendamentos na forma de arquivos do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e67db-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="e67db-108">Devido à sua natureza sensível, o acesso a esses arquivos foi:</span><span class="sxs-lookup"><span data-stu-id="e67db-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="e67db-109">Restrito aos membros da equipe do Project 2X e à liderança sênior.</span><span class="sxs-lookup"><span data-stu-id="e67db-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="e67db-110">Criptografado e protegido com permissões para permitir o acesso apenas aos membros da equipe do Project 2X e à liderança sênior, mesmo se os arquivos foram distribuídos fora de suas pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="e67db-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="e67db-111">A equipe de IT da Contoso usou [uma equipe com isolamento de](secure-teams-security-isolation.md) segurança para o Project 2X e estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e67db-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="e67db-112">Etapa 1: Criar uma equipe privada</span><span class="sxs-lookup"><span data-stu-id="e67db-112">Step 1: Created a private team</span></span>

<span data-ttu-id="e67db-113">Primeiro, para proteger o acesso ao site subjacente do SharePoint para a equipe, os administradores de IT da Contoso configuraram as políticas de acesso recomendadas [do SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e67db-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="e67db-114">Em seguida, um administrador de IT da Contoso criou uma nova equipe privada chamada Project 2X e adicionou as contas de usuário da equipe do Project 2X como membros.</span><span class="sxs-lookup"><span data-stu-id="e67db-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="e67db-115">Eles também configuraram a equipe para que apenas os proprietários da equipe do Project 2X possam criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="e67db-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="e67db-116">Para obter os detalhes da configuração, [consulte Criar uma equipe privada.](secure-teams-security-isolation.md#create-a-private-team)</span><span class="sxs-lookup"><span data-stu-id="e67db-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="e67db-117">Etapa 2: Criou um rótulo de sensibilidade para a equipe do Project 2X</span><span class="sxs-lookup"><span data-stu-id="e67db-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="e67db-118">Os administradores da Contoso criaram um novo rótulo de sensibilidade chamado **Project 2X** que:</span><span class="sxs-lookup"><span data-stu-id="e67db-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="e67db-119">Criptografia habilitada.</span><span class="sxs-lookup"><span data-stu-id="e67db-119">Enabled encryption.</span></span>
- <span data-ttu-id="e67db-120">Permissões Co-Author permissões para o grupo do Microsoft 2X do Project 365.</span><span class="sxs-lookup"><span data-stu-id="e67db-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="e67db-121">Permissões de Visualizador Permitidas para o grupo liderança sênior.</span><span class="sxs-lookup"><span data-stu-id="e67db-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="e67db-122">Acesso bloqueado a dispositivos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="e67db-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="e67db-123">Os arquivos na **seção Documentos** do site subjacente do SharePoint do Project 2X foram protegidos por:</span><span class="sxs-lookup"><span data-stu-id="e67db-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="e67db-124">As permissões de site, que só permitem permissões completas a membros do grupo Do Project 2X microsoft 365 e permissões de leitura para o grupo de Liderança Sênior.</span><span class="sxs-lookup"><span data-stu-id="e67db-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="e67db-125">O rótulo de confidencialidade do Project 2X, com criptografia e permissões que viajam com o arquivo se ele for movido ou copiado do site.</span><span class="sxs-lookup"><span data-stu-id="e67db-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="e67db-126">Para obter os detalhes de configuração, [consulte Criar um rótulo de sensibilidade.](secure-teams-security-isolation.md#create-a-sensitivity-label)</span><span class="sxs-lookup"><span data-stu-id="e67db-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="e67db-127">Etapa 3: Configurar o site subjacente do SharePoint</span><span class="sxs-lookup"><span data-stu-id="e67db-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="e67db-128">Primeiro, para proteger o acesso ao site subjacente do SharePoint para a equipe, os administradores de IT da Contoso configuraram as políticas de acesso recomendadas [do SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e67db-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="e67db-129">Em seguida, eles definiram configurações de permissão adicionais para o site:</span><span class="sxs-lookup"><span data-stu-id="e67db-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="e67db-130">Para impedir que os membros do grupo do Project 2X compartilhem acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="e67db-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="e67db-131">Para obter os detalhes de configuração, [confira As configurações do SharePoint para uma equipe com isolamento de segurança.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="e67db-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="e67db-132">Para permissões de leitura para o grupo liderança sênior.</span><span class="sxs-lookup"><span data-stu-id="e67db-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="e67db-133">Em seguida, eles definiram configurações de permissão adicionais para o site para impedir que os membros do grupo do Project 2X compartilhem acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="e67db-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="e67db-134">Como canais privados para o Project 2X foram criados, o proprietário do grupo desabilitou o compartilhamento de convidados e definiu o link de compartilhamento padrão para o **valor de pessoas** específicas.</span><span class="sxs-lookup"><span data-stu-id="e67db-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="e67db-135">Esta é a configuração resultante da equipe do Project 2X com isolamento de segurança.</span><span class="sxs-lookup"><span data-stu-id="e67db-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![A configuração resultante da equipe do Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="e67db-137">Etapa 4: Membros treinados da equipe do Project 2X</span><span class="sxs-lookup"><span data-stu-id="e67db-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="e67db-138">A equipe de segurança da Contoso treinamentou os membros da equipe do Project 2X em um curso obrigatório que os pesquisa:</span><span class="sxs-lookup"><span data-stu-id="e67db-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="e67db-139">Como acessar a nova equipe do Project 2X, usar reuniões e chats e como colaborar em arquivos da equipe.</span><span class="sxs-lookup"><span data-stu-id="e67db-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="e67db-140">Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.</span><span class="sxs-lookup"><span data-stu-id="e67db-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="e67db-141">Como rotular arquivos com o rótulo de sensibilidade do Project 2X.</span><span class="sxs-lookup"><span data-stu-id="e67db-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="e67db-142">Uma demonstração de como o rótulo do Project 2X protege um arquivo mesmo quando ele sai da equipe.</span><span class="sxs-lookup"><span data-stu-id="e67db-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="e67db-143">O resultado final foi um ambiente seguro no qual os membros da equipe do Project 2X colaboraram em um ambiente seguro para chats, reuniões e arquivos.</span><span class="sxs-lookup"><span data-stu-id="e67db-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="e67db-144">Aqui está um exemplo de um arquivo armazenado no site do Project 2X subjacente com o rótulo de confidencialidade do Project 2X atribuído.</span><span class="sxs-lookup"><span data-stu-id="e67db-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Um exemplo de um arquivo armazenado no site do Project 2X subjacente](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="e67db-146">Em alguns casos, os membros da equipe do Project 2X baixaram arquivos protegidos pelo rótulo do Project 2X em uma unidade local para trabalho offline.</span><span class="sxs-lookup"><span data-stu-id="e67db-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="e67db-147">No entanto, depois de serem solicitados a solicitar credenciais ao abri-las, eles percebidoam seu erro e as excluíram.</span><span class="sxs-lookup"><span data-stu-id="e67db-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="e67db-148">Devido ao ambiente de colaboração do Teams e aos recursos de segurança do Microsoft 365, os detalhes do Project 2X foram mantidos em segredo durante o projeto.</span><span class="sxs-lookup"><span data-stu-id="e67db-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="e67db-149">A Contoso anunciaram seus planos e está em processo de implantação dos novos produtos e serviços para a satisfação de seus clientes e investidores e o chagrin de seus concorrentes.</span><span class="sxs-lookup"><span data-stu-id="e67db-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="e67db-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e67db-150">Next step</span></span>

<span data-ttu-id="e67db-151">[Implante uma equipe com isolamento de segurança](secure-teams-security-isolation.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e67db-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

