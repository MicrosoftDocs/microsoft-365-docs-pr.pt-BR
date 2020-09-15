---
title: Acesso de parceiros por meio das APIs de proteção contra ameaças da Microsoft
description: Saiba como criar um aplicativo AAD para obter acesso programático à proteção contra ameaças da Microsoft em nome de seus clientes
keywords: parceiro, Access, API, multilocatário, consentimento, token de acesso, aplicativo
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
ms.openlocfilehash: d78996c0cd37a6b82edde52367b04647560d5cf7
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650105"
---
# <a name="partner-access-through-microsoft-threat-protection-apis"></a><span data-ttu-id="e7fa9-104">Acesso de parceiros por meio das APIs de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fa9-104">Partner access through Microsoft Threat Protection APIs</span></span>

<span data-ttu-id="e7fa9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e7fa9-105">**Applies to:**</span></span>
- <span data-ttu-id="e7fa9-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fa9-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="e7fa9-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e7fa9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="e7fa9-109">Esta página descreve como criar um aplicativo AAD para obter acesso programático à proteção contra ameaças da Microsoft em nome de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-109">This page describes how to create an AAD application to get programmatic access to Microsoft Threat Protection on behalf of your customers.</span></span>

<span data-ttu-id="e7fa9-110">A proteção contra ameaças da Microsoft expõe muito de seus dados e ações por meio de um conjunto de APIs de programação.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-110">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="e7fa9-111">Essas APIs ajudarão você a automatizar fluxos de trabalho e inovar com base nos recursos de proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-111">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="e7fa9-112">O acesso à API requer autenticação do OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-112">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="e7fa9-113">Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="e7fa9-113">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="e7fa9-114">Em geral, você precisará executar as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-114">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="e7fa9-115">Criar um aplicativo AAD **de vários locatários** .</span><span class="sxs-lookup"><span data-stu-id="e7fa9-115">Create a **multi-tenant** AAD application.</span></span>
- <span data-ttu-id="e7fa9-116">Obtenha autorização (consentimento) pelo administrador do cliente para seu aplicativo para acessar os recursos de proteção contra ameaças da Microsoft necessários.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-116">Get authorized (consent) by your customer administrator for your application to access Microsoft Threat Protection resources it needs.</span></span>
- <span data-ttu-id="e7fa9-117">Obtenha um token de acesso usando este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-117">Get an access token using this application.</span></span>
- <span data-ttu-id="e7fa9-118">Use o token para acessar a API de proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-118">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="e7fa9-119">As etapas a seguir orientam como criar um aplicativo AAD, obter um token de acesso para a proteção contra ameaças da Microsoft e validar o token.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-119">The following steps with guide you how to create an AAD application, get an access token to Microsoft Threat Protection and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="e7fa9-120">Criar o aplicativo multilocatário</span><span class="sxs-lookup"><span data-stu-id="e7fa9-120">Create the multi-tenant app</span></span>

