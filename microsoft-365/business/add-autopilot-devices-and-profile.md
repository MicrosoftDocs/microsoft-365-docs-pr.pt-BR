---
title: Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Saiba como usar o Windows AutoPilot para configurar novos dispositivos Windows 10 para sua empresa para que eles estão prontos para uso do funcionário.
ms.openlocfilehash: f263cc90656ae5e7be1a89e3c7f56bfb2d0e3651
ms.sourcegitcommit: 3b369a44b71540c8b8214ce588a7aa6f47c3bb1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099741"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="73ead-103">Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot</span><span class="sxs-lookup"><span data-stu-id="73ead-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="73ead-104">Você pode usar o Windows AutoPilot para configurar novos dispositivos **Windows** 10 para sua empresa para que eles ficam prontos para uso quando você os entrega aos funcionários.</span><span class="sxs-lookup"><span data-stu-id="73ead-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="73ead-105">Requisitos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="73ead-105">Device requirements</span></span>

<span data-ttu-id="73ead-106">Os dispositivos devem atender a estes requisitos:</span><span class="sxs-lookup"><span data-stu-id="73ead-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="73ead-107">Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="73ead-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="73ead-108">Novos dispositivos que não passaram pela configuração de configuração do Windows</span><span class="sxs-lookup"><span data-stu-id="73ead-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="73ead-109">Usar o guia de configuração para criar perfis e dispositivos</span><span class="sxs-lookup"><span data-stu-id="73ead-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="73ead-110">[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="73ead-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="73ead-111">Se você ainda não criou grupos de dispositivos ou perfis, a melhor maneira de começar é usando o guia passo a passo.</span><span class="sxs-lookup"><span data-stu-id="73ead-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="73ead-112">Você também pode [adicionar dispositivos](create-and-edit-autopilot-devices.md) [e atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia.</span><span class="sxs-lookup"><span data-stu-id="73ead-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="73ead-113">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="73ead-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="73ead-114">No painel de navegação esquerdo, escolha **Dispositivos** \> **AutoPilot.**</span><span class="sxs-lookup"><span data-stu-id="73ead-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![No centro de administração, escolha os dispositivos e o AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="73ead-116">Na página **AutoPilot,** clique ou toque no **guia Iniciar.**</span><span class="sxs-lookup"><span data-stu-id="73ead-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="73ead-118">No arquivo **Upload .csv com a lista** de dispositivos, navegue até um local onde você preparou. Arquivo CSV **e,** em seguida, Abrir \> **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="73ead-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="73ead-119">O arquivo deve ter três headers:</span><span class="sxs-lookup"><span data-stu-id="73ead-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="73ead-120">Coluna A: Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="73ead-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="73ead-121">Coluna B: ID do produto Windows</span><span class="sxs-lookup"><span data-stu-id="73ead-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="73ead-122">Coluna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="73ead-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="73ead-123">Você pode obter essas informações do fornecedor de hardware ou usar o [script Get-WindowsAutoPilotInfo powerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) para gerar um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="73ead-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="73ead-p103">Para saber mais, confira o [Arquivo CSV da lista de dispositivos](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="73ead-p103">For more information, see [Device list CSV-file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="73ead-126">Esse script usa WMI para recuperar as propriedades necessárias para que um cliente registre um dispositivo com o Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="73ead-126">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="73ead-127">Observe que é normal que o arquivo CSV resultante não colete um valor de ID de Produto (PKID) do Windows, pois isso não é necessário para registrar um dispositivo e o PKID sendo NULL no CSV de saída é totalmente bom.</span><span class="sxs-lookup"><span data-stu-id="73ead-127">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="73ead-128">Somente o número de série e o hash de hardware serão preenchidos.</span><span class="sxs-lookup"><span data-stu-id="73ead-128">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="73ead-129">Na página **Atribuir um perfil,** você pode escolher um perfil existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="73ead-129">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="73ead-130">Se você ainda não tiver um, será solicitado a criar um.</span><span class="sxs-lookup"><span data-stu-id="73ead-130">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="73ead-131">Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73ead-131">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="73ead-132">Os recursos padrão são necessários e são definidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="73ead-132">The default features are required and are set automatically.</span></span> <span data-ttu-id="73ead-133">Os recursos padrão são:</span><span class="sxs-lookup"><span data-stu-id="73ead-133">The default features are:</span></span>
    
    - <span data-ttu-id="73ead-134">Ignore o registro da Cortana, do OneDrive e do OEM.</span><span class="sxs-lookup"><span data-stu-id="73ead-134">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="73ead-135">Crie uma experiência de entrada com a marca da sua empresa</span><span class="sxs-lookup"><span data-stu-id="73ead-135">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="73ead-136">Conecte seus dispositivos às contas do Azure Active Directory e inscreva-os automaticamente para serem gerenciados pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="73ead-136">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="73ead-137">Para obter mais informações, consulte Sobre as configurações do [Perfil do AutoPilot.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="73ead-137">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="73ead-138">As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="73ead-138">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="73ead-139">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="73ead-139">Choose **Next**.</span></span>
    
6. <span data-ttu-id="73ead-140">**Você terminou indica que** o perfil que você criou (ou escolheu) será aplicado ao grupo de dispositivos que você criou carregando a lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73ead-140">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="73ead-141">As configurações entrarão em vigor quando os usuários do dispositivo entrarem em seguida.</span><span class="sxs-lookup"><span data-stu-id="73ead-141">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="73ead-142">Escolha **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="73ead-142">Choose **Close**.</span></span>
    
