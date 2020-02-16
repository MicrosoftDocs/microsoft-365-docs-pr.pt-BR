---
title: Implantar um conector para arquivar dados de páginas de negócios do Facebook
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
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem configurar um conector nativo para importar e arquivar páginas de negócios do Facebook para o Microsoft 365. Depois que esses dados são importados para a Microsoft 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados de Facebook da sua organização.
ms.openlocfilehash: 48747dade98701303c4ca6a8c00192ec7faff34a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075948"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="b98a1-104">Implantar um conector para arquivar dados de páginas de negócios do Facebook</span><span class="sxs-lookup"><span data-stu-id="b98a1-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="b98a1-105">Este artigo contém o processo passo a passo para implantar um conector que usa o serviço de importação 365 da Microsoft para importar dados de páginas de negócios do Facebook para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b98a1-105">This article contains the step-by-step process to deploy a connector that uses the Microsoft 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="b98a1-106">Para obter uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Facebook, consulte [configurar um conector para arquivar dados do Facebook](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b98a1-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="b98a1-107">Etapa 1: criar um aplicativo no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b98a1-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="b98a1-108">Vá para <https://portal.azure.com> e entre usando as credenciais de uma conta de administrador global do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b98a1-108">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Criar aplicativo no AAD](../media/FBCimage1.png)

2. <span data-ttu-id="b98a1-110">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Clique em Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="b98a1-112">No painel de navegação esquerdo, clique em **registros de aplicativo (visualização)** e clique em **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Clique em \* \* registros de aplicativo (visualização) \* \* e, em seguida, clique em \* \* novo registro \* \*](../media/FBCimage3.png)

4. <span data-ttu-id="b98a1-114">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b98a1-114">Register the application.</span></span> <span data-ttu-id="b98a1-115">Em URI de redirecionamento, selecione Web na lista suspensa tipo de aplicativo <https://portal.azure.com> e digite na caixa para o URI.</span><span class="sxs-lookup"><span data-stu-id="b98a1-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrar o aplicativo](../media/FBCimage4.png)

5. <span data-ttu-id="b98a1-117">Copie a ID de **aplicativo (cliente)** e a ID de **diretório (locatário)** e salve-as em um arquivo de texto ou outro local seguro.</span><span class="sxs-lookup"><span data-stu-id="b98a1-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="b98a1-118">Você usa essas IDs em etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="b98a1-118">You use these IDs in later steps.</span></span>

   ![Copie a ID do aplicativo e a ID de diretório e salve-as](../media/FBCimage5.png)

6. <span data-ttu-id="b98a1-120">Vá até **certificados & segredos para o novo aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="b98a1-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Vá até certificados & segredos para o novo aplicativo](../media/FBCimage6.png)

7. <span data-ttu-id="b98a1-122">Clique em **novo segredo do cliente**</span><span class="sxs-lookup"><span data-stu-id="b98a1-122">Click **New client secret**</span></span>

   ![Clique em novo segredo do cliente](../media/FBCimage7.png)

8. <span data-ttu-id="b98a1-124">Criar um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="b98a1-124">Create a new secret.</span></span> <span data-ttu-id="b98a1-125">Na caixa Descrição, digite o segredo e, em seguida, escolha um período de expiração.</span><span class="sxs-lookup"><span data-stu-id="b98a1-125">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![Digite o segredo e, em seguida, escolha um período de expiração](../media/FBCimage8.png)

