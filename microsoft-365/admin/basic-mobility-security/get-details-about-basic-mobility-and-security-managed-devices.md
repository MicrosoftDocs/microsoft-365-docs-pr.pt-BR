---
title: Obter detalhes sobre dispositivos de mobilidade e gerenciamento de segurança básicos
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Use o Windows PowerShell para obter detalhes sobre dispositivos de segurança e mobilidade básicos em sua organização.
ms.openlocfilehash: 7b041e54d512291163616d3b61973cef989cec5c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336699"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="c1927-103">Obter detalhes sobre dispositivos de mobilidade e gerenciamento de segurança básicos</span><span class="sxs-lookup"><span data-stu-id="c1927-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="c1927-104">Este artigo mostra como usar o Windows PowerShell para obter detalhes sobre os dispositivos em sua organização que você configurou para mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="c1927-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="c1927-105">Aqui está uma divisão dos detalhes do dispositivo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="c1927-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="c1927-106">**Ver os detalhes**</span><span class="sxs-lookup"><span data-stu-id="c1927-106">**Detail**</span></span>|<span data-ttu-id="c1927-107">**O que procurar no PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c1927-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="c1927-108">O dispositivo está inscrito em mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="c1927-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="c1927-109">Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span><span class="sxs-lookup"><span data-stu-id="c1927-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md)</span></span>|<span data-ttu-id="c1927-110">O valor do parâmetro *IsManaged*   é:</span><span class="sxs-lookup"><span data-stu-id="c1927-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="c1927-111">**True**= o dispositivo está inscrito.</span><span class="sxs-lookup"><span data-stu-id="c1927-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="c1927-112">**False**= o dispositivo não está inscrito.</span><span class="sxs-lookup"><span data-stu-id="c1927-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="c1927-113">O dispositivo é compatível com suas políticas de segurança de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1927-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="c1927-114">Para saber mais, confira [criar políticas de segurança de dispositivo](create-device-security-policies-in-basic-mmobility-and-security.md)</span><span class="sxs-lookup"><span data-stu-id="c1927-114">For more info, see [Create device security policies](create-device-security-policies-in-basic-mmobility-and-security.md)</span></span>|<span data-ttu-id="c1927-115">O valor do parâmetro *IsCompliant*   é:</span><span class="sxs-lookup"><span data-stu-id="c1927-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="c1927-116">**True**   = o dispositivo é compatível com políticas.</span><span class="sxs-lookup"><span data-stu-id="c1927-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="c1927-117">**False**   = o dispositivo não é compatível com políticas.</span><span class="sxs-lookup"><span data-stu-id="c1927-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parâmetros básicos de mobilidade e segurança do PowerShell":::

>[!NOTE]
><span data-ttu-id="c1927-119">Os comandos e scripts neste artigo também retornam detalhes sobre qualquer dispositivo gerenciado pelo [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="c1927-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c1927-120">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c1927-120">Before you begin</span></span>

<span data-ttu-id="c1927-121">Há algumas coisas que você precisa configurar para executar os comandos e scripts descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c1927-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c1927-122">Etapa 1: baixar e instalar o módulo Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1927-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="c1927-123">Para obter mais informações sobre essas etapas, consulte [conectar-se ao Microsoft 365 com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c1927-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="c1927-124">Vá para [Assistente de conexão do Microsoft Online Services para profissionais de ti RTWl](https://www.microsoft.com/download/details.aspx?id=41950)   e selecione  **download para assistente de conexão do Microsoft Online Services**.</span><span class="sxs-lookup"><span data-stu-id="c1927-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/download/details.aspx?id=41950) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>   

2. <span data-ttu-id="c1927-125">Instale o Módulo Microsoft Azure Active Directory para Windows PowerShell seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c1927-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>   

    1. <span data-ttu-id="c1927-126">Abra um prompt de comando do PowerShell do nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="c1927-126">Open an administrator-level PowerShell command prompt.</span></span>  

    2. <span data-ttu-id="c1927-127">Execute o comando Install-Module MSOnline.</span><span class="sxs-lookup"><span data-stu-id="c1927-127">Run the Install-Module MSOnline command.</span></span>
    
    3. <span data-ttu-id="c1927-128">Se solicitado a instalar o provedor de NuGet, digite Y e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="c1927-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>   

    4. <span data-ttu-id="c1927-129">Se solicitado a instalar o módulo de PSGallery, digite Y e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="c1927-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>   

    5. <span data-ttu-id="c1927-130">Após a instalação, feche a janela de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1927-130">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="c1927-131">Etapa 2: conectar-se à sua assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1927-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="c1927-132">No módulo do Windows Azure Active Directory para Windows PowerShell, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c1927-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>  

    <span data-ttu-id="c1927-133">$UserCredential = Get-Credential</span><span class="sxs-lookup"><span data-stu-id="c1927-133">$UserCredential = Get-Credential</span></span>

