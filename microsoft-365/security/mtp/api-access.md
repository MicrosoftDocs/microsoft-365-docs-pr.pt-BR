---
title: Acessar as APIs do Microsoft 365 defender
description: Saiba como acessar as APIs do Microsoft 365 defender
keywords: acesso, APIs, contexto de aplicativo, contexto de usuário, aplicativo AAD, token de acesso
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845007"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="896b4-104">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="896b4-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="896b4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="896b4-105">**Applies to:**</span></span>
- <span data-ttu-id="896b4-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="896b4-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="896b4-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="896b4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="896b4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="896b4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="896b4-109">O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação.</span><span class="sxs-lookup"><span data-stu-id="896b4-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="896b4-110">Essas APIs permitirão que você automatize os fluxos de trabalho e inovações com base nos recursos do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="896b4-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="896b4-111">O acesso à API requer autenticação do OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="896b4-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="896b4-112">Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="896b4-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="896b4-113">Em geral, você precisará executar as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="896b4-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="896b4-114">Criar um aplicativo AAD</span><span class="sxs-lookup"><span data-stu-id="896b4-114">Create an AAD application</span></span>
- <span data-ttu-id="896b4-115">Obter um token de acesso usando este aplicativo</span><span class="sxs-lookup"><span data-stu-id="896b4-115">Get an access token using this application</span></span>
- <span data-ttu-id="896b4-116">Usar o token para acessar a API do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="896b4-116">Use the token to access  Microsoft 365 Defender API</span></span>


<span data-ttu-id="896b4-117">Você pode acessar a API do Microsoft 365 defender com **contexto do aplicativo** ou **contexto do usuário**.</span><span class="sxs-lookup"><span data-stu-id="896b4-117">You can access Microsoft 365 Defender API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="896b4-118">**Contexto do aplicativo: (recomendado)**</span><span class="sxs-lookup"><span data-stu-id="896b4-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="896b4-119">Usado por aplicativos que são executados sem um usuário conectado presente.</span><span class="sxs-lookup"><span data-stu-id="896b4-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="896b4-120">por exemplo, aplicativos executados como serviços em segundo plano ou daemons.</span><span class="sxs-lookup"><span data-stu-id="896b4-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="896b4-121">Etapas que precisam ser executadas para acessar a API do Microsoft 365 defender com contexto de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="896b4-121">Steps that need to be taken to access  Microsoft 365 Defender API with application context:</span></span>

  1. <span data-ttu-id="896b4-122">Criar um aplicativo Web do AAD.</span><span class="sxs-lookup"><span data-stu-id="896b4-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="896b4-123">Atribua a permissão desejada ao exemplo de applicationFor, **Incident. Read. All** , **AdvancedHunting. Read. All**.</span><span class="sxs-lookup"><span data-stu-id="896b4-123">Assign the desired permission to the applicationFor example, **Incident.Read.All** , **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="896b4-124">Crie uma chave para este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="896b4-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="896b4-125">Obtém o token usando o aplicativo com sua chave.</span><span class="sxs-lookup"><span data-stu-id="896b4-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="896b4-126">Usar o token para acessar a API do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="896b4-126">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="896b4-127">Para obter mais informações, consulte [obter acesso com contexto de aplicativo](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="896b4-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="896b4-128">**Contexto do usuário:**</span><span class="sxs-lookup"><span data-stu-id="896b4-128">**User Context:**</span></span> <br>
    <span data-ttu-id="896b4-129">Usado para executar ações na API em nome de um usuário.</span><span class="sxs-lookup"><span data-stu-id="896b4-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="896b4-130">Etapas que devem ser seguidas para acessar a API do Microsoft 365 defender com contexto de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="896b4-130">Steps that needs to be taken to access  Microsoft 365 Defender API with application context:</span></span>
  1. <span data-ttu-id="896b4-131">Criar aplicativo nativo do AAD.</span><span class="sxs-lookup"><span data-stu-id="896b4-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="896b4-132">Atribua a permissão desejada ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="896b4-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="896b4-133">Por exemplo, **Incident. Read** , **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="896b4-133">For example, **Incident.Read** , **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="896b4-134">Obtém o token usando o aplicativo com credenciais do usuário.</span><span class="sxs-lookup"><span data-stu-id="896b4-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="896b4-135">Usar o token para acessar a API do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="896b4-135">Use the token to access  Microsoft 365 Defender API</span></span>

     <span data-ttu-id="896b4-136">Para obter mais informações, consulte [obter acesso com contexto de usuário](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="896b4-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="896b4-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="896b4-137">Related topics</span></span>
- [<span data-ttu-id="896b4-138">APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="896b4-138">Microsoft 365 Defender APIs</span></span>](api-supported.md)
- [<span data-ttu-id="896b4-139">Acessar o Microsoft 365 defender com contexto de aplicativo</span><span class="sxs-lookup"><span data-stu-id="896b4-139">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="896b4-140">Acessar o Microsoft 365 defender com contexto de usuário</span><span class="sxs-lookup"><span data-stu-id="896b4-140">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
