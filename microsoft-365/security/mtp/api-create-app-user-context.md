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
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a>Acessar APIs do Microsoft 365 defender em nome do usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 defender em nome de um usuário.

Se você precisar de acesso programático ao Microsoft 365 defender sem um usuário, consulte [criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md).

Se você não tiver certeza de qual acesso você precisa, leia o [Access The Microsoft 365 defender APIs](api-access.md).

O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs permitirão que você automatize fluxos de trabalho e inovações com base nos recursos do Microsoft 365 defender. O acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Em geral, você precisará executar as seguintes etapas para usar as APIs:
- Criar um aplicativo AAD
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API do Microsoft 365 defender

Esta página explica como criar um aplicativo AAD, obter um token de acesso para o Microsoft 365 defender e validar o token.

>[!NOTE]
> Ao acessar a API do Microsoft 365 defender em nome de um usuário, você precisará da permissão de aplicativo e da permissão de usuário corretas.


>[!TIP]
> Se você tem a permissão para executar uma ação no portal, você tem a permissão para executar a ação na API.

## <a name="create-an-app"></a>Criar um aplicativo

1. Faça logon no [Azure](https://portal.azure.com) com um usuário com função de **administrador global** .

2. Navegue até registro de aplicativo **do Azure Active Directory**  >  **App registrations**  >  **novo registro**. 

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. No registro de, digite as informações a seguir e clique em **registrar**.

   ![Imagem da janela de criação de aplicativo](../../media/nativeapp-create2.PNG)

   - **Nome:** O nome do aplicativo
   - **Tipo de aplicativo:** Cliente público
   - **URI de redirecionamento:**https://portal.azure.com

4. Para permitir que seu aplicativo acesse o Microsoft 365 defender e atribuir permissões de ti, na página do aplicativo, selecione **permissões de API**  >  **Adicionar APIs de permissão**  >  **a minha organização usa** >, digite **Microsoft 365 defender** e selecione **Microsoft 365 defender**.

    >[!NOTE]
    > O Microsoft 365 defender não aparece na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.

      ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)

    - Escolha **permissões delegadas** > escolha as permissões relevantes para o seu cenário, por exemplo, **Incident. Read** e, em seguida, selecione **adicionar permissões**.

      ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     >Você precisa selecionar as permissões relevantes. 

    -  Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você está interessado em chamar.

    - Clique em **conceder consentimento**

      >[!NOTE]
      >Toda vez que você adicionar permissão, deverá clicar em **conceder consentimento** para que a nova permissão entre em vigor.

      ![Imagem de conceder permissões](../../media/grant-consent-delegated.PNG)

6. Anote a ID do aplicativo e a ID do locatário:

   - Na página do aplicativo, vá para **visão geral** e copie o seguinte:

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a>Obter um token de acesso usando o PowerShell

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

## <a name="related-topics"></a>Tópicos relacionados
- [Acessar as APIs do Microsoft 365 defender](api-access.md)
- [Acessar o Microsoft 365 defender com contexto de aplicativo](api-create-app-web.md)
