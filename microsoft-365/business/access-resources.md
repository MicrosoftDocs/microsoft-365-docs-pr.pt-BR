---
title: Acessar recursos locais de um dispositivo ingressado no Azure AD no Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Saiba como obter acesso a recursos locais, como aplicativos de linha de negócios, compartilhamentos de arquivos e impressoras de um dispositivo do Azure Active Directory ingressado no Windows 10.
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913513"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="b2d4f-103">Acessar recursos locais de um dispositivo ingressado no Azure AD no Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b2d4f-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="b2d4f-104">Este artigo se aplica ao Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="b2d4f-105">Qualquer dispositivo Windows 10 ingressado no Azure Active Directory tem acesso a todos os recursos baseados em nuvem, como seus aplicativos do Microsoft 365, e pode ser protegido pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="b2d4f-106">Você também pode permitir o acesso a recursos locais, como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="b2d4f-107">Para permitir o acesso, use [o Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) para sincronizar seu Active Directory local com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="b2d4f-108">Para saber mais, confira [Introdução ao gerenciamento de dispositivos no Azure Active Directory](/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="b2d4f-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="b2d4f-109">As etapas também são resumidas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="b2d4f-110">Executar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="b2d4f-110">Run Azure AD Connect</span></span>

<span data-ttu-id="b2d4f-111">Conclua as etapas a seguir para habilitar os dispositivos ingressados no Azure AD da sua organização para acessar recursos locais.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="b2d4f-112">Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, execute o assistente de sincronização de diretórios e o Azure AD Connect, conforme descrito em Configurar a sincronização de diretórios para [o Office 365](../enterprise/set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="b2d4f-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>
    
2. <span data-ttu-id="b2d4f-113">Depois que a sincronização de diretórios for concluída, certifique-se de que os dispositivos Windows 10 da sua organização estejam ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="b2d4f-114">Esta etapa é feita individualmente em cada dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="b2d4f-115">Consulte [Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="b2d4f-116">Depois que os dispositivos Windows 10 ingressarem no Azure AD, cada usuário deverá reiniciar seus dispositivos e entrar com suas credenciais do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="b2d4f-117">Todos os dispositivos agora têm acesso a recursos locais também.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="b2d4f-118">Nenhuma etapa adicional é necessária para obter acesso a recursos locais para dispositivos ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="b2d4f-119">Essa funcionalidade é criada no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="b2d4f-120">Se você tiver planos de fazer logon no dispositivo AADJ que não seja o método de senha Como PIN/Biométrica por meio do logon de credencial WHFB e, em seguida, acessar recursos locais (compartilhamentos,impressoras.. etc), siga https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="b2d4f-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="b2d4f-121">Se sua organização não estiver pronta para implantar na configuração de dispositivo ingressada no Azure AD descrita acima, considere configurar a configuração de dispositivo ingressada no [Azure AD híbrido.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="b2d4f-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="b2d4f-122">Considerações ao ingressar dispositivos Windows no Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2d4f-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="b2d4f-123">Se o dispositivo Windows que você ingressou no Azure-AD foi ingressado anteriormente no domínio ou em um grupo de trabalho, considere as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="b2d4f-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="b2d4f-124">Quando um dispositivo do Azure AD entra, ele cria um novo usuário sem fazer referência a um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="b2d4f-125">Os perfis devem ser migrados manualmente.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="b2d4f-126">Um perfil de usuário contém informações como favoritos, arquivos locais, configurações do navegador e configurações de menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="b2d4f-127">Uma melhor abordagem é encontrar uma ferramenta de terceiros para mapear arquivos e configurações existentes para o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="b2d4f-128">Se o dispositivo estiver usando Objetos de Política de Grupo (GPO), alguns GPOs podem não ter um CSP [(Provedor](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) de Serviços de Configuração) comparável no Intune.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="b2d4f-129">Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para encontrar CSPs comparáveis para GPOs existentes.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="b2d4f-130">Os usuários podem não ser capazes de se autenticar em aplicativos que dependem da autenticação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="b2d4f-131">Avalie o aplicativo herdado e considere atualizar para um aplicativo que usa a Auth moderna, se possível.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="b2d4f-132">A descoberta da impressora do Active Directory não funcionará.</span><span class="sxs-lookup"><span data-stu-id="b2d4f-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="b2d4f-133">Você pode fornecer caminhos de impressora diretos para todos os usuários ou usar [Impressão Universal](/universal-print/).</span><span class="sxs-lookup"><span data-stu-id="b2d4f-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>