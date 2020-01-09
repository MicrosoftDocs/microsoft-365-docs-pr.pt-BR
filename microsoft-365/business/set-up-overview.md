---
title: Visão geral da configuração
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Visão geral das etapas de configuração para o Microsoft 365 Business.
ms.openlocfilehash: cab999493bf86ed0adf32521eaf6b3943f107f79
ms.sourcegitcommit: cf7b0fd80ecfb7a216111a801269c5322794795e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "40995241"
---
# <a name="overview-of-setup"></a><span data-ttu-id="5db33-103">Visão geral da configuração</span><span class="sxs-lookup"><span data-stu-id="5db33-103">Overview of setup</span></span>

<span data-ttu-id="5db33-104">Assista a um pequeno vídeo sobre a configuração do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="5db33-104">Watch a short video about Microsoft 365 Business setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="5db33-105">Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="5db33-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="5db33-106">A maioria das etapas de configuração pode ser feita no assistente de configuração, mas as outras opções também são listadas.</span><span class="sxs-lookup"><span data-stu-id="5db33-106">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="5db33-107">Etapa 1: adicionar seu domínio e seus usuários</span><span class="sxs-lookup"><span data-stu-id="5db33-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="5db33-108">**[Adicione seu domínio](set-up.md#add-your-domain-to-personalize-sign-in)** (se você comprou seu domínio durante a [inscrição](sign-up.md), esta etapa já foi feita.)</span><span class="sxs-lookup"><span data-stu-id="5db33-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="5db33-109">**Adicionar usuários**.</span><span class="sxs-lookup"><span data-stu-id="5db33-109">**Add users**.</span></span> <span data-ttu-id="5db33-110">Você pode adicionar usuários de uma das três maneiras:</span><span class="sxs-lookup"><span data-stu-id="5db33-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="5db33-111">No [Assistente](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="5db33-111">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="5db33-112">Use a sincronização de diretórios para [Adicionar usuários usando o Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) se você tiver um Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="5db33-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="5db33-113">Você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="5db33-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="5db33-114">Etapa 2: configurar políticas de segurança e configurar dispositivos</span><span class="sxs-lookup"><span data-stu-id="5db33-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="5db33-115">Use o [Assistente de configuração](set-up.md#protect-your-organization) para configurar as políticas de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5db33-115">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="5db33-116">Você também pode adicionar mais ou editá-los mais tarde no [centro de administração](view-policies-and-devices.md) e no [portal do Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="5db33-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="5db33-117">O assistente de configuração também definirá as configurações básicas de proteção contra ameaças e prevenção contra perda de dados.</span><span class="sxs-lookup"><span data-stu-id="5db33-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="5db33-118">Além das configurações de segurança no assistente de instalação, você pode aumentar a segurança adicionando as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5db33-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="5db33-119">**Proteção contra malware de email**</span><span class="sxs-lookup"><span data-stu-id="5db33-119">**Email malware protection**</span></span>
- <span data-ttu-id="5db33-120">**Anti-phishing ATP**</span><span class="sxs-lookup"><span data-stu-id="5db33-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="5db33-121">**Arquivamento do Exchange Online**</span><span class="sxs-lookup"><span data-stu-id="5db33-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="5db33-122">**Proteção de informações do Azure (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="5db33-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="5db33-123">Para começar, consulte [aumentar a proteção contra ameaças](increase-threat-protection.md) e [configurar recursos de conformidade](set-up-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="5db33-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="5db33-124">Confira também [as 10 maneiras principais de proteger o Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para um mapa de práticas recomendadas de segurança.</span><span class="sxs-lookup"><span data-stu-id="5db33-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="5db33-125">Etapa 3: configurar e gerenciar dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="5db33-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="5db33-126">Depois de executar o assistente de configuração, você desejará proctectr todos os computadores windwos 10 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5db33-126">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="5db33-127">O Windows 10 pro é um [pré-requisito](pre-requisites-for-data-protection.md) para o Microsoft 365 Business, mas se você tiver o Windows 7 Pro, Windows 8 Pro ou Windows 8,1 Pro, sua assinatura lhe contitulará uma [atualização para o Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="5db33-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="5db33-128">Siga as etapas em [proteger PCs Windows 10](secure-win-10-pcs.md) para configurar políticas para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5db33-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="5db33-129">Ao ingressar em um dispositivo Windows 10 no Azure AD, as políticas definidas para computadores com Windows 10 são aplicadas a ela.</span><span class="sxs-lookup"><span data-stu-id="5db33-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="5db33-130">Para obter mais informações, consulte [set up Windows Devices for Microsoft 365 business users](set-up-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="5db33-130">For more information, see [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="5db33-131">Etapa 4: instalar o Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="5db33-131">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="5db33-132">Você pode instalar automaticamente o Office nos dispositivos Windows usando o [Assistente de configuração](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="5db33-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="5db33-133">Permitir que os usuários [instalem aplicativos do Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5db33-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="5db33-134">Avançado</span><span class="sxs-lookup"><span data-stu-id="5db33-134">Advanced</span></span>
- <span data-ttu-id="5db33-135">**Usar o piloto automático para configurar novos dispositivos**</span><span class="sxs-lookup"><span data-stu-id="5db33-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="5db33-136">Você pode usar o [Windows AutoPilot](add-autopilot-devices-and-profile.md) para configurar automaticamente **novos** dispositivos Windows 10 para um usuário, mas pode ser mais fácil obter um [parceiro](https://www.microsoft.com/solution-providers/search) que pode fazer isso para você.</span><span class="sxs-lookup"><span data-stu-id="5db33-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="5db33-137">Você também pode ir para a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e solicitar que um especialista em tecnologia de nuvem configure novos dispositivos que você comprou.</span><span class="sxs-lookup"><span data-stu-id="5db33-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="5db33-138">**Acesse recursos locais**</span><span class="sxs-lookup"><span data-stu-id="5db33-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="5db33-139">Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local.</span><span class="sxs-lookup"><span data-stu-id="5db33-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="5db33-140">Siga as etapas em [habilitar dispositivos do Windows 10 associados ao domínio para serem gerenciados pela Microsoft 365 Business](manage-windows-devices.md) para configurar isso.</span><span class="sxs-lookup"><span data-stu-id="5db33-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="5db33-141">Este é o método preferencial, e os dispositivos nesse estado são chamados de dispositivos do Azure AD associados híbridos.</span><span class="sxs-lookup"><span data-stu-id="5db33-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="5db33-142">Se sua empresa tiver um Active Directory local que contenha alguns recursos locais (como compartilhamento de arquivos e impressoras), você poderá dar aos seus dispositivos associados ao AD do Azure acesso a esses recursos seguindo as etapas aqui: [acessar recursos locais de um dispositivo associado ao AD do Azure no Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="5db33-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5db33-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="5db33-143">See also</span></span>

[<span data-ttu-id="5db33-144">Vídeos de treinamento do Microsoft 365 Business </span><span class="sxs-lookup"><span data-stu-id="5db33-144">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
