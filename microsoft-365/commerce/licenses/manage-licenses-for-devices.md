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
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237348"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="19813-103">Gerenciar licenças para dispositivos</span><span class="sxs-lookup"><span data-stu-id="19813-103">Manage licenses for devices</span></span>

<span data-ttu-id="19813-104">Se você tiver o Office 365 ProPlus for Education (dispositivo), poderá atribuir licenças aos dispositivos usando grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="19813-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="19813-105">Quando um dispositivo tem uma licença, qualquer pessoa que use o dispositivo pode usar o Office 365.</span><span class="sxs-lookup"><span data-stu-id="19813-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="19813-106">Por exemplo, digamos que você tenha 20 laptops e tablets que são usados por pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="19813-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="19813-107">Quando você atribui uma licença a cada dispositivo, cada pessoa que faz logon em um dos dispositivos usa o Office 365 sem a necessidade de sua própria licença.</span><span class="sxs-lookup"><span data-stu-id="19813-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19813-108">O Office 365 ProPlus for Education (dispositivo) só está disponível para os clientes de licenciamento por volume a3 e a5.</span><span class="sxs-lookup"><span data-stu-id="19813-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="19813-109">Para começar, você cria um grupo no centro de administração do Azure Active Directory e, em seguida, atribui dispositivos ao grupo.</span><span class="sxs-lookup"><span data-stu-id="19813-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="19813-110">Para saber mais sobre licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos podem ser usados e como configurar o Office 365 PROPLUS para usar o licenciamento de dispositivos, consulte [Device Licensing for Office 365 ProPlus for Education Customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="19813-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19813-111">Você deve ser um administrador global para concluir as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="19813-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="19813-112">Atribuir licenças a dispositivos</span><span class="sxs-lookup"><span data-stu-id="19813-112">Assign licenses to devices</span></span>

<span data-ttu-id="19813-113">Ao atribuir licenças a um grupo, você atribui licenças a todos os dispositivos do grupo.</span><span class="sxs-lookup"><span data-stu-id="19813-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="19813-114">Você só pode atribuir uma assinatura a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="19813-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="19813-115">No centro de administração do Microsoft 365, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .</span><span class="sxs-lookup"><span data-stu-id="19813-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="19813-116">Na página **licenças** , escolha **Office 365 PROPLUS para educação (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="19813-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="19813-117">Na página **Office 365 ProPlus for Education (dispositivo)** , escolha uma assinatura e, em seguida, escolha **atribuir licenças**.</span><span class="sxs-lookup"><span data-stu-id="19813-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="19813-118">No painel **atribuir licenças a um grupo** , comece a digitar o nome de um grupo e, em seguida, escolha-o nos resultados para adicioná-lo à lista.</span><span class="sxs-lookup"><span data-stu-id="19813-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="19813-119">Escolha **atribuir**e, em seguida, escolha **fechar**.</span><span class="sxs-lookup"><span data-stu-id="19813-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="19813-120">Cancelar a atribuição de licenças de dispositivos</span><span class="sxs-lookup"><span data-stu-id="19813-120">Unassign licenses from devices</span></span>

<span data-ttu-id="19813-121">Ao cancelar a atribuição de licenças de um grupo, você remove as licenças de todos os dispositivos do grupo.</span><span class="sxs-lookup"><span data-stu-id="19813-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="19813-122">Todos os aplicativos e seus dados associados serão somente leitura.</span><span class="sxs-lookup"><span data-stu-id="19813-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="19813-123">No centro de administração, vá para a página<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenças</a> de **cobrança** > .</span><span class="sxs-lookup"><span data-stu-id="19813-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="19813-124">Na página **licenças** , escolha **Office 365 PROPLUS para educação (dispositivo)**.</span><span class="sxs-lookup"><span data-stu-id="19813-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="19813-125">Na página **Office 365 ProPlus for Education (dispositivo)** , escolha uma assinatura, escolha **mais ações**e, em seguida, escolha **Cancelar atribuição de licenças**.</span><span class="sxs-lookup"><span data-stu-id="19813-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="19813-126">Na caixa de diálogo **cancelar a atribuição de licenças** , escolha **Cancelar atribuição**.</span><span class="sxs-lookup"><span data-stu-id="19813-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>