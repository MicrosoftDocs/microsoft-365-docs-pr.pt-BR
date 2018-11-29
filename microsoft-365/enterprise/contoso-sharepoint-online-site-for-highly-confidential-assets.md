---
title: Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Resumo: Como Contoso implementou um site do SharePoint Online para altamente regulamentados dados para facilitar a colaboração entre sua pesquisa equipes.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865270"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="64604-103">Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="64604-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="64604-104">**Resumo:** Como a Contoso implementou um site do SharePoint Online para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="64604-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="64604-p101">Ativos mais valiosos da Contoso sua propriedade intelectual na forma de segredos comerciais, como o proprietário de fabricação técnicas e crie as especificações para os produtos que estão em desenvolvimento. Esses ativos estão em formato digital, originalmente armazenado como arquivos em um site do SharePoint Server 2016. Quando Contoso implantado Microsoft 365 Enterprise, eles queriam fazer a transição de seus ativos digitais do local para a nuvem para facilitar o acesso e mais vulnerável colaboração entre as equipes de pesquisa em Bangalore, Moscou, Nova York, Pequim e Paris.</span><span class="sxs-lookup"><span data-stu-id="64604-p101">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development. These assets are in digital form, originally stored as files on a SharePoint Server 2016 site. When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="64604-108">No entanto, devido à sua natureza confidencial, acesso a esses arquivos deve ser:</span><span class="sxs-lookup"><span data-stu-id="64604-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="64604-109">Restrito ao conjunto de pessoas que têm permissão para exibir ou alterá-los, com permissões em andamento para o site administrado somente por administradores do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="64604-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="64604-110">Protegido com Data Loss Prevention (DLP) para impedir que usuários distribuí-las fora do site.</span><span class="sxs-lookup"><span data-stu-id="64604-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="64604-111">Listas para impedir que usuários não autorizados acessem seus conteúdos, mesmo que elas sejam distribuídas fora do site de controle de acesso criptografado e protegido com.</span><span class="sxs-lookup"><span data-stu-id="64604-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="64604-112">Os administradores de segurança e o SharePoint em Contoso do departamento de TI decidiu usar um [site do SharePoint Online para altamente regulamentado dados](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="64604-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="64604-113">A Contoso usou estas etapas para criar e proteger um sites de equipe do SharePoint Online para suas equipes de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="64604-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="64604-114">Etapa 1: Revisar e verificar os membros de grupos de equipe de pesquisa</span><span class="sxs-lookup"><span data-stu-id="64604-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="64604-p102">Os administradores de TI da Contoso executada uma análise do conjunto de grupos de segurança para suas equipes de pesquisa. Eles removidos, qualquer pessoa que não estava Pesquisador ou não foram necessárias para o acesso aos ativos research.</span><span class="sxs-lookup"><span data-stu-id="64604-p102">Contoso IT admins performed a review of the set of security groups for their research teams. They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="64604-117">Eles também e criado esses novos grupos de segurança:</span><span class="sxs-lookup"><span data-stu-id="64604-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="64604-118">**Administração de pesquisa**  O conjunto de administradores do SharePoint que têm controle total sobre o site, incluindo a capacidade de modificar permissões.</span><span class="sxs-lookup"><span data-stu-id="64604-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="64604-119">**Membros de pesquisa**  O conjunto de grupos de segurança para as equipes de pesquisa em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="64604-119">**Research Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="64604-120">**Visualizadores de pesquisa**  O conjunto de usuários de gerenciamento, como executivos da organização research, que pode exibir os ativos no site.</span><span class="sxs-lookup"><span data-stu-id="64604-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="64604-121">Etapa 2: Criado um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="64604-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="64604-p103">Administradores da Contoso SharePoint criado pela primeira vez um novo site de equipe denominado **Research**. Em seguida, eles configurados:</span><span class="sxs-lookup"><span data-stu-id="64604-p103">Contoso SharePoint admins first created a new team site named **Research**. They then configured:</span></span>

- <span data-ttu-id="64604-124">O nível de permissão Controle total para usar o grupo de proprietários do SharePoint Research, que tem o grupo de segurança **Administradores de pesquisa** como membro</span><span class="sxs-lookup"><span data-stu-id="64604-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="64604-125">O nível de permissão Editar para usar Research grupo membros do SharePoint, que tem o grupo de segurança **Membros Research** como membro</span><span class="sxs-lookup"><span data-stu-id="64604-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="64604-126">O nível de permissão de leitura para usar o grupo do SharePoint de visitantes Research, que tem o grupo de segurança de **Pesquisa-visualizadores** como membro</span><span class="sxs-lookup"><span data-stu-id="64604-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="64604-127">Aqui estão os níveis de permissão do SharePoint resultantes, grupos do SharePoint e seus membros.</span><span class="sxs-lookup"><span data-stu-id="64604-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="64604-128">Em seguida, eles configurados restrições adicionais para o site.</span><span class="sxs-lookup"><span data-stu-id="64604-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="64604-129">Para obter os detalhes de configuração, consulte [Deploy um site de equipe do SharePoint Online isolado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="64604-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a><span data-ttu-id="64604-130">Etapa 3: Configurado o site para um rótulo do Office 365 restritivo política de DLP</span><span class="sxs-lookup"><span data-stu-id="64604-130">Step 3: Configured the site for a restrictive Office 365 label DLP policy</span></span>

