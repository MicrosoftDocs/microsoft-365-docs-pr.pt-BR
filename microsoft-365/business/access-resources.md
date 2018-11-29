---
title: Acesso a recursos de um dispositivo associado ao AD Azure no Microsoft 365 Business local
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Saiba como obter acesso a recursos locais, como aplicativos de linha de negócios, compartilhamentos de arquivos e impressoras a partir de um Windows Azure Active Directory ingressou dispositivo Windows 10.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864706"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="d4a6c-103">Acesso a recursos de um dispositivo associado ao AD Azure no Microsoft 365 Business local</span><span class="sxs-lookup"><span data-stu-id="d4a6c-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="d4a6c-p101">Qualquer dispositivo de 10 do Windows Azure Active Directory ingressou terão acesso a todos os recursos baseados em nuvem, como seus aplicativos do Office 365 e pode ser protegido pela Microsoft 365 Business. Para permitir o acesso aos recursos locais como aplicativos de linha de negócios (LOB), compartilhamentos de arquivos e impressoras também, você deve sincronizar seu Active Directory no local com o Windows Azure Active Directory usando [Conectar do Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Consulte a [Introdução ao gerenciamento de dispositivo no Windows Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="d4a6c-107">Conecte-se de executar o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-107">Run Azure AD Connect</span></span>

<span data-ttu-id="d4a6c-108">Conclua as seguintes etapas para permitir que os dispositivos da sua organização Azure AD ingressado acessar recursos locais.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="d4a6c-109">Para sincronizar seus usuários, grupos e contatos do Active Directory local para o Windows Azure Active Directory, execute o Assistente de sincronização de diretório e o Azure AD conectar-se como descrito em [Configurar a sincronização de diretório para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="d4a6c-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="d4a6c-p102">Depois que a sincronização de diretório estiver concluída, verifique se Windows 10 dispositivos de sua organização são Azure AD ingressado. Esta etapa é realizada individualmente em cada dispositivo Windows 10. Para obter detalhes, consulte [Configurar os dispositivos do Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="d4a6c-p103">Depois que os dispositivos Windows 10 estiverem Azure AD ingressado, cada usuário deve reinicializar seus dispositivos e o logon com suas credenciais do Microsoft 365 Business. Todos os dispositivos terão acesso aos recursos de local também.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="d4a6c-p104">Não há etapas adicionais são necessárias para obter acesso a recursos do Windows Azure AD ingressou dispositivos no local. Isso é interna funcionalidade disponível no Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="d4a6c-117">Se sua organização não estiver pronta para implantar o Windows Azure AD ingressou dispositivo configuração descrita acima, considere a configuração de [configuração de dispositivo ingressado for híbrida Azure AD](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="d4a6c-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="d4a6c-118">Considerações ao ingressar seus dispositivos do Windows Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="d4a6c-119">Se você estiver Azure AD ingressar em um dispositivo do Windows que tenha sido previamente associados a um domínio ou em um grupo de trabalho, você precisa considerar as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="d4a6c-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="d4a6c-p105">Quando um dispositivo Azure AD ingressa, ele cria um novo usuário sem fazer referência a um perfil existente. Para corrigir esse problema, perfis precisam ser migrados manualmente. Um perfil de usuário contém informações sobre como Favoritos, arquivos locais, as configurações do navegador, configurações do menu Iniciar, etc. Uma abordagem recomendada é encontrar uma ferramenta de terceiros para mapear os arquivos existentes e configurações para o novo perfil</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="d4a6c-p106">Se o dispositivo está usando objetos de diretiva de grupo (GPO), alguns GPOs podem não ter um comparável [Provedor de serviço de configuração](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) no Intune. Execute a [ferramenta MMAT](https://www.microsoft.com/download/details.aspx?id=45520) para encontrar provedores comparáveis para os GPOs existentes.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="d4a6c-p107">Os usuários não poderão autenticar aos aplicativos que dependem de autenticação do Active Directory. Para lidar com isso avaliar usando um aplicativo de legado e considerar a atualização para um aplicativo que usa autenticação moderna se possível.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="d4a6c-p108">Descoberta de impressora do Active Directory não funcionará. Para corrigir esse problema, forneça caminhos de impressora direto para todos os usuários ou aproveitar a [Impressão de nuvem híbrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="d4a6c-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