1. <span data-ttu-id="e7fa9-121">Faça logon em seu [locatário do Azure](https://portal.azure.com) com um usuário com função de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="e7fa9-121">Log on to your [Azure tenant](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="e7fa9-122">Navegue até registro de aplicativo **do Azure Active Directory**  >  **App registrations**  >  **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-122">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="e7fa9-124">No formulário de registro:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-124">In the registration form:</span></span>

    - <span data-ttu-id="e7fa9-125">Escolha um nome para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-125">Choose a name for your application.</span></span>

    - <span data-ttu-id="e7fa9-126">Tipos de conta com suporte – contas em qualquer diretório organizacional.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-126">Supported account types - accounts in any organizational directory.</span></span>

    - <span data-ttu-id="e7fa9-127">Redirecionar URI-tipo: Web, URI: https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="e7fa9-127">Redirect URI - type: Web, URI: https://portal.azure.com</span></span>

    ![Imagem do registro do aplicativo parceiro do Microsoft Azure](../../media/atp-api-new-app-partner.png)


4. <span data-ttu-id="e7fa9-129">Permita que seu aplicativo acesse a proteção contra ameaças da Microsoft e atribua-o com o conjunto mínimo de permissões necessárias para a conclusão da integração.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-129">Allow your Application to access Microsoft Threat Protection and assign it with the minimal set of permissions required to complete the integration.</span></span>

   - <span data-ttu-id="e7fa9-130">Na página do aplicativo, clique em **permissões de API**  >  **Adicionar**APIs de permissão  >  **minha organização usa** > digite **proteção contra ameaças da Microsoft** e clique em **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-130">On your application page, click **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft Threat Protection** and click on **Microsoft Threat Protection**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="e7fa9-131">A proteção contra ameaças da Microsoft não aparece na lista original.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-131">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="e7fa9-132">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)
   
   ### <a name="request-api-permissions"></a><span data-ttu-id="e7fa9-134">Solicitar permissões de API</span><span class="sxs-lookup"><span data-stu-id="e7fa9-134">Request API permissions</span></span>

   <span data-ttu-id="e7fa9-135">Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você está interessado em chamar.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-135">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span> 

   <span data-ttu-id="e7fa9-136">No exemplo a seguir, usaremos a permissão **"ler todos os incidentes"** :</span><span class="sxs-lookup"><span data-stu-id="e7fa9-136">In the following example we will use **'Read all incidents'** permission:</span></span>

   <span data-ttu-id="e7fa9-137">Escolha **aplicativos permissões**  >  **incidentes. Read. All** > clique em **adicionar permissões**</span><span class="sxs-lookup"><span data-stu-id="e7fa9-137">Choose **Application permissions** > **Incidents.Read.All** > Click on **Add permissions**</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)


5. <span data-ttu-id="e7fa9-139">Clique em **conceder consentimento**</span><span class="sxs-lookup"><span data-stu-id="e7fa9-139">Click **Grant consent**</span></span>

    >[!NOTE]
    ><span data-ttu-id="e7fa9-140">Toda vez que você adicionar permissão, deverá clicar em **conceder consentimento** para que a nova permissão entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-140">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

6. <span data-ttu-id="e7fa9-142">Adicione um segredo ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-142">Add a secret to the application.</span></span>

    - <span data-ttu-id="e7fa9-143">Clique em **certificados & segredos**, adicione descrição ao segredo e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-143">Click **Certificates & secrets**, add description to the secret and click **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="e7fa9-144">Depois de selecionar **Adicionar**, **Copie o valor de segredo gerado**.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-144">After selecting **Add**, **copy the generated secret value**.</span></span> <span data-ttu-id="e7fa9-145">Você não poderá recuperar após sair!</span><span class="sxs-lookup"><span data-stu-id="e7fa9-145">You won't be able to retrieve after you leave!</span></span>

    ![Imagem da chave de criação de aplicativo](../../media/webapp-create-key2.png)

7. <span data-ttu-id="e7fa9-147">Anote sua ID de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-147">Write down your application ID:</span></span>

   - <span data-ttu-id="e7fa9-148">Na página do aplicativo, vá para **visão geral** e copie o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-148">On your application page, go to **Overview** and copy the following:</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-id.png)

8. <span data-ttu-id="e7fa9-150">Adicione o aplicativo ao locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-150">Add the application to your customer's tenant.</span></span>

    <span data-ttu-id="e7fa9-151">Você precisa que seu aplicativo seja aprovado em cada locatário do cliente onde você pretende usá-lo.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-151">You need your application to be approved in each customer tenant where you intend to use it.</span></span> <span data-ttu-id="e7fa9-152">Isso se deve ao fato de o aplicativo interagir com o aplicativo proteção contra ameaças da Microsoft em nome de seu cliente.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-152">This is because your application interacts with Microsoft Threat Protection application on behalf of your customer.</span></span>

    <span data-ttu-id="e7fa9-153">Um usuário com **administrador global** do locatário do cliente precisa clicar no link de consentimento e aprovar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-153">A user with **Global Administrator** from your customer's tenant need to click the consent link and approve your application.</span></span>

    <span data-ttu-id="e7fa9-154">O link de consentimento tem o formato:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-154">Consent link is of the form:</span></span>

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="e7fa9-155">Onde 00000000-0000-0000-0000-000000000000 deve ser substituído por sua ID de aplicativo</span><span class="sxs-lookup"><span data-stu-id="e7fa9-155">Where 00000000-0000-0000-0000-000000000000 should be replaced with your Application ID</span></span>

    <span data-ttu-id="e7fa9-156">Após clicar no link de consentimento, faça logon com o administrador global do locatário do cliente e concorde com o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-156">After clicking on the consent link, login with the Global Administrator of the customer's tenant and consent the application.</span></span>

    ![Imagem de consentimento](../../media/app-consent-partner.png)

    <span data-ttu-id="e7fa9-158">Além disso, você precisará solicitar sua ID de locatário ao cliente e salvá-lo para uso futuro ao adquirir o token.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-158">In addition, you will need to ask your customer for their tenant ID and save it for future use when acquiring the token.</span></span>

