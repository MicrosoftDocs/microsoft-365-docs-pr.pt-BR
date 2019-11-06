---
title: Migrar para o Microsoft 365 Business do Office 365 E3
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Saiba como mover sua empresa para o Microsoft 365 Business do Office 365 E3.
ms.openlocfilehash: 5142038110cada6e1da77d405c82f119e0f9e4d3
ms.sourcegitcommit: 0fa897d06b664c0ed005817752da1426d4ee17cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38002412"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="f829e-103">Migrando do Office 365 E3 para a Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f829e-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="f829e-104">O Microsoft 365 Business tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseada na nuvem com gerenciamento e segurança simples de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f829e-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span>  <span data-ttu-id="f829e-105">Se você tiver uma assinatura do Office 365 E3, mas não tiver mais de 300 funcionários, considere mudar para o Microsoft 365 Business para recursos de segurança adicionais.</span><span class="sxs-lookup"><span data-stu-id="f829e-105">If you currently have an Office 365 E3 subscription, but don’t have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="f829e-106">A migração é fácil: primeiro você muda de licenças e todos os seus dados e informações de usuário em sua assinatura atual são mantidos.</span><span class="sxs-lookup"><span data-stu-id="f829e-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="f829e-107">Após a migração, você precisará configurar os recursos que são adicionados no Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f829e-107">After the migration you will need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="f829e-108">Diferenças entre o Office 365 E3 e o Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f829e-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="f829e-109">Esta tabela mostra as diferenças entre o Microsoft 365 Business e o Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="f829e-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="f829e-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="f829e-110">Feature</span></span>   | <span data-ttu-id="f829e-111">Suporte no Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="f829e-111">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="f829e-112">Suporte no Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="f829e-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="f829e-113">**No local**</span><span class="sxs-lookup"><span data-stu-id="f829e-113">**On-premises**</span></span>       | | | 
| <span data-ttu-id="f829e-114">Aplicativos do Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f829e-114">Office apps<sup>1</sup></span></span>   | <span data-ttu-id="f829e-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="f829e-115">Office 365 Business</span></span>   | <span data-ttu-id="f829e-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="f829e-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="f829e-117">**Aplicativos de produtividade em nuvem**</span><span class="sxs-lookup"><span data-stu-id="f829e-117">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="f829e-118">Exchange Online e Outlook</span><span class="sxs-lookup"><span data-stu-id="f829e-118">Exchange Online and Outlook</span></span>   | <span data-ttu-id="f829e-119">limite de armazenamento de 50 GB por caixa de correio e arquivamento ilimitado do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f829e-119">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="f829e-120">limite de armazenamento de 100 GB por caixa de correio e arquivamento ilimitado do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f829e-120">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="f829e-121">Teams</span><span class="sxs-lookup"><span data-stu-id="f829e-121">Teams</span></span> | ![Incluído no Microsoft 365 Business](./media/check-mark.png)   | ![Incluído com o Office 365 E3](./media/check-mark.png) | 
| <span data-ttu-id="f829e-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="f829e-124">OneDrive for Business</span></span> | <span data-ttu-id="f829e-125">limite de armazenamento de 1 TB por usuário</span><span class="sxs-lookup"><span data-stu-id="f829e-125">1 TB storage limit per user</span></span>   | <span data-ttu-id="f829e-126">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="f829e-126">Unlimited</span></span> | 
| <span data-ttu-id="f829e-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="f829e-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluído no Microsoft 365 Business](./media/check-mark.png)   | ![Incluído com o Office 365 E3](./media/check-mark.png) | 
| <span data-ttu-id="f829e-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="f829e-130">StaffHub</span></span>  | ![Incluído no Microsoft 365 Business](./media/check-mark.png)   | ![Incluído com o Office 365 E3](./media/check-mark.png) | 
| <span data-ttu-id="f829e-133">Gerenciador de clientes do Outlook, MileIQ</span><span class="sxs-lookup"><span data-stu-id="f829e-133">Outlook Customer Manager, MileIQ</span></span>  | ![Incluído no Microsoft 365 Business](./media/check-mark.png)   | | 
| <span data-ttu-id="f829e-135">**Proteção contra ameaças**</span><span class="sxs-lookup"><span data-stu-id="f829e-135">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="f829e-136">Office 365 plano de proteção avançada contra ameaças (ATP) 1</span><span class="sxs-lookup"><span data-stu-id="f829e-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Incluído no Microsoft 365 Business](./media/check-mark.png)  | <span data-ttu-id="f829e-138">Não está incluído, mas pode ser adicionado em</span><span class="sxs-lookup"><span data-stu-id="f829e-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="f829e-139">**O gerenciamento de identidades**</span><span class="sxs-lookup"><span data-stu-id="f829e-139">**Identity management**</span></span>       | | | 
| <span data-ttu-id="f829e-140">Redefinição de senha de autoatendimento para contas híbridas do Azure Active Directory (Azure AD), autenticação multifator do Azure (MFA), acesso condicional, write-back de senha para identidades locais</span><span class="sxs-lookup"><span data-stu-id="f829e-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Incluído no Microsoft 365 Business](./media/check-mark.png) |  | 
| <span data-ttu-id="f829e-142">**Gerenciamento de dispositivos e aplicativos**</span><span class="sxs-lookup"><span data-stu-id="f829e-142">**Device and app management**</span></span>     | | |
| <span data-ttu-id="f829e-143">Microsoft Intune, piloto automático do Windows</span><span class="sxs-lookup"><span data-stu-id="f829e-143">Microsoft Intune, Windows AutoPilot</span></span>|  ![Incluído no Microsoft 365 Business](./media/check-mark.png) |  |
| <span data-ttu-id="f829e-145">Ativação de computador compartilhado</span><span class="sxs-lookup"><span data-stu-id="f829e-145">Shared computer activation</span></span>|   ![Incluído no Microsoft 365 Business](./media/check-mark.png) | ![Incluído com o Office 365 E3](./media/check-mark.png)| 
| <span data-ttu-id="f829e-148">Atualizar direitos para o Windows 10 pro de licenças do Win 7/8.1 pro</span><span class="sxs-lookup"><span data-stu-id="f829e-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Incluído no Microsoft 365 Business](./media/check-mark.png) || 
| <span data-ttu-id="f829e-150">**Proteção de informações**</span><span class="sxs-lookup"><span data-stu-id="f829e-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="f829e-151">Prevenção de perda de dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="f829e-151">Office 365 Data Loss Prevention</span></span>|   ![Incluído no Microsoft 365 Business](./media/check-mark.png)|![Incluído com o Office 365 E3](./media/check-mark.png)|
|<span data-ttu-id="f829e-154">Plano de proteção de informações do Azure 1, imposição do BitLocker</span><span class="sxs-lookup"><span data-stu-id="f829e-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Incluído no Microsoft 365 Business](./media/check-mark.png)||
|<span data-ttu-id="f829e-156">Plano de proteção de informações do Azure 1, rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="f829e-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Incluído no Microsoft 365 Business](./media/check-mark.png)||
|<span data-ttu-id="f829e-158">**Licença de acesso para cliente (direitos de CAL)**</span><span class="sxs-lookup"><span data-stu-id="f829e-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="f829e-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="f829e-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Incluído com o Office 365 E3](./media/check-mark.png)|

