---
title: Hello World para a API REST do Microsoft 365 defender
description: Saiba como criar um aplicativo e usar um token para acessar as APIs do Microsoft 365 defender
keywords: aplicativo, token, Access, AAD, aplicativo, registro de aplicativo, PowerShell, script, administrador global, permissão
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
ms.openlocfilehash: bd4f7e5485d67cf74477900ae2cc5c77f1a6ee41
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844039"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a><span data-ttu-id="9ed0a-104">Hello World para a API REST do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="9ed0a-104">Hello World for Microsoft 365 Defender REST API</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9ed0a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9ed0a-105">**Applies to:**</span></span>
- <span data-ttu-id="9ed0a-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="9ed0a-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="9ed0a-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="9ed0a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="get-incidents-using-a-simple-powershell-script"></a><span data-ttu-id="9ed0a-109">Obter incidentes usando um script simples do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ed0a-109">Get incidents using a simple PowerShell script</span></span>

### <a name="how-long-it-takes-to-go-through-this-example"></a><span data-ttu-id="9ed0a-110">Quanto tempo leva para passar por este exemplo?</span><span class="sxs-lookup"><span data-stu-id="9ed0a-110">How long it takes to go through this example?</span></span>
<span data-ttu-id="9ed0a-111">Isso leva apenas 5 minutos para ser feito em duas etapas:</span><span class="sxs-lookup"><span data-stu-id="9ed0a-111">It only takes 5 minutes done in two steps:</span></span>
- <span data-ttu-id="9ed0a-112">Registro de aplicativo</span><span class="sxs-lookup"><span data-stu-id="9ed0a-112">Application registration</span></span>
- <span data-ttu-id="9ed0a-113">Exemplos de uso: requer apenas copiar/colar um breve script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9ed0a-113">Use examples: only requires copy/paste of a short PowerShell script</span></span>

### <a name="do-i-need-a-permission-to-connect"></a><span data-ttu-id="9ed0a-114">Preciso de uma permissão para se conectar?</span><span class="sxs-lookup"><span data-stu-id="9ed0a-114">Do I need a permission to connect?</span></span>
<span data-ttu-id="9ed0a-115">Para o estágio de registro de aplicativo, você deve ter uma função de **administrador global** em seu locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="9ed0a-115">For the Application registration stage, you must have a **Global administrator** role in your Azure Active Directory (Azure AD) tenant.</span></span>

### <a name="step-1---create-an-app-in-azure-active-directory"></a><span data-ttu-id="9ed0a-116">Etapa 1: criar um aplicativo no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9ed0a-116">Step 1 - Create an App in Azure Active Directory</span></span>

1. <span data-ttu-id="9ed0a-117">Faça logon no [Azure](https://portal.azure.com) com o usuário de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="9ed0a-117">Log on to [Azure](https://portal.azure.com) with your **Global administrator** user.</span></span>

2. <span data-ttu-id="9ed0a-118">Navegue até registro de aplicativo **do Azure Active Directory**  >  **App registrations**  >  **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-118">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="9ed0a-120">No formulário de registro, escolha um nome para o aplicativo e, em seguida, selecione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-120">In the registration form, choose a name for your application and then select **Register**.</span></span>

4. <span data-ttu-id="9ed0a-121">Permitir que seu aplicativo acesse o Microsoft defender para ponto de extremidade e atribuí-lo a permissão de **todos os incidentes** :</span><span class="sxs-lookup"><span data-stu-id="9ed0a-121">Allow your Application to access Microsoft Defender for Endpoint and assign it **Read all incidents** permission:</span></span>

   - <span data-ttu-id="9ed0a-122">Na página do aplicativo, selecione **permissões de API**  >  **Adicionar APIs de permissão**  >  **minha organização usa** > digite **Microsoft 365 defender** e selecione no **Microsoft 365 defender**.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-122">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** > type **Microsoft 365 Defender** and select on **Microsoft 365 Defender**.</span></span>

   >[!NOTE]
   ><span data-ttu-id="9ed0a-123">O Microsoft 365 defender não aparece na lista original.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-123">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="9ed0a-124">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-124">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)

   - <span data-ttu-id="9ed0a-126">Escolha **Application Permissions**  >  **Incident. Read. All** > selecionar em **adicionar permissões**</span><span class="sxs-lookup"><span data-stu-id="9ed0a-126">Choose **Application permissions** > **Incident.Read.All** > Select on **Add permissions**</span></span>

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   ><span data-ttu-id="9ed0a-128">Você precisa selecionar as permissões relevantes.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-128">You need to select the relevant permissions.</span></span> 

     <span data-ttu-id="9ed0a-129">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="9ed0a-129">For instance,</span></span>

     - <span data-ttu-id="9ed0a-130">Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você está interessado em chamar.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-130">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

