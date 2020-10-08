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
description: Integre o Microsoft 365 com o Azure AD se você quiser sincronização de senha ou logon único com seu ambiente local.
ms.openlocfilehash: b1f20ebc692421ed6df0d6f7c31a4d80347133e3
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384743"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="394fc-103">Integração do Azure com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="394fc-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="394fc-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="394fc-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="394fc-105">O Microsoft 365 usa o Azure Active Directory (Azure AD) para gerenciar as identidades de usuário nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="394fc-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="394fc-106">Sua assinatura do Microsoft 365 inclui uma assinatura gratuita do Azure AD para que você possa integrar seus serviços de domínio do Active Directory (AD DS) local para sincronizar contas de usuário e senhas ou configurar o logon único.</span><span class="sxs-lookup"><span data-stu-id="394fc-106">Your Microsoft 365 subscription includes a free Azure AD subscription so that you can integrate your on-premises Active Directory Domain Services (AD DS) to synchronize user accounts and passwords or set up single sign-on.</span></span> <span data-ttu-id="394fc-107">Você também pode adquirir recursos avançados para gerenciar melhor suas contas.</span><span class="sxs-lookup"><span data-stu-id="394fc-107">You can also purchase advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="394fc-108">O Azure AD também oferece outras funcionalidades, como gerenciar aplicativos integrados, que você pode usar para estender e personalizar suas assinaturas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="394fc-108">Azure AD also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="394fc-109">Você pode usar os consultores de implantação do Azure AD para uma experiência de instalação e configuração orientada no centro de administração do Microsoft 365 (você deve estar conectado ao Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="394fc-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience in the Microsoft 365 admin center (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="394fc-110">Supervisor de conexão do Azure AD</span><span class="sxs-lookup"><span data-stu-id="394fc-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="394fc-111">Supervisor de implantação do AD FS</span><span class="sxs-lookup"><span data-stu-id="394fc-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="394fc-112">Guia de instalação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="394fc-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="394fc-113">Edições do Azure Active Directory e gerenciamento de identidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="394fc-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="394fc-114">Se você tiver uma assinatura paga do Microsoft 365, também terá uma assinatura gratuita do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="394fc-114">If you have a paid subscription to Microsoft 365, you also have a free Azure AD subscription.</span></span> <span data-ttu-id="394fc-115">Você pode usar o Azure AD para criar e gerenciar contas de usuário e de grupo.</span><span class="sxs-lookup"><span data-stu-id="394fc-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="394fc-116">Para ativar essa assinatura, você deve concluir um registro de uma única vez.</span><span class="sxs-lookup"><span data-stu-id="394fc-116">To activate this subscription, you have to complete a one-time registration.</span></span> <span data-ttu-id="394fc-117">Depois disso, você pode acessar o Azure AD do seu centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="394fc-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="394fc-118">Para obter instruções para registrar sua assinatura gratuita do Azure AD, confira [usar sua assinatura gratuita do Azure ad](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="394fc-118">For instructions to register your free Azure AD subscription, see [use your free Azure AD subscription](../compliance/use-your-free-azure-ad-subscription-in-office-365.md).</span></span> <span data-ttu-id="394fc-119">Não vá diretamente para o azure.microsoft.com para se inscrever ou você terminará com uma assinatura de avaliação ou paga para o Microsoft Azure separada da sua assinatura gratuita do Azure AD com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="394fc-119">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free Azure AD subscription with Microsoft 365.</span></span> 
  
<span data-ttu-id="394fc-120">Com a assinatura gratuita, você pode sincronizar com os diretórios locais, configurar o logon único e sincronizar com vários softwares como aplicativos de serviço, como Salesforce, DropBox e muito mais.</span><span class="sxs-lookup"><span data-stu-id="394fc-120">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox, and many more.</span></span>
  
<span data-ttu-id="394fc-121">Se quiser uma funcionalidade avançada do AD DS, uma sincronização bidirecional e outros recursos de gerenciamento, você poderá atualizar sua assinatura gratuita para uma assinatura premium paga.</span><span class="sxs-lookup"><span data-stu-id="394fc-121">If you want enhanced AD DS functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="394fc-122">Para obter detalhes, consulte [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="394fc-122">For the details, see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="394fc-123">Para obter mais informações sobre o Microsoft 365 e o Azure AD, consulte [microsoft 365 Identity Models](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="394fc-123">For more information about Microsoft 365 and Azure AD, see [Microsoft 365 identity models](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="394fc-124">Estenda os recursos do seu locatário do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="394fc-124">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="394fc-125">**Recurso**</span><span class="sxs-lookup"><span data-stu-id="394fc-125">**Feature**</span></span>|<span data-ttu-id="394fc-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="394fc-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="394fc-127">Aplicativos integrados</span><span class="sxs-lookup"><span data-stu-id="394fc-127">Integrated apps</span></span>  <br/> |<span data-ttu-id="394fc-128">Você pode conceder acesso a aplicativos individuais a seus dados do Microsoft 365, como emails, calendários, contatos, usuários, grupos, arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="394fc-128">You can grant individual apps access to your Microsoft 365 data, such as mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="394fc-129">Você também pode autorizar esses aplicativos no nível de administração global e disponibilizá-los para toda a empresa registrando os aplicativos no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="394fc-129">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="394fc-130">Formore informações, consulte [aplicativos integrados e o Azure ad para administradores do Microsoft 365](integrated-apps-and-azure-ads.md).</span><span class="sxs-lookup"><span data-stu-id="394fc-130">Formore information, see [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md).</span></span>  <br/> <span data-ttu-id="394fc-131">Confira também o [logon único](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="394fc-131">Also see [Single sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="394fc-132">PowerApps</span><span class="sxs-lookup"><span data-stu-id="394fc-132">PowerApps</span></span>  <br/> | <span data-ttu-id="394fc-133">Os aplicativos de energia são aplicativos focados para dispositivos móveis que podem se conectar às fontes de dados existentes, como listas do SharePoint e outros aplicativos de dados.</span><span class="sxs-lookup"><span data-stu-id="394fc-133">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists and other data apps.</span></span> <span data-ttu-id="394fc-134">Confira [criar um PowerApp para uma lista no SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) e na [página do PowerApps](https://powerapps.microsoft.com/) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="394fc-134">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and the [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="394fc-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="394fc-135">See also</span></span>

[<span data-ttu-id="394fc-136">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="394fc-136">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
