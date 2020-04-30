---
title: Implantar um conector para arquivar dados do Twitter
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector nativo para importar e arquivar dados do Twitter para o Microsoft 365. Depois que esses dados são importados para a Microsoft 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados do Twitter da sua organização.
ms.openlocfilehash: 1476350f9f1e777ab5b6706d9802a7d528ec3698
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943024"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="09117-104">Implantar um conector para arquivar dados do Twitter</span><span class="sxs-lookup"><span data-stu-id="09117-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="09117-105">Este artigo contém o processo passo a passo para implantar um conector que usa o serviço de importação do Office 365 para importar dados da conta do Twitter da sua organização para a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09117-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="09117-106">Para obter uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Twitter, consulte [configurar um conector para arquivar dados do Twitter ](archive-twitter-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="09117-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="09117-107">Etapa 1: criar um aplicativo no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="09117-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="09117-108">Vá para <https://portal.azure.com> e entre usando as credenciais de uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="09117-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Entrar no Azure](../media/TCimage01.png)

2. <span data-ttu-id="09117-110">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="09117-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Vá para o Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="09117-112">No painel de navegação esquerdo, clique em **registros de aplicativo (visualização)** e clique em **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="09117-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Criar um novo registro de aplicativo](../media/TCimage03.png)

4. <span data-ttu-id="09117-114">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="09117-114">Register the application.</span></span> <span data-ttu-id="09117-115">Em **URI de redirecionamento (opcional)**, selecione **Web** na lista suspensa tipo de aplicativo `https://portal.azure.com` e digite a caixa para o URI.</span><span class="sxs-lookup"><span data-stu-id="09117-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![<span data-ttu-id="09117-116">Tipo https://portal.azure.com para o URI de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="09117-116">Type https://portal.azure.com for the redirect URI</span></span> ](../media/TCimage04.png)

5. <span data-ttu-id="09117-117">Copie a ID de **aplicativo (cliente)** e a ID de **diretório (locatário)** e salve-as em um arquivo de texto ou outro local seguro.</span><span class="sxs-lookup"><span data-stu-id="09117-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="09117-118">Você usa essas IDs em etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="09117-118">You use these IDs in later steps.</span></span>

    ![Copie e salve a ID do aplicativo e a ID de diretório](../media/TCimage05.png)

6. <span data-ttu-id="09117-120">Vá até **certificados & segredos para o novo aplicativo** e, em **segredos do cliente** , clique em **novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="09117-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Criar um novo segredo do cliente](../media/TCimage06.png)

7. <span data-ttu-id="09117-122">Criar um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="09117-122">Create a new secret.</span></span> <span data-ttu-id="09117-123">Na caixa Descrição, digite o segredo e, em seguida, escolha um período de expiração.</span><span class="sxs-lookup"><span data-stu-id="09117-123">In the description box, type the secret and then choose an expiration period.</span></span> 

   ![Digite o segredo e escolha o período de expiração](../media/TCimage08.png)

8. <span data-ttu-id="09117-125">Copie o valor do segredo e salve-o em um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="09117-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="09117-126">Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="09117-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Copie e salve o segredo](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="09117-128">Etapa 2: implantar o serviço Web do conector do GitHub em sua conta do Azure</span><span class="sxs-lookup"><span data-stu-id="09117-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="09117-129">Vá para [este site do GitHub](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) e clique em **implantar no Azure**.</span><span class="sxs-lookup"><span data-stu-id="09117-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Ir para a home page do Azure](../media/FBCimage11.png)