5. <span data-ttu-id="9ed0a-131">Selecionar **conceder consentimento do administrador**</span><span class="sxs-lookup"><span data-stu-id="9ed0a-131">Select **Grant admin consent**</span></span>

    - >[!NOTE]
      > <span data-ttu-id="9ed0a-132">Toda vez que você adicionar permissão, deverá selecionar o **consentimento conceder** para que a nova permissão entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-132">Every time you add permission you must select on **Grant consent** for the new permission to take effect.</span></span>

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

6. <span data-ttu-id="9ed0a-134">Adicione um segredo ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-134">Add a secret to the application.</span></span>

    - <span data-ttu-id="9ed0a-135">Selecione **certificados & segredos** , adicione descrição ao segredo e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-135">Select **Certificates & secrets** , add description to the secret and select **Add**.</span></span>

    >[!IMPORTANT]
    > <span data-ttu-id="9ed0a-136">Depois de selecionar **Adicionar** , **Copie o valor de segredo gerado**.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-136">After selecting **Add** , **copy the generated secret value**.</span></span> <span data-ttu-id="9ed0a-137">Você não poderá recuperar após sair!</span><span class="sxs-lookup"><span data-stu-id="9ed0a-137">You won't be able to retrieve after you leave!</span></span>

    ![Imagem da chave de criação de aplicativo](../../media/webapp-create-key2.png)

7. <span data-ttu-id="9ed0a-139">Anote a ID do aplicativo e a ID do locatário:</span><span class="sxs-lookup"><span data-stu-id="9ed0a-139">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="9ed0a-140">Na página do aplicativo, vá para **visão geral** e copie o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9ed0a-140">On your application page, go to **Overview** and copy the following:</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)


<span data-ttu-id="9ed0a-142">Terminado!</span><span class="sxs-lookup"><span data-stu-id="9ed0a-142">Done!</span></span> <span data-ttu-id="9ed0a-143">Você registrou com êxito um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-143">You have successfully registered an application.</span></span>

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a><span data-ttu-id="9ed0a-144">Etapa 2: obter um token usando o aplicativo e usar esse token para acessar a API.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-144">Step 2 - Get a token using the App and use this token to access the API.</span></span>

