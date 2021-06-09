---
title: Buscar alertas do locatário do cliente MSSP
description: Saiba como buscar alertas de um locatário do cliente
keywords: provedor de serviços de segurança gerenciado, mssp, configurar, integração
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770764"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="07b69-104">Buscar alertas do locatário do cliente MSSP</span><span class="sxs-lookup"><span data-stu-id="07b69-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07b69-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="07b69-105">**Applies to:**</span></span>
- [<span data-ttu-id="07b69-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="07b69-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="07b69-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="07b69-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="07b69-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="07b69-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="07b69-109">Essa ação é tomada pelo MSSP.</span><span class="sxs-lookup"><span data-stu-id="07b69-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="07b69-110">Há duas maneiras de buscar alertas:</span><span class="sxs-lookup"><span data-stu-id="07b69-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="07b69-111">Usando o método SIEM</span><span class="sxs-lookup"><span data-stu-id="07b69-111">Using the SIEM method</span></span>
- <span data-ttu-id="07b69-112">Usando APIs</span><span class="sxs-lookup"><span data-stu-id="07b69-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="07b69-113">Buscar alertas em seu SIEM</span><span class="sxs-lookup"><span data-stu-id="07b69-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="07b69-114">Para buscar alertas no sistema SIEM, você precisará seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="07b69-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="07b69-115">Etapa 1: Criar um aplicativo de terceiros</span><span class="sxs-lookup"><span data-stu-id="07b69-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="07b69-116">Etapa 2: obter tokens de acesso e atualização do locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="07b69-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="07b69-117">Etapa 3: permitir que seu aplicativo Central de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="07b69-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="07b69-118">Etapa 1: Criar um aplicativo no Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="07b69-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="07b69-119">Você precisará criar um aplicativo e conceder permissões a ele para buscar alertas do locatário do Microsoft Defender para Ponto de Extremidade do seu cliente.</span><span class="sxs-lookup"><span data-stu-id="07b69-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="07b69-120">Entre no portal [do Azure AD.](https://aad.portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="07b69-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="07b69-121">Selecione **Azure Active Directory**  >  **registros do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="07b69-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="07b69-122">Clique **em Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="07b69-122">Click **New registration**.</span></span>

4. <span data-ttu-id="07b69-123">Especifique os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="07b69-123">Specify the following values:</span></span>

    - <span data-ttu-id="07b69-124">Nome: \<Tenant_name\> Conector do SIEM MSSP (substitua Tenant_name pelo nome de exibição do locatário)</span><span class="sxs-lookup"><span data-stu-id="07b69-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="07b69-125">Tipos de conta com suporte: Conta somente neste diretório organizacional</span><span class="sxs-lookup"><span data-stu-id="07b69-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="07b69-126">URI de redirecionamento: selecione Web e digite `https://<domain_name>/SiemMsspConnector` (substitua <domain_name> pelo nome do locatário)</span><span class="sxs-lookup"><span data-stu-id="07b69-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="07b69-127">Clique em **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="07b69-127">Click **Register**.</span></span> <span data-ttu-id="07b69-128">O aplicativo é exibido na lista de aplicativos que você possui.</span><span class="sxs-lookup"><span data-stu-id="07b69-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="07b69-129">Selecione o aplicativo e clique em **Visão Geral**.</span><span class="sxs-lookup"><span data-stu-id="07b69-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="07b69-130">Copie o valor do campo ID do aplicativo **(cliente)** para um local seguro, você precisará disso na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="07b69-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="07b69-131">Selecione **Certificado & segredos** no novo painel de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="07b69-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="07b69-132">Clique **em Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="07b69-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="07b69-133">Descrição: insira uma descrição da chave.</span><span class="sxs-lookup"><span data-stu-id="07b69-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="07b69-134">Expira: Selecionar **em 1 ano**</span><span class="sxs-lookup"><span data-stu-id="07b69-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="07b69-135">Clique **em Adicionar**, copie o valor do segredo do cliente para um local seguro, você precisará disso na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="07b69-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="07b69-136">Etapa 2: obter tokens de acesso e atualização do locatário do cliente</span><span class="sxs-lookup"><span data-stu-id="07b69-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="07b69-137">Esta seção orienta você sobre como usar um script do PowerShell para obter os tokens do locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="07b69-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="07b69-138">Este script usa o aplicativo da etapa anterior para obter os tokens de acesso e atualização usando o código de autorização OAuth Flow.</span><span class="sxs-lookup"><span data-stu-id="07b69-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="07b69-139">Depois de fornecer suas credenciais, você precisará conceder consentimento ao aplicativo para que o aplicativo seja provisionado no locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="07b69-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="07b69-140">Crie uma nova pasta e nomee-a: `MsspTokensAcquisition` .</span><span class="sxs-lookup"><span data-stu-id="07b69-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="07b69-141">Baixe o [módulo LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) e salve-o na `MsspTokensAcquisition` pasta.</span><span class="sxs-lookup"><span data-stu-id="07b69-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="07b69-142">Na linha 30, substitua `authorzationUrl` por `authorizationUrl` .</span><span class="sxs-lookup"><span data-stu-id="07b69-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="07b69-143">Crie um arquivo com o seguinte conteúdo e salve-o com o nome `MsspTokensAcquisition.ps1` na pasta:</span><span class="sxs-lookup"><span data-stu-id="07b69-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="07b69-144">Abra um prompt de comando do PowerShell com elevação na `MsspTokensAcquisition` pasta.</span><span class="sxs-lookup"><span data-stu-id="07b69-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="07b69-145">Execute o seguinte comando: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="07b69-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="07b69-146">Insira os seguintes comandos: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="07b69-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="07b69-147">Substitua \<client_id\> pela **ID de aplicativo (cliente)** que você recebeu da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="07b69-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="07b69-148">Substitua \<app_key\> pelo Segredo do Cliente **criado** na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="07b69-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="07b69-149">Substitua \<customer_tenant_id\> pela ID de **Locatário do seu cliente.**</span><span class="sxs-lookup"><span data-stu-id="07b69-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="07b69-150">Você será solicitado a fornecer suas credenciais e consentimento.</span><span class="sxs-lookup"><span data-stu-id="07b69-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="07b69-151">Ignore o redirecionamento de página.</span><span class="sxs-lookup"><span data-stu-id="07b69-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="07b69-152">Na janela do PowerShell, você receberá um token de acesso e um token de atualização.</span><span class="sxs-lookup"><span data-stu-id="07b69-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="07b69-153">Salve o token de atualização para configurar seu conector SIEM.</span><span class="sxs-lookup"><span data-stu-id="07b69-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="07b69-154">Etapa 3: Permitir que seu aplicativo Central de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="07b69-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="07b69-155">Você precisará permitir o aplicativo criado em Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="07b69-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="07b69-156">Você precisará ter a permissão **Gerenciar configurações do** sistema de portal para permitir o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="07b69-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="07b69-157">Caso contrário, você precisará solicitar que seu cliente permita o aplicativo para você.</span><span class="sxs-lookup"><span data-stu-id="07b69-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="07b69-158">Vá para `https://securitycenter.windows.com?tid=<customer_tenant_id>` (substitua \<customer_tenant_id\> pela ID de locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="07b69-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="07b69-159">Clique **Configurações**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="07b69-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="07b69-160">Selecione a **guia MSSP.**</span><span class="sxs-lookup"><span data-stu-id="07b69-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="07b69-161">Insira a **ID do Aplicativo** na primeira etapa e a **ID do locatário.**</span><span class="sxs-lookup"><span data-stu-id="07b69-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="07b69-162">Clique **em Autorizar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="07b69-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="07b69-163">Agora você pode baixar o arquivo de configuração relevante para seu SIEM e se conectar à API do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="07b69-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="07b69-164">Para obter mais informações, consulte [Pull alerts to your SIEM tools](configure-siem.md).</span><span class="sxs-lookup"><span data-stu-id="07b69-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="07b69-165">No arquivo de configuração arcSight/arquivo propriedades de autenticação Splunk, escreva a chave do aplicativo manualmente definindo o valor secreto.</span><span class="sxs-lookup"><span data-stu-id="07b69-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="07b69-166">Em vez de adquirir um token de atualização no portal, use o script da etapa anterior para adquirir um token de atualização (ou adquiri-lo por outros meios).</span><span class="sxs-lookup"><span data-stu-id="07b69-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="07b69-167">Buscar alertas do locatário do cliente MSSP usando APIs</span><span class="sxs-lookup"><span data-stu-id="07b69-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="07b69-168">Para obter informações sobre como buscar alertas usando a API REST, consulte [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span><span class="sxs-lookup"><span data-stu-id="07b69-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="07b69-169">Confira também</span><span class="sxs-lookup"><span data-stu-id="07b69-169">See also</span></span>
- [<span data-ttu-id="07b69-170">Conceder acesso MSSP ao portal</span><span class="sxs-lookup"><span data-stu-id="07b69-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="07b69-171">Acessar o portal do cliente MSSP</span><span class="sxs-lookup"><span data-stu-id="07b69-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="07b69-172">Configurar notificações de alerta</span><span class="sxs-lookup"><span data-stu-id="07b69-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
