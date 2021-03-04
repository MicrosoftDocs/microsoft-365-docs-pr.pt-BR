---
title: Registrar seu dispositivo móvel usando o Basic Mobility and Security
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
description: Antes de poder usar os serviços do Microsoft 365 com seu dispositivo, talvez seja necessário inscredá-lo primeiro no Basic Mobility and Security para o Microsoft 365.
ms.openlocfilehash: 2a9c0bd9faf670d7dca340d3bc4e9f6586bd6b66
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423196"
---
# <a name="enroll-your-mobile-device-using-basic-mobility-and-security"></a><span data-ttu-id="80c57-103">Registrar seu dispositivo móvel usando o Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="80c57-103">Enroll your mobile device using Basic Mobility and Security</span></span>

<span data-ttu-id="80c57-104">Usar seu telefone, tablet e outros dispositivos móveis para trabalhar é uma ótima maneira de se manter informado e trabalhar em projetos de negócios enquanto você está longe do escritório.</span><span class="sxs-lookup"><span data-stu-id="80c57-104">Using your phone, tablet, and other mobile devices for work is a great way to stay informed and work on business projects while you’re away from the office.</span></span> <span data-ttu-id="80c57-105">Antes de poder usar os serviços do Microsoft 365 com seu dispositivo, talvez seja necessário inscredá-lo primeiro no Basic Mobility and Security para o Microsoft 365 usando o Microsoft Intune Company Portal.</span><span class="sxs-lookup"><span data-stu-id="80c57-105">Before you can use Microsoft 365 services with your device, you might need to first enroll it in Basic Mobility and Security for Microsoft 365 using Microsoft Intune Company Portal.</span></span>

