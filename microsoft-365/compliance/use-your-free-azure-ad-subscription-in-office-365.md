---
title: Usar sua assinatura gratuita do Azure Active Directory no Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: Saiba como acessar o Azure Active Directory, que vem incluído na assinatura paga de sua organização para o Office 365.
ms.openlocfilehash: b8487b245001ffc73b975ed8f756b83e7093b1e7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069209"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="76077-103">Usar sua assinatura gratuita do Azure Active Directory no Office 365</span><span class="sxs-lookup"><span data-stu-id="76077-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="76077-p101">Se sua organização tiver uma assinatura paga do Office 365, do Microsoft Dynamics CRM Online, do Enterprise Mobility Suite ou de outros serviços da Microsoft, você terá uma assinatura gratuita do Microsoft Azure Active Directory. Você e outros administradores podem usar o Azure AD para criar e gerenciar contas de usuário e grupo. Para usar o Azure AD, basta ir ao portal do Azure e entrar usando sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="76077-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="76077-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="76077-107">Before you begin</span></span>

<span data-ttu-id="76077-p102">Use uma sessão de navegação privada (não uma sessão normal) para acessar o portal do Azure (na etapa 1 abaixo) porque isso impedirá que a credencial com a qual você fez logon passe para o Azure. Para abrir uma sessão de Navegação InPrivate no Internet Explorer ou uma sessão de navegação particular no Mozilla FireFox, pressione Ctrl+Shift+P. Para abrir uma sessão de navegação anônima no Google Chrome (chamada de janela anônima), pressione Ctrl+Shift+N.</span><span class="sxs-lookup"><span data-stu-id="76077-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this will prevent the credential that you are currently logged on with from being passed to Azure. To open an InPrivate Browsing session in Internet Explorer or a Private Browsing session in Mozilla FireFox, just press CTRL+SHIFT+P. To open a private browsing session in Google Chrome (called an incognito window), press CTRL+SHIFT+N.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="76077-111">Acessar o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="76077-111">Access Azure Active Directory</span></span>

1. <span data-ttu-id="76077-112">Vá para [portal.azure.com](https://portal.azure.com) e entre com sua conta corporativa ou de estudante do Office 365.</span><span class="sxs-lookup"><span data-stu-id="76077-112">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="76077-113">No painel de navegação à esquerda no portal do Azure, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="76077-113">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![Clique em Azure Active Directory no painel de navegação à esquerda no portal do Azure.](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="76077-115">O Centro de administração do **Azure Active Directory** aparece.</span><span class="sxs-lookup"><span data-stu-id="76077-115">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="76077-116">Mais informações</span><span class="sxs-lookup"><span data-stu-id="76077-116">More information</span></span>

- <span data-ttu-id="76077-117">Uma assinatura gratuita do Azure Active Directory não inclui o relatório de atividade de entrada.</span><span class="sxs-lookup"><span data-stu-id="76077-117">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="76077-118">Para registrar a atividade de entrada (que pode ser útil no caso de um vazamento de dados), você precisa de uma assinatura do Azure Active Directory Premium.</span><span class="sxs-lookup"><span data-stu-id="76077-118">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="76077-119">Para saber mais, consulte [Por quanto tempo o Azure AD armazena os dados?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span><span class="sxs-lookup"><span data-stu-id="76077-119">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="76077-120">Você também pode acessar o centro de administração do **Azure Active Directory** do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76077-120">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="76077-121">No painel de navegação à esquerda do centro de administração do Microsoft 365, clique em **Centros de administração do** \> **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="76077-121">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="76077-122">Confira informações sobre como gerenciar usuários e grupos e realizar outras tarefas de gerenciamento do diretório em [Gerenciar seu diretório do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span><span class="sxs-lookup"><span data-stu-id="76077-122">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
