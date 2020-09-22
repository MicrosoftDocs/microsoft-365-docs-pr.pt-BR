---
title: Hello World para a API REST de proteção contra ameaças da Microsoft
description: Saiba como criar um aplicativo e usar um token para acessar as APIs de proteção contra ameaças da Microsoft
keywords: aplicativo, token, Access, AAD, aplicativo, registro de aplicativo, PowerShell, script, administrador global, permissão
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
ms.openlocfilehash: cdf3f6a0c007763d2772233b1a299d59c931b2e5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201322"
---
# <a name="hello-world-for-microsoft-threat-protection-rest-api"></a>Hello World para a API REST de proteção contra ameaças da Microsoft 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


## <a name="get-incidents-using-a-simple-powershell-script"></a>Obter incidentes usando um script simples do PowerShell

### <a name="how-long-it-takes-to-go-through-this-example"></a>Quanto tempo leva para passar por este exemplo?
Isso leva apenas 5 minutos para ser feito em duas etapas:
- Registro de aplicativo
- Exemplos de uso: requer apenas copiar/colar um breve script do PowerShell

### <a name="do-i-need-a-permission-to-connect"></a>Preciso de uma permissão para se conectar?
Para o estágio de registro de aplicativo, você deve ter uma função de **administrador global** em seu locatário do Azure Active Directory (Azure AD).

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Etapa 1: criar um aplicativo no Azure Active Directory

1. Faça logon no [Azure](https://portal.azure.com) com o usuário de **administrador global** .

2. Navegue até registro de aplicativo **do Azure Active Directory**  >  **App registrations**  >  **novo registro**. 

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. No formulário de registro, escolha um nome para o aplicativo e, em seguida, selecione **registrar**.

4. Permitir que seu aplicativo acesse o Microsoft defender ATP e atribuí-lo a permissão de **todos os incidentes** :

   - Na página do aplicativo, selecione **permissões de API**  >  **Adicionar APIs de permissão**  >  **minha organização usa** > digite **proteção contra ameaças da Microsoft** e selecione na **proteção contra ameaças da Microsoft**.

   >[!NOTE]
   >A proteção contra ameaças da Microsoft não aparece na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.

   ![Imagem de acesso à API e seleção de API](../../media/apis-in-my-org-tab.PNG)

   - Escolha **Application Permissions**  >  **Incident. Read. All** > selecionar em **adicionar permissões**

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions.PNG)

   >[!IMPORTANT]
   >Você precisa selecionar as permissões relevantes. 

     Por exemplo,

     - Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você está interessado em chamar.

5. Selecionar **conceder consentimento do administrador**

    - >[!NOTE]
      > Toda vez que você adicionar permissão, deverá selecionar o **consentimento conceder** para que a nova permissão entre em vigor.

    ![Imagem de conceder permissões](../../media/grant-consent.PNG)

6. Adicione um segredo ao aplicativo.

    - Selecione **certificados & segredos**, adicione descrição ao segredo e selecione **Adicionar**.

    >[!IMPORTANT]
    > Depois de selecionar **Adicionar**, **Copie o valor de segredo gerado**. Você não poderá recuperar após sair!

    ![Imagem da chave de criação de aplicativo](../../media/webapp-create-key2.png)

7. Anote a ID do aplicativo e a ID do locatário:

   - Na página do aplicativo, vá para **visão geral** e copie o seguinte:

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)


Terminado! Você registrou com êxito um aplicativo.

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Etapa 2: obter um token usando o aplicativo e usar esse token para acessar a API.

-   Copie o script abaixo para o PowerShell ISE ou para um editor de texto e salve-o como "**Get-Token.ps1**"
-   Executar esse script gerará um token e o salvará na pasta de trabalho com o nome "**Latest-token.txt**".

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

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

-   Verificação de sanidade:<br>
Execute o script.<br>
No navegador, vá para: https://jwt.ms/ <br>
Copie o token (o conteúdo do arquivo de Latest-token.txt).<br>
Colar na caixa superior.<br>
Procure a seção "funções". Encontre a ```Incidents.Read.All``` função.<br>
O exemplo a seguir é de um aplicativo que ```Incidents.Read.All``` tem ```Incidents.ReadWrite.All``` e ```AdvancedHunting.Read.All``` permissões.

![Jwt.ms de imagem](../../media/api-jwt-ms.png)

### <a name="lets-get-the-incidents"></a>Permite obter os incidentes!

-   O script abaixo usará **Get-Token.ps1** para acessar a API e obterá os incidentes atualizados pela última vez nas últimas 48 horas.
-   Salvar este script na mesma pasta em que você salvou o script anterior **Get-Token.ps1**. 
-   O script um arquivo JSON com os dados na mesma pasta dos scripts.

```
# Returns Incidents last updated in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Incidents from the last 48 hours. Make sure you have incidents in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")

# The URL contains the type of query and the time filter we created above
$url = "https://api.security.microsoft.com/api/incidents?$filter=lastUpdateTime+ge+$dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    'Accept' = 'application/json'
    'Authorization' = "Bearer $token"
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the incidents from the results. 
$incidents =  ($response | ConvertFrom-Json).value | ConvertTo-Json -Depth 99

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json
$outputJsonPath = "./Latest Incidents $dateTimeForFileName.json"     

Out-File -FilePath $outputJsonPath -InputObject $incidents 
```

Você terminou! Você acabou de fazer o êxito:
-   Criado e registrado e aplicativo
-   Permissão concedida para que o aplicativo Leia os alertas
-   Conexão da API
-   Usou um script do PowerShell para retornar incidentes criados nas últimas 48 horas



## <a name="related-topic"></a>Tópico relacionado
- [Acessar as APIs de proteção contra ameaças da Microsoft](api-access.md)
- [Acesso à proteção contra ameaças da Microsoft com contexto de aplicativo](api-create-app-web.md)
- [Acesso à proteção contra ameaças da Microsoft com contexto de usuário](api-create-app-user-context.md)
