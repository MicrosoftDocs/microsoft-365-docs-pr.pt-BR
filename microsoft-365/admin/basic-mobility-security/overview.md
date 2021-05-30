---
title: Visão geral da mobilidade básica e segurança para Microsoft 365
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
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706305"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a><span data-ttu-id="c6851-103">Visão geral da mobilidade básica e segurança para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6851-103">Overview of Basic Mobility and Security for Microsoft 365</span></span>

<span data-ttu-id="c6851-104">Você pode gerenciar e proteger dispositivos móveis quando eles estão conectados à sua organização Microsoft 365 usando o Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="c6851-104">You can manage and secure mobile devices when they're connected to your Microsoft 365 organization by using Basic Mobility and Security.</span></span> <span data-ttu-id="c6851-105">Dispositivos móveis, como smartphones e tablets, que são usados para acessar o email de trabalho, o calendário, os contatos e documentos tem um papel importante garantir que os funcionários consigam trabalhar a qualquer momento, de praticamente qualquer lugar.</span><span class="sxs-lookup"><span data-stu-id="c6851-105">Mobile devices like smartphones and tablets that are used to access work email, calendar, contacts, and documents play a big part in making sure that employees get their work done anytime, from anywhere.</span></span> <span data-ttu-id="c6851-106">Portanto, é fundamental que você ajude a proteger as informações da sua organização quando as pessoas usam dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6851-106">So it’s critical that you help protect your organization's information when people use devices.</span></span> <span data-ttu-id="c6851-107">Você pode usar o Basic Mobility and Security para definir políticas de segurança de dispositivos e regras de acesso e apagar dispositivos móveis se eles são perdidos ou roubados.</span><span class="sxs-lookup"><span data-stu-id="c6851-107">You can use Basic Mobility and Security to set device security policies and access rules, and to wipe mobile devices if they’re lost or stolen.</span></span>

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Instalação básica de mobilidade e segurança":::

## <a name="what-types-of-devices-can-you-manage"></a><span data-ttu-id="c6851-109">Que tipos de dispositivos você pode gerenciar?</span><span class="sxs-lookup"><span data-stu-id="c6851-109">What types of devices can you manage?</span></span>

<span data-ttu-id="c6851-110">Você pode usar o Basic Mobility and Security para gerenciar vários tipos de dispositivos móveis, como Windows Phone, Android, iPhone e iPad.</span><span class="sxs-lookup"><span data-stu-id="c6851-110">You can use Basic Mobility and Security to manage many types of mobile devices like Windows Phone, Android, iPhone, and iPad.</span></span> <span data-ttu-id="c6851-111">Para gerenciar dispositivos móveis usados por pessoas em sua organização, cada pessoa deve ter uma licença Microsoft 365 aplicável e seu dispositivo deve estar inscrito em Mobilidade Básica e Segurança.</span><span class="sxs-lookup"><span data-stu-id="c6851-111">To manage mobile devices used by people in your organization, each person must have an applicable Microsoft 365 license and their device must be enrolled in Basic Mobility and Security.</span></span>

