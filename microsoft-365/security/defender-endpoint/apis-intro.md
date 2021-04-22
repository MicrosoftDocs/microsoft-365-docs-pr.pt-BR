---
title: Acessar as APIs do Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Saiba como você pode usar APIs para automatizar fluxos de trabalho e inovar com base nos recursos do Microsoft Defender para o Ponto de Extremidade
keywords: apis, api, Microsoft Defender para Ponto de Extremidade, api aberta, api do Microsoft Defender para Ponto de Extremidade, api pública, apis com suporte, alertas, dispositivo, usuário, domínio, ip, arquivo, busca avançada, consulta
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 87dce8ff4fde505eb8d4e458c8d9fb56556f4d78
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935099"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="0a0f7-104">Acessar as APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0a0f7-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0a0f7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0a0f7-105">**Applies to:**</span></span>
- [<span data-ttu-id="0a0f7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0a0f7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0a0f7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a0f7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="0a0f7-108">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0a0f7-108">**Applies to:**</span></span> 
- [<span data-ttu-id="0a0f7-109">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0a0f7-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="0a0f7-110">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0a0f7-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0a0f7-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="0a0f7-112">O Defender for Endpoint expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="0a0f7-113">Essas APIs permitirão que você automatize fluxos de trabalho e inove com base nos recursos do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="0a0f7-114">O acesso à API requer autenticação OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="0a0f7-115">Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="0a0f7-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="0a0f7-116">Assista a este vídeo para uma visão geral rápida do Defender para APIs do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="0a0f7-117">Em geral, você precisará seguir as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="0a0f7-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="0a0f7-118">Criar um aplicativo AAD</span><span class="sxs-lookup"><span data-stu-id="0a0f7-118">Create an AAD application</span></span>
- <span data-ttu-id="0a0f7-119">Obter um token de acesso usando este aplicativo</span><span class="sxs-lookup"><span data-stu-id="0a0f7-119">Get an access token using this application</span></span>
- <span data-ttu-id="0a0f7-120">Usar o token para acessar a API do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0a0f7-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="0a0f7-121">Você pode acessar a API do Defender para Ponto de Extremidade com **Contexto de Aplicativo** ou Contexto do **Usuário.**</span><span class="sxs-lookup"><span data-stu-id="0a0f7-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="0a0f7-122">**Contexto do aplicativo: (Recomendado)**</span><span class="sxs-lookup"><span data-stu-id="0a0f7-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="0a0f7-123">Usado por aplicativos que são executados sem um usuário assinado presente.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="0a0f7-124">por exemplo, aplicativos que são executados como serviços em segundo plano ou daemons.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="0a0f7-125">Etapas que precisam ser tomadas para acessar a API do Defender for Endpoint com contexto de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="0a0f7-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="0a0f7-126">Crie um Aplicativo Web do AAD.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="0a0f7-127">Atribua a permissão desejada ao aplicativo, por exemplo, 'Alertas de leitura', 'Isolar Máquinas'.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="0a0f7-128">Crie uma chave para este Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="0a0f7-129">Obter token usando o aplicativo com sua chave.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="0a0f7-130">Usar o token para acessar a API do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a0f7-130">Use the token to access Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="0a0f7-131">Para obter mais informações, consulte [Obter acesso com o contexto do aplicativo](exposed-apis-create-app-webapp.md).</span><span class="sxs-lookup"><span data-stu-id="0a0f7-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="0a0f7-132">**Contexto do usuário:**</span><span class="sxs-lookup"><span data-stu-id="0a0f7-132">**User Context:**</span></span> <br>
    <span data-ttu-id="0a0f7-133">Usado para executar ações na API em nome de um usuário.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="0a0f7-134">Etapas a serem tomadas para acessar a API do Defender para Ponto de Extremidade com contexto de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="0a0f7-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="0a0f7-135">Criar aplicativo nativo do AAD.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="0a0f7-136">Atribua a permissão desejada ao aplicativo, por exemplo, "Alertas de leitura", "Isolar Máquinas" etc.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="0a0f7-137">Obter token usando o aplicativo com credenciais de usuário.</span><span class="sxs-lookup"><span data-stu-id="0a0f7-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="0a0f7-138">Usar o token para acessar a API do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a0f7-138">Use the token to access Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="0a0f7-139">Para obter mais informações, consulte [Obter acesso com o contexto do usuário](exposed-apis-create-app-nativeapp.md).</span><span class="sxs-lookup"><span data-stu-id="0a0f7-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="0a0f7-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0a0f7-140">Related topics</span></span>
- [<span data-ttu-id="0a0f7-141">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0a0f7-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="0a0f7-142">Acessar o Microsoft Defender para Ponto de Extremidade com contexto de aplicativo</span><span class="sxs-lookup"><span data-stu-id="0a0f7-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="0a0f7-143">Acessar o Microsoft Defender para Ponto de Extremidade com contexto de usuário</span><span class="sxs-lookup"><span data-stu-id="0a0f7-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
