---
title: Exibir licenças e serviços do Microsoft 365 com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Explica como usar o PowerShell para exibir informações sobre os planos de licenciamento, serviços e licenças disponíveis na sua organização do Microsoft 365.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687160"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="ed5ab-103">Exibir licenças e serviços do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed5ab-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="ed5ab-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ed5ab-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ed5ab-105">Cada assinatura do Microsoft 365 consiste nos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="ed5ab-106">**Planos de licenciamento** Eles também são conhecidos como planos de licença ou planos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="ed5ab-107">Os planos de licenciamento definem os serviços do Microsoft 365 que estão disponíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="ed5ab-108">Sua assinatura do Microsoft 365 pode conter vários planos de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="ed5ab-109">Um plano de licenciamento de exemplo seria o Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="ed5ab-110">**Serviços** do Eles também são conhecidos como planos de serviço.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="ed5ab-111">Os serviços são os produtos, recursos e recursos do Microsoft 365 que estão disponíveis em cada plano de licenciamento, por exemplo, Exchange Online e Microsoft 365 aplicativos para empresas (anteriormente denominado Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="ed5ab-112">Os usuários podem receber várias licenças de diferentes planos de licenciamento que garantem o acesso a diferentes serviços.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="ed5ab-113">**Licenças** do Cada plano de licenciamento contém o número de licenças que você comprou.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="ed5ab-114">Você atribui licenças aos usuários para que eles possam usar os serviços do Microsoft 365 definidos pelo plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="ed5ab-115">Cada conta de usuário requer pelo menos uma licença de um plano de licenciamento para que possa fazer logon no Microsoft 365 e usar os serviços.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="ed5ab-116">Você pode usar o PowerShell para Microsoft 365 para exibir detalhes sobre os planos de licenciamento, licenças e serviços disponíveis na sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="ed5ab-117">Para obter mais informações sobre os produtos, recursos e serviços que estão disponíveis em assinaturas diferentes do Office 365, confira [Opções de plano do office 365](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="ed5ab-118">Use o PowerShell do Azure Active Directory para o módulo do gráfico</span><span class="sxs-lookup"><span data-stu-id="ed5ab-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="ed5ab-119">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="ed5ab-120">Para exibir informações resumidas sobre seus planos de licenciamento atuais e as licenças disponíveis para cada plano, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="ed5ab-121">Os resultados contêm:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-121">The results contain:</span></span>
  
- <span data-ttu-id="ed5ab-122">**SkuPartNumber:** Mostra os planos de licenciamento disponíveis para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="ed5ab-123">Por exemplo, `ENTERPRISEPACK` é o nome do plano de licença para o Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="ed5ab-124">**Habilitado:** Número de licenças que você comprou para um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="ed5ab-125">**ConsumedUnits:** número de licenças que você atribuiu aos usuários de um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="ed5ab-126">Para exibir detalhes sobre os serviços do Microsoft 365 que estão disponíveis em todos os seus planos de licença, primeiro exiba uma lista de seus planos de licença.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="ed5ab-127">Em seguida, armazene as informações dos planos de licença em uma variável.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="ed5ab-128">Em seguida, exiba os serviços em um plano de licença específico.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="ed5ab-129">\<index> é um inteiro que especifica o número da linha do plano de licença a partir da exibição do `Get-AzureADSubscribedSku | Select SkuPartNumber` comando, menos 1.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="ed5ab-130">Por exemplo, se a exibição do `Get-AzureADSubscribedSku | Select SkuPartNumber` comando for:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="ed5ab-131">Em seguida, o comando para exibir os serviços do plano de licença do ENTERPRISEPREMIUM é:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="ed5ab-132">ENTERPRISEPREMIUM é a terceira linha.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="ed5ab-133">Portanto, o valor de índice é (3-1) ou 2.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="ed5ab-134">Para obter uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, confira [nomes de produtos e identificadores de planos de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ed5ab-135">Use o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ed5ab-136">Primeiro, [Conecte-se ao seu locatário do Microsoft 365](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="ed5ab-137">Um script do PowerShell está disponível e automatiza os procedimentos descritos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="ed5ab-138">Especificamente, o script permite que você exiba e desabilite serviços na sua organização do Microsoft 365, incluindo Sway.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="ed5ab-139">Confira mais informações em [desabilitar o acesso ao Sway com o PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="ed5ab-140">Para exibir informações resumidas sobre seus planos de licenciamento atuais e as licenças disponíveis para cada plano, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="ed5ab-141">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="ed5ab-142">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="ed5ab-143">Os resultados contêm as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="ed5ab-144">**AccountSkuId:** Mostre os planos de licenciamento disponíveis para sua organização usando a sintaxe `<CompanyName>:<LicensingPlan>` .</span><span class="sxs-lookup"><span data-stu-id="ed5ab-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="ed5ab-145">_\<CompanyName>_ é o valor que você forneceu quando registrou no Microsoft 365 e é exclusivo para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="ed5ab-146">O _\<LicensingPlan>_ valor é o mesmo para todos.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="ed5ab-147">Por exemplo, no valor `litwareinc:ENTERPRISEPACK` , o nome da empresa é  `litwareinc` e o nome do plano de licenciamento  `ENTERPRISEPACK` , que é o nome do sistema do Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="ed5ab-148">**ActiveUnits:** Número de licenças que você comprou para um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="ed5ab-149">**WarningUnits:** número de licenças em um plano de licenciamento que você não renovou e que expirará após um período de carência de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="ed5ab-150">**ConsumedUnits:** número de licenças que você atribuiu aos usuários de um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="ed5ab-151">Para exibir detalhes sobre os serviços do Microsoft 365 que estão disponíveis em todos os seus planos de licença, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="ed5ab-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="ed5ab-152">A tabela a seguir mostra os planos de serviço do Microsoft 365 e seus nomes amigáveis para os serviços mais comuns.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="ed5ab-153">Sua lista de planos de serviço pode ser diferente.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="ed5ab-154">**Plano de serviço**</span><span class="sxs-lookup"><span data-stu-id="ed5ab-154">**Service plan**</span></span>|<span data-ttu-id="ed5ab-155">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ed5ab-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="ed5ab-156">Sway</span><span class="sxs-lookup"><span data-stu-id="ed5ab-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="ed5ab-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed5ab-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="ed5ab-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="ed5ab-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="ed5ab-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="ed5ab-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="ed5ab-160">Microsoft 365 Apps for Enterprise *(anteriormente chamado Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="ed5ab-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="ed5ab-161">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ed5ab-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="ed5ab-162">Office</span><span class="sxs-lookup"><span data-stu-id="ed5ab-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="ed5ab-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ed5ab-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="ed5ab-164">Plano 2 do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ed5ab-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="ed5ab-165">Para obter uma lista completa de planos de licença (também conhecidos como nomes de produtos), seus planos de serviço incluídos e seus nomes amigáveis correspondentes, confira [nomes de produtos e identificadores de planos de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="ed5ab-166">Para exibir detalhes sobre os serviços do Microsoft 365 que estão disponíveis em um plano de licenciamento específico, use a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="ed5ab-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="ed5ab-167">Este exemplo mostra os serviços que estão disponíveis no plano de licenciamento do litwareinc: ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="ed5ab-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="ed5ab-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed5ab-168">See also</span></span>

[<span data-ttu-id="ed5ab-169">Gerenciar contas de usuário, licenças e grupos do Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed5ab-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ed5ab-170">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed5ab-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ed5ab-171">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed5ab-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
