---
title: Criar um aplicativo para acessar a proteção contra ameaças da Microsoft sem um usuário
description: Saiba como criar um aplicativo para acessar a proteção contra ameaças da Microsoft sem um usuário
keywords: aplicativo, Access, API, criar
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
ms.openlocfilehash: 57ba0eb77ccb855cc0c0224b5321f11809e21ae8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201414"
---
# <a name="create-an-app-to-access-microsoft-threat-protection-without-a-user"></a><span data-ttu-id="025e4-104">Criar um aplicativo para acessar a proteção contra ameaças da Microsoft sem um usuário</span><span class="sxs-lookup"><span data-stu-id="025e4-104">Create an app to access Microsoft Threat Protection without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="025e4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="025e4-105">**Applies to:**</span></span>
- <span data-ttu-id="025e4-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="025e4-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="025e4-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="025e4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="025e4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="025e4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="025e4-109">Esta página descreve como criar um aplicativo para obter acesso programático à proteção contra ameaças da Microsoft sem um usuário.</span><span class="sxs-lookup"><span data-stu-id="025e4-109">This page describes how to create an application to get programmatic access to Microsoft Threat Protection without a user.</span></span> <span data-ttu-id="025e4-110">Se você precisar de acesso programático à proteção contra ameaças da Microsoft em nome de um usuário, consulte [obter acesso com contexto de usuário](api-create-app-user-context.md).</span><span class="sxs-lookup"><span data-stu-id="025e4-110">If you need programmatic access to Microsoft Threat Protection on behalf of a user, see [Get access with user context](api-create-app-user-context.md).</span></span> <span data-ttu-id="025e4-111">Se você não tiver certeza sobre qual acesso você precisa, consulte [introdução](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="025e4-111">If you are not sure which access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="025e4-112">A proteção contra ameaças da Microsoft expõe muito de seus dados e ações por meio de um conjunto de APIs de programação.</span><span class="sxs-lookup"><span data-stu-id="025e4-112">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="025e4-113">Essas APIs ajudarão você a automatizar fluxos de trabalho e inovar com base nos recursos de proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="025e4-113">Those APIs will help you automate work flows and innovate based on Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="025e4-114">O acesso à API requer autenticação do OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="025e4-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="025e4-115">Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="025e4-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="025e4-116">Em geral, você precisará executar as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="025e4-116">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="025e4-117">Criar um aplicativo do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="025e4-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="025e4-118">Obtenha um token de acesso usando este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="025e4-118">Get an access token using this application.</span></span>
- <span data-ttu-id="025e4-119">Use o token para acessar a API de proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="025e4-119">Use the token to access Microsoft Threat Protection API.</span></span>

<span data-ttu-id="025e4-120">Este artigo explica como criar um aplicativo do Azure AD, obter um token de acesso para a proteção contra ameaças da Microsoft e validar o token.</span><span class="sxs-lookup"><span data-stu-id="025e4-120">This article explains how to create an Azure AD application, get an access token to Microsoft Threat Protection, and validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="025e4-121">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="025e4-121">Create an app</span></span>

1. <span data-ttu-id="025e4-122">Faça logon no [Azure](https://portal.azure.com) com um usuário que tenha a função de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="025e4-122">Log on to [Azure](https://portal.azure.com) with a user that has the **Global Administrator** role.</span></span>

2. <span data-ttu-id="025e4-123">Navegue até registro de aplicativo **do Azure Active Directory**  >  **App registrations**  >  **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="025e4-123">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="025e4-125">No formulário de registro, escolha um nome para o aplicativo e, em seguida, selecione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="025e4-125">In the registration form, choose a name for your application, and then select **Register**.</span></span>

4. <span data-ttu-id="025e4-126">Para permitir que seu aplicativo acesse a proteção contra ameaças da Microsoft e atribuir permissões de ti, na página do aplicativo, selecione **permissões de API**  >  **Adicionar APIs de permissão**  >  **minha organização usa** >, digite **proteção contra ameaças da Microsoft**e selecione **proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="025e4-126">To enable your app to access Microsoft Threat Protection and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and then select **Microsoft Threat Protection**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="025e4-127">A proteção contra ameaças da Microsoft não aparece na lista original.</span><span class="sxs-lookup"><span data-stu-id="025e4-127">Microsoft Threat Protection does not appear in the original list.</span></span> <span data-ttu-id="025e4-128">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.</span><span class="sxs-lookup"><span data-stu-id="025e4-128">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="025e4-130">Selecionar **permissões de aplicativo** > escolha as permissões relevantes para o seu cenário, por exemplo, **Incident. Read. All**e, em seguida, selecione **adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="025e4-130">Select **Application permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read.All**, and then select **Add permissions**.</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

    >[!NOTE]
    ><span data-ttu-id="025e4-132">Você precisa selecionar as permissões relevantes para o seu cenário, **' ler todos os incidentes '** é apenas um exemplo.</span><span class="sxs-lookup"><span data-stu-id="025e4-132">You need to select the relevant permissions for your scenario, **'Read all incidents'** is just an example.</span></span> <span data-ttu-id="025e4-133">Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você está interessado em chamar.</span><span class="sxs-lookup"><span data-stu-id="025e4-133">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="025e4-134">Selecione **conceder consentimento**.</span><span class="sxs-lookup"><span data-stu-id="025e4-134">Select **Grant consent**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="025e4-135">Toda vez que você adicionar uma permissão, deverá selecionar **conceder consentimento** para que a nova permissão entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="025e4-135">Every time you add a permission, you must select **Grant consent** for the new permission to take effect.</span></span>

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

6. <span data-ttu-id="025e4-137">Para adicionar um segredo ao aplicativo, selecione **certificados & segredos**, adicione uma descrição ao segredo e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="025e4-137">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, and then select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="025e4-138">Depois de selecionar **Adicionar**, selecione **copiar o valor de segredo gerado**.</span><span class="sxs-lookup"><span data-stu-id="025e4-138">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="025e4-139">Você não poderá recuperar esse valor depois de sair.</span><span class="sxs-lookup"><span data-stu-id="025e4-139">You won't be able to retrieve this value after you leave.</span></span>

    ![Imagem da chave de criação de aplicativo](../../media/webapp-create-key2.png)

7. <span data-ttu-id="025e4-141">Anote a ID do aplicativo e a ID do locatário.</span><span class="sxs-lookup"><span data-stu-id="025e4-141">Write down your application ID and your tenant ID.</span></span> <span data-ttu-id="025e4-142">Na página do aplicativo, vá para **visão geral** e copie o seguinte.</span><span class="sxs-lookup"><span data-stu-id="025e4-142">On your application page, go to **Overview** and copy the following.</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

8. <span data-ttu-id="025e4-144">**Somente para parceiros de proteção contra ameaças da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="025e4-144">**For Microsoft Threat Protection Partners only**.</span></span> <span data-ttu-id="025e4-145">[Siga as instruções aqui](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span><span class="sxs-lookup"><span data-stu-id="025e4-145">[Follow the instructions here](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access).</span></span> <span data-ttu-id="025e4-146">Defina seu aplicativo como multilocatário (disponível em todos os locatários após o consentimento).</span><span class="sxs-lookup"><span data-stu-id="025e4-146">Set your app to be multi-tenanted (available in all tenants after consent).</span></span> <span data-ttu-id="025e4-147">Isso é **necessário** para aplicativos de terceiros (por exemplo, se você criar um aplicativo destinado a ser executado no locatário de vários clientes).</span><span class="sxs-lookup"><span data-stu-id="025e4-147">This is **required** for third-party apps (for example, if you create an app that is intended to run in multiple customers' tenant).</span></span> <span data-ttu-id="025e4-148">Isso **não é necessário** se você criar um serviço que deseja executar somente em seu locatário (por exemplo, se você criar um aplicativo para seu próprio uso que só interaja com seus próprios dados).</span><span class="sxs-lookup"><span data-stu-id="025e4-148">This is **not required** if you create a service that you want to run in your tenant only (for example, if you create an application for your own usage that will only interact with your own data).</span></span> <span data-ttu-id="025e4-149">Para definir seu aplicativo como multilocatários:</span><span class="sxs-lookup"><span data-stu-id="025e4-149">To set your app to be multi-tenanted:</span></span>

    - <span data-ttu-id="025e4-150">Vá para **autenticação**e adicione https://portal.azure.com como o **URI de redirecionamento**.</span><span class="sxs-lookup"><span data-stu-id="025e4-150">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="025e4-151">Na parte inferior da página, em **tipos de conta com suporte**, selecione as **contas em qualquer** consentimento de aplicativo de diretório organizacional para seu aplicativo de vários locatários.</span><span class="sxs-lookup"><span data-stu-id="025e4-151">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="025e4-152">Você precisa que seu aplicativo seja aprovado em cada locatário onde você pretende usá-lo.</span><span class="sxs-lookup"><span data-stu-id="025e4-152">You need your application to be approved in each tenant where you intend to use it.</span></span> <span data-ttu-id="025e4-153">Isso ocorre porque seu aplicativo interage com a proteção contra ameaças da Microsoft em nome de seu cliente.</span><span class="sxs-lookup"><span data-stu-id="025e4-153">This is because your application interacts Microsoft Threat Protection on behalf of your customer.</span></span>

    <span data-ttu-id="025e4-154">Você (ou seu cliente se estiver escrevendo um aplicativo de terceiros) precisará selecionar o link de consentimento e aprovar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="025e4-154">You (or your customer if you are writing a third-party app) need to select the consent link and approve your app.</span></span> <span data-ttu-id="025e4-155">O consentimento deve ser feito com um usuário que tenha privilégios administrativos no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="025e4-155">The consent should be done with a user who has administrative privileges in Active Directory.</span></span>

    <span data-ttu-id="025e4-156">O link de consentimento é formado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="025e4-156">The consent link is formed as follows:</span></span> 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="025e4-157">Em que 00000000-0000-0000-0000-000000000000 é substituído pela sua ID de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="025e4-157">Where 00000000-0000-0000-0000-000000000000 is replaced with your application ID.</span></span>


<span data-ttu-id="025e4-158">**Terminado!**</span><span class="sxs-lookup"><span data-stu-id="025e4-158">**Done!**</span></span> <span data-ttu-id="025e4-159">Você registrou com êxito um aplicativo!</span><span class="sxs-lookup"><span data-stu-id="025e4-159">You have successfully registered an application!</span></span> <span data-ttu-id="025e4-160">Confira os exemplos abaixo para obter uma aquisição de token e validação.</span><span class="sxs-lookup"><span data-stu-id="025e4-160">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="025e4-161">Obter um token de acesso</span><span class="sxs-lookup"><span data-stu-id="025e4-161">Get an access token</span></span>

<span data-ttu-id="025e4-162">Para obter mais detalhes sobre tokens do Azure AD, consulte o [tutorial do Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="025e4-162">For more details on Azure AD tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

### <a name="use-powershell"></a><span data-ttu-id="025e4-163">Usar o PowerShell</span><span class="sxs-lookup"><span data-stu-id="025e4-163">Use PowerShell</span></span>

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

### <a name="use-c"></a><span data-ttu-id="025e4-164">Use C#:</span><span class="sxs-lookup"><span data-stu-id="025e4-164">Use C#:</span></span>

<span data-ttu-id="025e4-165">O código a seguir foi testado com o NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="025e4-165">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="025e4-166">Criar um novo aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="025e4-166">Create a new console application.</span></span>
1. <span data-ttu-id="025e4-167">Instale [o NuGet Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="025e4-167">Install Nuget [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="025e4-168">Adicione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="025e4-168">Add the following:</span></span>

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="025e4-169">Copie e cole o código a seguir em seu aplicativo (não se esqueça de atualizar as três variáveis: ```tenantId, appId, appSecret``` ):</span><span class="sxs-lookup"><span data-stu-id="025e4-169">Copy and paste the following code in your app (don't forget to update the three variables: ```tenantId, appId, appSecret```):</span></span>

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a><span data-ttu-id="025e4-170">Usar Python</span><span class="sxs-lookup"><span data-stu-id="025e4-170">Use Python</span></span> 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a><span data-ttu-id="025e4-171">Rotação de uso</span><span class="sxs-lookup"><span data-stu-id="025e4-171">Use Curl</span></span>

> [!NOTE]
> <span data-ttu-id="025e4-172">O procedimento a seguir supõe que a rotação do Windows já está instalada no seu computador.</span><span class="sxs-lookup"><span data-stu-id="025e4-172">The following procedure assumes that Curl for Windows is already installed on your computer.</span></span>

1. <span data-ttu-id="025e4-173">Abra um prompt de comando e defina CLIENT_ID para sua ID de aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="025e4-173">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="025e4-174">Defina CLIENT_SECRET como seu segredo de aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="025e4-174">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="025e4-175">Defina TENANT_ID para a ID do locatário do Azure do cliente que deseja usar seu aplicativo para acessar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="025e4-175">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft Threat Protection.</span></span>
1. <span data-ttu-id="025e4-176">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="025e4-176">Run the following command:</span></span>

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="025e4-177">Você receberá uma resposta no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="025e4-177">You will get an answer in the following form:</span></span>

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="025e4-178">Validar o token</span><span class="sxs-lookup"><span data-stu-id="025e4-178">Validate the token</span></span>

<span data-ttu-id="025e4-179">Verifique se você recebeu o token correto:</span><span class="sxs-lookup"><span data-stu-id="025e4-179">Ensure that you got the correct token:</span></span>

1. <span data-ttu-id="025e4-180">Copie e cole o token obtido na etapa anterior em [JWT](https://jwt.ms) para decodificá-lo.</span><span class="sxs-lookup"><span data-stu-id="025e4-180">Copy and paste the token you got in the previous step into [JWT](https://jwt.ms) in order to decode it.</span></span>
1. <span data-ttu-id="025e4-181">Validar que você obtém uma declaração "Roles" com as permissões desejadas</span><span class="sxs-lookup"><span data-stu-id="025e4-181">Validate that you get a 'roles' claim with the desired permissions</span></span>
1. <span data-ttu-id="025e4-182">Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo ```Incidents.Read.All``` com ```Incidents.ReadWrite.All``` e ```AdvancedHunting.Read.All``` permissões:</span><span class="sxs-lookup"><span data-stu-id="025e4-182">In the following image, you can see a decoded token acquired from an app with ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagem da validação do token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-threat-protection-api"></a><span data-ttu-id="025e4-184">Usar o token para acessar a API de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="025e4-184">Use the token to access Microsoft Threat Protection API</span></span>

1. <span data-ttu-id="025e4-185">Escolha a API que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="025e4-185">Choose the API you want to use.</span></span> <span data-ttu-id="025e4-186">Confira mais informações em [APIs de proteção contra ameaças da Microsoft suportadas](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="025e4-186">For more information, see [Supported Microsoft Threat Protection APIs](api-supported.md).</span></span>

2. <span data-ttu-id="025e4-187">Defina o cabeçalho de autorização na solicitação HTTP que você envia para "portador {token}" (o portador é o esquema de autorização).</span><span class="sxs-lookup"><span data-stu-id="025e4-187">Set the authorization header in the http request you send to "Bearer {token}" (Bearer is the authorization scheme).</span></span>

3. <span data-ttu-id="025e4-188">O tempo de expiração do token é uma hora.</span><span class="sxs-lookup"><span data-stu-id="025e4-188">The expiration time of the token is one hour.</span></span> <span data-ttu-id="025e4-189">Você pode enviar mais de uma solicitação com o mesmo token.</span><span class="sxs-lookup"><span data-stu-id="025e4-189">You can send more then one request with the same token.</span></span>

<span data-ttu-id="025e4-190">Veja a seguir um exemplo de envio de uma solicitação para obter uma lista de incidentes **usando C#**:</span><span class="sxs-lookup"><span data-stu-id="025e4-190">The following is an example of sending a request to get a list of incidents **using C#**:</span></span> 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a><span data-ttu-id="025e4-191">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="025e4-191">Related topics</span></span>
- [<span data-ttu-id="025e4-192">Acessar as APIs de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="025e4-192">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="025e4-193">Acesso à proteção contra ameaças da Microsoft com contexto de aplicativo</span><span class="sxs-lookup"><span data-stu-id="025e4-193">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="025e4-194">Acesso à proteção contra ameaças da Microsoft com contexto de usuário</span><span class="sxs-lookup"><span data-stu-id="025e4-194">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
