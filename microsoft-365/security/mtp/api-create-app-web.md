---
title: Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário
description: Saiba como criar um aplicativo para acessar o Microsoft 365 defender sem um usuário
keywords: aplicativo, Access, API, criar
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
ms.openlocfilehash: 446db803cc47bfd519642928a4a0257c4b3d57c8
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846063"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 defender sem um usuário. Se você precisar de acesso programático ao Microsoft 365 defender em nome de um usuário, consulte [obter acesso com contexto de usuário](api-create-app-user-context.md). Se você não tiver certeza sobre qual acesso você precisa, consulte [introdução](api-access.md).

O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs ajudarão você a automatizar fluxos de trabalho e inovar com base nos recursos do Microsoft 365 defender. O acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Em geral, você precisará executar as seguintes etapas para usar as APIs:
- Criar um aplicativo do Azure Active Directory (Azure AD).
- Obtenha um token de acesso usando este aplicativo.
- Use o token para acessar a API do Microsoft 365 defender.

Este artigo explica como criar um aplicativo do Azure AD, obter um token de acesso para o Microsoft 365 defender e validar o token.

## <a name="create-an-app"></a>Criar um aplicativo

1. Faça logon no [Azure](https://portal.azure.com) com um usuário que tenha a função de **administrador global** .

2. Navegue até registro de aplicativo **do Azure Active Directory**  >  **App registrations**  >  **novo registro**. 

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. No formulário de registro, escolha um nome para o aplicativo e, em seguida, selecione **registrar**.

4. Para permitir que seu aplicativo acesse o Microsoft 365 defender e atribuir permissões de ti, na página do aplicativo, selecione **permissões de API**  >  **Adicionar APIs de permissão**  >  **a minha organização usa** >, digite **Microsoft 365 defender** e selecione **Microsoft 365 defender**.

   > [!NOTE]
   > O Microsoft 365 defender não aparece na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.

   ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)

   - Selecionar **permissões de aplicativo** > escolha as permissões relevantes para o seu cenário, por exemplo, **Incident. Read. All** e, em seguida, selecione **adicionar permissões**.

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

    >[!NOTE]
    >Você precisa selecionar as permissões relevantes para o seu cenário, **' ler todos os incidentes '** é apenas um exemplo. Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você está interessado em chamar.

5. Selecione **conceder consentimento**.

     > [!NOTE]
     > Toda vez que você adicionar uma permissão, deverá selecionar **conceder consentimento** para que a nova permissão entre em vigor.

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

6. Para adicionar um segredo ao aplicativo, selecione **certificados & segredos** , adicione uma descrição ao segredo e, em seguida, selecione **Adicionar**.

    > [!NOTE]
    > Depois de selecionar **Adicionar** , selecione **copiar o valor de segredo gerado**. Você não poderá recuperar esse valor depois de sair.

    ![Imagem da chave de criação de aplicativo](../../media/webapp-create-key2.png)

7. Anote a ID do aplicativo e a ID do locatário. Na página do aplicativo, vá para **visão geral** e copie o seguinte.

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

8. **Somente para parceiros do Microsoft 365 defender**. [Siga as instruções aqui](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access). Defina seu aplicativo como multilocatário (disponível em todos os locatários após o consentimento). Isso é **necessário** para aplicativos de terceiros (por exemplo, se você criar um aplicativo destinado a ser executado no locatário de vários clientes). Isso **não é necessário** se você criar um serviço que deseja executar somente em seu locatário (por exemplo, se você criar um aplicativo para seu próprio uso que só interaja com seus próprios dados). Para definir seu aplicativo como multilocatários:

    - Vá para **autenticação** e adicione https://portal.azure.com como o **URI de redirecionamento**.

    - Na parte inferior da página, em **tipos de conta com suporte** , selecione as **contas em qualquer** consentimento de aplicativo de diretório organizacional para seu aplicativo de vários locatários.

    Você precisa que seu aplicativo seja aprovado em cada locatário onde você pretende usá-lo. Isso se deve ao fato de o aplicativo interagir com o Microsoft 365 defender em nome de seu cliente.

    Você (ou seu cliente se estiver escrevendo um aplicativo de terceiros) precisará selecionar o link de consentimento e aprovar seu aplicativo. O consentimento deve ser feito com um usuário que tenha privilégios administrativos no Active Directory.

    O link de consentimento é formado da seguinte maneira: 

    ```
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=00000000-0000-0000-0000-000000000000&response_type=code&sso_reload=true
    ```

    Em que 00000000-0000-0000-0000-000000000000 é substituído pela sua ID de aplicativo.


