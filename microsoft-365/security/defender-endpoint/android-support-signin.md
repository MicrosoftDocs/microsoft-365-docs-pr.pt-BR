---
title: Solucionar problemas no Microsoft Defender para Ponto de Extremidade no Android
description: Solucionar problemas do Microsoft Defender para Ponto de Extremidade no Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, cloud, connectivity, communication
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246351"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="77c47-104">Solução de problemas no Microsoft Defender para Ponto de Extremidade no Android</span><span class="sxs-lookup"><span data-stu-id="77c47-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="77c47-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="77c47-105">**Applies to:**</span></span>
- [<span data-ttu-id="77c47-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="77c47-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="77c47-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77c47-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="77c47-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="77c47-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="77c47-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="77c47-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="77c47-110">Ao fazer a integração de um dispositivo, você pode ver problemas de entrada após a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="77c47-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="77c47-111">Durante a integração, você pode encontrar problemas de entrada após a instalação do aplicativo em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77c47-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="77c47-112">Este artigo fornece soluções para ajudar a resolver os problemas de login.</span><span class="sxs-lookup"><span data-stu-id="77c47-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="77c47-113">Falha ao entrar - erro inesperado</span><span class="sxs-lookup"><span data-stu-id="77c47-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="77c47-114">**Falha ao entrar:** *Erro inesperado, tente mais tarde*</span><span class="sxs-lookup"><span data-stu-id="77c47-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Imagem de erro de falha de login Erro inesperado](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="77c47-116">**Mensagem:**</span><span class="sxs-lookup"><span data-stu-id="77c47-116">**Message:**</span></span>

<span data-ttu-id="77c47-117">Erro inesperado, tente mais tarde</span><span class="sxs-lookup"><span data-stu-id="77c47-117">Unexpected error, try later</span></span>

<span data-ttu-id="77c47-118">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="77c47-118">**Cause:**</span></span>

<span data-ttu-id="77c47-119">Você tem uma versão mais antiga do aplicativo "Microsoft Authenticator" instalada em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="77c47-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="77c47-120">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="77c47-120">**Solution:**</span></span>

<span data-ttu-id="77c47-121">Instale a versão mais recente e [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) da Google Play Store e tente novamente</span><span class="sxs-lookup"><span data-stu-id="77c47-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="77c47-122">Falha ao entrar - licença inválida</span><span class="sxs-lookup"><span data-stu-id="77c47-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="77c47-123">**Falha ao entrar:** *Licença inválida, entre em contato com o administrador*</span><span class="sxs-lookup"><span data-stu-id="77c47-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Falha na imagem de entrar, entre em contato com o administrador](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="77c47-125">**Mensagem:** *Licença inválida, entre em contato com o administrador*</span><span class="sxs-lookup"><span data-stu-id="77c47-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="77c47-126">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="77c47-126">**Cause:**</span></span>

<span data-ttu-id="77c47-127">Você não tem uma Microsoft 365 atribuída, ou sua organização não tem uma licença para Microsoft 365 Enterprise assinatura.</span><span class="sxs-lookup"><span data-stu-id="77c47-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="77c47-128">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="77c47-128">**Solution:**</span></span>

<span data-ttu-id="77c47-129">Entre em contato com o administrador para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="77c47-129">Contact your administrator for help.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="77c47-130">Relatar site não seguro</span><span class="sxs-lookup"><span data-stu-id="77c47-130">Report unsafe site</span></span>

<span data-ttu-id="77c47-131">Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras.</span><span class="sxs-lookup"><span data-stu-id="77c47-131">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="77c47-132">Visite a [página Fornecer comentários sobre a](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) proteção de rede se quiser relatar um site que pode ser um site de phishing.</span><span class="sxs-lookup"><span data-stu-id="77c47-132">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="77c47-133">Páginas de phishing não são bloqueadas em alguns dispositivos OEM</span><span class="sxs-lookup"><span data-stu-id="77c47-133">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="77c47-134">**Aplica-se a:** Somente OEMs específicos</span><span class="sxs-lookup"><span data-stu-id="77c47-134">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="77c47-135">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="77c47-135">**Xiaomi**</span></span>

<span data-ttu-id="77c47-136">Phishing e ameaças na Web prejudiciais detectadas pelo Defender para Ponto de Extremidade para Android não são bloqueadas em alguns dispositivos Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="77c47-136">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="77c47-137">A funcionalidade a seguir não funciona nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="77c47-137">The following functionality doesn't work on these devices.</span></span>

![Imagem do site relatada não segura](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="77c47-139">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="77c47-139">**Cause:**</span></span>

<span data-ttu-id="77c47-140">Os dispositivos Xiaomi incluem um novo modelo de permissão.</span><span class="sxs-lookup"><span data-stu-id="77c47-140">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="77c47-141">Isso impede que o Defender para Ponto de Extremidade para Android ex displaye janelas pop-up enquanto ele é executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="77c47-141">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="77c47-142">Permissão de dispositivos Xiaomi: "Exibir janelas pop-up durante a execução em segundo plano".</span><span class="sxs-lookup"><span data-stu-id="77c47-142">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Imagem da configuração pop-up](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="77c47-144">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="77c47-144">**Solution:**</span></span>

<span data-ttu-id="77c47-145">Habilita a permissão necessária em dispositivos Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="77c47-145">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="77c47-146">Exibir janelas pop-up durante a execução em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="77c47-146">Display pop-up windows while running in the background.</span></span>
