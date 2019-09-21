---
title: Implantar um conector para arquivar dados do Facebook no Office 365
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
description: Os administradores podem configurar um conector nativo para importar e arquivar páginas de negócios do Facebook no Office 365. Depois que esses dados são importados para o Office 365, você pode usar recursos de conformidade, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados de Facebook da sua organização.
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070741"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a><span data-ttu-id="545cb-104">Implantar um conector para arquivar dados do Facebook no Office 365</span><span class="sxs-lookup"><span data-stu-id="545cb-104">Deploy a connector to archive Facebook data in Office 365</span></span>

<span data-ttu-id="545cb-105">Este artigo contém o processo passo a passo para implantar um conector que usa o serviço de importação do Office 365 para importar dados de páginas de negócios do Facebook para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="545cb-105">This article contains the step-by-step process to deploy a connector that uses the Office 365 Import service to import data from Facebook Business pages to Office 365.</span></span> <span data-ttu-id="545cb-106">Para obter uma visão geral de alto nível desse processo e uma lista de pré-requisitos necessários para implantar um conector do Facebook, consulte [usar um conector de exemplo para arquivar dados do Facebook no Office 365 (versão prévia)](archive-facebook-data-with-sample-connector.md).</span><span class="sxs-lookup"><span data-stu-id="545cb-106">For a high-level overview of this process and a list of prerequisites required to deploy a Facebook connector, see [Use a sample connector to archive Facebook data in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md).</span></span> 

## <a name="step-1-download-the-package"></a><span data-ttu-id="545cb-107">Etapa 1: baixar o pacote</span><span class="sxs-lookup"><span data-stu-id="545cb-107">Step 1: Download the package</span></span>

<span data-ttu-id="545cb-108">Baixe o pacote pré-criado da seção liberar no repositório do GitHub em <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span><span class="sxs-lookup"><span data-stu-id="545cb-108">Download the prebuilt package from the Release section in the GitHub repository at <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>.</span></span> <span data-ttu-id="545cb-109">Na versão mais recente, baixe o arquivo zip chamado **SampleConnector. zip**.</span><span class="sxs-lookup"><span data-stu-id="545cb-109">Under the latest release, download the zip file named **SampleConnector.zip**.</span></span> <span data-ttu-id="545cb-110">Você carrega este arquivo zip no Azure na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="545cb-110">You upload this zip file to Azure in Step 4.</span></span>

## <a name="step-2-create-an-app-in-azure-active-directory"></a><span data-ttu-id="545cb-111">Etapa 2: criar um aplicativo no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="545cb-111">Step 2: Create an app in Azure Active Directory</span></span>

1. <span data-ttu-id="545cb-112">Vá para <https://portal.azure.com> e entre usando as credenciais de uma conta de administrador global do Office 365.</span><span class="sxs-lookup"><span data-stu-id="545cb-112">Go to <https://portal.azure.com> and sign in using the credentials of an Office 365 global admin account.</span></span>

    ![Criar aplicativo no AAD](media/FBCimage1.png)

2. <span data-ttu-id="545cb-114">No painel de navegação esquerdo, clique em **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="545cb-114">In the left navigation pane, click **Azure Active Directory**.</span></span>

    ![](media/FBCimage2.png)

3. <span data-ttu-id="545cb-115">No painel de navegação esquerdo, clique em **registros de aplicativo (visualização)** e clique em **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="545cb-115">In the left navigation pane, click **App registrations (Preview)** and then click **New registration**.</span></span>

    ![](media/FBCimage3.png)

4. <span data-ttu-id="545cb-116">Registre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="545cb-116">Register the application.</span></span> <span data-ttu-id="545cb-117">Em URI de redirecionamento, selecione Web na lista suspensa tipo de aplicativo <https://portal.azure.com> e digite na caixa para o URI.</span><span class="sxs-lookup"><span data-stu-id="545cb-117">Under Redirect URI, select Web in the application type dropdown list and then type <https://portal.azure.com> in the box for the URI.</span></span>

   ![](media/FBCimage4.png)

