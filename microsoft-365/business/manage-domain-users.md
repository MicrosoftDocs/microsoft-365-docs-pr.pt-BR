---
title: Sincronizar os usuários do domínio com o Microsoft 365
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
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841350"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="0a7a0-103">Sincronizar os usuários do domínio com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0a7a0-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="0a7a0-104">1. preparar para a sincronização de diretório</span><span class="sxs-lookup"><span data-stu-id="0a7a0-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="0a7a0-105">Antes de sincronizar os usuários e computadores do domínio do Active Directory local, revise [preparar para a sincronização de diretório para o Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="0a7a0-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="0a7a0-106">Em particular:</span><span class="sxs-lookup"><span data-stu-id="0a7a0-106">In particular:</span></span>

   - <span data-ttu-id="0a7a0-107">Verifique se não há duplicatas no diretório para os seguintes atributos: **mail** , **proxyAddresses** e **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="0a7a0-107">Make sure that no duplicates exist in your directory for the following attributes: **mail** , **proxyAddresses** , and **userPrincipalName** .</span></span> <span data-ttu-id="0a7a0-108">Esses valores devem ser exclusivos e qualquer duplicatas deve ser removida.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="0a7a0-109">Recomendamos que você configure o atributo **userPrincipalName** (UPN) para cada conta de usuário local para corresponder ao endereço de email principal que corresponde ao usuário licenciado 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="0a7a0-110">Por exemplo: *Mary.Shelley@contoso.com* em vez de *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="0a7a0-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="0a7a0-111">Se o domínio do Active Directory terminar em um sufixo não roteável, como. *local* ou *. LAN* , em vez de um sufixo roteável na Internet, como *. com* ou *. org* , ajuste o sufixo UPN das contas de usuário local primeiro, conforme descrito em [preparar um domínio não roteável para a sincronização de diretórios](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="0a7a0-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan* , instead of an internet routable suffix such as *.com* or *.org* , adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="0a7a0-112">A **execução IdFix** na etapa quatro (4) abaixo também garantirá que o Active Directory local está pronto para a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="0a7a0-113">2. instalar e configurar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="0a7a0-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="0a7a0-114">Para sincronizar os usuários, grupos e contatos do Active Directory local para o Active Directory do Azure, instale o Azure Active Directory Connect e configure a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="0a7a0-115">No [centro de administração](https://go.microsoft.com/fwlink/p/?linkid=2024339), selecione **configuração** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="0a7a0-116">Em **entrada e segurança** , escolha **Exibir**  em **sincronizar usuários do diretório da sua organização** .</span><span class="sxs-lookup"><span data-stu-id="0a7a0-116">Under **Sign-in and security** , choose **View**  under **Sync users from your org's directory** .</span></span>

 3. <span data-ttu-id="0a7a0-117">Na página **sincronizar usuários do diretório da organização** , escolha **introdução** .</span><span class="sxs-lookup"><span data-stu-id="0a7a0-117">On the **Sync users from your org's directory** page, choose **Get started** .</span></span>

 4. <span data-ttu-id="0a7a0-118">Na primeira etapa, execute IdFix Tool para preparar a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="0a7a0-119">Siga as etapas do assistente para baixar o Azure AD Connect e usá-lo para sincronizar seus usuários de domínio controlado com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="0a7a0-120">Confira [Configurar a sincronização de diretórios para o Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="0a7a0-121">Ao configurar suas opções para o Azure AD Connect, recomendamos que você habilite a **sincronização de senha** , o **logon único contínuo** e o recurso **write-back de senha** , que também é suportado no Microsoft 365 for Business.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization** , **Seamless Single Sign-On** , and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="0a7a0-122">Há algumas etapas adicionais para o Write-back de senha além da caixa de seleção no Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="0a7a0-123">Para obter mais informações, consulte [como fazer: configurar o Write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="0a7a0-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="0a7a0-124">Se você também quiser gerenciar dispositivos Windows 10 associados ao domínio, confira [habilitar dispositivos Windows 10 associados ao domínio para que sejam gerenciados pelo Microsoft 365 Business Premium](manage-windows-devices.md) para configurar uma associação híbrida do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0a7a0-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 