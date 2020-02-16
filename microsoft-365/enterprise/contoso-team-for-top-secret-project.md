---
title: Equipe para um projeto confidencial da Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: como a contoso usou uma equipe para dados altamente regulamentados de um projeto de segredo superior para desenvolver um novo pacote de produtos e serviços.'
ms.openlocfilehash: 58d381751db3e94f35a0c1b8f7a14c191918e754
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068018"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="d67ea-103">Equipe para um projeto confidencial da Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="d67ea-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="d67ea-104">Após um executivo externo, o CEO da Contoso pediu o desenvolvimento de um novo pacote de produtos e serviços que poderia dobrar os lucros da Contoso nos próximos cinco anos.</span><span class="sxs-lookup"><span data-stu-id="d67ea-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="d67ea-105">O projeto de segredo superior para desenvolver o plano de negócios, de engenharia e de mercado foi chamado de **projeto 2x** e o principal pessoal na empresa foi recrutado.</span><span class="sxs-lookup"><span data-stu-id="d67ea-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="d67ea-106">Os cronogramas para pesquisa e desenvolvimento estavam apertados, o que significava que a colaboração era eficiente e forneceva reuniões seguras, conversas em andamento e armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d67ea-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="d67ea-107">Os resultados finais do projeto 2X foram planos de negócios, especificações de produtos e de engenharia e materiais de marketing e agendamentos no formato de arquivos do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="d67ea-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="d67ea-108">Devido à sua natureza confidencial, o acesso a esses arquivos era:</span><span class="sxs-lookup"><span data-stu-id="d67ea-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="d67ea-109">Restrito aos membros da equipe do projeto 2.</span><span class="sxs-lookup"><span data-stu-id="d67ea-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="d67ea-110">Protegido por uma política de prevenção contra perda de dados (DLP) para impedir que os membros da equipe do projeto 2 o compartilhem fora da equipe.</span><span class="sxs-lookup"><span data-stu-id="d67ea-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="d67ea-111">Criptografado e protegido com permissões para permitir acesso somente aos membros da equipe do Project 2X, mesmo que os arquivos tenham sido distribuídos fora da contoso.</span><span class="sxs-lookup"><span data-stu-id="d67ea-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="d67ea-112">A equipe de ti da Contoso usou uma [equipe para dados altamente regulamentados](secure-teams-highly-regulated-data-scenario.md) para o projeto 2x e estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d67ea-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="d67ea-113">Etapa 1: criar uma equipe privada e bloquear o site do SharePoint subjacente</span><span class="sxs-lookup"><span data-stu-id="d67ea-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="d67ea-114">Para proteger o acesso ao site do SharePoint subjacente para a equipe, os administradores de ti da Contoso configuraram as [políticas de acesso recomendadas do SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d67ea-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="d67ea-115">Em seguida, um administrador de ti da Contoso criou uma nova equipe privada chamada projeto 2X e adicionou as contas de usuário do projeto 2X como membros.</span><span class="sxs-lookup"><span data-stu-id="d67ea-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="d67ea-116">Em seguida, eles definiram configurações de permissão adicionais para o site a fim de evitar que o projeto seja compartilhado de compartilhar o acesso ao site e impedir outros de solicitar acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="d67ea-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="d67ea-117">Para obter detalhes sobre a configuração, consulte [configurações do SharePoint para uma equipe altamente regulamentada](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span><span class="sxs-lookup"><span data-stu-id="d67ea-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="d67ea-118">Etapa 2: configurou uma política de DLP e o site subjacente para um rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="d67ea-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="d67ea-119">Primeiro, os administradores da Contoso aplicaram o rótulo de retenção do Office 365 **altamente confidencial** existente à seção **documentos** do site do SharePoint subjacente da equipe do projeto 2.</span><span class="sxs-lookup"><span data-stu-id="d67ea-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="d67ea-120">Em seguida, criamos uma nova política de DLP do Office 365 chamada **Project 2x** que:</span><span class="sxs-lookup"><span data-stu-id="d67ea-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="d67ea-121">Usa o rótulo de retenção altamente confidencial do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d67ea-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="d67ea-122">Bloqueia os usuários quando eles tentam compartilhar um arquivo na equipe do projeto 2X fora da contoso.</span><span class="sxs-lookup"><span data-stu-id="d67ea-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="d67ea-123">Para obter os detalhes de configuração, consulte [proteger arquivos no Microsoft Teams com rótulos de retenção e DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span><span class="sxs-lookup"><span data-stu-id="d67ea-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="d67ea-124">Etapa 3: criou um rótulo de confidencialidade do Office 365 para o projeto 2X Team</span><span class="sxs-lookup"><span data-stu-id="d67ea-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="d67ea-125">Os administradores da Contoso criaram um novo rótulo de sensibilidade do Office 365 chamado **projeto 2x** que:</span><span class="sxs-lookup"><span data-stu-id="d67ea-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="d67ea-126">Requer criptografia.</span><span class="sxs-lookup"><span data-stu-id="d67ea-126">Requires encryption.</span></span>
- <span data-ttu-id="d67ea-127">Permite permissões de coautoria para o grupo do projeto 2X Office 365.</span><span class="sxs-lookup"><span data-stu-id="d67ea-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="d67ea-128">Veja a seguir a configuração resultante da equipe do projeto 2X.</span><span class="sxs-lookup"><span data-stu-id="d67ea-128">Here is the resulting configuration of the Project 2X team.</span></span>

![A configuração resultante da equipe do projeto 2X](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="d67ea-130">Arquivos na seção Documents do projeto subjacente o site do SharePoint é protegido por:</span><span class="sxs-lookup"><span data-stu-id="d67ea-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="d67ea-131">As permissões de site, que permitem apenas o acesso aos membros do grupo do projeto 2X do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d67ea-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="d67ea-132">O rótulo de retenção altamente confidencial, que é atribuído automaticamente a novos arquivos.</span><span class="sxs-lookup"><span data-stu-id="d67ea-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="d67ea-133">Uma política de DLP que usa o rótulo e as configurações de retenção altamente confidenciais que impedirão o arquivo de ser compartilhado com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="d67ea-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="d67ea-134">O rótulo de sensibilidade do projeto 2X, com criptografia e permissões que trafegam com o arquivo se ele for movido ou copiado do site.</span><span class="sxs-lookup"><span data-stu-id="d67ea-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="d67ea-135">Aqui está um exemplo de um arquivo armazenado no site subjacente do projeto 2 com o rótulo de retenção altamente regulamentado e o rótulo de sensibilidade do projeto 2X atribuído.</span><span class="sxs-lookup"><span data-stu-id="d67ea-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Um exemplo de um arquivo armazenado no site subjacente do projeto 2](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="d67ea-137">Etapa 4: projeto treinado 2 membros da equipe</span><span class="sxs-lookup"><span data-stu-id="d67ea-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="d67ea-138">A equipe de segurança da Contoso treinou o projeto 2 membros da equipe em um curso obrigatório que os apresentou:</span><span class="sxs-lookup"><span data-stu-id="d67ea-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="d67ea-139">Como acessar a nova equipe do projeto 2, use reuniões e chats e como colaborar em arquivos da equipe.</span><span class="sxs-lookup"><span data-stu-id="d67ea-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="d67ea-140">Como criar novos arquivos na equipe e carregar novos arquivos criados localmente.</span><span class="sxs-lookup"><span data-stu-id="d67ea-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="d67ea-141">Uma demonstração de como a política de DLP impede que os arquivos sejam compartilhados externamente.</span><span class="sxs-lookup"><span data-stu-id="d67ea-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="d67ea-142">Como rotular arquivos com o rótulo de sensibilidade do projeto 2X.</span><span class="sxs-lookup"><span data-stu-id="d67ea-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="d67ea-143">Uma demonstração de como o rótulo projeto 2X protege um arquivo, mesmo quando ele sai da equipe.</span><span class="sxs-lookup"><span data-stu-id="d67ea-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="d67ea-144">O resultado final era um ambiente seguro no qual o projeto 2X membros da equipe colaboraram em um ambiente seguro para chats, reuniões e arquivos.</span><span class="sxs-lookup"><span data-stu-id="d67ea-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="d67ea-145">Em alguns casos, o Project 2X os membros da equipe baixaram arquivos protegidos pelo rótulo Project 2X para uma unidade local para trabalho offline.</span><span class="sxs-lookup"><span data-stu-id="d67ea-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="d67ea-146">No entanto, após serem solicitadas as credenciais ao serem abertas, elas perceberam o erro e as excluíram.</span><span class="sxs-lookup"><span data-stu-id="d67ea-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="d67ea-147">Por causa do ambiente de colaboração do Teams e dos recursos de segurança do Microsoft 365, os detalhes do projeto 2X foram mantidos secretos para a duração do projeto.</span><span class="sxs-lookup"><span data-stu-id="d67ea-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="d67ea-148">A contoso anunciou seus planos e está no processo de distribuir os novos produtos e serviços para a encantarão de seus clientes e investidores e para o Chagrin de seus concorrentes.</span><span class="sxs-lookup"><span data-stu-id="d67ea-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="d67ea-149">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d67ea-149">Next step</span></span>

<span data-ttu-id="d67ea-150">[Implantar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d67ea-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="d67ea-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="d67ea-151">See also</span></span>

<span data-ttu-id="d67ea-152">[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="d67ea-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