5. <span data-ttu-id="545cb-118">Copie a ID de **aplicativo (cliente)** e a ID de **diretório (locatário)** e salve-as em um arquivo de texto ou outro local seguro.</span><span class="sxs-lookup"><span data-stu-id="545cb-118">Copy the **Application (client) ID** and **Directory (tenant) ID** and save them to a text file or other safe location.</span></span> <span data-ttu-id="545cb-119">Você usa essas IDs em etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="545cb-119">You use these IDs in later steps.</span></span>

   ![](media/FBCimage5.png)

6. <span data-ttu-id="545cb-120">Vá até **certificados & segredos para o novo aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="545cb-120">Go to **Certificates & secrets for the new app.**</span></span>

   ![](media/FBCimage6.png)

7. <span data-ttu-id="545cb-121">Clique em **novo segredo do cliente**</span><span class="sxs-lookup"><span data-stu-id="545cb-121">Click **New client secret**</span></span>

   ![](media/FBCimage7.png)

8. <span data-ttu-id="545cb-122">Criar um novo segredo.</span><span class="sxs-lookup"><span data-stu-id="545cb-122">Create a new secret.</span></span> <span data-ttu-id="545cb-123">Na caixa Descrição, digite o segredo e, em seguida, escolha um período de expiração.</span><span class="sxs-lookup"><span data-stu-id="545cb-123">In the description box, type the secret and then choose an expiration period.</span></span> 

    ![](media/FBCimage8.png)

9. <span data-ttu-id="545cb-124">Copie o valor do segredo e salve-o em um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-124">Copy the value of the secret and save it to a text file or other storage location.</span></span> <span data-ttu-id="545cb-125">Este é o segredo do aplicativo AAD que você usa nas etapas posteriores.</span><span class="sxs-lookup"><span data-stu-id="545cb-125">This is the AAD application secret that you use in later steps.</span></span>

   ![](media/FBCimage9.png)

10. <span data-ttu-id="545cb-126">Vá para **manifesto** e copie o identifieruris agora (que também é chamado de URI do aplicativo AAD) como realçado na captura de tela a seguir.</span><span class="sxs-lookup"><span data-stu-id="545cb-126">Go to **Manifest** and copy the identifierUris (which is also called the AAD application Uri) as highlighted in the following screenshot.</span></span> <span data-ttu-id="545cb-127">Copie o URI do aplicativo AAD para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-127">Copy the AAD application Uri to a text file or other storage location.</span></span> <span data-ttu-id="545cb-128">Você pode usá-lo na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="545cb-128">You use it in Step 6.</span></span>

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a><span data-ttu-id="545cb-129">Etapa 3: criar uma conta de armazenamento do Azure</span><span class="sxs-lookup"><span data-stu-id="545cb-129">Step 3: Create an Azure storage account</span></span>

1. <span data-ttu-id="545cb-130">Vá para a home page do Azure para sua organização.</span><span class="sxs-lookup"><span data-stu-id="545cb-130">Go to the Azure home page for your organization.</span></span>

    ![](media/FBCimage11.png)

2. <span data-ttu-id="545cb-131">Clique em **criar um recurso** e digite a **conta de armazenamento** na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="545cb-131">Click **Create a resource** and they type **storage account** in the search box.</span></span>

    ![](media/FBCimage12.png)

3. <span data-ttu-id="545cb-132">Clique em **armazenamento**e, em seguida, clique em **conta de armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="545cb-132">Click **Storage**, and then click **Storage account**.</span></span>

    ![](media/FBCimage13.png)

4. <span data-ttu-id="545cb-133">Na página **criar conta de armazenamento** , na caixa assinatura, selecione **pagar como você** ou **avaliação gratuita** , dependendo do tipo de assinatura do Azure que você tem.</span><span class="sxs-lookup"><span data-stu-id="545cb-133">On the **Create storage account** page, in the Subscription box, select **Pay-As-You-Go** or **Free Trial** depending on which type of Azure subscription you have.</span></span> <span data-ttu-id="545cb-134">Em seguida, selecione ou crie um grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="545cb-134">Then select or create a resource group.</span></span>

    ![](media/FBCimage14.png)

