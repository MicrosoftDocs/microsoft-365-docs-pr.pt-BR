---
title: Habilitar dispositivos Windows 10 associados a um domínio para serem gerenciados pelo Microsoft 365 for Business
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Saiba como habilitar o Microsoft 365 para proteger dispositivos do Windows 10 locais associados ao Active Directory em apenas algumas etapas.
ms.openlocfilehash: 431c1be74723e156befb13ffe1ed98b48b9a23cb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633274"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a><span data-ttu-id="b3736-103">Habilitar dispositivos Windows 10 associados a um domínio para serem gerenciados pelo Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="b3736-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for business</span></span>

<span data-ttu-id="b3736-104">Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 for Business para proteger seus dispositivos Windows 10, enquanto mantém o acesso a recursos locais que exigem autenticação local.</span><span class="sxs-lookup"><span data-stu-id="b3736-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 for business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="b3736-105">Para configurar essa proteção, é possível implementar **dispositivos híbridos associados ao AD do Azure**.</span><span class="sxs-lookup"><span data-stu-id="b3736-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="b3736-106">Esses dispositivos fazem parte de seu Active Directory local e do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b3736-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="b3736-107">Este vídeo descreve as etapas para configurar isso para o cenário mais comum, que também é detalhado nas etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="b3736-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="b3736-108">1. preparar para a sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="b3736-108">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="b3736-109">Antes de sincronizar os usuários e computadores do domínio do Active Directory local, examine [preparar a sincronização de diretório para o Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="b3736-109">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="b3736-110">Em particular:</span><span class="sxs-lookup"><span data-stu-id="b3736-110">In particular:</span></span>

   - <span data-ttu-id="b3736-111">Verifique se não há duplicatas no diretório para os seguintes atributos: **mail**, **proxyAddresses**e **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="b3736-111">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="b3736-112">Esses valores devem ser exclusivos e qualquer duplicatas deve ser removida.</span><span class="sxs-lookup"><span data-stu-id="b3736-112">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="b3736-113">Recomendamos que você configure o atributo **userPrincipalName** (UPN) para cada conta de usuário local para corresponder ao endereço de email principal que corresponde ao usuário licenciado 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b3736-113">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="b3736-114">Por exemplo: *Mary.Shelley@contoso.com* em vez de *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="b3736-114">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="b3736-115">Se o domínio do Active Directory terminar em um sufixo não roteável, como. *local* ou *. LAN*, em vez de um sufixo roteável na Internet, como *. com* ou *. org*, ajuste o sufixo UPN das contas de usuário local primeiro, conforme descrito em [preparar um domínio não roteável para a sincronização de diretórios](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="b3736-115">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="b3736-116">2. instalar e configurar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="b3736-116">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="b3736-117">Para sincronizar os usuários, grupos e contatos do Active Directory local para o Active Directory do Azure, instale o Azure Active Directory Connect e configure a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="b3736-117">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> <span data-ttu-id="b3736-118">Confira [Configurar a sincronização de diretórios para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b3736-118">See [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="b3736-119">As etapas são exatamente as mesmas para o Microsoft 365 for Business.</span><span class="sxs-lookup"><span data-stu-id="b3736-119">The steps are exactly the same for Microsoft 365 for business.</span></span> 

<span data-ttu-id="b3736-120">Ao configurar suas opções para o Azure AD Connect, recomendamos que você habilite a **sincronização de senha**, o **logon único contínuo**e o recurso **write-back de senha** , que também é suportado no Microsoft 365 for Business.</span><span class="sxs-lookup"><span data-stu-id="b3736-120">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="b3736-121">Há algumas etapas adicionais para o Write-back de senha além da caixa de seleção no Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b3736-121">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="b3736-122">Para obter mais informações, consulte [como fazer: configurar o Write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="b3736-122">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

## <a name="3-configure-hybrid-azure-ad-join"></a><span data-ttu-id="b3736-123">3. configurar a União híbrida do Azure AD</span><span class="sxs-lookup"><span data-stu-id="b3736-123">3. Configure Hybrid Azure AD Join</span></span>

<span data-ttu-id="b3736-124">Antes de habilitar os dispositivos Windows 10 para que o Azure AD híbrido seja associado, verifique se você atende aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="b3736-124">Before you enable Windows 10 devices to be Hybrid Azure AD joined, make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="b3736-125">Você está executando a versão mais recente do Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="b3736-125">You're running the latest version of Azure AD Connect.</span></span>

   - <span data-ttu-id="b3736-126">O Azure AD Connect sincronizou todos os objetos de computador dos dispositivos que você deseja que sejam associados ao Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="b3736-126">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="b3736-127">Se os objetos de computador pertencem a unidades organizacionais (OU) específicas, verifique se essas UOs estão definidas para sincronização no Azure AD Connect também.</span><span class="sxs-lookup"><span data-stu-id="b3736-127">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>

<span data-ttu-id="b3736-128">Para registrar dispositivos do Windows 10 associados a um domínio existente como ingressado no Azure AD, siga as etapas no [tutorial: configurar o Azure Active Directory híbrido ingressar em domínios gerenciados](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span><span class="sxs-lookup"><span data-stu-id="b3736-128">To register existing domain-joined Windows 10 devices as Hybrid Azure AD joined, follow the steps in the [Tutorial: Configure hybrid Azure Active Directory join for managed domains](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="b3736-129">Este híbrido permite que seu Active Directory local existente ingresse em computadores Windows 10 e torne-o pronto para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="b3736-129">This hybrid-enables your existing on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a><span data-ttu-id="b3736-130">4. habilitar o registro automático para o Windows 10</span><span class="sxs-lookup"><span data-stu-id="b3736-130">4. Enable automatic enrollment for Windows 10</span></span>

 <span data-ttu-id="b3736-131">Para registrar automaticamente dispositivos Windows 10 para gerenciamento de dispositivos móveis no Intune, confira [registrar um dispositivo Windows 10 automaticamente usando a política de grupo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span><span class="sxs-lookup"><span data-stu-id="b3736-131">To automatically enroll Windows 10 devices for mobile device management in Intune, see [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy).</span></span> <span data-ttu-id="b3736-132">Você pode definir a política de grupo em um nível de computador local ou para operações em massa, você pode usar o console de gerenciamento de política de grupo e os modelos ADMX para criar essa configuração de política de grupo no seu controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="b3736-132">You can set the Group Policy at a local computer level, or for bulk operations, you can use the Group Policy Management Console and ADMX templates to create this Group Policy setting on your Domain Controller.</span></span>

## <a name="5-configure-seamless-single-sign-on"></a><span data-ttu-id="b3736-133">5. configurar o logon único contínuo</span><span class="sxs-lookup"><span data-stu-id="b3736-133">5. Configure Seamless Single Sign-On</span></span>

  <span data-ttu-id="b3736-134">O SSO direto assina automaticamente os usuários em seus recursos de nuvem do Microsoft 365 quando eles usam computadores corporativos.</span><span class="sxs-lookup"><span data-stu-id="b3736-134">Seamless SSO automatically signs users into their Microsoft 365 cloud resources when they use corporate computers.</span></span> <span data-ttu-id="b3736-135">Basta implantar uma das duas opções de política de grupo descritas no [logon único contínuo do Azure Active Directory: início rápido](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span><span class="sxs-lookup"><span data-stu-id="b3736-135">Simply deploy one of the two Group Policy options described in [Azure Active Directory Seamless Single Sign-On: Quick start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature).</span></span> <span data-ttu-id="b3736-136">A opção de **política de grupo** não permite que os usuários alterem suas configurações, enquanto a opção de **preferência política de grupo** define os valores, mas também os deixa configuráveis pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b3736-136">The **Group Policy** option doesn't allow users to change their settings, while the **Group Policy Preference** option sets the values but also leaves them user-configurable.</span></span>

## <a name="6-set-up-windows-hello-for-business"></a><span data-ttu-id="b3736-137">6. configurar o Windows Hello para empresas</span><span class="sxs-lookup"><span data-stu-id="b3736-137">6. Set up Windows Hello for Business</span></span>

 <span data-ttu-id="b3736-138">O Windows Hello para empresas substitui senhas com autenticação de dois fatores (2FA) para entrar em um computador local.</span><span class="sxs-lookup"><span data-stu-id="b3736-138">Windows Hello for Business replaces passwords with strong two-factor authentication (2FA) for signing into a local computer.</span></span> <span data-ttu-id="b3736-139">Um fator é um par de chaves assimétricas e o outro é um PIN ou outro gesto local, como impressão digital ou reconhecimento facial se o seu dispositivo suportar.</span><span class="sxs-lookup"><span data-stu-id="b3736-139">One factor is an asymmetric key pair, and the other is a PIN or other local gesture such as fingerprint or facial recognition if your device supports it.</span></span> <span data-ttu-id="b3736-140">É recomendável substituir senhas com o 2FA e o Windows Hello para empresas, onde for possível.</span><span class="sxs-lookup"><span data-stu-id="b3736-140">We recommend that you replace passwords with 2FA and Windows Hello for Business where possible.</span></span>

<span data-ttu-id="b3736-141">Para configurar o Windows Hello para empresas híbridos, revise os [pré-requisitos de confiança da chave híbrida do Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span><span class="sxs-lookup"><span data-stu-id="b3736-141">To configure Hybrid Windows Hello for Business, review the [Hybrid Key trust Windows Hello for Business Prerequisites](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs).</span></span> <span data-ttu-id="b3736-142">Siga as instruções em [configurar as configurações de confiança de chave híbrida do Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span><span class="sxs-lookup"><span data-stu-id="b3736-142">Then follow the instructions in [Configure Hybrid Windows Hello for Business key trust settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings).</span></span> 