<span data-ttu-id="f829e-161"><sup>1</sup> a versão do Microsoft 365 Business dos aplicativos do Office não inclui ativação de volume por meio da política de grupo, telemetria de aplicativos, controles de atualização, comparação de planilhas e consultas de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="f829e-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps do not include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, and business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="f829e-162">Migração</span><span class="sxs-lookup"><span data-stu-id="f829e-162">Migration</span></span>

<span data-ttu-id="f829e-163">Para migrar sua assinatura, consulte [mudar para um plano diferente manualmente](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) para obter instruções se você deseja mover apenas algumas pessoas para o Microsoft 365 Business, você pode [atualizar todos automaticamente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)ou pode trabalhar com o parceiro para migrar o E3 assinatura e licenças para uma assinatura do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="f829e-163">To migrate your subscription, see [switch to a different plan manually](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) for instructions if you want to move just a few people to Microsoft 365 Business, you can [upgrade everyone automatically](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan), or you can work with partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="f829e-164">As seções a seguir descrevem as alterações que você precisa fazer, se houver, e o que você pode fazer após a migração.</span><span class="sxs-lookup"><span data-stu-id="f829e-164">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="f829e-165">Dados e configuração de assinatura do Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="f829e-165">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="f829e-166">Você não precisa fazer alterações em sua assinatura atual ou dados antes de migrar, o que inclui:</span><span class="sxs-lookup"><span data-stu-id="f829e-166">You don’t need to do any changes to your current subscription or data prior to migrating, which includes:</span></span>

