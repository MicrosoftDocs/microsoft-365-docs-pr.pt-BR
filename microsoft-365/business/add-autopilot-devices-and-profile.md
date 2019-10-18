---
title: Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Saiba como usar o Windows AutoPilot para configurar novos dispositivos Windows 10 para sua empresa.
ms.openlocfilehash: d028ea3e902965d55c445dc3b3a02aa315201b25
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574779"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="f685c-103">Use o guia passo a passo para adicionar perfil e dispositivos do Autopilot</span><span class="sxs-lookup"><span data-stu-id="f685c-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="f685c-104">Você pode usar o Windows AutoPilot para configurar **novos** dispositivos Windows 10 para sua empresa, de modo que eles estejam prontos para uso produtivo assim que você os fornecer aos seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="f685c-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="f685c-105">Requisitos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f685c-105">Device requirements</span></span>

<span data-ttu-id="f685c-106">Os dispositivos precisam atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="f685c-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="f685c-107">Windows 10, versão 1703 ou posteriores.</span><span class="sxs-lookup"><span data-stu-id="f685c-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="f685c-108">Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="f685c-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="f685c-109">Usar o guia de configuração para criar perfis e dispositivos</span><span class="sxs-lookup"><span data-stu-id="f685c-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="f685c-110">[![Rótulo para permitir que o centro de administração esteja mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="f685c-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="f685c-111">Se você ainda não tiver perfis ou grupos de dispositivos criados, a melhor maneira de começar é usando o guia passo a passo, mas também pode [adicionar dispositivos](create-and-edit-autopilot-devices.md) e [atribuir perfis](create-and-edit-autopilot-profiles.md) a eles sem usar o guia.</span><span class="sxs-lookup"><span data-stu-id="f685c-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="f685c-112">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f685c-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="f685c-113">Na navegação à esquerda, escolha o **piloto automático**de **dispositivos** \> .</span><span class="sxs-lookup"><span data-stu-id="f685c-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![No centro de administração, escolha dispositivos e, em seguida, piloto automático.](media/AutoPilot.png)
  
2. <span data-ttu-id="f685c-115">Na página **AutoPilot** , clique ou toque em **iniciar guia**.</span><span class="sxs-lookup"><span data-stu-id="f685c-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="f685c-p101">Na página **Carregar arquivo .csv com a lista de dispositivos**, navegue até um local onde está o arquivo .CSV preparado. Em seguida, **Abrir** \> **Avançar**. O arquivo deve ter três cabeçalhos:</span><span class="sxs-lookup"><span data-stu-id="f685c-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="f685c-119">Coluna A: Número de série do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f685c-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="f685c-120">Coluna B: ID do produto Windows</span><span class="sxs-lookup"><span data-stu-id="f685c-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="f685c-121">Coluna C: Hash de hardware</span><span class="sxs-lookup"><span data-stu-id="f685c-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="f685c-122">Você encontra essas informações com seu fornecedor de hardware ou pode usar o [script Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) que gerará um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f685c-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="f685c-p102">Para saber mais, confira o [Arquivo CSV da lista de dispositivos](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Você também pode baixar um exemplo de arquivo na página **Carregar arquivo .csv com uma lista de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f685c-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="f685c-p103">Na página **Atribuir um perfil**, você pode escolher perfil existente ou criar um novo. Se você ainda não tiver um, será solicitado a criar um novo.</span><span class="sxs-lookup"><span data-stu-id="f685c-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="f685c-127">Um perfil é um conjunto de configurações que podem ser aplicadas a um único dispositivo ou a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f685c-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="f685c-p104">Os recursos padrão são necessários e serão definidos automaticamente. Os recursos padrão são:</span><span class="sxs-lookup"><span data-stu-id="f685c-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="f685c-130">São ignorados os registros Cortana, OneDrive e OEM.</span><span class="sxs-lookup"><span data-stu-id="f685c-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="f685c-131">Crie uma experiência de entrada com a marca da sua empresa</span><span class="sxs-lookup"><span data-stu-id="f685c-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="f685c-132">Seus dispositivos serão conectados às contas do Azure Active Directory e inscritos automaticamente para serem gerenciados pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f685c-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="f685c-133">Para saber mais, confira</span><span class="sxs-lookup"><span data-stu-id="f685c-133">For more information, see</span></span>
    
    <span data-ttu-id="f685c-134">[Sobre as configurações de perfil do AutoPilot](autopilot-profile-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="f685c-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="f685c-135">As outras configurações são **Ignorar as configurações de privacidade** e **Não permitir que o usuário se torne o administrador local**. Por padrão, essas configuração são definidas como **Desativado**.</span><span class="sxs-lookup"><span data-stu-id="f685c-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="f685c-136">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f685c-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="f685c-p105">A página **Pronto** indica que o perfil criado (ou escolhido) será aplicado ao grupo de dispositivos que você criou ao carregar a lista de dispositivos. Essas configurações entrarão em vigor quando os usuários do dispositivo fizerem logon na próxima vez. Escolha **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f685c-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    