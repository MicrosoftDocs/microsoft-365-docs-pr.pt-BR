---
title: Hello World para a API REST do Microsoft 365 Defender
description: Saiba como criar um aplicativo e usar um token para acessar as APIs do Microsoft 365 Defender
keywords: app, token, access, aad, app, application registration, powershell, script, administrador global, permissão, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 66afa27d0fa7a092d3f9e9ed6c3b6abc6020cb8d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928373"
---
# <a name="hello-world-for-microsoft-365-defender-rest-api"></a>Hello World para a API REST do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="get-incidents-using-a-simple-powershell-script"></a>Obter incidentes usando um script simples do PowerShell

Deve levar de 5 a 10 minutos para concluir esse projeto. Essa estimativa de tempo inclui o registro do aplicativo e a aplicação do código do script de exemplo do PowerShell.

### <a name="register-an-app-in-azure-active-directory"></a>Registrar um aplicativo no Azure Active Directory

1. Entre no [Azure como um](https://portal.azure.com) usuário com a função de **administrador** global.

2. Navegue até registros de aplicativo **do Azure Active Directory** Novo  >    >  **registro.**

   ![Imagem do Microsoft Azure e navegação para o registro do aplicativo](../../media/atp-azure-new-app2.png)

3. In the registration form, choose a name for your application, then select **Register**. Selecionar um URI de redirecionamento é opcional. Você não precisará de um para concluir este exemplo.

4. Na página do seu aplicativo, selecione Permissões de API Adicionar **APIs** de permissão que minha organização usa >, digite Proteção contra Ameaças da Microsoft e selecione  >    >   Proteção contra Ameaças **da Microsoft.**  Seu aplicativo agora pode acessar o Microsoft 365 Defender.

   > [!TIP]
   > *A Proteção contra* Ameaças da Microsoft é um nome antigo do Microsoft 365 Defender e não aparecerá na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.
   ![Imagem da seleção de permissão da API](../../media/apis-in-my-org-tab.PNG)

   - Escolha **Application permissions**  >  **Incident.Read.All** e selecione **Add permissions**.

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

5. Selecione **Conceder consentimento de administrador.** Sempre que adicionar uma permissão, você deve selecionar Conceder **consentimento de administrador** para que ela entre em vigor.

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

6. Adicione um segredo ao aplicativo. Selecione **Certificados & segredos,** adicione uma descrição ao segredo e selecione **Adicionar.**

    > [!TIP]
    > Depois de selecionar **Adicionar,** selecione **copiar o valor secreto gerado.** Você não poderá recuperar o valor secreto depois de sair.

    ![Imagem de criar chave do aplicativo](../../media/webapp-create-key2.png)

7. Grave sua ID de aplicativo e sua ID de locatário em algum lugar seguro. Eles estão listados em **Visão Geral** na página do aplicativo.

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

### <a name="get-a-token-using-the-app-and-use-the-token-to-access-the-api"></a>Obter um token usando o aplicativo e usar o token para acessar a API

Para saber mais sobre tokens do Azure Active Directory, confira o [tutorial do Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

> [!IMPORTANT]
> Embora o exemplo neste aplicativo de demonstração incentive você a colar  seu valor secreto para fins de teste, você nunca deve codificar segredos em um aplicativo em execução em produção. Terceiros podem usar seu segredo para acessar recursos. Você pode ajudar a manter os segredos do seu aplicativo seguros usando o [Azure Key Vault.](https://docs.microsoft.com/azure/key-vault/general/about-keys-secrets-certificates) Para um exemplo prático de como você pode proteger seu aplicativo, confira Gerenciar segredos em seus aplicativos de servidor com o [Azure Key Vault.](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)

1. Copie o script abaixo e copie-o em seu editor de texto favorito. Salvar como **Get-Token.ps1**. Você também pode executar o código como está no ISE do PowerShell, mas deve salvá-lo, pois será necessário executar novamente quando usarmos o script de busca de incidentes na próxima seção.

    Esse script irá gerar um token e salvá-lo na pasta de trabalho sob o nome, *Latest-token.txt*.

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

1. Copie e colar o token recebido no [JWT](https://jwt.ms) para decodificá-lo.
1. *JWT* significa *JSON Web Token*. O token decodificado conterá vários itens ou declarações formatados em JSON. Certifique-se de *que a* declaração de funções dentro do token decodificado contém as permissões desejadas.

    Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, com ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` permissões:

    ![Imagem jwt.ms](../../media/api-jwt-ms.png)

### <a name="get-a-list-of-recent-incidents"></a>Obter uma lista de incidentes recentes

O script a seguir usará **Get-Token.ps1** para acessar a API. Em seguida, ele recupera uma lista de incidentes que foram atualizados pela última vez nas últimas 48 horas e salva a lista como um arquivo JSON.

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

Pronto! Você conseguiu:

- Criou e registrou um aplicativo.
- Permissão concedida para esse aplicativo ler alertas.
- Conectado à API.
- Usou um script do PowerShell para retornar incidentes atualizados nas últimas 48 horas.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
- [Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário](api-create-app-web.md)
- [Criar um aplicativo para acessar as APIs do Microsoft 365 Defender em nome de um usuário](api-create-app-user-context.md)
- [Criar um aplicativo com acesso de parceiro multi-locatário às APIs do Microsoft 365 Defender](api-partner-access.md)
- [Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Autorização do OAuth 2.0 para entrada do usuário e acesso à API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
