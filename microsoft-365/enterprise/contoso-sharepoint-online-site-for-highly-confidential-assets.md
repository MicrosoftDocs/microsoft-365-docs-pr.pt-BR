---
title: Site do SharePoint para ativos digitais altamente confidenciais da Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumo: como a contoso implementou um site do SharePoint para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.'
ms.openlocfilehash: 08676f9fa89d9cbf932f9d70664ad1d17a153e3b
ms.sourcegitcommit: 80dc9ceb14e3eb3ae61b0fc2c8c3d73d564a7ef9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2019
ms.locfileid: "37617249"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a><span data-ttu-id="cb656-103">Site do SharePoint para ativos digitais altamente confidenciais da Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="cb656-103">SharePoint site for highly confidential digital assets of the Contoso Corporation</span></span>

 <span data-ttu-id="cb656-104">**Resumo:** Como a contoso implementou um site do SharePoint para dados altamente regulamentados para facilitar a colaboração entre suas equipes de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cb656-104">**Summary:** How Contoso implemented a SharePoint site for highly regulated data for easier collaboration between its research teams.</span></span>
  
<span data-ttu-id="cb656-105">Os ativos mais valiosos da Contoso são sua propriedade intelectual na forma de segredos comerciais, como técnicas de fabricação proprietárias e especificações de design para produtos que estão em desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="cb656-105">Contoso's most valuable assets are its intellectual property in the form of trade secrets, such as proprietary manufacturing techniques, and design specifications for products that are in development.</span></span> <span data-ttu-id="cb656-106">Esses ativos estavam em formato digital, originalmente armazenados como arquivos em um site do SharePoint Server 2016.</span><span class="sxs-lookup"><span data-stu-id="cb656-106">These assets were in digital form, originally stored as files on a SharePoint Server 2016 site.</span></span> <span data-ttu-id="cb656-107">Quando a contoso implantou o Microsoft 365 Enterprise, eles queriam migrar seus ativos digitais locais para a nuvem para facilitar o acesso e mais colaboração aberta entre as equipes de pesquisa em Paris, Moscow, Nova York, Pequim e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="cb656-107">When Contoso deployed Microsoft 365 Enterprise, they wanted to transition their on-premises digital assets to the cloud for easier access and more open collaboration across research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 
  
<span data-ttu-id="cb656-108">No entanto, devido à natureza confidencial, o acesso a esses arquivos deve ser:</span><span class="sxs-lookup"><span data-stu-id="cb656-108">However, due to their sensitive nature, access to these files must be:</span></span>

- <span data-ttu-id="cb656-109">Restrito ao conjunto de pessoas que têm permissão para acessá-las.</span><span class="sxs-lookup"><span data-stu-id="cb656-109">Restricted to the set of people who are allowed access them.</span></span> 
- <span data-ttu-id="cb656-110">Protegido por uma política de prevenção contra perda de dados (DLP) para impedir que os usuários os distribuam fora do site.</span><span class="sxs-lookup"><span data-stu-id="cb656-110">Protected with a Data Loss Prevention (DLP) policy to prevent users from distributing them outside the site.</span></span>
- <span data-ttu-id="cb656-111">Criptografado e protegido com permissões para impedir que usuários não autorizados acessem seus conteúdos, mesmo que eles sejam distribuídos fora do site.</span><span class="sxs-lookup"><span data-stu-id="cb656-111">Encrypted and protected with permissions to prevent unauthorized users from accessing their contents, even if they are distributed outside the site.</span></span>

<span data-ttu-id="cb656-112">Administradores de segurança e do SharePoint no departamento de ti da Contoso decidiram usar um [site do SharePoint para dados altamente regulamentados](teams-sharepoint-online-sites-highly-regulated-data.md).</span><span class="sxs-lookup"><span data-stu-id="cb656-112">Security and SharePoint administrators in Contoso's IT department decided to use a [SharePoint site for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md).</span></span>
  
<span data-ttu-id="cb656-113">A contoso usou estas etapas para criar e proteger sites de equipe do SharePoint para suas equipes de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cb656-113">Contoso used these steps to create and secure a SharePoint team sites for their research teams.</span></span>

## <a name="step-1-created-a-private-sharepoint-team-site"></a><span data-ttu-id="cb656-114">Etapa 1: criou um site de equipe do SharePoint privado</span><span class="sxs-lookup"><span data-stu-id="cb656-114">Step 1: Created a private SharePoint team site</span></span>

