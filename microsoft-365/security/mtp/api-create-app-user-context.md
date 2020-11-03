---
title: Acessar APIs do Microsoft 365 defender usando em nome do usuário
description: Saiba como acessar as APIs do Microsoft 365 defender usando em nome do usuário
keywords: acesso, em nome de usuário, API, aplicativo, usuário, token de acesso, token,
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847351"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a><span data-ttu-id="1e93a-104">Acessar APIs do Microsoft 365 defender em nome do usuário</span><span class="sxs-lookup"><span data-stu-id="1e93a-104">Access Microsoft 365 Defender APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1e93a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1e93a-105">**Applies to:**</span></span>
- <span data-ttu-id="1e93a-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1e93a-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1e93a-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="1e93a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1e93a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="1e93a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="1e93a-109">Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 defender em nome de um usuário.</span><span class="sxs-lookup"><span data-stu-id="1e93a-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a user.</span></span>

<span data-ttu-id="1e93a-110">Se você precisar de acesso programático ao Microsoft 365 defender sem um usuário, consulte [criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="1e93a-110">If you need programmatic access Microsoft 365 Defender without a user, refer to [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="1e93a-111">Se você não tiver certeza de qual acesso você precisa, leia o [Access The Microsoft 365 defender APIs](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="1e93a-111">If you are not sure which access you need, read the [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="1e93a-112">O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação.</span><span class="sxs-lookup"><span data-stu-id="1e93a-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1e93a-113">Essas APIs permitirão que você automatize fluxos de trabalho e inovações com base nos recursos do Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="1e93a-113">Those APIs will enable you to automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="1e93a-114">O acesso à API requer autenticação do OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="1e93a-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1e93a-115">Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="1e93a-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1e93a-116">Em geral, você precisará executar as seguintes etapas para usar as APIs:</span><span class="sxs-lookup"><span data-stu-id="1e93a-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="1e93a-117">Criar um aplicativo AAD</span><span class="sxs-lookup"><span data-stu-id="1e93a-117">Create an AAD application</span></span>
- <span data-ttu-id="1e93a-118">Obter um token de acesso usando este aplicativo</span><span class="sxs-lookup"><span data-stu-id="1e93a-118">Get an access token using this application</span></span>
- <span data-ttu-id="1e93a-119">Usar o token para acessar a API do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1e93a-119">Use the token to access Microsoft 365 Defender API</span></span>

<span data-ttu-id="1e93a-120">Esta página explica como criar um aplicativo AAD, obter um token de acesso para o Microsoft 365 defender e validar o token.</span><span class="sxs-lookup"><span data-stu-id="1e93a-120">This page explains how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="1e93a-121">Ao acessar a API do Microsoft 365 defender em nome de um usuário, você precisará da permissão de aplicativo e da permissão de usuário corretas.</span><span class="sxs-lookup"><span data-stu-id="1e93a-121">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="1e93a-122">Se você tem a permissão para executar uma ação no portal, você tem a permissão para executar a ação na API.</span><span class="sxs-lookup"><span data-stu-id="1e93a-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="1e93a-123">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="1e93a-123">Create an app</span></span>

1. <span data-ttu-id="1e93a-124">Faça logon no [Azure](https://portal.azure.com) com um usuário com função de **administrador global** .</span><span class="sxs-lookup"><span data-stu-id="1e93a-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="1e93a-125">Navegue até registro de aplicativo **do Azure Active Directory**  >  **App registrations**  >  **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="1e93a-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1e93a-127">No registro de, digite as informações a seguir e clique em **registrar**.</span><span class="sxs-lookup"><span data-stu-id="1e93a-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![Imagem da janela de criação de aplicativo](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="1e93a-129">**Nome:** O nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="1e93a-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="1e93a-130">**Tipo de aplicativo:** Cliente público</span><span class="sxs-lookup"><span data-stu-id="1e93a-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="1e93a-131">**URI de redirecionamento:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="1e93a-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="1e93a-132">Para permitir que seu aplicativo acesse o Microsoft 365 defender e atribuir permissões de ti, na página do aplicativo, selecione **permissões de API**  >  **Adicionar APIs de permissão**  >  **a minha organização usa** >, digite **Microsoft 365 defender** e selecione **Microsoft 365 defender**.</span><span class="sxs-lookup"><span data-stu-id="1e93a-132">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="1e93a-133">O Microsoft 365 defender não aparece na lista original.</span><span class="sxs-lookup"><span data-stu-id="1e93a-133">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="1e93a-134">Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.</span><span class="sxs-lookup"><span data-stu-id="1e93a-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="1e93a-136">Escolha **permissões delegadas** > escolha as permissões relevantes para o seu cenário, por exemplo, **Incident. Read** e, em seguida, selecione **adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="1e93a-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read** , and then select **Add permissions**.</span></span>

      ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="1e93a-138">Você precisa selecionar as permissões relevantes.</span><span class="sxs-lookup"><span data-stu-id="1e93a-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="1e93a-139">Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você está interessado em chamar.</span><span class="sxs-lookup"><span data-stu-id="1e93a-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="1e93a-140">Clique em **conceder consentimento**</span><span class="sxs-lookup"><span data-stu-id="1e93a-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="1e93a-141">Toda vez que você adicionar permissão, deverá clicar em **conceder consentimento** para que a nova permissão entre em vigor.</span><span class="sxs-lookup"><span data-stu-id="1e93a-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![Imagem de conceder permissões](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="1e93a-143">Anote a ID do aplicativo e a ID do locatário:</span><span class="sxs-lookup"><span data-stu-id="1e93a-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="1e93a-144">Na página do aplicativo, vá para **visão geral** e copie o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1e93a-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="1e93a-146">Obter um token de acesso usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e93a-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="1e93a-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1e93a-147">Related topics</span></span>
- [<span data-ttu-id="1e93a-148">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="1e93a-148">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1e93a-149">Acessar o Microsoft 365 defender com contexto de aplicativo</span><span class="sxs-lookup"><span data-stu-id="1e93a-149">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