2. <span data-ttu-id="c1927-134">Na caixa de diálogo solicitação de credencial do Windows PowerShell, digite o nome de usuário e a senha da sua conta de administrador global do Microsoft 365 e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1927-134">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>
    
3. <span data-ttu-id="c1927-135">Execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c1927-135">Run the following command.</span></span>
    
    <span data-ttu-id="c1927-136">Connect-MsolService-Credential $UserCredential</span><span class="sxs-lookup"><span data-stu-id="c1927-136">Connect-MsolService -Credential $UserCredential</span></span>

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="c1927-137">Etapa 3: Verifique se é possível executar scripts do PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1927-137">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

>[!NOTE]
><span data-ttu-id="c1927-138">Você pode ignorar esta etapa se já estiver configurado para executar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1927-138">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="c1927-139">Para executar o script Get-MsolUserDeviceComplianceStatus.ps1, você precisa habilitar a execução de scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1927-139">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="c1927-140">Na área de trabalho do Windows, selecione **Iniciar**e digite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1927-140">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="c1927-141">Clique com o botão direito do mouse em Windows PowerShell e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="c1927-141">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="c1927-142">Execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c1927-142">Run the following command.</span></span>
    
    <span data-ttu-id="c1927-143">Set-ExecutionPolicy RemoteSigned</span><span class="sxs-lookup"><span data-stu-id="c1927-143">Set-ExecutionPolicy  RemoteSigned</span></span>

3. <span data-ttu-id="c1927-144">Quando solicitado, digite s e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="c1927-144">When prompted, type Y and then press Enter.</span></span>
    
<span data-ttu-id="c1927-145">**Execute o cmdlet Get-MsolDevice para exibir detalhes de todos os dispositivos em sua organização**</span><span class="sxs-lookup"><span data-stu-id="c1927-145">**Run the Get-MsolDevice cmdlet to display details for all devices in your organization**</span></span>

1. <span data-ttu-id="c1927-146">Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1927-146">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>  

2. <span data-ttu-id="c1927-147">Execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c1927-147">Run the following command.</span></span>
    
    <span data-ttu-id="c1927-148">Get-MsolDevice-All-ReturnRegisteredOwners | Em que-Object {$ _. RegisteredOwners. Count-gt 0}</span><span class="sxs-lookup"><span data-stu-id="c1927-148">Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}</span></span>

<span data-ttu-id="c1927-149">Para obter mais exemplos, consulte  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span><span class="sxs-lookup"><span data-stu-id="c1927-149">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="c1927-150">Executar um script para obter detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="c1927-150">Run a script to get device details</span></span>

<span data-ttu-id="c1927-151">Primeiro, salve o script no seu computador.</span><span class="sxs-lookup"><span data-stu-id="c1927-151">First, save the script to your computer.</span></span>

1. <span data-ttu-id="c1927-152">Copie e cole o texto a seguir no bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="c1927-152">Copy and paste the following text into Notepad.</span></span>  

2.  <span data-ttu-id="c1927-153">parâmetros</span><span class="sxs-lookup"><span data-stu-id="c1927-153">param (</span></span>
    

3.  <span data-ttu-id="c1927-154">[PSObject []] $users = @ (),</span><span class="sxs-lookup"><span data-stu-id="c1927-154">[PSObject[]]$users = @(),</span></span>
    

4.  <span data-ttu-id="c1927-155">[Opção] $export,</span><span class="sxs-lookup"><span data-stu-id="c1927-155">[Switch]$export,</span></span>
    

5.  <span data-ttu-id="c1927-156">[Cadeia de caracteres] $exportFileName = "UserDeviceComplianceStatus_" + (Get-Date-Format "yyMMdd_HHMMss") + ". csv",</span><span class="sxs-lookup"><span data-stu-id="c1927-156">[String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",</span></span>
    

6.  <span data-ttu-id="c1927-157">[Cadeia de caracteres] $exportPath = [ambiente]:: GetFolderPath ("área de trabalho")</span><span class="sxs-lookup"><span data-stu-id="c1927-157">[String]$exportPath = [Environment]::GetFolderPath("Desktop")</span></span>
    

7.  <span data-ttu-id="c1927-158">)</span><span class="sxs-lookup"><span data-stu-id="c1927-158">)</span></span>
    

