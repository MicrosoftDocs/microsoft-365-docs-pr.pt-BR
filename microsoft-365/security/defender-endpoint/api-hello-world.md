---
title: Hello World para a API do Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Crie uma chamada de API de estilo "Hello world" para a API do Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, busca avançada, consulta, microsoft defender atp, microsoft defender para ponto de extremidade
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 08188acf1209ea2247a0eb09d722ce74c4540254
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939607"
---
# <a name="microsoft-defender-for-endpoint-api---hello-world"></a>API do Microsoft Defender para Ponto de Extremidade - Hello World 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** 
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)


- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="get-alerts-using-a-simple-powershell-script"></a>Obter alertas usando um script simples do PowerShell

### <a name="how-long-it-takes-to-go-through-this-example"></a>Quanto tempo leva para passar por este exemplo?
Leva apenas 5 minutos para ser feito em duas etapas:
- Registro de aplicativo
- Exemplos de uso: só requer cópia/colar de um script curto do PowerShell

### <a name="do-i-need-a-permission-to-connect"></a>Preciso de uma permissão para me conectar?
Para o estágio de registro do aplicativo, você deve ter uma função de administrador **global** no locatário do Azure Active Directory (Azure AD).

### <a name="step-1---create-an-app-in-azure-active-directory"></a>Etapa 1 - Criar um aplicativo no Azure Active Directory

1. Faça logoff no [Azure](https://portal.azure.com) com seu **usuário de administrador** global.

2. Navegue **até registros do Aplicativo do Azure Active Directory** Novo  >    >  **registro**. 

   ![Imagem do Microsoft Azure e navegação para registro de aplicativo](images/atp-azure-new-app2.png)

3. No formulário de registro, escolha um nome para seu aplicativo e clique em **Registrar**.

4. Permitir que seu aplicativo acesse o Defender para Ponto de Extremidade e atribua a permissão **"Ler todos os alertas":**

   - Em sua página de aplicativo, clique em Permissões de **API** Adicionar APIs de permissão que minha organização usa > tipo  >    >   **WindowsDefenderATP** e clique em **WindowsDefenderATP**.

   - **Observação**: WindowsDefenderATP não aparece na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.

   ![Imagem de acesso à API e seleção de API1](images/add-permission.png)

   - Escolha **Permissões de aplicativo**  >  **Alert.Read.All** > Clique em Adicionar **permissões**

   ![Imagem de acesso à API e seleção de API2](images/application-permissions.png)

   **Observação importante:** você precisa selecionar as permissões relevantes. 'Ler Todos os Alertas' é apenas um exemplo!

     Por exemplo,

     - Para [executar consultas avançadas,](run-advanced-query-api.md)selecione 'Executar consultas avançadas' permissão
     - Para [isolar um computador,](isolate-machine.md)selecione a permissão 'Isolar máquina'
     - Para determinar de que permissão você precisa, consulte a seção **Permissões** na API que você está interessado em chamar.

5. Clique **em Conceder consentimento**

    - **Observação**: sempre que você adicionar permissão, clique em **Conceder consentimento** para que a nova permissão entre em vigor.

    ![Imagem de Permissões de Concessão](images/grant-consent.png)

6. Adicione um segredo ao aplicativo.

    - Clique **em Certificados & segredos,** adicione a descrição ao segredo e clique em **Adicionar**.

    **Importante**: depois de clicar em Adicionar, **copie o valor secreto gerado.** Você não poderá recuperar depois de sair!

    ![Imagem de criar chave de aplicativo](images/webapp-create-key2.png)

7. Anote sua ID de aplicativo e sua ID de locatário:

   - Na página do aplicativo, vá para **Visão Geral** e copie o seguinte:

   ![Imagem da ID do aplicativo criado](images/app-and-tenant-ids.png)


Pronto! Você registrou com êxito um aplicativo!

### <a name="step-2---get-a-token-using-the-app-and-use-this-token-to-access-the-api"></a>Etapa 2 : Obter um token usando o Aplicativo e usar esse token para acessar a API.

-   Copie o script abaixo para o ISE do PowerShell ou para um editor de texto e salve-o como "**Get-Token.ps1**"
-   Executar esse script gerará um token e o salvará na pasta de trabalho com o nome "**Latest-token.txt**".

```
# That code gets the App Context Token and save it to a file named "Latest-token.txt" under the current directory
# Paste below your Tenant ID, App ID and App Secret (App key).

$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://api.securitycenter.microsoft.com'
$oAuthUri = "https://login.microsoftonline.com/$TenantId/oauth2/token"
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
Copie o token (o conteúdo do arquivo Latest-token.txt arquivo).<br>
Colar na caixa superior.<br>
Procure a seção "funções". Encontre a função Alert.Read.All.

![Imagem jwt.ms](images/api-jwt-ms.png)

### <a name="lets-get-the-alerts"></a>Vamos obter os Alertas!

-   O script a seguir usará **Get-Token.ps1** acessar a API e receberá os alertas das últimas 48 horas.
-   Salve esse script na mesma pasta que você salvou o script **anteriorGet-Token.ps1**. 
-   O script cria dois arquivos (json e csv) com os dados na mesma pasta que os scripts.

```
# Returns Alerts created in the past 48 hours.

$token = ./Get-Token.ps1       #run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-Token.ps1

# Get Alert from the last 48 hours. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-48).ToString("o")       

# The URL contains the type of query and the time filter we create above
# Read more about other query options and filters at   Https://TBD- add the documentation link
$url = "https://api.securitycenter.microsoft.com/api/alerts?`$filter=alertCreationTime ge $dateTime"

# Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

# Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop

# Extract the alerts from the results. 
$alerts =  ($response | ConvertFrom-Json).value | ConvertTo-Json

# Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

# Save the result as json and as csv
$outputJsonPath = "./Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "./Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
($alerts | ConvertFrom-Json) | Export-CSV $outputCsvPath -NoTypeInformation 
```

Você terminou! Você acabou de fazer isso com êxito:
-   Criado e registrado e aplicativo
-   Permissão concedida para que o aplicativo leia alertas
-   Conectado a API
-   Usou um script do PowerShell para retornar alertas criados nas últimas 48 horas



## <a name="related-topic"></a>Tópicos relacionados
- [APIs do Microsoft Defender para Ponto de Extremidade](exposed-apis-list.md)
- [Acessar o Microsoft Defender para Ponto de Extremidade com contexto de aplicativo](exposed-apis-create-app-webapp.md)
- [Acessar o Microsoft Defender para Ponto de Extremidade com contexto de usuário](exposed-apis-create-app-nativeapp.md)