2. <span data-ttu-id="09117-131">Depois de clicar em **implantar no Azure**, você será redirecionado para um portal do Azure com uma página de modelo Personalizada.</span><span class="sxs-lookup"><span data-stu-id="09117-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="09117-132">Preencha os detalhes **básico** e **configurações** e clique em **compra**.</span><span class="sxs-lookup"><span data-stu-id="09117-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Clique em criar uma conta de armazenamento de recurso e tipo](../media/FBCimage12.png)

    - <span data-ttu-id="09117-134">**Assinatura:** Selecione sua assinatura do Azure para a qual você deseja implantar o serviço Web do conector do Twitter.</span><span class="sxs-lookup"><span data-stu-id="09117-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>
    
    - <span data-ttu-id="09117-135">**Grupo de recursos:** Escolha ou crie um novo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="09117-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="09117-136">Um grupo de recursos é um contêiner que armazena recursos relacionados a uma solução do Azure.</span><span class="sxs-lookup"><span data-stu-id="09117-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="09117-137">**Local:** Escolha um local.</span><span class="sxs-lookup"><span data-stu-id="09117-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="09117-138">**Nome do aplicativo Web:** Forneça um nome exclusivo para o aplicativo Web do conector.</span><span class="sxs-lookup"><span data-stu-id="09117-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="09117-139">O nome do ésimo deve ter entre 3 e 18 caracteres de comprimento.</span><span class="sxs-lookup"><span data-stu-id="09117-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="09117-140">Esse nome é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, se você fornecer o nome do aplicativo Web do **twitterconnector** , a URL do serviço de aplicativo do Azure será **twitterconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="09117-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="09117-141">**tenantid:** A ID de locatário da sua organização do Microsoft 365 que você copiou após criar o aplicativo do Facebook Connector no Azure Active Directory na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="09117-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="09117-142">**APISecretKey:** Você pode digitar qualquer valor como o segredo.</span><span class="sxs-lookup"><span data-stu-id="09117-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="09117-143">Isso é usado para acessar o aplicativo Web do conector na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="09117-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="09117-144">Após a implantação ter êxito, a página será semelhante à captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="09117-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Clique em armazenamento e em conta de armazenamento](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="09117-146">Etapa 3: criar o aplicativo Twitter</span><span class="sxs-lookup"><span data-stu-id="09117-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="09117-147">Vá para https://developer.twitter.com, faça logon usando as credenciais da conta de desenvolvedor da sua organização e clique em **aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="09117-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Ir para https://developer.twitter.com e fazer logon](../media/TCimage25-5.png)
2. <span data-ttu-id="09117-149">Clique em **criar um aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="09117-149">Click **Create an app**.</span></span>
   
   ![Ir para a página aplicativos para criar um aplicativo](../media/TCimage26.png)

3. <span data-ttu-id="09117-151">Em **detalhes do aplicativo**, adicione informações sobre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="09117-151">Under **App details**, add information about the application.</span></span>

   ![Inserir informações sobre o aplicativo](../media/TCimage27.png)

4. <span data-ttu-id="09117-153">No painel de desenvolvedor do Twitter, selecione o aplicativo que você acabou de criar e copie a ID do aplicativo que é exibida e salve-a em um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="09117-153">On the Twitter developer dashboard, select the app that you just created and copy the App ID that's displayed  and save it to a text file or other storage location.</span></span> <span data-ttu-id="09117-154">Em seguida, clique em **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="09117-154">Then click **Details**.</span></span>
   
   ![Copiar e salvar a ID do aplicativo](../media/TCimage28.png)

5. <span data-ttu-id="09117-156">Na guia **chaves e tokens** , em **chaves da API do consumidor** , copie a chave secreta da API e salve-a em um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="09117-156">On the **Keys and tokens** tab, under **Consumer API keys** copy the API secret key and save it to a text file or other storage location.</span></span> <span data-ttu-id="09117-157">Em seguida, clique em **criar** para gerar um token de acesso e um segredo de token de acesso e copie-os para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="09117-157">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>
   
   ![Copiar e salvar a chave secreta da API](../media/TCimage29.png)

   <span data-ttu-id="09117-159">Em seguida, clique em **criar** para gerar um token de acesso e um segredo de token de acesso e copie-os para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="09117-159">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="09117-160">Clique na guia **permissões** e configure as permissões conforme mostrado na captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="09117-160">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurar permissões](../media/TCimage30.png)

