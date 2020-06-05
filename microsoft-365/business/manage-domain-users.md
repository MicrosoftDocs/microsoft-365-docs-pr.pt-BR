---
title: Sincronizar usuários do domínio com o Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Sincronizar usuários controlados pelo domínio com o Microsoft 365 for Business.
ms.openlocfilehash: a22e567fa99456b35742fcf40c07193c96c83cf0
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565682"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="496f1-103">Sincronizar usuários do domínio com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="496f1-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="496f1-104">1. preparar para a sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="496f1-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="496f1-105">Antes de sincronizar os usuários e computadores do domínio do Active Directory local, examine [preparar a sincronização de diretório para o Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="496f1-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="496f1-106">Em particular:</span><span class="sxs-lookup"><span data-stu-id="496f1-106">In particular:</span></span>

   - <span data-ttu-id="496f1-107">Verifique se não há duplicatas no diretório para os seguintes atributos: **mail**, **proxyAddresses**e **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="496f1-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="496f1-108">Esses valores devem ser exclusivos e qualquer duplicatas deve ser removida.</span><span class="sxs-lookup"><span data-stu-id="496f1-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="496f1-109">Recomendamos que você configure o atributo **userPrincipalName** (UPN) para cada conta de usuário local para corresponder ao endereço de email principal que corresponde ao usuário licenciado 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="496f1-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="496f1-110">Por exemplo: *Mary.Shelley@contoso.com* em vez de *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="496f1-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="496f1-111">Se o domínio do Active Directory terminar em um sufixo não roteável, como. *local* ou *. LAN*, em vez de um sufixo roteável na Internet, como *. com* ou *. org*, ajuste o sufixo UPN das contas de usuário local primeiro, conforme descrito em [preparar um domínio não roteável para a sincronização de diretórios](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="496f1-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="496f1-112">A **execução IdFix** na etapa quatro (4) abaixo também garantirá que o Active Directory local está pronto para a sincronização de dir.</span><span class="sxs-lookup"><span data-stu-id="496f1-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="496f1-113">2. instalar e configurar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="496f1-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="496f1-114">Para sincronizar os usuários, grupos e contatos do Active Directory local para o Active Directory do Azure, instale o Azure Active Directory Connect e configure a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="496f1-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="496f1-115">No centro de administração, em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> selecionar **configuração** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="496f1-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="496f1-116">Em **entrada e segurança**, escolha **Exibir** em **sincronizar usuários do diretório da sua organização**.</span><span class="sxs-lookup"><span data-stu-id="496f1-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="496f1-117">Na página **sincronizar usuários do diretório da organização** , escolha **introdução**.</span><span class="sxs-lookup"><span data-stu-id="496f1-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="496f1-118">Na primeira etapa, execute IdFix Tool para preparar a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="496f1-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="496f1-119">Siga as etapas do assistente para baixar o Azure AD Connect e usá-lo para sincronizar seus usuários de domínio controlado com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="496f1-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="496f1-120">Confira [Configurar a sincronização de diretórios para o Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="496f1-120">See [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="496f1-121">Ao configurar suas opções para o Azure AD Connect, recomendamos que você habilite a **sincronização de senha**, o **logon único contínuo**e o recurso **write-back de senha** , que também é suportado no Microsoft 365 for Business.</span><span class="sxs-lookup"><span data-stu-id="496f1-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="496f1-122">Há algumas etapas adicionais para o Write-back de senha além da caixa de seleção no Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="496f1-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="496f1-123">Para obter mais informações, consulte [como fazer: configurar o Write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="496f1-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="496f1-124">Se você quiser gerenciar dispositivos Windows 10 associados ao domínio também, confira [habilitar dispositivos Windows 10 associados ao domínio para que sejam gerenciados pelo Microsoft 365 Business Premium](manage-windows-devices.md) para configurar uma associação híbrida do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="496f1-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 