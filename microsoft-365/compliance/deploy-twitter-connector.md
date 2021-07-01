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
description: Os administradores podem configurar um conector nativo para importar e arquivar dados do Twitter para Microsoft 365. Depois que esses dados são importados para Microsoft 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados do Twitter da sua organização.
ms.openlocfilehash: 0a0ebb18cb39b7dd7416f2d03dcb5b4d21332c9b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227050"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a><span data-ttu-id="89bf7-104">Implantar um conector para arquivar dados do Twitter</span><span class="sxs-lookup"><span data-stu-id="89bf7-104">Deploy a connector to archive Twitter data</span></span>

<span data-ttu-id="89bf7-105">Este artigo contém o processo passo a passo para implantar um conector que usa o serviço Office 365 Import para importar dados da conta do Twitter da sua organização para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="89bf7-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from your organization's Twitter account to Microsoft 365.</span></span> <span data-ttu-id="89bf7-106">Para uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Twitter, consulte Configurar um conector para arquivar dados [do Twitter. ](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="89bf7-106">For a high-level overview of this process and a list of prerequisites required to deploy a Twitter connector, see [Set up a connector to archive Twitter data ](archive-twitter-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="89bf7-107">Etapa 1: Criar um aplicativo no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="89bf7-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="89bf7-108">Acesse e <https://portal.azure.com> entre usando as credenciais de uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="89bf7-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

   ![Entrar no Azure](../media/TCimage01.png)

2. <span data-ttu-id="89bf7-110">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

   ![Vá para Azure Active Directory](../media/TCimage02.png)

3. <span data-ttu-id="89bf7-112">No painel de navegação esquerdo, clique em **Registros de aplicativo (Visualização)** e clique em **Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

   ![Criar um novo registro de aplicativo](../media/TCimage03.png)