<span data-ttu-id="80c57-106">As organizações escolhem Mobilidade Básica e Segurança para que os funcionários possam usar seus dispositivos móveis para acessar com segurança emails, calendários e documentos de trabalho, enquanto a empresa garante dados importantes e atende aos requisitos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="80c57-106">Organizations choose Basic Mobility and Security so that employees can use their mobile devices to securely access work email, calendars, and documents while the business secures important data and meets their compliance requirements.</span></span><span data-ttu-id="80c57-107">Para saber mais, consulte [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span><span class="sxs-lookup"><span data-stu-id="80c57-107"> To learn more, see [Overview of Basic Mobility and Security for Microsoft 365](overview.md).</span></span> <span data-ttu-id="80c57-108">Para obter mais informações, consulte Quais informações minha organização pode [ver ao registrar meu dispositivo?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span><span class="sxs-lookup"><span data-stu-id="80c57-108">For more info, see [What information can my organization see when I enroll my device?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune).</span></span>

>[!IMPORTANT] 
><span data-ttu-id="80c57-109">Ao registrar seu dispositivo no Basic Mobility and Security para o Microsoft 365, talvez seja necessário configurar uma senha, além de permitir que a sua organização de trabalho limpe o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="80c57-109">When you enroll your device in Basic Mobility and Security for Microsoft 365, you might be required to set up a password, together with allowing the option for your work organization to wipe the device.</span></span> <span data-ttu-id="80c57-110">Uma limpeza de dispositivo pode ser executada do Centro de administração do Microsoft 365, por exemplo, para remover todos os dados do dispositivo se a senha for inserida incorretamente muitas vezes ou se os termos de uso estão quebrados.</span><span class="sxs-lookup"><span data-stu-id="80c57-110">A device wipe can be performed from the Microsoft 365 admin center, for example, to remove all data from the device if the password is entered incorrectly too many times or if usage terms are broken.</span></span>

## <a name="supported-devices"></a><span data-ttu-id="80c57-111">Dispositivos suportados</span><span class="sxs-lookup"><span data-stu-id="80c57-111">Supported devices</span></span>

<span data-ttu-id="80c57-112">O Basic Mobility and Security para o Microsoft 365 hospedado pelo serviço do Intune funciona com a maioria, mas não todos os dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="80c57-112">Basic Mobility and Security for Microsoft 365 hosted by the Intune service works with most, but not all, mobile devices.</span></span> <span data-ttu-id="80c57-113">Os seguintes são suportados com Mobilidade Básica e Segurança:</span><span class="sxs-lookup"><span data-stu-id="80c57-113">The following are supported with Basic Mobility and Security:</span></span>

- <span data-ttu-id="80c57-114">iOS 10.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="80c57-114">iOS 10.0 or later</span></span>

- <span data-ttu-id="80c57-115">Android 4.4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="80c57-115">Android 4.4 or later</span></span>

- <span data-ttu-id="80c57-116">Windows 8.1 e Windows 10 (Telefone e computador)</span><span class="sxs-lookup"><span data-stu-id="80c57-116">Windows 8.1 and Windows 10 (Phone and PC)</span></span>

<span data-ttu-id="80c57-117">Se o dispositivo não estiver listado acima e você precisar usá-lo com Mobilidade Básica e Segurança, entre em contato com seu administrador do trabalho ou da escola.</span><span class="sxs-lookup"><span data-stu-id="80c57-117">If your device is not listed above, and you need to use it with Basic Mobility and Security, contact your work or school administrator.</span></span>

>[!TIP]
><span data-ttu-id="80c57-118">Se você estiver com problemas para registrar seu dispositivo, consulte [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="80c57-118">If you're having trouble enrolling your device, see [Troubleshoot Basic Mobility and Security](troubleshoot.md).</span></span>

## <a name="set-up-your-mobile-device-with-intune-and-basic-mobility-and-security"></a><span data-ttu-id="80c57-119">Configurar seu dispositivo móvel com o Intune e o Basic Mobility and Security</span><span class="sxs-lookup"><span data-stu-id="80c57-119">Set up your mobile device with Intune and Basic Mobility and Security</span></span>

<span data-ttu-id="80c57-120">O Portal da Empresa do Intune permite que um dispositivo seja gerenciado pelo Microsoft 365 e Pela Mobilidade Básica e Segurança.</span><span class="sxs-lookup"><span data-stu-id="80c57-120">The Intune Company Portal enables a device to be managed by Microsoft 365 and Basic Mobility and Security.</span></span>

### <a name="iphone-or-ipad"></a><span data-ttu-id="80c57-121">iPhone ou iPad</span><span class="sxs-lookup"><span data-stu-id="80c57-121">iPhone or iPad</span></span>

>[!TIP]
><span data-ttu-id="80c57-122">Você não poderá enviar e receber emails até concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="80c57-122">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="80c57-123">Vá para a Apple App Store e baixe e instale o Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="80c57-123">Go to the Apple App Store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="80c57-124">Para conectar e configurar seu telefone ou tablet iOS com o portal da empresa para o Office 365, consulte Configurar o acesso de dispositivo iOS aos recursos [da sua empresa.](https://go.microsoft.com/fwlink/?linkid=875316)</span><span class="sxs-lookup"><span data-stu-id="80c57-124">To connect and configure your iOS phone or tablet with the Company portal to Office 365, see [Set up iOS device access to your company resources](https://go.microsoft.com/fwlink/?linkid=875316).</span></span>

### <a name="android-phone-or-tablet"></a><span data-ttu-id="80c57-125">Telefone ou tablet Android</span><span class="sxs-lookup"><span data-stu-id="80c57-125">Android phone or tablet</span></span>

>[!TIP]
><span data-ttu-id="80c57-126">Você não poderá enviar e receber emails até concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="80c57-126">You won’t be able to send and receive email until you complete this step.</span></span>

<span data-ttu-id="80c57-127">Acesse a Google Play Store e baixe e instale o Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="80c57-127">Go to the Google Play store, and download and install Intune Company Portal.</span></span>

<span data-ttu-id="80c57-128">Para conectar e configurar seu telefone ou tablet Android com o portal da Empresa para o Microsoft 365, consulte Registrar seu dispositivo [com o Portal da Empresa.](https://go.microsoft.com/fwlink/?linkid=875317)</span><span class="sxs-lookup"><span data-stu-id="80c57-128">To connect and configure your Android phone or tablet with the Company portal to Microsoft 365, see [Enroll your device with Company Portal](https://go.microsoft.com/fwlink/?linkid=875317).</span></span>

### <a name="windows-81-and-windows-10"></a><span data-ttu-id="80c57-129">Windows 8.1 e Windows 10</span><span class="sxs-lookup"><span data-stu-id="80c57-129">Windows 8.1 and Windows 10</span></span>

<span data-ttu-id="80c57-130">Vá para a Microsoft Store e baixe e instale o Portal da Empresa do Intune</span><span class="sxs-lookup"><span data-stu-id="80c57-130">Go to the Microsoft Store, and download and install Intune Company Portal</span></span>

<span data-ttu-id="80c57-131">Para conectar e configurar seu telefone ou computador Windows com o portal da Empresa para o Microsoft 365, consulte Registro de dispositivos Windows no Portal da Empresa do [Intune](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span><span class="sxs-lookup"><span data-stu-id="80c57-131">To connect and configure your Windows phone or PC with the Company portal to Microsoft 365, see [Windows device enrollment in Intune Company Portal](https://docs.microsoft.com/intune-user-help/windows-enrollment-company-portal).</span></span>

## <a name="whats-next"></a><span data-ttu-id="80c57-132">O que vem a seguir?</span><span class="sxs-lookup"><span data-stu-id="80c57-132">What's next?</span></span>

<span data-ttu-id="80c57-133">Depois que seu dispositivo for inscrito no Basic Mobility and Security, você poderá começar a usar aplicativos do Office em seu dispositivo para trabalhar com email, calendário, contatos e documentos.</span><span class="sxs-lookup"><span data-stu-id="80c57-133">After your device is enrolled in Basic Mobility and Security, you can start using Office apps on your device to work with email, calendar, contacts, and documents.</span></span>
