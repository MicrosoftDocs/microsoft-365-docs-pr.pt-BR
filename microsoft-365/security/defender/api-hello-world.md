---
title: Hello World para a API REST do Microsoft 365 Defender
description: Saiba como criar um aplicativo e usar um token para acessar as APIs do Microsoft 365 Defender
keywords: app, token, access, aad, app, application registration, powershell, script, administrador global, permission, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ffdcf91da6b5def7d63e5fdb8ff51ddbdb1ec550
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053513"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="9cb27-104">Hello World para a API REST do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb27-104">Hello World for Microsoft 365 Defender REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9cb27-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9cb27-105">**Applies to:**</span></span>

- <span data-ttu-id="9cb27-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb27-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cb27-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="9cb27-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9cb27-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="9cb27-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="9cb27-109">Obter incidentes usando um script simples do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9cb27-109">Get incidents using a simple PowerShell script</span></span>

<span data-ttu-id="9cb27-110">Deve levar de 5 a 10 minutos para concluir esse projeto.</span><span class="sxs-lookup"><span data-stu-id="9cb27-110">It should take 5 to 10 minutes to complete this project.</span></span> <span data-ttu-id="9cb27-111">Essa estimativa de tempo inclui o registro do aplicativo e a aplicação do código do script de exemplo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cb27-111">This time estimate includes registering the application, and applying the code from the PowerShell sample script.</span></span>

### <a name="register-an-app-in-azure-active-directory"></a><span data-ttu-id="9cb27-112">Registrar um aplicativo no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9cb27-112">Register an app in Azure Active Directory</span></span>

1. <span data-ttu-id="9cb27-113">Entre no [Azure](https://portal.azure.com) como um usuário com a **função de administrador** global.</span><span class="sxs-lookup"><span data-stu-id="9cb27-113">Sign in to [Azure](https://portal.azure.com) as a user with the **Global administrator** role.</span></span>

2. <span data-ttu-id="9cb27-114">Navegue **até registros do Aplicativo do Azure Active Directory** Novo  >    >  **registro**.</span><span class="sxs-lookup"><span data-stu-id="9cb27-114">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagem do Microsoft Azure e navegação para registro de aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="9cb27-116">No formulário de registro, escolha um nome para seu aplicativo e selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="9cb27-116">In the registration form, choose a name for your application, then select **Register**.</span></span> <span data-ttu-id="9cb27-117">Selecionar um URI de redirecionamento é opcional.</span><span class="sxs-lookup"><span data-stu-id="9cb27-117">Selecting a redirect URI is optional.</span></span> <span data-ttu-id="9cb27-118">Você não precisará de um para concluir este exemplo.</span><span class="sxs-lookup"><span data-stu-id="9cb27-118">You won't need one to complete this example.</span></span>

4. <span data-ttu-id="9cb27-119">Em sua página de aplicativo, selecione **Permissões** de API Adicionar  >    >  **APIs** de permissão que minha organização usa >, digite Proteção contra Ameaças da Microsoft e selecione Proteção contra Ameaças da Microsoft .</span><span class="sxs-lookup"><span data-stu-id="9cb27-119">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="9cb27-120">Seu aplicativo agora pode acessar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="9cb27-120">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="9cb27-121">*A Proteção contra Ameaças* da Microsoft é um nome antigo do Microsoft 365 Defender e não aparecerá na lista original.</span><span class="sxs-lookup"><span data-stu-id="9cb27-121">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="9cb27-122">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.</span><span class="sxs-lookup"><span data-stu-id="9cb27-122">You need to start writing its name in the text box to see it appear.</span></span>
   <span data-ttu-id="9cb27-123">![Imagem da seleção de permissão da API](../../media/apis-in-my-org-tab.PNG)</span><span class="sxs-lookup"><span data-stu-id="9cb27-123">![Image of API permission selection](../../media/apis-in-my-org-tab.PNG)</span></span>

   - <span data-ttu-id="9cb27-124">Escolha **Permissões de aplicativo**  >  **Incident.Read.All** e selecione Adicionar **permissões**.</span><span class="sxs-lookup"><span data-stu-id="9cb27-124">Choose **Application permissions** > **Incident.Read.All** and select **Add permissions**.</span></span>

   ![Imagem do acesso à API e seleção de API](../../media/request-api-permissions.PNG)

5. <span data-ttu-id="9cb27-126">Selecione **Conceder consentimento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="9cb27-126">Select **Grant admin consent**.</span></span> <span data-ttu-id="9cb27-127">Sempre que você adicionar uma permissão, você deve selecionar **Conceder consentimento de administrador** para que ela entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="9cb27-127">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Imagem de Permissões de Concessão](../../media/grant-consent.PNG)

