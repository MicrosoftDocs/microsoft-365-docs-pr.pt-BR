---
title: Migrar do Microsoft 365 Business para o Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Saiba como mover sua empresa da Microsoft 365 Business para a Microsoft 365 E3.
ms.openlocfilehash: cd6b9b14e9bc1ed03635be12873fb90592efe527
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065312"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-e3"></a><span data-ttu-id="841b0-103">Migrar do Microsoft 365 Business para o Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="841b0-103">Migrate from Microsoft 365 Business to Microsoft 365 E3</span></span>

<span data-ttu-id="841b0-104">O Microsoft 365 Business tem tudo o que você precisa para sua pequena empresa, combinando os melhores aplicativos de produtividade baseada na nuvem com gerenciamento de dispositivos simples e segurança que permitem que seus funcionários façam o melhor trabalho.</span><span class="sxs-lookup"><span data-stu-id="841b0-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="841b0-105">Em alguns casos, no entanto, talvez você precise migrar sua assinatura de negócios do Microsoft 365 para a Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="841b0-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="841b0-106">Por exemplo, sua empresa cresceu e precisa de mais de 300 licenças (Parabéns, da forma).</span><span class="sxs-lookup"><span data-stu-id="841b0-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="841b0-107">Ou, seus negócios precisam de recursos corporativos, como o Office 365 ProPlus, o Windows 10 Enterprise E3 ou as licenças de acesso para Cliente Enterprise (CALs).</span><span class="sxs-lookup"><span data-stu-id="841b0-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="841b0-108">A atualização é fácil: você pode iniciar a atualização [a partir do centro de administração](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="841b0-108">Upgrading is easy: you can start the upgrade [from the Admin center](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan?view=o365-worldwide).</span></span> <span data-ttu-id="841b0-109">Todos os dados e a configuração da sua assinatura atual são mantidos.</span><span class="sxs-lookup"><span data-stu-id="841b0-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="841b0-110">Não há nada para se preparar para a migração e nada para fazer posteriormente, exceto aproveitar os novos recursos.</span><span class="sxs-lookup"><span data-stu-id="841b0-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span> 

>[!Note]
><span data-ttu-id="841b0-111">Você também pode usar uma assinatura do Microsoft 365 Business para até 300 estações e obter uma assinatura do Microsoft 365 E3 por mais de 300 estações.</span><span class="sxs-lookup"><span data-stu-id="841b0-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="841b0-112">No entanto, o Office 365 ATP não está incluído no Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="841b0-112">However, Office 365 ATP is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="841b0-113">Para obter proteção contínua contra ameaças, você deve adicionar mais licenças do Office 365 ATP para que todos os usuários no escopo das suas políticas de ATP do Office 365 sejam licenciados.</span><span class="sxs-lookup"><span data-stu-id="841b0-113">For continued threat protection, you should add additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="841b0-114">Diferenças entre o Microsoft 365 Business e o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="841b0-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="841b0-115">Esta tabela mostra as diferenças entre o Microsoft 365 Business e o Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="841b0-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 E3.</span></span>

| <span data-ttu-id="841b0-116">Recurso</span><span class="sxs-lookup"><span data-stu-id="841b0-116">Feature</span></span>   | <span data-ttu-id="841b0-117">Suporte no Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="841b0-117">Support in Microsoft 365 Business</span></span> | <span data-ttu-id="841b0-118">Suporte no Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="841b0-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="841b0-119">**No local**</span><span class="sxs-lookup"><span data-stu-id="841b0-119">**On-premises**</span></span>       | | | 
| <span data-ttu-id="841b0-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="841b0-120">Windows 10</span></span>    | <span data-ttu-id="841b0-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="841b0-121">Windows 10 Business</span></span>  |    <span data-ttu-id="841b0-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="841b0-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="841b0-123">Aplicativos do Office \*</span><span class="sxs-lookup"><span data-stu-id="841b0-123">Office apps\*</span></span>  | [<span data-ttu-id="841b0-124">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="841b0-124">Office 365 Business</span></span>](#office-365-business)   | <span data-ttu-id="841b0-125">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="841b0-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="841b0-126">**Aplicativos de produtividade em nuvem**</span><span class="sxs-lookup"><span data-stu-id="841b0-126">**Cloud productivity apps**</span></span>       | | | 
| <span data-ttu-id="841b0-127">Exchange Online e Outlook</span><span class="sxs-lookup"><span data-stu-id="841b0-127">Exchange Online and Outlook</span></span>   | <span data-ttu-id="841b0-128">limite de armazenamento de 50 GB por caixa de correio e arquivamento ilimitado do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="841b0-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>   | <span data-ttu-id="841b0-129">limite de armazenamento de 100 GB por caixa de correio e arquivamento ilimitado do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="841b0-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="841b0-130">Teams</span><span class="sxs-lookup"><span data-stu-id="841b0-130">Teams</span></span> | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-133">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="841b0-133">OneDrive for Business</span></span> | <span data-ttu-id="841b0-134">limite de armazenamento de 1 TB por usuário</span><span class="sxs-lookup"><span data-stu-id="841b0-134">1 TB storage limit per user</span></span>   | <span data-ttu-id="841b0-135">Ilimitado</span><span class="sxs-lookup"><span data-stu-id="841b0-135">Unlimited</span></span> | 
| <span data-ttu-id="841b0-136">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="841b0-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-139">Gerenciador de clientes do Outlook, MileIQ</span><span class="sxs-lookup"><span data-stu-id="841b0-139">Outlook Customer Manager, MileIQ</span></span>  | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | | 
| <span data-ttu-id="841b0-141">**Proteção contra Ameaças**</span><span class="sxs-lookup"><span data-stu-id="841b0-141">**Threat Protection**</span></span>     | | | 
| <span data-ttu-id="841b0-142">Recursos de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="841b0-142">Attack surface reduction capabilities</span></span> | [<span data-ttu-id="841b0-143">Confira esta lista</span><span class="sxs-lookup"><span data-stu-id="841b0-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="841b0-144">Gerenciamento corporativo de isolamento baseado em hardware para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="841b0-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="841b0-145">Office 365 plano de proteção avançada contra ameaças (ATP) 1</span><span class="sxs-lookup"><span data-stu-id="841b0-145">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Incluído no Microsoft 365 Business](../media/check-mark.png) | <span data-ttu-id="841b0-147">Não está incluído, mas pode ser adicionado em</span><span class="sxs-lookup"><span data-stu-id="841b0-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="841b0-148">**O gerenciamento de identidades**</span><span class="sxs-lookup"><span data-stu-id="841b0-148">**Identity management**</span></span>       | | | 
| <span data-ttu-id="841b0-149">Redefinição de senha de autoatendimento para contas híbridas do Azure Active Directory (Azure AD), autenticação multifator do Azure (MFA), acesso condicional, write-back de senha para identidades locais</span><span class="sxs-lookup"><span data-stu-id="841b0-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|    ![Incluído no Microsoft 365 Business](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-152">Descoberta do Cloud app, integridade do Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="841b0-152">Cloud App Discovery, Azure AD Connect Health</span></span>  |   | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-154">Logon único (SSO) de aplicativos do Azure AD Office 365:10 aplicativos por usuário (Galeria de aplicativos SaaS como Salesforce) \*</span><span class="sxs-lookup"><span data-stu-id="841b0-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Incluído no Microsoft 365 Business](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-157">Azure AD Premium 1 SSO: sem limite (aplicativos locais por meio do proxy de aplicativo do Azure AD e aplicativos não-Galeria usando modelos de integração de aplicativos de autoatendimento)</span><span class="sxs-lookup"><span data-stu-id="841b0-157">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>  |   | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-159">**Gerenciamento de dispositivos e aplicativos**</span><span class="sxs-lookup"><span data-stu-id="841b0-159">**Device and app management**</span></span>     | | | 
| <span data-ttu-id="841b0-160">Microsoft Intune, piloto automático do Windows</span><span class="sxs-lookup"><span data-stu-id="841b0-160">Microsoft Intune, Windows Autopilot</span></span>|  ![Incluído no Microsoft 365 Business](../media/check-mark.png)    | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="841b0-163">Acesso à área de trabalho virtual (VDA)</span><span class="sxs-lookup"><span data-stu-id="841b0-163">Virtual Desktop Access (VDA)</span></span>   |  |    ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="841b0-165">Área de trabalho virtual do Windows (WVD)</span><span class="sxs-lookup"><span data-stu-id="841b0-165">Windows Virtual Desktop (WVD)</span></span>  | ![Incluído no Microsoft 365 Business](../media/check-mark.png) |    ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="841b0-168">Ativação de computador compartilhado (SCA)</span><span class="sxs-lookup"><span data-stu-id="841b0-168">Shared Computer Activation (SCA)</span></span>   | ![Incluído no Microsoft 365 Business](../media/check-mark.png) |    ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-171">Pacote de otimização de área de trabalho da Microsoft</span><span class="sxs-lookup"><span data-stu-id="841b0-171">Microsoft Desktop Optimization Package</span></span>    | |     ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-173">**Proteção de informações**</span><span class="sxs-lookup"><span data-stu-id="841b0-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="841b0-174">Prevenção de perda de dados do Office 365, plano de proteção de informações do Azure 1</span><span class="sxs-lookup"><span data-stu-id="841b0-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>  | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-177">Proteção de informações da janela para o Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="841b0-177">Window Information Protection for endpoint DLP</span></span>    | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-180">**Licença de acesso para cliente (direitos de CAL)**</span><span class="sxs-lookup"><span data-stu-id="841b0-180">**Client Access License (CAL rights)**</span></span>    | | |   
| <span data-ttu-id="841b0-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, gerenciamento de direitos do Windows)</span><span class="sxs-lookup"><span data-stu-id="841b0-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |       ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-183">**Conformidade**</span><span class="sxs-lookup"><span data-stu-id="841b0-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="841b0-184">Arquivamento ilimitado de email</span><span class="sxs-lookup"><span data-stu-id="841b0-184">Unlimited email archiving</span></span> | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-187">Pontuação de conformidade/gerente de conformidade</span><span class="sxs-lookup"><span data-stu-id="841b0-187">Compliance Score/Compliance Manager</span></span>   | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-190">Descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="841b0-190">eDiscovery</span></span>    | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-193">Bloqueio in-loco e retenção de litígio</span><span class="sxs-lookup"><span data-stu-id="841b0-193">In-place hold and litigation hold</span></span> | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="841b0-196">Marcas de retenção e políticas de retenção do MRM (gerenciamento de registros de mensagens)</span><span class="sxs-lookup"><span data-stu-id="841b0-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>  | ![Incluído no Microsoft 365 Business](../media/check-mark.png)  | ![Incluído no Microsoft 365 E3](../media/check-mark.png) | 
||||

<span data-ttu-id="841b0-199">\*Os usuários aos quais foram atribuídos acesso aos aplicativos SaaS podem obter acesso SSO para até 10 aplicativos.</span><span class="sxs-lookup"><span data-stu-id="841b0-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="841b0-200">Os administradores podem configurar o SSO e alterar o acesso de usuário para aplicativos SaaS diferentes, mas o acesso SSO só é permitido para 10 aplicativos por usuário por vez.</span><span class="sxs-lookup"><span data-stu-id="841b0-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="841b0-201">Todos os aplicativos do Office 365 são contados como um único aplicativo.</span><span class="sxs-lookup"><span data-stu-id="841b0-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="841b0-202">Migração</span><span class="sxs-lookup"><span data-stu-id="841b0-202">Migration</span></span>

<span data-ttu-id="841b0-203">Para migrar, trabalhe com seu parceiro para transferir sua assinatura e licenças do Microsoft 365 Business para uma assinatura do Microsoft 365 E3 adequada com suas licenças.</span><span class="sxs-lookup"><span data-stu-id="841b0-203">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="841b0-204">As seções a seguir descrevem as alterações que você precisa fazer, se houver, e o que você pode fazer após a migração.</span><span class="sxs-lookup"><span data-stu-id="841b0-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="841b0-205">Dados e configuração de assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="841b0-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="841b0-206">Você não precisa fazer alterações na assinatura atual ou nos dados antes de migrar, o que inclui:</span><span class="sxs-lookup"><span data-stu-id="841b0-206">You don’t need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="841b0-207">Configuração de assinatura, como nomes de domínio DNS.</span><span class="sxs-lookup"><span data-stu-id="841b0-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="841b0-208">Contas de usuário e de grupo e configurações de autenticação, como a autenticação multifator ou políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="841b0-208">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="841b0-209">Configurações de serviço de produtividade e seus dados, como equipes, caixas de correio do Exchange Online, sites do SharePoint Online, pastas do OneDrive for Business e blocos de anotações do OneNote.</span><span class="sxs-lookup"><span data-stu-id="841b0-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="841b0-210">Os usuários agora podem desfrutar de armazenamento ilimitado nas pastas caixas de correio do Exchange Online e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="841b0-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="841b0-211">Você pode começar a usar a descoberta do Cloud app, o Azure AD Connect Health e o SSO para mais de 10 aplicativos.</span><span class="sxs-lookup"><span data-stu-id="841b0-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="841b0-212">Os usuários migrados para o Microsoft 365 E3 não podem mais usar o Gerenciador de clientes do Outlook e o MileIQ.</span><span class="sxs-lookup"><span data-stu-id="841b0-212">Users migrated to Microsoft 365 E3 can no longer use Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="841b0-213">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="841b0-213">Threat protection</span></span>

<span data-ttu-id="841b0-214">O Windows 10 Business inclui estas proteções:</span><span class="sxs-lookup"><span data-stu-id="841b0-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="841b0-215">Aplicação da integridade do processo de inicialização do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="841b0-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="841b0-216">Aplicação de integridade de componentes operacionais confidenciais</span><span class="sxs-lookup"><span data-stu-id="841b0-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="841b0-217">Atenuações de vulnerabilidade avançada e de exploração de dia zero</span><span class="sxs-lookup"><span data-stu-id="841b0-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="841b0-218">Proteção de rede baseada em reputação para o Microsoft Edge, o Internet Explorer e o Chrome</span><span class="sxs-lookup"><span data-stu-id="841b0-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="841b0-219">Firewall baseado em host</span><span class="sxs-lookup"><span data-stu-id="841b0-219">Host-based firewall</span></span>
- <span data-ttu-id="841b0-220">Atenuações de ransomware</span><span class="sxs-lookup"><span data-stu-id="841b0-220">Ransomware mitigations</span></span>
- <span data-ttu-id="841b0-221">Isolamento baseado em hardware para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="841b0-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="841b0-222">Controle de aplicativo equipado com o gráfico de segurança inteligente</span><span class="sxs-lookup"><span data-stu-id="841b0-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="841b0-223">Controle de dispositivo (USB)</span><span class="sxs-lookup"><span data-stu-id="841b0-223">Device control (USB)</span></span>
- <span data-ttu-id="841b0-224">Proteção de rede para ameaças baseadas na Web</span><span class="sxs-lookup"><span data-stu-id="841b0-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="841b0-225">Regras de prevenção de invasão do host</span><span class="sxs-lookup"><span data-stu-id="841b0-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="841b0-226">O Windows 10 Enterprise E3 também inclui o gerenciamento corporativo de isolamento baseado em hardware para o Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="841b0-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="841b0-227">Os usuários migrados para o Microsoft 365 E3 precisarão de uma licença do Office 365 ATP para proteção contínua contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="841b0-227">Users migrated to Microsoft 365 E3 will each require an Office 365 ATP license for continued threat protection.</span></span> <span data-ttu-id="841b0-228">Certifique-se de adquirir licenças adicionais do Office 365 ATP para que todos os usuários no escopo de suas políticas de ATP do Office 365 sejam licenciados.</span><span class="sxs-lookup"><span data-stu-id="841b0-228">Be sure to purchase additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="841b0-229">Gerenciamento de dispositivos com o Intune</span><span class="sxs-lookup"><span data-stu-id="841b0-229">Device management with Intune</span></span>

<span data-ttu-id="841b0-230">Você não precisa fazer alterações na configuração atual do Intune antes de migrar, o que inclui dispositivos registrados e configurações de dispositivo e aplicativo.</span><span class="sxs-lookup"><span data-stu-id="841b0-230">You don’t need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="841b0-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="841b0-231">Windows 10</span></span>

<span data-ttu-id="841b0-232">O Microsoft 365 Business inclui o Windows 10 Business, que você pode instalar com o Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="841b0-232">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="841b0-233">Quando você migra para o Microsoft 365 E3, cada licença de usuário inclui o Windows 10 Enterprise E3, que também pode ser instalado com o Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="841b0-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="841b0-234">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="841b0-234">Office 365 Business</span></span>

<span data-ttu-id="841b0-235">Seu cliente comercial do Office 365 instalado em seus dispositivos começará automaticamente a usar os recursos do Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="841b0-235">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="841b0-236">Após a migração, agora você pode usar:</span><span class="sxs-lookup"><span data-stu-id="841b0-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="841b0-237">Ativação por volume através da diretiva de grupo</span><span class="sxs-lookup"><span data-stu-id="841b0-237">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="841b0-238">Telemetria de aplicativos</span><span class="sxs-lookup"><span data-stu-id="841b0-238">App telemetry</span></span>
 - <span data-ttu-id="841b0-239">Atualizar controles</span><span class="sxs-lookup"><span data-stu-id="841b0-239">Update controls</span></span>
 - <span data-ttu-id="841b0-240">Comparar e consultar planilhas</span><span class="sxs-lookup"><span data-stu-id="841b0-240">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="841b0-241">Business intelligence</span><span class="sxs-lookup"><span data-stu-id="841b0-241">Business intelligence</span></span>

