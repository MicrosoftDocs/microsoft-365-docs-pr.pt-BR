---
title: Visão geral da mobilidade básica e segurança para o Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Use mobilidade básica e segurança para definir políticas de segurança de dispositivos e regras de acesso.
ms.openlocfilehash: 7c1a4bc5ddf476463788f99305215ee6853190f1
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336702"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="02dc0-103">Visão geral da mobilidade básica e segurança para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02dc0-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="02dc0-104">Você pode gerenciar e proteger dispositivos móveis quando eles estão conectados à sua organização do Microsoft 365 usando mobilidade e segurança básica.</span><span class="sxs-lookup"><span data-stu-id="02dc0-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="02dc0-105">Dispositivos móveis, como smartphones e tablets, que são usados para acessar o email de trabalho, o calendário, os contatos e documentos tem um papel importante garantir que os funcionários consigam trabalhar a qualquer momento, de praticamente qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="02dc0-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="02dc0-106">Portanto, é fundamental que você ajude a proteger as informações da sua organização quando as pessoas usam dispositivos.</span><span class="sxs-lookup"><span data-stu-id="02dc0-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="02dc0-107">Você pode usar mobilidade básica e segurança para definir políticas de segurança de dispositivos e regras de acesso e para apagar dispositivos móveis se eles forem perdidos ou roubados.</span><span class="sxs-lookup"><span data-stu-id="02dc0-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuração básica de segurança e mobilidade":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="02dc0-109">Que tipos de dispositivos você pode gerenciar?</span><span class="sxs-lookup"><span data-stu-id="02dc0-109">What types of devices can you manage?</span></span>

<span data-ttu-id="02dc0-110">Você pode usar mobilidade básica e segurança para gerenciar muitos tipos de dispositivos móveis, como Windows Phone, Android, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="02dc0-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="02dc0-111">Para gerenciar dispositivos móveis usados por pessoas em sua organização, cada pessoa deve ter uma licença do Microsoft 365 aplicável e o dispositivo deve ser inscrito em mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="02dc0-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="02dc0-112">Para ver quais mobilidade e segurança básica dão suporte a cada tipo de dispositivo, consulte [recursos de mobilidade básica e segurança](capabilities-of-basic-mobility-and-secruity.md).</span><span class="sxs-lookup"><span data-stu-id="02dc0-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities-of-basic-mobility-and-secruity.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="02dc0-113">Etapas de configuração para mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="02dc0-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="02dc0-114">Um Microsoft 365 global admin deve concluir as seguintes etapas para ativar e configurar mobilidade e segurança básicas.</span><span class="sxs-lookup"><span data-stu-id="02dc0-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="02dc0-115">Para obter etapas detalhadas, siga as orientações em [Configurar mobilidade e segurança básica](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="02dc0-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span> 

<span data-ttu-id="02dc0-116">Veja um resumo das etapas:</span><span class="sxs-lookup"><span data-stu-id="02dc0-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="02dc0-117">**Etapa 1:** Ative a mobilidade básica e a segurança seguindo as etapas descritas em [Configurar mobilidade básica e segurança](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="02dc0-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>

<span data-ttu-id="02dc0-118">**Etapa 2:** Configurar mobilidade básica e segurança por exemplo, criando um certificado APNs para gerenciar dispositivos iOS e adicionar um registro DNS (sistema de nomes de domínio) para seu domínio para dar suporte a telefones Windows.</span><span class="sxs-lookup"><span data-stu-id="02dc0-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="02dc0-119">**Etapa 3:** Criar políticas de dispositivo e aplicá-las a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="02dc0-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="02dc0-120">Ao fazer isso, os usuários recebem uma mensagem de registro em seus dispositivos e, quando concluíram o registro, seus dispositivos são restritos pelas políticas que você configurou para eles.</span><span class="sxs-lookup"><span data-stu-id="02dc0-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="02dc0-121">Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device-using-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="02dc0-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device-using-basic-mobility-and-security.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de segurança e mobilidade":::

## <a name="device-management-tasks"></a><span data-ttu-id="02dc0-123">Tarefas de gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="02dc0-123">Device management tasks</span></span>

<span data-ttu-id="02dc0-124">Depois que você tiver uma mobilidade básica e uma configuração de segurança e seus usuários tiverem inscrito seus dispositivos, você poderá gerenciar os dispositivos, bloquear o acesso ou apagar um dispositivo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="02dc0-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="02dc0-125">Para saber mais sobre algumas tarefas comuns de gerenciamento de dispositivos, incluindo onde concluir as tarefas, confira [gerenciar dispositivos registrados no gerenciamento de dispositivo móvel para o Microsoft 365](manage-devices-enrolled-in-mdm-in-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="02dc0-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-devices-enrolled-in-mdm-in-microsoft-365.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="02dc0-126">Outras maneiras de gerenciar dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="02dc0-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="02dc0-127">Se você precisar apenas do gerenciamento de aplicativo móvel (MAM), talvez para pessoas que estejam Atualizando projetos de trabalho em seus próprios dispositivos, o Intune fornecerá outra opção além de registrar e gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="02dc0-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="02dc0-128">Uma assinatura do Intune permite que você configure políticas de MAM usando o portal do Azure, mesmo se os dispositivos de pessoas não estiverem registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="02dc0-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="02dc0-129">Para saber mais, confira [visão geral de políticas de proteção de aplicativo](https://go.microsoft.com/fwlink/?LinkId=2132517).</span><span class="sxs-lookup"><span data-stu-id="02dc0-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="02dc0-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="02dc0-130">Related topics</span></span>

[<span data-ttu-id="02dc0-131">Configurar a Mobilidade Básica e a Segurança</span><span class="sxs-lookup"><span data-stu-id="02dc0-131">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)

[<span data-ttu-id="02dc0-132">Registrar seu dispositivo móvel usando mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="02dc0-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device-using-basic-mobility-and-security.md)

[<span data-ttu-id="02dc0-133">Gerenciar dispositivos registrados no gerenciamento de dispositivos móveis para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="02dc0-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-devices-enrolled-in-mdm-in-microsoft-365.md)

[<span data-ttu-id="02dc0-134">Obter detalhes sobre dispositivos gerenciados pela mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="02dc0-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-basic-mobility-and-security-managed-devices.md)