<span data-ttu-id="cb656-115">Para proteger o acesso ao site do SharePoint, a contoso configurou as [políticas de acesso recomendadas do SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cb656-115">To protect access to the SharePoint site, Contoso IT configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="cb656-116">Em seguida, os administradores de ti da Contoso compilaram uma lista das contas de usuário dos pesquisadores em seus escritórios Paris, Moscou, New York, Pequim e Bangalore.</span><span class="sxs-lookup"><span data-stu-id="cb656-116">Next, Contoso IT admins compiled a list of the user accounts for the researchers in their Paris, Moscow, New York, Beijing, and Bangalore offices.</span></span> 

<span data-ttu-id="cb656-117">Em seguida, um administrador de ti da Contoso criou um novo site de equipe privado chamado **pesquisa** e adicionou todas as contas de usuário para seus pesquisadores.</span><span class="sxs-lookup"><span data-stu-id="cb656-117">Next, a Contoso IT admin created a new private team site named **Research** and added all of the user accounts for its researchers.</span></span>

<span data-ttu-id="cb656-118">Em seguida, eles definiram configurações de permissão adicionais para o site a fim de evitar que pesquisadores compartilhem o acesso ao site e impedir que não pesquisadores solicitem acesso ao site.</span><span class="sxs-lookup"><span data-stu-id="cb656-118">Then they configured additional permission settings for the site to prevent researchers from sharing access to the site and to prevent non-researchers from requesting access to the site.</span></span>

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a><span data-ttu-id="cb656-119">Etapa 2: configurar o site para uma política de DLP restritiva</span><span class="sxs-lookup"><span data-stu-id="cb656-119">Step 2: Configured the site for a restrictive DLP policy</span></span>

<span data-ttu-id="cb656-120">Primeiro, os administradores da Contoso aplicaram o rótulo de retenção do Office 365 **altamente confidencial** existente à pasta documentos do site de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="cb656-120">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the Documents folder of the **Research** site.</span></span>

<span data-ttu-id="cb656-121">Em seguida, criamos uma nova política de DLP do Office 365 chamada **pesquisa** que:</span><span class="sxs-lookup"><span data-stu-id="cb656-121">Next, they created a new Office 365 DLP policy named **Research** that:</span></span>

- <span data-ttu-id="cb656-122">Usa o rótulo de retenção **altamente confidencial** do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb656-122">Uses the **Highly Confidential** Office 365 retention label.</span></span> 
- <span data-ttu-id="cb656-123">Bloqueia os usuários quando eles tentam compartilhar um ativo digital no site de **pesquisa** fora da contoso.</span><span class="sxs-lookup"><span data-stu-id="cb656-123">Blocks users when they attempt to share a digital asset on the **Research** site outside of Contoso.</span></span>

<span data-ttu-id="cb656-124">Para obter os detalhes de configuração, consulte [proteger arquivos do SharePoint com rótulos de retenção e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span><span class="sxs-lookup"><span data-stu-id="cb656-124">For the configuration details, see [Protect SharePoint files with retention labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</span></span>

## <a name="step-4-created-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="cb656-125">Etapa 4: criar um subrótulo de sensibilidade do Office 365 para o site</span><span class="sxs-lookup"><span data-stu-id="cb656-125">Step 4: Created an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="cb656-126">Os administradores da Contoso criaram um novo subrótulo de confidencialidade do Office 365 chamado **Teams de pesquisa** do rótulo **altamente confidencial** que:</span><span class="sxs-lookup"><span data-stu-id="cb656-126">Contoso admins created a new Office 365 sensitivity sublabel named **Research Teams** of the **Highly Confidential** label that:</span></span>

- <span data-ttu-id="cb656-127">Requer criptografia.</span><span class="sxs-lookup"><span data-stu-id="cb656-127">Requires encryption.</span></span>
- <span data-ttu-id="cb656-128">Permite permissões de coautoria para o grupo de **pesquisa** do Office 365</span><span class="sxs-lookup"><span data-stu-id="cb656-128">Allows Co-Author permissions for the **Research** Office 365 group</span></span>
- <span data-ttu-id="cb656-129">Aplica-se ao grupo de **pesquisa** do Office 365</span><span class="sxs-lookup"><span data-stu-id="cb656-129">Applies to the **Research** Office 365 group</span></span>

<span data-ttu-id="cb656-130">Aqui está a configuração resultante do site de equipe de **pesquisa** para ativos altamente confidenciais.</span><span class="sxs-lookup"><span data-stu-id="cb656-130">Here is the resulting configuration of the **Research** team site for highly confidential assets.</span></span>

![A configuração resultante do site de equipe de pesquisa para ativos altamente confidenciais](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

<span data-ttu-id="cb656-132">Arquivos em pastas do site de **pesquisa** são protegidos por:</span><span class="sxs-lookup"><span data-stu-id="cb656-132">Files in folders of the **Research** site are protected by:</span></span>

- <span data-ttu-id="cb656-133">As permissões de site, que permitem acesso somente aos membros do grupo **Research** Office 365.</span><span class="sxs-lookup"><span data-stu-id="cb656-133">The site permissions, which only allow access to members of the **Research** Office 365 group.</span></span>
- <span data-ttu-id="cb656-134">A política de DLP de **pesquisa** , que usa o rótulo de retenção **altamente confidencial** e as configurações que impedem o arquivo de ser compartilhado com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="cb656-134">The **Research** DLP policy, which uses the **Highly Confidential** retention label and settings that prevent the file from being shared with external users.</span></span>
- <span data-ttu-id="cb656-135">O subrótulo de confidencialidade das **equipes de pesquisa** , com criptografia e permissões que trafegam com o arquivo se ele for movido ou copiado do site de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="cb656-135">The **Research Teams** sensitivity sublabel, with encryption and permissions that travel with the file if it is moved or copied from the **Research** site.</span></span>

<span data-ttu-id="cb656-136">Aqui está um exemplo de um arquivo armazenado no site de **pesquisa** com o subrótulo de confidencialidade das **equipes de pesquisa** atribuído.</span><span class="sxs-lookup"><span data-stu-id="cb656-136">Here is an example of a file stored in the **Research** site with the **Research Teams** sensitivity sublabel assigned.</span></span>

![A configuração resultante do site de equipe de pesquisa para ativos altamente confidenciais](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a><span data-ttu-id="cb656-138">Etapa 5: migrar os dados de pesquisa do SharePoint local</span><span class="sxs-lookup"><span data-stu-id="cb656-138">Step 5: Migrated the on-premises SharePoint research data</span></span>

<span data-ttu-id="cb656-139">Os administradores da Contoso moveram todos os arquivos de pesquisa local no site do SharePoint Server 2016 local para pastas no novo site do SharePoint de **pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="cb656-139">Contoso admins moved all of the on-premises research files in the on-premises SharePoint Server 2016 site to folders in the new **Research** SharePoint site.</span></span>

## <a name="step-6-trained-their-researchers"></a><span data-ttu-id="cb656-140">Etapa 6: treinado seus pesquisadores</span><span class="sxs-lookup"><span data-stu-id="cb656-140">Step 6: Trained their researchers</span></span>

<span data-ttu-id="cb656-141">A equipe de segurança da Contoso treinou os membros do grupo **Research** Office 365 em um curso obrigatório que os apresentou por meio de:</span><span class="sxs-lookup"><span data-stu-id="cb656-141">Contoso security staff trained the members of the **Research** Office 365 group in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="cb656-142">Como acessar o novo site de **pesquisa** e seus arquivos existentes.</span><span class="sxs-lookup"><span data-stu-id="cb656-142">How to access the new **Research** site and its existing files.</span></span>
- <span data-ttu-id="cb656-143">Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="cb656-143">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="cb656-144">Uma demonstração de como a política de DLP de **pesquisa** impede que os arquivos sejam compartilhados externamente.</span><span class="sxs-lookup"><span data-stu-id="cb656-144">A demonstration of how the **Research** DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="cb656-145">Como rotular arquivos com o subrótulo de confidencialidade das **equipes de pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="cb656-145">How to label files with the **Research Teams** sensitivity sublabel.</span></span>
- <span data-ttu-id="cb656-146">Uma demonstração de como o subrótulo das **equipes de pesquisa** protege um arquivo, mesmo quando ele é vazado do site.</span><span class="sxs-lookup"><span data-stu-id="cb656-146">A demonstration of how the **Research Teams** sub-label protects a file even when it is leaked from the site.</span></span>

<span data-ttu-id="cb656-147">O resultado final é um ambiente seguro no qual os pesquisadores podem colaborar através da Contoso em um ambiente seguro em arquivos que contenham informações de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="cb656-147">The end result is a secure environment in which the researchers can collaborate across Contoso in a secure environment on files containing research information.</span></span> 

<span data-ttu-id="cb656-148">Se um documento de pesquisa com o subrótulo **Teams de pesquisa** deixa o site de **pesquisa** , ele é criptografado e acessível somente aos membros do grupo **Research** Office 365 com credenciais de conta de usuário válidas.</span><span class="sxs-lookup"><span data-stu-id="cb656-148">If a research document with the **Research Teams** sublabel leaves the **Research** site, it is encrypted and accessible only to members of the **Research** Office 365 group with valid user account credentials.</span></span>

## <a name="next-step"></a><span data-ttu-id="cb656-149">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="cb656-149">Next step</span></span>

<span data-ttu-id="cb656-150">[Implantar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb656-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb656-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="cb656-151">See also</span></span>

<span data-ttu-id="cb656-152">[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="cb656-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
