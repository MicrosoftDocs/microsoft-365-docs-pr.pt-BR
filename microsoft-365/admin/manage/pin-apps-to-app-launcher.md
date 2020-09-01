---
title: Fixar aplicativos no inicializador de aplicativos dos usuários
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: Como um administrador global, você pode fixar até três aplicativos ao inicializador de aplicativos dos seus usuários.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310870"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="37d72-103">Fixar aplicativos no inicializador de aplicativos dos usuários</span><span class="sxs-lookup"><span data-stu-id="37d72-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="37d72-104">Você pode usar controles no portal do Azure Active Directory para fixar até três aplicativos no Office.com e no inicializador de aplicativos para todos os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="37d72-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="37d72-105">Você também pode organizar grupos de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="37d72-105">You can also organize groups of applications.</span></span> <span data-ttu-id="37d72-106">Qualquer aplicativo adicionado poderá ser posteriormente desafixado pelo usuário a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="37d72-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="37d72-107">Para fixar um aplicativo para seus usuários, você deve ser um administrador de aplicativo em nuvem ou um administrador de aplicativo no Active Directory do Azure ou um administrador global no Office 365.</span><span class="sxs-lookup"><span data-stu-id="37d72-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="37d72-108">Para obter mais informações sobre funções de administrador, consulte [funções de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [funções de administrador no Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="37d72-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="37d72-109">Para obter mais informações sobre o inicializador de aplicativos e o Office.com, consulte [atender ao inicializador de aplicativos](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) e [atualizações para o Office.com e o artigo de blog do inicializador de aplicativos do Office 365](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) .</span><span class="sxs-lookup"><span data-stu-id="37d72-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="37d72-110">Usar o portal do Azure Active Directory para fixar aplicativos</span><span class="sxs-lookup"><span data-stu-id="37d72-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="37d72-111">Vá para o centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="37d72-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="37d72-112">No painel de navegação à esquerda, escolha **Mostrar tudo**e, em **centros de administração**, escolha **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="37d72-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="37d72-113">No **Azure Active Directory**, escolha configurações de usuário de **aplicativos corporativos**  >  **User settings**.</span><span class="sxs-lookup"><span data-stu-id="37d72-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="37d72-114">Na seção **configurações do Office 365** , escolha **Adicionar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="37d72-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="37d72-115">Escolha os aplicativos que você deseja fixar no inicializador de aplicativos dos usuários e, em seguida, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="37d72-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Configurações do Microsoft 365 para fixar aplicativos.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="37d72-117">Fixar um aplicativo personalizado</span><span class="sxs-lookup"><span data-stu-id="37d72-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="37d72-118">A interface do usuário indicará se você precisa adquirir licenças adicionais do Azure AD para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="37d72-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="37d72-119">Para obter mais informações, consulte [preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="37d72-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="37d72-120">No **Azure Active Directory**, escolha **aplicativos corporativos**  >  **novo aplicativo** na parte superior da página **todos os aplicativos** .</span><span class="sxs-lookup"><span data-stu-id="37d72-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="37d72-121">Na página **Adicionar um aplicativo** , escolha **aplicativo não-Galeria** ou **crie seu próprio aplicativo** se estiver na versão de visualização do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="37d72-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="37d72-122">Digite um nome para o aplicativo e, em seguida, atribua usuário na guia **usuários e grupos** .</span><span class="sxs-lookup"><span data-stu-id="37d72-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="37d72-123">Use a guia **Propriedades** para carregar um ícone para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="37d72-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="37d72-124">Para atribuir uma URL ao aplicativo, na guia **logon único** , escolha **vinculado** e digite uma URL.</span><span class="sxs-lookup"><span data-stu-id="37d72-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="37d72-125">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37d72-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="37d72-126">Criar conjuntos de aplicativos</span><span class="sxs-lookup"><span data-stu-id="37d72-126">Create application collections</span></span>

<span data-ttu-id="37d72-127">Você também pode criar conjuntos de aplicativos para os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="37d72-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="37d72-128">Para obter instruções, consulte [criar coleções no portal meus aplicativos no portal do Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span><span class="sxs-lookup"><span data-stu-id="37d72-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>