5. <span data-ttu-id="545cb-135">Digite um nome para a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-135">Type a name for the storage account.</span></span>

    ![](media/FBCimage15.png)

6. <span data-ttu-id="545cb-136">Revise e clique em **criar** para criar a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-136">Review and then click **Create** to create the storage account.</span></span>

    ![](media/FBCimage16.png)

7. <span data-ttu-id="545cb-137">Após alguns momentos, clique em **Atualizar** e clique em **ir para recurso** para navegar até a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-137">After a few moments, click **Refresh** and then click **Go to resource** to navigate to the storage account.</span></span>

    ![](media/FBCimage17.png)

8. <span data-ttu-id="545cb-138">Clique em **teclas de acesso** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="545cb-138">Click **Access keys** in the left navigation pane.</span></span>

    ![](media/FBCimage18.png)

9. <span data-ttu-id="545cb-139">Copie uma **cadeia de caracteres de conexão** e salve-a em um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-139">Copy a **Connection string** and save it to a text file or other storage location.</span></span> <span data-ttu-id="545cb-140">Você usa isso ao criar um recurso do aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="545cb-140">You use this when creating a web app resource.</span></span>

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a><span data-ttu-id="545cb-141">Etapa 4: criar um novo recurso do aplicativo Web no Azure</span><span class="sxs-lookup"><span data-stu-id="545cb-141">Step 4: Create a new web app resource in Azure</span></span>

1. <span data-ttu-id="545cb-142">Na **Home** Page do portal do Azure, clique em **criar um recurso \> para \> todos os aplicativos Web**.</span><span class="sxs-lookup"><span data-stu-id="545cb-142">On the **Home** page in the Azure portal, click **Create a resource \> Everything \> Web app**.</span></span> <span data-ttu-id="545cb-143">Na página **Web App** , clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="545cb-143">On the **Web app** page, click **Create**.</span></span> 

   ![](media/FBCimage20.png)

2. <span data-ttu-id="545cb-144">Preencha os detalhes (conforme mostrado abaixo) e, em seguida, crie o aplicativo Web.</span><span class="sxs-lookup"><span data-stu-id="545cb-144">Fill in the details (as shown below) and then create the Web app.</span></span> <span data-ttu-id="545cb-145">Observe que o nome inserido na caixa nome do **aplicativo** é usado para criar a URL do serviço de aplicativo do Azure; por exemplo, fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="545cb-145">Note that the name that you enter in the **App name** box is used to create the Azure app service URL; for example, fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage21.png)

3. <span data-ttu-id="545cb-146">Vá para o recurso aplicativo Web recém-criado, clique em **configurações do aplicativo** no painel de navegação esquerdo.</span><span class="sxs-lookup"><span data-stu-id="545cb-146">Go to the newly created web app resource, click **Application Settings** in the left navigation pane.</span></span> <span data-ttu-id="545cb-147">Em configurações do aplicativo, clique em Adicionar nova configuração e adicione as três configurações a seguir: Use os valores (que você copiou para o arquivo de texto das etapas anteriores):</span><span class="sxs-lookup"><span data-stu-id="545cb-147">Under Application settings, click Add new setting and add the following three settings: Use the values (that you copied to the text file from the previous steps):</span></span> 

    <span data-ttu-id="545cb-148">– **APISecretKey** – você pode digitar qualquer valor como o segredo.</span><span class="sxs-lookup"><span data-stu-id="545cb-148">– **APISecretKey** – You can type any value as the secret.</span></span> <span data-ttu-id="545cb-149">Isso é usado para acessar o aplicativo Web do conector na etapa 7.</span><span class="sxs-lookup"><span data-stu-id="545cb-149">This is used to access the connector web app in Step 7.</span></span>

    <span data-ttu-id="545cb-150">– \* \* StorageAccountConnectionString — o URI da cadeia de caracteres de conexão que você copiou após a criação da conta de armazenamento do Azure na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="545cb-150">– \*\*StorageAccountConnectionString — The connection string Uri that you copied after creating the Azure storage account in Step 3.</span></span>

    <span data-ttu-id="545cb-151">– **tenantid** – a ID do locatário de sua organização do Office 365 que você copiou depois de criar o aplicativo do Facebook Connector no Azure Active Directory na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="545cb-151">– **tenantId** – The tenant ID of your Office 365 organization that you copied after creating the Facebook connector app in Azure Active Directory in Step 2.</span></span>

    ![](media/FBCimage22.png)

