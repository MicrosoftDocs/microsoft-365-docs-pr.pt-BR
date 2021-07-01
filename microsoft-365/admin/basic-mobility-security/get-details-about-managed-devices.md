---
title: Obter detalhes sobre dispositivos gerenciados de Mobilidade Básica e Segurança
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
description: Use Windows PowerShell para obter detalhes sobre dispositivos Básicos de Mobilidade e Segurança em sua organização.
ms.openlocfilehash: 2edee1b08f137d3e4f977b4d6800c1b0fc0e0473
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228166"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a><span data-ttu-id="cc097-103">Obter detalhes sobre dispositivos gerenciados de Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="cc097-103">Get details about Basic Mobility and Security managed devices</span></span>

<span data-ttu-id="cc097-104">Este artigo mostra como usar o Windows PowerShell para obter detalhes sobre os dispositivos em sua organização que você definiu para Mobilidade Básica e Segurança.</span><span class="sxs-lookup"><span data-stu-id="cc097-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Basic Mobility and Security.</span></span>

<span data-ttu-id="cc097-105">Aqui está uma análise dos detalhes do dispositivo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="cc097-105">Here's a breakdown for the device details available to you.</span></span>

|<span data-ttu-id="cc097-106">**Ver os detalhes**</span><span class="sxs-lookup"><span data-stu-id="cc097-106">**Detail**</span></span>|<span data-ttu-id="cc097-107">**O que procurar no PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cc097-107">**What to look for in PowerShell**</span></span>|
|:----------------|:------------------------------------------------------------------------------|
|<span data-ttu-id="cc097-108">O dispositivo está inscrito no Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="cc097-108">Device is enrolled in Basic Mobility and Security.</span></span> <span data-ttu-id="cc097-109">Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="cc097-109">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md)</span></span>|<span data-ttu-id="cc097-110">O valor do parâmetro *isManaged*   é:</span><span class="sxs-lookup"><span data-stu-id="cc097-110">The value of the *isManaged* parameter is:</span></span><br/><span data-ttu-id="cc097-111">**True**= dispositivo está inscrito.</span><span class="sxs-lookup"><span data-stu-id="cc097-111">**True**= device is enrolled.</span></span><br/><span data-ttu-id="cc097-112">**False**= dispositivo não está inscrito.</span><span class="sxs-lookup"><span data-stu-id="cc097-112">**False**= device is not enrolled.</span></span> |
|<span data-ttu-id="cc097-113">O dispositivo está em conformidade com as políticas de segurança do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc097-113">Device is compliant with your device security policies.</span></span> <span data-ttu-id="cc097-114">Para obter mais informações, consulte [Create device security policies](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cc097-114">For more info, see [Create device security policies](create-device-security-policies.md)</span></span>|<span data-ttu-id="cc097-115">O valor do parâmetro *isCompliant*   é:</span><span class="sxs-lookup"><span data-stu-id="cc097-115">The value of the *isCompliant* parameter is:</span></span><br/><span data-ttu-id="cc097-116">**True**   = o dispositivo está em conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="cc097-116">**True** = device is compliant with policies.</span></span><br/><span data-ttu-id="cc097-117">**False**   = o dispositivo não está em conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="cc097-117">**False** = device is not compliant with policies.</span></span>|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="Parâmetros básicos de Mobilidade e Segurança do PowerShell":::

