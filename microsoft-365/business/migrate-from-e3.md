---
title: Migrar para o Microsoft 365 Business do Office 365 E3
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
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Saiba como mover sua empresa para o Microsoft 365 Business Premium do Office 365 E3.
ms.openlocfilehash: 3f9fd70b2d31b32027981e638de249d92e98ea08
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164524"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="85992-103">Migrando do Office 365 E3 para o Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="85992-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="85992-104">O Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseados em nuvem com gerenciamento de dispositivos simples e segurança.</span><span class="sxs-lookup"><span data-stu-id="85992-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="85992-105">Se você tem atualmente uma assinatura do Office 365 E3, mas não tem mais de 300 funcionários, considere alternar para o Microsoft 365 Business Premium para recursos de segurança adicionais.</span><span class="sxs-lookup"><span data-stu-id="85992-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="85992-106">A migração é fácil: primeiro você alterna licenças e todas as informações de dados e usuários em sua assinatura atual são mantidas.</span><span class="sxs-lookup"><span data-stu-id="85992-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="85992-107">Após a migração, você precisará configurar os recursos adicionados ao Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="85992-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="85992-108">Diferenças entre o Office 365 E3 e o Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="85992-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="85992-109">Esta tabela mostra as diferenças entre o Microsoft 365 Business Premium e o Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="85992-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="85992-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="85992-110">Feature</span></span>    | <span data-ttu-id="85992-111">Suporte no Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="85992-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="85992-112">Suporte no Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="85992-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="85992-113">**No local**</span><span class="sxs-lookup"><span data-stu-id="85992-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="85992-114">Aplicativos do Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="85992-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="85992-115">Microsoft 365 Apps para Pequenos e Médios negócios</span><span class="sxs-lookup"><span data-stu-id="85992-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="85992-116">Microsoft 365 Apps para Grandes Empresas</span><span class="sxs-lookup"><span data-stu-id="85992-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="85992-117">**Aplicativos de produtividade na nuvem**</span><span class="sxs-lookup"><span data-stu-id="85992-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="85992-118">Exchange Online e Outlook</span><span class="sxs-lookup"><span data-stu-id="85992-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="85992-119">Limite de armazenamento de 50 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="85992-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="85992-120">Limite de armazenamento de 100 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="85992-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="85992-121">Teams</span><span class="sxs-lookup"><span data-stu-id="85992-121">Teams</span></span>    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="85992-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="85992-124">OneDrive for Business</span></span>    | <span data-ttu-id="85992-125">Limite de armazenamento de 1 TB por usuário</span><span class="sxs-lookup"><span data-stu-id="85992-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="85992-126">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="85992-126">Unlimited</span></span> | 
| <span data-ttu-id="85992-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="85992-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="85992-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="85992-130">StaffHub</span></span>    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="85992-133">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="85992-133">Outlook Customer Manager</span></span>    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="85992-135">**Proteção contra Ameaças**</span><span class="sxs-lookup"><span data-stu-id="85992-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="85992-136">Microsoft Defender para Office 365 Plano 1</span><span class="sxs-lookup"><span data-stu-id="85992-136">Defender for Office 365 Plan 1</span></span> | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="85992-138">Não incluído, mas pode ser adicionado em</span><span class="sxs-lookup"><span data-stu-id="85992-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="85992-139">**O gerenciamento de identidades**</span><span class="sxs-lookup"><span data-stu-id="85992-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="85992-140">Redefinição de senha de autoatendamento para contas híbridas do Azure Active Directory (Azure AD), autenticação multifacional do Azure AD (MFA), Acesso Condicional, write-back de senha para identidades locais</span><span class="sxs-lookup"><span data-stu-id="85992-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="85992-142">**Gerenciamento de aplicativo e dispositivo**</span><span class="sxs-lookup"><span data-stu-id="85992-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="85992-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="85992-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="85992-145">Ativação de computador compartilhado</span><span class="sxs-lookup"><span data-stu-id="85992-145">Shared computer activation</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="85992-148">Direitos de atualização para o Windows 10 Pro a partir de licenças do Win 7/8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="85992-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="85992-150">**Proteção de informações**</span><span class="sxs-lookup"><span data-stu-id="85992-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="85992-151">Prevenção contra Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="85992-151">Office 365 Data Loss Prevention</span></span>|    ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)|![Incluído no Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="85992-154">Plano 1 de Proteção de Informações do Azure, imposição do Bitlocker</span><span class="sxs-lookup"><span data-stu-id="85992-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="85992-156">Plano 1 de Proteção de Informações do Azure, rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="85992-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="85992-158">**Licença de Acesso para Cliente (direitos CAL)**</span><span class="sxs-lookup"><span data-stu-id="85992-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="85992-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="85992-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Incluído no Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="85992-161"><sup>1</sup> A versão do Microsoft 365 Business Premium dos aplicativos do Office não inclui ativação de volume por meio da Política de Grupo, telemetria de aplicativos, controles de atualização, comparação e consulta de planilhas ou business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="85992-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="85992-162">Migração</span><span class="sxs-lookup"><span data-stu-id="85992-162">Migration</span></span>

<span data-ttu-id="85992-163">Para migrar sua assinatura, consulte [Alterar planos manualmente](../commerce/subscriptions/change-plans-manually.md) para obter instruções se você deseja mover apenas algumas pessoas para o Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="85992-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="85992-164">Você também pode [atualizar todos](../commerce/subscriptions/upgrade-to-different-plan.md)automaticamente ou trabalhar com um parceiro para mover sua assinatura e licenças do E3 para uma assinatura do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="85992-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="85992-165">As seções a seguir descrevem as alterações que você precisa fazer, se alguma, e o que você pode fazer após a migração.</span><span class="sxs-lookup"><span data-stu-id="85992-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="85992-166">Dados e configuração de assinatura do Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="85992-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="85992-167">Você não precisa fazer alterações na sua assinatura ou dados atuais antes de migrar, o que inclui:</span><span class="sxs-lookup"><span data-stu-id="85992-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="85992-168">Configuração de assinatura, como registros DNS e nomes de domínio.</span><span class="sxs-lookup"><span data-stu-id="85992-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="85992-169">Contas de usuário e grupo e configurações de autenticação, como autenticação multifacional ou políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="85992-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="85992-170">Configurações de serviço de produtividade e seus dados, como Teams, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.</span><span class="sxs-lookup"><span data-stu-id="85992-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="85992-171">Os aplicativos do Office serão dimensionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="85992-171">Office applications will scale automatically.</span></span> <span data-ttu-id="85992-172">O licenciamento moderno do Office 365 verificará a atribuição de licença do usuário a cada 72 horas e converterá os aplicativos do Office na versão que corresponde à assinatura do usuário.</span><span class="sxs-lookup"><span data-stu-id="85992-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="85992-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="85992-173">Windows 10</span></span>

<span data-ttu-id="85992-174">Se o Windows ainda não estiver na atualização do Windows Pro Creator, [atualize-os para Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="85992-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="85992-175">Configurar políticas para proteger os dispositivos e arquivos do usuário</span><span class="sxs-lookup"><span data-stu-id="85992-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="85992-176">Se você configurar políticas e dispositivos do Office 365 MDM, esses dispositivos serão listados na página Dispositivos no Centro de administração do Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="85992-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="85992-177">Todas as políticas configuradas aparecerão na lista de políticas clássicas no [portal do Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="85992-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="85992-178">Depois de ter atribuído licenças ao Microsoft 365 Business Premium, você pode começar a proteger os dispositivos e arquivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="85992-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="85992-179">Se você atualizou todos na sua organização para o Microsoft 365 Business Premium, você verá o assistente de instalação na Home page e poderá seguir a configuração do [Microsoft 365 Business Premium](set-up.md) nas etapas do assistente de configuração para proteger arquivos e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="85992-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="85992-180">Você também pode concluir estas etapas na página Dispositivos:</span><span class="sxs-lookup"><span data-stu-id="85992-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="85992-181">No centro de administração, na nav esquerda, vá para **Políticas de** \> **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="85992-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="85992-182">Na página **Políticas de** dispositivo, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="85992-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="85992-183">No painel **Adicionar política,** dê um nome à política e escolha um **tipo de Política** no drop-down.</span><span class="sxs-lookup"><span data-stu-id="85992-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="85992-184">Você pode configurar políticas de aplicativos para proteger arquivos em dispositivos Android e iPhone, bem como o Windows 10, e pode configurar políticas de configuração de dispositivo para dispositivos Windows 10 pertencentes à empresa.</span><span class="sxs-lookup"><span data-stu-id="85992-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="85992-185">Confira os seguintes links para obter detalhes:</span><span class="sxs-lookup"><span data-stu-id="85992-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="85992-186">Definir configurações de proteção de aplicativo para dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="85992-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="85992-187">Definir configurações de proteção de aplicativo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="85992-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="85992-188">Definir configurações de proteção de dispositivo para computadores com Windows 10</span><span class="sxs-lookup"><span data-stu-id="85992-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="85992-189">Depois de configurar políticas, você e seus funcionários podem configurar dispositivos:</span><span class="sxs-lookup"><span data-stu-id="85992-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="85992-190">Consulte [Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium](set-up-windows-devices.md) para etapas para dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="85992-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="85992-191">Consulte [Configurar dispositivos móveis para usuários do Microsoft 365 Business Premium](set-up-mobile-devices.md) para etapas para telefones Android e iPhones.</span><span class="sxs-lookup"><span data-stu-id="85992-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="85992-192">Tamanho da caixa de correio</span><span class="sxs-lookup"><span data-stu-id="85992-192">Mailbox Size</span></span>

<span data-ttu-id="85992-193">O Microsoft 365 Business Premium tem um limite de armazenamento de 50 GB, pois usa o Plano 1 do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="85992-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="85992-194">Ao migrar para o Microsoft 365 Business Premium, se algum de seus usuários exceder 50 GB de armazenamento de caixa de correio, é recomendável atribuir a esse usuário um Plano 2 do Exchange Online e remover o Plano 1 do Exchange Online, pois não é viável atribuir ambos.</span><span class="sxs-lookup"><span data-stu-id="85992-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="85992-195">Proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="85992-195">Threat protection</span></span>

<span data-ttu-id="85992-196">Depois de migrar para o Microsoft 365 Business Premium, você terá o Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="85992-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="85992-197">Consulte [o Microsoft Defender para Office 365](../security/defender-365-security/defender-for-office-365.md) para ver uma visão geral.</span><span class="sxs-lookup"><span data-stu-id="85992-197">See [Microsoft Defender for Office 365](../security/defender-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="85992-198">Para configurar, consulte [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), set up Safe [Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="85992-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="85992-199">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="85992-199">Sensitivity labels</span></span>

<span data-ttu-id="85992-200">Para começar a usar rótulos de sensibilidade, consulte [Visão geral dos](../compliance/sensitivity-labels.md) rótulos de sensibilidade e crie e gerencie o vídeo de [rótulos de sensibilidade.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="85992-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