- <span data-ttu-id="e7fa9-159">**Terminado!**</span><span class="sxs-lookup"><span data-stu-id="e7fa9-159">**Done!**</span></span> <span data-ttu-id="e7fa9-160">Você registrou com êxito um aplicativo!</span><span class="sxs-lookup"><span data-stu-id="e7fa9-160">You have successfully registered an application!</span></span> 
- <span data-ttu-id="e7fa9-161">Confira os exemplos abaixo para obter uma aquisição de token e validação.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-161">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token-examples"></a><span data-ttu-id="e7fa9-162">Obtenha exemplos de token de acesso:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-162">Get an access token examples:</span></span>

>[!NOTE]
> <span data-ttu-id="e7fa9-163">Para obter o token de acesso em nome de seu cliente, use a ID de locatário do cliente nas aquisições de token a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-163">To get access token on behalf of your customer, use the customer's tenant ID on the following token acquisitions.</span></span>

<br><span data-ttu-id="e7fa9-164">Para obter mais detalhes sobre o token do AAD, consulte [tutorial do AAD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="e7fa9-164">For more details on AAD token, refer to [AAD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span></span>

### <a name="using-powershell"></a><span data-ttu-id="e7fa9-165">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7fa9-165">Using PowerShell</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="using-c"></a><span data-ttu-id="e7fa9-166">Usando C#:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-166">Using C#:</span></span>

><span data-ttu-id="e7fa9-167">O código a seguir foi testado com o NuGet Microsoft. IdentityModel. clients. ActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="e7fa9-167">The below code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory</span></span>

- <span data-ttu-id="e7fa9-168">Criar um novo aplicativo de console</span><span class="sxs-lookup"><span data-stu-id="e7fa9-168">Create a new Console Application</span></span>
- <span data-ttu-id="e7fa9-169">Instalar [o NuGet Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span><span class="sxs-lookup"><span data-stu-id="e7fa9-169">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)</span></span>
- <span data-ttu-id="e7fa9-170">Adicione o seguinte usando</span><span class="sxs-lookup"><span data-stu-id="e7fa9-170">Add the below using</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

- <span data-ttu-id="e7fa9-171">Copie/cole o código abaixo em seu aplicativo (não se esqueça de atualizar as 3 variáveis: ```tenantId, appId, appSecret``` )</span><span class="sxs-lookup"><span data-stu-id="e7fa9-171">Copy/Paste the below code in your application (do not forget to update the 3 variables: ```tenantId, appId, appSecret```)</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string mtpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(mtpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```



### <a name="using-curl"></a><span data-ttu-id="e7fa9-172">Usando a ondulação</span><span class="sxs-lookup"><span data-stu-id="e7fa9-172">Using Curl</span></span>

> [!NOTE]
> <span data-ttu-id="e7fa9-173">O procedimento a seguir deve ser enrolado para o Windows já está instalado no computador</span><span class="sxs-lookup"><span data-stu-id="e7fa9-173">The below procedure supposed Curl for Windows is already installed on your computer</span></span>

- <span data-ttu-id="e7fa9-174">Abrir uma janela de comando</span><span class="sxs-lookup"><span data-stu-id="e7fa9-174">Open a command window</span></span>
- <span data-ttu-id="e7fa9-175">Definir CLIENT_ID para sua ID de aplicativo do Azure</span><span class="sxs-lookup"><span data-stu-id="e7fa9-175">Set CLIENT_ID to your Azure application ID</span></span>
- <span data-ttu-id="e7fa9-176">Definir CLIENT_SECRET como seu segredo de aplicativo do Azure</span><span class="sxs-lookup"><span data-stu-id="e7fa9-176">Set CLIENT_SECRET to your Azure application secret</span></span>
- <span data-ttu-id="e7fa9-177">Defina TENANT_ID para a ID do locatário do Azure do cliente que deseja usar seu aplicativo para acessar o aplicativo de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fa9-177">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your application to access Microsoft Threat Protection application</span></span>
- <span data-ttu-id="e7fa9-178">Execute o comando abaixo:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-178">Run the below command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="e7fa9-179">Você receberá uma resposta da forma:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-179">You will get an answer of the form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="e7fa9-180">Validar o token</span><span class="sxs-lookup"><span data-stu-id="e7fa9-180">Validate the token</span></span>

<span data-ttu-id="e7fa9-181">Verificação de sanidade para garantir que você recebeu um token correto:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-181">Sanity check to make sure you got a correct token:</span></span>

- <span data-ttu-id="e7fa9-182">Copiar/colar no [JWT](https://jwt.ms) o token obtido na etapa anterior para decodificá-lo</span><span class="sxs-lookup"><span data-stu-id="e7fa9-182">Copy/paste into [JWT](https://jwt.ms) the token you get in the previous step in order to decode it</span></span>
- <span data-ttu-id="e7fa9-183">Validar você obtém uma declaração "Roles" com as permissões desejadas</span><span class="sxs-lookup"><span data-stu-id="e7fa9-183">Validate you get a 'roles' claim with the desired permissions</span></span>
- <span data-ttu-id="e7fa9-184">Na captura de tela a seguir, você pode ver um token decodificado adquirido de um aplicativo com várias permissões para a proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="e7fa9-184">In the screenshot below, you can see a decoded token acquired from an Application with multiple permissions to Microsoft Threat Protection:</span></span>
- <span data-ttu-id="e7fa9-185">A declaração "tid" é a ID do locatário à qual o token pertence.</span><span class="sxs-lookup"><span data-stu-id="e7fa9-185">The "tid" claim is the tenant ID the token belongs to.</span></span>

![Imagem da validação do token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="e7fa9-187">Usar o token para acessar a API de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fa9-187">Use the token to access Microsoft Threat Protection API</span></span>

- <span data-ttu-id="e7fa9-188">Escolha a API que você deseja usar, para saber mais, confira [APIs de proteção contra ameaças da Microsoft compatíveis](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="e7fa9-188">Choose the API you want to use, for more information, see [Supported Microsoft Threat Protection APIs](api-supported.md)</span></span>
- <span data-ttu-id="e7fa9-189">Definir o cabeçalho de autorização na solicitação HTTP que você envia para "portador {token}" (o portador é o esquema de autorização)</span><span class="sxs-lookup"><span data-stu-id="e7fa9-189">Set the Authorization header in the Http request you send to "Bearer {token}" (Bearer is the Authorization scheme)</span></span>
- <span data-ttu-id="e7fa9-190">O tempo de expiração do token é de 1 hora (você pode enviar mais de uma solicitação com o mesmo token)</span><span class="sxs-lookup"><span data-stu-id="e7fa9-190">The Expiration time of the token is 1 hour (you can send more then one request with the same token)</span></span>

- <span data-ttu-id="e7fa9-191">Exemplo de envio de uma solicitação para obter uma lista de incidentes **usando C#**</span><span class="sxs-lookup"><span data-stu-id="e7fa9-191">Example of sending a request to get a list of incidents **using C#**</span></span> 
    ```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="related-topics"></a><span data-ttu-id="e7fa9-192">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7fa9-192">Related topics</span></span> 

- [<span data-ttu-id="e7fa9-193">Acessar as APIs de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e7fa9-193">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="e7fa9-194">Acesso à proteção contra ameaças da Microsoft com contexto de aplicativo</span><span class="sxs-lookup"><span data-stu-id="e7fa9-194">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="e7fa9-195">Acesso à proteção contra ameaças da Microsoft com contexto de usuário</span><span class="sxs-lookup"><span data-stu-id="e7fa9-195">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
