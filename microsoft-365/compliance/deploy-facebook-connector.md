---
title: Implantar um conector para arquivar dados de páginas comerciais do Facebook
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
description: Os administradores podem configurar um conector nativo para importar e arquivar páginas do Facebook Business no Microsoft 365. Depois que esses dados são importados para o Microsoft 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados do Facebook da sua organização.
ms.openlocfilehash: b771c50eb5c2eb5f99269f1f399d27043ebee6bb
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619947"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a><span data-ttu-id="3dc62-104">Implantar um conector para arquivar dados de páginas comerciais do Facebook</span><span class="sxs-lookup"><span data-stu-id="3dc62-104">Deploy a connector to archive Facebook Business pages data</span></span>

<span data-ttu-id="3dc62-105">Este artigo contém o processo passo a passo para implantar um conector que usa o serviço importar do Office 365 para importar dados de páginas do Facebook Business para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3dc62-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Microsoft 365.</span></span> <span data-ttu-id="3dc62-106">Para uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Facebook, confira Configurar um conector para arquivar dados do [Facebook.](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="3dc62-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Set up a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md).</span></span>

## <a name="step-1-create-an-app-in-azure-active-directory"></a><span data-ttu-id="3dc62-107">Etapa 1: Criar um aplicativo no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3dc62-107">Step 1: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="3dc62-108">Acesse e <https://portal.azure.com> entre usando as credenciais de uma conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="3dc62-108">Go to <https://portal.azure.com> and sign in using the credentials of a global admin account.</span></span>

    ![Criar aplicativo no AAD](../media/FBCimage1.png)

2. <span data-ttu-id="3dc62-110">No painel de navegação esquerdo, clique no **Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-110">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![Clique no Azure Active Directory](../media/FBCimage2.png)

3. <span data-ttu-id="3dc62-112">No painel de navegação esquerdo, clique em **Registros de aplicativo (Visualização)** e clique em **Novo registro.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-112">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![Click **App registrations (Preview)** and then click **New registration**](../media/FBCimage3.png)

4. <span data-ttu-id="3dc62-114">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3dc62-114">Register the application.</span></span> <span data-ttu-id="3dc62-115">Em URI de redirecionamento, selecione Web na lista de tipos de aplicativos e digite a caixa <https://portal.azure.com> para o URI.</span><span class="sxs-lookup"><span data-stu-id="3dc62-115">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![Registrar o aplicativo](../media/FBCimage4.png)

5. <span data-ttu-id="3dc62-117">Copie a **ID do Aplicativo (cliente)** e a ID do Diretório **(locatário)** e salve-as em um arquivo de texto ou em outro local seguro.</span><span class="sxs-lookup"><span data-stu-id="3dc62-117">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="3dc62-118">Use essas IDs em etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="3dc62-118">You use these IDs in later steps.</span></span>

   ![Copie a ID do Aplicativo e a ID do Diretório e salve-as](../media/FBCimage5.png)

6. <span data-ttu-id="3dc62-120">Vá para **Certificados & segredos do novo aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![Vá para Certificados & segredos do novo aplicativo](../media/FBCimage6.png)

7. <span data-ttu-id="3dc62-122">Clique **em Novo segredo do cliente**</span><span class="sxs-lookup"><span data-stu-id="3dc62-122">Click **New client secret**</span></span>

   ![Clique em Novo segredo do cliente](../media/FBCimage7.png)

8. <span data-ttu-id="3dc62-124">Crie um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="3dc62-124">Create a new secret.</span></span> <span data-ttu-id="3dc62-125">Na caixa de descrição, digite o segredo e escolha um período de expiração.</span><span class="sxs-lookup"><span data-stu-id="3dc62-125">In the description box, type the secret and then choose an expiration period.</span></span>

    ![Digite o segredo e escolha um período de expiração](../media/FBCimage8.png)

9. <span data-ttu-id="3dc62-127">Copie o valor do segredo e salve-o em um arquivo de texto ou em outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="3dc62-127">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="3dc62-128">Esse é o segredo do aplicativo AAD que você usa nas etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="3dc62-128">This is the AAD application secret that you use in later steps.</span></span>

   ![Copie o valor do segredo e salve-o](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a><span data-ttu-id="3dc62-130">Etapa 2: Implantar o serviço Web do conector do GitHub em sua conta do Azure</span><span class="sxs-lookup"><span data-stu-id="3dc62-130">Step 2: Deploy the connector web service from GitHub to your Azure account</span></span>

1. <span data-ttu-id="3dc62-131">Acesse este [site do GitHub e](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) clique em Implantar no **Azure.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-131">Go to [this GitHub site](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) and click **Deploy to Azure**.</span></span>

    ![Clique em Implantar no Azure](../media/FBCGithubApp.png)

2. <span data-ttu-id="3dc62-133">Depois de clicar **em Implantar no Azure,** você será redirecionado para um portal do Azure com uma página de modelo personalizada.</span><span class="sxs-lookup"><span data-stu-id="3dc62-133">After you click **Deploy to Azure**, you will be redirected to an Azure portal with a custom template page.</span></span> <span data-ttu-id="3dc62-134">Preencha os detalhes **de Noções básicas** **e configurações** e clique em **Comprar.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-134">Fill in the **Basics** and **Settings** details and then click **Purchase**.</span></span>

   - <span data-ttu-id="3dc62-135">**Assinatura:** Selecione sua assinatura do Azure na que você deseja implantar o serviço Web do conector de páginas do Facebook Business.</span><span class="sxs-lookup"><span data-stu-id="3dc62-135">**Subscription:** Select your Azure subscription that you want to deploy the Facebook Business pages connector web service to.</span></span>

   - <span data-ttu-id="3dc62-136">**Grupo de recursos:** Escolha ou crie um novo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="3dc62-136">**Resource group:** Choose or create a new resource group.</span></span> <span data-ttu-id="3dc62-137">Um grupo de recursos é um contêiner que contém recursos relacionados para uma solução do Azure.</span><span class="sxs-lookup"><span data-stu-id="3dc62-137">A resource group is a container that holds related resources for an Azure solution.</span></span>

   - <span data-ttu-id="3dc62-138">**Local:** Escolha um local.</span><span class="sxs-lookup"><span data-stu-id="3dc62-138">**Location:** Choose a location.</span></span>

   - <span data-ttu-id="3dc62-139">**Nome do aplicativo Web:** Forneça um nome exclusivo para o aplicativo Web do conector.</span><span class="sxs-lookup"><span data-stu-id="3dc62-139">**Web App Name:** Provide a unique name for the connector web app.</span></span> <span data-ttu-id="3dc62-140">O nome deve ter entre 3 e 18 caracteres.</span><span class="sxs-lookup"><span data-stu-id="3dc62-140">Th name must be between 3 and 18 characters in length.</span></span> <span data-ttu-id="3dc62-141">Esse nome é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, se você fornecer o nome do aplicativo Web **do fbconnector,** a URL do serviço de aplicativo do Azure será **fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="3dc62-141">This name is used to create the Azure app service URL; for example, if you provide the Web app name of **fbconnector** then the Azure app service URL  will be **fbconnector.azurewebsites.net**.</span></span>

   - <span data-ttu-id="3dc62-142">**tenantId:** A ID de locatário da sua organização do Microsoft 365 que você copiou depois de criar o aplicativo de conector do Facebook no Azure Active Directory na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3dc62-142">**tenantId:** The tenant ID of your Microsoft 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 1.</span></span>

   - <span data-ttu-id="3dc62-143">**APISecretKey:** Você pode digitar qualquer valor como o segredo.</span><span class="sxs-lookup"><span data-stu-id="3dc62-143">**APISecretKey:** You can type any value as the secret.</span></span> <span data-ttu-id="3dc62-144">Isso é usado para acessar o aplicativo Web do conector na Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="3dc62-144">This is used to access the connector web app in Step 5.</span></span>

     ![Clique em Criar uma conta de armazenamento de tipo e recurso](../media/FBCimage12.png)

3. <span data-ttu-id="3dc62-146">Depois que a implantação for bem-sucedida, a página será semelhante à seguinte captura de tela:</span><span class="sxs-lookup"><span data-stu-id="3dc62-146">After the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![Clique em Armazenamento e em Conta de armazenamento](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a><span data-ttu-id="3dc62-148">Etapa 3: registrar o aplicativo do Facebook</span><span class="sxs-lookup"><span data-stu-id="3dc62-148">Step 3: Register the Facebook app</span></span>

1. <span data-ttu-id="3dc62-149">Vá para , faça logoff usando as credenciais da conta para as páginas de negócios do Facebook da sua organização e clique em <https://developers.facebook.com> **Adicionar Novo Aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-149">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization's Facebook Business pages, and then click **Add New App**.</span></span>

   ![Adicionar um novo aplicativo para a página de negócios do Facebook](../media/FBCimage25.png)

2. <span data-ttu-id="3dc62-151">Crie uma nova ID de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3dc62-151">Create a new app ID.</span></span>

   ![Criar uma nova ID de aplicativo](../media/FBCimage26.png)

3. <span data-ttu-id="3dc62-153">No painel de navegação esquerdo, clique em **Adicionar Produtos** e, em seguida, clique em Configurar **no** lado do Logon do **Facebook.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-153">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![Clique em Adicionar Produtos](../media/FBCimage27.png)

4. <span data-ttu-id="3dc62-155">Na página Integrar Logon do Facebook, clique **na Web.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-155">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![Clique na Web na página Integrar Logon do Facebook](../media/FBCimage28.png)

5. <span data-ttu-id="3dc62-157">Adicione a URL do serviço de aplicativo do Azure; por `https://fbconnector.azurewebsites.net` exemplo.</span><span class="sxs-lookup"><span data-stu-id="3dc62-157">Add the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   ![Adicionar a URL do serviço de aplicativo do Azure](../media/FBCimage29.png)

6. <span data-ttu-id="3dc62-159">Conclua a seção Guia de Início Rápido da configuração de Logon do Facebook.</span><span class="sxs-lookup"><span data-stu-id="3dc62-159">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![Concluir a seção Guia de Início Rápido](../media/FBCimage30.png)

7. <span data-ttu-id="3dc62-161">No painel de navegação esquerdo em Logon do **Facebook,** clique em Configurações e adicione o URI de redirecionamento OAuth na caixa URIs de redirecionamento **OAuth** válidos.</span><span class="sxs-lookup"><span data-stu-id="3dc62-161">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="3dc62-162">Use o formato **\<connectorserviceuri> /Views/FacebookOAuth**, onde o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo, `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="3dc62-162">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, `https://fbconnector.azurewebsites.net`.</span></span>

   ![Adicionar o URI de redirecionamento OAuth à caixa URIs de redirecionamento OAuth válidos](../media/FBCimage31.png)

8. <span data-ttu-id="3dc62-164">No painel de navegação esquerdo, clique em **Adicionar Produtos** e em **Webhooks.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-164">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="3dc62-165">In the **Page** pull-down menu, click **Page**.</span><span class="sxs-lookup"><span data-stu-id="3dc62-165">In the **Page** pull-down menu, click **Page**.</span></span>

   ![Clique em Adicionar Produtos e em \*\*Webhooks](../media/FBCimage32.png)

9. <span data-ttu-id="3dc62-167">Adicione a URL de retorno de chamada de Webhooks e adicione um token de verificação.</span><span class="sxs-lookup"><span data-stu-id="3dc62-167">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="3dc62-168">O formato da URL de retorno de chamada, use o formato **<connectorserviceuri> /api/FbPageWebhook**, onde o valor para connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por `https://fbconnector.azurewebsites.net` exemplo.</span><span class="sxs-lookup"><span data-stu-id="3dc62-168">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example `https://fbconnector.azurewebsites.net`.</span></span>

   <span data-ttu-id="3dc62-169">O token de verificação deve ser semelhante a uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="3dc62-169">The verify token should similar to a strong password.</span></span> <span data-ttu-id="3dc62-170">Copie o token de verificação para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="3dc62-170">Copy the verify token to a text file or other storage location.</span></span>

   ![Adicionar o token de verificação](../media/FBCimage33.png)

10. <span data-ttu-id="3dc62-172">Teste e inscreva-se no ponto de extremidade para feed.</span><span class="sxs-lookup"><span data-stu-id="3dc62-172">Test and subscribe to the endpoint for feed.</span></span>

    ![Testar e assinar o ponto de extremidade](../media/FBCimage34.png)

11. <span data-ttu-id="3dc62-174">Adicione uma URL de privacidade, um ícone de aplicativo e um uso comercial.</span><span class="sxs-lookup"><span data-stu-id="3dc62-174">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="3dc62-175">Além disso, copie a ID do aplicativo e o segredo do aplicativo para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="3dc62-175">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![Adicionar uma URL de privacidade, um ícone de aplicativo e um uso comercial](../media/FBCimage35.png)

12. <span data-ttu-id="3dc62-177">Tornar o aplicativo público.</span><span class="sxs-lookup"><span data-stu-id="3dc62-177">Make the app public.</span></span>

    ![Tornar o aplicativo público](../media/FBCimage36.png)

13. <span data-ttu-id="3dc62-179">Adicionar usuário à função de administrador ou testador.</span><span class="sxs-lookup"><span data-stu-id="3dc62-179">Add user to the admin or tester role.</span></span>

    ![Adicionar usuário à função de administrador ou testador](../media/FBCimage37.png)

14. <span data-ttu-id="3dc62-181">Adicione a **permissão Acesso a Conteúdo Público de** Página.</span><span class="sxs-lookup"><span data-stu-id="3dc62-181">Add the **Page Public Content Access** permission.</span></span>

    ![dd the Page Public Content Access permission](../media/FBCimage38.png)

15. <span data-ttu-id="3dc62-183">Adicione a permissão Gerenciar Páginas.</span><span class="sxs-lookup"><span data-stu-id="3dc62-183">Add Manage Pages permission.</span></span>

    ![Adicionar permissão Gerenciar Páginas](../media/FBCimage39.png)

16. <span data-ttu-id="3dc62-185">Obter o aplicativo revisado pelo Facebook.</span><span class="sxs-lookup"><span data-stu-id="3dc62-185">Get the application reviewed by Facebook.</span></span>

    ![Obter o aplicativo revisado pelo Facebook](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a><span data-ttu-id="3dc62-187">Etapa 4: Configurar o aplicativo Web do conector</span><span class="sxs-lookup"><span data-stu-id="3dc62-187">Step 4: Configure the connector web app</span></span>

1. <span data-ttu-id="3dc62-188">Vá para (onde AzureAppResourceName é o nome do recurso de aplicativo do `https://<AzureAppResourceName>.azurewebsites.net` Azure nomeado na Etapa 4).</span><span class="sxs-lookup"><span data-stu-id="3dc62-188">Go to `https://<AzureAppResourceName>.azurewebsites.net` (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4).</span></span> <span data-ttu-id="3dc62-189">Por exemplo, se o nome for **fbconnector,** vá para `https://fbconnector.azurewebsites.net` .</span><span class="sxs-lookup"><span data-stu-id="3dc62-189">For example, if the name is **fbconnector**, go to `https://fbconnector.azurewebsites.net`.</span></span> <span data-ttu-id="3dc62-190">A home page do aplicativo terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="3dc62-190">The home page of the app will look like the following screenshot:</span></span>

   ![Vá até o aplicativo Web do conector](../media/FBCimage41.png)

2. <span data-ttu-id="3dc62-192">Clique **em Configurar** para exibir uma página de login.</span><span class="sxs-lookup"><span data-stu-id="3dc62-192">Click **Configure** to display a sign in page.</span></span>

   ![Clique em Configurar para exibir uma página de login](../media/FBCimage42.png)

3. <span data-ttu-id="3dc62-194">Na caixa ID do locatário, digite ou colar a ID do locatário (obtida na Etapa 2).</span><span class="sxs-lookup"><span data-stu-id="3dc62-194">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="3dc62-195">Na caixa de senha, digite ou colar a APISecretKey (obtida na  Etapa 2) e clique em Definir Definições de Configuração para exibir a página de detalhes da configuração.</span><span class="sxs-lookup"><span data-stu-id="3dc62-195">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the configuration details page.</span></span>

    ![Entre usando sua ID de locatário e senha e vá para a página de detalhes de configuração](../media/FBCimage43.png)

4. <span data-ttu-id="3dc62-197">Insira as seguintes definições de configuração</span><span class="sxs-lookup"><span data-stu-id="3dc62-197">Enter the following configuration settings</span></span>

   - <span data-ttu-id="3dc62-198">**ID do aplicativo do Facebook:** A ID do aplicativo do Facebook que você obteve na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="3dc62-198">**Facebook application ID:** The app ID for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="3dc62-199">**Segredo do aplicativo do Facebook:** O segredo do aplicativo do Facebook que você obteve na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="3dc62-199">**Facebook application secret:** The app secret for the Facebook application that you obtained in Step 3.</span></span>

   - <span data-ttu-id="3dc62-200">**Os webhooks do Facebook verificam o token:** O token de verificação criado na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="3dc62-200">**Facebook webhooks verify token:** The verify token that you created in Step 3.</span></span>

   - <span data-ttu-id="3dc62-201">**ID do aplicativo AAD:** A ID do aplicativo do Azure Active Directory que você criou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3dc62-201">**AAD application ID:** The application ID for the Azure Active Directory app that you created in Step 1.</span></span>

   - <span data-ttu-id="3dc62-202">**Segredo do aplicativo AAD:** O valor do segredo APISecretKey que você criou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3dc62-202">**AAD application secret:** The value for the APISecretKey secret that you created in Step 1.</span></span>

5. <span data-ttu-id="3dc62-203">Clique **em Salvar** para salvar as configurações do conector.</span><span class="sxs-lookup"><span data-stu-id="3dc62-203">Click **Save** to save the connector settings.</span></span>

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="3dc62-204">Etapa 5: Configurar um conector do Facebook no centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3dc62-204">Step 5: Set up a Facebook connector in the Microsoft 365 compliance center</span></span>

1. <span data-ttu-id="3dc62-205">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Conectores de dados** na barra de entrada esquerda.</span><span class="sxs-lookup"><span data-stu-id="3dc62-205">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="3dc62-206">Na página **Conectores de dados em** **páginas do Facebook Business,** clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="3dc62-206">On the **Data connectors** page under **Facebook Business pages**, click **View**.</span></span>

3. <span data-ttu-id="3dc62-207">Na página páginas **comerciais do Facebook,** clique **em Adicionar conector.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-207">On the **Facebook business pages** page, click **Add connector**.</span></span>

4. <span data-ttu-id="3dc62-208">Na página **Termos de serviço,** clique em **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="3dc62-208">On the **Terms of service** page, click **Accept**.</span></span>

5. <span data-ttu-id="3dc62-209">Na página **Adicionar credenciais para o aplicativo do** conector, insira as informações a seguir e clique em **Validar conexão.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-209">On the **Add credentials for your connector app** page, enter the following information and then click **Validate connection**.</span></span>

   ![Inserir credenciais do aplicativo do conector](../media/TCimage38.png)

   - <span data-ttu-id="3dc62-211">Na caixa **Nome,** digite um nome para o conector, como a página **de notícias do Facebook.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-211">In the **Name** box, type a name for the connector, such as **Facebook news page**.</span></span>

   - <span data-ttu-id="3dc62-212">Na caixa **URL da Conexão,** digite ou colar a URL do serviço de aplicativo do Azure; por `https://fbconnector.azurewebsites.net` exemplo.</span><span class="sxs-lookup"><span data-stu-id="3dc62-212">In the **Connection URL** box, type or paste the Azure app service URL; for example `https://fbconnector.azurewebsites.net`.</span></span>

   - <span data-ttu-id="3dc62-213">Na caixa **Senha,** digite ou colar o valor da APISecretKey que você adicionou na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3dc62-213">In the **Password** box, type or paste the value of the APISecretKey that you added in Step 2.</span></span>

   - <span data-ttu-id="3dc62-214">Na caixa ID do Aplicativo **do Azure,** digite ou colar o valor da ID do Aplicativo (cliente) também chamada de ID do Aplicativo AAD que você criou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="3dc62-214">In the **Azure App ID** box, type or paste the value of the Application (client) ID also called as AAD Application ID that you created in Step 1.</span></span>

6. <span data-ttu-id="3dc62-215">Depois que a conexão for validada com êxito, clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-215">After the connection is successfully validated, click **Next**.</span></span>

7. <span data-ttu-id="3dc62-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click Login web **app**.</span><span class="sxs-lookup"><span data-stu-id="3dc62-216">On the **Authorize Microsoft 365 to import data** page, type or paste the APISecretKey again and then click **Login web app**.</span></span>

8. <span data-ttu-id="3dc62-217">Na página Configurar aplicativo do conector do **Facebook,** clique em Logon com **o Facebook** e faça logon usando as credenciais da conta das páginas de negócios do Facebook da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3dc62-217">On the **Configure Facebook connector app** page, click **Login with Facebook** and log in using the credentials for the account for your organization's Facebook Business pages.</span></span> <span data-ttu-id="3dc62-218">Certifique-se de que a conta do Facebook à que você entrou tenha a função de administrador para as páginas de negócios do Facebook da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3dc62-218">Make sure the Facebook account that you logged in to is assigned the admin role for your organization's Facebook Business pages.</span></span>

   ![Faça logoff com o Facebook](../media/FBCimage50.png)

9. <span data-ttu-id="3dc62-220">É exibida uma lista das páginas de negócios gerenciadas pela conta do Facebook em que você entrou.</span><span class="sxs-lookup"><span data-stu-id="3dc62-220">A list of the business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="3dc62-221">Selecione a página a ser arquivada e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-221">Select the page to archive and then click **Next**.</span></span>

   ![Selecione a página de negócios da organização que você deseja arquivar](../media/FBCimage52.png)

10. <span data-ttu-id="3dc62-223">Clique **em Continuar** para sair da configuração do aplicativo de serviço do conector.</span><span class="sxs-lookup"><span data-stu-id="3dc62-223">Click **Continue** to exit the setup of the connector service app.</span></span>

11. <span data-ttu-id="3dc62-224">Na página **Definir filtros,** você pode aplicar um filtro para importar inicialmente itens com uma determinada idade.</span><span class="sxs-lookup"><span data-stu-id="3dc62-224">On the **Set filters** page, you can apply a filter to initially import items that are a certain age.</span></span> <span data-ttu-id="3dc62-225">Selecione uma idade e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-225">Select an age, and then click **Next**.</span></span>

12. <span data-ttu-id="3dc62-226">Na página **Escolher local** de armazenamento, digite o endereço de email da caixa de correio do Microsoft 365 para a qual os itens do Facebook serão importados e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="3dc62-226">On the **Choose storage location** page, type the email address of Microsoft 365 mailbox that the Facebook items will be imported to, and then click **Next**.</span></span>

13. <span data-ttu-id="3dc62-227">Clique **em Próximo** para revisar as configurações do conector e clique em **Concluir** para concluir a configuração do conector.</span><span class="sxs-lookup"><span data-stu-id="3dc62-227">Click **Next** to review the connector settings and then click **Finish** to complete the connector setup.</span></span>

14. <span data-ttu-id="3dc62-228">No centro de conformidade,  vá para a página Conectores de dados e clique na guia **Conectores** para ver o progresso do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="3dc62-228">In the compliance center, go to the **Data connectors** page, and click the **Connectors** tab to see the progress of the import process.</span></span>
