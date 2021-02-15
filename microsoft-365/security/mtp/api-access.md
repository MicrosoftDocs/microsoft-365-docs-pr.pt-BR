---
title: Acessar as APIs do Microsoft 365 Defender
description: Saiba como acessar as APIs do Microsoft 365 Defender
keywords: access, apis, contexto de aplicativo, contexto de usuário, aplicativo aad, token de acesso
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932149"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="3cf4b-104">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cf4b-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3cf4b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3cf4b-105">**Applies to:**</span></span>

- <span data-ttu-id="3cf4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cf4b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cf4b-107">Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3cf4b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3cf4b-109">O Microsoft 365 Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="3cf4b-110">Essas APIs ajudam a automatizar fluxos de trabalho e usar totalmente os recursos do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="3cf4b-111">Em geral, você precisará seguir as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="3cf4b-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="3cf4b-112">Criar um aplicativo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3cf4b-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="3cf4b-113">Obter um token de acesso usando este aplicativo</span><span class="sxs-lookup"><span data-stu-id="3cf4b-113">Get an access token using this application</span></span>
- <span data-ttu-id="3cf4b-114">Usar o token para acessar a API do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cf4b-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="3cf4b-115">O acesso à API requer autenticação OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="3cf4b-116">Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="3cf4b-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="3cf4b-117">Depois de realizar essas etapas, você estará pronto para acessar a API do Microsoft 365 Defender usando um contexto específico.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="3cf4b-118">Contexto de aplicativo (recomendado)</span><span class="sxs-lookup"><span data-stu-id="3cf4b-118">Application context (Recommended)</span></span>

<span data-ttu-id="3cf4b-119">Use esse contexto para aplicativos que são executados sem um usuário entrar, como serviços em segundo plano ou daemons.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="3cf4b-120">Crie um aplicativo Web do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="3cf4b-121">Atribua as permissões desejadas ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="3cf4b-122">Crie uma chave para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-122">Create a key for the application.</span></span>
4. <span data-ttu-id="3cf4b-123">Obter um token de segurança usando o aplicativo e sua chave.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="3cf4b-124">Use o token para acessar a API do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="3cf4b-125">Para obter mais informações, **[consulte Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="3cf4b-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="3cf4b-126">Contexto do usuário</span><span class="sxs-lookup"><span data-stu-id="3cf4b-126">User context</span></span>

<span data-ttu-id="3cf4b-127">Use esse contexto para executar ações em nome de um único usuário.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="3cf4b-128">Crie um aplicativo nativo do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="3cf4b-129">Atribua a permissão desejada ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="3cf4b-130">Obter um token de segurança usando as credenciais do usuário para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="3cf4b-131">Use o token para acessar a API do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="3cf4b-132">Para obter mais informações, consulte Criar um aplicativo para acessar as APIs do **[Microsoft 365 Defender em nome de um usuário.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="3cf4b-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="3cf4b-133">Contexto de parceiro</span><span class="sxs-lookup"><span data-stu-id="3cf4b-133">Partner context</span></span>

<span data-ttu-id="3cf4b-134">Use esse contexto quando precisar fornecer um aplicativo para vários usuários em [vários locatários.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="3cf4b-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="3cf4b-135">Crie um aplicativo multi-locatário do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="3cf4b-136">Atribua a permissão desejada ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="3cf4b-137">Obter [consentimento do administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para o aplicativo de cada locatário.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="3cf4b-138">Obter um token de segurança usando credenciais de usuário com base na ID de locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="3cf4b-139">Use o token para acessar a API do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3cf4b-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="3cf4b-140">Para saber mais, confira **[Criar um aplicativo com acesso de parceiro às APIs do Microsoft 365 Defender.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="3cf4b-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="3cf4b-141">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="3cf4b-141">Related articles</span></span>

- [<span data-ttu-id="3cf4b-142">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3cf4b-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="3cf4b-143">Autorização do OAuth 2.0 para entrada do usuário e acesso à API</span><span class="sxs-lookup"><span data-stu-id="3cf4b-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="3cf4b-144">Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="3cf4b-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="3cf4b-145">Criar um aplicativo "Hello world" que acesse as APIs do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cf4b-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