> [!NOTE]
> <span data-ttu-id="cc097-119">Os comandos e scripts deste artigo também retornam detalhes sobre todos os dispositivos gerenciados [por Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="cc097-119">The commands and scripts in this article also return details about any devices managed by [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="cc097-120">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cc097-120">Before you begin</span></span>

<span data-ttu-id="cc097-121">Há algumas coisas que você precisa configurar para executar os comandos e scripts descritos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="cc097-121">There are a few things you need to set up to run the commands and scripts described in this article.</span></span>

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="cc097-122">Etapa 1: Baixar e instalar o módulo Azure Active Directory para Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc097-122">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="cc097-123">Para obter mais informações sobre essas etapas, [consulte Conexão Microsoft 365 com o PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="cc097-123">For more info on these steps, see [Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>

1. <span data-ttu-id="cc097-124">Vá para Microsoft Online Services Sign-In Assistente para Profissionais de [TI RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)e selecione Baixar para Microsoft Online Services   Assistente de  **Login.**</span><span class="sxs-lookup"><span data-stu-id="cc097-124">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) and select  **Download for Microsoft Online Services Sign-in Assistant**.</span></span>

2. <span data-ttu-id="cc097-125">Instale o Módulo Microsoft Azure Active Directory para Windows PowerShell seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="cc097-125">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>

    1. <span data-ttu-id="cc097-126">Abra um prompt de comando do PowerShell do nível de administrador.</span><span class="sxs-lookup"><span data-stu-id="cc097-126">Open an administrator-level PowerShell command prompt.</span></span>

    2. <span data-ttu-id="cc097-127">Execute o comando `Install-Module MSOnline`.</span><span class="sxs-lookup"><span data-stu-id="cc097-127">Run the `Install-Module MSOnline` command.</span></span>

    3. <span data-ttu-id="cc097-128">Se solicitado a instalar o provedor de NuGet, digite Y e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="cc097-128">If prompted to install the NuGet provider, type Y and press ENTER.</span></span>

    4. <span data-ttu-id="cc097-129">Se solicitado a instalar o módulo de PSGallery, digite Y e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="cc097-129">If prompted to install the module from PSGallery, type Y and press ENTER.</span></span>

    5. <span data-ttu-id="cc097-130">Após a instalação, feche a janela de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc097-130">After installation, close the PowerShell command window.</span></span>

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a><span data-ttu-id="cc097-131">Etapa 2: Conexão para sua assinatura Microsoft 365 assinatura</span><span class="sxs-lookup"><span data-stu-id="cc097-131">Step 2: Connect to your Microsoft 365 subscription</span></span>

1. <span data-ttu-id="cc097-132">No módulo Windows Azure Active Directory para Windows PowerShell, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="cc097-132">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="cc097-133">Na caixa Windows PowerShell caixa de diálogo Solicitação de Credencial, digite o nome de usuário e a senha da sua conta de administrador global Microsoft 365 e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc097-133">In the Windows PowerShell Credential Request dialog box, type the user name and password for your Microsoft 365 global admin account, and then select **OK**.</span></span>

3. <span data-ttu-id="cc097-134">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cc097-134">Run the following command.</span></span>

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="cc097-135">Etapa 3: certifique-se de que você é capaz de executar scripts do PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc097-135">Step 3: Make sure you’re able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="cc097-136">Você pode ignorar essa etapa se já estiver configurada para executar scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc097-136">You can skip this step if you’re already set up to run PowerShell scripts.</span></span>

<span data-ttu-id="cc097-137">Para executar o Get-MsolUserDeviceComplianceStatus.ps1, você precisa habilitar a execução de scripts do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc097-137">To run the Get-MsolUserDeviceComplianceStatus.ps1 script, you need to enable the running of PowerShell scripts.</span></span>

1. <span data-ttu-id="cc097-138">Na sua Windows Desktop, selecione **Iniciar** e digite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc097-138">From your Windows Desktop, select **Start**, and then type Windows PowerShell.</span></span> <span data-ttu-id="cc097-139">Clique com o botão Windows PowerShell e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="cc097-139">Right-click Windows PowerShell, and then select **Run as administrator**.</span></span>

2. <span data-ttu-id="cc097-140">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cc097-140">Run the following command.</span></span>

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. <span data-ttu-id="cc097-141">Quando solicitado, digite Y e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="cc097-141">When prompted, type Y and then press Enter.</span></span>

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="cc097-142">Execute o cmdlet Get-MsolDevice para exibir detalhes de todos os dispositivos em sua organização</span><span class="sxs-lookup"><span data-stu-id="cc097-142">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="cc097-143">Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc097-143">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="cc097-144">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="cc097-144">Run the following command.</span></span>

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

<span data-ttu-id="cc097-145">Para obter mais exemplos, consulte  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span><span class="sxs-lookup"><span data-stu-id="cc097-145">For more examples, see  [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939).</span></span>

## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="cc097-146">Executar um script para obter detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cc097-146">Run a script to get device details</span></span>

<span data-ttu-id="cc097-147">Primeiro, salve o script no computador.</span><span class="sxs-lookup"><span data-stu-id="cc097-147">First, save the script to your computer.</span></span>

1. <span data-ttu-id="cc097-148">Copie e colar o texto a seguir em Bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="cc097-148">Copy and paste the following text into Notepad.</span></span>

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. <span data-ttu-id="cc097-149">Salve-o como um arquivo Windows PowerShell script usando a extensão de arquivo .ps1; por exemplo, Get-MsolUserDeviceComplianceStatus.ps1.</span><span class="sxs-lookup"><span data-stu-id="cc097-149">Save it as a Windows PowerShell script file by using the file extension .ps1; for example, Get-MsolUserDeviceComplianceStatus.ps1.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="cc097-150">Execute o script para obter informações do dispositivo para uma única conta de usuário</span><span class="sxs-lookup"><span data-stu-id="cc097-150">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="cc097-151">Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc097-151">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="cc097-152">Vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="cc097-152">Go to the folder where you saved the script.</span></span> <span data-ttu-id="cc097-153">Por exemplo, se você o salvou em C:\PS-Scripts, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="cc097-153">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="cc097-154">Execute o seguinte comando para identificar o usuário para o qual você deseja obter detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc097-154">Run the following command to identify the user you want to get device details for.</span></span> <span data-ttu-id="cc097-155">Este exemplo obtém detalhes para bar@example.com.</span><span class="sxs-lookup"><span data-stu-id="cc097-155">This example gets details for bar@example.com.</span></span>

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. <span data-ttu-id="cc097-156">Execute o seguinte comando para iniciar o script.</span><span class="sxs-lookup"><span data-stu-id="cc097-156">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="cc097-157">As informações são exportadas para sua área de trabalho Windows como um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="cc097-157">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="cc097-158">Você pode usar parâmetros adicionais para especificar o nome de arquivo e o caminho do CSV.</span><span class="sxs-lookup"><span data-stu-id="cc097-158">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="cc097-159">Execute o script para obter informações do dispositivo para um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="cc097-159">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="cc097-160">Abra o Módulo Microsoft Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cc097-160">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>

2. <span data-ttu-id="cc097-161">Vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="cc097-161">Go to the folder where you saved the script.</span></span> <span data-ttu-id="cc097-162">Por exemplo, se você o salvou em C:\PS-Scripts, execute o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="cc097-162">For example, if you saved it to C:\PS-Scripts, run the following command.</span></span>

   ```powershell
   cd C:\PS-Scripts
   ```

3. <span data-ttu-id="cc097-163">Execute o seguinte comando para identificar o grupo para o qual você deseja obter detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="cc097-163">Run the following command to identify the group you want to get device details for.</span></span> <span data-ttu-id="cc097-164">Este exemplo obtém detalhes para os usuários no grupo FinanceStaff.</span><span class="sxs-lookup"><span data-stu-id="cc097-164">This example gets details for users in the FinanceStaff group.</span></span>

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. <span data-ttu-id="cc097-165">Execute o seguinte comando para iniciar o script.</span><span class="sxs-lookup"><span data-stu-id="cc097-165">Run the following command to initiate the script.</span></span>

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

<span data-ttu-id="cc097-166">As informações são exportadas para sua área de trabalho Windows como um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="cc097-166">The information is exported to your Windows Desktop as a CSV file.</span></span> <span data-ttu-id="cc097-167">Você pode usar parâmetros adicionais para especificar o nome de arquivo e o caminho do CSV.</span><span class="sxs-lookup"><span data-stu-id="cc097-167">You can use additional parameters to specify the file name and path of the CSV.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc097-168">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cc097-168">Related topics</span></span>

[<span data-ttu-id="cc097-169">O Microsoft Conexão foi retirado</span><span class="sxs-lookup"><span data-stu-id="cc097-169">Microsoft Connect Has Been Retired</span></span>](/collaborate/connect-redirect)

[<span data-ttu-id="cc097-170">Visão geral da Mobilidade e Segurança Básicas</span><span class="sxs-lookup"><span data-stu-id="cc097-170">Overview of Basic Mobility and Security</span></span>](overview.md)

[<span data-ttu-id="cc097-171">Get-MsolDevice</span><span class="sxs-lookup"><span data-stu-id="cc097-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=2157939)
