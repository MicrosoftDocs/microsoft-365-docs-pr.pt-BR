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
ms.openlocfilehash: 0efe7098f90064184f222acb671ae6f96c1b38d5
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384760"
---
# <a name="device-management-roadmap-for-microsoft-365"></a><span data-ttu-id="6aa06-104">Roteiro de gerenciamento de dispositivo para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6aa06-104">Device management roadmap for Microsoft 365</span></span>

<span data-ttu-id="6aa06-105">O Microsoft 365 for Enterprise inclui recursos para ajudar a gerenciar dispositivos e seus aplicativos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6aa06-105">Microsoft 365 for enterprise includes features to help manage devices, and their apps, within your organization.</span></span> <span data-ttu-id="6aa06-106">Gerenciar dispositivos móveis ajuda você a proteger e proteger os recursos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6aa06-106">Managing mobile devices helps you secure and protect your organization's resources.</span></span>

<span data-ttu-id="6aa06-107">Há duas opções para o gerenciamento de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="6aa06-107">There are two options for device management:</span></span>

- [<span data-ttu-id="6aa06-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6aa06-108">Microsoft Intune</span></span>](#microsoft-intune)
- [<span data-ttu-id="6aa06-109">Mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="6aa06-109">Basic Mobility and Security</span></span>](#basic-mobility-and-security)

## <a name="microsoft-intune"></a><span data-ttu-id="6aa06-110">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6aa06-110">Microsoft Intune</span></span>

<span data-ttu-id="6aa06-111">Você pode usar o Microsoft Intune para gerenciar o acesso à sua organização usando o gerenciamento de dispositivos móveis ou o gerenciamento de aplicativos móveis.</span><span class="sxs-lookup"><span data-stu-id="6aa06-111">You can use Microsoft Intune to manage access to your organization using mobile device management or mobile application management.</span></span> <span data-ttu-id="6aa06-112">O gerenciamento de dispositivos móveis é quando os usuários "registram" seus dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="6aa06-112">Mobile device management is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="6aa06-113">Após um dispositivo ser inscrito, é um dispositivo gerenciado; Portanto, ele pode receber as políticas, as regras e as configurações da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6aa06-113">After a device is enrolled, it is a managed device; therefore, it can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="6aa06-114">Por exemplo, você pode instalar aplicativos específicos, criar uma política de senha, instalar uma conexão VPN e muito mais.</span><span class="sxs-lookup"><span data-stu-id="6aa06-114">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="6aa06-115">Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e pelas políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6aa06-115">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="6aa06-116">Mas você ainda precisa proteger os recursos e os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6aa06-116">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="6aa06-117">Neste cenário, você pode proteger seus aplicativos usando o gerenciamento de aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="6aa06-117">In this scenario, you can protect your apps using mobile application management.</span></span> <span data-ttu-id="6aa06-118">Por exemplo, você pode usar uma política de gerenciamento de aplicativo móvel que exige que um usuário insira um PIN ao acessar o SharePoint Online no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6aa06-118">For example, you can use a mobile application management policy that requires a user to enter a PIN when accessing SharePoint Online on the device.</span></span>

<span data-ttu-id="6aa06-119">Você também determinará como você vai gerenciar dispositivos pessoais e dispositivos de propriedade da organização.</span><span class="sxs-lookup"><span data-stu-id="6aa06-119">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="6aa06-120">Você pode querer tratar os dispositivos de forma diferente, dependendo de seus usos.</span><span class="sxs-lookup"><span data-stu-id="6aa06-120">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="basic-mobility-and-security"></a><span data-ttu-id="6aa06-121">Mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="6aa06-121">Basic Mobility and Security</span></span>

<span data-ttu-id="6aa06-122">Isso é feito no Microsoft 365 e ajuda você a proteger e gerenciar os dispositivos móveis dos seus usuários, como iPhones, iPads, Androids e Windows phones.</span><span class="sxs-lookup"><span data-stu-id="6aa06-122">This is built into Microsoft 365 and helps you secure and manage your users' mobile devices like iPhones, iPads, Androids, and Windows phones.</span></span> <span data-ttu-id="6aa06-123">Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6aa06-123">You can create and manage device security policies, remotely wipe a device, and view detailed device reports.</span></span>

## <a name="choose-between-the-two-options"></a><span data-ttu-id="6aa06-124">Escolha entre as duas opções</span><span class="sxs-lookup"><span data-stu-id="6aa06-124">Choose between the two options</span></span>

<span data-ttu-id="6aa06-125">Para ajudá-lo a avaliar melhor qual opção de gerenciamento de dispositivos é melhor para você, consulte [escolher entre a segurança de mobilidade básica e o Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span><span class="sxs-lookup"><span data-stu-id="6aa06-125">To help you better assess which device management option is best for you, see [Choose between Basic Mobility Security and Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).</span></span>

<span data-ttu-id="6aa06-126">Com base em sua avaliação, comece a gerenciar seus dispositivos com:</span><span class="sxs-lookup"><span data-stu-id="6aa06-126">Based on your assessment, get started managing your devices with:</span></span>

- <span data-ttu-id="6aa06-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span><span class="sxs-lookup"><span data-stu-id="6aa06-127">[Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).</span></span>
- <span data-ttu-id="6aa06-128">[Mobilidade básica e segurança](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span><span class="sxs-lookup"><span data-stu-id="6aa06-128">[Basic Mobility and Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).</span></span>
 
## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="6aa06-129">Recomendações de acesso de dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="6aa06-129">Identity and device access recommendations</span></span>

<span data-ttu-id="6aa06-130">A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva.</span><span class="sxs-lookup"><span data-stu-id="6aa06-130">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="6aa06-131">Para acesso ao dispositivo, use as recomendações e configurações nestes artigos:</span><span class="sxs-lookup"><span data-stu-id="6aa06-131">For device access, use the recommendations and settings in these articles:</span></span>

- [<span data-ttu-id="6aa06-132">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="6aa06-132">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="6aa06-133">Identidade comum e políticas de acesso ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="6aa06-133">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a><span data-ttu-id="6aa06-134">Como a contoso fazia o gerenciamento de dispositivos para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6aa06-134">How Contoso did device management for Microsoft 365</span></span>

<span data-ttu-id="6aa06-135">Para obter informações sobre como uma empresa multinacional fictícia, mas representativa, implantou sua infraestrutura de gerenciamento de dispositivo móvel com os serviços de nuvem da Microsoft 365, consulte [Mobile Device Management for contoso](contoso-mdm.md).</span><span class="sxs-lookup"><span data-stu-id="6aa06-135">For information about how a fictional but representative multi-national business deployed their mobile device management infrastructure with Microsoft 365 cloud services, see [Mobile device management for Contoso](contoso-mdm.md).</span></span>
