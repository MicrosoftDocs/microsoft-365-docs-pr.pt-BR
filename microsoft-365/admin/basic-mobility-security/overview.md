---
title: Visão geral do Basic Mobility and Security para o Microsoft 365
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
description: Use o Basic Mobility and Security para definir políticas de segurança de dispositivos e regras de acesso.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430057"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="2f86c-103">Visão geral do Basic Mobility and Security para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f86c-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="2f86c-104">Você pode gerenciar e proteger dispositivos móveis quando eles estão conectados à sua organização do Microsoft 365 usando Mobilidade e Segurança Básica.</span><span class="sxs-lookup"><span data-stu-id="2f86c-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="2f86c-105">Dispositivos móveis, como smartphones e tablets, que são usados para acessar o email de trabalho, o calendário, os contatos e documentos tem um papel importante garantir que os funcionários consigam trabalhar a qualquer momento, de praticamente qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="2f86c-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="2f86c-106">Portanto, é fundamental que você ajude a proteger as informações da sua organização quando as pessoas usam dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f86c-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="2f86c-107">Você pode usar o Basic Mobility and Security para definir políticas de segurança de dispositivos e regras de acesso e apagar dispositivos móveis se eles são perdidos ou roubados.</span><span class="sxs-lookup"><span data-stu-id="2f86c-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuração básica de mobilidade e segurança":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="2f86c-109">Que tipos de dispositivos você pode gerenciar?</span><span class="sxs-lookup"><span data-stu-id="2f86c-109">What types of devices can you manage?</span></span>

<span data-ttu-id="2f86c-110">Você pode usar o Basic Mobility and Security para gerenciar vários tipos de dispositivos móveis, como Windows Phone, Android, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="2f86c-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="2f86c-111">Para gerenciar dispositivos móveis usados por pessoas em sua organização, cada pessoa deve ter uma licença aplicável do Microsoft 365 e seu dispositivo deve estar inscrito no Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="2f86c-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="2f86c-112">Para ver o que o Basic Mobility and Security suporta para cada tipo de dispositivo, consulte [Recursos de Mobilidade e Segurança Básica.](capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="2f86c-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="2f86c-113">Etapas de configuração para Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="2f86c-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="2f86c-114">Um administrador global do Microsoft 365 deve concluir as etapas a seguir para ativar e configurar o Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="2f86c-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="2f86c-115">Para obter etapas detalhadas, siga as orientações em [Configurar Mobilidade Básica e Segurança.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="2f86c-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="2f86c-116">Veja um resumo das etapas:</span><span class="sxs-lookup"><span data-stu-id="2f86c-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="2f86c-117">**Etapa 1:** Ative o Basic Mobility and Security seguindo as etapas na  [configuração básica de mobilidade e segurança.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="2f86c-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="2f86c-118">**Etapa 2:** Configurar a Mobilidade Básica e Segurança criando, por exemplo, um certificado APNs para gerenciar dispositivos iOS e adicionando um registro DNS (Sistema de Nomes de Domínio) para seu domínio para dar suporte a telefones Windows.</span><span class="sxs-lookup"><span data-stu-id="2f86c-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="2f86c-119">**Etapa 3:** Crie políticas de dispositivo e aplique-as a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="2f86c-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="2f86c-120">Quando você faz isso, os usuários receberão uma mensagem de registro em seus dispositivos e, quando eles concluirem o registro, seus dispositivos serão restritos pelas políticas que você definiu para eles.</span><span class="sxs-lookup"><span data-stu-id="2f86c-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="2f86c-121">Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança.](enroll-your-mobile-device.md)</span><span class="sxs-lookup"><span data-stu-id="2f86c-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações de política básica de segurança e mobilidade":::

## <a name="device-management-tasks"></a><span data-ttu-id="2f86c-123">Tarefas de gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="2f86c-123">Device management tasks</span></span>

<span data-ttu-id="2f86c-124">Depois de configurar a Mobilidade Básica e Segurança e os usuários registrarem seus dispositivos, você poderá gerenciar os dispositivos, bloquear o acesso ou apagar um dispositivo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2f86c-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="2f86c-125">Para saber mais sobre algumas tarefas comuns de gerenciamento de dispositivos, incluindo onde concluir as tarefas, confira Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel do [Microsoft 365.](manage-enrolled-devices.md)</span><span class="sxs-lookup"><span data-stu-id="2f86c-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="2f86c-126">Outras maneiras de gerenciar dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="2f86c-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="2f86c-127">Se você precisar apenas do gerenciamento de aplicativos móveis (MAM), talvez para pessoas atualizando projetos de trabalho em seus próprios dispositivos, o Intune oferece outra opção além de registrar e gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f86c-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="2f86c-128">Uma assinatura do Intune permite configurar políticas de MAM usando o portal do Azure, mesmo que os dispositivos das pessoas não sejam inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="2f86c-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="2f86c-129">Para obter mais informações, consulte Visão [geral das políticas de proteção de aplicativos.](https://go.microsoft.com/fwlink/?LinkId=2132517)</span><span class="sxs-lookup"><span data-stu-id="2f86c-129">For more info, see [App protection policies overview](https://go.microsoft.com/fwlink/?LinkId=2132517).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f86c-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2f86c-130">Related topics</span></span>

[<span data-ttu-id="2f86c-131">Configurar a Mobilidade Básica e a Segurança</span><span class="sxs-lookup"><span data-stu-id="2f86c-131">Set up Basic Mobility and Security</span></span>](set-up.md)

[<span data-ttu-id="2f86c-132">Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="2f86c-132">Enroll your mobile device using Basic Mobility and Security</span></span>](enroll-your-mobile-device.md)

[<span data-ttu-id="2f86c-133">Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2f86c-133">Manage devices enrolled in Mobile Device Management for Microsoft 365</span></span>](manage-enrolled-devices.md)

[<span data-ttu-id="2f86c-134">Obter detalhes sobre dispositivos gerenciados pela Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="2f86c-134">Get details about devices managed by Basic Mobility and Security</span></span>](get-details-about-managed-devices.md)