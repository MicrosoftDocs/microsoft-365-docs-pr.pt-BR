---
title: Acessar APIs de proteção contra ameaças da Microsoft usando em nome do usuário
description: Saiba como acessar as APIs de proteção contra ameaças da Microsoft usando em nome do usuário
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
ms.openlocfilehash: a62d90004d00e8c553f1b011e77b871df7cd94f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197792"
---
# <a name="access-microsoft-threat-protection-apis-on-behalf-of-user"></a>Acessar as APIs de proteção contra ameaças da Microsoft em nome do usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


Esta página descreve como criar um aplicativo para obter acesso programático à proteção contra ameaças da Microsoft em nome de um usuário.

Se você precisar de acesso programático à proteção contra ameaças da Microsoft sem um usuário, consulte [criar um aplicativo para acessar a proteção contra ameaças da Microsoft sem um usuário](api-create-app-web.md).

Se você não tiver certeza de qual acesso você precisa, leia as [APIs de proteção contra ameaças da Microsoft](api-access.md).

A proteção contra ameaças da Microsoft expõe muito de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs permitirão que você automatize fluxos de trabalho e inovações com base nos recursos de proteção contra ameaças da Microsoft. O acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Em geral, você precisará executar as seguintes etapas para usar as APIs:
- Criar um aplicativo AAD
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API de proteção contra ameaças da Microsoft

Esta página explica como criar um aplicativo AAD, obter um token de acesso para a proteção contra ameaças da Microsoft e validar o token.

>[!NOTE]
> Ao acessar a API de proteção contra ameaças da Microsoft em nome de um usuário, você precisará da permissão de aplicativo e da permissão de usuário corretas.


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

4. Para permitir que seu aplicativo acesse a proteção contra ameaças da Microsoft e atribuir permissões de ti, na página do aplicativo, selecione **permissões de API**  >  **Adicionar APIs de permissão**  >  **minha organização usa** >, digite **proteção contra ameaças da Microsoft**e selecione **proteção contra ameaças da Microsoft**.

    >[!NOTE]
    > A proteção contra ameaças da Microsoft não aparece na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.

      ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)

    - Escolha **permissões delegadas** > escolha as permissões relevantes para o seu cenário, por exemplo, **Incident. Read**e, em seguida, selecione **adicionar permissões**.

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
- [Acessar as APIs de proteção contra ameaças da Microsoft](api-access.md)
- [Acesso à proteção contra ameaças da Microsoft com contexto de aplicativo](api-create-app-web.md)
