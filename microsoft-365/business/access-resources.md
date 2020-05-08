---
title: Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Saiba como obter acesso a recursos locais, como aplicativos de linha de negócios, compartilhamento de arquivos e impressoras de um dispositivo Windows 10 associado ao Azure Active Directory.
ms.openlocfilehash: 980efbf09349cc0203ac50ae5e028c008d5694ca
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165892"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="f4dfd-103">Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="f4dfd-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="f4dfd-104">Qualquer dispositivo Windows 10 que esteja associado ao Azure Active Directory tem acesso a todos os recursos baseados na nuvem, como seus aplicativos do Microsoft 365 e pode ser protegido pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="f4dfd-105">Você também pode permitir o acesso a recursos locais, como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="f4dfd-106">Para permitir o acesso, use o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) para sincronizar seu Active Directory local com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="f4dfd-107">Para saber mais, confira [Introduction to Device Management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="f4dfd-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="f4dfd-108">As etapas também são resumidas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-108">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4dfd-109">Este procedimento só é aplicável ao OAuth e ao NTLM.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-109">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="f4dfd-110">Não há suporte para Kerberos.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-110">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="f4dfd-111">Executar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="f4dfd-111">Run Azure AD Connect</span></span>

<span data-ttu-id="f4dfd-112">Conclua as etapas a seguir para habilitar os dispositivos ingressados no Azure AD da sua organização para acessar recursos locais.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-112">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="f4dfd-113">Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, execute o assistente de sincronização de diretórios e o Azure AD Connect, conforme descrito em [Configurar a sincronização de diretórios para o Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="f4dfd-113">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="f4dfd-114">Após a conclusão da sincronização de diretório, verifique se os dispositivos Windows 10 da sua organização estão associados ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-114">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="f4dfd-115">Esta etapa é feita individualmente em cada dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-115">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="f4dfd-116">Consulte [configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-116">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="f4dfd-117">Depois que os dispositivos Windows 10 são associados ao Azure AD, cada usuário deve reinicializar seus dispositivos e entrar com suas credenciais do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-117">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="f4dfd-118">Agora, todos os dispositivos também têm acesso a recursos locais.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-118">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="f4dfd-119">Nenhuma etapa adicional é necessária para obter acesso a recursos locais para dispositivos ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-119">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="f4dfd-120">Essa funcionalidade é incorporada no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-120">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="f4dfd-121">Se você planeja fazer logon no dispositivo AADJ que não seja o método de senha, como PIN/bio-Metric via login de credencial do WHFB e, em seguida, acesse recursos locais (compartilhamentos, impressoras. etc.), sigahttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="f4dfd-121">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="f4dfd-122">Se sua organização não estiver pronta para implantar na configuração de dispositivo associado ao Azure AD, descrita acima, considere configurar a [configuração do dispositivo associado ao Azure ad híbrido](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="f4dfd-122">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="f4dfd-123">Considerações ao ingressar em dispositivos Windows no Azure AD</span><span class="sxs-lookup"><span data-stu-id="f4dfd-123">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="f4dfd-124">Se o dispositivo do Windows que você ingressou no Azure no AD tiver ingressado anteriormente no domínio ou em um grupo de trabalho, considere as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="f4dfd-124">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="f4dfd-125">Quando um dispositivo do Azure AD se une, ele cria um novo usuário sem fazer referência a um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-125">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="f4dfd-126">Os perfis devem ser migrados manualmente.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-126">Profiles must be manually migrated.</span></span> <span data-ttu-id="f4dfd-127">Um perfil de usuário contém informações como favoritos, arquivos locais, configurações do navegador e configurações do menu iniciar.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-127">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="f4dfd-128">Uma melhor abordagem é localizar uma ferramenta de terceiros para mapear arquivos e configurações existentes para o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-128">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="f4dfd-129">Se o dispositivo estiver usando objetos de política de grupo (GPO), alguns GPOs podem não ter um [provedor de serviços de configuração](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) comparável (CSP) no Intune.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-129">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="f4dfd-130">Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para localizar CSPs comparáveis para GPOs existentes.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-130">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="f4dfd-131">Os usuários não conseguirão se autenticar nos aplicativos que dependem da autenticação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-131">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="f4dfd-132">Avalie o aplicativo herdado e considere a atualização para um aplicativo que usa autenticação moderna, se possível.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-132">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="f4dfd-133">A descoberta de impressora do Active Directory não funcionará.</span><span class="sxs-lookup"><span data-stu-id="f4dfd-133">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="f4dfd-134">Você pode fornecer caminhos de impressora direta para todos os usuários ou usar a [impressão de nuvem híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="f4dfd-134">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
