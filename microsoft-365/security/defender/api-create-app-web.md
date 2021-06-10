---
title: Criar um aplicativo para acessar Microsoft 365 Defender sem um usuário
description: Saiba como criar um aplicativo para acessar Microsoft 365 Defender sem um usuário.
keywords: app, access, api, create
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
ms.openlocfilehash: 8ffa04492f42f7e1ee5f3fc7fadad963e6bb7fbe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054034"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Criar um aplicativo para acessar Microsoft 365 Defender sem um usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 Defender sem um usuário definido, por exemplo, se você estiver criando um daemon ou serviço em segundo plano.

Se você precisar de acesso programático ao Microsoft 365 Defender em nome de um ou mais usuários, consulte Create an app to access [Microsoft 365 Defender APIs](api-create-app-user-context.md) on behalf of a user and Create an app with [partner access to Microsoft 365 Defender APIs](api-partner-access.md). Se você não tiver certeza de que tipo de acesso precisa, consulte [Começar](api-access.md).

Microsoft 365 O Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas. Essas APIs ajudam você a automatizar fluxos de trabalho e usar Microsoft 365 recursos do Defender. Esse acesso à API requer autenticação OAuth2.0. Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Em geral, você precisará seguir as seguintes etapas para usar estas APIs:

- Crie um Azure Active Directory (Azure AD).
- Obter um token de acesso usando este aplicativo.
- Use o token para acessar Microsoft 365 API do Defender.

Este artigo explica como:

- Criar um aplicativo Microsoft Azure Active Directory
- Obter um token de acesso para Microsoft 365 Defender
- Valide o token.

## <a name="create-an-app"></a>Criar um aplicativo

