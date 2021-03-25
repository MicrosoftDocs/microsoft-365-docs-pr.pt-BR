---
title: Solucionar problemas no Microsoft Defender ATP para Android
description: Solucionar problemas do Microsoft Defender ATP para Android
keywords: microsoft, defender, atp, android, nuvem, conectividade, comunicação
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 444541c85f8f4416288dcebf4bbee2c65a33d3d2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164864"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="c8d7d-104">Solução de problemas no Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="c8d7d-104">Troubleshooting issues on Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8d7d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8d7d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c8d7d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8d7d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8d7d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c8d7d-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c8d7d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8d7d-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="c8d7d-110">Ao fazer a integração de um dispositivo, você pode ver problemas de entrada após a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="c8d7d-111">Durante a integração, você pode encontrar problemas de entrada após a instalação do aplicativo em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="c8d7d-112">Este artigo fornece soluções para ajudar a resolver os problemas de login.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="c8d7d-113">Falha ao entrar - erro inesperado</span><span class="sxs-lookup"><span data-stu-id="c8d7d-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="c8d7d-114">**Falha ao entrar:** *Erro inesperado, tente mais tarde*</span><span class="sxs-lookup"><span data-stu-id="c8d7d-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Imagem de erro de falha de login Erro inesperado](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="c8d7d-116">**Mensagem:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-116">**Message:**</span></span>

<span data-ttu-id="c8d7d-117">Erro inesperado, tente mais tarde</span><span class="sxs-lookup"><span data-stu-id="c8d7d-117">Unexpected error, try later</span></span>

<span data-ttu-id="c8d7d-118">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-118">**Cause:**</span></span>

<span data-ttu-id="c8d7d-119">Você tem uma versão mais antiga do aplicativo "Microsoft Authenticator" instalada em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="c8d7d-120">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-120">**Solution:**</span></span>

<span data-ttu-id="c8d7d-121">Instalar a versão mais recente e o [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) na Google Play Store e tentar novamente</span><span class="sxs-lookup"><span data-stu-id="c8d7d-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="c8d7d-122">Falha ao entrar - licença inválida</span><span class="sxs-lookup"><span data-stu-id="c8d7d-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="c8d7d-123">**Falha ao entrar:** *Licença inválida, entre em contato com o administrador*</span><span class="sxs-lookup"><span data-stu-id="c8d7d-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Falha na imagem de entrar, entre em contato com o administrador](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="c8d7d-125">**Mensagem:** *Licença inválida, entre em contato com o administrador*</span><span class="sxs-lookup"><span data-stu-id="c8d7d-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="c8d7d-126">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-126">**Cause:**</span></span>

<span data-ttu-id="c8d7d-127">Você não tem a licença do Microsoft 365 atribuída ou sua organização não tem uma licença para a assinatura do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="c8d7d-128">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-128">**Solution:**</span></span>

<span data-ttu-id="c8d7d-129">Entre em contato com o administrador para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="c8d7d-130">Páginas de phishing não são bloqueadas em alguns dispositivos OEM</span><span class="sxs-lookup"><span data-stu-id="c8d7d-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="c8d7d-131">**Aplica-se a:** Somente OEMs específicos</span><span class="sxs-lookup"><span data-stu-id="c8d7d-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="c8d7d-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-132">**Xiaomi**</span></span>

<span data-ttu-id="c8d7d-133">Phishing e ameaças na Web prejudiciais detectadas pelo Defender para Ponto de Extremidade para Android não são bloqueadas em alguns dispositivos Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="c8d7d-134">A funcionalidade a seguir não funciona nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-134">The following functionality doesn't work on these devices.</span></span>

![Imagem do site relatada não segura](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="c8d7d-136">**Causa:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-136">**Cause:**</span></span>

<span data-ttu-id="c8d7d-137">Os dispositivos Xiaomi incluem um novo modelo de permissão.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="c8d7d-138">Isso impede que o Defender para Ponto de Extremidade para Android ex displaye janelas pop-up enquanto ele é executado em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="c8d7d-139">Permissão de dispositivos Xiaomi: "Exibir janelas pop-up durante a execução em segundo plano".</span><span class="sxs-lookup"><span data-stu-id="c8d7d-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Imagem da configuração pop-up](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="c8d7d-141">**Solução:**</span><span class="sxs-lookup"><span data-stu-id="c8d7d-141">**Solution:**</span></span>

<span data-ttu-id="c8d7d-142">Habilita a permissão necessária em dispositivos Xiaomi.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="c8d7d-143">Exibir janelas pop-up durante a execução em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c8d7d-143">Display pop-up windows while running in the background.</span></span>