4. <span data-ttu-id="545cb-152">Em **configurações gerais**, clique **em** ao lado de **sempre ligado**.</span><span class="sxs-lookup"><span data-stu-id="545cb-152">Under **General settings**, click **On** next to the **Always On**.</span></span> <span data-ttu-id="545cb-153">Clique em **salvar** na parte superior da página para salvar as configurações do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="545cb-153">Click **Save** at the top of the page to save application settings.</span></span>

   ![](media/FBCimage23.png)

5. <span data-ttu-id="545cb-154">A etapa final é carregar o código-fonte do aplicativo conector para o Azure que você baixou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="545cb-154">The final step is to upload the connector app source code to Azure that you downloaded in Step 1.</span></span> <span data-ttu-id="545cb-155">Em um navegador da Web, vá para<AzureAppResourceName>https://. SCM.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="545cb-155">In a web browser, go to https://<AzureAppResourceName>.scm.azurewebsites.net/ZipDeployUi.</span></span> <span data-ttu-id="545cb-156">Por exemplo, se o nome do seu recurso de aplicativo do Azure (que você nomeou na etapa 2 nesta seção) for **fbconnector**, vá para https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span><span class="sxs-lookup"><span data-stu-id="545cb-156">For example, if the name of your Azure app resource (which you named in step 2 in this section) is **fbconnector**, then you would go to https://fbconnector.scm.azurewebsites.net/ZipDeployUi.</span></span> 

6. <span data-ttu-id="545cb-157">Arraste e solte o SampleConnector. zip (que você baixou na etapa 1) para esta página.</span><span class="sxs-lookup"><span data-stu-id="545cb-157">Drag and drop the SampleConnector.zip (that you downloaded in Step 1) to this page.</span></span> <span data-ttu-id="545cb-158">Após o carregamento dos arquivos e a implantação ter êxito, a página será semelhante à captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="545cb-158">After the files are uploaded and the deployment is successful, the page will look similar to the following screenshot:</span></span>

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a><span data-ttu-id="545cb-159">Etapa 5: registrar o aplicativo do Facebook</span><span class="sxs-lookup"><span data-stu-id="545cb-159">Step 5: Register the Facebook app</span></span>

1. <span data-ttu-id="545cb-160">Vá para <https://developers.facebook.com>, faça logon usando as credenciais da conta das páginas de negócios de Facebook da sua organização e clique em **Adicionar novo aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="545cb-160">Go to <https://developers.facebook.com>, log in using the credentials for the account for your organization’s Facebook Business pages, and then click **Add New App**.</span></span>

   ![](media/FBCimage25.png)

2. <span data-ttu-id="545cb-161">Crie uma nova ID de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="545cb-161">Create a new app ID.</span></span>

   ![](media/FBCimage26.png)

3. <span data-ttu-id="545cb-162">No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **Configurar** no bloco de **logon do Facebook** .</span><span class="sxs-lookup"><span data-stu-id="545cb-162">In the left navigation pane, click **Add Products** and then click **Set Up** in the **Facebook Login** tile.</span></span>

   ![](media/FBCimage27.png)

4. <span data-ttu-id="545cb-163">Na página integrar login do Facebook, clique em **Web**.</span><span class="sxs-lookup"><span data-stu-id="545cb-163">On the Integrate Facebook Login page, click **Web**.</span></span>

   ![](media/FBCimage28.png)