9. <span data-ttu-id="b98a1-127">Copie o valor do segredo e salve-o em um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b98a1-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="b98a1-128">Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="b98a1-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Copie o valor do segredo e salve-o](../media/FBCimage9.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="b98a1-130">Etapa 2: implantar o serviço Web do conector do GitHub em sua conta do Azure</span><span class="sxs-lookup"><span data-stu-id="b98a1-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="b98a1-131">Vá para [este site do GitHub](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) e clique em **implantar no Azure**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Clique em implantar no Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="b98a1-133">Depois de clicar em **implantar no Azure**, você será redirecionado para um portal do Azure com uma página de modelo Personalizada.</span><span class="sxs-lookup"><span data-stu-id="b98a1-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="b98a1-134">Preencha os detalhes **básico** e **configurações** e clique em **compra**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

    - <span data-ttu-id="b98a1-135">**Assinatura:** Selecione sua assinatura do Azure para a qual você deseja implantar o serviço Web do conector de páginas de negócios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="b98a1-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>
    
    - <span data-ttu-id="b98a1-136">**Grupo de recursos:** Escolha ou crie um novo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="b98a1-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="b98a1-137">Um grupo de recursos é um contêiner que armazena recursos relacionados a uma solução do Azure.</span><span class="sxs-lookup"><span data-stu-id="b98a1-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

    - <span data-ttu-id="b98a1-138">**Local:** Escolha um local.</span><span class="sxs-lookup"><span data-stu-id="b98a1-138">**Location:** Choose a location.</span></span>

    - <span data-ttu-id="b98a1-139">**Nome do aplicativo Web:** Forneça um nome exclusivo para o aplicativo Web do conector.</span><span class="sxs-lookup"><span data-stu-id="b98a1-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="b98a1-140">O nome do ésimo deve ter entre 3 e 18 caracteres de comprimento.</span><span class="sxs-lookup"><span data-stu-id="b98a1-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="b98a1-141">Esse nome é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, se você fornecer o nome do aplicativo Web do **fbconnector** , a URL do serviço de aplicativo do Azure será **fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>
    
    - <span data-ttu-id="b98a1-142">**tenantid:** A ID de locatário da sua organização do Microsoft 365 que você copiou após criar o aplicativo do Facebook Connector no Azure Active Directory na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b98a1-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>
    
   - <span data-ttu-id="b98a1-143">**APISecretKey:** Você pode digitar qualquer valor como o segredo.</span><span class="sxs-lookup"><span data-stu-id="b98a1-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="b98a1-144">Isso é usado para acessar o aplicativo Web do conector na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="b98a1-144">This is used to access the connector web app in Step 5.</span></span>
   
     ![Clique em criar uma conta de armazenamento de recurso e tipo](../media/FBCimage12.png)

3. <span data-ttu-id="b98a1-146">Após a implantação ter êxito, a página será semelhante à captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="b98a1-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

     ![Clique em armazenamento e em conta de armazenamento](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="b98a1-148">Etapa 3: registrar o aplicativo do Facebook</span><span class="sxs-lookup"><span data-stu-id="b98a1-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="b98a1-149">Vá para <https://developers.facebook.com>, faça logon usando as credenciais da conta das páginas de negócios de Facebook da sua organização e clique em **Adicionar novo aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![Adicionar um novo aplicativo para a página de negócios do Facebook](../media/FBCimage25.png)

2. <span data-ttu-id="b98a1-151">Crie uma nova ID de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b98a1-151">Create a new app ID.</span></span>

   ![Criar uma nova ID de aplicativo](../media/FBCimage26.png)

3. <span data-ttu-id="b98a1-153">No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **Configurar** no bloco de **logon do Facebook** .</span><span class="sxs-lookup"><span data-stu-id="b98a1-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Clique em Adicionar produtos](../media/FBCimage27.png)

4. <span data-ttu-id="b98a1-155">Na página integrar login do Facebook, clique em **Web**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Clique em Web na página integrar logon do Facebook](../media/FBCimage28.png)

5. <span data-ttu-id="b98a1-157">Adicione a URL do serviço de aplicativo do Azure; por exemplo `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="b98a1-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Adicionar a URL do serviço de aplicativo do Azure](../media/FBCimage29.png)

6. <span data-ttu-id="b98a1-159">Preencha a seção QuickStart da configuração de login do Facebook.</span><span class="sxs-lookup"><span data-stu-id="b98a1-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Concluir a seção QuickStart](../media/FBCimage30.png)

7. <span data-ttu-id="b98a1-161">No painel de navegação esquerdo em **logon do Facebook**, clique em **configurações**e adicione o URI de redirecionamento OAuth na caixa **URIs de redirecionamento OAuth válidos** .</span><span class="sxs-lookup"><span data-stu-id="b98a1-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="b98a1-162">Use o formato \*\* \<connectorserviceuri>/views/facebookoauth\*\*, onde o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo, `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="b98a1-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Adicione o URI de redirecionamento OAuth à caixa URIs de redirecionamento OAuth válidos](../media/FBCimage31.png)

8. <span data-ttu-id="b98a1-164">No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **WebHooks.**</span><span class="sxs-lookup"><span data-stu-id="b98a1-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="b98a1-165">No menu suspenso da **página** , clique em **página**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-165">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![Clique em Adicionar produtos e em \* \* WebHooks](../media/FBCimage32.png)

9. <span data-ttu-id="b98a1-167">Adicione URL de retorno de chamada de WebHooks e adicione um token de verificação.</span><span class="sxs-lookup"><span data-stu-id="b98a1-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="b98a1-168">O formato da URL de retorno de chamada, use o formato \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, em que o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="b98a1-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span> 

    <span data-ttu-id="b98a1-169">O token de verificação deve ser semelhante a uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="b98a1-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="b98a1-170">Copie o token de verificação para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b98a1-170">Copy the verify token to a text file or other storage location.</span></span>

        ![Add the verify token](../media/FBCimage33.png)