- <span data-ttu-id="f829e-167">Configuração de assinatura, como registros DNS e nomes de domínio.</span><span class="sxs-lookup"><span data-stu-id="f829e-167">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="f829e-168">Contas de usuário e de grupo e configurações de autenticação, como a autenticação multifator ou políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="f829e-168">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="f829e-169">Configurações de serviço de produtividade e seus dados, como equipes, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.</span><span class="sxs-lookup"><span data-stu-id="f829e-169">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="f829e-170">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f829e-170">Windows 10</span></span>

<span data-ttu-id="f829e-171">Se o Windows ainda não estiver na atualização do Windows pro Creator, será necessário [atualizá-lo para a atualização do Windows pro Creators](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="f829e-171">If your Windows aren't already on Windows Pro Creator update, you will need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="f829e-172">Configurar políticas para proteger os arquivos e os dispositivos do usuário</span><span class="sxs-lookup"><span data-stu-id="f829e-172">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="f829e-173">Se você configurar as políticas e dispositivos do Office 365 MDM, esses dispositivos serão listados na página **dispositivos** no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f829e-173">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f829e-174">Qualquer política configurada será mostrada na lista de políticas clássicas no [portal do Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="f829e-174">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="f829e-175">Após ter atribuído licenças para o Microsoft 365 Business, você pode começar a proteger os dispositivos e arquivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="f829e-175">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="f829e-176">Se você atualizou todas as pessoas em sua organização para o Microsoft 365 Business, verá o assistente de configuração na Home Page e poderá seguir as etapas [Configurar o Microsoft 365 Business no assistente de instalação](set-up.md) para proteger arquivos e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="f829e-176">If you upgraded everyone in your organization to Microsoft 365 Business, you will see the set up wizard on teh home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="f829e-177">Você também pode concluir estas etapas na página dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f829e-177">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="f829e-178">No centro de administração, na navegação à esquerda, vá para \*\*\*\* \> **políticas**de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f829e-178">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="f829e-179">Na página **políticas de dispositivo** , escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f829e-179">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="f829e-180">No painel **Adicionar política** , dê um nome à política e, em seguida, escolha um **tipo de política** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="f829e-180">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="f829e-181">Você pode configurar políticas de aplicativo para proteger arquivos em dispositivos Android e iPhone, bem como Windows 10, e pode configurar políticas de configuração de dispositivo para dispositivos do Windows 10 de propriedade da empresa.</span><span class="sxs-lookup"><span data-stu-id="f829e-181">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="f829e-182">Confira os seguintes links para obter detalhes:</span><span class="sxs-lookup"><span data-stu-id="f829e-182">See the following links for details:</span></span>
    
  - [<span data-ttu-id="f829e-183">Definir configurações de proteção de aplicativo para dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="f829e-183">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="f829e-184">Definir configurações de proteção de aplicativo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="f829e-184">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="f829e-185">Definir configurações de proteção de dispositivos para computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="f829e-185">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="f829e-186">Depois de configurar as políticas, você e seus funcionários poderão configurar dispositivos:</span><span class="sxs-lookup"><span data-stu-id="f829e-186">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="f829e-187">Confira [configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) para obter etapas para dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="f829e-187">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="f829e-188">Confira [configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md) para obter etapas para telefones Android e iPhones.</span><span class="sxs-lookup"><span data-stu-id="f829e-188">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="f829e-189">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="f829e-189">Threat protection</span></span>

<span data-ttu-id="f829e-190">Após a migração para o Microsoft 365 Business, você tem o Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="f829e-190">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="f829e-191">Confira o [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) para obter uma visão geral e configurar a configuração de [links de segurança ATP](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [configurar os anexos seguros de ATP](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) e [Configurar a ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="f829e-191">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview and to set up see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="f829e-192">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="f829e-192">Sensitivity labels</span></span>

<span data-ttu-id="f829e-193">Para começar a usar rótulos de sensibilidade, confira [visão geral dos rótulos de confidencialidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) e [criar e gerenciar o vídeo de rótulos de Sensibilidade](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="f829e-193">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
