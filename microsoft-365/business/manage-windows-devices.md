---
title: Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Saiba como habilitar o Microsoft 365 para proteger dispositivos do Windows 10 associados ao AD local.
ms.openlocfilehash: af0e78ef6e79bfd612b11a16538e7afcd377ffb0
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071541"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="4dc65-103">Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="4dc65-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="4dc65-104">Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local.</span><span class="sxs-lookup"><span data-stu-id="4dc65-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="4dc65-105">Você pode configurar isso primeiro sincronizando o Active Directory com o Azure Active Directory, seguido ao registrar os dispositivos Windows 10 com o Azure AD e registrá-los para gerenciamento de dispositivos móveis pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="4dc65-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="4dc65-106">Configurar dispositivos associados ao domínio para serem gerenciados pelo Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="4dc65-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="4dc65-107">Para configurar os dispositivos que ingressaram no domínio da sua organização para se beneficiar dos recursos fornecidos pelo Azure Active Directory, além do Active Directory local, é possível implementar **dispositivos do Azure ad associados híbridos**.</span><span class="sxs-lookup"><span data-stu-id="4dc65-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="4dc65-108">Estes são os dispositivos que ingressaram no seu Active Directory local e no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4dc65-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="4dc65-109">Dispositivos híbridos associados do Azure AD podem ser protegidos e gerenciados pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="4dc65-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="4dc65-110">Conclua as etapas abaixo para tornar seus dispositivos Windows 10 híbridos do Azure AD associados e gerenciados pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="4dc65-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="4dc65-111">Para sincronizar seus usuários, grupos e contatos do Active Directory local para o Active Directory do Azure, execute o assistente de sincronização de diretórios e o Azure Active Directory Connect conforme descrito em [Configurar a sincronização de diretórios para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="4dc65-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4dc65-112">As etapas são exatamente as mesmas para o Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="4dc65-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="4dc65-113">Antes de concluir a etapa 3 para permitir que os dispositivos Windows 10 sejam associados ao Azure AD híbrido, você precisa certificar-se de que atende aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="4dc65-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="4dc65-114">Você está executando a versão mais recente do Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="4dc65-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="4dc65-115">O Azure AD Connect sincronizou todos os objetos de computador dos dispositivos que você deseja que sejam associados ao Azure AD híbrido.</span><span class="sxs-lookup"><span data-stu-id="4dc65-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="4dc65-116">Se os objetos de computador pertencem a unidades organizacionais (OU) específicas, verifique se essas UOs estão definidas para sincronização no Azure AD Connect também.</span><span class="sxs-lookup"><span data-stu-id="4dc65-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="4dc65-117">Registre os dispositivos Windows 10 associados ao domínio existente para que o Azure AD híbrido seja Unido e registre-os para gerenciamento de dispositivos móveis pelo Intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="4dc65-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="4dc65-118">Siga as instruções passo a passo sobre [como configurar dispositivos híbridos associados do Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="4dc65-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="4dc65-119">Isso permitirá que a sincronização de seu Active Directory local seja associada aos computadores Windows 10 e tornará-os prontos para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="4dc65-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="4dc65-120">Para registrar um dispositivo Windows 10 para gerenciamento de dispositivos móveis, confira [registrar um dispositivo Windows 10 com o Intune usando uma política de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="4dc65-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="4dc65-121">Você pode definir a política de grupo em um nível de computador local ou para operações em massa, você pode criar essa configuração de política de grupo no servidor de controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="4dc65-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>