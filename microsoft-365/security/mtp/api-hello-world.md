---
title: Hello World para a API REST do Microsoft 365 defender
description: Saiba como criar um aplicativo e usar um token para acessar as APIs do Microsoft 365 defender
keywords: aplicativo, token, Access, AAD, aplicativo, registro de aplicativo, PowerShell, script, administrador global, permissão, Microsoft 365 defender
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
ms.openlocfilehash: b36a6acca5880a455a66b03b5355cdf1fb85b29b
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719305"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World para a API REST do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Obter incidentes usando um script simples do PowerShell

Deve levar de 5 a 10 minutos para concluir este projeto. Este tempo estimado inclui registrar o aplicativo e aplicar o código do script de exemplo do PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Registrar um aplicativo no Azure Active Directory

1. Entre no [Azure](https://portal.azure.com) como um usuário com a função de **administrador global** .

2. Navegue até registro de aplicativo **do Azure Active Directory**  >    >  **novo registro**.

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. No formulário de registro, escolha um nome para o aplicativo e, em seguida, selecione **registrar**. Selecionar um URI de redirecionamento é opcional. Você não precisa de um para concluir esse exemplo.

4. Na página do aplicativo, selecione **permissões de API**  >  **Adicionar**  >  **APIs de permissão minha organização usa** >, digite **proteção contra ameaças da Microsoft** e selecione **proteção contra ameaças da Microsoft**. Seu aplicativo agora pode acessar o Microsoft 365 defender.

   > [!TIP]
   > A *proteção contra ameaças da Microsoft* é um nome anterior para o Microsoft 365 defender e não aparecerá na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.
   ![Imagem da seleção de permissão de API](../../media/apis-in-my-org-tab.PNG)

   - Escolha **Application Permissions**  >  **Incident. Read. All** e selecione **adicionar permissões**.

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

5. Selecione **conceder consentimento do administrador**. Toda vez que você adicionar uma permissão, deverá selecionar **conceder consentimento de administrador** para que ela entre em vigor.

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

6. Adicione um segredo ao aplicativo. Selecione **certificados & segredos**, adicione uma descrição ao segredo e, em seguida, selecione **Adicionar**.

    > [!TIP]
    > Depois de selecionar **Adicionar**, selecione **copiar o valor de segredo gerado**. Você não poderá recuperar o valor secreto após sair.

    ![Imagem da chave de criação de aplicativo](../../media/webapp-create-key2.png)

7. Registre a ID do aplicativo e sua ID de locatário em algum lugar seguro. Eles estão listados em **visão geral** na página do aplicativo.

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Obter um token usando o aplicativo e usar o token para acessar a API

Para obter mais informações sobre tokens do Azure Active Directory, consulte o [tutorial do Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

> [!IMPORTANT]
> Embora o exemplo neste aplicativo de demonstração incentive que você cole o valor secreto para fins de teste, você **nunca codifica segredos** em um aplicativo executado na produção. Uma terceira parte pode usar seu segredo para acessar recursos. Você pode ajudar a manter os segredos do seu aplicativo seguros usando o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates). Para obter um exemplo prático de como você pode proteger seu aplicativo, confira [gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/).

1. Copie o script abaixo e cole-o no seu editor de texto favorito. Salvar como **Get-Token.ps1**. Você também pode executar o código como está no PowerShell ISE, mas deve salvá-lo, pois será necessário executá-lo novamente quando usarmos o script de busca de incidente na próxima seção.

    Este script irá gerar um token e salvá-lo na pasta de trabalho com o nome *Latest-token.txt*.

    ```PowerShell
    # This script gets the app context token and saves it to a file named "Latest-token.txt" under the current directory.
    # Paste in your tenant ID, client ID and app secret (App key).

    $tenantId = '' # Paste your directory (tenant) ID here
    $clientId = '' # Paste your application (client) ID here
    $appSecret = '' # # Paste your own app secret here to test, then store it in a safe place!

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

#### <a name="validate-the-token"></a>Validar o token

1. Copie e cole o token recebido em [JWT](https://jwt.ms) para decodificá-lo.
1. *JWT* significa *token Web JSON*. O token decodificado conterá um número de itens ou declarações formatados por JSON. Certifique-se de que a declaração de *funções* dentro do token decodificado contenha as permissões desejadas.

    Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, ```Incidents.Read.All``` com ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` as permissões e:

    ![Jwt.ms de imagem](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Obter uma lista de incidentes recentes

O script abaixo usará **Get-Token.ps1** para acessar a API. Em seguida, ele recupera uma lista de incidentes que foram atualizados pela última vez nas últimas 48 horas e salva a lista como um arquivo JSON.

> [!IMPORTANT]
> Salve esse script na mesma pasta que você salvou **Get-Token.ps1**.

```PowerShell
# This script returns incidents last updated within the past 48 hours.

$token = ./Get-Token.ps1

# Get incidents from the past 48 hours.
# The script may appear to fail if you don't have any incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# This URL contains the type of query and the time filter we created above.
# Note that `$filter` does not refer to a local variable in our script --
# it's actually an OData operator and part of the API's syntax.
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the webrequest headers
$headers = @{
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the request and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results.
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get a string containing the execution time. We concatenate that string to the name 
# of the output file to avoid overwriting the file on consecutive runs of the script.
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"

Out-File -FilePath $outputJsonPath -InputObject $incidents
```

Você terminou! Você teve êxito:

- Criar e registrar um aplicativo.
- Concedida permissão para que o aplicativo Leia os alertas.
- Conectado à API.
- Usou um script do PowerShell para retornar incidentes atualizados nas últimas 48 horas.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 defender](api-overview.md)
- [Acessar as APIs do Microsoft 365 defender](api-access.md)
- [Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md)
- [Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário](api-create-app-user-context.md)
- [Criar um aplicativo com acesso de parceiro multilocatário às APIs do Microsoft 365 defender](api-partner-access.md)
- [Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Autorização OAuth 2,0 para entrada de usuário e acesso à API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