5. <span data-ttu-id="545cb-164">Adicione a URL do serviço de aplicativo do Azure; por exemplo https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="545cb-164">Add the Azure app service URL; for example https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage29.png)

6. <span data-ttu-id="545cb-165">Preencha a seção QuickStart da configuração de login do Facebook.</span><span class="sxs-lookup"><span data-stu-id="545cb-165">Complete the QuickStart section of the Facebook Login setup.</span></span>

   ![](media/FBCimage30.png)

7. <span data-ttu-id="545cb-166">No painel de navegação esquerdo em **logon do Facebook**, clique em **configurações**e adicione o URI de redirecionamento OAuth na caixa **URIs de redirecionamento OAuth válidos** .</span><span class="sxs-lookup"><span data-stu-id="545cb-166">In the left navigation pane under **Facebook Login**, click **Settings**, and add the OAuth redirect URI in the **Valid OAuth Redirect URIs** box.</span></span> <span data-ttu-id="545cb-167">Use o formato \*\* \<connectorserviceuri>/views/facebookoauth\*\*, onde o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo, https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="545cb-167">Use the format **\<connectorserviceuri>/Views/FacebookOAuth**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example, https://fbconnector.azurewebsites.net.</span></span>

   ![](media/FBCimage31.png)

8. <span data-ttu-id="545cb-168">No painel de navegação esquerdo, clique em **Adicionar produtos** e, em seguida, clique em **WebHooks.**</span><span class="sxs-lookup"><span data-stu-id="545cb-168">In the left navigation pane, click **Add Products** and then click **Webhooks.**</span></span> <span data-ttu-id="545cb-169">No menu suspenso da **página** , clique em **página**.</span><span class="sxs-lookup"><span data-stu-id="545cb-169">In the **Page** pull-down menu, click **Page**.</span></span> 

   ![](media/FBCimage32.png)

9. <span data-ttu-id="545cb-170">Adicione URL de retorno de chamada de WebHooks e adicione um token de verificação.</span><span class="sxs-lookup"><span data-stu-id="545cb-170">Add Webhooks Callback URL and add a verify token.</span></span> <span data-ttu-id="545cb-171">O formato da URL de retorno de chamada, use o formato \*\* <connectorserviceuri>/API/FbPageWebhook\*\*, em que o valor de connectorserviceuri é a URL do serviço de aplicativo do Azure para sua organização; por exemplo https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="545cb-171">The format of the callback URL, use the format **<connectorserviceuri>/api/FbPageWebhook**, where the value for connectorserviceuri is the Azure app service URL for your organization; for example https://fbconnector.azurewebsites.net.</span></span> 

    <span data-ttu-id="545cb-172">O token de verificação deve ser semelhante a uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="545cb-172">The verify token should similar to a strong password.</span></span> <span data-ttu-id="545cb-173">Copie o token de verificação para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-173">Copy the verify token to a text file or other storage location.</span></span>

     ![](media/FBCimage33.png)

10. <span data-ttu-id="545cb-174">Teste e assine o ponto de extremidade do feed.</span><span class="sxs-lookup"><span data-stu-id="545cb-174">Test and subscribe to the endpoint for feed.</span></span>

    ![](media/FBCimage34.png)

11. <span data-ttu-id="545cb-175">Adicione uma URL de privacidade, ícone de aplicativo e uso comercial.</span><span class="sxs-lookup"><span data-stu-id="545cb-175">Add a privacy URL, app icon, and business use.</span></span> <span data-ttu-id="545cb-176">Além disso, copie a ID do aplicativo e o segredo do aplicativo para um arquivo de texto ou outro local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="545cb-176">Also, copy the app ID and app secret to a text file or other storage location.</span></span>

    ![](media/FBCimage35.png)

12. <span data-ttu-id="545cb-177">Tornar o aplicativo público.</span><span class="sxs-lookup"><span data-stu-id="545cb-177">Make the app public.</span></span>

    ![](media/FBCimage36.png)