9.  <span data-ttu-id="c1927-159">[System. Collections. IDictionary] $script: Schema = @ {</span><span class="sxs-lookup"><span data-stu-id="c1927-159">[System.Collections.IDictionary]$script:schema = @{</span></span>
    

11.  <span data-ttu-id="c1927-160">DeviceID = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-160">DeviceId = ''</span></span>
    

12.  <span data-ttu-id="c1927-161">DeviceOSType = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-161">DeviceOSType = ''</span></span>
    

13.  <span data-ttu-id="c1927-162">DeviceOSVersion = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-162">DeviceOSVersion = ''</span></span>
    

14.  <span data-ttu-id="c1927-163">DeviceTrustLevel = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-163">DeviceTrustLevel = ''</span></span>
    

15.  <span data-ttu-id="c1927-164">DisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-164">DisplayName = ''</span></span>
    

16.  <span data-ttu-id="c1927-165">IsCompliant = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-165">IsCompliant = ''</span></span>
    

17.  <span data-ttu-id="c1927-166">IsManaged = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-166">IsManaged = ''</span></span>
    

18.  <span data-ttu-id="c1927-167">ApproximateLastLogonTimestamp = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-167">ApproximateLastLogonTimestamp = ''</span></span>
    

19.  <span data-ttu-id="c1927-168">DeviceObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-168">DeviceObjectId = ''</span></span>
    

20.  <span data-ttu-id="c1927-169">RegisteredOwnerUpn = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-169">RegisteredOwnerUpn = ''</span></span>
    

21.  <span data-ttu-id="c1927-170">RegisteredOwnerObjectId = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-170">RegisteredOwnerObjectId = ''</span></span>
    

22.  <span data-ttu-id="c1927-171">RegisteredOwnerDisplayName = ' '</span><span class="sxs-lookup"><span data-stu-id="c1927-171">RegisteredOwnerDisplayName = ''</span></span>
    

23.  <span data-ttu-id="c1927-172">}</span><span class="sxs-lookup"><span data-stu-id="c1927-172">}</span></span>
    

25.  <span data-ttu-id="c1927-173">função createresultobject</span><span class="sxs-lookup"><span data-stu-id="c1927-173">function createResultObject</span></span>
    