4. <span data-ttu-id="89bf7-114">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89bf7-114">Register the application.</span></span> <span data-ttu-id="89bf7-115">Em **URI de redirecionamento (opcional),** selecione **Web** na lista suspenso tipo de aplicativo e digite a caixa `https://portal.azure.com` para o URI.</span><span class="sxs-lookup"><span data-stu-id="89bf7-115">Under **Redirect URI (optional)**, select **Web** in the application type dropdown list and then type `https://portal.azure.com` in the box for the URI.</span></span>

   ![Digite https://portal.azure.com para o URI de redirecionamento](../media/TCimage04.png)

5. <span data-ttu-id="89bf7-117">Copie a **ID do Aplicativo (cliente)** e a ID de Diretório **(locatário)** e salve-os em um arquivo de texto ou em outro local seguro.</span><span class="sxs-lookup"><span data-stu-id="89bf7-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="89bf7-118">Use essas IDs em etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="89bf7-118">You use these IDs in later steps.</span></span>

    ![Copiar e salvar a ID do Aplicativo e a ID do Diretório](../media/TCimage05.png)

6. <span data-ttu-id="89bf7-120">Vá para **Certificados & segredos do** novo aplicativo e em **Segredos do** cliente clique em Novo segredo **do cliente.**</span><span class="sxs-lookup"><span data-stu-id="89bf7-120">Go to **Certificates & secrets for the new app** and under **Client secrets** click **New client secret**.</span></span>

   ![Criar um novo segredo do cliente](../media/TCimage06.png)

7. <span data-ttu-id="89bf7-122">Crie um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="89bf7-122">Create a new secret.</span></span> <span data-ttu-id="89bf7-123">Na caixa descrição, digite o segredo e escolha um período de expiração.</span><span class="sxs-lookup"><span data-stu-id="89bf7-123">In the description box, type the secret and then choose an expiration period.</span></span>

   ![Digite o segredo e escolha o período de expiração](../media/TCimage08.png)

8. <span data-ttu-id="89bf7-125">Copie o valor do segredo e salve-o em um arquivo de texto ou em outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="89bf7-125">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="89bf7-126">Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="89bf7-126">This is the AAD application secret that you use in later steps.</span></span>

   ![Copiar e salvar o segredo](../media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="89bf7-128">Etapa 2: Implantar o serviço Web do conector GitHub sua conta do Azure</span><span class="sxs-lookup"><span data-stu-id="89bf7-128">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="89bf7-129">Vá para [este GitHub site e](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) clique em Implantar no **Azure**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-129">Go to [this GitHub site](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Vá para a home page do Azure](../media/FBCimage11.png)

2. <span data-ttu-id="89bf7-131">Depois de clicar **em Implantar no Azure,** você será redirecionado para um portal do Azure com uma página de modelo personalizada.</span><span class="sxs-lookup"><span data-stu-id="89bf7-131">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="89bf7-132">Preencha os **detalhes básicos** **e Configurações** e clique em **Comprar**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-132">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   ![Clique em Criar um recurso e digite conta de armazenamento](../media/FBCimage12.png)

    - <span data-ttu-id="89bf7-134">**Assinatura:** Selecione sua assinatura do Azure para a que você deseja implantar o serviço Web do Conector do Twitter.</span><span class="sxs-lookup"><span data-stu-id="89bf7-134">**Subscription:** Select your Azure subscription that you want to deploy the Twitter connector web service to.</span></span>

    - <span data-ttu-id="89bf7-135">**Grupo de recursos:** Escolha ou crie um novo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="89bf7-135">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="89bf7-136">Um grupo de recursos é um contêiner que contém recursos relacionados para uma solução do Azure.</span><span class="sxs-lookup"><span data-stu-id="89bf7-136">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="89bf7-137">**Local:** Escolha um local.</span><span class="sxs-lookup"><span data-stu-id="89bf7-137">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="89bf7-138">**Nome do aplicativo Web:** Forneça um nome exclusivo para o aplicativo Web do conector.</span><span class="sxs-lookup"><span data-stu-id="89bf7-138">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="89bf7-139">O nome deve ter entre 3 e 18 caracteres de comprimento.</span><span class="sxs-lookup"><span data-stu-id="89bf7-139">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="89bf7-140">Esse nome é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, se você fornecer o nome do aplicativo Web do **twitterconnector,** a URL do serviço de aplicativo do Azure **será** twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="89bf7-140">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **twitterconnector** then the Azure app service URL  will be **twitterconnector.azurewebsites.net**.</span></span>

    - <span data-ttu-id="89bf7-141">**tenantId:** A ID de locatário da sua Microsoft 365 que você copiou após criar o aplicativo conector do Facebook no Azure Active Directory na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="89bf7-141">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure       Active Directory in Step 1.</span></span>

   - <span data-ttu-id="89bf7-142">**APISecretKey:** Você pode digitar qualquer valor como o segredo.</span><span class="sxs-lookup"><span data-stu-id="89bf7-142">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="89bf7-143">Isso é usado para acessar o aplicativo Web do conector na Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="89bf7-143">This is used to access the connector web app in Step 5.</span></span>

3. <span data-ttu-id="89bf7-144">Depois que a implantação for bem-sucedida, a página será semelhante à seguinte captura de tela:</span><span class="sxs-lookup"><span data-stu-id="89bf7-144">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

    ![Clique Armazenamento e clique em Armazenamento conta](../media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a><span data-ttu-id="89bf7-146">Etapa 3: Criar o aplicativo twitter</span><span class="sxs-lookup"><span data-stu-id="89bf7-146">Step 3: Create the Twitter app</span></span>

1. <span data-ttu-id="89bf7-147">Vá para , faça logoff usando as credenciais da conta de desenvolvedor da sua organização e clique https://developer.twitter.com em **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-147">Go to https://developer.twitter.com, log in using the credentials for the developer account for your organization, and then click **Apps**.</span></span>

   ![Vá para https://developer.twitter.com e faça logoff](../media/TCimage25-5.png)
2. <span data-ttu-id="89bf7-149">Clique **em Criar um aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-149">Click **Create an app**.</span></span>

   ![Vá para a página Aplicativos para criar um aplicativo](../media/TCimage26.png)

3. <span data-ttu-id="89bf7-151">Em **Detalhes do aplicativo,** adicione informações sobre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89bf7-151">Under **App details**, add information about the application.</span></span>

   ![Insira informações sobre o aplicativo](../media/TCimage27.png)

4. <span data-ttu-id="89bf7-153">No painel de desenvolvedores do Twitter, selecione o aplicativo que você acabou de criar e clique em **Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="89bf7-153">On the Twitter developer dashboard, select the app that you just created and then click **Details**.</span></span>

   ![Copiar e salvar a ID do Aplicativo](../media/TCimage28.png)

5. <span data-ttu-id="89bf7-155">Na guia **Chaves e tokens,** em Chaves da API do Consumidor, copie a Chave da **API** e a chave secreta da API e salve-as em um arquivo de texto ou em outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="89bf7-155">On the **Keys and tokens** tab, under **Consumer API keys** copy both the API Key and the API secret key and save them to a text file or other storage location.</span></span> <span data-ttu-id="89bf7-156">Em **seguida, clique** em Criar para gerar um token de acesso e acessar o segredo do token e copiá-los para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="89bf7-156">Then click **Create** to generate an access token and access token secret and copy these to a text file or other storage location.</span></span>

   ![Copiar e salvar na chave secreta da API](../media/TCimage29.png)

   <span data-ttu-id="89bf7-158">Em **seguida, clique** em Criar para gerar um token de acesso e um segredo de token de acesso e copie-os para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="89bf7-158">Then click **Create** to generate an access token and an access token secret, and copy these to a text file or other storage location.</span></span>

6. <span data-ttu-id="89bf7-159">Clique na **guia Permissões** e configure as permissões conforme mostrado na captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="89bf7-159">Click the **Permissions** tab and configure the permissions as shown in the following screenshot:</span></span>

   ![Configurar as permissões](../media/TCimage30.png)

7. <span data-ttu-id="89bf7-161">Depois de salvar as configurações de permissão, clique na guia Detalhes **do** aplicativo e clique em Editar > **Editar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-161">After you save the permission settings, click the **App details** tab, and then click **Edit > Edit details**.</span></span>

   ![Editar os detalhes do aplicativo](../media/TCimage31.png)

8. <span data-ttu-id="89bf7-163">Faça as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="89bf7-163">Do the following tasks:</span></span>

   - <span data-ttu-id="89bf7-164">Marque a caixa de seleção para permitir que o aplicativo conector entre no Twitter.</span><span class="sxs-lookup"><span data-stu-id="89bf7-164">Select the checkbox to allow the connector app to sign in to Twitter.</span></span>

   - <span data-ttu-id="89bf7-165">Adicione o Uri de redirecionamento OAuth usando o seguinte formato: **\<connectorserviceuri> /Views/TwitterOAuth**, onde o valor *de connectorserviceuri* é a URL de serviço de aplicativo do Azure para sua organização; por exemplo, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth .</span><span class="sxs-lookup"><span data-stu-id="89bf7-165">Add the OAuth redirect Uri using the following format: **\<connectorserviceuri>/Views/TwitterOAuth**, where the value of *connectorserviceuri* is the Azure app service URL for your organization; for example, https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.</span></span>

    ![Permitir que o aplicativo conector entre no Twitter e adicione Uri de redirecionamento OAuth](../media/TCimage32.png)

<span data-ttu-id="89bf7-167">O aplicativo de desenvolvedor do Twitter agora está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="89bf7-167">The Twitter developer app is now ready to use.</span></span>

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="89bf7-168">Etapa 4: Configurar o aplicativo Web do conector</span><span class="sxs-lookup"><span data-stu-id="89bf7-168">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="89bf7-169">Vá para https:// \<AzureAppResourceName> .azurewebsites.net (onde **AzureAppResourceName** é o nome do seu recurso de aplicativo do Azure nomeado na Etapa 4).</span><span class="sxs-lookup"><span data-stu-id="89bf7-169">Go to https://\<AzureAppResourceName>.azurewebsites.net (where **AzureAppResourceName** is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="89bf7-170">Por exemplo, se o nome for **twitterconnector,** vá para https://twitterconnector.azurewebsites.net .</span><span class="sxs-lookup"><span data-stu-id="89bf7-170">For example, if the name is **twitterconnector**, go to https://twitterconnector.azurewebsites.net.</span></span> <span data-ttu-id="89bf7-171">A home page do aplicativo se parece com a seguinte captura de tela:</span><span class="sxs-lookup"><span data-stu-id="89bf7-171">The home page of the app looks like the following screenshot:</span></span>

   ![Vá para a página de recursos do aplicativo do Azure](../media/FBCimage41.png)

2. <span data-ttu-id="89bf7-173">Clique **em Configurar** para exibir uma página de login.</span><span class="sxs-lookup"><span data-stu-id="89bf7-173">Click **Configure** to display a sign in page.</span></span>

   ![Clique em Configurar para exibir a página de login](../media/FBCimage42.png)

3. <span data-ttu-id="89bf7-175">Na caixa ID do locatário, digite ou colar sua ID de locatário (obtida na Etapa 2).</span><span class="sxs-lookup"><span data-stu-id="89bf7-175">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="89bf7-176">Na caixa senha, digite ou colar a APISecretKey (obtida na Etapa 2) e clique em Definir Configuração **Configurações** para exibir a página de detalhes de configuração.</span><span class="sxs-lookup"><span data-stu-id="89bf7-176">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

   ![Entrar usando a ID do locatário e a chave secreta da API](../media/TCimage35.png)

4. <span data-ttu-id="89bf7-178">Insira as seguintes configurações</span><span class="sxs-lookup"><span data-stu-id="89bf7-178">Enter the following configuration settings</span></span>

   - <span data-ttu-id="89bf7-179">**Chave da Api do Twitter:** A chave da API para o aplicativo Twitter que você criou na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="89bf7-179">**Twitter Api Key:** The API key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="89bf7-180">**Chave Secreta da Api do Twitter:** A chave secreta da API para o aplicativo Twitter que você criou na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="89bf7-180">**Twitter Api Secret Key:** The API secret key for the Twitter application that you created in Step 3.</span></span>

   - <span data-ttu-id="89bf7-181">**Token de Acesso para Twitter:** O token de acesso que você criou na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="89bf7-181">**Twitter Access Token:** The access token that you created in Step 3.</span></span>

   - <span data-ttu-id="89bf7-182">**Segredo do Token de Acesso ao Twitter:** O segredo do token de acesso que você criou na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="89bf7-182">**Twitter Access Token Secret:** The access token secret that you created in Step 3.</span></span>

   - <span data-ttu-id="89bf7-183">**ID do aplicativo AAD:** A ID do aplicativo para o Azure Active Directory que você criou na Etapa 1</span><span class="sxs-lookup"><span data-stu-id="89bf7-183">**AAD Application ID:** The application ID for the Azure Active Directory app that you created in Step 1</span></span>

   - <span data-ttu-id="89bf7-184">**Segredo do aplicativo AAD:** O valor do segredo APISecretKey criado na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="89bf7-184">**AAD Application Secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="89bf7-185">Clique **em Salvar** para salvar as configurações do conector.</span><span class="sxs-lookup"><span data-stu-id="89bf7-185">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="89bf7-186">Etapa 5: Configurar um conector do Twitter no Centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="89bf7-186">Step 5: Set up a Twitter connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="89bf7-187">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** na nav esquerda.</span><span class="sxs-lookup"><span data-stu-id="89bf7-187">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="89bf7-188">Na página **Conectores de dados** em **Twitter,** clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-188">On the **Data connectors** page under **Twitter**, click **View**.</span></span>

3. <span data-ttu-id="89bf7-189">Na página **Twitter,** clique em **Adicionar conector**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-189">On the **Twitter** page, click **Add connector**.</span></span>

4. <span data-ttu-id="89bf7-190">Na página **Termos de serviço,** clique em **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-190">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="89bf7-191">Na página **Adicionar credenciais para seu** aplicativo do conector, insira as informações a seguir e clique em **Validar conexão**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-191">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Inserir credenciais de aplicativo de conector](../media/TCimage38.png)

    - <span data-ttu-id="89bf7-193">Na caixa **Nome,** digite um nome para o conector, como Ajuda **do Twitter para manipular**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-193">In the **Name** box, type a name for the connector, such as **Twitter help handle**.</span></span>

    - <span data-ttu-id="89bf7-194">Na caixa **URL do Conector,** digite ou colar a URL do serviço de aplicativo do Azure; por exemplo `https://twitterconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="89bf7-194">In the **Connector URL** box, type or paste the Azure app service URL; for example `https://twitterconnector.azurewebsites.net`.</span></span>

    - <span data-ttu-id="89bf7-195">Na caixa **Senha,** digite ou colar o valor da APISecretKey que você criou na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="89bf7-195">In the **Password** box, type or paste the value of the APISecretKey that you created in Step 2.</span></span>

    - <span data-ttu-id="89bf7-196">Na caixa ID do Aplicativo **do Azure,** digite ou colar o valor da ID do Aplicativo do Azure (também chamada de *ID* do cliente ) obtida na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="89bf7-196">In the **Azure App ID** box, type or paste the value of the Azure Application App Id (also called the *client ID*) that you obtained in Step 1.</span></span>

6. <span data-ttu-id="89bf7-197">Depois que a conexão for validada com êxito, clique em **Next**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-197">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="89bf7-198">Na página **Autorizar Microsoft 365 importar** dados, digite ou colar a APISecretKey novamente e clique em **Logon do aplicativo Web**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-198">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click  **Login web app**.</span></span>

8. <span data-ttu-id="89bf7-199">Clique **em Logon com o Twitter**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-199">Click **Login with Twitter**.</span></span>

9. <span data-ttu-id="89bf7-200">Na página de login do Twitter, entre usando as credenciais da conta do Twitter da sua organização.</span><span class="sxs-lookup"><span data-stu-id="89bf7-200">On the Twitter sign in page, sign in using the credentials for your organization's Twitter account.</span></span>

   ![Entrar na conta do Twitter](../media/TCimage42.png)

   <span data-ttu-id="89bf7-202">Depois de entrar, a página do Twitter exibirá a seguinte mensagem, "Trabalho do Conector do Twitter Configurada com êxito".</span><span class="sxs-lookup"><span data-stu-id="89bf7-202">After you sign in, the Twitter page will display the following message, "Twitter Connector Job Successfully set up."</span></span>

10. <span data-ttu-id="89bf7-203">Clique **em Continuar** para concluir a configuração do conector do Twitter.</span><span class="sxs-lookup"><span data-stu-id="89bf7-203">Click **Continue** to complete setting up the Twitter connector.</span></span>

11. <span data-ttu-id="89bf7-204">Na página **Definir filtros,** você pode aplicar um filtro para importar inicialmente itens que têm uma determinada idade.</span><span class="sxs-lookup"><span data-stu-id="89bf7-204">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="89bf7-205">Selecione uma idade e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-205">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="89bf7-206">Na página **Escolher local de armazenamento,** digite o endereço de email Microsoft 365 caixa de correio para a qual os itens do Twitter serão importados e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="89bf7-206">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Twitter items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="89bf7-207">Clique **em Próximo** para revisar as configurações do conector e clique em **Concluir** para concluir a configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="89bf7-207">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="89bf7-208">No centro de conformidade, vá até a página **Conectores de** dados e clique na guia **Conectores** para ver o andamento do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="89bf7-208">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
