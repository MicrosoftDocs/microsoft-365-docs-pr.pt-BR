---
title: Equipe isolada para um projeto secreto da Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
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
description: 'Resumo: Como a Contoso usou uma equipe com isolamento de segurança para um projeto top-secret para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029011"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="89d93-103">Equipe isolada para um projeto secreto da Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="89d93-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="89d93-104">Depois de um executivo fora do local, o CEO da Contoso ordenou o desenvolvimento de um novo pacote de produtos e serviços que poderia duplicar os lucros da Contoso nos próximos cinco anos.</span><span class="sxs-lookup"><span data-stu-id="89d93-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="89d93-105">O projeto ultra-secreto para desenvolver o plano de negócios, engenharia e mercado foi chamado **Project 2X** e a equipe-chave em toda a empresa foi recrutada.</span><span class="sxs-lookup"><span data-stu-id="89d93-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="89d93-106">As linhas do tempo para pesquisa e desenvolvimento eram estreitas, o que significava que a colaboração precisava ser eficiente e fornecer reuniões seguras, conversas em andamento e armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="89d93-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="89d93-107">Os produtos resultantes para o Project 2X eram planos de negócios, especificações de produto e engenharia e materiais de marketing e agendamentos na forma de arquivos word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="89d93-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="89d93-108">Devido à sua natureza sensível, o acesso a esses arquivos foi:</span><span class="sxs-lookup"><span data-stu-id="89d93-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="89d93-109">Restrito a Project membros da equipe 2X e liderança sênior.</span><span class="sxs-lookup"><span data-stu-id="89d93-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="89d93-110">Criptografado e protegido com permissões para permitir o acesso apenas a membros da equipe 2X e liderança sênior, mesmo que os arquivos tenham sido distribuído Project s fora de suas pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="89d93-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="89d93-111">A equipe de IT da Contoso usou uma [equipe com](secure-teams-security-isolation.md) isolamento de segurança para Project 2X e essas etapas.</span><span class="sxs-lookup"><span data-stu-id="89d93-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="89d93-112">Etapa 1: Criar uma equipe privada</span><span class="sxs-lookup"><span data-stu-id="89d93-112">Step 1: Created a private team</span></span>

