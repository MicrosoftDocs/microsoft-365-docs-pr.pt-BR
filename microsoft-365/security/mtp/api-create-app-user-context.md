---
title: Criar um aplicativo para acessar APIs do Microsoft 365 Defender em nome de um usuário
description: Saiba como acessar as APIs do Microsoft 365 Defender em nome de um usuário.
keywords: access, em nome do usuário, api, aplicativo, usuário, token de acesso, token,
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
ms.openlocfilehash: 85c41c0bae9590e76801c18b2a33401874cc7cc3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903947"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="8699a-104">Criar um aplicativo para acessar APIs do Microsoft 365 Defender em nome de um usuário</span><span class="sxs-lookup"><span data-stu-id="8699a-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8699a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8699a-105">**Applies to:**</span></span>

- <span data-ttu-id="8699a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8699a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8699a-107">Algumas informações se relacionam ao produto pré-lançamento, que pode ser substancialmente modificado antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="8699a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="8699a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="8699a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="8699a-109">Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 Defender em nome de um único usuário.</span><span class="sxs-lookup"><span data-stu-id="8699a-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="8699a-110">Se você precisar de acesso programático ao Microsoft 365 Defender sem um usuário definido (por exemplo, se você estiver escrevendo um aplicativo em segundo plano ou daemon), consulte [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="8699a-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="8699a-111">Se você precisar fornecer acesso a vários locatários, por exemplo, se estiver servindo uma grande organização ou um grupo de clientes, consulte Create an app with [partner access to Microsoft 365 Defender APIs](api-partner-access.md). Se você não tiver certeza de que tipo de acesso precisa, consulte [Começar](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="8699a-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="8699a-112">O Microsoft 365 Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas.</span><span class="sxs-lookup"><span data-stu-id="8699a-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="8699a-113">Essas APIs ajudam a automatizar fluxos de trabalho e usar os recursos do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8699a-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="8699a-114">Esse acesso à API requer autenticação OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="8699a-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="8699a-115">Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="8699a-115">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="8699a-116">Em geral, você precisará seguir as seguintes etapas para usar estas APIs:</span><span class="sxs-lookup"><span data-stu-id="8699a-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="8699a-117">Crie um aplicativo do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8699a-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="8699a-118">Obter um token de acesso usando este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8699a-118">Get an access token using this application.</span></span>
- <span data-ttu-id="8699a-119">Use o token para acessar a API do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8699a-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="8699a-120">Este artigo explica como:</span><span class="sxs-lookup"><span data-stu-id="8699a-120">This article explains how to:</span></span>

- <span data-ttu-id="8699a-121">Criar um aplicativo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="8699a-121">Create an Azure AD application</span></span>
- <span data-ttu-id="8699a-122">Obter um token de acesso ao Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8699a-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="8699a-123">Validar o token</span><span class="sxs-lookup"><span data-stu-id="8699a-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="8699a-124">Ao acessar a API do Microsoft 365 Defender em nome de um usuário, você precisará das permissões de aplicativo e permissões de usuário corretas.</span><span class="sxs-lookup"><span data-stu-id="8699a-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="8699a-125">Se você tiver permissão para executar uma ação no portal, terá permissão para executar a ação na API.</span><span class="sxs-lookup"><span data-stu-id="8699a-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="8699a-126">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="8699a-126">Create an app</span></span>

1. <span data-ttu-id="8699a-127">Entre no [Azure como](https://portal.azure.com) um usuário com a função **Administrador Global.**</span><span class="sxs-lookup"><span data-stu-id="8699a-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="8699a-128">Navegue **até registros do Aplicativo do Azure Active Directory** Novo  >    >  **registro**.</span><span class="sxs-lookup"><span data-stu-id="8699a-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagem do Microsoft Azure e navegação para registro de aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="8699a-130">No formulário, escolha um nome para seu aplicativo e insira as seguintes informações para o URI de **redirecionamento** e selecione Registrar .</span><span class="sxs-lookup"><span data-stu-id="8699a-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Imagem da janela Criar aplicativo](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="8699a-132">**Tipo de aplicativo:** Cliente público</span><span class="sxs-lookup"><span data-stu-id="8699a-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="8699a-133">**URI de redirecionamento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="8699a-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="8699a-134">Em sua página de aplicativo, selecione **Permissões** de API Adicionar  >    >  **APIs** de permissão que minha organização usa >, digite Proteção contra Ameaças da Microsoft e selecione Proteção contra Ameaças da Microsoft .</span><span class="sxs-lookup"><span data-stu-id="8699a-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="8699a-135">Seu aplicativo agora pode acessar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8699a-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="8699a-136">*A Proteção contra Ameaças* da Microsoft é um nome antigo do Microsoft 365 Defender e não aparecerá na lista original.</span><span class="sxs-lookup"><span data-stu-id="8699a-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="8699a-137">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.</span><span class="sxs-lookup"><span data-stu-id="8699a-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagem da seleção de permissão da API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="8699a-139">Escolha **Permissões delegadas**.</span><span class="sxs-lookup"><span data-stu-id="8699a-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="8699a-140">Escolha as permissões relevantes para seu cenário (por **exemplo, Incident.Read**) e selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="8699a-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Imagem do acesso à API e seleção de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="8699a-142">Você precisa selecionar as permissões relevantes para seu cenário.</span><span class="sxs-lookup"><span data-stu-id="8699a-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="8699a-143">*Ler todos os incidentes* é apenas um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8699a-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="8699a-144">Para determinar de que permissão você precisa, consulte a seção **Permissões** na API que você deseja chamar.</span><span class="sxs-lookup"><span data-stu-id="8699a-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="8699a-145">Por exemplo, para [executar consultas avançadas,](api-advanced-hunting.md)selecione a permissão "Executar consultas avançadas"; para [isolar um dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecione a permissão 'Isolar máquina'.</span><span class="sxs-lookup"><span data-stu-id="8699a-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="8699a-146">Selecione **Conceder consentimento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="8699a-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="8699a-147">Sempre que você adicionar uma permissão, você deve selecionar **Conceder consentimento de administrador** para que ela entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="8699a-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Imagem de Permissões de Concessão](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="8699a-149">Grave sua ID de aplicativo e sua ID de locatário em algum lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="8699a-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="8699a-150">Eles estão listados em **Visão Geral** na página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8699a-150">They're listed under **Overview** on your application page.</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="8699a-152">Obter um token de acesso</span><span class="sxs-lookup"><span data-stu-id="8699a-152">Get an access token</span></span>

<span data-ttu-id="8699a-153">Para obter mais informações sobre tokens do Azure Active Directory, consulte o tutorial do [Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="8699a-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="8699a-154">Obter um token de acesso usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8699a-154">Get an access token using PowerShell</span></span>

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a><span data-ttu-id="8699a-155">Validar o token</span><span class="sxs-lookup"><span data-stu-id="8699a-155">Validate the token</span></span>

1. <span data-ttu-id="8699a-156">Copie e colar o token em [JWT](https://jwt.ms) para decodificá-lo.</span><span class="sxs-lookup"><span data-stu-id="8699a-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="8699a-157">Certifique-se de que *as funções* de declaração dentro do token decodificado contenham as permissões desejadas.</span><span class="sxs-lookup"><span data-stu-id="8699a-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="8699a-158">Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, com ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` permissões:</span><span class="sxs-lookup"><span data-stu-id="8699a-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagem da validação de token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="8699a-160">Usar o token para acessar a API do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8699a-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="8699a-161">Escolha a API que você deseja usar (incidentes ou busca avançada).</span><span class="sxs-lookup"><span data-stu-id="8699a-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="8699a-162">Para obter mais informações, consulte APIs do [Microsoft 365 Defender com suporte.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="8699a-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="8699a-163">Na solicitação http que você está prestes a enviar, de definir o cabeçalho de autorização como , o portador é o esquema de autorização e o token sendo `"Bearer" <token>` seu token  validado. </span><span class="sxs-lookup"><span data-stu-id="8699a-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="8699a-164">O token expirará dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="8699a-164">The token will expire within one hour.</span></span> <span data-ttu-id="8699a-165">Você pode enviar mais de uma solicitação durante esse tempo com o mesmo token.</span><span class="sxs-lookup"><span data-stu-id="8699a-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="8699a-166">O exemplo a seguir mostra como enviar uma solicitação para obter uma lista de incidentes **usando C#**.</span><span class="sxs-lookup"><span data-stu-id="8699a-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="8699a-167">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="8699a-167">Related articles</span></span>

- [<span data-ttu-id="8699a-168">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8699a-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="8699a-169">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8699a-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="8699a-170">Criar um aplicativo 'Hello world'</span><span class="sxs-lookup"><span data-stu-id="8699a-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="8699a-171">Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário</span><span class="sxs-lookup"><span data-stu-id="8699a-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="8699a-172">Criar um aplicativo com acesso de parceiro de vários locatários às APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8699a-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="8699a-173">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="8699a-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="8699a-174">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="8699a-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="8699a-175">Autorização OAuth 2.0 para entrada do usuário e acesso à API</span><span class="sxs-lookup"><span data-stu-id="8699a-175">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)