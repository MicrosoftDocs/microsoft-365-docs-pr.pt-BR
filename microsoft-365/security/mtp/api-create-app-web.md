---
title: Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário
description: Saiba como criar um aplicativo para acessar o Microsoft 365 defender sem um usuário.
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
ms.openlocfilehash: de925fa52056a051592fe5024c0abd40b51ad57b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719351"
---
# <a name="create-an-app-to-access-microsoft-365-defender-without-a-user"></a>Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 defender sem um usuário definido — por exemplo, se você estiver criando um daemon ou serviço de plano de fundo.

Se você precisar de acesso programático ao Microsoft 365 defender em nome de um ou mais usuários, confira [criar um aplicativo para acessar as APIs do microsoft 365 defender em nome de um usuário](api-create-app-user-context.md) e [criar um aplicativo com acesso de parceiro às apis do Microsoft 365 defender](api-partner-access.md). Se você não tiver certeza sobre qual tipo de acesso precisa, consulte [introdução](api-access.md).

O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs ajudam a automatizar os fluxos de trabalho e a usar os recursos do Microsoft 365 defender. Este acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Em geral, você precisará executar as seguintes etapas para usar estas APIs:

- Criar um aplicativo do Azure Active Directory (Azure AD).
- Obtenha um token de acesso usando este aplicativo.
- Use o token para acessar a API do Microsoft 365 defender.

Este artigo explica como:

- Criar um aplicativo do Azure AD
- Obter um token de acesso para o Microsoft 365 defender
- Valide o token.

## <a name="create-an-app"></a>Criar um aplicativo

