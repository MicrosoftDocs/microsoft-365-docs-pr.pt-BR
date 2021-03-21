---
title: Roteiro de gerenciamento de dispositivos para Microsoft 365
keywords: Microsoft 365, Microsoft 365 para empresas, documentação do Microsoft 365, gerenciamento de dispositivo móvel, Intune
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
ms.openlocfilehash: 4c37033898865372fea19ddbb53ec9c8586f27b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918961"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="4c0e1-104">Roteiro de gerenciamento de dispositivos para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c0e1-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="4c0e1-105">O Microsoft 365 para empresas inclui recursos para ajudar a gerenciar dispositivos e seus aplicativos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="4c0e1-106">Gerenciar dispositivos móveis ajuda você a proteger e proteger os recursos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="4c0e1-107">Há duas opções para gerenciamento de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="4c0e1-107">There are two options for device management:</span></span>

- [<span data-ttu-id="4c0e1-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4c0e1-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="4c0e1-109">Mobilidade e Segurança Básica</span><span class="sxs-lookup"><span data-stu-id="4c0e1-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="4c0e1-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4c0e1-110">Microsoft Intune</span></span>

<span data-ttu-id="4c0e1-111">Você pode usar o Microsoft Intune para gerenciar o acesso à sua organização usando o gerenciamento de dispositivo móvel ou o gerenciamento de aplicativos móveis.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="4c0e1-112">O gerenciamento de dispositivos móveis é quando os usuários "registram" seus dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="4c0e1-113">Depois que um dispositivo é inscrito, ele é um dispositivo gerenciado; portanto, ele pode receber as políticas, regras e configurações da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="4c0e1-114">Por exemplo, você pode instalar aplicativos específicos, criar uma política de senha, instalar uma conexão VPN e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="4c0e1-115">Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e pelas políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="4c0e1-116">Mas você ainda precisa proteger os recursos e os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="4c0e1-117">Nesse cenário, você pode proteger seus aplicativos usando o gerenciamento de aplicativos móveis.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="4c0e1-118">Por exemplo, você pode usar uma política de gerenciamento de aplicativo móvel que exija que um usuário insira um PIN ao acessar o SharePoint Online no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="4c0e1-119">Você também determinará como gerenciar dispositivos pessoais e dispositivos de propriedade da organização.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="4c0e1-120">Talvez você queira tratar os dispositivos de forma diferente, dependendo de seus usos.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="4c0e1-121">Mobilidade e Segurança Básica</span><span class="sxs-lookup"><span data-stu-id="4c0e1-121">Basic Mobility and Security</span></span>

<span data-ttu-id="4c0e1-122">Isso é integrado ao Microsoft 365 e ajuda você a proteger e gerenciar dispositivos móveis de seus usuários, como iPhones, iPads, Androids e telefones Windows.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="4c0e1-123">Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="4c0e1-124">Escolha entre as duas opções</span><span class="sxs-lookup"><span data-stu-id="4c0e1-124">Choose between the two options</span></span>

<span data-ttu-id="4c0e1-125">Para ajudá-lo a avaliar melhor qual opção de gerenciamento de dispositivo é a melhor para você, consulte [Choose between Basic Mobility Security and Intune](/office365/securitycompliance/choose-between-mdm-and-intune).</span><span class="sxs-lookup"><span data-stu-id="4c0e1-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="4c0e1-126">Com base em sua avaliação, começar a gerenciar seus dispositivos com:</span><span class="sxs-lookup"><span data-stu-id="4c0e1-126">Based on your assessment, get started managing your devices with:</span></span>

- [<span data-ttu-id="4c0e1-127">Intune</span><span class="sxs-lookup"><span data-stu-id="4c0e1-127">Intune</span></span>](/mem/intune/fundamentals/planning-guide)
- [<span data-ttu-id="4c0e1-128">Mobilidade e Segurança Básica</span><span class="sxs-lookup"><span data-stu-id="4c0e1-128">Basic Mobility and Security</span></span>](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="4c0e1-129">Recomendações de acesso de dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="4c0e1-129">Identity and device access recommendations</span></span>

<span data-ttu-id="4c0e1-130">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](../security/office-365-security/microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva.</span><span class="sxs-lookup"><span data-stu-id="4c0e1-130">Microsoft provides a set of recommendations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="4c0e1-131">Para acesso ao dispositivo, use as recomendações e configurações nestes artigos:</span><span class="sxs-lookup"><span data-stu-id="4c0e1-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="4c0e1-132">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4c0e1-132">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="4c0e1-133">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="4c0e1-133">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="4c0e1-134">Como a Contoso fez o gerenciamento de dispositivos para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c0e1-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="4c0e1-135">Para obter informações sobre como uma empresa multi-nacional fictícia, mas representativa, implantou sua infraestrutura de gerenciamento de dispositivo móvel com os serviços de nuvem do Microsoft 365, consulte Gerenciamento de [dispositivos móveis para Contoso](contoso-mdm.md).</span><span class="sxs-lookup"><span data-stu-id="4c0e1-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>