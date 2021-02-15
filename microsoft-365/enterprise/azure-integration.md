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
description: Integre o Microsoft 365 ao Azure AD se você quiser a sincronização de senha ou o single sign-on com seu ambiente local.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384743"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="1feda-103">Integração do Azure com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1feda-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="1feda-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1feda-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1feda-105">O Microsoft 365 usa o Azure Active Directory (Azure AD) para gerenciar identidades de usuários em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1feda-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="1feda-106">Sua assinatura do Microsoft 365 inclui uma assinatura gratuita do Azure AD para que você possa integrar seus Serviços de Domínio do Active Directory (AD DS) local para sincronizar contas de usuário e senhas ou configurar o single sign-on.</span><span class="sxs-lookup"><span data-stu-id="1feda-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="1feda-107">Você também pode comprar recursos avançados para gerenciar melhor suas contas.</span><span class="sxs-lookup"><span data-stu-id="1feda-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="1feda-108">O Azure AD também oferece outras funcionalidades, como o gerenciamento de aplicativos integrados, que você pode usar para estender e personalizar suas assinaturas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1feda-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="1feda-109">Você pode usar os consultores de implantação do Azure AD para uma experiência guiada de configuração e configuração no Centro de administração do Microsoft 365 (você deve estar integrado ao Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="1feda-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="1feda-110">Consultor do Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="1feda-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="1feda-111">Consultor de implantação do AD FS</span><span class="sxs-lookup"><span data-stu-id="1feda-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="1feda-112">Guia de configuração do Azure AD</span><span class="sxs-lookup"><span data-stu-id="1feda-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="1feda-113">Edições do Azure AD e gerenciamento de identidades do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1feda-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="1feda-114">Se você tiver uma assinatura paga do Microsoft 365, também terá uma assinatura gratuita do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1feda-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="1feda-115">Você pode usar o Azure AD para criar e gerenciar contas de usuários e grupos.</span><span class="sxs-lookup"><span data-stu-id="1feda-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="1feda-116">Para ativar essa assinatura, você precisa concluir um registro único.</span><span class="sxs-lookup"><span data-stu-id="1feda-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="1feda-117">Depois, você pode acessar o Azure AD no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1feda-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="1feda-118">Para obter instruções para registrar sua assinatura gratuita do Azure AD, confira usar sua assinatura gratuita do [Azure AD.](../compliance/use-your-free-azure-ad-subscription-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="1feda-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="1feda-119">Não vá diretamente para azure.microsoft.com se inscrever ou você acabará com uma assinatura de avaliação ou paga do Microsoft Azure que é separada da sua assinatura gratuita do Azure AD com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1feda-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="1feda-120">Com a assinatura gratuita, você pode sincronizar com diretórios locais, configurar o single sign-on e sincronizar com muitos softwares como aplicativos de serviço, como Salesforce, DropBox e muito mais.</span><span class="sxs-lookup"><span data-stu-id="1feda-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="1feda-121">Se quiser uma funcionalidade aprimorada do AD DS, sincronização bi-direcional e outros recursos de gerenciamento, você pode atualizar sua assinatura gratuita para uma assinatura premium paga.</span><span class="sxs-lookup"><span data-stu-id="1feda-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="1feda-122">Para saber mais, confira [as edições do Azure Active Directory.](https://azure.microsoft.com/pricing/details/active-directory/)</span><span class="sxs-lookup"><span data-stu-id="1feda-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="1feda-123">Para saber mais sobre o Microsoft 365 e o Azure AD, confira modelos de identidade do [Microsoft 365.](about-microsoft-365-identity.md)</span><span class="sxs-lookup"><span data-stu-id="1feda-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="1feda-124">Estender os recursos do locatário do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1feda-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="1feda-125">**Recurso**</span><span class="sxs-lookup"><span data-stu-id="1feda-125">**Feature**</span></span>|<span data-ttu-id="1feda-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1feda-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1feda-127">Aplicativos integrados</span><span class="sxs-lookup"><span data-stu-id="1feda-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="1feda-128">Você pode conceder acesso a aplicativos individuais aos seus dados do Microsoft 365, como email, calendários, contatos, usuários, grupos, arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="1feda-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="1feda-129">Você também pode autorizar esses aplicativos no nível de administrador global e torná-los disponíveis para toda a empresa registrando os aplicativos no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1feda-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="1feda-130">Para obter mais informações, consulte [Aplicativos integrados e o Azure AD para administradores do Microsoft 365.](integrated-apps-and-azure-ads.md)</span><span class="sxs-lookup"><span data-stu-id="1feda-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="1feda-131">Consulte também [o single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="1feda-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="1feda-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="1feda-132">PowerApps</span></span>  <br/> | <span data-ttu-id="1feda-133">Os aplicativos de energia são aplicativos voltados para dispositivos móveis que podem se conectar às suas fontes de dados existentes, como listas do SharePoint e outros aplicativos de dados.</span><span class="sxs-lookup"><span data-stu-id="1feda-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="1feda-134">Consulte [Criar um PowerApp para obter uma lista no SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) e na página do [PowerApps](https://powerapps.microsoft.com/) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="1feda-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1feda-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="1feda-135">See also</span></span>

[<span data-ttu-id="1feda-136">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1feda-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