13. <span data-ttu-id="545cb-178">Adicionar usuário à função de administrador ou de testador.</span><span class="sxs-lookup"><span data-stu-id="545cb-178">Add user to the admin or tester role.</span></span>

    ![](media/FBCimage37.png)

14. <span data-ttu-id="545cb-179">Adicione a permissão de **acesso ao conteúdo público da página** .</span><span class="sxs-lookup"><span data-stu-id="545cb-179">Add the **Page Public Content Access** permission.</span></span>

    ![](media/FBCimage38.png)

15. <span data-ttu-id="545cb-180">Permissão Adicionar gerenciar páginas.</span><span class="sxs-lookup"><span data-stu-id="545cb-180">Add Manage Pages permission.</span></span>

    ![](media/FBCimage39.png)

16. <span data-ttu-id="545cb-181">Obtenha o aplicativo revisado pelo Facebook.</span><span class="sxs-lookup"><span data-stu-id="545cb-181">Get the application reviewed by Facebook.</span></span>

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a><span data-ttu-id="545cb-182">Etapa 6: configurar o aplicativo Web do conector</span><span class="sxs-lookup"><span data-stu-id="545cb-182">Step 6: Configure the connector web app</span></span>

1. <span data-ttu-id="545cb-183">Vá para https://\<AzureAppResourceName>. azurewebsites.net (onde AzureAppResourceName é o nome do seu recurso do aplicativo do Azure que você nomeou na etapa 4) por exemplo, se o nome for **fbconnector**, vá para https://fbconnector.azurewebsites.net.</span><span class="sxs-lookup"><span data-stu-id="545cb-183">Go to https://\<AzureAppResourceName>.azurewebsites.net (where AzureAppResourceName is the name of your Azure app resource that you named in Step 4) For example, if the name is **fbconnector**, go to https://fbconnector.azurewebsites.net.</span></span> <span data-ttu-id="545cb-184">A home page do aplicativo se parecerá com a captura de tela a seguir:</span><span class="sxs-lookup"><span data-stu-id="545cb-184">The home page of the app will look like the following screenshot:</span></span>


   ![](media/FBCimage41.png)

2. <span data-ttu-id="545cb-185">Clique em **Configurar** para exibir uma página de entrada.</span><span class="sxs-lookup"><span data-stu-id="545cb-185">Click **Configure** to display a sign in page.</span></span>
 
   ![](media/FBCimage42.png)

3. <span data-ttu-id="545cb-186">Na caixa ID do locatário, digite ou cole sua ID de locatário (que você obteve na etapa 2).</span><span class="sxs-lookup"><span data-stu-id="545cb-186">In the Tenant Id box, type or paste your tenant Id (that you obtained in Step 2).</span></span> <span data-ttu-id="545cb-187">Na caixa senha, digite ou cole o APISecretKey (que você obteve na etapa 2) e clique em **definir definições de configuração** para exibir a página **detalhes da configuração** .</span><span class="sxs-lookup"><span data-stu-id="545cb-187">In the password box, type or paste the APISecretKey (that you obtained in Step 2), and then click **Set Configuration Settings** to display the **Configuration Details** page.</span></span>

    ![](media/FBCimage43.png)