10. <span data-ttu-id="b98a1-171">Teste e assine o ponto de extremidade do feed.</span><span class="sxs-lookup"><span data-stu-id="b98a1-171">Test and subscribe to the endpoint for feed.</span></span>

    ![Testar e inscrever-se no ponto de extremidade](../media/FBCimage34.png)

11. <span data-ttu-id="b98a1-173">Adicione uma URL de privacidade, ícone de aplicativo e uso comercial.</span><span class="sxs-lookup"><span data-stu-id="b98a1-173">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="b98a1-174">Além disso, copie a ID do aplicativo e o segredo do aplicativo para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b98a1-174">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Adicionar uma URL de privacidade, ícone de aplicativo e uso comercial](../media/FBCimage35.png)

12. <span data-ttu-id="b98a1-176">Tornar o aplicativo público.</span><span class="sxs-lookup"><span data-stu-id="b98a1-176">Make the app public.</span></span>

    ![Tornar o aplicativo público](../media/FBCimage36.png)

13. <span data-ttu-id="b98a1-178">Adicionar usuário à função de administrador ou de testador.</span><span class="sxs-lookup"><span data-stu-id="b98a1-178">Add user to the admin or tester role.</span></span>

    ![Adicionar usuário à função de administrador ou de testador](../media/FBCimage37.png)

14. <span data-ttu-id="b98a1-180">Adicione a permissão de **acesso ao conteúdo público da página** .</span><span class="sxs-lookup"><span data-stu-id="b98a1-180">Add the **Page Public Content Access** permission.</span></span>

    ![Adicionar a permissão de acesso ao conteúdo público da página](../media/FBCimage38.png)

15. <span data-ttu-id="b98a1-182">Permissão Adicionar gerenciar páginas.</span><span class="sxs-lookup"><span data-stu-id="b98a1-182">Add Manage Pages permission.</span></span>

    ![Permissão Adicionar gerenciar páginas](../media/FBCimage39.png)

16. <span data-ttu-id="b98a1-184">Obtenha o aplicativo revisado pelo Facebook.</span><span class="sxs-lookup"><span data-stu-id="b98a1-184">Get the application reviewed by Facebook.</span></span>

    ![Obter o aplicativo revisado pelo Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="b98a1-186">Etapa 4: configurar o aplicativo Web do conector</span><span class="sxs-lookup"><span data-stu-id="b98a1-186">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="b98a1-187">Vá para https://\<AzureAppResourceName>. azurewebsites.net (onde AzureAppResourceName é o nome do seu recurso do aplicativo do Azure que você nomeou na etapa 4) por exemplo, se o nome for **fbconnector**, vá para `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="b98a1-187">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="b98a1-188">A home page do aplicativo se parecerá com a captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="b98a1-188">The home page of the app will look like the following screenshot:</span></span>

   ![Vá para o aplicativo Web do conector](../media/FBCimage41.png)

2. <span data-ttu-id="b98a1-190">Clique em **Configurar** para exibir uma página de entrada.</span><span class="sxs-lookup"><span data-stu-id="b98a1-190">Click **Configure** to display a sign in page.</span></span>
 
   ![Clique em configurar para exibir uma página de entrada](../media/FBCimage42.png)

3. <span data-ttu-id="b98a1-192">Na caixa ID do locatário, digite ou cole sua ID de locatário (que você obteve na etapa 2).</span><span class="sxs-lookup"><span data-stu-id="b98a1-192">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="b98a1-193">Na caixa senha, digite ou cole o APISecretKey (que você obteve na etapa 2) e clique em **definir definições de configuração** para exibir a página detalhes da configuração.</span><span class="sxs-lookup"><span data-stu-id="b98a1-193">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Entre usando sua ID de locatário e senha e vá para a página de detalhes de configuração](../media/FBCimage43.png)

