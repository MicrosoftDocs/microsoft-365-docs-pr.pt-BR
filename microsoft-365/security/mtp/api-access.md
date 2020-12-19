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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719233"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="5704f-104">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="5704f-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5704f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5704f-105">**Applies to:**</span></span>

- <span data-ttu-id="5704f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5704f-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5704f-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="5704f-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="5704f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="5704f-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="5704f-109">O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação.</span><span class="sxs-lookup"><span data-stu-id="5704f-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="5704f-110">Essas APIs ajudam a automatizar os fluxos de trabalho e a fazer uso completo dos recursos do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="5704f-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="5704f-111">Em geral, você precisará executar as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="5704f-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="5704f-112">Criar um aplicativo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5704f-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="5704f-113">Obter um token de acesso usando este aplicativo</span><span class="sxs-lookup"><span data-stu-id="5704f-113">Get an access token using this application</span></span>
- <span data-ttu-id="5704f-114">Usar o token para acessar a API do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="5704f-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="5704f-115">O acesso à API requer autenticação do OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="5704f-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="5704f-116">Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="5704f-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="5704f-117">Depois de concluir essas etapas, você estará pronto para acessar a API do Microsoft 365 defender usando um contexto específico.</span><span class="sxs-lookup"><span data-stu-id="5704f-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="5704f-118">Contexto do aplicativo (recomendado)</span><span class="sxs-lookup"><span data-stu-id="5704f-118">Application context (Recommended)</span></span>

<span data-ttu-id="5704f-119">Use este contexto para aplicativos que são executados sem um usuário conectado, como serviços de segundo plano ou daemons.</span><span class="sxs-lookup"><span data-stu-id="5704f-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="5704f-120">Criar um aplicativo Web do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5704f-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="5704f-121">Atribua as permissões desejadas ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5704f-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="5704f-122">Crie uma chave para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5704f-122">Create a key for the application.</span></span>
4. <span data-ttu-id="5704f-123">Obtenha um token de segurança usando o aplicativo e sua chave.</span><span class="sxs-lookup"><span data-stu-id="5704f-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="5704f-124">Use o token para acessar a API do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="5704f-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="5704f-125">Para obter mais informações, consulte **[criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md)**.</span><span class="sxs-lookup"><span data-stu-id="5704f-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="5704f-126">Contexto de usuário</span><span class="sxs-lookup"><span data-stu-id="5704f-126">User context</span></span>

<span data-ttu-id="5704f-127">Use este contexto para executar ações em nome de um único usuário.</span><span class="sxs-lookup"><span data-stu-id="5704f-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="5704f-128">Criar um aplicativo nativo do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5704f-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="5704f-129">Atribua a permissão desejada ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5704f-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="5704f-130">Obtenha um token de segurança usando as credenciais do usuário para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5704f-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="5704f-131">Use o token para acessar a API do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="5704f-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="5704f-132">Para obter mais informações, consulte **[criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário](api-create-app-user-context.md)**.</span><span class="sxs-lookup"><span data-stu-id="5704f-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="5704f-133">Contexto de parceiro</span><span class="sxs-lookup"><span data-stu-id="5704f-133">Partner context</span></span>

<span data-ttu-id="5704f-134">Use este contexto quando precisar fornecer um aplicativo a muitos usuários em [vários locatários](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span><span class="sxs-lookup"><span data-stu-id="5704f-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="5704f-135">Criar um aplicativo de vários locatários do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5704f-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="5704f-136">Atribua a permissão desejada ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5704f-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="5704f-137">Obter o [consentimento do administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para o aplicativo de cada locatário.</span><span class="sxs-lookup"><span data-stu-id="5704f-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="5704f-138">Obter um token de segurança usando credenciais de usuário com base na ID de locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="5704f-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="5704f-139">Use o token para acessar a API do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="5704f-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="5704f-140">Para obter mais informações, consulte **[criar um aplicativo com acesso de parceiro às APIs do Microsoft 365 defender](api-partner-access.md)**.</span><span class="sxs-lookup"><span data-stu-id="5704f-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="5704f-141">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="5704f-141">Related articles</span></span>

- [<span data-ttu-id="5704f-142">Visão geral das APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="5704f-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="5704f-143">Autorização OAuth 2,0 para entrada de usuário e acesso à API</span><span class="sxs-lookup"><span data-stu-id="5704f-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="5704f-144">Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="5704f-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="5704f-145">Criar um aplicativo de "Hello World" que acessa as APIs do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5704f-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
