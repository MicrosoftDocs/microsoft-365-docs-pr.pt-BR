---
title: Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: como a contoso implementou um site do SharePoint Online para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.'
ms.openlocfilehash: c20e3a1c4ad0b862e81b897acc1462e3a1d1f776
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289209"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="ccaf6-103">Site do SharePoint Online para ativos digitais altamente confidenciais da Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="ccaf6-103">SharePoint Online site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="ccaf6-104">**Resumo:** Como a contoso implementou um site do SharePoint Online para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-104">**Summary:** How Contoso implemented a SharePoint Online site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="ccaf6-105">Os ativos mais valiosos da Contoso são sua propriedade intelectual na forma de segredos comerciais, como técnicas de fabricação proprietárias e especificações de design para produtos que estão em desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="ccaf6-106">Esses ativos estão em formato digital, originalmente armazenados como arquivos em um site do SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-106">These assets are in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="ccaf6-107">Quando a contoso implantou o Microsoft 365 Enterprise, eles queriam migrar seus ativos digitais locais para a nuvem para facilitar o acesso e mais colaboração aberta entre as equipes de pesquisa em Paris, Moscow, Nova York, Pequim e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="ccaf6-108">No enTanto, devido à natureza confidencial, o acesso a esses arquivos deve ser:</span><span class="sxs-lookup"><span data-stu-id="ccaf6-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="ccaf6-109">Restrito ao conjunto de pessoas que têm permissão para exibir ou alterá-las, com permissões contínuas para o site administrado somente pelos administradores do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-109">Restricted to the set of people who are allowed to view or change them, with ongoing permissions for the site administered only by SharePoint admins.</span></span> 
- <span data-ttu-id="ccaf6-110">Protegido por DLP (prevenção contra perda de dados) para impedir que os usuários os distribuam fora do site.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-110">Protected with Data Loss Prevention (DLP) to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="ccaf6-111">Criptografado e protegido com listas de controle de acesso para impedir que usuários não autorizados acessem seus conteúdos, mesmo que eles sejam distribuídos fora do site.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-111">Encrypted and protected with access control lists to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="ccaf6-112">Administradores de segurança e do SharePoint no departamento de ti da Contoso decidiram usar um [site do SharePoint Online para dados altamente regulamentados](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="ccaf6-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint Online site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="ccaf6-113">A contoso usou estas etapas para criar e proteger sites de equipe do SharePoint Online para suas equipes de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-113">Contoso used these steps to create and secure a SharePoint Online team sites for their research teams.</span></span>

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a><span data-ttu-id="ccaf6-114">Etapa 1: reVisado e verificado os membros dos grupos da equipe de pesquisa</span><span class="sxs-lookup"><span data-stu-id="ccaf6-114">Step 1: Reviewed and verified the members of research team groups</span></span>

<span data-ttu-id="ccaf6-115">Os administradores de ti da Contoso executaram uma análise do conjunto de grupos de segurança para suas equipes de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-115">Contoso IT admins performed a review of the set of security groups for their research teams.</span></span> <span data-ttu-id="ccaf6-116">Eles removeram qualquer pessoa que não seja um pesquisador ou não precisevam de acesso aos ativos de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-116">They removed anyone who was not a researcher or did not need access to research assets.</span></span> 

<span data-ttu-id="ccaf6-117">Eles também criaram esses novos grupos de segurança:</span><span class="sxs-lookup"><span data-stu-id="ccaf6-117">They also and created these new security groups:</span></span>

- <span data-ttu-id="ccaf6-118">**Research-admins**  O conjunto de administradores do SharePoint que têm controle total sobre o site, incluindo a capacidade de modificar permissões.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-118">**Research-Admins**  The set of SharePoint admins that have full control over the site, including the ability to modify permissions.</span></span>
- <span data-ttu-id="ccaf6-119">**Pesquisa-Membros**  O conjunto de grupos de segurança para as equipes de pesquisa em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-119">**Research-Members**  The set of security groups for the research teams around the world.</span></span>
- <span data-ttu-id="ccaf6-120">**Pesquisa-visualizadores**  O conjunto de usuários de gerenciamento, como executivos na organização de pesquisa, que só pode exibir os ativos no site.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-120">**Research-Viewers**  The set of management users, such as executives in the research organization, that can only view the assets on the site.</span></span>

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="ccaf6-121">Etapa 2: criado um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="ccaf6-121">Step 2: Created an isolated SharePoint Online team site</span></span> 

<span data-ttu-id="ccaf6-122">Os administradores do SharePoint da Contoso criaram primeiro um novo site de equipe chamado **pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-122">Contoso SharePoint admins first created a new team site named **Research**.</span></span> <span data-ttu-id="ccaf6-123">Eles então configurados:</span><span class="sxs-lookup"><span data-stu-id="ccaf6-123">They then configured:</span></span>

- <span data-ttu-id="ccaf6-124">O nível de permissão controle total para usar o grupo de proprietários de pesquisa do SharePoint, que tem o grupo de segurança **Research-admins** como um membro</span><span class="sxs-lookup"><span data-stu-id="ccaf6-124">The Full Control permission level to use the Research Owners SharePoint group, which has the **Research-Admins** security group as a member</span></span>
- <span data-ttu-id="ccaf6-125">O nível de permissão Editar para usar o grupo de membros de pesquisa do SharePoint, que tem o grupo de segurança **membros de pesquisa** como um membro</span><span class="sxs-lookup"><span data-stu-id="ccaf6-125">The Edit permission level to use the Research Members SharePoint group, which has the **Research Members** security group as a member</span></span>
- <span data-ttu-id="ccaf6-126">O nível de permissão de leitura para usar o grupo de visitantes de pesquisa do SharePoint, que tem o grupo de segurança de **Visualizador de pesquisa** como membro</span><span class="sxs-lookup"><span data-stu-id="ccaf6-126">The Read permission level to use the Research Visitors SharePoint group, which has the **Research-Viewers** security group as a member</span></span>

<span data-ttu-id="ccaf6-127">Estes são os níveis de permissão do SharePoint resultantes, grupos do SharePoint e seus membros.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-127">Here are the resulting SharePoint permission levels, SharePoint groups, and their members.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

<span data-ttu-id="ccaf6-128">Em seguida, eles configuraram restrições adicionais para o site.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-128">Next, they configured additional restrictions for the site.</span></span>

<span data-ttu-id="ccaf6-129">Para obter os detalhes de configuração, consulte [implantar um site de equipe do SharePoint Online isolado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span><span class="sxs-lookup"><span data-stu-id="ccaf6-129">For the configuration details, see [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).</span></span>

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="ccaf6-130">Etapa 3: configurar o site para uma política de DLP restritiva</span><span class="sxs-lookup"><span data-stu-id="ccaf6-130">Step 3: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="ccaf6-131">Primeiro, os administradores da Contoso aplicaram o rótulo de retenção **altamente confidencial** do Office 365 ao site de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-131">First, Contoso admins applied the **Highly Confidential** Office 365 retention label to the **Research** site.</span></span>

<span data-ttu-id="ccaf6-132">Em seguida, criamos uma nova política de DLP do Office 365 chamada **pesquisa** que:</span><span class="sxs-lookup"><span data-stu-id="ccaf6-132">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="ccaf6-133">Usa o rótulo de retenção **altamente confidencial** do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-133">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="ccaf6-134">É aplicado ao site de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-134">Is applied to the **Research** site.</span></span>
- <span data-ttu-id="ccaf6-135">Impede que os usuários compartilhem documentos.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-135">Prevents users from sharing documents.</span></span>

<span data-ttu-id="ccaf6-136">Para obter detalhes sobre a configuração, consulte [proteger arquivos do SharePoint Online com rótulos do Office 365 e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="ccaf6-136">For the configuration details, see [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="ccaf6-137">Etapa 4: criou um subrótulo da proteção de informações do Azure para o site</span><span class="sxs-lookup"><span data-stu-id="ccaf6-137">Step 4: Created an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="ccaf6-138">Os administradores da Contoso criaram um novo subrótulo de proteção de informações do Azure chamado **pesquisa** do rótulo **altamente confidencial** padrão em uma política com escopo:</span><span class="sxs-lookup"><span data-stu-id="ccaf6-138">Contoso admins created a new Azure Information Protection sub-label named **Research** of the default **Highly Confidential** label in a scoped policy that:</span></span>

- <span data-ttu-id="ccaf6-139">Requer criptografia.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-139">Requires encryption.</span></span>
- <span data-ttu-id="ccaf6-140">Permite acesso total por membros do grupo de segurança **Research-Members** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-140">Allows full access by members of the **Research-Members** security group.</span></span>
- <span data-ttu-id="ccaf6-141">Permite o acesso de leitura por membros do grupo de segurança de visualizadores de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-141">Allows read access by members of the **Research-Viewers** security group.</span></span>

<span data-ttu-id="ccaf6-142">Em seguida, implantamos o cliente de proteção de informações do Azure nos dispositivos dos membros da equipe de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-142">Next, they deployed the Azure Information Protection client to the devices of research team members.</span></span>

<span data-ttu-id="ccaf6-143">Para obter detalhes sobre a configuração, consulte [proteger arquivos do SharePoint Online com a proteção de informações do Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span><span class="sxs-lookup"><span data-stu-id="ccaf6-143">For the configuration details, see [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</span></span> 

<span data-ttu-id="ccaf6-144">Aqui está a configuração resultante do site de **pesquisa** para ativos altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-144">Here is the resulting configuration of the **Research** site for highly confidential assets.</span></span>

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="ccaf6-145">Arquivos em pastas do site de **pesquisa** são protegidos por:</span><span class="sxs-lookup"><span data-stu-id="ccaf6-145">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="ccaf6-146">O subrótulo de proteção de informações do Azure de **pesquisa** , que aplica criptografia e permssions a cada arquivo que viaja com o arquivo quando ele é movido ou copiado do site de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-146">The **Research** Azure Information Protection sublabel, which applies encryption and permssions to each file that travel with the file when it is moved or copied from the **Research** site.</span></span>
- <span data-ttu-id="ccaf6-147">A política de DLP de **pesquisa** , que usa o rótulo de retenção **altamente confidencial** e as configurações que impedem o arquivo de sair do site.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-147">The **Research** DLP policy, which uses the **Highly Sensitive** retention label and settings that prevent the file from leaving the site.</span></span>
- <span data-ttu-id="ccaf6-148">O conjunto de permissões de site, que só permite o acesso aos membros dos grupos de segurança e administração de **pesquisa de membros** e **visualizadores** de pesquisa pelos membros do grupo de segurança **Research-admins** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-148">The set of site permissions, which only allow access to members of the **Research-Members** and **Research-Viewers** security groups and administration by members of the **Research-Admins** security group.</span></span>

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="ccaf6-149">Etapa 5: migrar os dados de pesquisa do SharePoint local</span><span class="sxs-lookup"><span data-stu-id="ccaf6-149">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="ccaf6-150">Os administradores da Contoso mudaram todos os arquivos de pesquisa local no site do SharePoint Server 2016 local para pastas no novo site do SharePoint Online de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-150">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint Online site.</span></span>

## <a name="step-6-trained-their-users"></a><span data-ttu-id="ccaf6-151">Etapa 6: treinado seus usuários</span><span class="sxs-lookup"><span data-stu-id="ccaf6-151">Step 6: Trained their users</span></span> 

<span data-ttu-id="ccaf6-152">A equipe de segurança da Contoso treinou as equipes de pesquisa em um curso obrigatório que as apresentou:</span><span class="sxs-lookup"><span data-stu-id="ccaf6-152">Contoso security staff trained the research teams in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="ccaf6-153">Como acessar o novo site do SharePoint Online de **pesquisa** e seus arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-153">How to access the new **Research** SharePoint Online site and its existing files.</span></span>
- <span data-ttu-id="ccaf6-154">Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-154">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="ccaf6-155">Uma demonstração de como a política de DLP impede que os arquivos sejam compartilhados externamente.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-155">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="ccaf6-156">Como usar o cliente de proteção de informações do Azure para rotular arquivos de pesquisa com o subrótulo de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="ccaf6-156">How to use the Azure Information Protection client to label research files with the **Research** sub-label.</span></span>
- <span data-ttu-id="ccaf6-157">Uma demonstração de como o subrótulo de **pesquisa** protege um arquivo mesmo quando ele é vazado do site.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-157">A demonstration of how the **Research** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="ccaf6-158">O resultado final é um ambiente seguro no qual os pesquisadores podem colaborar através da organização em um ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-158">The end result is a secure environment in which the researchers can collaborate across the organization in a secure environment.</span></span> 

<span data-ttu-id="ccaf6-159">Se um documento de pesquisa com o subrótulo de **pesquisa** for vazado no site de **pesquisa** , ele será criptografado e acessível somente para os membros dos grupos de segurança **Research-Members** e **Research-visualizadores** com credenciais válidas.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-159">If a research document with the **Research** sub-label is leaked from the **Research** site, it is encrypted and accessible only to members of the **Research-Members** and **Research-Viewers** security groups with valid credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="ccaf6-160">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ccaf6-160">Next step</span></span>

<span data-ttu-id="ccaf6-161">[Implantar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ccaf6-161">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

