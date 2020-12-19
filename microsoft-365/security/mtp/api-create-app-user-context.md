---
title: Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário
description: Saiba como acessar as APIs do Microsoft 365 defender em nome de um usuário.
keywords: acesso, em nome de usuário, API, aplicativo, usuário, token de acesso, token,
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719411"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a><span data-ttu-id="31870-104">Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário</span><span class="sxs-lookup"><span data-stu-id="31870-104">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="31870-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="31870-105">**Applies to:**</span></span>

- <span data-ttu-id="31870-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31870-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31870-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="31870-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="31870-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="31870-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="31870-109">Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 defender em nome de um único usuário.</span><span class="sxs-lookup"><span data-stu-id="31870-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a single user.</span></span>

<span data-ttu-id="31870-110">Se você precisar de acesso programático ao Microsoft 365 defender sem um usuário definido (por exemplo, se você estiver criando um aplicativo de plano de fundo ou daemon), confira [criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="31870-110">If you need programmatic access to Microsoft 365 Defender without a defined user (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="31870-111">Se você precisar fornecer acesso para vários locatários — por exemplo, se estiver servindo uma grande organização ou um grupo de clientes, confira [criar um aplicativo com acesso para parceiros às APIs do Microsoft 365 defender](api-partner-access.md). Se você não tiver certeza sobre qual tipo de acesso precisa, consulte [introdução](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="31870-111">If you need to provide access for multiple tenants—for example, if you're serving a large organization or a group of customers—see [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="31870-112">O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação.</span><span class="sxs-lookup"><span data-stu-id="31870-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="31870-113">Essas APIs ajudam a automatizar os fluxos de trabalho e a usar os recursos do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="31870-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="31870-114">Este acesso à API requer autenticação do OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="31870-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="31870-115">Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="31870-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="31870-116">Em geral, você precisará executar as seguintes etapas para usar estas APIs:</span><span class="sxs-lookup"><span data-stu-id="31870-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="31870-117">Criar um aplicativo do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="31870-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="31870-118">Obtenha um token de acesso usando este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="31870-118">Get an access token using this application.</span></span>
- <span data-ttu-id="31870-119">Use o token para acessar a API do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="31870-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="31870-120">Este artigo explica como:</span><span class="sxs-lookup"><span data-stu-id="31870-120">This article explains how to:</span></span>

- <span data-ttu-id="31870-121">Criar um aplicativo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="31870-121">Create an Azure AD application</span></span>
- <span data-ttu-id="31870-122">Obter um token de acesso para o Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="31870-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="31870-123">Validar o token</span><span class="sxs-lookup"><span data-stu-id="31870-123">Validate the token</span></span>

> [!NOTE]
> <span data-ttu-id="31870-124">Ao acessar a API do Microsoft 365 defender em nome de um usuário, você precisará das permissões de aplicativo e permissões de usuário corretas.</span><span class="sxs-lookup"><span data-stu-id="31870-124">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct application permissions and user permissions.</span></span>

> [!TIP]
> <span data-ttu-id="31870-125">Se você tem a permissão para executar uma ação no portal, você tem a permissão para executar a ação na API.</span><span class="sxs-lookup"><span data-stu-id="31870-125">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="31870-126">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="31870-126">Create an app</span></span>

1. <span data-ttu-id="31870-127">Entre no [Azure](https://portal.azure.com) como um usuário com a função de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="31870-127">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="31870-128">Navegue até registro de aplicativo **do Azure Active Directory**  >    >  **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="31870-128">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="31870-130">No formulário, escolha um nome para o seu aplicativo e insira as seguintes informações para o URI de redirecionamento e, em seguida, selecione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="31870-130">In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.</span></span>

   ![Imagem da janela de criação de aplicativo](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="31870-132">**Tipo de aplicativo:** Cliente público</span><span class="sxs-lookup"><span data-stu-id="31870-132">**Application type:** Public client</span></span>
   - <span data-ttu-id="31870-133">**URI de redirecionamento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="31870-133">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="31870-134">Na página do aplicativo, selecione **permissões de API**  >  **Adicionar**  >  **APIs de permissão minha organização usa** >, digite **proteção contra ameaças da Microsoft** e selecione **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="31870-134">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="31870-135">Seu aplicativo agora pode acessar o Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="31870-135">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="31870-136">A *proteção contra ameaças da Microsoft* é um nome anterior para o Microsoft 365 defender e não aparecerá na lista original.</span><span class="sxs-lookup"><span data-stu-id="31870-136">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="31870-137">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.</span><span class="sxs-lookup"><span data-stu-id="31870-137">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagem da seleção de permissão de API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="31870-139">Escolha **permissões delegadas**.</span><span class="sxs-lookup"><span data-stu-id="31870-139">Choose **Delegated permissions**.</span></span> <span data-ttu-id="31870-140">Escolha as permissões relevantes para o seu cenário (por exemplo, **incidente. ler**) e selecione **adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="31870-140">Choose the relevant permissions for your scenario (for example **Incident.Read**), and then select **Add permissions**.</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > <span data-ttu-id="31870-142">Você precisa selecionar as permissões relevantes para o seu cenário.</span><span class="sxs-lookup"><span data-stu-id="31870-142">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="31870-143">*Ler todos os incidentes* é apenas um exemplo.</span><span class="sxs-lookup"><span data-stu-id="31870-143">*Read all incidents* is just an example.</span></span> <span data-ttu-id="31870-144">Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você deseja chamar.</span><span class="sxs-lookup"><span data-stu-id="31870-144">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="31870-145">Por exemplo, para [executar consultas avançadas](api-advanced-hunting.md), selecione a permissão "executar consultas avançadas"; para [isolar um dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecione a permissão "isolar máquina".</span><span class="sxs-lookup"><span data-stu-id="31870-145">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

5. <span data-ttu-id="31870-146">Selecione **conceder consentimento do administrador**.</span><span class="sxs-lookup"><span data-stu-id="31870-146">Select **Grant admin consent**.</span></span> <span data-ttu-id="31870-147">Toda vez que você adicionar uma permissão, deverá selecionar **conceder consentimento de administrador** para que ela entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="31870-147">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

   ![Imagem de conceder permissões](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="31870-149">Registre a ID do aplicativo e sua ID de locatário em algum lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="31870-149">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="31870-150">Eles estão listados em **visão geral** na página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="31870-150">They're listed under **Overview** on your application page.</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a><span data-ttu-id="31870-152">Obter um token de acesso</span><span class="sxs-lookup"><span data-stu-id="31870-152">Get an access token</span></span>

<span data-ttu-id="31870-153">Para obter mais informações sobre tokens do Azure Active Directory, consulte o [tutorial do Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="31870-153">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="31870-154">Obter um token de acesso usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="31870-154">Get an access token using PowerShell</span></span>

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

## <a name="validate-the-token"></a><span data-ttu-id="31870-155">Validar o token</span><span class="sxs-lookup"><span data-stu-id="31870-155">Validate the token</span></span>

1. <span data-ttu-id="31870-156">Copie e cole o token em [JWT](https://jwt.ms) para decodificá-lo.</span><span class="sxs-lookup"><span data-stu-id="31870-156">Copy and paste the token into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="31870-157">Certifique-se de que a declaração de *funções* dentro do token decodificado contenha as permissões desejadas.</span><span class="sxs-lookup"><span data-stu-id="31870-157">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="31870-158">Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, ```Incidents.Read.All``` com ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` as permissões e:</span><span class="sxs-lookup"><span data-stu-id="31870-158">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagem da validação do token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="31870-160">Usar o token para acessar a API do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="31870-160">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="31870-161">Escolha a API que você deseja usar (incidentes ou busca avançada).</span><span class="sxs-lookup"><span data-stu-id="31870-161">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="31870-162">Para obter mais informações, consulte [supported Microsoft 365 defender APIs](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="31870-162">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="31870-163">Na solicitação HTTP que você está prestes a enviar, defina o cabeçalho de autorização `"Bearer" <token>` , o *portador* como o esquema de autorização e o *token* que é o token validado.</span><span class="sxs-lookup"><span data-stu-id="31870-163">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="31870-164">O token expirará dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="31870-164">The token will expire within one hour.</span></span> <span data-ttu-id="31870-165">Você pode enviar mais de uma solicitação durante esse tempo com o mesmo token.</span><span class="sxs-lookup"><span data-stu-id="31870-165">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="31870-166">O exemplo a seguir mostra como enviar uma solicitação para obter uma lista de incidentes **usando C#**.</span><span class="sxs-lookup"><span data-stu-id="31870-166">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="31870-167">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="31870-167">Related articles</span></span>

- [<span data-ttu-id="31870-168">Visão geral das APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="31870-168">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="31870-169">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="31870-169">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="31870-170">Criar um aplicativo "Olá mundo"</span><span class="sxs-lookup"><span data-stu-id="31870-170">Create a 'Hello world' app</span></span>](api-hello-world.md)
- [<span data-ttu-id="31870-171">Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário</span><span class="sxs-lookup"><span data-stu-id="31870-171">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="31870-172">Criar um aplicativo com acesso de parceiro multilocatário às APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="31870-172">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="31870-173">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="31870-173">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="31870-174">Entender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="31870-174">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="31870-175">Autorização OAuth 2,0 para entrada de usuário e acesso à API</span><span class="sxs-lookup"><span data-stu-id="31870-175">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
