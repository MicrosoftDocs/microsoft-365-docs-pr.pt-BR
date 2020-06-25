---
title: Configuração de base leve
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use este Guia de Laboratório de Teste para criar um ambiente de teste leve para testar o Microsoft 365 Enterprise.
ms.openlocfilehash: 7a4800d374416a1e197536bc1a867d3fbc4b1243
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818748"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="2bd3d-103">A configuração de base leve</span><span class="sxs-lookup"><span data-stu-id="2bd3d-103">The lightweight base configuration</span></span>

<span data-ttu-id="2bd3d-104">*Este Guia de Laboratório de Testes pode ser usado para ambientes de teste corporativo do Microsoft 365 Enterprise e do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="2bd3d-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2bd3d-105">Este artigo fornece instruções passo a passo para criar um ambiente simplificado com a assinatura do Microsoft 365 E5 e um computador com o Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![O ambiente de teste leve do Microsoft 3656 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="2bd3d-107">Use o ambiente resultante para testar os recursos e as funcionalidades do [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="2bd3d-109">Acesse [Guia de laboratório de teste do Microsoft 365 Enterprise](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para obter um mapa visual de todos os artigos da Guia de laboratório de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-109">Click [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="2bd3d-110">Fase 1: criar uma assinatura do Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="2bd3d-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="2bd3d-111">Começaremos com uma assinatura de avaliação do Office 365 E5 e, em seguida, adicionaremos a assinatura do Microsoft 365 E5 a ela.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="2bd3d-112">Para começar a usar a sua assinatura de avaliação do Office 365 E5, primeiro é necessário um nome de empresa fictícia e uma nova conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="2bd3d-113">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-113">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required.</span></span> <span data-ttu-id="2bd3d-114">Record your fictitious company name here:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-114">Record your fictitious company name here:</span></span> ![Linha](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="2bd3d-116">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-116">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address.</span></span> <span data-ttu-id="2bd3d-117">You will use this account to sign up for Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-117">You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="2bd3d-118">Armazene o nome e sobrenome da sua nova conta aqui:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-118">Record the first and last name of your new account here:</span></span> ![Linha](../media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="2bd3d-120">Armazene o novo endereço da conta de email aqui: </span><span class="sxs-lookup"><span data-stu-id="2bd3d-120">Record the new email account address here:</span></span> ![Linha](../media/Common-Images/TableLine.png)<span data-ttu-id="2bd3d-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="2bd3d-122">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="2bd3d-123">Inscrever-se em uma assinatura de avaliação do Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="2bd3d-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="2bd3d-124">Abra o navegador da Internet no computador e vá para [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="2bd3d-125">Na página **Obrigado por escolher o Office 365 E5**, especifique o endereço de sua nova conta de email na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="2bd3d-126">Na etapa 2 do processo de assinatura de avaliação, digite as informações solicitadas e execute a verificação.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="2bd3d-127">Na etapa 3, digite o nome da organização e, em seguida, o nome da conta que será o administrador global da assinatura.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="2bd3d-128">Para a etapa 4, armazene a URL da página de entrada aqui (selecione e copie): </span><span class="sxs-lookup"><span data-stu-id="2bd3d-128">For step 4, record the sign-in page here (select and copy):</span></span> ![Linha](../media/Common-Images/TableLine.png) 
6. <span data-ttu-id="2bd3d-130">Armazene a ID de usuário aqui: ![Linha](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2bd3d-130">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="2bd3d-131">Armazene a senha que você digitou em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="2bd3d-132">Esse valor será chamado de **nome do administrador global**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-132">This value will be referred to as the **global administrator name**.</span></span>
8. <span data-ttu-id="2bd3d-133">Clique em **Ir para Configuração**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="2bd3d-134">Na configuração do Office 365 E5, clique em **Continuar usando *sua organização*.onmicrosoft.com para o email e para entrar** e clique em **Sair e continuar mais tarde**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="2bd3d-135">Você deve ver o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="2bd3d-136">A criação de uma assinatura de avaliação do Office 365 é necessária para que seu ambiente de teste tenha um locatário do Azure AD separado de qualquer assinatura paga que você possua.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="2bd3d-137">Este separação significa que você pode adicionar e remover usuários e grupos no locatário de teste sem afetar suas assinaturas de produção.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="2bd3d-138">Fase 2: configurar a sua assinatura de avaliação do Office 365</span><span class="sxs-lookup"><span data-stu-id="2bd3d-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="2bd3d-139">Nesta fase, você configurará a sua assinatura com outros usuários, atribuindo a eles licenças do Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-139">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="2bd3d-140">Use as instruções em [Conectar ao Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) para conectar à sua assinatura com módulo o Azure Active Directory PowerShell for Graph do seu computador.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="2bd3d-141">Na caixa de diálogo **Solicitação de credenciais do Windows PowerShell**, digite o nome do administrador global (exemplo: jdoe@contosotoycompany.onmicrosoft.com) e senha.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-141">In the **Windows PowerShell Credential Request** dialog box, type the global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="2bd3d-142">Preencha o nome de sua organização (exemplo: contosotoycompany), o código de país com dois caracteres para a sua localização e execute os seguintes comandos no prompt do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="2bd3d-143">O uso de uma senha comum aqui é para a automação e facilidade de configuração para um ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="2bd3d-144">Obviamente, isso é recomendado para assinaturas de produção.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="2bd3d-145">Registrar principais informações para referência futura</span><span class="sxs-lookup"><span data-stu-id="2bd3d-145">Record key information for future reference</span></span>

<span data-ttu-id="2bd3d-146">Talvez você queira imprimir este artigo para registrar as informações específicas necessárias para esse ambiente pelos 30 dias da assinatura de avaliação do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="2bd3d-147">É possível estender facilmente a assinatura de avaliação por mais 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="2bd3d-148">Para um ambiente de teste permanente, crie uma nova assinatura paga com um locatário do Azure AD separado e uma pequena quantidade de licenças.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="2bd3d-149">Registre esses valores:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-149">Record these values:</span></span>
  
- <span data-ttu-id="2bd3d-150">nome do administrador global:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-150">global administrator name:</span></span> ![Linha](../media/Common-Images/TableLine.png)<span data-ttu-id="2bd3d-152">onmicrosoft.com (na etapa 6 da Fase 1)</span><span class="sxs-lookup"><span data-stu-id="2bd3d-152">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="2bd3d-153">Também armazene a senha dessa conta em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="2bd3d-154">Nome da sua organização de assinatura de avaliação: </span><span class="sxs-lookup"><span data-stu-id="2bd3d-154">Your trial subscription organization name:</span></span> ![Linha](../media/Common-Images/TableLine.png) <span data-ttu-id="2bd3d-156">(na etapa 4 da Fase 1)</span><span class="sxs-lookup"><span data-stu-id="2bd3d-156">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="2bd3d-157">Para listar as contas do usuário 2, Usuário 3, Usuário 4 e Usuário 5, execute o seguinte comando no prompt do Módulo do Windows Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="2bd3d-158">Armazene os nomes de contas aqui:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="2bd3d-159">Nome da conta do usuário 2: usuário2@</span><span class="sxs-lookup"><span data-stu-id="2bd3d-159">User 2 account name: user2@</span></span>![Linha](../media/Common-Images/TableLine.png)<span data-ttu-id="2bd3d-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2bd3d-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="2bd3d-162">Nome da conta do usuário 3: usuário3@</span><span class="sxs-lookup"><span data-stu-id="2bd3d-162">User 3 account name: user3@</span></span>![Linha](../media/Common-Images/TableLine.png)<span data-ttu-id="2bd3d-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2bd3d-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="2bd3d-165">Nome da conta do usuário 4: usuário4@</span><span class="sxs-lookup"><span data-stu-id="2bd3d-165">User 4 account name: user4@</span></span>![Linha](../media/Common-Images/TableLine.png)<span data-ttu-id="2bd3d-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2bd3d-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="2bd3d-168">Nome da conta do usuário 5: usuário5@</span><span class="sxs-lookup"><span data-stu-id="2bd3d-168">User 5 account name: user5@</span></span>![Linha](../media/Common-Images/TableLine.png)<span data-ttu-id="2bd3d-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2bd3d-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="2bd3d-171">Também registre a senha em comum dessas contas em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="2bd3d-172">Usando um ambiente de teste do Office 365</span><span class="sxs-lookup"><span data-stu-id="2bd3d-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="2bd3d-173">Se você quiser apenas um ambiente de teste do Office 365, você pode parar aqui.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="2bd3d-174">Confira [Guias de Laboratório de Testes do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) para Guias de Laboratório de Testes adicionais que se aplicam ao Office 365 e ao Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="2bd3d-175">Fase 3: adicionar uma assinatura de avaliação do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2bd3d-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="2bd3d-176">Nesta fase, inscreva-se para a assinatura de avaliação do Microsoft 365 E5 e adicione-a à mesma organização de sua assinatura de avaliação do Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="2bd3d-177">Primeiro, adicione a assinatura de avaliação do Microsoft 365 E5 e atribua a nova licença do Microsoft 365 à sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="2bd3d-178">Com uma instância particular de um navegador da Internet, acesse o Centro de administração do Microsoft 365 na [https://admin.microsoft.com](https://admin.microsoft.com) com suas credenciais da conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="2bd3d-179">Na página **Centro de administração do Microsoft 365**, na navegação à esquerda, clique em **Cobrança > Serviços de compra**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="2bd3d-180">Na página **Serviços de compra**, clique em **Microsoft 365 E5** e, em seguida, clique em **Obter avaliação gratuita**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="2bd3d-181">Na página **Avaliação do Microsoft 365 E5**, escolha receber uma chamada ou um texto, insira seu número de telefone e clique em **Receber mensagem de texto** ou **Receber chamada**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="2bd3d-182">Execute a verificação.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-182">Perform the verification.</span></span>

5. <span data-ttu-id="2bd3d-183">Na página **Confirmar seu pedido**, clique em **Experimentar agora**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="2bd3d-184">Na página **Recibo do pedido**, clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="2bd3d-185">No centro de administração do Microsoft 365, clique em **Usuários > Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="2bd3d-186">Em **Usuários ativos**, clique na sua conta de administrador.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="2bd3d-187">Clique em **Licenças e aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="2bd3d-188">Desabilite a licença do Office 365 Enterprise E5 e habilite a licença do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="2bd3d-189">Clique em **Salvar alterações** e feche o painel de informações da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="2bd3d-190">Em seguida, repita as etapas de 8 a 11 do procedimento anterior para todas as outras contas (Usuário 2, Usuário 3, Usuário 4 e Usuário 5).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bd3d-191">A assinatura de avaliação do Microsoft 365 E5 é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="2bd3d-192">Para um ambiente de teste permanente, converta esta assinatura de avaliação em uma assinatura paga com uma pequena quantidade de licenças.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="2bd3d-193">Seu ambiente de teste agora tem:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="2bd3d-194">Uma assinatura de avaliação do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="2bd3d-195">Todas as suas contas de usuário apropriadas (tanto a conta de administrador global como todas as cinco contas de usuário) são habilitadas para usar o Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="2bd3d-196">Essa é a configuração resultante, que adiciona o Microsoft 365 E5, incluindo o Office 365 e o Enterprise Security + Management (EMS).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Fase 3 do ambiente de teste do Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="2bd3d-198">Fase 4: criar um computador com o Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2bd3d-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="2bd3d-199">Nesta fase, crie um computador autônomo executando o Windows 10 Enterprise como um computador físico, uma máquina virtual ou uma máquina virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="2bd3d-200">Computador físico</span><span class="sxs-lookup"><span data-stu-id="2bd3d-200">Physical computer</span></span>

<span data-ttu-id="2bd3d-201">Obtain a personal computer and install Windows 10 Enterprise on it.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-201">Obtain a personal computer and install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="2bd3d-202">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-202">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="2bd3d-203">Máquina virtual</span><span class="sxs-lookup"><span data-stu-id="2bd3d-203">Virtual machine</span></span>

<span data-ttu-id="2bd3d-204">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-204">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="2bd3d-205">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-205">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="2bd3d-206">Máquina virtual no Azure</span><span class="sxs-lookup"><span data-stu-id="2bd3d-206">Virtual machine in Azure</span></span>

<span data-ttu-id="2bd3d-207">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-207">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise.</span></span> <span data-ttu-id="2bd3d-208">Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-208">Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image.</span></span> <span data-ttu-id="2bd3d-209">For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-209">For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bd3d-210">The following command sets use the latest version of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-210">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="2bd3d-211">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-211">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="2bd3d-212">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-212">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="2bd3d-213">If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-213">If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="2bd3d-214">Inicie um prompt do Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="2bd3d-215">Entre na sua conta do Azure usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="2bd3d-216">Para obter o nome de sua assinatura, use este comando.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="2bd3d-217">Set your Azure subscription.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-217">Set your Azure subscription.</span></span> <span data-ttu-id="2bd3d-218">Replace everything within the quotes, including the \< and > characters, with the correct name.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-218">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="2bd3d-219">Next, create a new resource group.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-219">Next, create a new resource group.</span></span> <span data-ttu-id="2bd3d-220">To determine a unique resource group name, use this command to list your existing resource groups.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-220">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="2bd3d-221">Create your new resource group with these commands.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-221">Create your new resource group with these commands.</span></span> <span data-ttu-id="2bd3d-222">Replace everything within the quotes, including the \< and > characters, with the correct names.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-222">Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="2bd3d-223">Next, you create a new virtual network and the WIN10 virtual machine with these commands.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-223">Next, you create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="2bd3d-224">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-224">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="2bd3d-225">Fase 5: adicionar o computador com Windows 10 no Azure AD</span><span class="sxs-lookup"><span data-stu-id="2bd3d-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="2bd3d-226">Depois de criar a máquina física ou virtual com Windows 10 Enterprise, entre com uma conta Administrador local.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bd3d-227">Para uma máquina virtual no Azure, conecte-se usando [estas instruções](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="2bd3d-228">Em seguida, adicione o computador com Windows 10 no locatário do Azure AD das suas assinaturas do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="2bd3d-229">Na área de trabalho do computador WIN10, clique em **Iniciar > Configurações > Contas > Acessar trabalho ou escola > Conectar**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="2bd3d-230">Na caixa de diálogo **Configurar uma conta corporativa ou de estudante**, clique em **Adicionar este dispositivo ao Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="2bd3d-231">Em **Conta corporativa ou de estudante**, digite o nome da conta do administrador global da sua assinatura do Microsoft 365 E5 e depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="2bd3d-232">Em **Digitar Senha**, digite a senha da conta de administrador global e clique em **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="2bd3d-233">Quando solicitado para garantir que esta é sua organização, clique em **Ingressar** e em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="2bd3d-234">Feche a janela de configurações.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-234">Close the settings window.</span></span>
    
<span data-ttu-id="2bd3d-235">Em seguida, instale os Aplicativos do Microsoft 365 para empresas no computador do WIN10.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-235">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="2bd3d-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="2bd3d-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="2bd3d-238">Na guia **Microsoft Office Home**, clique em **Instalar o Office**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="2bd3d-239">Quando solicitado sobre o que fazer, clique em **Executar** e em **Sim** para **Controle de Conta de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="2bd3d-240">Wait for Office to complete its installation.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-240">Wait for Office to complete its installation.</span></span> <span data-ttu-id="2bd3d-241">When you see **You're all set!**, click **Close** twice.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-241">When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="2bd3d-242">Este é o ambiente resultante.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-242">Here is your resulting environment.</span></span>

![Fase 5 do ambiente de teste do Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="2bd3d-244">Isso inclui o computador WIN10 que tem:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="2bd3d-245">Ingressou no locatário do Azure AD das suas assinaturas do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="2bd3d-246">Registrou um dispositivo do Azure AD no Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="2bd3d-247">Tenha os Aplicativos do Microsoft 365 para empresas instalados.</span><span class="sxs-lookup"><span data-stu-id="2bd3d-247">Has Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="2bd3d-248">Agora você está pronto para experimentar os recursos adicionais do [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="2bd3d-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="2bd3d-249">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2bd3d-249">Next steps</span></span>

<span data-ttu-id="2bd3d-250">Explore esses conjuntos adicionais de guias de laboratório de teste:</span><span class="sxs-lookup"><span data-stu-id="2bd3d-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="2bd3d-251">Identidade</span><span class="sxs-lookup"><span data-stu-id="2bd3d-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="2bd3d-252">Gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="2bd3d-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="2bd3d-253">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="2bd3d-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="2bd3d-254">Confira também</span><span class="sxs-lookup"><span data-stu-id="2bd3d-254">See also</span></span>

[<span data-ttu-id="2bd3d-255">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2bd3d-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2bd3d-256">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2bd3d-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2bd3d-257">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2bd3d-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