1. Entre no [Azure como](https://portal.azure.com) um usuário com a função **Administrador Global.**

2. Navegue **até Azure Active Directory** registros do  >  **aplicativo** Novo  >  **registro**.

   ![Imagem de Microsoft Azure e navegação para registro de aplicativos](../../media/atp-azure-new-app2.png)

3. No formulário, escolha um nome para seu aplicativo e selecione **Registrar**.

4. Na página do aplicativo, selecione Permissões de **API** Adicionar  >    >  **APIs** de permissão que minha organização usa >, digite Proteção contra Ameaças da Microsoft e selecione Proteção contra Ameaças da Microsoft . Seu aplicativo agora pode acessar Microsoft 365 Defender.

   > [!TIP]
   > *Proteção contra Ameaças da Microsoft* é um nome antigo para Microsoft 365 Defender e não aparecerá na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.

   ![Imagem da seleção de permissão da API](../../media/apis-in-my-org-tab.PNG)

5. Selecione **Permissões de aplicativo**. Escolha as permissões relevantes para seu cenário (por exemplo, **Incident.Read.All**) e selecione **Adicionar permissões**.

   ![Imagem do acesso à API e seleção de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Você precisa selecionar as permissões relevantes para seu cenário. *Ler todos os incidentes* é apenas um exemplo. Para determinar de que permissão você precisa, consulte a seção **Permissões** na API que você deseja chamar.
    >
    > Por exemplo, para [executar consultas avançadas,](api-advanced-hunting.md)selecione a permissão "Executar consultas avançadas"; para [isolar um dispositivo,](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecione a permissão 'Isolar máquina'.

6. Selecione **Conceder consentimento de administrador**. Sempre que você adicionar uma permissão, você deve selecionar **Conceder consentimento de administrador** para que ela entre em vigor.

    ![Imagem de Permissões de Concessão](../../media/grant-consent.PNG)

7. Para adicionar um segredo ao aplicativo, selecione **Certificados & segredos**, adicione uma descrição ao segredo e selecione **Adicionar**.

    > [!TIP]
    > Depois de selecionar **Adicionar**, selecione **copiar o valor secreto gerado.** Você não poderá recuperar o valor secreto depois de sair.

    ![Imagem de criar chave de aplicativo](../../media/webapp-create-key2.png)

8. Grave sua ID de aplicativo e sua ID de locatário em algum lugar seguro. Eles estão listados em **Visão Geral** na página do aplicativo.

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

9. Somente **para** Microsoft 365 Parceiros do Defender [:](./api-partner-access.md) siga estas instruções para o acesso de parceiros por meio das APIs do Microsoft 365 Defender, de definir seu aplicativo como multi locatário, para que ele possa estar disponível em todos os locatários depois que você receber o consentimento do administrador. O acesso de parceiros **é necessário** para aplicativos de terceiros, por exemplo, se você criar um aplicativo destinado a ser executado em vários locatários de clientes. Não será **necessário se** você criar um serviço que você deseja executar apenas em seu locatário, como um aplicativo para seu próprio uso que interagirá apenas com seus próprios dados. Para definir seu aplicativo como multi locatário:

    - Vá para **Autenticação** e adicione https://portal.azure.com como o **URI de redirecionamento.**

    - Na parte inferior da página, em Tipos  **de** conta com suporte, selecione Contas em qualquer consentimento de aplicativo de diretório organizacional para seu aplicativo multi-locatário.

    Como seu aplicativo interage com o Microsoft 365 Defender em nome de seus usuários, ele precisa ser aprovado para cada locatário no qual você pretende usá-lo.

    O administrador global do Active Directory para cada locatário precisa selecionar o link de consentimento e aprovar seu aplicativo.

    O link de consentimento tem a seguinte estrutura:

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    Os dígitos `00000000-0000-0000-0000-000000000000` devem ser substituídos pela ID do aplicativo.  

**Pronto!** Você registrou com êxito um aplicativo! Consulte exemplos abaixo para aquisição e validação de token.

## <a name="get-an-access-token"></a>Obter um token de acesso

Para obter mais informações sobre Azure Active Directory tokens, consulte o [tutorial do Azure AD](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Embora os exemplos nesta seção incentivem você a colar valores  secretos para fins de teste, você nunca deve codificar segredos em um aplicativo em execução em produção. Um terceiro pode usar seu segredo para acessar recursos. Você pode ajudar a manter os segredos do seu aplicativo seguros usando o [Azure Key Vault.](/azure/key-vault/general/about-keys-secrets-certificates) Para ver um exemplo prático de como proteger seu aplicativo, consulte Gerenciar segredos em seus aplicativos de servidor com o [Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/).

### <a name="get-an-access-token-using-powershell"></a>Obter um token de acesso usando o PowerShell

```PowerShell
# This code gets the application context token and saves it to a file named "Latest-token.txt" under the current directory.

$tenantId = '' # Paste your directory (tenant) ID here
$clientId = '' # Paste your application (client) ID here
$appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

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

### <a name="get-an-access-token-using-c"></a>Obter um token de acesso usando C\#

> [!NOTE]
> O código a seguir foi testado com Nuget Microsoft.IdentityModel.Clients.ActiveDirectory 3.19.8.

1. Crie um novo aplicativo de console.

1. Instale NuGet [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

1. Adicione a seguinte linha:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copie e colar o seguinte código em seu aplicativo (não se esqueça de atualizar as três variáveis: `tenantId` , `clientId` , `appSecret` ):

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

### <a name="get-an-access-token-using-python"></a>Obter um token de acesso usando Python

```Python
import json
import urllib.request
import urllib.parse

tenantId = '' # Paste your directory (tenant) ID here
clientId = '' # Paste your application (client) ID here
appSecret = '' # Paste your own app secret here to test, then store it in a safe place, such as the Azure Key Vault!

url = "https://login.windows.net/%s/oauth2/token" % (tenantId)

resourceAppIdUri = 'https://api.security.microsoft.com'

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

### <a name="get-an-access-token-using-curl"></a>Obter um token de acesso usando o cache

> [!NOTE]
> O cache é pré-instalado no Windows 10, versões 1803 e posteriores. Para outras versões do Windows, baixe e instale a ferramenta diretamente do [site de cache oficial.](https://curl.haxx.se/windows/)

1. Abra um prompt de comando e de CLIENT_ID para sua ID de aplicativo do Azure.

1. De CLIENT_SECRET seu segredo de aplicativo do Azure.

1. De TENANT_ID a ID do locatário do Azure do cliente que deseja usar seu aplicativo para acessar o Microsoft 365 Defender.

1. Execute o seguinte comando:

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://api.security.microsoft.com/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   Uma resposta bem-sucedida terá esta aparência:

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>Validar o token

1. Copie e colar o token no site do validador de [token web JSON, JWT,](https://jwt.ms) para decodificá-lo.

1. Certifique-se de que *as funções* de declaração dentro do token decodificado contenham as permissões desejadas.

   Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, com `Incidents.Read.All` `Incidents.ReadWrite.All` , e `AdvancedHunting.Read.All` permissões:

   ![Imagem da validação de token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usar o token para acessar a API Microsoft 365 Defender

1. Escolha a API que você deseja usar (incidentes ou busca avançada). Para obter mais informações, consulte [Supported Microsoft 365 Defender APIs](api-supported.md).

2. Na solicitação http que você está prestes a enviar, de definir o cabeçalho de autorização como , o portador é o esquema de autorização e o token sendo `"Bearer" <token>` seu token  validado. 

3. O token expirará dentro de uma hora. Você pode enviar mais de uma solicitação durante esse tempo com o mesmo token.

O exemplo a seguir mostra como enviar uma solicitação para obter uma lista de incidentes **usando C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft 365 Visão geral das APIs do Defender](api-overview.md)
- [Acessar as APIs Microsoft 365 Defender](api-access.md)
- [Criar um aplicativo 'Hello world'](api-hello-world.md)
- [Criar um aplicativo para acessar Microsoft 365 APIs do Defender em nome de um usuário](api-create-app-user-context.md)
- [Criar um aplicativo com acesso a parceiros de vários locatários para Microsoft 365 APIs do Defender](api-partner-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Compreender códigos de erro](api-error-codes.md)
- [Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Autorização OAuth 2.0 para entrada do usuário e acesso à API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)