4. <span data-ttu-id="545cb-188">Em **detalhes da configuração**, insira as seguintes definições de configuração</span><span class="sxs-lookup"><span data-stu-id="545cb-188">Under **Configuration Details**, enter the following configuration settings</span></span> 

   <span data-ttu-id="545cb-189">– **ID do aplicativo do Facebook** – a ID do aplicativo para o aplicativo Facebook obtido na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="545cb-189">– **Facebook application ID** – The app ID for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="545cb-190">– **Segredo do aplicativo do Facebook** – o segredo do aplicativo para o aplicativo do Facebook obtido na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="545cb-190">– **Facebook application secret** – The app secret for the Facebook application that you obtained in Step 5.</span></span>
   <span data-ttu-id="545cb-191">– **Token de verificação de WebHooks do Facebook** – o token de verificação que você criou na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="545cb-191">– **Facebook webhooks verify token** – The verify token that you created in Step 5.</span></span>
   <span data-ttu-id="545cb-192">– **ID do aplicativo AAD** – a ID do aplicativo para o aplicativo do Azure Active Directory que você criou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="545cb-192">– **AAD application ID** – The application ID for the Azure Active Directory app that you created in Step 2.</span></span>
   <span data-ttu-id="545cb-193">– **Segredo do aplicativo AAD** – o valor para o segredo APISecretKey que você criou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="545cb-193">– **AAD application secret** – The value for the APISecretKey secret that you created in Step 4.</span></span>
   <span data-ttu-id="545cb-194">– **URI do aplicativo AAD** – o URI do aplicativo AAD obtido na etapa 2; por exemplo, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span><span class="sxs-lookup"><span data-stu-id="545cb-194">– **AAD application Uri** – The AAD application Uri obtained in Step 2; for example, https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.</span></span>
   <span data-ttu-id="545cb-195">– **Chave de instrumentação do App insights** – deixe esta caixa em branco.</span><span class="sxs-lookup"><span data-stu-id="545cb-195">– **App insights instrumentation key** – Leave this box blank.</span></span>

5. <span data-ttu-id="545cb-196">Clique em **salvar** para salvar as configurações do conector.</span><span class="sxs-lookup"><span data-stu-id="545cb-196">Click **Save** to save the connector settings.</span></span>

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a><span data-ttu-id="545cb-197">Etapa 7: configurar um conector personalizado no centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="545cb-197">Step 7: Set up a custom connector in the Security & Compliance Center</span></span>

1. <span data-ttu-id="545cb-198">Vá para <https://protection.office.com> e, em seguida, clique em **arquivar importação \> \> de governança de dados dados de terceiros**.</span><span class="sxs-lookup"><span data-stu-id="545cb-198">Go to <https://protection.office.com> and then click **Data governance \> Import \> Archive third-party data**.</span></span>

   ![](media/FBCimage44.png)

2.  <span data-ttu-id="545cb-199">Clique em **Adicionar um conector** e, em seguida, clique em **páginas do Facebook**.</span><span class="sxs-lookup"><span data-stu-id="545cb-199">Click **Add a connector** and then click **Facebook pages**.</span></span>

    ![](media/FBCimage46.png)

3.  <span data-ttu-id="545cb-200">Na página **Adicionar aplicativo do conector** , digite as informações a seguir e clique em **validar conector**.</span><span class="sxs-lookup"><span data-stu-id="545cb-200">On the **Add Connector App** page, enter the following information and then click **Validate connector**.</span></span>

    <span data-ttu-id="545cb-201">– Na primeira caixa, digite um nome para o conector, como o **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="545cb-201">– In the first box, type a name for the connector, such as **Facebook**.</span></span>
    <span data-ttu-id="545cb-202">– Na segunda caixa, digite ou cole o valor do APISecretKey que você adicionou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="545cb-202">– In the second box, type or paste the value of the APISecretKey that you added in Step 4.</span></span>
    <span data-ttu-id="545cb-203">– Na terceira caixa, digite ou cole a URL do serviço de aplicativo do Azure; por exemplo **https://fbconnector.azurewebsites.net**.</span><span class="sxs-lookup"><span data-stu-id="545cb-203">– In the third box, type or paste the Azure app service URL; for example **https://fbconnector.azurewebsites.net**.</span></span>
 
    <span data-ttu-id="545cb-204">Depois que o conector for validado com êxito, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="545cb-204">After the connector is successfully validated, click **Next**.</span></span>
    
    ![](media/FBCimage47.png)

4.  <span data-ttu-id="545cb-205">Clique em **login com o aplicativo do conector**.</span><span class="sxs-lookup"><span data-stu-id="545cb-205">Click **Login with Connector App**.</span></span>

    ![](media/FBCimage45.png)

