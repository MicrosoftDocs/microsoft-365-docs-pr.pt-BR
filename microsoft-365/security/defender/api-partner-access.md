---
title: Acesso de parceiros por meio Microsoft 365 APIs do Defender
description: Saiba como criar um aplicativo para obter acesso programático ao Microsoft 365 Defender em nome de seus usuários.
keywords: partner, access, api, multi tenant, consent, access token, app
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
ms.openlocfilehash: 46876fef8a0279ee350d57fdc85aeced82696656
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052843"
---
# <a name="create-an-app-with-partner-access-to-microsoft-365-defender-apis"></a><span data-ttu-id="3c5e5-104">Criar um aplicativo com acesso de parceiro a Microsoft 365 APIs do Defender</span><span class="sxs-lookup"><span data-stu-id="3c5e5-104">Create an app with partner access to Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3c5e5-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3c5e5-105">**Applies to:**</span></span>

- <span data-ttu-id="3c5e5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c5e5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c5e5-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="3c5e5-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="3c5e5-109">Esta página descreve como criar um aplicativo Azure Active Directory que tenha acesso programático ao Microsoft 365 Defender, em nome de usuários em vários locatários.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-109">This page describes how to create an Azure Active Directory app that has programmatic access to Microsoft 365 Defender, on behalf of users across multiple tenants.</span></span> <span data-ttu-id="3c5e5-110">Aplicativos de vários locatários são úteis para atender a grandes grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-110">Multi-tenant apps are useful for serving large groups of users.</span></span>

