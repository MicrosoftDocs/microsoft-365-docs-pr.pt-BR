---
title: Migrar para Microsoft 365 Business do Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Saiba como mover sua empresa para Microsoft 365 Business Premium do Office 365 E3.
ms.openlocfilehash: 990ca8bdae979f1efb8a60a3460add2953a51892
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327161"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="976a3-103">Migrando do Office 365 E3 para Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="976a3-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="976a3-104">Microsoft 365 Business Premium tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseados em nuvem com gerenciamento e segurança de dispositivos simples.</span><span class="sxs-lookup"><span data-stu-id="976a3-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="976a3-105">Se você tiver uma assinatura Office 365 E3, mas não tiver mais de 300 funcionários, considere alternar para o Microsoft 365 Business Premium para recursos de segurança adicionais.</span><span class="sxs-lookup"><span data-stu-id="976a3-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="976a3-106">A migração é fácil: primeiro você alterna licenças e todas as informações de dados e usuários em sua assinatura atual são mantidas.</span><span class="sxs-lookup"><span data-stu-id="976a3-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="976a3-107">Após a migração, você precisará configurar os recursos que são adicionados Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="976a3-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="976a3-108">Diferenças entre Office 365 E3 e Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="976a3-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="976a3-109">Esta tabela mostra as diferenças entre Microsoft 365 Business Premium e Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="976a3-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="976a3-110">Recurso</span><span class="sxs-lookup"><span data-stu-id="976a3-110">Feature</span></span>    | <span data-ttu-id="976a3-111">Suporte em Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="976a3-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="976a3-112">Suporte no Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="976a3-112">Support in Office 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="976a3-113">**No local**</span><span class="sxs-lookup"><span data-stu-id="976a3-113">**On-premises**</span></span>        | | |
| <span data-ttu-id="976a3-114">Office apps<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="976a3-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="976a3-115">Microsoft 365 Apps para Pequenos e Médios negócios</span><span class="sxs-lookup"><span data-stu-id="976a3-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="976a3-116">Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="976a3-116">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="976a3-117">**Aplicativos de produtividade na nuvem**</span><span class="sxs-lookup"><span data-stu-id="976a3-117">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="976a3-118">Exchange Online e Outlook</span><span class="sxs-lookup"><span data-stu-id="976a3-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="976a3-119">Limite de armazenamento de 50 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="976a3-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="976a3-120">Limite de armazenamento de 100 GB por caixa de correio e limites ilimitados Arquivamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="976a3-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> |
| <span data-ttu-id="976a3-121">Teams</span><span class="sxs-lookup"><span data-stu-id="976a3-121">Teams</span></span>    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="976a3-124">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="976a3-124">OneDrive for Business</span></span>    | <span data-ttu-id="976a3-125">Limite de armazenamento de 1 TB por usuário</span><span class="sxs-lookup"><span data-stu-id="976a3-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="976a3-126">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="976a3-126">Unlimited</span></span> | 
| <span data-ttu-id="976a3-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="976a3-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="976a3-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="976a3-130">StaffHub</span></span>    | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png) |
| <span data-ttu-id="976a3-133">**Proteção contra Ameaças**</span><span class="sxs-lookup"><span data-stu-id="976a3-133">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="976a3-134">Microsoft Defender para Office 365 Plano 1</span><span class="sxs-lookup"><span data-stu-id="976a3-134">Defender for Office 365 Plan 1</span></span> | ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="976a3-136">Não incluído, mas pode ser adicionado em</span><span class="sxs-lookup"><span data-stu-id="976a3-136">Not included, but can be added on</span></span> |
| <span data-ttu-id="976a3-137">**O gerenciamento de identidades**</span><span class="sxs-lookup"><span data-stu-id="976a3-137">**Identity management**</span></span>        | | |
| <span data-ttu-id="976a3-138">Redefinição de senha de autoatenduro para contas Azure Active Directory (Azure AD), autenticação multifacional do Azure AD (MFA), Acesso Condicional, write-back de senha para identidades locais</span><span class="sxs-lookup"><span data-stu-id="976a3-138">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="976a3-140">**Gerenciamento de aplicativo e dispositivo**</span><span class="sxs-lookup"><span data-stu-id="976a3-140">**Device and app management**</span></span>        | | |
| <span data-ttu-id="976a3-141">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="976a3-141">Microsoft Intune, Windows AutoPilot</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="976a3-143">Ativação de computador compartilhado</span><span class="sxs-lookup"><span data-stu-id="976a3-143">Shared computer activation</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    | ![Incluído no Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="976a3-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span><span class="sxs-lookup"><span data-stu-id="976a3-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)    ||
| <span data-ttu-id="976a3-148">**Proteção de informações**</span><span class="sxs-lookup"><span data-stu-id="976a3-148">**Information protection**</span></span>        | | |
|<span data-ttu-id="976a3-149">Prevenção contra Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="976a3-149">Office 365 Data Loss Prevention</span></span>|    ![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)|![Incluído no Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="976a3-152">Plano 1 de Proteção de Informações do Azure, BitLocker imposição</span><span class="sxs-lookup"><span data-stu-id="976a3-152">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="976a3-154">Plano 1 de Proteção de Informações do Azure, rótulos de sensibilidade</span><span class="sxs-lookup"><span data-stu-id="976a3-154">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Incluído no Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="976a3-156">**Licença de Acesso para Cliente (direitos CAL)**</span><span class="sxs-lookup"><span data-stu-id="976a3-156">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="976a3-157">Enterprise Pacote CAL (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="976a3-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Incluído no Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="976a3-159"><sup>1</sup> A Microsoft 365 Business Premium versão Office aplicativos do Office não inclui ativação de volume por meio da Política de Grupo, telemetria de aplicativos, controles de atualização, comparação e consulta de planilhas ou business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="976a3-159"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="976a3-160">Migração</span><span class="sxs-lookup"><span data-stu-id="976a3-160">Migration</span></span>

<span data-ttu-id="976a3-161">Para migrar sua assinatura, consulte [Alterar planos manualmente](../commerce/subscriptions/change-plans-manually.md) para obter instruções se você deseja mover apenas algumas pessoas para Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="976a3-161">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="976a3-162">Você também pode [atualizar todos automaticamente](../commerce/subscriptions/upgrade-to-different-plan.md)ou trabalhar com um parceiro para mover sua assinatura e licenças do E3 para uma Microsoft 365 Business Premium assinatura.</span><span class="sxs-lookup"><span data-stu-id="976a3-162">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="976a3-163">As seções a seguir descrevem as alterações que você precisa fazer, se alguma, e o que você pode fazer após a migração.</span><span class="sxs-lookup"><span data-stu-id="976a3-163">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="976a3-164">Office 365 Dados e configuração de assinatura do E3</span><span class="sxs-lookup"><span data-stu-id="976a3-164">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="976a3-165">Você não precisa fazer alterações na sua assinatura ou dados atuais antes de migrar, o que inclui:</span><span class="sxs-lookup"><span data-stu-id="976a3-165">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="976a3-166">Configuração de assinatura, como registros DNS e nomes de domínio.</span><span class="sxs-lookup"><span data-stu-id="976a3-166">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="976a3-167">Contas de usuário e grupo e configurações de autenticação, como autenticação multifacional ou políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="976a3-167">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="976a3-168">Configurações de serviço de produtividade e seus dados, como Teams, caixas de correio Exchange Online, sites do SharePoint Online, pastas OneDrive for Business e OneNote blocos de anotações.</span><span class="sxs-lookup"><span data-stu-id="976a3-168">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="976a3-169">Office aplicativos serão dimensionados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="976a3-169">Office applications will scale automatically.</span></span> <span data-ttu-id="976a3-170">Office 365 licenciamento moderno verificará a atribuição de licença do usuário a cada 72 horas e converterá Office aplicativos para a versão que corresponde à assinatura do usuário.</span><span class="sxs-lookup"><span data-stu-id="976a3-170">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="976a3-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="976a3-171">Windows 10</span></span>

<span data-ttu-id="976a3-172">Se o Windows já não estiver na atualização Windows Pro do Criador, atualize-os para Windows Pro [Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="976a3-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="976a3-173">Configurar políticas para proteger os dispositivos e arquivos do usuário</span><span class="sxs-lookup"><span data-stu-id="976a3-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="976a3-174">Se você configurar Office 365 e dispositivos MDM, esses dispositivos serão listados na página **Dispositivos** no Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="976a3-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="976a3-175">Todas as políticas configuradas aparecerão na lista de políticas clássicas no [portal do Intune.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="976a3-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="976a3-176">Depois de ter atribuído licenças Microsoft 365 Business Premium, você pode começar a proteger os dispositivos e arquivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="976a3-176">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="976a3-177">Se você atualizou todos na sua organização para Microsoft 365 Business Premium, você verá o assistente de [](set-up.md) instalação na Home page e poderá seguir o guia Configurar Microsoft 365 Business Premium nas etapas do assistente de instalação para proteger arquivos e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="976a3-177">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="976a3-178">Você também pode concluir estas etapas na página Dispositivos:</span><span class="sxs-lookup"><span data-stu-id="976a3-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="976a3-179">No centro de administração, na nav esquerda, vá para **Políticas de** \> **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="976a3-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="976a3-180">Na página **Políticas de** dispositivo, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="976a3-180">On the **Device policies** page, choose **Add**.</span></span>

3. <span data-ttu-id="976a3-181">No painel **Adicionar política,** dê um nome à política e escolha um **tipo de Política** no drop-down.</span><span class="sxs-lookup"><span data-stu-id="976a3-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span>

     <span data-ttu-id="976a3-182">Você pode configurar políticas de aplicativos para proteger arquivos em dispositivos Android e iPhone, bem como Windows 10, e pode configurar políticas de configuração de dispositivos para dispositivos Windows 10 da empresa.</span><span class="sxs-lookup"><span data-stu-id="976a3-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="976a3-183">Confira os seguintes links para obter detalhes:</span><span class="sxs-lookup"><span data-stu-id="976a3-183">See the following links for details:</span></span>

  - [<span data-ttu-id="976a3-184">Definir configurações de proteção de aplicativo para dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="976a3-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

  - [<span data-ttu-id="976a3-185">Definir configurações de proteção de aplicativo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="976a3-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

  - [<span data-ttu-id="976a3-186">Definir configurações de proteção de dispositivo para Windows 10 PCs</span><span class="sxs-lookup"><span data-stu-id="976a3-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="976a3-187">Depois de configurar políticas, você e seus funcionários podem configurar dispositivos:</span><span class="sxs-lookup"><span data-stu-id="976a3-187">Once you set up policies, you and your employees can set up devices:</span></span>

  - <span data-ttu-id="976a3-188">Consulte [Configurar dispositivos Windows para usuários Microsoft 365 Business Premium para](set-up-windows-devices.md) etapas para Windows dispositivos.</span><span class="sxs-lookup"><span data-stu-id="976a3-188">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 

  - <span data-ttu-id="976a3-189">Consulte [Configurar dispositivos móveis para usuários Microsoft 365 Business Premium para](set-up-mobile-devices.md) etapas para telefones Android e iPhones.</span><span class="sxs-lookup"><span data-stu-id="976a3-189">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="976a3-190">Tamanho da caixa de correio</span><span class="sxs-lookup"><span data-stu-id="976a3-190">Mailbox Size</span></span>

<span data-ttu-id="976a3-191">Microsoft 365 Business Premium tem um limite de armazenamento de 50 GB, pois usa Exchange Online Plano 1.</span><span class="sxs-lookup"><span data-stu-id="976a3-191">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="976a3-192">Ao migrar para o Microsoft 365 Business Premium, se algum de seus usuários exceder 50 GB de armazenamento de caixa de correio, é recomendável atribuir a esse usuário um plano 2 do Exchange Online e remover o plano 1 do Exchange Online, pois não é viável atribuir ambos.</span><span class="sxs-lookup"><span data-stu-id="976a3-192">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>

### <a name="threat-protection"></a><span data-ttu-id="976a3-193">Proteção contra ameaças</span><span class="sxs-lookup"><span data-stu-id="976a3-193">Threat protection</span></span>

<span data-ttu-id="976a3-194">Depois de migrar para Microsoft 365 Business Premium, você terá o Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="976a3-194">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="976a3-195">Consulte [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) para ver uma visão geral.</span><span class="sxs-lookup"><span data-stu-id="976a3-195">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="976a3-196">Para configurar, consulte [configurar Cofre Links,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)configurar Cofre [Anexos](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)e configurar [Anti-phishing](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)no Defender para Office 365 .</span><span class="sxs-lookup"><span data-stu-id="976a3-196">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="976a3-197">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="976a3-197">Sensitivity labels</span></span>

<span data-ttu-id="976a3-198">Para começar a usar rótulos de sensibilidade, consulte [Visão geral dos](../compliance/sensitivity-labels.md) rótulos de sensibilidade e crie e gerencie o vídeo de [rótulos de sensibilidade.](../business-video/create-sensitivity-labels.md)</span><span class="sxs-lookup"><span data-stu-id="976a3-198">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>