**Terminado!** Você registrou com êxito um aplicativo! Confira os exemplos abaixo para obter uma aquisição de token e validação.

## <a name="get-an-access-token"></a>Obter um token de acesso

Para obter mais detalhes sobre tokens do Azure AD, consulte o [tutorial do Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

### <a name="use-powershell"></a>Usar o Windows PowerShell!

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application key here

$resourceAppIdUri = 'https://api.security.microsoft.com'
$oAuthUri = "https://login.windows.net/$TenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$token = $authResponse.access_token
Out-File -FilePath "./Latest-token.txt" -InputObject $token
return $token
```

### <a name="use-c"></a>Use C#:

O código a seguir foi testado com o NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.

1. Criar um novo aplicativo de console.
1. Instale [o NuGet Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).
1. Adicione o seguinte:

    ```
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copie e cole o código a seguir em seu aplicativo (não se esqueça de atualizar as três variáveis: ```tenantId, appId, appSecret``` ):

    ```
    string tenantId = "00000000-0000-0000-0000-000000000000"; // Paste your own tenant ID here
    string appId = "11111111-1111-1111-1111-111111111111"; // Paste your own app ID here
    string appSecret = "22222222-2222-2222-2222-222222222222"; // Paste your own app secret here for a test, and then store it in a safe place! 

    const string authority = "https://login.windows.net";
    const string wdatpResourceId = "https://api.security.microsoft.com";

    AuthenticationContext auth = new AuthenticationContext($"{authority}/{tenantId}/");
    ClientCredential clientCredential = new ClientCredential(appId, appSecret);
    AuthenticationResult authenticationResult = auth.AcquireTokenAsync(wdatpResourceId, clientCredential).GetAwaiter().GetResult();
    string token = authenticationResult.AccessToken;
    ```


### <a name="use-python"></a>Usar Python 

```
import json
import urllib.request
import urllib.parse

tenantId = '00000000-0000-0000-0000-000000000000' # Paste your own tenant ID here
appId = '11111111-1111-1111-1111-111111111111' # Paste your own app ID here
appSecret = '22222222-2222-2222-2222-222222222222' # Paste your own app secret here

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.securitycenter.windows.com'

body = {
    'resource' : resourceAppIdUri,
    'client_id' : appId,
    'client_secret' : appSecret,
    'grant_type' : 'client_credentials'
}

data = urllib.parse.urlencode(body).encode("utf-8")

req = urllib.request.Request(url, data)
response = urllib.request.urlopen(req)
jsonResponse = json.loads(response.read())
aadToken = jsonResponse["access_token"]
```
### <a name="use-curl"></a>Rotação de uso

> [!NOTE]
> O procedimento a seguir supõe que a rotação do Windows já está instalada no seu computador.

1. Abra um prompt de comando e defina CLIENT_ID para sua ID de aplicativo do Azure.
1. Defina CLIENT_SECRET como seu segredo de aplicativo do Azure.
1. Defina TENANT_ID para a ID do locatário do Azure do cliente que deseja usar seu aplicativo para acessar o Microsoft 365 defender.
1. Execute o seguinte comando:

```
curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
```

Você receberá uma resposta no seguinte formato:

```
{"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
```

## <a name="validate-the-token"></a>Validar o token

Verifique se você recebeu o token correto:

1. Copie e cole o token obtido na etapa anterior em [JWT](https://jwt.ms) para decodificá-lo.
1. Validar que você obtém uma declaração "Roles" com as permissões desejadas
1. Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo ```Incidents.Read.All``` com ```Incidents.ReadWrite.All``` e ```AdvancedHunting.Read.All``` permissões:

![Imagem da validação do token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-microsoft-365-defender-api"></a>Usar o token para acessar a API do Microsoft 365 defender

1. Escolha a API que você deseja usar. Para obter mais informações, consulte [supported Microsoft 365 defender APIs](api-supported.md).

2. Defina o cabeçalho de autorização na solicitação HTTP que você envia para "portador {token}" (o portador é o esquema de autorização).

3. O tempo de expiração do token é uma hora. Você pode enviar mais de uma solicitação com o mesmo token.

Veja a seguir um exemplo de envio de uma solicitação para obter uma lista de incidentes **usando C#** : 

```
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
```

## <a name="related-topics"></a>Tópicos relacionados
- [Acessar as APIs do Microsoft 365 defender](api-access.md)
- [Acessar o Microsoft 365 defender com contexto de aplicativo](api-create-app-web.md)
- [Acessar o Microsoft 365 defender com contexto de usuário](api-create-app-user-context.md)
