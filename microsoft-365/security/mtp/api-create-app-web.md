---
title: Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário
description: Saiba como criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário.
keywords: app, access, api, create
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
ms.openlocfilehash: f438189b4ba9fb66124650782b3de2ee34dfee64
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928433"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a><span data-ttu-id="c21f1-104">Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário</span><span class="sxs-lookup"><span data-stu-id="c21f1-104">Create an app to access Microsoft 365 Defender without a user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c21f1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c21f1-105">**Applies to:**</span></span>

- <span data-ttu-id="c21f1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c21f1-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c21f1-107">Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="c21f1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c21f1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="c21f1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="c21f1-109">Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 Defender sem um usuário definido— por exemplo, se você estiver criando um daemon ou serviço em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="c21f1-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender without a defined user—for example, if you're creating a daemon or background service.</span></span>

<span data-ttu-id="c21f1-110">Se você precisar de acesso programático ao Microsoft 365 Defender em nome de um ou mais usuários, confira Criar um aplicativo para acessar as APIs do [Microsoft 365 Defender](api-create-app-user-context.md) em nome de um usuário e criar um aplicativo com acesso de parceiro às APIs do Microsoft [365 Defender.](api-partner-access.md)</span><span class="sxs-lookup"><span data-stu-id="c21f1-110">If you need programmatic access to Microsoft 365 Defender on behalf of one or more users, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md) and [Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md).</span></span> <span data-ttu-id="c21f1-111">Se você não tiver certeza de que tipo de acesso precisa, confira [Começar.](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c21f1-111">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="c21f1-112">O Microsoft 365 Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas.</span><span class="sxs-lookup"><span data-stu-id="c21f1-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="c21f1-113">Essas APIs ajudam a automatizar fluxos de trabalho e usar os recursos do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c21f1-113">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="c21f1-114">Esse acesso à API requer autenticação OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="c21f1-114">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="c21f1-115">Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="c21f1-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="c21f1-116">Em geral, você precisará seguir as seguintes etapas para usar essas APIs:</span><span class="sxs-lookup"><span data-stu-id="c21f1-116">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="c21f1-117">Crie um aplicativo do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c21f1-117">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="c21f1-118">Obter um token de acesso usando este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c21f1-118">Get an access token using this application.</span></span>
- <span data-ttu-id="c21f1-119">Use o token para acessar a API do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c21f1-119">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="c21f1-120">Este artigo explica como:</span><span class="sxs-lookup"><span data-stu-id="c21f1-120">This article explains how to:</span></span>

- <span data-ttu-id="c21f1-121">Criar um aplicativo do Azure AD</span><span class="sxs-lookup"><span data-stu-id="c21f1-121">Create an Azure AD application</span></span>
- <span data-ttu-id="c21f1-122">Obter um token de acesso para o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c21f1-122">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="c21f1-123">Valide o token.</span><span class="sxs-lookup"><span data-stu-id="c21f1-123">Validate the token.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="c21f1-124">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="c21f1-124">Create an app</span></span>

1. <span data-ttu-id="c21f1-125">Entre no [Azure como um](https://portal.azure.com) usuário com a função de Administrador **Global.**</span><span class="sxs-lookup"><span data-stu-id="c21f1-125">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="c21f1-126">Navegue até registros de aplicativo **do Azure Active Directory** Novo  >    >  **registro.**</span><span class="sxs-lookup"><span data-stu-id="c21f1-126">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagem do Microsoft Azure e navegação para o registro do aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="c21f1-128">In the form, choose a name for your application, then select **Register**.</span><span class="sxs-lookup"><span data-stu-id="c21f1-128">In the form, choose a name for your application, then select **Register**.</span></span>

4. <span data-ttu-id="c21f1-129">Na página do seu aplicativo, selecione Permissões de API Adicionar **APIs** de permissão que minha organização usa >, digite Proteção contra Ameaças da Microsoft e selecione  >    >   Proteção contra Ameaças **da Microsoft.** </span><span class="sxs-lookup"><span data-stu-id="c21f1-129">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="c21f1-130">Seu aplicativo agora pode acessar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c21f1-130">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="c21f1-131">*A Proteção contra* Ameaças da Microsoft é um nome antigo do Microsoft 365 Defender e não aparecerá na lista original.</span><span class="sxs-lookup"><span data-stu-id="c21f1-131">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="c21f1-132">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.</span><span class="sxs-lookup"><span data-stu-id="c21f1-132">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagem da seleção de permissão da API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="c21f1-134">Selecione **permissões de aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="c21f1-134">Select **Application permissions**.</span></span> <span data-ttu-id="c21f1-135">Escolha as permissões relevantes para seu cenário (por exemplo, **Incident.Read.All**) e, em seguida, **selecione Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="c21f1-135">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="c21f1-137">Você precisa selecionar as permissões relevantes para seu cenário.</span><span class="sxs-lookup"><span data-stu-id="c21f1-137">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="c21f1-138">*Ler todos os incidentes* é apenas um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c21f1-138">*Read all incidents* is just an example.</span></span> <span data-ttu-id="c21f1-139">Para determinar de que permissão você precisa, consulte a seção **Permissões** na API que você deseja chamar.</span><span class="sxs-lookup"><span data-stu-id="c21f1-139">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="c21f1-140">Por exemplo, para [executar consultas avançadas,](api-advanced-hunting.md)selecione a permissão "Executar consultas avançadas"; para [isolar um dispositivo,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecione a permissão "Isolar máquina".</span><span class="sxs-lookup"><span data-stu-id="c21f1-140">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="c21f1-141">Selecione **Conceder consentimento de administrador.**</span><span class="sxs-lookup"><span data-stu-id="c21f1-141">Select **Grant admin consent**.</span></span> <span data-ttu-id="c21f1-142">Sempre que adicionar uma permissão, você deve selecionar Conceder **consentimento de administrador** para que ela entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="c21f1-142">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

7. <span data-ttu-id="c21f1-144">Para adicionar um segredo ao aplicativo, selecione Certificados & **segredos,** adicione uma descrição ao segredo e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c21f1-144">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c21f1-145">Depois de selecionar **Adicionar,** selecione **copiar o valor secreto gerado.**</span><span class="sxs-lookup"><span data-stu-id="c21f1-145">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="c21f1-146">Você não poderá recuperar o valor secreto depois de sair.</span><span class="sxs-lookup"><span data-stu-id="c21f1-146">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Imagem de criar chave do aplicativo](../../media/webapp-create-key2.png)

8. <span data-ttu-id="c21f1-148">Grave sua ID de aplicativo e sua ID de locatário em algum lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="c21f1-148">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="c21f1-149">Eles estão listados em **Visão Geral** na página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c21f1-149">They're listed under **Overview** on your application page.</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="c21f1-151">Somente para parceiros do Microsoft [](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) **365 Defender:** siga estas instruções para acesso de parceiros por meio das APIs do Microsoft 365 Defender, de definidas como multi-locatários, para que ele possa estar disponível em todos os locatários depois que você receber o consentimento do administrador.</span><span class="sxs-lookup"><span data-stu-id="c21f1-151">**For Microsoft 365 Defender Partners only**: [Follow these instructions](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) for partner access through the Microsoft 365 Defender APIs, set your app to be multi-tenant, so it can be available in all tenants once you receive admin consent.</span></span> <span data-ttu-id="c21f1-152">O acesso de parceiros **é necessário** para aplicativos de terceiros— por exemplo, se você criar um aplicativo que se destina a ser executado em locatários de vários clientes.</span><span class="sxs-lookup"><span data-stu-id="c21f1-152">Partner access is **required** for third-party apps—for example, if you create an app that is intended to run in multiple customers' tenants.</span></span> <span data-ttu-id="c21f1-153">Não será **necessário se** você criar um serviço que deseja executar somente em seu locatário, como um aplicativo para seu próprio uso que só interagirá com seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="c21f1-153">It is **not required** if you create a service that you want to run in your tenant only, such as an application for your own usage that will only interact with your own data.</span></span> <span data-ttu-id="c21f1-154">Para definir seu aplicativo como multi-locatário:</span><span class="sxs-lookup"><span data-stu-id="c21f1-154">To set your app to be multi-tenant:</span></span>

    - <span data-ttu-id="c21f1-155">Vá para **Autenticação** e adicione https://portal.azure.com como o **URI de redirecionamento.**</span><span class="sxs-lookup"><span data-stu-id="c21f1-155">Go to **Authentication**, and add https://portal.azure.com as the **Redirect URI**.</span></span>

    - <span data-ttu-id="c21f1-156">Na parte inferior da página, em Tipos  de conta com **suporte,** selecione as Contas em qualquer consentimento do aplicativo de diretório organizacional para seu aplicativo multi-locatário.</span><span class="sxs-lookup"><span data-stu-id="c21f1-156">On the bottom of the page, under **Supported account types**, select the **Accounts in any organizational directory** application consent for your multi-tenant app.</span></span>

    <span data-ttu-id="c21f1-157">Como seu aplicativo interage com o Microsoft 365 Defender em nome de seus usuários, ele precisa ser aprovado para todos os locatários em que você pretende usá-lo.</span><span class="sxs-lookup"><span data-stu-id="c21f1-157">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

    <span data-ttu-id="c21f1-158">O administrador global do Active Directory para cada locatário precisa selecionar o link de consentimento e aprovar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c21f1-158">The Active Directory global admin for each tenant needs to select the consent link and approve your app.</span></span>

    <span data-ttu-id="c21f1-159">O link de consentimento tem a seguinte estrutura:</span><span class="sxs-lookup"><span data-stu-id="c21f1-159">The consent link has the following structure:</span></span>

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    <span data-ttu-id="c21f1-160">Os dígitos `00000000-0000-0000-0000-000000000000` devem ser substituídos pela ID do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c21f1-160">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>  

<span data-ttu-id="c21f1-161">**Pronto!**</span><span class="sxs-lookup"><span data-stu-id="c21f1-161">**Done!**</span></span> <span data-ttu-id="c21f1-162">Você registrou com êxito um aplicativo!</span><span class="sxs-lookup"><span data-stu-id="c21f1-162">You've successfully registered an application!</span></span> <span data-ttu-id="c21f1-163">Veja os exemplos abaixo para aquisição e validação de token.</span><span class="sxs-lookup"><span data-stu-id="c21f1-163">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="c21f1-164">Obter um token de acesso</span><span class="sxs-lookup"><span data-stu-id="c21f1-164">Get an access token</span></span>

<span data-ttu-id="c21f1-165">Para saber mais sobre tokens do Azure Active Directory, confira o [tutorial do Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)</span><span class="sxs-lookup"><span data-stu-id="c21f1-165">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c21f1-166">Embora os exemplos nesta seção incentivem você a colar valores  secretos para fins de teste, você nunca deve codificar segredos em um aplicativo em execução na produção.</span><span class="sxs-lookup"><span data-stu-id="c21f1-166">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="c21f1-167">Terceiros podem usar seu segredo para acessar recursos.</span><span class="sxs-lookup"><span data-stu-id="c21f1-167">A third party could use your secret to access resources.</span></span> <span data-ttu-id="c21f1-168">Você pode ajudar a manter os segredos do seu aplicativo seguros usando o [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="c21f1-168">You can help keep your app's secrets secure by using [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="c21f1-169">Para ver um exemplo prático de como você pode proteger seu aplicativo, confira Gerenciar segredos em seus aplicativos de servidor com o [Azure Key Vault.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)</span><span class="sxs-lookup"><span data-stu-id="c21f1-169">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="c21f1-170">Obter um token de acesso usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="c21f1-170">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$tenantId/oauth2/token"

$authBody = [Ordered] @{
    resource = $resourceAppIdUri
    client_id = $clientId
    client_secret = $appSecret
    grant_type = 'client_credentials'
}

$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token

Out-File -FilePath "./Latest-token.txt" -InputObject $token

return $token
```

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="c21f1-171">Obter um token de acesso usando C\#</span><span class="sxs-lookup"><span data-stu-id="c21f1-171">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="c21f1-172">O código a seguir foi testado com Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="c21f1-172">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="c21f1-173">Crie um novo aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="c21f1-173">Create a new console application.</span></span>

1. <span data-ttu-id="c21f1-174">Instale o NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="c21f1-174">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>

1. <span data-ttu-id="c21f1-175">Adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="c21f1-175">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="c21f1-176">Copie e colar o seguinte código em seu aplicativo (não se esqueça de atualizar as três variáveis: `tenantId` , `clientId` `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="c21f1-176">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

    ```C#
    string tenantId = ""; // Paste your directory (tenant) ID here
    string clientId = ""; // Paste your application (client) ID here
    string appSecret = ""; // Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(clientId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="c21f1-177">Obter um token de acesso usando o Python</span><span class="sxs-lookup"><span data-stu-id="c21f1-177">Get an access token using Python</span></span>

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : clientId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="c21f1-178">Obter um token de acesso usando o token de acesso</span><span class="sxs-lookup"><span data-stu-id="c21f1-178">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="c21f1-179">O Windows 10, versões 1803 e posteriores, foi pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="c21f1-179">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="c21f1-180">Para outras versões do Windows, baixe e instale a ferramenta diretamente do [site oficial do website.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="c21f1-180">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="c21f1-181">Abra um prompt de comando e de definida CLIENT_ID sua ID de aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="c21f1-181">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>

1. <span data-ttu-id="c21f1-182">De CLIENT_SECRET seu segredo do aplicativo Azure.</span><span class="sxs-lookup"><span data-stu-id="c21f1-182">Set CLIENT_SECRET to your Azure application secret.</span></span>

1. <span data-ttu-id="c21f1-183">De TENANT_ID a ID de locatário do Azure do cliente que deseja usar seu aplicativo para acessar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="c21f1-183">Set TENANT_ID to the Azure tenant ID of the customer that wants to use your app to access Microsoft 365 Defender.</span></span>

1. <span data-ttu-id="c21f1-184">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c21f1-184">Run the following command:</span></span>

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   <span data-ttu-id="c21f1-185">Uma resposta bem-sucedida terá a aparência a seguir:</span><span class="sxs-lookup"><span data-stu-id="c21f1-185">A successful response will look like this:</span></span>

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a><span data-ttu-id="c21f1-186">Validar o token</span><span class="sxs-lookup"><span data-stu-id="c21f1-186">Validate the token</span></span>

1. <span data-ttu-id="c21f1-187">Copie e colar o token no site do validador de [token Web JSON, JWT,](https://jwt.ms) para decodificá-lo.</span><span class="sxs-lookup"><span data-stu-id="c21f1-187">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>

1. <span data-ttu-id="c21f1-188">Certifique-se de *que a* declaração de funções dentro do token decodificado contém as permissões desejadas.</span><span class="sxs-lookup"><span data-stu-id="c21f1-188">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

   <span data-ttu-id="c21f1-189">Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, com `Incidents.Read.All` `Incidents.ReadWrite.All` , e `AdvancedHunting.Read.All` permissões:</span><span class="sxs-lookup"><span data-stu-id="c21f1-189">In the following image, you can see a decoded token acquired from an app, with `Incidents.Read.All`, `Incidents.ReadWrite.All`, and `AdvancedHunting.Read.All` permissions:</span></span>

   ![Imagem de validação de token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="c21f1-191">Usar o token para acessar a API do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c21f1-191">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="c21f1-192">Escolha a API que você deseja usar (incidentes ou busca avançada).</span><span class="sxs-lookup"><span data-stu-id="c21f1-192">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="c21f1-193">Para saber mais, confira [AS APIs do Microsoft 365 Defender com suporte.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="c21f1-193">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

2. <span data-ttu-id="c21f1-194">Na solicitação http que você está prestes a enviar, de definir o cabeçalho de autorização como , portador sendo o esquema de autorização e token sendo `"Bearer" <token>` seu token  validado. </span><span class="sxs-lookup"><span data-stu-id="c21f1-194">In the http request you are about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>

3. <span data-ttu-id="c21f1-195">O token expirará dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="c21f1-195">The token will expire within one hour.</span></span> <span data-ttu-id="c21f1-196">Você pode enviar mais de uma solicitação durante esse período com o mesmo token.</span><span class="sxs-lookup"><span data-stu-id="c21f1-196">You can send more than one request during this time with the same token.</span></span>

<span data-ttu-id="c21f1-197">O exemplo a seguir mostra como enviar uma solicitação para obter uma lista de incidentes **usando C#**.</span><span class="sxs-lookup"><span data-stu-id="c21f1-197">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="c21f1-198">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c21f1-198">Related articles</span></span>

- [<span data-ttu-id="c21f1-199">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c21f1-199">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="c21f1-200">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c21f1-200">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c21f1-201">Criar um aplicativo "Hello world"</span><span class="sxs-lookup"><span data-stu-id="c21f1-201">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="c21f1-202">Criar um aplicativo para acessar as APIs do Microsoft 365 Defender em nome de um usuário</span><span class="sxs-lookup"><span data-stu-id="c21f1-202">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="c21f1-203">Criar um aplicativo com acesso de parceiro multi-locatário às APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c21f1-203">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="c21f1-204">Saiba mais sobre limites e licenciamento de API</span><span class="sxs-lookup"><span data-stu-id="c21f1-204">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c21f1-205">Noções sobre códigos de erro</span><span class="sxs-lookup"><span data-stu-id="c21f1-205">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="c21f1-206">Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="c21f1-206">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="c21f1-207">Autorização do OAuth 2.0 para entrada do usuário e acesso à API</span><span class="sxs-lookup"><span data-stu-id="c21f1-207">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