1. Entre no [Azure](https://portal.azure.com) como um usuário com a função de **administrador global** .

2. Navegue até registro de aplicativo **do Azure Active Directory**  >    >  **novo registro**.

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. No formulário, escolha um nome para o aplicativo e, em seguida, selecione **registrar**.

4. Na página do aplicativo, selecione **permissões de API**  >  **Adicionar**  >  **APIs de permissão minha organização usa** >, digite **proteção contra ameaças da Microsoft** e selecione **proteção contra ameaças da Microsoft**. Seu aplicativo agora pode acessar o Microsoft 365 defender.

   > [!TIP]
   > A *proteção contra ameaças da Microsoft* é um nome anterior para o Microsoft 365 defender e não aparecerá na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.

   ![Imagem da seleção de permissão de API](../../media/apis-in-my-org-tab.PNG)

5. Selecione **permissões do aplicativo**. Escolha as permissões relevantes para o seu cenário (por exemplo, **incidente. Read. All**) e selecione **adicionar permissões**.

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

    > [!NOTE]
    > Você precisa selecionar as permissões relevantes para o seu cenário. *Ler todos os incidentes* é apenas um exemplo. Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você deseja chamar.
    >
    > Por exemplo, para [executar consultas avançadas](api-advanced-hunting.md), selecione a permissão "executar consultas avançadas"; para [isolar um dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecione a permissão "isolar máquina".

6. Selecione **conceder consentimento do administrador**. Toda vez que você adicionar uma permissão, deverá selecionar **conceder consentimento de administrador** para que ela entre em vigor.

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

7. Para adicionar um segredo ao aplicativo, selecione **certificados & segredos**, adicione uma descrição ao segredo e, em seguida, selecione **Adicionar**.

    > [!TIP]
    > Depois de selecionar **Adicionar**, selecione **copiar o valor de segredo gerado**. Você não poderá recuperar o valor secreto após sair.

    ![Imagem da chave de criação de aplicativo](../../media/webapp-create-key2.png)

8. Registre a ID do aplicativo e sua ID de locatário em algum lugar seguro. Eles estão listados em **visão geral** na página do aplicativo.

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

9. **Somente para parceiros do microsoft 365 defender**: [siga estas instruções](https://docs.microsoft.com/microsoft-365/security/mtp/api-partner-access) para acesso de parceiros por meio das APIs do Microsoft 365 defender, defina seu aplicativo como multilocatário, para que ele possa estar disponível em todos os locatários quando você receber o consentimento do administrador. O acesso do parceiro é **necessário** para aplicativos de terceiros — por exemplo, se você criar um aplicativo destinado a ser executado em vários locatários de clientes. Ela **não será necessária** se você criar um serviço que você deseja executar somente em seu locatário, como um aplicativo para seu próprio uso que só interaja com seus próprios dados. Para definir seu aplicativo como multilocatário:

    - Vá para **autenticação** e adicione https://portal.azure.com como o **URI de redirecionamento**.

    - Na parte inferior da página, em **tipos de conta com suporte**, selecione as **contas em qualquer** consentimento de aplicativo de diretório organizacional para seu aplicativo de vários locatários.

    Como o seu aplicativo interage com o Microsoft 365 defender em nome dos seus usuários, ele precisa ser aprovado para cada locatário em que você pretende usá-lo.

    O administrador global do Active Directory para cada locatário precisa selecionar o link de consentimento e aprovar o aplicativo.

    O link de consentimento tem a seguinte estrutura:

    ```http
    https://login.microsoftonline.com/common/oauth2/authorize?prompt=consent&client_id=<00000000-0000-0000-0000-000000000000>&response_type=code&sso_reload=true
    ```

    Os dígitos `00000000-0000-0000-0000-000000000000` devem ser substituídos pela ID do aplicativo.  

**Terminado!** Você registrou com êxito um aplicativo! Confira os exemplos abaixo para obter uma aquisição de token e validação.

## <a name="get-an-access-token"></a>Obter um token de acesso

Para obter mais informações sobre tokens do Azure Active Directory, consulte o [tutorial do Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Embora os exemplos nesta seção incentivem que você cole valores secretos para fins de teste, você **nunca codifica segredos** em um aplicativo executado na produção. Uma terceira parte pode usar seu segredo para acessar recursos. Você pode ajudar a manter os segredos do seu aplicativo seguros usando o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Para obter um exemplo prático de como você pode proteger seu aplicativo, confira [gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

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
> O código a seguir foi testado com o NuGet Microsoft. IdentityModel. clients. ActiveDirectory 3.19.8.

1. Criar um novo aplicativo de console.

1. Instale [o NuGet Microsoft. IdentityModel. clients. ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

1. Adicione a seguinte linha:

    ```C#
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    ```

1. Copie e cole o código a seguir em seu aplicativo (não se esqueça de atualizar as três variáveis: `tenantId` , `clientId` , `appSecret` ):

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

### <a name="get-an-access-token-using-curl"></a>Obter um token de acesso usando ondulação

> [!NOTE]
> A ondulação é pré-instalada no Windows 10, versões 1803 e posteriores. Para outras versões do Windows, baixe e instale a ferramenta diretamente no [site oficial da ondulação](https://curl.haxx.se/windows/).

1. Abra um prompt de comando e defina CLIENT_ID para sua ID de aplicativo do Azure.

1. Defina CLIENT_SECRET como seu segredo de aplicativo do Azure.

1. Defina TENANT_ID para a ID do locatário do Azure do cliente que deseja usar seu aplicativo para acessar o Microsoft 365 defender.

1. Execute o seguinte comando:

   ```bash
   curl -i -X POST -H "Content-Type:application/x-www-form-urlencoded" -d "grant_type=client_credentials" -d "client_id=%CLIENT_ID%" -d "scope=https://securitycenter.onmicrosoft.com/windowsatpservice/.default" -d "client_secret=%CLIENT_SECRET%" "https://login.microsoftonline.com/%TENANT_ID%/oauth2/v2.0/token" -k
   ```

   Uma resposta bem-sucedida terá a seguinte aparência:

   ```bash
   {"token_type":"Bearer","expires_in":3599,"ext_expires_in":0,"access_token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsIn <truncated> aWReH7P0s0tjTBX8wGWqJUdDA"}
   ```

## <a name="validate-the-token"></a>Validar o token

1. Copie e cole o token no [site do validador de token de JSON Web, JWT,](https://jwt.ms) para decodificá-lo.

1. Certifique-se de que a declaração de *funções* dentro do token decodificado contenha as permissões desejadas.

   Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, `Incidents.Read.All` com `Incidents.ReadWrite.All` `AdvancedHunting.Read.All` as permissões e:

   ![Imagem da validação do token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usar o token para acessar a API do Microsoft 365 defender

1. Escolha a API que você deseja usar (incidentes ou busca avançada). Para obter mais informações, consulte [supported Microsoft 365 defender APIs](api-supported.md).

2. Na solicitação HTTP que você está prestes a enviar, defina o cabeçalho de autorização `"Bearer" <token>` , o *portador* como o esquema de autorização e o *token* que é o token validado.

3. O token expirará dentro de uma hora. Você pode enviar mais de uma solicitação durante esse tempo com o mesmo token.

O exemplo a seguir mostra como enviar uma solicitação para obter uma lista de incidentes **usando C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 defender](api-overview.md)
- [Acessar as APIs do Microsoft 365 defender](api-access.md)
- [Criar um aplicativo "Olá mundo"](api-hello-world.md)
- [Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário](api-create-app-user-context.md)
- [Criar um aplicativo com acesso de parceiro multilocatário às APIs do Microsoft 365 defender](api-partner-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Entender códigos de erro](api-error-codes.md)
- [Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Autorização OAuth 2,0 para entrada de usuário e acesso à API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