6. <span data-ttu-id="9cb27-129">Adicione um segredo ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9cb27-129">Add a secret to the application.</span></span> <span data-ttu-id="9cb27-130">Selecione **Certificados & segredos,** adicione uma descrição ao segredo e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9cb27-130">Select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9cb27-131">Depois de selecionar **Adicionar**, selecione **copiar o valor secreto gerado.**</span><span class="sxs-lookup"><span data-stu-id="9cb27-131">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="9cb27-132">Você não poderá recuperar o valor secreto depois de sair.</span><span class="sxs-lookup"><span data-stu-id="9cb27-132">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Imagem de criar chave de aplicativo](../../media/webapp-create-key2.png)

7. <span data-ttu-id="9cb27-134">Grave sua ID de aplicativo e sua ID de locatário em algum lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="9cb27-134">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="9cb27-135">Eles estão listados em **Visão Geral** na página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9cb27-135">They're listed under **Overview** on your application page.</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a><span data-ttu-id="9cb27-137">Obter um token usando o aplicativo e usar o token para acessar a API</span><span class="sxs-lookup"><span data-stu-id="9cb27-137">Get a token using the app and use the token to access the API</span></span>

<span data-ttu-id="9cb27-138">Para obter mais informações sobre tokens do Azure Active Directory, consulte o tutorial do [Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="9cb27-138">For more information on Azure Active Directory tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cb27-139">Embora o exemplo neste aplicativo de demonstração incentive você a colar  seu valor secreto para fins de teste, você nunca deve codificar segredos em um aplicativo em execução em produção.</span><span class="sxs-lookup"><span data-stu-id="9cb27-139">Although the example in this demo app encourage you to paste in your secret value for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="9cb27-140">Um terceiro pode usar seu segredo para acessar recursos.</span><span class="sxs-lookup"><span data-stu-id="9cb27-140">A third party could use your secret to access resources.</span></span> <span data-ttu-id="9cb27-141">Você pode ajudar a manter os segredos do seu aplicativo seguros usando o [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="9cb27-141">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="9cb27-142">Para ver um exemplo prático de como proteger seu aplicativo, consulte Gerenciar segredos em seus aplicativos de servidor com o [Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="9cb27-142">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

1. <span data-ttu-id="9cb27-143">Copie o script abaixo e o colar no editor de texto favorito.</span><span class="sxs-lookup"><span data-stu-id="9cb27-143">Copy the script below and paste it into your favorite text editor.</span></span> <span data-ttu-id="9cb27-144">Salve como **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="9cb27-144">Save as **Get-Token.ps1**.</span></span> <span data-ttu-id="9cb27-145">Você também pode executar o código como está no ISE do PowerShell, mas você deve salvá-lo, pois precisamos executar novamente quando usarmos o script de busca de incidentes na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="9cb27-145">You can also run the code as-is in PowerShell ISE, but you should save it, because we'll need to run it again when we use the incident-fetching script in the next section.</span></span>

    <span data-ttu-id="9cb27-146">Esse script gerará um token e o salvará na pasta de trabalho sob o nome, *Latest-token.txt*.</span><span class="sxs-lookup"><span data-stu-id="9cb27-146">This script will generate a token and save it in the working folder under the name, *Latest-token.txt*.</span></span>

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a><span data-ttu-id="9cb27-147">Validar o token</span><span class="sxs-lookup"><span data-stu-id="9cb27-147">Validate the token</span></span>

1. <span data-ttu-id="9cb27-148">Copie e colar o token recebido em [JWT](https://jwt.ms) para decodificá-lo.</span><span class="sxs-lookup"><span data-stu-id="9cb27-148">Copy and paste the token you received into [JWT](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="9cb27-149">*JWT* significa *JSON Web Token*.</span><span class="sxs-lookup"><span data-stu-id="9cb27-149">*JWT* stands for *JSON Web Token*.</span></span> <span data-ttu-id="9cb27-150">O token decodificado conterá um número de itens ou declarações formatados por JSON.</span><span class="sxs-lookup"><span data-stu-id="9cb27-150">The decoded token will contain a number of JSON-formatted items or claims.</span></span> <span data-ttu-id="9cb27-151">Certifique-se de que *as funções* de declaração dentro do token decodificado contenham as permissões desejadas.</span><span class="sxs-lookup"><span data-stu-id="9cb27-151">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

    <span data-ttu-id="9cb27-152">Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, com ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` permissões:</span><span class="sxs-lookup"><span data-stu-id="9cb27-152">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

    ![Imagem jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a><span data-ttu-id="9cb27-154">Obter uma lista de incidentes recentes</span><span class="sxs-lookup"><span data-stu-id="9cb27-154">Get a list of recent incidents</span></span>

<span data-ttu-id="9cb27-155">O script a seguir **usará** Get-Token.ps1acessar a API.</span><span class="sxs-lookup"><span data-stu-id="9cb27-155">The script below will use **Get-Token.ps1** to access the API.</span></span> <span data-ttu-id="9cb27-156">Em seguida, recupera uma lista de incidentes que foram atualizados pela última vez nas últimas 48 horas e salva a lista como um arquivo JSON.</span><span class="sxs-lookup"><span data-stu-id="9cb27-156">It then retrieves a list of incidents that were last updated within the past 48 hours, and saves the list as a JSON file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9cb27-157">Salve esse script na mesma pasta que você salvou **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="9cb27-157">Save this script in the same folder you saved **Get-Token.ps1**.</span></span>

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

<span data-ttu-id="9cb27-158">Você terminou!</span><span class="sxs-lookup"><span data-stu-id="9cb27-158">You're all done!</span></span> <span data-ttu-id="9cb27-159">Você conseguiu:</span><span class="sxs-lookup"><span data-stu-id="9cb27-159">You've successfully:</span></span>

- <span data-ttu-id="9cb27-160">Criado e registrado um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9cb27-160">Created and registered an application.</span></span>
- <span data-ttu-id="9cb27-161">Permissão concedida para que o aplicativo leia alertas.</span><span class="sxs-lookup"><span data-stu-id="9cb27-161">Granted permission for that application to read alerts.</span></span>
- <span data-ttu-id="9cb27-162">Conectado à API.</span><span class="sxs-lookup"><span data-stu-id="9cb27-162">Connected to the API.</span></span>
- <span data-ttu-id="9cb27-163">Usou um script do PowerShell para retornar incidentes atualizados nas últimas 48 horas.</span><span class="sxs-lookup"><span data-stu-id="9cb27-163">Used a PowerShell script to return incidents updated in the past 48 hours.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9cb27-164">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="9cb27-164">Related articles</span></span>

- [<span data-ttu-id="9cb27-165">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb27-165">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="9cb27-166">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb27-166">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="9cb27-167">Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário</span><span class="sxs-lookup"><span data-stu-id="9cb27-167">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="9cb27-168">Criar um aplicativo para acessar APIs do Microsoft 365 Defender em nome de um usuário</span><span class="sxs-lookup"><span data-stu-id="9cb27-168">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="9cb27-169">Criar um aplicativo com acesso de parceiro de vários locatários às APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9cb27-169">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md)
- [<span data-ttu-id="9cb27-170">Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="9cb27-170">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="9cb27-171">Autorização OAuth 2.0 para entrada do usuário e acesso à API</span><span class="sxs-lookup"><span data-stu-id="9cb27-171">OAuth 2.0 Authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)