5. <span data-ttu-id="545cb-206">Digite ou cole o APISecretKey novamente e, em seguida, clique em **login to Connector Service**.</span><span class="sxs-lookup"><span data-stu-id="545cb-206">Type or paste the APISecretKey again and then click  **Login to Connector Service**.</span></span>

   ![](media/FBCimage48.png)


6. <span data-ttu-id="545cb-207">Clique em **login com o Facebook.**</span><span class="sxs-lookup"><span data-stu-id="545cb-207">Click **Login with Facebook.**</span></span>

   ![](media/FBCimage49.png)

7. <span data-ttu-id="545cb-208">Na página **fazer logon no Facebook** , faça o login usando as credenciais da conta das páginas de negócios de Facebook da sua organização.</span><span class="sxs-lookup"><span data-stu-id="545cb-208">On the **Log in to Facebook** page, log in using the credentials for the account for your organization’s Facebook Business pages.</span></span> <span data-ttu-id="545cb-209">Certifique-se de que a conta do Facebook na qual você está conectado tenha a função de administrador para as páginas de negócios de Facebook da sua organização</span><span class="sxs-lookup"><span data-stu-id="545cb-209">Make sure the Facebook account that you logged in to is assigned the admin role for your organization’s Facebook Business pages</span></span>

   ![](media/FBCimage50.png)

8. <span data-ttu-id="545cb-210">Clique em **selecionar páginas** para escolher as páginas comerciais da sua organização que você deseja arquivar no Office 365.</span><span class="sxs-lookup"><span data-stu-id="545cb-210">Click **Select Pages** to choose your organization’s business pages that you want to archive in Office 365.</span></span>

   ![](media/FBCimage51.png)

9. <span data-ttu-id="545cb-211">É exibida uma lista das páginas de negócios gerenciadas pela conta do Facebook que você fez logon.</span><span class="sxs-lookup"><span data-stu-id="545cb-211">A list of the Business pages managed by the Facebook account that you logged in to is displayed.</span></span> <span data-ttu-id="545cb-212">Selecione a página para arquivar e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="545cb-212">Select the page to archive and then click **Save**.</span></span>

    ![](media/FBCimage52.png)

10. <span data-ttu-id="545cb-213">Clique em **preparar** para sair da configuração do aplicativo de serviço do conector.</span><span class="sxs-lookup"><span data-stu-id="545cb-213">Click **prepare** to exit the setup of the connector service app.</span></span>

    ![](media/FBCimage53.png)

11. <span data-ttu-id="545cb-214">Na página **definir filtros** , você pode aplicar um filtro para importar (e arquivar) itens que são uma determinada idade.</span><span class="sxs-lookup"><span data-stu-id="545cb-214">On the **Set Filters** page, you can apply a filter to import (and archive) items that are a certain age.</span></span> <span data-ttu-id="545cb-215">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="545cb-215">Click **Next**.</span></span>

    ![](media/FBCimage54.png)

12. <span data-ttu-id="545cb-216">Na página **definir conta de armazenamento** , selecione a caixa de correio do Office 365 que os itens das páginas de negócios do Facebook que você selecionou anteriormente serão importados.</span><span class="sxs-lookup"><span data-stu-id="545cb-216">On the **Set Storage Account** page, select the Office 365 mailbox that the items from the Facebook Business pages that you previously selected will be imported to.</span></span>

    ![](media/FBCimage55.png)

13. <span data-ttu-id="545cb-217">Revise suas configurações e clique em **concluir** para concluir a configuração do conector no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="545cb-217">Review your settings and then click **Finish** to complete the connector setup in the Security & Compliance Center.</span></span>

    ![](media/FBCimage56.png)

14. <span data-ttu-id="545cb-218">Vá para a página **arquivar dados** de terceiros para ver o andamento do processo de importação.</span><span class="sxs-lookup"><span data-stu-id="545cb-218">Go to the **Archive third-party data** page to see the progress of the import process.</span></span>

    ![](media/FBCimage58.png)
