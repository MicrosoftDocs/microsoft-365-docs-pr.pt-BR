---
title: Integração do Azure com o Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
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
ms.openlocfilehash: 045760f000abdbf053e09d89b296fbafa4c24786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687470"
---
# <a name="azure-integration-with-microsoft-365"></a><span data-ttu-id="57b74-103">Integração do Azure com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57b74-103">Azure integration with Microsoft 365</span></span>

<span data-ttu-id="57b74-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="57b74-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="57b74-105">O Microsoft 365 usa o Azure Active Directory (Azure AD) para gerenciar as identidades de usuário nos bastidores.</span><span class="sxs-lookup"><span data-stu-id="57b74-105">Microsoft 365 uses Azure Active Directory (Azure AD) to manage user identities behind the scenes.</span></span> <span data-ttu-id="57b74-106">Sua assinatura do Microsoft 365 inclui uma assinatura gratuita do Azure AD para que você possa integrar o Microsoft 365 com o Azure AD se quiser sincronizar senhas ou configurar o logon único com seu ambiente local.</span><span class="sxs-lookup"><span data-stu-id="57b74-106">Your Microsoft 365 subscription includes a free subscription to Azure AD so that you can integrate Microsoft 365 with Azure AD if you want to sync passwords or set up single sign-on with your on-premises environment.</span></span> <span data-ttu-id="57b74-107">Você também pode comprar recursos avançados para gerenciar melhor suas contas.</span><span class="sxs-lookup"><span data-stu-id="57b74-107">You can also buy advanced features to better manage your accounts.</span></span>
  
<span data-ttu-id="57b74-108">O Azure também oferece outras funcionalidades, como gerenciamento de aplicativos integrados, que você pode usar para estender e personalizar suas assinaturas do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57b74-108">Azure also offers other functionality, like managing integrated apps, that you can use to extend and customize your Microsoft 365 subscriptions.</span></span>
  
