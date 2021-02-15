---
title: Determinar se a Implantação Centralizada de complementos funciona para sua organização
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine se o locatário e os usuários atendem aos requisitos, para que você possa usar a Implantação Centralizada para implantar os complementos do Office.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519360"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="64dda-103">Determinar se a Implantação Centralizada de complementos funciona para sua organização</span><span class="sxs-lookup"><span data-stu-id="64dda-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="64dda-104">A Implantação Centralizada é a maneira recomendada e mais rica em recursos para a maioria dos clientes implantar os complementos do Office para usuários e grupos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="64dda-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="64dda-105">Se você for um administrador, use este guia para determinar se sua organização e os usuários atendem aos requisitos para que você possa usar a Implantação Centralizada.</span><span class="sxs-lookup"><span data-stu-id="64dda-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="64dda-106">A Implantação Centralizada oferece os seguintes benefícios:</span><span class="sxs-lookup"><span data-stu-id="64dda-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="64dda-107">Um administrador global pode atribuir um complemento diretamente a um usuário, a vários usuários por meio de um grupo ou a todos na organização.</span><span class="sxs-lookup"><span data-stu-id="64dda-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="64dda-108">Quando o aplicativo relevante do Office é iniciado, o complemento é baixado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="64dda-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="64dda-109">Se o complemento for compatível com comandos de complemento, o complemento aparecerá automaticamente na faixa de opções dentro do aplicativo do Office.</span><span class="sxs-lookup"><span data-stu-id="64dda-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="64dda-110">Os complementos não aparecerão mais para os usuários se o administrador desligar ou excluir o complemento, ou se o usuário for removido do Azure Active Directory ou de um grupo ao qual o complemento está atribuído.</span><span class="sxs-lookup"><span data-stu-id="64dda-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="64dda-111">A Implantação Centralizada dá suporte a três plataformas de área de trabalho de aplicativos do Windows, Mac e Online do Office.</span><span class="sxs-lookup"><span data-stu-id="64dda-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="64dda-112">A Implantação Centralizada também dá suporte a iOS e Android (Apenas para o Outlook Mobile Add-ins).</span><span class="sxs-lookup"><span data-stu-id="64dda-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="64dda-113">Pode levar até 24 horas para um complemento aparecer para o cliente para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="64dda-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="64dda-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64dda-114">Requirements</span></span>