-   <span data-ttu-id="9ed0a-145">Copie o script abaixo para o PowerShell ISE ou para um editor de texto e salve-o como " **Get-Token.ps1** "</span><span class="sxs-lookup"><span data-stu-id="9ed0a-145">Copy the script below to PowerShell ISE or to a text editor, and save it as " **Get-Token.ps1** "</span></span>
-   <span data-ttu-id="9ed0a-146">Executar esse script gerará um token e o salvará na pasta de trabalho com o nome " **Latest-token.txt** ".</span><span class="sxs-lookup"><span data-stu-id="9ed0a-146">Running this script will generate a token and will save it in the working folder under the name " **Latest-token.txt** ".</span></span>

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   <span data-ttu-id="9ed0a-147">Verificação de sanidade:</span><span class="sxs-lookup"><span data-stu-id="9ed0a-147">Sanity Check:</span></span><br>
<span data-ttu-id="9ed0a-148">Execute o script.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-148">Run the script.</span></span><br>
<span data-ttu-id="9ed0a-149">No navegador, vá para: https://jwt.ms/</span><span class="sxs-lookup"><span data-stu-id="9ed0a-149">In your browser go to: https://jwt.ms/</span></span> <br>
<span data-ttu-id="9ed0a-150">Copie o token (o conteúdo do arquivo de Latest-token.txt).</span><span class="sxs-lookup"><span data-stu-id="9ed0a-150">Copy the token (the content of the Latest-token.txt file).</span></span><br>
<span data-ttu-id="9ed0a-151">Colar na caixa superior.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-151">Paste in the top box.</span></span><br>
<span data-ttu-id="9ed0a-152">Procure a seção "funções".</span><span class="sxs-lookup"><span data-stu-id="9ed0a-152">Look for the "roles" section.</span></span> <span data-ttu-id="9ed0a-153">Encontre a ```Incidents.Read.All``` função.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-153">Find the ```Incidents.Read.All``` role.</span></span><br>
<span data-ttu-id="9ed0a-154">O exemplo a seguir é de um aplicativo que ```Incidents.Read.All``` tem ```Incidents.ReadWrite.All``` e ```AdvancedHunting.Read.All``` permissões.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-154">The below example is from an app that has ```Incidents.Read.All```, ```Incidents.ReadWrite.All``` and ```AdvancedHunting.Read.All``` permissions.</span></span>

![Jwt.ms de imagem](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a><span data-ttu-id="9ed0a-156">Permite obter os incidentes!</span><span class="sxs-lookup"><span data-stu-id="9ed0a-156">Lets get the Incidents!</span></span>

-   <span data-ttu-id="9ed0a-157">O script abaixo usará **Get-Token.ps1** para acessar a API e obterá os incidentes atualizados pela última vez nas últimas 48 horas.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-157">The script below will use **Get-Token.ps1** to access the API and will get the incidents last updated in past 48 hours.</span></span>
-   <span data-ttu-id="9ed0a-158">Salvar este script na mesma pasta em que você salvou o script anterior **Get-Token.ps1**.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-158">Save this script in the same folder you saved the previous script **Get-Token.ps1**.</span></span> 
-   <span data-ttu-id="9ed0a-159">O script um arquivo JSON com os dados na mesma pasta dos scripts.</span><span class="sxs-lookup"><span data-stu-id="9ed0a-159">The script a json file with the data in the same folder as the scripts.</span></span>

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

<span data-ttu-id="9ed0a-160">Você terminou!</span><span class="sxs-lookup"><span data-stu-id="9ed0a-160">You're all done!</span></span> <span data-ttu-id="9ed0a-161">Você acabou de fazer o êxito:</span><span class="sxs-lookup"><span data-stu-id="9ed0a-161">You have just successfully:</span></span>
-   <span data-ttu-id="9ed0a-162">Criado e registrado e aplicativo</span><span class="sxs-lookup"><span data-stu-id="9ed0a-162">Created and registered and application</span></span>
-   <span data-ttu-id="9ed0a-163">Permissão concedida para que o aplicativo Leia os alertas</span><span class="sxs-lookup"><span data-stu-id="9ed0a-163">Granted permission for that application to read alerts</span></span>
-   <span data-ttu-id="9ed0a-164">Conexão da API</span><span class="sxs-lookup"><span data-stu-id="9ed0a-164">Connected the API</span></span>
-   <span data-ttu-id="9ed0a-165">Usou um script do PowerShell para retornar incidentes criados nas últimas 48 horas</span><span class="sxs-lookup"><span data-stu-id="9ed0a-165">Used a PowerShell script to return incidents created in the past 48 hours</span></span>



## <a name="related-topic"></a><span data-ttu-id="9ed0a-166">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="9ed0a-166">Related topic</span></span>
- [<span data-ttu-id="9ed0a-167">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="9ed0a-167">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="9ed0a-168">Acessar o Microsoft 365 defender com contexto de aplicativo</span><span class="sxs-lookup"><span data-stu-id="9ed0a-168">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="9ed0a-169">Acessar o Microsoft 365 defender com contexto de usuário</span><span class="sxs-lookup"><span data-stu-id="9ed0a-169">Access  Microsoft 365 Defender with user context</span></span>](api-create-app-user-context.md)
