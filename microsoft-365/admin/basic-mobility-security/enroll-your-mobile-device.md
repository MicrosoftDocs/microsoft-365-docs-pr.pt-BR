---
title: Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança
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
description: Antes de poder usar os serviços do Microsoft 365 com seu dispositivo, talvez seja necessário primeiro inscreva-lo no Basic Mobility and Security para o Microsoft 365.
ms.openlocfilehash: dc5a43b12fce50c9146200a4559fe9b7e6824b18
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877051"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="11f2e-103">Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="11f2e-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="11f2e-104">Usar seu telefone, tablet e outros dispositivos móveis para trabalhar é uma ótima maneira de se manter informado e trabalhar em projetos de negócios enquanto você estiver fora do escritório.</span><span class="sxs-lookup"><span data-stu-id="11f2e-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="11f2e-105">Antes de poder usar os serviços do Microsoft 365 com seu dispositivo, talvez seja necessário primeiro inscreva-lo no Basic Mobility and Security para o Microsoft 365 usando o Portal da Empresa do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="11f2e-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="11f2e-106">As organizações escolhem Mobilidade e Segurança Básica para que os funcionários possam usar seus dispositivos móveis para acessar com segurança emails, calendários e documentos de trabalho enquanto a empresa segura dados importantes e atende aos seus requisitos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="11f2e-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="11f2e-107">Para saber mais, confira [Visão geral do Basic Mobility and Security para o Microsoft 365.](overview.md)</span><span class="sxs-lookup"><span data-stu-id="11f2e-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="11f2e-108">Para obter mais informações, [consulte Quais informações minha organização pode ver ao registrar meu dispositivo?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="11f2e-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="11f2e-109">Ao registrar seu dispositivo no Basic Mobility and Security para o Microsoft 365, talvez seja necessário configurar uma senha, juntamente com a opção para sua organização de trabalho apagar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11f2e-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="11f2e-110">Uma limpeza de dispositivo pode ser realizada no centro de administração do Microsoft 365, por exemplo, para remover todos os dados do dispositivo se a senha for inserida incorretamente muitas vezes ou se os termos de uso não foram quebrados.</span><span class="sxs-lookup"><span data-stu-id="11f2e-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="11f2e-111">Dispositivos suportados</span><span class="sxs-lookup"><span data-stu-id="11f2e-111">Supported devices</span></span>

<span data-ttu-id="11f2e-112">A Mobilidade Básica e Segurança do Microsoft 365 hospedada pelo serviço do Intune funciona com a maioria dos dispositivos móveis, mas não todos.</span><span class="sxs-lookup"><span data-stu-id="11f2e-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="11f2e-113">Os seguintes são suportados com o Basic Mobility and Security:</span><span class="sxs-lookup"><span data-stu-id="11f2e-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="11f2e-114">iOS 10.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="11f2e-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="11f2e-115">Android 4.4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="11f2e-115">Android 4.4 or later</span></span>

- <span data-ttu-id="11f2e-116">Windows 8.1 e Windows 10 (telefone e computador)</span><span class="sxs-lookup"><span data-stu-id="11f2e-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="11f2e-117">Se o dispositivo não estiver listado acima e você precisar usá-lo com Mobilidade Básica e Segurança, entre em contato com o administrador do trabalho ou da escola.</span><span class="sxs-lookup"><span data-stu-id="11f2e-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="11f2e-118">Se você estiver tendo problemas para registrar seu dispositivo, consulte [Solucionar problemas básicos de mobilidade e segurança.](/basic-mobility-security/troubleshoot.md)</span><span class="sxs-lookup"><span data-stu-id="11f2e-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](/basic-mobility-security/troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="11f2e-119">Configurar seu dispositivo móvel com o Intune e a Mobilidade Básica e Segurança</span><span class="sxs-lookup"><span data-stu-id="11f2e-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="11f2e-120">O Portal da Empresa do Intune permite que um dispositivo seja gerenciado pelo Microsoft 365 e mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="11f2e-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="11f2e-121">iPhone ou iPad</span><span class="sxs-lookup"><span data-stu-id="11f2e-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="11f2e-122">Você não poderá enviar e receber emails até concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="11f2e-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="11f2e-123">Vá para a Apple App Store e baixe e instale o Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="11f2e-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="11f2e-124">Para conectar e configurar seu telefone ou tablet iOS com o portal da empresa para o Office 365, confira Configurar o acesso do dispositivo iOS aos [recursos da sua empresa.](https://go.microsoft.com/fwlink/?linkid=875316)</span><span class="sxs-lookup"><span data-stu-id="11f2e-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="11f2e-125">Telefone Ou tablet Android</span><span class="sxs-lookup"><span data-stu-id="11f2e-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="11f2e-126">Você não poderá enviar e receber emails até concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="11f2e-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="11f2e-127">Vá para a Google Play Store e baixe e instale o Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="11f2e-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="11f2e-128">Para conectar e configurar seu telefone Ou tablet Android com o portal da empresa para o Microsoft 365, confira Registrar seu dispositivo [no Portal da Empresa.](https://go.microsoft.com/fwlink/?linkid=875317)</span><span class="sxs-lookup"><span data-stu-id="11f2e-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="11f2e-129">Windows 8.1 e Windows 10</span><span class="sxs-lookup"><span data-stu-id="11f2e-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="11f2e-130">Acesse a Microsoft Store e baixe e instale o Portal da Empresa do Intune</span><span class="sxs-lookup"><span data-stu-id="11f2e-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="11f2e-131">Para conectar e configurar seu telefone Windows ou computador com o portal da empresa para o Microsoft 365, confira o registro de dispositivos Windows no Portal da Empresa do [Intune.](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal)</span><span class="sxs-lookup"><span data-stu-id="11f2e-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="11f2e-132">O que vem a seguir?</span><span class="sxs-lookup"><span data-stu-id="11f2e-132">What's next?</span></span>

<span data-ttu-id="11f2e-133">Depois que seu dispositivo for inscrito no Basic Mobility and Security, você poderá começar a usar os aplicativos do Office em seu dispositivo para trabalhar com email, calendário, contatos e documentos.</span><span class="sxs-lookup"><span data-stu-id="11f2e-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
