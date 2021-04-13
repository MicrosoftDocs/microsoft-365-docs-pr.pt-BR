---
title: Microsoft Defender ATP para Android - Informações de privacidade
description: Controles de privacidade, como configurar configurações de política que impactam a privacidade e informações sobre os dados de diagnóstico coletados no Microsoft Defender ATP para Android.
keywords: microsoft, defender, atp, android, privacidade, diagnóstico
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d38d7a54aa860049e1968e5b92c801107bea0514
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687956"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a><span data-ttu-id="eaf57-104">Microsoft Defender para Ponto de Extremidade no Android - Informações de privacidade</span><span class="sxs-lookup"><span data-stu-id="eaf57-104">Microsoft Defender for Endpoint on Android - Privacy information</span></span>

<span data-ttu-id="eaf57-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="eaf57-105">**Applies to:**</span></span>
- [<span data-ttu-id="eaf57-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="eaf57-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eaf57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eaf57-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eaf57-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="eaf57-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eaf57-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="eaf57-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="eaf57-110">O Defender for Endpoint para Android coleta informações de seus dispositivos Android configurados e as armazena no mesmo locatário onde você tem o Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="eaf57-110">Defender for Endpoint for Android collects information from your configured Android devices and stores it in the same tenant where you have Defender for Endpoint.</span></span>

<span data-ttu-id="eaf57-111">As informações são coletadas para ajudar a manter o Defender for Endpoint para Android seguro, atualizado, executando conforme esperado e para dar suporte ao serviço.</span><span class="sxs-lookup"><span data-stu-id="eaf57-111">Information is collected to help keep Defender for Endpoint for Android secure, up-to-date, performing as expected and to support the service.</span></span>

## <a name="required-data"></a><span data-ttu-id="eaf57-112">Dados Necessários</span><span class="sxs-lookup"><span data-stu-id="eaf57-112">Required Data</span></span> 

<span data-ttu-id="eaf57-113">Os dados necessários consistem em dados necessários para que o Defender for Endpoint para Android funcione conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="eaf57-113">Required data consists of data that is necessary to make Defender for Endpoint for Android work as expected.</span></span> <span data-ttu-id="eaf57-114">Esses dados são essenciais para a operação do serviço e podem incluir dados relacionados ao usuário final, organização, dispositivo e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="eaf57-114">This data is essential to the operation of the service and can include data related to the end user, organization, device, and apps.</span></span> <span data-ttu-id="eaf57-115">Aqui está uma lista dos tipos de dados que estão sendo coletados:</span><span class="sxs-lookup"><span data-stu-id="eaf57-115">Here's a list of the types of data being collected:</span></span>

### <a name="app-information"></a><span data-ttu-id="eaf57-116">Informações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="eaf57-116">App information</span></span>

<span data-ttu-id="eaf57-117">Informações sobre pacotes de aplicativos Android (APKs) no dispositivo, incluindo</span><span class="sxs-lookup"><span data-stu-id="eaf57-117">Information about Android application packages (APKs) on the device including</span></span>

-  <span data-ttu-id="eaf57-118">Instalar origem</span><span class="sxs-lookup"><span data-stu-id="eaf57-118">Install source</span></span>
-  <span data-ttu-id="eaf57-119">Local de armazenamento (caminho do arquivo) do APK</span><span class="sxs-lookup"><span data-stu-id="eaf57-119">Storage location (file path) of the APK</span></span>
-  <span data-ttu-id="eaf57-120">Hora da instalação, tamanho do APK e permissões</span><span class="sxs-lookup"><span data-stu-id="eaf57-120">Time of install, size of APK and permissions</span></span>

### <a name="web-page--network-information"></a><span data-ttu-id="eaf57-121">Página da Web / Informações de rede</span><span class="sxs-lookup"><span data-stu-id="eaf57-121">Web page / Network information</span></span>

- <span data-ttu-id="eaf57-122">URL completa (em navegadores com suporte), quando clicado</span><span class="sxs-lookup"><span data-stu-id="eaf57-122">Full URL (on supported browsers), when clicked</span></span>
- <span data-ttu-id="eaf57-123">Informações de conexão</span><span class="sxs-lookup"><span data-stu-id="eaf57-123">Connection information</span></span>
- <span data-ttu-id="eaf57-124">Tipo de protocolo (como HTTP, HTTPS, etc.)</span><span class="sxs-lookup"><span data-stu-id="eaf57-124">Protocol type (such as HTTP, HTTPS, etc.)</span></span>


### <a name="device-and-account-information"></a><span data-ttu-id="eaf57-125">Informações de dispositivo e conta</span><span class="sxs-lookup"><span data-stu-id="eaf57-125">Device and account information</span></span>

- <span data-ttu-id="eaf57-126">Informações do dispositivo, como data & hora, versão do Android, modelo OEM, informações da CPU e identificador de dispositivo</span><span class="sxs-lookup"><span data-stu-id="eaf57-126">Device information such as date & time, Android version, OEM model, CPU       info, and Device identifier</span></span>
- <span data-ttu-id="eaf57-127">O identificador de dispositivo é um dos abaixo:</span><span class="sxs-lookup"><span data-stu-id="eaf57-127">Device identifier is one of the below:</span></span>
    - <span data-ttu-id="eaf57-128">Wi-Fi mac adaptador</span><span class="sxs-lookup"><span data-stu-id="eaf57-128">Wi-Fi adapter MAC address</span></span>
    - <span data-ttu-id="eaf57-129">[ID do Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (conforme gerado pelo Android no momento da primeira inicialização do dispositivo)</span><span class="sxs-lookup"><span data-stu-id="eaf57-129">[Android       ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (as generated by Android at the time of first boot of the device)</span></span>
    - <span data-ttu-id="eaf57-130">Identificador global exclusivo gerado aleatoriamente (GUID)</span><span class="sxs-lookup"><span data-stu-id="eaf57-130">Randomly generated globally unique identifier (GUID)</span></span>

- <span data-ttu-id="eaf57-131">Informações de locatário, dispositivo e usuário</span><span class="sxs-lookup"><span data-stu-id="eaf57-131">Tenant, Device and User information</span></span>
    -   <span data-ttu-id="eaf57-132">ID do Dispositivo do Azure Active Directory (AD) e ID do Usuário do Azure: identifica exclusivamente o dispositivo, Usuário, respectivamente, no diretório do Azure Active.</span><span class="sxs-lookup"><span data-stu-id="eaf57-132">Azure Active Directory (AD) Device ID and Azure User ID: Uniquely     identifies the device, User respectively at Azure Active directory.</span></span>

    -   <span data-ttu-id="eaf57-133">ID do locatário do Azure - GUID que identifica sua organização no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eaf57-133">Azure tenant ID - GUID that identifies your organization within     Azure Active Directory</span></span>

    -   <span data-ttu-id="eaf57-134">ID da organização do Microsoft Defender ATP - Identificador exclusivo associado à empresa à que o dispositivo pertence.</span><span class="sxs-lookup"><span data-stu-id="eaf57-134">Microsoft Defender ATP org ID - Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="eaf57-135">Permite que a Microsoft identifique se os problemas estão afetando um conjunto selecionado de empresas e quantas empresas são impactadas</span><span class="sxs-lookup"><span data-stu-id="eaf57-135">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted</span></span> 

    -   <span data-ttu-id="eaf57-136">Nome principal do usuário – ID de email do usuário</span><span class="sxs-lookup"><span data-stu-id="eaf57-136">User Principal Name – Email ID of the user</span></span>

### <a name="product-and-service-usage-data"></a><span data-ttu-id="eaf57-137">Dados de uso de produtos e serviços</span><span class="sxs-lookup"><span data-stu-id="eaf57-137">Product and service usage data</span></span>
-   <span data-ttu-id="eaf57-138">Informações do pacote do aplicativo, incluindo o nome, a versão e o status da atualização do aplicativo</span><span class="sxs-lookup"><span data-stu-id="eaf57-138">App package info, including name, version, and app upgrade status</span></span>

-   <span data-ttu-id="eaf57-139">Ações executadas no aplicativo</span><span class="sxs-lookup"><span data-stu-id="eaf57-139">Actions performed in the app</span></span>

-   <span data-ttu-id="eaf57-140">Informações de detecção de ameaças, como nome da ameaça, categoria, etc.</span><span class="sxs-lookup"><span data-stu-id="eaf57-140">Threat detection information, such as threat name, category, etc.</span></span>

-   <span data-ttu-id="eaf57-141">Logs de relatório de falha gerados pelo Android</span><span class="sxs-lookup"><span data-stu-id="eaf57-141">Crash report logs generated by Android</span></span>

## <a name="optional-data"></a><span data-ttu-id="eaf57-142">Dados Opcionais</span><span class="sxs-lookup"><span data-stu-id="eaf57-142">Optional Data</span></span>

<span data-ttu-id="eaf57-143">Os dados opcionais incluem dados de diagnóstico e comentários.</span><span class="sxs-lookup"><span data-stu-id="eaf57-143">Optional data includes diagnostic data and feedback data.</span></span> <span data-ttu-id="eaf57-144">Os Dados de diagnóstico opcionais são dados adicionais que nos ajudam a melhorar o produto e fornecem informações aprimoradas para nos ajudar a detectar, diagnosticar e corrigir problemas.</span><span class="sxs-lookup"><span data-stu-id="eaf57-144">Optional diagnostic data is additional data that helps us make product improvements and provides enhanced information to help us detect, diagnose, and fix issues.</span></span> <span data-ttu-id="eaf57-145">Os dados de diagnóstico opcionais incluem:</span><span class="sxs-lookup"><span data-stu-id="eaf57-145">Optional diagnostic data includes:</span></span>

-   <span data-ttu-id="eaf57-146">Uso de aplicativo, CPU e rede</span><span class="sxs-lookup"><span data-stu-id="eaf57-146">App, CPU, and network usage</span></span>

-   <span data-ttu-id="eaf57-147">Estado do dispositivo na perspectiva do aplicativo, incluindo status de verificação, tempos de verificação, permissões de aplicativo concedidas e status de atualização</span><span class="sxs-lookup"><span data-stu-id="eaf57-147">State of the device from the app perspective, including scan status, scan timings, app permissions granted, and upgrade status</span></span>

-   <span data-ttu-id="eaf57-148">Recursos configurados pelo administrador</span><span class="sxs-lookup"><span data-stu-id="eaf57-148">Features configured by the admin</span></span>

-   <span data-ttu-id="eaf57-149">Informações básicas sobre os navegadores no dispositivo</span><span class="sxs-lookup"><span data-stu-id="eaf57-149">Basic information about the browsers on the device</span></span>

<span data-ttu-id="eaf57-150">**Dados de feedback** são coletados por meio de comentários no aplicativo fornecidos pelo usuário</span><span class="sxs-lookup"><span data-stu-id="eaf57-150">**Feedback Data** is collected through in-app feedback provided by the user</span></span>

-   <span data-ttu-id="eaf57-151">O endereço de email do usuário, se ele optar por fornecer</span><span class="sxs-lookup"><span data-stu-id="eaf57-151">The user’s email address, if they choose to provide it</span></span>

-   <span data-ttu-id="eaf57-152">Tipo de comentários (risos, carrancudos, ideias) e comentários enviados pelo usuário</span><span class="sxs-lookup"><span data-stu-id="eaf57-152">Feedback type (smile, frown, idea) and any feedback comments submitted by the user</span></span>
