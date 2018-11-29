---
title: Permitir que os dispositivos Windows 10 associados a um domínio a ser gerenciado pelo Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Aprenda a habilitar o Microsoft 365 proteger AD local ingressou dispositivos Windows 10.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864828"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="61d6f-103">Permitir que os dispositivos Windows 10 associados a um domínio a ser gerenciado pelo Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="61d6f-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="61d6f-p101">Se sua organização usa o Windows Server Active Directory local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10, e ainda manter o acesso aos recursos locais que exigem autenticação local. Você pode configurar esse primeiro sincronizando seu Active Directory com o Windows Azure Active Directory, seguido pelo registrando os dispositivos Windows 10 com o Azure AD e inscrevendo-los para o gerenciamento de dispositivo móvel pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="61d6f-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="61d6f-106">Configurar os dispositivos de domínio a ser gerenciado pelo Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="61d6f-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="61d6f-p102">Para configurar o domínio dispositivos de sua organização para se beneficiar dos recursos fornecidos pelo Windows Azure Active Directory além do Active Directory no local, você pode implementar **híbrida Azure AD ingressou dispositivos**. Esses são dispositivos que são reunidos tanto para seu Active Directory no local e seu Active Directory do Windows Azure. Híbrido Azure AD ingressado dispositivos podem ser protegidos e gerenciados pelo Microsoft 365 Business..</span><span class="sxs-lookup"><span data-stu-id="61d6f-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="61d6f-110">Conclua as etapas abaixo para tornar seus dispositivos Windows 10 híbrida Azure AD ingressou e gerenciados pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="61d6f-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="61d6f-111">Para sincronizar seus usuários, grupos e contatos do Active Directory local para o Windows Azure Active Directory, execute o Assistente de sincronização de diretórios e o Azure Active Directory Connect conforme descrito em [Configurar a sincronização de diretório para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="61d6f-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="61d6f-112">As etapas são exatamente as mesmas para a Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="61d6f-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="61d6f-113">Antes de concluir a etapa 3 para permitir que os dispositivos Windows 10 a ser híbrida ingressou Azure AD, você precisará certificar-se de que você atende aos seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="61d6f-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="61d6f-114">Você estiver executando a versão mais recente do Azure AD se conectar.</span><span class="sxs-lookup"><span data-stu-id="61d6f-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="61d6f-p103">Conecte-se do Azure AD foi sincronizada todos os objetos de computador dos dispositivos que farão parte híbrida ingressou Azure AD. Se os objetos de computador pertencem ao específica (unidade Organizacional), em seguida, verifique se que essas UOs são definidos para a sincronização do Azure AD conecte também.</span><span class="sxs-lookup"><span data-stu-id="61d6f-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="61d6f-117">Registre os dispositivos de Windows 10 associados a um domínio existentes para ser híbrida ingressado for Azure AD e registrá-los para o gerenciamento de dispositivo móvel pelo Intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="61d6f-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="61d6f-p104">Siga as instruções passo a passo [como configurar dispositivos do Azure Active Directory ingressou híbrida](https://go.microsoft.com/fwlink/p/?linkid=872870). Isso permitirá a sincronização de seu local Active Directory ingressou computadores Windows 10 e torná-los a ready na nuvem.</span><span class="sxs-lookup"><span data-stu-id="61d6f-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="61d6f-p105">Para registrar um dispositivo Windows 10 para gerenciamento de dispositivos móveis, consulte [registrar um dispositivo Windows 10 com Intune usando uma diretiva de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obter instruções. Você pode definir a diretiva de grupo em um computador local nível ou para operações em massa, você pode criar essa configuração de diretiva de grupo no seu servidor do controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="61d6f-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