<span data-ttu-id="89d93-113">Primeiro, para proteger o acesso ao site de SharePoint subjacente para a equipe, os administradores de IT da Contoso configuraram as políticas de SharePoint [de acesso recomendadas.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="89d93-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="89d93-114">Em seguida, um administrador de IT da Contoso criou uma nova equipe privada chamada Project 2X e adicionou as contas de usuário da equipe Project 2X como membros.</span><span class="sxs-lookup"><span data-stu-id="89d93-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="89d93-115">Eles também configuraram a equipe para que apenas Project proprietários de equipe 2X possam criar canais privados.</span><span class="sxs-lookup"><span data-stu-id="89d93-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="89d93-116">Para obter os detalhes da configuração, consulte [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="89d93-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="89d93-117">Etapa 2: Criou um rótulo de sensibilidade para a equipe Project 2X</span><span class="sxs-lookup"><span data-stu-id="89d93-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="89d93-118">Os administradores da Contoso criaram um novo rótulo de sensibilidade **chamado Project 2X** que:</span><span class="sxs-lookup"><span data-stu-id="89d93-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="89d93-119">Criptografia habilitada.</span><span class="sxs-lookup"><span data-stu-id="89d93-119">Enabled encryption.</span></span>
- <span data-ttu-id="89d93-120">Permissões Co-Author para o grupo Project 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89d93-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="89d93-121">Permissões permitidas do Visualizador para o grupo de Liderança Sênior.</span><span class="sxs-lookup"><span data-stu-id="89d93-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="89d93-122">Acesso bloqueado a dispositivos não autorizados.</span><span class="sxs-lookup"><span data-stu-id="89d93-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="89d93-123">Os arquivos na **seção Documentos** do site de Project 2X SharePoint foram protegidos por:</span><span class="sxs-lookup"><span data-stu-id="89d93-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="89d93-124">As permissões de site, que só permitem permissões completas para membros do grupo Project 2X Microsoft 365 e permissões de leitura para o grupo de Liderança Sênior.</span><span class="sxs-lookup"><span data-stu-id="89d93-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="89d93-125">O Project de confidencialidade 2X, com criptografia e permissões que viajam com o arquivo se ele for movido ou copiado do site.</span><span class="sxs-lookup"><span data-stu-id="89d93-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="89d93-126">Para obter os detalhes da configuração, [consulte Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="89d93-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="89d93-127">Etapa 3: Configured the underlying SharePoint site</span><span class="sxs-lookup"><span data-stu-id="89d93-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="89d93-128">Primeiro, para proteger o acesso ao site de SharePoint subjacente para a equipe, os administradores de IT da Contoso configuraram as políticas de SharePoint [de acesso recomendadas.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="89d93-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="89d93-129">Em seguida, eles configuraram configurações de permissão adicionais para o site:</span><span class="sxs-lookup"><span data-stu-id="89d93-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="89d93-130">Para impedir que Project membros do grupo 2X compartilhem acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="89d93-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="89d93-131">Para obter os detalhes da configuração, [consulte SharePoint configurações de uma equipe com isolamento de segurança](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="89d93-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="89d93-132">Para permissões de leitura para o grupo de Liderança Sênior.</span><span class="sxs-lookup"><span data-stu-id="89d93-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="89d93-133">Em seguida, eles configuraram configurações de permissão adicionais para o site para impedir que Project membros do grupo 2X compartilhem acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="89d93-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="89d93-134">Como canais privados para o Project 2X foram criados, o proprietário do grupo desabilitou o compartilhamento de convidados e definiu o link de compartilhamento padrão para **o valor Pessoas** específicas.</span><span class="sxs-lookup"><span data-stu-id="89d93-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="89d93-135">Aqui está a configuração resultante da equipe Project 2X com isolamento de segurança.</span><span class="sxs-lookup"><span data-stu-id="89d93-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![A configuração resultante da equipe Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="89d93-137">Etapa 4: Membros Project equipe 2X treinados</span><span class="sxs-lookup"><span data-stu-id="89d93-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="89d93-138">A equipe de segurança da Contoso Project os membros da equipe 2X em um curso obrigatório que os fez passar por:</span><span class="sxs-lookup"><span data-stu-id="89d93-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="89d93-139">Como acessar a nova equipe Project 2X, usar reuniões e chats e como colaborar em arquivos de equipe.</span><span class="sxs-lookup"><span data-stu-id="89d93-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="89d93-140">Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.</span><span class="sxs-lookup"><span data-stu-id="89d93-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="89d93-141">Como rotular arquivos com o rótulo Project de sensibilidade 2X.</span><span class="sxs-lookup"><span data-stu-id="89d93-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="89d93-142">Uma demonstração de como o Project 2X protege um arquivo mesmo quando ele sai da equipe.</span><span class="sxs-lookup"><span data-stu-id="89d93-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="89d93-143">O resultado final foi um ambiente seguro no qual Project membros da equipe 2X colaboraram em um ambiente seguro para chats, reuniões e arquivos.</span><span class="sxs-lookup"><span data-stu-id="89d93-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="89d93-144">Aqui está um exemplo de um arquivo armazenado no site Project 2X subjacente com o rótulo de confidencialidade Project 2X atribuído.</span><span class="sxs-lookup"><span data-stu-id="89d93-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Um exemplo de um arquivo armazenado no site Project 2X subjacente](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="89d93-146">Em algumas instâncias, Project membros da equipe 2X baixaram arquivos protegidos pelo rótulo Project 2X para uma unidade local para trabalho offline.</span><span class="sxs-lookup"><span data-stu-id="89d93-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="89d93-147">No entanto, após serem solicitados a solicitar credenciais ao abri-las, eles perceberam o erro e as excluíram.</span><span class="sxs-lookup"><span data-stu-id="89d93-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="89d93-148">Devido ao ambiente de colaboração do Teams e dos recursos de segurança do Microsoft 365, os detalhes do Project 2X foram mantidos em segredo durante a duração do projeto.</span><span class="sxs-lookup"><span data-stu-id="89d93-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="89d93-149">A Contoso anuncia seus planos e está em processo de implantação dos novos produtos e serviços para o deleite de seus clientes e investidores e o adélio de seus concorrentes.</span><span class="sxs-lookup"><span data-stu-id="89d93-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="89d93-150">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="89d93-150">Next step</span></span>

<span data-ttu-id="89d93-151">[Implante uma equipe com isolamento de segurança](secure-teams-security-isolation.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="89d93-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

