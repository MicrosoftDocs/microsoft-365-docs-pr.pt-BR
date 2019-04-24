---
title: Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Saiba como obter acesso a recursos locais, como aplicativos de linha de negócios, compartilhamento de arquivos e impressoras de um dispositivo Windows 10 associado ao Azure Active Directory.
ms.openlocfilehash: 212685bc229f519152e69b09d0a745bfac7a38cd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276872"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="ff1de-103">Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="ff1de-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="ff1de-104">Qualquer dispositivo Windows 10 que seja associado ao Active Directory do Azure terá acesso a todos os recursos baseados na nuvem, como seus aplicativos do Office 365 e pode ser protegido pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="ff1de-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="ff1de-105">Para permitir o acesso a recursos locais, como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras, você deve sincronizar o Active Directory local com o Azure Active Directory usando o [Azure ad Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="ff1de-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> <span data-ttu-id="ff1de-106">ConFira [introdução ao gerenciamento de dispositivos no Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="ff1de-106">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="ff1de-107">Executar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="ff1de-107">Run Azure AD Connect</span></span>

<span data-ttu-id="ff1de-108">Conclua as etapas a seguir para habilitar os dispositivos ingressados no Azure AD da sua organização para acessar recursos locais.</span><span class="sxs-lookup"><span data-stu-id="ff1de-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="ff1de-109">Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, execute o assistente de sincronização de diretórios e o Azure AD Connect, conforme descrito em [Configurar a sincronização de diretórios para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="ff1de-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="ff1de-110">Após a conclusão da sincronização de diretório, verifique se os dispositivos Windows 10 da sua organização estão associados ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ff1de-110">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="ff1de-111">Esta etapa é feita individualmente em cada dispositivo Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ff1de-111">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="ff1de-112">Consulte [configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="ff1de-112">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="ff1de-113">Depois que os dispositivos Windows 10 são associados ao Azure AD, cada usuário deve reinicializar seus dispositivos e fazer logon com suas credenciais de negócios do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff1de-113">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="ff1de-114">Todos os dispositivos agora também terão acesso aos recursos locais.</span><span class="sxs-lookup"><span data-stu-id="ff1de-114">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="ff1de-115">Nenhuma etapa adicional é necessária para obter acesso a recursos no local para dispositivos ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ff1de-115">No additional steps are required to get access to on-premise resources for Azure AD joined devices.</span></span> <span data-ttu-id="ff1de-116">Essa é uma funcionalidade interna disponível no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ff1de-116">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="ff1de-117">Se sua organização não estiver pronta para implantar na configuração de dispositivo associado ao Azure AD, descrita acima, considere configurar a [configuração do dispositivo associado ao Azure ad híbrido](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="ff1de-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="ff1de-118">Considerações ao ingressar em seus dispositivos Windows no Azure AD</span><span class="sxs-lookup"><span data-stu-id="ff1de-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="ff1de-119">Se você for o Azure AD ingressando em um dispositivo do Windows que tenha sido ingressado no domínio ou em um grupo de trabalho, você precisará considerar as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="ff1de-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="ff1de-120">Quando um dispositivo do Azure AD se une, ele cria um novo usuário sem fazer referência a um perfil existente.</span><span class="sxs-lookup"><span data-stu-id="ff1de-120">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="ff1de-121">Para corrigir isso, os perfis precisam ser migrados manualmente.</span><span class="sxs-lookup"><span data-stu-id="ff1de-121">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="ff1de-122">Um perfil de usuário contém informações como favoritos, arquivos locais, configurações do navegador, configurações do menu Iniciar, etc. Uma melhor abordagem é localizar uma ferramenta de terceiros para mapear arquivos e configurações existentes para o novo perfil</span><span class="sxs-lookup"><span data-stu-id="ff1de-122">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="ff1de-123">Se o dispositivo estiver usando objetos de política de grupo (GPO), alguns GPOs podem não ter um [provedor de serviços de configuração](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) comparável (CSP) no Intune.</span><span class="sxs-lookup"><span data-stu-id="ff1de-123">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="ff1de-124">Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para localizar CSPs comparáveis para GPOs existentes.</span><span class="sxs-lookup"><span data-stu-id="ff1de-124">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="ff1de-125">Os usuários não poderão autenticar em aplicativos que dependem da autenticação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff1de-125">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="ff1de-126">Para lidar com essa avaliação usando um aplicativo herdado e considere a atualização para um aplicativo que usa autenticação moderna, se possível.</span><span class="sxs-lookup"><span data-stu-id="ff1de-126">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="ff1de-127">A descoberta de impressora do Active Directory não funcionará.</span><span class="sxs-lookup"><span data-stu-id="ff1de-127">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="ff1de-128">Para corrigir isso, forneça caminhos de impressora diretos para todos os usuários ou aproveite a [impressão de nuvem híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="ff1de-128">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