<span data-ttu-id="c6851-112">Para ver o que o Basic Mobility and Security oferece suporte para cada tipo de dispositivo, consulte [Capabilities of Basic Mobility and Security](capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="c6851-112">To see what Basic Mobility and Security supports for each type of device, see [Capabilities of Basic Mobility and Security](capabilities.md).</span></span>

## <a name="setup-steps-for-basic-mobility-and-security"></a><span data-ttu-id="c6851-113">Etapas de instalação para Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="c6851-113">Setup steps for Basic Mobility and Security</span></span>

<span data-ttu-id="c6851-114">Um Microsoft 365 global deve concluir as etapas a seguir para ativar e configurar o Basic Mobility and Security.</span><span class="sxs-lookup"><span data-stu-id="c6851-114">A Microsoft 365 global admin must complete the following steps to activate and set up Basic Mobility and Security.</span></span> <span data-ttu-id="c6851-115">Para obter etapas detalhadas, siga as orientações [em Configurar a Mobilidade Básica e a Segurança.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="c6851-115">For detailed steps, follow the guidance in [Set up Basic Mobility and Security](set-up.md).</span></span> 

<span data-ttu-id="c6851-116">Veja um resumo das etapas:</span><span class="sxs-lookup"><span data-stu-id="c6851-116">Here's a summary of the steps:</span></span>

<span data-ttu-id="c6851-117">**Etapa 1:** Ative a Mobilidade Básica e a Segurança seguindo as etapas  [na configuração de Mobilidade Básica e Segurança.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="c6851-117">**Step 1:** Activate Basic Mobility and Security by following steps in the [Set up Basic Mobility and Security](set-up.md).</span></span>

<span data-ttu-id="c6851-118">**Etapa 2:** Configurar a Mobilidade Básica e a Segurança criando, por exemplo, um certificado APNs para gerenciar dispositivos iOS e adicionar um registro DNS (Sistema de Nomes de Domínio) para seu domínio para dar suporte Windows telefones.</span><span class="sxs-lookup"><span data-stu-id="c6851-118">**Step 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.</span></span>

<span data-ttu-id="c6851-119">**Etapa 3:** Crie políticas de dispositivo e aplique-as a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="c6851-119">**Step 3:** Create device policies and apply them to groups of users.</span></span> <span data-ttu-id="c6851-120">Ao fazer isso, os usuários receberão uma mensagem de registro em seu dispositivo e, quando concluirem o registro, seus dispositivos serão restritos pelas políticas que você definiu para eles.</span><span class="sxs-lookup"><span data-stu-id="c6851-120">When you do this, your users get an enrollment message on their device, and when they've completed enrollment, their devices are restricted by the policies you've set up for them.</span></span> <span data-ttu-id="c6851-121">Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md).</span><span class="sxs-lookup"><span data-stu-id="c6851-121">For more info, see [Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md).</span></span> 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de segurança e mobilidade":::

## <a name="device-management-tasks"></a><span data-ttu-id="c6851-123">Tarefas de gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="c6851-123">Device management tasks</span></span>

<span data-ttu-id="c6851-124">Depois de configurar o Basic Mobility and Security e os usuários registrarem seus dispositivos, você poderá gerenciar os dispositivos, bloquear o acesso ou apagar um dispositivo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="c6851-124">After you've got Basic Mobility and Security set up and your users have enrolled their devices, you can manage the devices, block access, or wipe a device, if necessary.</span></span> <span data-ttu-id="c6851-125">Para saber mais sobre algumas tarefas comuns de gerenciamento de dispositivos, incluindo onde concluir as tarefas, consulte [Manage devices enrolled](manage-enrolled-devices.md)in Mobile Device Management for Microsoft 365 .</span><span class="sxs-lookup"><span data-stu-id="c6851-125">To learn more about some common device management tasks, including where to complete the tasks, see [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).</span></span>

## <a name="other-ways-to-manage-devices-and-apps"></a><span data-ttu-id="c6851-126">Outras maneiras de gerenciar dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="c6851-126">Other ways to manage devices and apps</span></span>

<span data-ttu-id="c6851-127">Se você precisar apenas de gerenciamento de aplicativo móvel (MAM), talvez para pessoas atualizando projetos de trabalho em seus próprios dispositivos, o Intune fornece outra opção além de registrar e gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c6851-127">If you just need mobile app management (MAM), perhaps for people updating work projects on their own devices, Intune provides another option besides enrolling and managing devices.</span></span> <span data-ttu-id="c6851-128">Uma assinatura do Intune permite configurar políticas de MAM usando o portal do Azure, mesmo que os dispositivos das pessoas não sejam inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="c6851-128">An Intune subscription allows you to set up MAM policies by using the Azure portal, even if people's devices aren't enrolled in Intune.</span></span> <span data-ttu-id="c6851-129">Para obter mais informações, consulte [Visão geral das políticas de proteção de aplicativos.](/mem/intune/apps/app-protection-policy)</span><span class="sxs-lookup"><span data-stu-id="c6851-129">For more info, see [App protection policies overview](/mem/intune/apps/app-protection-policy).</span></span>

## <a name="related-content"></a><span data-ttu-id="c6851-130">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="c6851-130">Related content</span></span>

<span data-ttu-id="c6851-131">[Configurar Mobilidade Básica e Segurança](set-up.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="c6851-131">[Set up Basic Mobility and Security](set-up.md) (article)</span></span>\
<span data-ttu-id="c6851-132">[Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="c6851-132">[Enroll your mobile device using Basic Mobility and Security](enroll-your-mobile-device.md) (article)</span></span>\
<span data-ttu-id="c6851-133">[Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel Microsoft 365](manage-enrolled-devices.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="c6851-133">[Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md) (article)</span></span>\
<span data-ttu-id="c6851-134">[Obter detalhes sobre dispositivos gerenciados](get-details-about-managed-devices.md) pela Basic Mobility and Security (artigo)</span><span class="sxs-lookup"><span data-stu-id="c6851-134">[Get details about devices managed by Basic Mobility and Security](get-details-about-managed-devices.md) (article)</span></span>