<span data-ttu-id="57b74-109">Você pode usar os consultores de implantação do Azure AD para uma experiência de instalação e configuração conduzida (você deve estar conectado ao Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="57b74-109">You can use the Azure AD deployment advisors for a guided setup and configuration experience (you must be signed in to Microsoft 365):</span></span>

 - [<span data-ttu-id="57b74-110">Supervisor de conexão do Azure AD</span><span class="sxs-lookup"><span data-stu-id="57b74-110">Azure AD Connect advisor</span></span>](https://aka.ms/aadconnectpwsync)
 - [<span data-ttu-id="57b74-111">Supervisor de implantação do AD FS</span><span class="sxs-lookup"><span data-stu-id="57b74-111">AD FS deployment advisor</span></span>](https://aka.ms/adfsguidance)
 - [<span data-ttu-id="57b74-112">Guia de instalação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="57b74-112">Azure AD setup guide</span></span>](https://aka.ms/aadpguidance)
  
## <a name="azure-ad-editions-and-microsoft-365-identity-management"></a><span data-ttu-id="57b74-113">Edições do Azure Active Directory e gerenciamento de identidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57b74-113">Azure AD editions and Microsoft 365 identity management</span></span>

<span data-ttu-id="57b74-114">Se você tiver uma assinatura paga do Microsoft 365, também terá uma assinatura gratuita do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="57b74-114">If you have a paid subscription to Microsoft 365, you also have a free subscription to Azure AD.</span></span> <span data-ttu-id="57b74-115">Você pode usar o Azure AD para criar e gerenciar contas de usuário e de grupo.</span><span class="sxs-lookup"><span data-stu-id="57b74-115">You can use Azure AD to create and manage user and group accounts.</span></span> <span data-ttu-id="57b74-116">Para ativar esta assinatura, você deve concluir um registro de uma única vez.</span><span class="sxs-lookup"><span data-stu-id="57b74-116">To activate this subscription you have to complete a one-time registration.</span></span> <span data-ttu-id="57b74-117">Depois disso, você pode acessar o Azure AD do seu centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57b74-117">Afterward, you can access Azure AD from your Microsoft 365 admin center.</span></span> 

<span data-ttu-id="57b74-118">Para obter instruções, consulte [usar sua assinatura gratuita do Azure ad](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span><span class="sxs-lookup"><span data-stu-id="57b74-118">For instructions, see [use your free Azure AD subscription](https://go.microsoft.com/fwlink/p/?LinkId=617127).</span></span> <span data-ttu-id="57b74-119">Siga as instruções para registrar a assinatura gratuita do Azure AD que acompanha sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57b74-119">Follow the instructions to register the free Azure AD subscription that comes with your subscription to Microsoft 365.</span></span> <span data-ttu-id="57b74-120">Não vá diretamente para o azure.microsoft.com para se inscrever ou você terminará com uma assinatura de avaliação ou paga para o Microsoft Azure que seja separada do seu gratuito para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57b74-120">Don't go directly to azure.microsoft.com to sign up or you'll end up with a trial or paid subscription to Microsoft Azure that is separate from your free one for Microsoft 365.</span></span> 
  
<span data-ttu-id="57b74-121">Com a assinatura gratuita, você pode sincronizar com os diretórios locais, configurar o logon único e sincronizar com vários softwares como aplicativos de serviço, como Salesforce, DropBox e muito mais.</span><span class="sxs-lookup"><span data-stu-id="57b74-121">With the free subscription you can synchronize with on-premises directories, set up single sign-on, and synchronize with many software as service applications, such as Salesforce, DropBox and many more.</span></span>
  
<span data-ttu-id="57b74-122">Se quiser a funcionalidade avançada dos serviços de domínio do Active Directory (AD DS), a sincronização bidirecional e outros recursos de gerenciamento, você poderá atualizar sua assinatura gratuita para uma assinatura premium paga.</span><span class="sxs-lookup"><span data-stu-id="57b74-122">If you want enhanced Active Directory Domain Services (AD DS) functionality, bi-directional synchronization, and other management capabilities, you can upgrade your free subscription to a paid premium subscription.</span></span> <span data-ttu-id="57b74-123">Para obter detalhes, consulte [Azure Active Directory Editions](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="57b74-123">For details see [Azure Active Directory editions](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>
  
<span data-ttu-id="57b74-124">Para obter mais informações sobre o Microsoft 365 e o Azure AD, consulte [Understanding microsoft 365 Identity e Azure Active Directory](about-microsoft-365-identity.md).</span><span class="sxs-lookup"><span data-stu-id="57b74-124">For more information about Microsoft 365 and Azure AD, see [Understanding Microsoft 365 Identity and Azure Active Directory](about-microsoft-365-identity.md).</span></span>
  
## <a name="extend-the-capabilities-of-your-microsoft-365-tenant"></a><span data-ttu-id="57b74-125">Estenda os recursos do seu locatário do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57b74-125">Extend the capabilities of your Microsoft 365 tenant</span></span>

|<span data-ttu-id="57b74-126">**Recurso**</span><span class="sxs-lookup"><span data-stu-id="57b74-126">**Feature**</span></span>|<span data-ttu-id="57b74-127">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="57b74-127">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="57b74-128">Aplicativos integrados</span><span class="sxs-lookup"><span data-stu-id="57b74-128">Integrated apps</span></span>  <br/> |<span data-ttu-id="57b74-129">Você pode conceder acesso a aplicativos individuais a seus dados do Microsoft 365, como emails, calendários, contatos, usuários, grupos, arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="57b74-129">You can grant individual apps access to your Microsoft 365 data, like mail, calendars, contacts, users, groups, files, and folders.</span></span> <span data-ttu-id="57b74-130">Você também pode autorizar esses aplicativos no nível de administração global e disponibilizá-los para toda a empresa registrando os aplicativos no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="57b74-130">You can also authorize these apps at global admin level and make them available to your entire company by registering the apps in Azure AD.</span></span> <span data-ttu-id="57b74-131">Para obter detalhes [, consulte aplicativos integrados e o Azure ad para administradores do Microsoft 365](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span><span class="sxs-lookup"><span data-stu-id="57b74-131">For details see [Integrated Apps and Azure AD for Microsoft 365 administrators](https://support.office.com/article/cb2250e3-451e-416f-bf4e-363549652c2a).</span></span>  <br/> <span data-ttu-id="57b74-132">Consulte também [logon único para aplicativos](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span><span class="sxs-lookup"><span data-stu-id="57b74-132">Also see [single sign-on to applications](https://go.microsoft.com/fwlink/p/?LinkId=698604).</span></span>  <br/> |
|<span data-ttu-id="57b74-133">PowerApps</span><span class="sxs-lookup"><span data-stu-id="57b74-133">PowerApps</span></span>  <br/> | <span data-ttu-id="57b74-134">Os aplicativos de energia são aplicativos focados para dispositivos móveis que podem se conectar às fontes de dados existentes, como listas do SharePoint e outros aplicativos de dados.</span><span class="sxs-lookup"><span data-stu-id="57b74-134">Power apps are focused apps for mobile devices that can connect to your existing data sources like SharePoint lists, and other data apps.</span></span> <span data-ttu-id="57b74-135">Consulte [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and [PowerApps Page](https://powerapps.microsoft.com/) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="57b74-135">See [Create a PowerApp for a list in SharePoint Online](https://support.office.com/article/9338b2d2-67ac-4b81-8e67-97da27e5e9ab) and [PowerApps page](https://powerapps.microsoft.com/) for details.</span></span>  <br/> |
   
<span data-ttu-id="57b74-136">Saiba mais em [aplicativos integrados e Azure ad para administradores do Microsoft 365](integrated-apps-and-azure-ads.md) e [Galeria de aplicativos do Azure AD e logon único](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span><span class="sxs-lookup"><span data-stu-id="57b74-136">Learn more at [Integrated Apps and Azure AD for Microsoft 365 administrators](integrated-apps-and-azure-ads.md) and [Azure AD application gallery and single-sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on).</span></span>

## <a name="see-also"></a><span data-ttu-id="57b74-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="57b74-137">See also</span></span>

[<span data-ttu-id="57b74-138">Visão geral do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="57b74-138">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)