<span data-ttu-id="3c5e5-111">Se você precisar de acesso programático para Microsoft 365 Defender em nome de um único usuário, consulte Create an app to access [Microsoft 365 Defender APIs em nome](api-create-app-user-context.md)de um usuário .</span><span class="sxs-lookup"><span data-stu-id="3c5e5-111">If you need programmatic access to Microsoft 365 Defender on behalf of a single user, see [Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md).</span></span> <span data-ttu-id="3c5e5-112">Se você precisar de acesso sem um usuário explicitamente definido (por exemplo, se você estiver escrevendo um aplicativo em segundo plano ou daemon), consulte Criar um aplicativo para acessar o [Microsoft 365 Defender](api-create-app-web.md)sem um usuário .</span><span class="sxs-lookup"><span data-stu-id="3c5e5-112">If you need access without a user explicitly defined (for example, if you're writing a background app or daemon), see [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span> <span data-ttu-id="3c5e5-113">Se você não tiver certeza de que tipo de acesso precisa, consulte [Começar](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-113">If you're not sure which kind of access you need, see [Get started](api-access.md).</span></span>

<span data-ttu-id="3c5e5-114">Microsoft 365 O Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-114">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="3c5e5-115">Essas APIs ajudam você a automatizar fluxos de trabalho e usar Microsoft 365 recursos do Defender.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-115">Those APIs help you automate workflows and make use of Microsoft 365 Defender's capabilities.</span></span> <span data-ttu-id="3c5e5-116">Esse acesso à API requer autenticação OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-116">This API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="3c5e5-117">Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-117">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="3c5e5-118">Em geral, você precisará seguir as seguintes etapas para usar estas APIs:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-118">In general, you'll need to take the following steps to use these APIs:</span></span>

- <span data-ttu-id="3c5e5-119">Crie um Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-119">Create an Azure Active Directory (Azure AD) application.</span></span>
- <span data-ttu-id="3c5e5-120">Obter um token de acesso usando este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-120">Get an access token using this application.</span></span>
- <span data-ttu-id="3c5e5-121">Use o token para acessar Microsoft 365 API do Defender.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-121">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="3c5e5-122">Como esse aplicativo é multi locatário, você também precisará do consentimento [de administrador](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) de cada locatário em nome de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-122">Since this app is multi-tenant, you'll also need [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) from each tenant on behalf of its users.</span></span>

<span data-ttu-id="3c5e5-123">Este artigo explica como:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-123">This article explains how to:</span></span>

- <span data-ttu-id="3c5e5-124">Criar um **aplicativo do** Azure AD com vários locatários</span><span class="sxs-lookup"><span data-stu-id="3c5e5-124">Create a **multi-tenant** Azure AD application</span></span>
- <span data-ttu-id="3c5e5-125">Obter consentimento autorizado do administrador do usuário para que seu aplicativo acesse o Microsoft 365 Defender de que ele precisa.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-125">Get authorized consent from your user administrator for your application to access the Microsoft 365 Defender that resources it needs.</span></span>
- <span data-ttu-id="3c5e5-126">Obter um token de acesso para Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c5e5-126">Get an access token to Microsoft 365 Defender</span></span>
- <span data-ttu-id="3c5e5-127">Validar o token</span><span class="sxs-lookup"><span data-stu-id="3c5e5-127">Validate the token</span></span>

<span data-ttu-id="3c5e5-128">Microsoft 365 O Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-128">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="3c5e5-129">Essas APIs ajudarão você a automatizar fluxos de trabalho e inovar com base Microsoft 365 recursos do Defender.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-129">Those APIs will help you automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="3c5e5-130">O acesso à API requer autenticação OAuth2.0.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-130">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="3c5e5-131">Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-131">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="3c5e5-132">Em geral, você precisará seguir as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-132">In general, you’ll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="3c5e5-133">Crie um **aplicativo do** Azure AD com vários locatários.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-133">Create a **multi-tenant** Azure AD application.</span></span>
- <span data-ttu-id="3c5e5-134">Obter autorização (consentimento) do administrador do usuário para que seu aplicativo acesse Microsoft 365 recursos do Defender necessários.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-134">Get authorized (consent) by your user administrator for your application to access Microsoft 365 Defender resources it needs.</span></span>
- <span data-ttu-id="3c5e5-135">Obter um token de acesso usando este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-135">Get an access token using this application.</span></span>
- <span data-ttu-id="3c5e5-136">Use o token para acessar Microsoft 365 API do Defender.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-136">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="3c5e5-137">As etapas a seguir orientam como criar um aplicativo do Azure AD com vários locatários, obter um token de acesso para o Microsoft 365 Defender e validar o token.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-137">The following steps with guide you how to create a multi-tenant Azure AD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

## <a name="create-the-multi-tenant-app"></a><span data-ttu-id="3c5e5-138">Criar o aplicativo de vários locatários</span><span class="sxs-lookup"><span data-stu-id="3c5e5-138">Create the multi-tenant app</span></span>

1. <span data-ttu-id="3c5e5-139">Entre no [Azure como](https://portal.azure.com) um usuário com a função **Administrador Global.**</span><span class="sxs-lookup"><span data-stu-id="3c5e5-139">Sign in to [Azure](https://portal.azure.com) as a user with the **Global Administrator** role.</span></span>

2. <span data-ttu-id="3c5e5-140">Navegue **até Azure Active Directory** registros do  >  **aplicativo** Novo  >  **registro**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-140">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span>

   ![Imagem de Microsoft Azure e navegação para registro de aplicativos](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="3c5e5-142">No formulário de registro:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-142">In the registration form:</span></span>

   - <span data-ttu-id="3c5e5-143">Escolha um nome para seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-143">Choose a name for your application.</span></span>
   - <span data-ttu-id="3c5e5-144">Em **Tipos de conta com suporte,** selecione Contas em qualquer diretório organizacional **(diretório any Azure AD) - Multitenant**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-144">From **Supported account types**, select **Accounts in any organizational directory (Any Azure AD directory) - Multitenant**.</span></span>
   - <span data-ttu-id="3c5e5-145">Preencha a seção **Redirecionar URI.**</span><span class="sxs-lookup"><span data-stu-id="3c5e5-145">Fill out the **Redirect URI** section.</span></span> <span data-ttu-id="3c5e5-146">Selecione tipo **Web** e dê o URI de redirecionamento como **https://portal.azure.com** .</span><span class="sxs-lookup"><span data-stu-id="3c5e5-146">Select type **Web** and give the redirect URI as **https://portal.azure.com**.</span></span>

   <span data-ttu-id="3c5e5-147">Depois de terminar de preencher o formulário, selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-147">After you're done filling out the form, select **Register**.</span></span>

   ![Imagem do formulário Registrar um aplicativo](../..//media/atp-api-new-app-partner.png)

4. <span data-ttu-id="3c5e5-149">Na página do aplicativo, selecione Permissões de **API** Adicionar  >    >  **APIs** de permissão que minha organização usa >, digite Proteção contra Ameaças da Microsoft e selecione Proteção contra Ameaças da Microsoft .</span><span class="sxs-lookup"><span data-stu-id="3c5e5-149">On your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft Threat Protection**, and select **Microsoft Threat Protection**.</span></span> <span data-ttu-id="3c5e5-150">Seu aplicativo agora pode acessar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-150">Your app can now access Microsoft 365 Defender.</span></span>

   > [!TIP]
   > <span data-ttu-id="3c5e5-151">*Proteção contra Ameaças da Microsoft* é um nome antigo para Microsoft 365 Defender e não aparecerá na lista original.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-151">*Microsoft Threat Protection* is a former name for Microsoft 365 Defender, and will not appear in the original list.</span></span> <span data-ttu-id="3c5e5-152">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-152">You need to start writing its name in the text box to see it appear.</span></span>

   ![Imagem da seleção de permissão da API](../../media/apis-in-my-org-tab.PNG)

5. <span data-ttu-id="3c5e5-154">Selecione **Permissões de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-154">Select **Application permissions**.</span></span> <span data-ttu-id="3c5e5-155">Escolha as permissões relevantes para seu cenário (por exemplo, **Incident.Read.All**) e selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-155">Choose the relevant permissions for your scenario (for example, **Incident.Read.All**), and then select **Add permissions**.</span></span>

   ![Imagem do acesso à API e seleção de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > <span data-ttu-id="3c5e5-157">Você precisa selecionar as permissões relevantes para seu cenário.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-157">You need to select the relevant permissions for your scenario.</span></span> <span data-ttu-id="3c5e5-158">*Ler todos os incidentes* é apenas um exemplo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-158">*Read all incidents* is just an example.</span></span> <span data-ttu-id="3c5e5-159">Para determinar de que permissão você precisa, consulte a seção **Permissões** na API que você deseja chamar.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-159">To determine which permission you need, please look at the **Permissions** section in the API you want to call.</span></span>
    >
    > <span data-ttu-id="3c5e5-160">Por exemplo, para [executar consultas avançadas,](api-advanced-hunting.md)selecione a permissão "Executar consultas avançadas"; para [isolar um dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecione a permissão 'Isolar máquina'.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-160">For instance, to [run advanced queries](api-advanced-hunting.md), select the 'Run advanced queries' permission; to [isolate a device](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), select the 'Isolate machine' permission.</span></span>

6. <span data-ttu-id="3c5e5-161">Selecione **Conceder consentimento de administrador**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-161">Select **Grant admin consent**.</span></span> <span data-ttu-id="3c5e5-162">Sempre que você adicionar uma permissão, você deve selecionar **Conceder consentimento de administrador** para que ela entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-162">Every time you add a permission, you must select **Grant admin consent** for it to take effect.</span></span>

    ![Imagem de Permissões de Concessão](../../media/grant-consent.PNG)

7. <span data-ttu-id="3c5e5-164">Para adicionar um segredo ao aplicativo, selecione **Certificados & segredos**, adicione uma descrição ao segredo e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-164">To add a secret to the application, select **Certificates & secrets**, add a description to the secret, then select **Add**.</span></span>

    > [!TIP]
    > <span data-ttu-id="3c5e5-165">Depois de selecionar **Adicionar**, selecione **copiar o valor secreto gerado.**</span><span class="sxs-lookup"><span data-stu-id="3c5e5-165">After you select **Add**, select **copy the generated secret value**.</span></span> <span data-ttu-id="3c5e5-166">Você não poderá recuperar o valor secreto depois de sair.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-166">You won't be able to retrieve the secret value after you leave.</span></span>

    ![Imagem de criar chave de aplicativo](../../media/webapp-create-key2.png)

8. <span data-ttu-id="3c5e5-168">Grave sua ID de aplicativo e sua ID de locatário em algum lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-168">Record your application ID and your tenant ID somewhere safe.</span></span> <span data-ttu-id="3c5e5-169">Eles estão listados em **Visão Geral** na página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-169">They're listed under **Overview** on your application page.</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

9. <span data-ttu-id="3c5e5-171">Adicione o aplicativo ao locatário do usuário.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-171">Add the application to your user's tenant.</span></span>

   <span data-ttu-id="3c5e5-172">Como seu aplicativo interage com o Microsoft 365 Defender em nome de seus usuários, ele precisa ser aprovado para cada locatário no qual você pretende usá-lo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-172">Since your application interacts with Microsoft 365 Defender on behalf of your users, it needs be approved for every tenant on which you intend to use it.</span></span>

   <span data-ttu-id="3c5e5-173">Um **Administrador Global** do locatário do usuário precisa exibir o link de consentimento e aprovar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-173">A **Global Administrator** from your user's tenant needs to view the consent link and approve your application.</span></span>

   <span data-ttu-id="3c5e5-174">O link de consentimento é do formulário:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-174">Consent link is of the form:</span></span>

   ```HTTP
   https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
   ```

   <span data-ttu-id="3c5e5-175">Os dígitos `00000000-0000-0000-0000-000000000000` devem ser substituídos pela ID do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-175">The digits `00000000-0000-0000-0000-000000000000` should be replaced with your Application ID.</span></span>

   <span data-ttu-id="3c5e5-176">Depois de clicar no link de consentimento, entre com o Administrador Global do locatário do usuário e consenta o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-176">After clicking on the consent link, sign in with the Global Administrator of the user's tenant and consent the application.</span></span>

   ![Imagem de consentimento](../../media/app-consent-partner.png)

   <span data-ttu-id="3c5e5-178">Você também precisará solicitar a ID do locatário ao seu usuário.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-178">You'll also need to ask your user for their tenant ID.</span></span> <span data-ttu-id="3c5e5-179">A ID do locatário é um dos identificadores usados para adquirir tokens de acesso.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-179">The tenant ID is one of the identifiers used to acquire access tokens.</span></span>

- <span data-ttu-id="3c5e5-180">**Pronto!**</span><span class="sxs-lookup"><span data-stu-id="3c5e5-180">**Done!**</span></span> <span data-ttu-id="3c5e5-181">Você registrou com êxito um aplicativo!</span><span class="sxs-lookup"><span data-stu-id="3c5e5-181">You've successfully registered an application!</span></span>
- <span data-ttu-id="3c5e5-182">Consulte exemplos abaixo para aquisição e validação de token.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-182">See examples below for token acquisition and validation.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="3c5e5-183">Obter um token de acesso</span><span class="sxs-lookup"><span data-stu-id="3c5e5-183">Get an access token</span></span>

<span data-ttu-id="3c5e5-184">Para obter mais informações sobre tokens do Azure AD, consulte o tutorial do [Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-184">For more information on Azure AD tokens, see the [Azure AD tutorial](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c5e5-185">Embora os exemplos nesta seção incentivem você a colar valores  secretos para fins de teste, você nunca deve codificar segredos em um aplicativo em execução em produção.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-185">Although the examples in this section encourage you to paste in secret values for testing purposes, you should **never hardcode secrets** into an application running in production.</span></span> <span data-ttu-id="3c5e5-186">Um terceiro pode usar seu segredo para acessar recursos.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-186">A third party could use your secret to access resources.</span></span> <span data-ttu-id="3c5e5-187">Você pode ajudar a manter os segredos do seu aplicativo seguros usando o [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates)</span><span class="sxs-lookup"><span data-stu-id="3c5e5-187">You can help keep your app's secrets secure by using [Azure Key Vault](/azure/key-vault/general/about-keys-secrets-certificates).</span></span> <span data-ttu-id="3c5e5-188">Para ver um exemplo prático de como proteger seu aplicativo, consulte Gerenciar segredos em seus aplicativos de servidor com o [Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-188">For a practical example of how you can protect your app, see [Manage secrets in your server apps with Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).</span></span>

> [!TIP]
> <span data-ttu-id="3c5e5-189">Nos exemplos a seguir, use a ID de locatário de um usuário para testar se o script está funcionando.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-189">In the following examples, use a user's tenant ID to test that the script is working.</span></span>

### <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="3c5e5-190">Obter um token de acesso usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="3c5e5-190">Get an access token using PowerShell</span></span>

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place!

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

### <a name="get-an-access-token-using-c"></a><span data-ttu-id="3c5e5-191">Obter um token de acesso usando C\#</span><span class="sxs-lookup"><span data-stu-id="3c5e5-191">Get an access token using C\#</span></span>

> [!NOTE]
> <span data-ttu-id="3c5e5-192">O código a seguir foi testado com Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-192">The following code was tested with Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.</span></span>

1. <span data-ttu-id="3c5e5-193">Crie um novo aplicativo de console.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-193">Create a new console application.</span></span>
1. <span data-ttu-id="3c5e5-194">Instale NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-194">Install NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).</span></span>
1. <span data-ttu-id="3c5e5-195">Adicione a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-195">Add the following line:</span></span>

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. <span data-ttu-id="3c5e5-196">Copie e colar o seguinte código em seu aplicativo (não se esqueça de atualizar as três variáveis: `tenantId` , `clientId` , `appSecret` ):</span><span class="sxs-lookup"><span data-stu-id="3c5e5-196">Copy and paste the following code into your app (don't forget to update the three variables: `tenantId`, `clientId`, `appSecret`):</span></span>

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

### <a name="get-an-access-token-using-python"></a><span data-ttu-id="3c5e5-197">Obter um token de acesso usando Python</span><span class="sxs-lookup"><span data-stu-id="3c5e5-197">Get an access token using Python</span></span>

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

### <a name="get-an-access-token-using-curl"></a><span data-ttu-id="3c5e5-198">Obter um token de acesso usando o cache</span><span class="sxs-lookup"><span data-stu-id="3c5e5-198">Get an access token using curl</span></span>

> [!NOTE]
> <span data-ttu-id="3c5e5-199">O cache é pré-instalado no Windows 10, versões 1803 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-199">Curl is pre-installed on Windows 10, versions 1803 and later.</span></span> <span data-ttu-id="3c5e5-200">Para outras versões do Windows, baixe e instale a ferramenta diretamente do [site de cache oficial.](https://curl.haxx.se/windows/)</span><span class="sxs-lookup"><span data-stu-id="3c5e5-200">For other versions of Windows, download and install the tool directly from the [official curl website](https://curl.haxx.se/windows/).</span></span>

1. <span data-ttu-id="3c5e5-201">Abra um prompt de comando e de CLIENT_ID para sua ID de aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-201">Open a command prompt, and set CLIENT_ID to your Azure application ID.</span></span>
1. <span data-ttu-id="3c5e5-202">De CLIENT_SECRET seu segredo de aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-202">Set CLIENT_SECRET to your Azure application secret.</span></span>
1. <span data-ttu-id="3c5e5-203">De TENANT_ID para a ID de locatário do Azure do usuário que deseja usar seu aplicativo para acessar Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-203">Set TENANT_ID to the Azure tenant ID of the user that wants to use your app to access Microsoft 365 Defender.</span></span>
1. <span data-ttu-id="3c5e5-204">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-204">Run the following command:</span></span>

```bash
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

<span data-ttu-id="3c5e5-205">Uma resposta bem-sucedida terá esta aparência:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-205">A successful response will look like this:</span></span>

```bash
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a><span data-ttu-id="3c5e5-206">Validar o token</span><span class="sxs-lookup"><span data-stu-id="3c5e5-206">Validate the token</span></span>

1. <span data-ttu-id="3c5e5-207">Copie e colar o token no site do validador de [token web JSON, JWT,](https://jwt.ms) para decodificá-lo.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-207">Copy and paste the token into the [JSON web token validator website, JWT,](https://jwt.ms) to decode it.</span></span>
1. <span data-ttu-id="3c5e5-208">Certifique-se de que *as funções* de declaração dentro do token decodificado contenham as permissões desejadas.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-208">Make sure that the *roles* claim within the decoded token contains the desired permissions.</span></span>

<span data-ttu-id="3c5e5-209">Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, com ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` permissões:</span><span class="sxs-lookup"><span data-stu-id="3c5e5-209">In the following image, you can see a decoded token acquired from an app, with ```Incidents.Read.All```, ```Incidents.ReadWrite.All```, and ```AdvancedHunting.Read.All``` permissions:</span></span>

![Imagem da validação de token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a><span data-ttu-id="3c5e5-211">Usar o token para acessar a API Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c5e5-211">Use the token to access the Microsoft 365 Defender API</span></span>

1. <span data-ttu-id="3c5e5-212">Escolha a API que você deseja usar (incidentes ou busca avançada).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-212">Choose the API you want to use (incidents, or advanced hunting).</span></span> <span data-ttu-id="3c5e5-213">Para obter mais informações, consulte [Supported Microsoft 365 Defender APIs](api-supported.md).</span><span class="sxs-lookup"><span data-stu-id="3c5e5-213">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>
2. <span data-ttu-id="3c5e5-214">Na solicitação http que você está prestes a enviar, de definir o cabeçalho de autorização como , o portador é o esquema de autorização e o token sendo `"Bearer" <token>` seu token  validado. </span><span class="sxs-lookup"><span data-stu-id="3c5e5-214">In the http request you're about to send, set the authorization header to `"Bearer" <token>`, *Bearer* being the authorization scheme, and *token* being your validated token.</span></span>
3. <span data-ttu-id="3c5e5-215">O token expirará dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-215">The token will expire within one hour.</span></span> <span data-ttu-id="3c5e5-216">Você pode enviar mais de uma solicitação durante esse tempo com o mesmo token.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-216">You can send more than one request during this time  with the same token.</span></span>

<span data-ttu-id="3c5e5-217">O exemplo a seguir mostra como enviar uma solicitação para obter uma lista de incidentes **usando C#**.</span><span class="sxs-lookup"><span data-stu-id="3c5e5-217">The following example shows how to send a request to get a list of incidents **using C#**.</span></span>

```C#
   var httpClient = new HttpClient();
   var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

   request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

   var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a><span data-ttu-id="3c5e5-218">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="3c5e5-218">Related articles</span></span>

- [<span data-ttu-id="3c5e5-219">Microsoft 365 Visão geral das APIs do Defender</span><span class="sxs-lookup"><span data-stu-id="3c5e5-219">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="3c5e5-220">Acessar as APIs Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c5e5-220">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="3c5e5-221">Criar um aplicativo 'Hello world'</span><span class="sxs-lookup"><span data-stu-id="3c5e5-221">Create a 'Hello world' application</span></span>](api-hello-world.md)
- [<span data-ttu-id="3c5e5-222">Criar um aplicativo para acessar Microsoft 365 Defender sem um usuário</span><span class="sxs-lookup"><span data-stu-id="3c5e5-222">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md)
- [<span data-ttu-id="3c5e5-223">Criar um aplicativo para acessar Microsoft 365 APIs do Defender em nome de um usuário</span><span class="sxs-lookup"><span data-stu-id="3c5e5-223">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md)
- [<span data-ttu-id="3c5e5-224">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="3c5e5-224">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="3c5e5-225">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="3c5e5-225">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="3c5e5-226">Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="3c5e5-226">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="3c5e5-227">Autorização OAuth 2.0 para entrada do usuário e acesso à API</span><span class="sxs-lookup"><span data-stu-id="3c5e5-227">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)