4. <span data-ttu-id="b98a1-195">Insira as seguintes definições de configuração</span><span class="sxs-lookup"><span data-stu-id="b98a1-195">Enter the following configuration settings</span></span> 

   - <span data-ttu-id="b98a1-196">**ID do aplicativo do Facebook:** A ID de aplicativo para o aplicativo do Facebook obtido na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="b98a1-196">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="b98a1-197">**Segredo do aplicativo do Facebook:** O segredo do aplicativo para o aplicativo do Facebook obtido na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="b98a1-197">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>
   
   - <span data-ttu-id="b98a1-198">**Token de verificação de WebHooks do Facebook:** O token de verificação que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="b98a1-198">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>
   
   - <span data-ttu-id="b98a1-199">**ID do aplicativo AAD:** A ID de aplicativo do aplicativo do Azure Active Directory que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b98a1-199">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>
   
   - <span data-ttu-id="b98a1-200">**Segredo do aplicativo AAD:** O valor para o segredo APISecretKey que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b98a1-200">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="b98a1-201">Clique em **salvar** para salvar as configurações do conector.</span><span class="sxs-lookup"><span data-stu-id="b98a1-201">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="b98a1-202">Etapa 5: configurar um conector do Facebook no centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b98a1-202">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="b98a1-203">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **conectores de dados** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="b98a1-203">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="b98a1-204">Na página **conectores de dados (visualização)** , em **páginas de negócios do Facebook**, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-204">On the **Data connectors (preview)** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="b98a1-205">Na página **páginas de negócios do Facebook** , clique em **Adicionar conector**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-205">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="b98a1-206">Na página **termos de serviço** , clique em **aceitar**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-206">On the **Terms of service** page, click **Accept**.</span></span>

5.  <span data-ttu-id="b98a1-207">Na página **Adicionar credenciais para seu aplicativo do conector** , digite as informações a seguir e clique em **validar conexão**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-207">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

    ![Inserir credenciais de aplicativo do conector](../media/TCimage38.png)

    - <span data-ttu-id="b98a1-209">Na caixa **nome** , digite um nome para o conector, como página de **notícias do Facebook**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-209">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>
    
    - <span data-ttu-id="b98a1-210">Na caixa **URL da conexão** , digite ou cole a URL do serviço de aplicativo do Azure; por exemplo `https://fbconnector.azurewebsites.net`.</span><span class="sxs-lookup"><span data-stu-id="b98a1-210">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>
    
    - <span data-ttu-id="b98a1-211">Na caixa **senha** , digite ou cole o valor do APISecretKey que você adicionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="b98a1-211">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>
    
    - <span data-ttu-id="b98a1-212">Na caixa **ID do aplicativo do Azure** , digite ou cole o valor da ID do aplicativo (cliente) também chamado de ID do aplicativo AAD que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b98a1-212">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>
 
6. <span data-ttu-id="b98a1-213">Depois que a conexão for validada com êxito, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-213">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="b98a1-214">Na página **autorizar o Microsoft 365 a importar dados** , digite ou cole o APISecretKey novamente e clique em **fazer logon no aplicativo Web**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-214">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="b98a1-215">Na página **Configurar aplicativo do Facebook Connector** , clique em **logon com Facebook** e faça logon usando as credenciais da conta para as páginas de negócios de Facebook da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b98a1-215">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="b98a1-216">Certifique-se de que a conta do Facebook na qual você está conectado tenha a função de administrador para as páginas de negócios de Facebook da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b98a1-216">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Faça logon com o Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="b98a1-218">É exibida uma lista das páginas de negócios gerenciadas pela conta do Facebook que você fez logon.</span><span class="sxs-lookup"><span data-stu-id="b98a1-218">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="b98a1-219">Selecione a página para arquivar e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-219">Select the page to archive and then click **Next**.</span></span>

    ![Selecione a página de negócios da organização que você deseja arquivar](../media/FBCimage52.png)

10. <span data-ttu-id="b98a1-221">Clique em **continuar** para sair da configuração do aplicativo de serviço do conector.</span><span class="sxs-lookup"><span data-stu-id="b98a1-221">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="b98a1-222">Na página **definir filtros** , você pode aplicar um filtro para importar inicialmente os itens que tenham uma determinada idade.</span><span class="sxs-lookup"><span data-stu-id="b98a1-222">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="b98a1-223">Selecione uma idade e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-223">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="b98a1-224">Na página **escolher local de armazenamento** , digite o endereço de email da caixa de correio do Microsoft 365 para o qual os itens do Facebook serão importados e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b98a1-224">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="b98a1-225">Em **fornecer consentimento do administrador**, clique em **fornecer consentimento** e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="b98a1-225">On the **Provide admin consent**, click **Provide consent** and then follow the steps.</span></span> <span data-ttu-id="b98a1-226">Você deve ser um administrador global para fornecer consentimento para o serviço de importação do Office 365 para acessar dados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b98a1-226">You must be a global admin to provide consent for the Office 365 Import service to access data in your organization.</span></span>

14. <span data-ttu-id="b98a1-227">Clique em **Avançar** para revisar as configurações do conector e clique em **concluir** para concluir a configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="b98a1-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

15. <span data-ttu-id="b98a1-228">No centro de conformidade, vá para a página **conectores de dados** e clique na guia **conectores** para ver o andamento do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="b98a1-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
