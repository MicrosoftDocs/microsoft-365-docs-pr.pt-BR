---
title: Equipe isolada para um projeto de segredo superior da Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- M365solutions
ms.custom: Ent_Architecture
description: 'Resumo: como a contoso usou uma equipe com isolamento de segurança para um projeto de segredo principal para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: 1083c9d3db3be9ca528b2eee40f072aa17c7431e
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159450"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="66187-103">Equipe isolada para um projeto de segredo superior da Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="66187-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="66187-104">Após um executivo externo, o CEO da Contoso pediu o desenvolvimento de um novo pacote de produtos e serviços que poderia dobrar os lucros da Contoso nos próximos cinco anos.</span><span class="sxs-lookup"><span data-stu-id="66187-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="66187-105">O projeto de segredo superior para desenvolver o plano de negócios, de engenharia e de mercado foi chamado de **projeto 2x** e o principal pessoal na empresa foi recrutado.</span><span class="sxs-lookup"><span data-stu-id="66187-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="66187-106">Os cronogramas para pesquisa e desenvolvimento estavam apertados, o que significava que a colaboração era eficiente e forneceva reuniões seguras, conversas em andamento e armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="66187-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="66187-107">Os resultados finais do projeto 2X foram planos de negócios, especificações de produtos e de engenharia e materiais de marketing e agendamentos no formato de arquivos do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="66187-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="66187-108">Devido à sua natureza confidencial, o acesso a esses arquivos era:</span><span class="sxs-lookup"><span data-stu-id="66187-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="66187-109">Restrito aos membros da equipe do projeto 2.</span><span class="sxs-lookup"><span data-stu-id="66187-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="66187-110">Criptografado e protegido com permissões para permitir acesso somente aos membros da equipe do Project 2X, mesmo que os arquivos tenham sido distribuídos fora de suas pastas seguras.</span><span class="sxs-lookup"><span data-stu-id="66187-110">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="66187-111">A equipe de ti da Contoso usou uma [equipe com isolamento de segurança](secure-teams-security-isolation.md) para o projeto 2 e estas etapas.</span><span class="sxs-lookup"><span data-stu-id="66187-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="66187-112">Etapa 1: criar uma equipe privada</span><span class="sxs-lookup"><span data-stu-id="66187-112">Step 1: Created a private team</span></span>