<span data-ttu-id="64dda-115">A implantação centralizada de complementos exige que os usuários usem SKUs do Microsoft 365 Enterprise: E3/E5/F3 ou SKUs de Negócios: Business Basic, Business Standard, Business Premium (e estão assinados no Office usando sua ID organizacional) e ter caixas de correio ativas do Exchange Online e exchange Online.</span><span class="sxs-lookup"><span data-stu-id="64dda-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="64dda-116">Seu diretório de assinatura deve estar ou federado ao Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="64dda-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="64dda-117">Você pode exibir os requisitos específicos para o Office e o Exchange abaixo ou usar o Verificador de Compatibilidade de Implantação [Centralizado.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="64dda-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="64dda-118">A Implantação Centralizada não é compatível com:</span><span class="sxs-lookup"><span data-stu-id="64dda-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="64dda-119">Suplementos que visam o Word, Excel ou o PowerPoint no Office 2013</span><span class="sxs-lookup"><span data-stu-id="64dda-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="64dda-120">Um serviço de diretório local</span><span class="sxs-lookup"><span data-stu-id="64dda-120">An on-premises directory service</span></span>
- <span data-ttu-id="64dda-121">Implantação de add-in em uma caixa de correio do Exchange no lugar</span><span class="sxs-lookup"><span data-stu-id="64dda-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="64dda-122">Implantação de suplemento no SharePoint</span><span class="sxs-lookup"><span data-stu-id="64dda-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="64dda-123">Aplicativos do Teams</span><span class="sxs-lookup"><span data-stu-id="64dda-123">Teams apps</span></span>
- <span data-ttu-id="64dda-124">Implantação de complementos COM (Component Object Model) ou Visual Studio Tools for Office (VSTO).</span><span class="sxs-lookup"><span data-stu-id="64dda-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="64dda-125">Implantações do Microsoft 365 que não incluem o Exchange Online, como SKUs: Aplicativos do Microsoft 365 para Empresas e Aplicativos do Microsoft 365 para Empresas.</span><span class="sxs-lookup"><span data-stu-id="64dda-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="64dda-126">Requisitos do Office</span><span class="sxs-lookup"><span data-stu-id="64dda-126">Office Requirements</span></span>

- <span data-ttu-id="64dda-127">Para os complementos do Word, Excel e PowerPoint, os usuários devem estar usando um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="64dda-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="64dda-128">Em um dispositivo Windows, versão 1704 ou posterior do Microsoft 365 Enterprise SKUs: E3/E5/F3 ou SKUs de negócios: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="64dda-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="64dda-129">Em um Mac, versão 15.34 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="64dda-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="64dda-130">Para o Outlook, os usuários devem estar usando um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="64dda-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="64dda-131">Versão 1701 ou posterior das SKUs do Microsoft 365 Enterprise: E3/E5/F3 ou SKUs corporativas: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="64dda-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="64dda-132">Versão 1808 ou posterior do Office Professional Plus 2019 ou Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="64dda-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="64dda-133">Versão 16.0.4494.1000 ou posterior do Office Professional Plus 2016 (MSI) ou Do Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="64dda-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="64dda-134">Versão 15.0.4937.1000 ou posterior do Office Professional Plus 2013 (MSI) ou Do Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="64dda-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="64dda-135">Versão 16.0.9318.1000 ou posterior do Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="64dda-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="64dda-136">Versão 2.75.0 ou posterior do Outlook Mobile para iOS</span><span class="sxs-lookup"><span data-stu-id="64dda-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="64dda-137">Versão 2.2.145 ou posterior do Outlook Mobile para Android</span><span class="sxs-lookup"><span data-stu-id="64dda-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="64dda-138">\*As versões MSI do Outlook mostram os complementos instalados pelo administrador na faixa de opções apropriada do Outlook, não na seção "Meus complementos".</span><span class="sxs-lookup"><span data-stu-id="64dda-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="64dda-139">Requisitos do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="64dda-139">Exchange Online requirements</span></span>

<span data-ttu-id="64dda-140">O Microsoft Exchange armazena os manifestos de complemento no locatário da sua organização.</span><span class="sxs-lookup"><span data-stu-id="64dda-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="64dda-141">O administrador que está implantando os complementos e os usuários que recebem esses complementos devem estar em uma versão do Exchange Online que dá suporte à autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="64dda-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="64dda-p106">Fale com o administrador do Exchange da sua organização para saber qual configuração está sendo usada. Para verificar a conectividade por usuário do OAuth, use o cmdlet do PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="64dda-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="64dda-144">Verificação de compatibilidade de implantação centralizada</span><span class="sxs-lookup"><span data-stu-id="64dda-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="64dda-145">Usando o Verificador de Compatibilidade de Implantação Centralizada, você pode verificar se os usuários em seu locatário estão definidos para usar a Implantação Centralizada para Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="64dda-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="64dda-146">O Verificador de Compatibilidade não é necessário para o suporte do Outlook.</span><span class="sxs-lookup"><span data-stu-id="64dda-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="64dda-147">Baixe o verificador de compatibilidade [aqui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="64dda-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="64dda-148">Executar o checker de compatibilidade</span><span class="sxs-lookup"><span data-stu-id="64dda-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="64dda-149">Inicie uma janela de PowerShell.exe elevada.</span><span class="sxs-lookup"><span data-stu-id="64dda-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="64dda-150">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="64dda-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="64dda-151">Execute o **comando Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="64dda-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="64dda-152">Este comando solicita  *_tenantDomain_* (por exemplo, *TailspinToysIncorporated.onmicrosoft. </span> com*) e  *_credenciais de TenantAdmin_* (use suas credenciais de administrador global) e, em seguida, solicita o consentimento.</span><span class="sxs-lookup"><span data-stu-id="64dda-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="64dda-153">O verificador pode ser concluído em minutos ou horas, dependendo da quantidade de usuários no locatário.</span><span class="sxs-lookup"><span data-stu-id="64dda-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="64dda-154">Quando a ferramenta conclui a execução, ela gera um arquivo de saída no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="64dda-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="64dda-155">O arquivo é salvo em **C:\windows\system32** por padrão.</span><span class="sxs-lookup"><span data-stu-id="64dda-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="64dda-156">O arquivo de saída contém as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="64dda-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="64dda-157">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="64dda-157">User Name</span></span>
    
- <span data-ttu-id="64dda-158">ID de usuário (o endereço de email do usuário)</span><span class="sxs-lookup"><span data-stu-id="64dda-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="64dda-159">Implantação Centralizada pronta, se os itens restantes forem verdadeiros</span><span class="sxs-lookup"><span data-stu-id="64dda-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="64dda-160">Plano do Office – O plano do Office para o que eles estão licenciados</span><span class="sxs-lookup"><span data-stu-id="64dda-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="64dda-161">Office ativado - Se ele ativou o Office</span><span class="sxs-lookup"><span data-stu-id="64dda-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="64dda-162">Caixa de correio com suporte - Se ele usa uma caixa de correio habilitada para OAuth</span><span class="sxs-lookup"><span data-stu-id="64dda-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="64dda-163">A autenticação multifator não é suportada ao usar o módulo Do PowerShell de Implantação Central.</span><span class="sxs-lookup"><span data-stu-id="64dda-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="64dda-164">Atribuições de usuário e grupo</span><span class="sxs-lookup"><span data-stu-id="64dda-164">User and group assignments</span></span>

<span data-ttu-id="64dda-165">Atualmente, o recurso Implantação Centralizada oferece suporte à maioria dos grupos com suporte do Azure Active Directory, incluindo grupos, listas de distribuição e grupos de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="64dda-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64dda-166">Os grupos de segurança não habilitados por email não têm suporte no momento.</span><span class="sxs-lookup"><span data-stu-id="64dda-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="64dda-167">A Implantação Centralizada dá suporte a atribuições para usuários individuais, grupos e todos no locatário.</span><span class="sxs-lookup"><span data-stu-id="64dda-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="64dda-168">A Implantação Centralizada é compatível com usuários em grupos de nível superior ou grupos sem grupos-pai, mas não é compatível com usuários em grupos aninhados ou grupos com grupos-pai.</span><span class="sxs-lookup"><span data-stu-id="64dda-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="64dda-p110">Examine o exemplo a seguir em que Sara, Maria Eduarda e o grupo do Departamento de Vendas são atribuídos a um suplemento. Como o Departamento de Vendas da Costa Oeste é um grupo aninhado, Humberto e Fábio não estão atribuídos a um suplemento.</span><span class="sxs-lookup"><span data-stu-id="64dda-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagrama do departamento de vendas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="64dda-172">Determinar se um grupo contém grupos aninhados</span><span class="sxs-lookup"><span data-stu-id="64dda-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="64dda-173">A maneira mais fácil de detectar se um grupo contém grupos aninhados é exibir o cartão de visita do grupo no Outlook.</span><span class="sxs-lookup"><span data-stu-id="64dda-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="64dda-174">Se você inserir o  nome do grupo no campo Para de um email e selecionar o nome do grupo quando for resolvido, ele mostrará se ele contém usuários ou grupos aninhados.</span><span class="sxs-lookup"><span data-stu-id="64dda-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="64dda-175">No exemplo abaixo, a guia **Membros** do cartão de visita do Outlook para o Grupo de Teste não mostra usuários nem grupos, apenas dois subgrupos.</span><span class="sxs-lookup"><span data-stu-id="64dda-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Guia Membros do cartão de visita do Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="64dda-p112">É possível fazer a consulta inversa resolvendo o grupo para ver se ele é membro de algum grupo. No exemplo abaixo, na guia **Associação** do cartão de visita do Outlook, é possível ver que o Subgrupo 1 é membro do Grupo de Teste.</span><span class="sxs-lookup"><span data-stu-id="64dda-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Guia Associação do cartão de visita do Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="64dda-p113">Se preferir, use a API do Graph do Azure Active Directory para executar consultas para localizar a lista de grupos dentro de um grupo. Para saber mais, veja [Operações em grupos | Referência da API do Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="64dda-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="64dda-182">Entrar em contato com a Microsoft para obter suporte</span><span class="sxs-lookup"><span data-stu-id="64dda-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="64dda-183">Se você ou seus usuários encontrarem problemas ao carregar o complemento ao usar aplicativos do Office para a Web (Word, Excel etc.), que foram implantados centralmente, talvez seja necessário entrar em contato com o suporte da Microsoft[(](../contact-support-for-business-products.md)saiba como ).</span><span class="sxs-lookup"><span data-stu-id="64dda-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="64dda-184">Forneça as seguintes informações sobre seu ambiente do Microsoft 365 no tíquete de suporte.</span><span class="sxs-lookup"><span data-stu-id="64dda-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="64dda-185">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="64dda-185">**Platform**</span></span>|<span data-ttu-id="64dda-186">**Informações de depuração**</span><span class="sxs-lookup"><span data-stu-id="64dda-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64dda-187">Office</span><span class="sxs-lookup"><span data-stu-id="64dda-187">Office</span></span>  <br/> | <span data-ttu-id="64dda-188">Registros de Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="64dda-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="64dda-189">ID do locatário ( [saiba como](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="64dda-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="64dda-190">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="64dda-190">CorrelationID.</span></span> <span data-ttu-id="64dda-191">Veja a origem de uma das páginas do Office, procure o valor da ID de Correlação e envie-o para suporte:</span><span class="sxs-lookup"><span data-stu-id="64dda-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="64dda-192">Clientes avançados (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="64dda-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="64dda-193">Registros de Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="64dda-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="64dda-194">Números de com build do aplicativo cliente (preferencialmente como uma captura de tela de **Arquivo/Conta)**</span><span class="sxs-lookup"><span data-stu-id="64dda-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
