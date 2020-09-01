---
title: Roteiro de gerenciamento de dispositivo para o Microsoft 365
keywords: Microsoft 365, Microsoft 365 para empresas, documentação do Microsoft 365, gerenciamento de dispositivos móveis, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: O roteiro para configurar o gerenciamento de dispositivos para o Microsoft 365.
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315736"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="f8434-104">Roteiro de gerenciamento de dispositivo para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8434-104">Device management roadmap for Microsoft 365</span></span>


<span data-ttu-id="f8434-105">O Microsoft 365 for Enterprise inclui recursos para ajudar a gerenciar dispositivos e seus aplicativos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8434-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="f8434-106">Gerenciar dispositivos móveis ajuda você a proteger e proteger os recursos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8434-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="f8434-107">Há duas opções para o gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f8434-107">There are two options for device management.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="f8434-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f8434-108">Microsoft Intune</span></span>

<span data-ttu-id="f8434-109">O Intune oferece opções para gerenciar o acesso à sua organização usando o gerenciamento de dispositivo móvel (MDM) ou o gerenciamento de aplicativo móvel (MAM).</span><span class="sxs-lookup"><span data-stu-id="f8434-109">Intune gives you options to manage access to your organization using Mobile Device Management (MDM) or Mobile Application Management (MAM).</span></span> <span data-ttu-id="f8434-110">O MDM é quando os usuários "registram" seus dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="f8434-110">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="f8434-111">Após o registro, eles são dispositivos gerenciados e podem receber quaisquer políticas, regras e configurações usadas por sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8434-111">Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="f8434-112">Por exemplo, você pode instalar aplicativos específicos, criar uma diretiva de senha, instalar uma conexão VPN e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f8434-112">For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="f8434-113">Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e suas políticas.</span><span class="sxs-lookup"><span data-stu-id="f8434-113">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your policies.</span></span> <span data-ttu-id="f8434-114">Mas você ainda precisa proteger os recursos e os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f8434-114">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="f8434-115">Neste cenário, você pode proteger seus aplicativos usando MAM.</span><span class="sxs-lookup"><span data-stu-id="f8434-115">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="f8434-116">Por exemplo, você pode usar uma política MAM que exige que um usuário insira um PIN ao acessar o SharePoint no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f8434-116">For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="f8434-117">Você também determinará como vai gerenciar dispositivos pessoais ou pertencentes à organização.</span><span class="sxs-lookup"><span data-stu-id="f8434-117">You'll also determine how you're going to manage personal or organization-owned devices.</span></span> <span data-ttu-id="f8434-118">Você pode querer tratar os dispositivos de forma diferente, dependendo do uso.</span><span class="sxs-lookup"><span data-stu-id="f8434-118">You may want to treat devices differently, depending on their use.</span></span> 

<span data-ttu-id="f8434-119">Inicie [aqui](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="f8434-119">Start [here](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="f8434-120">Mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="f8434-120">Basic Mobility and Security</span></span>
 
<span data-ttu-id="f8434-121">Isso é feito no Microsoft 365 e ajuda você a proteger e gerenciar os dispositivos móveis dos seus usuários, como iPhones, iPads, Androids e Windows phones.</span><span class="sxs-lookup"><span data-stu-id="f8434-121">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="f8434-122">Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f8434-122">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span> 

<span data-ttu-id="f8434-123">Inicie [aqui](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="f8434-123">Start [here](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="f8434-124">Recomendações de acesso de dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="f8434-124">Identity and device access recommendations</span></span>

<span data-ttu-id="f8434-125">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva.</span><span class="sxs-lookup"><span data-stu-id="f8434-125">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="f8434-126">Para acesso ao dispositivo, use as recomendações e configurações nestes artigos:</span><span class="sxs-lookup"><span data-stu-id="f8434-126">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="f8434-127">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f8434-127">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="f8434-128">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="f8434-128">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="f8434-129">Como a contoso fazia o gerenciamento de dispositivos para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8434-129">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="f8434-130">Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou sua infraestrutura de gerenciamento de dispositivo móvel com os](contoso-mdm.md) serviços de nuvem da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8434-130">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>