7. <span data-ttu-id="09117-162">Após salvar as configurações de permissão, clique na guia **detalhes do aplicativo** e, em seguida, clique em **Editar > editar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="09117-162">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Editar os detalhes do aplicativo](../media/TCimage31.png)

8. <span data-ttu-id="09117-164">Execute as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="09117-164">Do the following tasks:</span></span>

   - <span data-ttu-id="09117-165">Marque a caixa de seleção para permitir que o aplicativo conector entre no Twitter.</span><span class="sxs-lookup"><span data-stu-id="09117-165">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>
   
   - <span data-ttu-id="09117-166">Adicione o URI de redirecionamento OAuth usando o seguinte formato: \*\* \<connectorserviceuri>/views/twitteroauth\*\*, onde o valor de *connectorserviceuri* é a URL do serviço de aplicativo do Azure para sua organização; por exemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span><span class="sxs-lookup"><span data-stu-id="09117-166">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Permitir que o aplicativo conector entre no Twitter e adicione o URI de redirecionamento OAuth](../media/TCimage32.png)

<span data-ttu-id="09117-168">O aplicativo de desenvolvedor do Twitter agora está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="09117-168">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="09117-169">Etapa 4: configurar o aplicativo Web do conector</span><span class="sxs-lookup"><span data-stu-id="09117-169">Step 4: Configure the connector web app</span></span> 

1. <span data-ttu-id="09117-170">Vá para https://\<AzureAppResourceName>. azurewebsites.net (onde **AzureAppResourceName** é o nome do seu recurso do aplicativo do Azure que você nomeou na etapa 4).</span><span class="sxs-lookup"><span data-stu-id="09117-170">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="09117-171">Por exemplo, se o nome for **twitterconnector**, vá para https://twitterconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="09117-171">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="09117-172">A home page do aplicativo é semelhante à captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="09117-172">The home page of the app looks like the following screenshot:</span></span>

   ![Ir para a página de recursos do aplicativo do Azure](../media/FBCimage41.png)

2. <span data-ttu-id="09117-174">Clique em **Configurar** para exibir uma página de entrada.</span><span class="sxs-lookup"><span data-stu-id="09117-174">Click **Configure** to display a sign in page.</span></span>

   ![Clique em configurar para exibir a página de entrada](../media/FBCimage42.png)

3. <span data-ttu-id="09117-176">Na caixa ID do locatário, digite ou cole sua ID de locatário (que você obteve na etapa 2).</span><span class="sxs-lookup"><span data-stu-id="09117-176">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="09117-177">Na caixa senha, digite ou cole o APISecretKey (que você obteve na etapa 2) e clique em **definir definições de configuração** para exibir a página detalhes da configuração.</span><span class="sxs-lookup"><span data-stu-id="09117-177">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Entrar usando a ID do locatário e a chave secreta da API](../media/TCimage35.png)

