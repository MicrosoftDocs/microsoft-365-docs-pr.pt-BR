---
title: Gerenciar licenças para dispositivos
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Saiba como atribuir licenças a grupos para uso com dispositivos.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: c590c2d47699c4c3cbea4b5145bea9e7c9fc79ec
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535657"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="2e556-103">Gerenciar licenças para dispositivos</span><span class="sxs-lookup"><span data-stu-id="2e556-103">Manage licenses for devices</span></span>

<span data-ttu-id="2e556-104">Se você tiver Microsoft 365 Apps para Grandes Empresas (dispositivo) ou Microsoft 365 Apps para Educação (dispositivo), poderá atribuir licenças a dispositivos usando grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2e556-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="2e556-105">Quando um dispositivo tem uma licença, qualquer pessoa que usa esse dispositivo pode usar Microsoft 365 Apps para Grandes Empresas (anteriormente chamado Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="2e556-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="2e556-106">Por exemplo, digamos que você tenha 20 laptops e tablets usados por pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2e556-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="2e556-107">Quando você atribui uma licença a cada dispositivo, cada pessoa que faz o login em um dos dispositivos usa Microsoft 365 Apps para Grandes Empresas sem a necessidade de sua própria licença.</span><span class="sxs-lookup"><span data-stu-id="2e556-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e556-108">O licenciamento baseado em dispositivo para Microsoft 365 Apps para Grandes Empresas está disponível apenas como uma licença de complemento para alguns clientes comerciais e alguns clientes de educação.</span><span class="sxs-lookup"><span data-stu-id="2e556-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="2e556-109">Para clientes comerciais, a licença é *Microsoft 365 Apps para Grandes Empresas (dispositivo)* e está disponível somente por meio Enterprise Agreement/Enterprise Agreement Assinatura.</span><span class="sxs-lookup"><span data-stu-id="2e556-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="2e556-110">Para clientes de educação, a licença é Microsoft 365 Apps para Educação *(dispositivo)* e está disponível somente por meio do Registro para Soluções de Educação (EES).</span><span class="sxs-lookup"><span data-stu-id="2e556-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="2e556-111">Para obter mais informações, leia a postagem do blog sobre disponibilidade [educacional.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)</span><span class="sxs-lookup"><span data-stu-id="2e556-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="2e556-112">Para disponibilidade comercial, entre em contato com seu representante de conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2e556-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="2e556-113">Para começar, crie um grupo no centro de administração Azure Active Directory e atribua dispositivos ao grupo.</span><span class="sxs-lookup"><span data-stu-id="2e556-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="2e556-114">Para saber mais sobre licenciamento de dispositivos, incluindo requisitos de dispositivo, quais tipos de grupos você pode usar e como configurar o Microsoft 365 Apps para Grandes Empresas para usar o licenciamento de dispositivo, consulte [Licenciamento](/deployoffice/device-based-licensing)baseado em dispositivo para Microsoft 365 Apps para Grandes Empresas .</span><span class="sxs-lookup"><span data-stu-id="2e556-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e556-115">Você deve ser um administrador global para concluir as tarefas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2e556-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="2e556-116">Atribuir licenças a dispositivos</span><span class="sxs-lookup"><span data-stu-id="2e556-116">Assign licenses to devices</span></span>

<span data-ttu-id="2e556-117">Quando você atribui licenças a um grupo, atribui licenças a todos os dispositivos do grupo.</span><span class="sxs-lookup"><span data-stu-id="2e556-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="2e556-118">Você só pode atribuir uma assinatura a qualquer grupo único.</span><span class="sxs-lookup"><span data-stu-id="2e556-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="2e556-119">No centro Microsoft 365 de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="2e556-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="2e556-120">Na página **Licenças,** escolha **Microsoft 365 Apps para Educação (dispositivo)** **ou Microsoft 365 Apps para Grandes Empresas (dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="2e556-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="2e556-121">Na próxima página, escolha uma assinatura e escolha **Atribuir licenças**.</span><span class="sxs-lookup"><span data-stu-id="2e556-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="2e556-122">No painel **Atribuir licenças a** um grupo, comece a digitar um nome de grupo e escolha-o entre os resultados para adicioná-lo à lista.</span><span class="sxs-lookup"><span data-stu-id="2e556-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="2e556-123">Escolha **Atribuir** e, em seguida, **escolha Fechar**.</span><span class="sxs-lookup"><span data-stu-id="2e556-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="2e556-124">Unassign licenses from devices</span><span class="sxs-lookup"><span data-stu-id="2e556-124">Unassign licenses from devices</span></span>

<span data-ttu-id="2e556-125">Quando você desaigna licenças de um grupo, você remove as licenças de todos os dispositivos dentro do grupo.</span><span class="sxs-lookup"><span data-stu-id="2e556-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="2e556-126">Todos os aplicativos e seus dados associados são, em seguida, somente leitura.</span><span class="sxs-lookup"><span data-stu-id="2e556-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="2e556-127">No centro de administração, vá para a página  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenças de</a> Cobrança.</span><span class="sxs-lookup"><span data-stu-id="2e556-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="2e556-128">Na página **Licenças,** escolha **Microsoft 365 Apps para Educação (dispositivo)** **ou Microsoft 365 Apps para Grandes Empresas (dispositivo).**</span><span class="sxs-lookup"><span data-stu-id="2e556-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="2e556-129">Na próxima página, escolha uma assinatura, selecione os três pontos (mais ações) e escolha **Unassign licenses**.</span><span class="sxs-lookup"><span data-stu-id="2e556-129">On the next page, choose a subscription, select the three dots (more actions), and then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="2e556-130">Na caixa **de diálogo Licenças não assinadas,** escolha **Unassign**.</span><span class="sxs-lookup"><span data-stu-id="2e556-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
