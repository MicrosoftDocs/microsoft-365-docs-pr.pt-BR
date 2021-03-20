---
title: Integração do Azure com o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: a5efce5d-9c9c-4190-b61b-fd273c1d425f
description: Integre o Microsoft 365 ao Azure AD se quiser sincronização de senha ou um único login com seu ambiente local.
ms.openlocfilehash: f977969634401d59d7598136f9323cb0e37f9ece
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905327"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="4907c-103">Integração do Azure com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4907c-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="4907c-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4907c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4907c-105">O Microsoft 365 usa o Azure Active Directory (Azure AD) para gerenciar identidades de usuários nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="4907c-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="4907c-106">Sua assinatura do Microsoft 365 inclui uma assinatura gratuita do Azure AD para que você possa integrar seus Serviços de Domínio do Active Directory local (AD DS) para sincronizar contas de usuário e senhas ou configurar o logom único.</span><span class="sxs-lookup"><span data-stu-id="4907c-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="4907c-107">Você também pode comprar recursos avançados para gerenciar melhor suas contas.</span><span class="sxs-lookup"><span data-stu-id="4907c-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="4907c-108">O Azure AD também oferece outras funcionalidades, como o gerenciamento de aplicativos integrados, que você pode usar para estender e personalizar suas assinaturas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4907c-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="4907c-109">Você pode usar os consultores de implantação do Azure AD para uma experiência de configuração e configuração guiada no Centro de administração do Microsoft 365 (você deve estar integrado ao Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="4907c-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="4907c-110">Consultor do Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="4907c-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="4907c-111">Consultor de implantação do AD FS</span><span class="sxs-lookup"><span data-stu-id="4907c-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="4907c-112">Guia de configuração do Azure AD</span><span class="sxs-lookup"><span data-stu-id="4907c-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="4907c-113">Edições do Azure AD e gerenciamento de identidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4907c-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="4907c-114">Se você tiver uma assinatura paga do Microsoft 365, também terá uma assinatura gratuita do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4907c-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="4907c-115">Você pode usar o Azure AD para criar e gerenciar contas de usuário e grupo.</span><span class="sxs-lookup"><span data-stu-id="4907c-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="4907c-116">Para ativar essa assinatura, você precisa concluir um registro único.</span><span class="sxs-lookup"><span data-stu-id="4907c-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="4907c-117">Depois, você pode acessar o Azure AD no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4907c-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="4907c-118">Para obter instruções para registrar sua assinatura gratuita do Azure AD, consulte use sua assinatura gratuita [do Azure AD](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4907c-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="4907c-119">Não vá diretamente para azure.microsoft.com se inscrever ou você terminará com uma assinatura de avaliação ou paga para o Microsoft Azure que está separada da sua assinatura gratuita do Azure AD com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4907c-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="4907c-120">Com a assinatura gratuita, você pode sincronizar com diretórios locais, configurar o logor único e sincronizar com muitos softwares como aplicativos de serviço, como Salesforce, DropBox e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4907c-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="4907c-121">Se você quiser funcionalidade aprimorada do AD DS, sincronização bi-direcional e outros recursos de gerenciamento, você pode atualizar sua assinatura gratuita para uma assinatura premium paga.</span><span class="sxs-lookup"><span data-stu-id="4907c-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="4907c-122">Para obter os detalhes, consulte [Edições do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="4907c-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="4907c-123">Para obter mais informações sobre o Microsoft 365 e o Azure AD, consulte Modelos de identidade [do Microsoft 365.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="4907c-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="4907c-124">Estender os recursos do locatário do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4907c-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="4907c-125">**Recurso**</span><span class="sxs-lookup"><span data-stu-id="4907c-125">**Feature**</span></span>|<span data-ttu-id="4907c-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4907c-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4907c-127">Aplicativos integrados</span><span class="sxs-lookup"><span data-stu-id="4907c-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="4907c-128">Você pode conceder acesso a aplicativos individuais aos seus dados do Microsoft 365, como emails, calendários, contatos, usuários, grupos, arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="4907c-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="4907c-129">Você também pode autorizar esses aplicativos no nível de administrador global e torná-los disponíveis para toda a sua empresa registrando os aplicativos no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4907c-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="4907c-130">Para obter mais informações, consulte [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="4907c-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="4907c-131">Consulte [Também Sign-on único](/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="4907c-131">Also see [Single sign-on](/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>  <br/> |
|<span data-ttu-id="4907c-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="4907c-132">PowerApps</span></span>  <br/> | <span data-ttu-id="4907c-133">Os aplicativos de energia são aplicativos voltados para dispositivos móveis que podem se conectar às fontes de dados existentes, como listas do SharePoint e outros aplicativos de dados.</span><span class="sxs-lookup"><span data-stu-id="4907c-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="4907c-134">Consulte [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page for](https://powerapps.microsoft.com/) details.</span><span class="sxs-lookup"><span data-stu-id="4907c-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="4907c-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="4907c-135">See also</span></span>

[<span data-ttu-id="4907c-136">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4907c-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)