4. <span data-ttu-id="09117-179">Insira as seguintes definições de configuração</span><span class="sxs-lookup"><span data-stu-id="09117-179">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="09117-180">**Chave de API do Twitter:** A ID do aplicativo do Twitter que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="09117-180">**Twitter Api Key:** The app ID for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="09117-181">**Chave secreta da API do Twitter:** A chave secreta da API do aplicativo Twitter que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="09117-181">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>
   
   - <span data-ttu-id="09117-182">**Token de acesso do Twitter:** O token de acesso que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="09117-182">**Twitter Access Token:** The access token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="09117-183">**Segredo do token de acesso do Twitter:** O segredo do token de acesso que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="09117-183">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>
   
   - <span data-ttu-id="09117-184">**ID do aplicativo AAD:** A ID de aplicativo do aplicativo do Azure Active Directory que você criou na etapa 1</span><span class="sxs-lookup"><span data-stu-id="09117-184">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>
   
   - <span data-ttu-id="09117-185">**Segredo do aplicativo AAD:** O valor para o segredo APISecretKey que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="09117-185">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="09117-186">Clique em **salvar** para salvar as configurações do conector.</span><span class="sxs-lookup"><span data-stu-id="09117-186">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="09117-187">Etapa 5: configurar um conector do Twitter no centro de conformidade da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="09117-187">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="09117-188">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="09117-188">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="09117-189">Na página **conectores de dados (visualização)** , em **Twitter**, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="09117-189">On the **Data connectors (preview)** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="09117-190">Na página do **Twitter** , clique em **Adicionar conector**.</span><span class="sxs-lookup"><span data-stu-id="09117-190">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="09117-191">Na página **termos de serviço** , clique em **aceitar**.</span><span class="sxs-lookup"><span data-stu-id="09117-191">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="09117-192">Na página **Adicionar credenciais para seu aplicativo do conector** , digite as informações a seguir e clique em **validar conexão**.</span><span class="sxs-lookup"><span data-stu-id="09117-192">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Inserir credenciais de aplicativo do conector](../media/TCimage38.png)

    - <span data-ttu-id="09117-194">Na caixa **nome** , digite um nome para o conector, como identificador de **ajuda do Twitter**.</span><span class="sxs-lookup"><span data-stu-id="09117-194">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>
    
    - <span data-ttu-id="09117-195">Na caixa **URL do conector** , digite ou cole a URL do serviço de aplicativo do Azure; por exemplo `https://twitterconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="09117-195">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="09117-196">Na caixa **senha** , digite ou cole o valor do APISecretKey que você criou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="09117-196">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>
    
    - <span data-ttu-id="09117-197">Na caixa **ID do aplicativo do Azure** , digite ou cole o valor da ID de aplicativo do aplicativo do Azure (também chamada de *ID do cliente*) obtida na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="09117-197">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="09117-198">Depois que a conexão for validada com êxito, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="09117-198">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="09117-199">Na página **autorizar o Microsoft 365 a importar dados** , digite ou cole o APISecretKey novamente e clique em **fazer logon no aplicativo Web**.</span><span class="sxs-lookup"><span data-stu-id="09117-199">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="09117-200">Clique em **login com Twitter**.</span><span class="sxs-lookup"><span data-stu-id="09117-200">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="09117-201">Na página de entrada do Twitter, entre usando as credenciais da conta do Twitter da sua organização.</span><span class="sxs-lookup"><span data-stu-id="09117-201">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Entrar na conta do Twitter](../media/TCimage42.png)

   <span data-ttu-id="09117-203">Depois que você entrar, a página do Twitter exibirá a seguinte mensagem, "trabalho do conector do Twitter configurado com êxito".</span><span class="sxs-lookup"><span data-stu-id="09117-203">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="09117-204">Clique em **continuar** para concluir a configuração do conector do Twitter.</span><span class="sxs-lookup"><span data-stu-id="09117-204">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="09117-205">Na página **definir filtros** , você pode aplicar um filtro para importar inicialmente os itens que tenham uma determinada idade.</span><span class="sxs-lookup"><span data-stu-id="09117-205">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="09117-206">Selecione uma idade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="09117-206">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="09117-207">Na página **escolher local de armazenamento** , digite o endereço de email da caixa de correio do Microsoft 365 para o qual os itens do Twitter serão importados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="09117-207">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="09117-208">Em **fornecer consentimento do administrador**, clique em **fornecer consentimento** e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="09117-208">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="09117-209">Você deve ser um administrador global para fornecer consentimento para o serviço de importação do Office 365 para acessar dados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="09117-209">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="09117-210">Clique em **Avançar** para revisar as configurações do conector e clique em **concluir** para concluir a configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="09117-210">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="09117-211">No centro de conformidade, vá para a página **conectores de dados** e clique na guia **conectores** para ver o andamento do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="09117-211">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
