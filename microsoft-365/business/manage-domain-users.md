---
title: Sincronizar os usuários do domínio com o Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Sincronizar usuários controlados por domínio com o Microsoft 365 para empresas.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578398"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="034b9-103">Sincronizar os usuários do domínio com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="034b9-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="034b9-104">1. Preparar-se para Sincronização de Diretórios</span><span class="sxs-lookup"><span data-stu-id="034b9-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="034b9-105">Antes de sincronizar seus usuários e computadores do Domínio Local do Active Directory, revise [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="034b9-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="034b9-106">Em particular:</span><span class="sxs-lookup"><span data-stu-id="034b9-106">In particular:</span></span>

   - <span data-ttu-id="034b9-107">Certifique-se de que não existam duplicatas no diretório para os seguintes atributos: **email,** **proxyAddresses** e **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="034b9-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="034b9-108">Esses valores devem ser exclusivos e quaisquer duplicatas devem ser removidas.</span><span class="sxs-lookup"><span data-stu-id="034b9-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="034b9-109">Recomendamos que você configure o **atributo userPrincipalName** (UPN) para cada conta de usuário local para corresponder ao endereço de email principal que corresponde ao usuário licenciado do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="034b9-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="034b9-110">Por exemplo: *mary.shelley@contoso.com* em vez *de mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="034b9-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="034b9-111">Se o domínio do Active Directory terminar em um sufixo não rouável como *.local* ou *.lan*, em vez de um sufixo de tabela de internet como *.com* ou *.org*, ajuste o sufixo UPN das contas de usuário locais primeiro, conforme descrito em [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="034b9-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="034b9-112">O **IdFix** de Executar na etapa quatro (4) abaixo também garantirá que o Active Directory local esteja pronto para sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="034b9-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="034b9-113">2. Instalar e configurar o Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="034b9-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="034b9-114">Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, instale o Azure Active Directory Connect e configurar a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="034b9-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="034b9-115">No centro [de administração,](https://go.microsoft.com/fwlink/p/?linkid=2024339)selecione **Instalação** na nav esquerda.</span><span class="sxs-lookup"><span data-stu-id="034b9-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="034b9-116">Em **Entrar e segurança,** escolha **Exibir** em **Sincronizar usuários no diretório da sua organização.**</span><span class="sxs-lookup"><span data-stu-id="034b9-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="034b9-117">Na página **Sincronizar usuários na página de** diretório da sua organização, escolha **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="034b9-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="034b9-118">Na primeira etapa, execute a ferramenta IdFix para se preparar para a sincronização de diretórios.</span><span class="sxs-lookup"><span data-stu-id="034b9-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="034b9-119">Siga as etapas do assistente para baixar o Azure AD Connect e usá-lo para sincronizar seus usuários controlados pelo domínio com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="034b9-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="034b9-120">Consulte [Configurar a sincronização de diretórios do Microsoft 365](../enterprise/set-up-directory-synchronization.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="034b9-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="034b9-121">Ao configurar suas opções para o Azure AD Connect, recomendamos que você habilita a Sincronização de **Senha,** o Logon Único Contínuo e o recurso de **writeback** de senha, que também é suportado no Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="034b9-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="034b9-122">Há algumas etapas adicionais para write-back de senha além da caixa de seleção no Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="034b9-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="034b9-123">Para obter mais informações, consulte [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="034b9-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="034b9-124">Se você também deseja gerenciar dispositivos Windows 10 ingressados no domínio, consulte [Enable domain-joined Windows 10 devices](manage-windows-devices.md) to be managed by Microsoft 365 Business Premium to set up a hybrid Azure AD Join.</span><span class="sxs-lookup"><span data-stu-id="034b9-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>