26.  <span data-ttu-id="c1927-174">{</span><span class="sxs-lookup"><span data-stu-id="c1927-174">{</span></span>
    

28.  <span data-ttu-id="c1927-175">[PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: Schema</span><span class="sxs-lookup"><span data-stu-id="c1927-175">[PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema</span></span>
    

30.  <span data-ttu-id="c1927-176">retornar $resultObject</span><span class="sxs-lookup"><span data-stu-id="c1927-176">return $resultObject</span></span>
    

31.  <span data-ttu-id="c1927-177">}</span><span class="sxs-lookup"><span data-stu-id="c1927-177">}</span></span>
    

33.  <span data-ttu-id="c1927-178">If ($users. Count-eq 0)</span><span class="sxs-lookup"><span data-stu-id="c1927-178">If ($users.Count -eq 0)</span></span>
    

34.  <span data-ttu-id="c1927-179">{</span><span class="sxs-lookup"><span data-stu-id="c1927-179">{</span></span>
    

35.  <span data-ttu-id="c1927-180">$users = Get-MsolUser</span><span class="sxs-lookup"><span data-stu-id="c1927-180">$users = Get-MsolUser</span></span>
    

36.  <span data-ttu-id="c1927-181">}</span><span class="sxs-lookup"><span data-stu-id="c1927-181">}</span></span>
    

38.  <span data-ttu-id="c1927-182">[PSObject []] $result = foreach ($u em $users)</span><span class="sxs-lookup"><span data-stu-id="c1927-182">[PSObject[]]$result = foreach ($u in $users)</span></span>
    

39.  <span data-ttu-id="c1927-183">{</span><span class="sxs-lookup"><span data-stu-id="c1927-183">{</span></span>
    

41.  <span data-ttu-id="c1927-184">[PSObject] $devices = Get-msoldevice-RegisteredOwnerUpn $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="c1927-184">[PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName</span></span>
    

42.  <span data-ttu-id="c1927-185">foreach ($d em $devices)</span><span class="sxs-lookup"><span data-stu-id="c1927-185">foreach ($d in $devices)</span></span>
    

43.  <span data-ttu-id="c1927-186">{</span><span class="sxs-lookup"><span data-stu-id="c1927-186">{</span></span>
    

44.  <span data-ttu-id="c1927-187">[PSObject] $deviceResult = createresultobject</span><span class="sxs-lookup"><span data-stu-id="c1927-187">[PSObject]$deviceResult = createResultObject</span></span>
    

45.  <span data-ttu-id="c1927-188">$deviceResult. DeviceID = $d. DeviceID</span><span class="sxs-lookup"><span data-stu-id="c1927-188">$deviceResult.DeviceId = $d.DeviceId</span></span>
    

46.  <span data-ttu-id="c1927-189">$deviceResult. DeviceOSType = $d. DeviceOSType</span><span class="sxs-lookup"><span data-stu-id="c1927-189">$deviceResult.DeviceOSType = $d.DeviceOSType</span></span>
    

47.  <span data-ttu-id="c1927-190">$deviceResult. DeviceOSVersion = $d. DeviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="c1927-190">$deviceResult.DeviceOSVersion = $d.DeviceOSVersion</span></span>
    

48.  <span data-ttu-id="c1927-191">$deviceResult. DeviceTrustLevel = $d. DeviceTrustLevel</span><span class="sxs-lookup"><span data-stu-id="c1927-191">$deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel</span></span>
    

49.  <span data-ttu-id="c1927-192">$deviceResult. DisplayName = $d. DisplayName</span><span class="sxs-lookup"><span data-stu-id="c1927-192">$deviceResult.DisplayName = $d.DisplayName</span></span>
    

50.  <span data-ttu-id="c1927-193">$deviceResult. IsCompliant = $d. GraphDeviceObject. IsCompliant</span><span class="sxs-lookup"><span data-stu-id="c1927-193">$deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant</span></span>
    

51.  <span data-ttu-id="c1927-194">$deviceResult. isgerencied = $d. GraphDeviceObject. isgerencied</span><span class="sxs-lookup"><span data-stu-id="c1927-194">$deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged</span></span>
    

52.  <span data-ttu-id="c1927-195">$deviceResult. DeviceObjectId = $d. ObjectId</span><span class="sxs-lookup"><span data-stu-id="c1927-195">$deviceResult.DeviceObjectId = $d.ObjectId</span></span>
    

53.  <span data-ttu-id="c1927-196">$deviceResult. RegisteredOwnerUpn = $u. UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="c1927-196">$deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName</span></span>
    

54.  <span data-ttu-id="c1927-197">$deviceResult. RegisteredOwnerObjectId = $u. ObjectId</span><span class="sxs-lookup"><span data-stu-id="c1927-197">$deviceResult.RegisteredOwnerObjectId = $u.ObjectId</span></span>
    

55.  <span data-ttu-id="c1927-198">$deviceResult. RegisteredOwnerDisplayName = $u. DisplayName</span><span class="sxs-lookup"><span data-stu-id="c1927-198">$deviceResult.RegisteredOwnerDisplayName = $u.DisplayName</span></span>
    

56.  <span data-ttu-id="c1927-199">$deviceResult. ApproximateLastLogonTimestamp = $d. ApproximateLastLogonTimestamp</span><span class="sxs-lookup"><span data-stu-id="c1927-199">$deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp</span></span>
    

58.  <span data-ttu-id="c1927-200">$deviceResult</span><span class="sxs-lookup"><span data-stu-id="c1927-200">$deviceResult</span></span>
    

59.  <span data-ttu-id="c1927-201">}</span><span class="sxs-lookup"><span data-stu-id="c1927-201">}</span></span>
    

61.  <span data-ttu-id="c1927-202">}</span><span class="sxs-lookup"><span data-stu-id="c1927-202">}</span></span>
    

63.  <span data-ttu-id="c1927-203">If ($export)</span><span class="sxs-lookup"><span data-stu-id="c1927-203">If ($export)</span></span>
    

64.  <span data-ttu-id="c1927-204">{</span><span class="sxs-lookup"><span data-stu-id="c1927-204">{</span></span>
    

65.  <span data-ttu-id="c1927-205">$result | Export-CSV-Path ($exportPath + " \" + $exportFileName)-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="c1927-205">$result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation</span></span>
    

66.  <span data-ttu-id="c1927-206">}</span><span class="sxs-lookup"><span data-stu-id="c1927-206">}</span></span>
    

67.  <span data-ttu-id="c1927-207">Else</span><span class="sxs-lookup"><span data-stu-id="c1927-207">Else</span></span>
    

68.  <span data-ttu-id="c1927-208">{</span><span class="sxs-lookup"><span data-stu-id="c1927-208">{</span></span>
    

69.  <span data-ttu-id="c1927-209">$result</span><span class="sxs-lookup"><span data-stu-id="c1927-209">$result</span></span>
    

70.  <span data-ttu-id="c1927-210">}</span><span class="sxs-lookup"><span data-stu-id="c1927-210">}</span></span>
    

71.  <span data-ttu-id="c1927-211">Salve-o como um arquivo de script do Windows PowerShell usando a extensão de arquivo. ps1; por exemplo, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="c1927-211">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="c1927-212">Executar o script para obter informações de dispositivo para uma única conta de usuário</span><span class="sxs-lookup"><span data-stu-id="c1927-212">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="c1927-213">Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1927-213">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c1927-214">Vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="c1927-214">Go to the folder where you saved the script.</span></span> <span data-ttu-id="c1927-215">Por exemplo, se você salvou-o no C:\PS-Scripts, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c1927-215">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>
    
    <span data-ttu-id="c1927-216">CD C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="c1927-216">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="c1927-217">Execute o seguinte comando para identificar o usuário para o qual você deseja obter detalhes de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1927-217">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="c1927-218">Este exemplo obtém detalhes de bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="c1927-218">This example gets details for bar@example.com.</span></span>
    
    <span data-ttu-id="c1927-219">$u = get-MsolUser-UserPrincipalName bar@example.com</span><span class="sxs-lookup"><span data-stu-id="c1927-219">$u = Get-MsolUser -UserPrincipalName bar@example.com</span></span>

4. <span data-ttu-id="c1927-220">Execute o seguinte comando para iniciar o script.</span><span class="sxs-lookup"><span data-stu-id="c1927-220">Run the following command to initiate the script.</span></span>

    <span data-ttu-id="c1927-221">.\Get-MsolUserDeviceComplianceStatus.ps1-user $u-Export</span><span class="sxs-lookup"><span data-stu-id="c1927-221">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="c1927-222">As informações são exportadas para a área de trabalho do Windows como um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c1927-222">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="c1927-223">Você pode usar parâmetros adicionais para especificar o nome do arquivo e o caminho do CSV.</span><span class="sxs-lookup"><span data-stu-id="c1927-223">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="c1927-224">Executar o script para obter informações de dispositivo para um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="c1927-224">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="c1927-225">Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c1927-225">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="c1927-226">Vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="c1927-226">Go to the folder where you saved the script.</span></span> <span data-ttu-id="c1927-227">Por exemplo, se você salvou-o no C:\PS-Scripts, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="c1927-227">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>   

    <span data-ttu-id="c1927-228">CD C:\PS-Scripts</span><span class="sxs-lookup"><span data-stu-id="c1927-228">cd C:\PS-Scripts</span></span>

3. <span data-ttu-id="c1927-229">Execute o seguinte comando para identificar o grupo para o qual você deseja obter detalhes de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c1927-229">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="c1927-230">Este exemplo obtém detalhes para usuários no grupo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="c1927-230">This example gets details for users in the FinanceStaff group.</span></span> 

    <span data-ttu-id="c1927-231">$u = get-MsolGroupMember-searchString "FinanceStaff" | % {Get-MsolUser-ObjectId $ _. IDs</span><span class="sxs-lookup"><span data-stu-id="c1927-231">$u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }</span></span>

4. <span data-ttu-id="c1927-232">Execute o seguinte comando para iniciar o script.</span><span class="sxs-lookup"><span data-stu-id="c1927-232">Run the following command to initiate the script.</span></span>   

    <span data-ttu-id="c1927-233">.\Get-MsolUserDeviceComplianceStatus.ps1-user $u-Export</span><span class="sxs-lookup"><span data-stu-id="c1927-233">.\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export</span></span>

<span data-ttu-id="c1927-234">As informações são exportadas para a área de trabalho do Windows como um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c1927-234">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="c1927-235">Você pode usar parâmetros adicionais para especificar o nome do arquivo e o caminho do CSV.</span><span class="sxs-lookup"><span data-stu-id="c1927-235">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c1927-236">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c1927-236">Related topics</span></span>

[<span data-ttu-id="c1927-237">O Microsoft Connect foi desativado</span><span class="sxs-lookup"><span data-stu-id="c1927-237">Microsoft Connect Has Been Retired</span></span>](https://docs.microsoft.com/collaborate/connect-redirect)

[<span data-ttu-id="c1927-238">Visão geral da mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="c1927-238">Overview of Basic Mobility and Security</span></span>](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[<span data-ttu-id="c1927-239">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="c1927-239">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)