---
title: Gerenciar licenças para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Saiba como atribuir licenças a grupos para uso com dispositivos.
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826274"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="7c176-103">Gerenciar licenças para dispositivos</span><span class="sxs-lookup"><span data-stu-id="7c176-103">Manage licenses for devices</span></span>

<span data-ttu-id="7c176-104">Se você tiver o Office 365 ProPlus (dispositivo) ou o Office 365 ProPlus for Education (dispositivo), poderá atribuir licenças aos dispositivos usando os grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7c176-104">If you have Office 365 ProPlus (device) or Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="7c176-105">Quando um dispositivo tem uma licença, qualquer pessoa que use o dispositivo pode usar o Office 365.</span><span class="sxs-lookup"><span data-stu-id="7c176-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="7c176-106">Por exemplo, digamos que você tenha 20 laptops e tablets que são usados por pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7c176-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="7c176-107">Quando você atribui uma licença a cada dispositivo, cada pessoa que faz logon em um dos dispositivos usa o Office 365 sem a necessidade de sua própria licença.</span><span class="sxs-lookup"><span data-stu-id="7c176-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c176-108">O licenciamento baseado em dispositivo para o Office 365 ProPlus está disponível somente como uma licença complementar para alguns clientes do commerical e alguns clientes de educação.</span><span class="sxs-lookup"><span data-stu-id="7c176-108">Device-based licensing for Office 365 ProPlus is available only as an add-on license for some commerical customers and some education customers.</span></span> <span data-ttu-id="7c176-109">Para clientes comerciais, a licença é o *Office 365 ProPlus (dispositivo)* e está disponível apenas por meio da assinatura do Enterprise Agreement/Enterprise Agreement.</span><span class="sxs-lookup"><span data-stu-id="7c176-109">For commercial customers, the license is *Office 365 ProPlus (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="7c176-110">Para clientes de educação, a licença é o *Office 365 ProPlus for Education (Device)* e está disponível apenas por meio do registro de soluções de educação (EES).</span><span class="sxs-lookup"><span data-stu-id="7c176-110">For education customers, the license is *Office 365 ProPlus for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="7c176-111">Para obter mais informações, leia a postagem de blog sobre [disponibilidade de educação](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="7c176-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="7c176-112">Para disponibilidade comercial, entre em contato com seu representante de conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7c176-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="7c176-113">Para começar, você cria um grupo no centro de administração do Azure Active Directory e, em seguida, atribui dispositivos ao grupo.</span><span class="sxs-lookup"><span data-stu-id="7c176-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="7c176-114">Para saber mais sobre licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos podem ser usados e como configurar o Office 365 PROPLUS para usar o licenciamento de dispositivos, consulte [Licenciamento baseado em dispositivo para o office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="7c176-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device-based licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7c176-115">Você deve ser um administrador global para concluir as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7c176-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="7c176-116">Atribuir licenças a dispositivos</span><span class="sxs-lookup"><span data-stu-id="7c176-116">Assign licenses to devices</span></span>

<span data-ttu-id="7c176-117">Ao atribuir licenças a um grupo, você atribui licenças a todos os dispositivos do grupo.</span><span class="sxs-lookup"><span data-stu-id="7c176-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="7c176-118">Você só pode atribuir uma assinatura a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="7c176-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="7c176-119">No centro de administração do Microsoft 365, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .</span><span class="sxs-lookup"><span data-stu-id="7c176-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="7c176-120">Na página **licenças** , escolha **Office 365 PROPLUS para educação (dispositivo)** ou **Office ProPlus (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="7c176-120">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="7c176-121">Na próxima página, escolha uma assinatura e, em seguida, escolha **atribuir licenças**.</span><span class="sxs-lookup"><span data-stu-id="7c176-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="7c176-122">No painel **atribuir licenças a um grupo** , comece a digitar o nome de um grupo e, em seguida, escolha-o nos resultados para adicioná-lo à lista.</span><span class="sxs-lookup"><span data-stu-id="7c176-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="7c176-123">Escolha **atribuir**e, em seguida, escolha **fechar**.</span><span class="sxs-lookup"><span data-stu-id="7c176-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="7c176-124">Cancelar a atribuição de licenças de dispositivos</span><span class="sxs-lookup"><span data-stu-id="7c176-124">Unassign licenses from devices</span></span>

<span data-ttu-id="7c176-125">Ao cancelar a atribuição de licenças de um grupo, você remove as licenças de todos os dispositivos do grupo.</span><span class="sxs-lookup"><span data-stu-id="7c176-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="7c176-126">Todos os aplicativos e seus dados associados serão somente leitura.</span><span class="sxs-lookup"><span data-stu-id="7c176-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="7c176-127">No centro de administração, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .</span><span class="sxs-lookup"><span data-stu-id="7c176-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="7c176-128">Na página **licenças** , escolha **Office 365 PROPLUS para educação (dispositivo)** ou **Office ProPlus (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="7c176-128">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="7c176-129">Na próxima página, escolha uma assinatura, escolha **mais ações**e, em seguida, escolha **cancelar a atribuição de licenças**.</span><span class="sxs-lookup"><span data-stu-id="7c176-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="7c176-130">Na caixa de diálogo **cancelar a atribuição de licenças** , escolha **Cancelar atribuição**.</span><span class="sxs-lookup"><span data-stu-id="7c176-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>