<span data-ttu-id="66187-113">Primeiro, para proteger o acesso ao site do SharePoint subjacente para a equipe, os administradores de ti da Contoso configuraram as [políticas de acesso recomendadas do SharePoint](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="66187-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="66187-114">Em seguida, um administrador de ti da Contoso criou uma nova equipe privada chamada projeto 2X e adicionou as contas de usuário do projeto 2X como membros.</span><span class="sxs-lookup"><span data-stu-id="66187-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="66187-115">Para obter detalhes sobre a configuração, consulte [Create a Private Team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="66187-115">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="66187-116">Etapa 2: criou um rótulo de confidencialidade para o projeto 2X Team</span><span class="sxs-lookup"><span data-stu-id="66187-116">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="66187-117">Os administradores da Contoso criaram um novo rótulo de sensibilidade chamado **projeto 2x** que:</span><span class="sxs-lookup"><span data-stu-id="66187-117">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="66187-118">Requer criptografia.</span><span class="sxs-lookup"><span data-stu-id="66187-118">Requires encryption.</span></span>
- <span data-ttu-id="66187-119">Permite permissões de coautoria para o grupo 2 do projeto do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66187-119">Allows Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>

<span data-ttu-id="66187-120">Arquivos na seção **Documents** do projeto subjacente o site do SharePoint é protegido por:</span><span class="sxs-lookup"><span data-stu-id="66187-120">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="66187-121">As permissões de site, que permitem o acesso somente aos membros do grupo 2 do projeto 2X Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66187-121">The site permissions, which only allow access to members of the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="66187-122">O rótulo de sensibilidade do projeto 2X, com criptografia e permissões que trafegam com o arquivo se ele for movido ou copiado do site.</span><span class="sxs-lookup"><span data-stu-id="66187-122">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="66187-123">Para obter detalhes sobre a configuração, consulte [criar um rótulo de confidencialidade](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="66187-123">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="66187-124">Etapa 3: configurou o site do SharePoint subjacente</span><span class="sxs-lookup"><span data-stu-id="66187-124">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="66187-125">Primeiro, para proteger o acesso ao site do SharePoint subjacente para a equipe, os administradores de ti da Contoso configuraram as [políticas de acesso recomendadas do SharePoint](../enterprise/sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="66187-125">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../enterprise/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="66187-126">Em seguida, eles definiram configurações de permissão adicionais para o site a fim de evitar que o projeto 2X Compartilhe o acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="66187-126">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site.</span></span> <span data-ttu-id="66187-127">Para obter detalhes sobre a configuração, consulte [configurações do SharePoint para uma equipe com isolamento de segurança](secure-teams-security-isolation.md#sharepoint-settings).</span><span class="sxs-lookup"><span data-stu-id="66187-127">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>

<span data-ttu-id="66187-128">Veja a seguir a configuração resultante da equipe do projeto 2X.</span><span class="sxs-lookup"><span data-stu-id="66187-128">Here is the resulting configuration of the Project 2X team.</span></span>

![A configuração resultante da equipe do projeto 2X](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="66187-130">Etapa 4: projeto treinado 2 membros da equipe</span><span class="sxs-lookup"><span data-stu-id="66187-130">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="66187-131">A equipe de segurança da Contoso treinou o projeto 2 membros da equipe em um curso obrigatório que os apresentou:</span><span class="sxs-lookup"><span data-stu-id="66187-131">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="66187-132">Como acessar a nova equipe do projeto 2, use reuniões e chats e como colaborar em arquivos da equipe.</span><span class="sxs-lookup"><span data-stu-id="66187-132">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="66187-133">Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.</span><span class="sxs-lookup"><span data-stu-id="66187-133">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="66187-134">Uma demonstração de como a política de DLP impede que os arquivos sejam compartilhados externamente.</span><span class="sxs-lookup"><span data-stu-id="66187-134">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="66187-135">Como rotular arquivos com o rótulo de sensibilidade do projeto 2X.</span><span class="sxs-lookup"><span data-stu-id="66187-135">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="66187-136">Uma demonstração de como o rótulo projeto 2X protege um arquivo, mesmo quando ele sai da equipe.</span><span class="sxs-lookup"><span data-stu-id="66187-136">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="66187-137">O resultado final era um ambiente seguro no qual o projeto 2X membros da equipe colaboraram em um ambiente seguro para chats, reuniões e arquivos.</span><span class="sxs-lookup"><span data-stu-id="66187-137">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="66187-138">Veja a seguir um exemplo de um arquivo armazenado no site subjacente do projeto 2 com o rótulo de sensibilidade do projeto 2 atribuído.</span><span class="sxs-lookup"><span data-stu-id="66187-138">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Um exemplo de um arquivo armazenado no site subjacente do projeto 2](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="66187-140">Em alguns casos, o Project 2X os membros da equipe baixaram arquivos protegidos pelo rótulo Project 2X para uma unidade local para trabalho offline.</span><span class="sxs-lookup"><span data-stu-id="66187-140">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="66187-141">No entanto, após serem solicitadas as credenciais ao serem abertas, elas perceberam o erro e as excluíram.</span><span class="sxs-lookup"><span data-stu-id="66187-141">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="66187-142">Por causa do ambiente de colaboração do Teams e dos recursos de segurança do Microsoft 365, os detalhes do projeto 2X foram mantidos secretos para a duração do projeto.</span><span class="sxs-lookup"><span data-stu-id="66187-142">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="66187-143">A contoso anunciou seus planos e está no processo de distribuir os novos produtos e serviços para a encantarão de seus clientes e investidores e para o Chagrin de seus concorrentes.</span><span class="sxs-lookup"><span data-stu-id="66187-143">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="66187-144">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="66187-144">Next step</span></span>

<span data-ttu-id="66187-145">[Implantar uma equipe com isolamento de segurança](secure-teams-security-isolation.md) em sua organização.</span><span class="sxs-lookup"><span data-stu-id="66187-145">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