<span data-ttu-id="64604-131">Em primeiro lugar, a Contoso admins aplicadas o rótulo do Office 365 **Altamente confidenciais** para o site de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="64604-131">First, Contoso admins applied the **Highly Confidential** Office 365 label to the **Research** site.</span></span>

<span data-ttu-id="64604-132">Em seguida, criou uma nova política de DLP do Office 365 denominado **Research** :</span><span class="sxs-lookup"><span data-stu-id="64604-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="64604-133">Usa o rótulo do Office 365 **Altamente confidenciais** .</span><span class="sxs-lookup"><span data-stu-id="64604-133">Uses the **Highly Confidential** Office 365 label.</span></span> 
- <span data-ttu-id="64604-134">É aplicado ao site de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="64604-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="64604-135">Impede que os usuários compartilhem documentos.</span><span class="sxs-lookup"><span data-stu-id="64604-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="64604-136">Para obter os detalhes de configuração, consulte [arquivos de proteger o SharePoint Online com o Office 365 rótulos e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="64604-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="64604-137">Etapa 4: Criado um rótulo de subsites de proteção de informações do Windows Azure para o site</span><span class="sxs-lookup"><span data-stu-id="64604-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="64604-138">Administradores da Contoso criados um novo rótulo de subsites de proteção de informações do Azure denominado **Research** do rótulo padrão **Altamente confidenciais** em uma política com escopo que:</span><span class="sxs-lookup"><span data-stu-id="64604-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="64604-139">Requer criptografia.</span><span class="sxs-lookup"><span data-stu-id="64604-139">Requires encryption.</span></span>
- <span data-ttu-id="64604-140">Permite acesso total por membros do grupo de segurança **Membros Research** .</span><span class="sxs-lookup"><span data-stu-id="64604-140">Allows full access by members of the **Research Members** security group.</span></span>
- <span data-ttu-id="64604-141">Permite o acesso de leitura por membros do grupo de segurança **Visualizadores Research** .</span><span class="sxs-lookup"><span data-stu-id="64604-141">Allows read access by members of the **Research Viewers** security group.</span></span>

<span data-ttu-id="64604-142">Em seguida, ele implantou o cliente de proteção de informações do Windows Azure para os dispositivos de membros da equipe de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="64604-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="64604-143">Para obter os detalhes de configuração, consulte [proteger o SharePoint Online arquivos com proteção de informações do Windows Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="64604-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="64604-144">Aqui está a configuração resultante do site **Research** para ativos altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="64604-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="64604-145">Etapa 5: Migrados os dados de pesquisa do SharePoint local</span><span class="sxs-lookup"><span data-stu-id="64604-145">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="64604-146">Os administradores da Contoso movido que todos os locais de arquivos no site local 2016 do SharePoint Server para pastas no novo site do SharePoint Online **Research** pesquisas.</span><span class="sxs-lookup"><span data-stu-id="64604-146">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="64604-147">Etapa 6: Treinados seus usuários</span><span class="sxs-lookup"><span data-stu-id="64604-147">Step 6: Trained their users</span></span> 

<span data-ttu-id="64604-148">A equipe de segurança Contoso treinada as equipes de pesquisa em um curso obrigatório que apresentado etapas-los por meio de:</span><span class="sxs-lookup"><span data-stu-id="64604-148">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="64604-149">Como acessar o novo site do SharePoint Online de **pesquisa** e seus arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="64604-149">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="64604-150">Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="64604-150">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="64604-151">Uma demonstração de como a política de DLP impede que arquivos sejam compartilhados externamente.</span><span class="sxs-lookup"><span data-stu-id="64604-151">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="64604-152">Como usar o cliente de proteção de informações do Windows Azure para rotular research arquivos com o rótulo de subsites **Research** .</span><span class="sxs-lookup"><span data-stu-id="64604-152">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="64604-153">Uma demonstração de como o rótulo de subsites **Research** protege um arquivo mesmo quando ele tenha vazado do site.</span><span class="sxs-lookup"><span data-stu-id="64604-153">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="64604-154">O resultado final é um ambiente seguro, na qual os pesquisadores podem colaborar em toda a organização em um ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="64604-154">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="64604-155">Se um documento de pesquisa com o rótulo de subsites **Research** tenha vazado do site **Research** , é criptografada e acessível somente aos membros dos grupos de segurança **Membros de pesquisa** e **Visualizadores de pesquisa** com credenciais válidas.</span><span class="sxs-lookup"><span data-stu-id="64604-155">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research Members** and **Research Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="64604-156">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="64604-156">Next step</span></span>

<span data-ttu-id="64604-157">[Implantar](deploy-microsoft-365-enterprise.md) o Microsoft 365 Enterprise na sua organização.</span><span class="sxs-lookup"><span data-stu-id="64604-157">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

