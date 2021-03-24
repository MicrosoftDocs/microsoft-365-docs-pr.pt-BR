---
title: Buscar alertas do locatário do cliente MSSP
description: Saiba como buscar alertas de um locatário do cliente
keywords: provedor de serviços de segurança gerenciado, mssp, configurar, integração
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: ee2a5e1815dd552753ac7f3dee30df11ac4332e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054487"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>Buscar alertas do locatário do cliente MSSP

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
>Essa ação é tomada pelo MSSP.


Há duas maneiras de buscar alertas:
- Usando o método SIEM
- Usando APIs

## <a name="fetch-alerts-into-your-siem"></a>Buscar alertas em seu SIEM

Para buscar alertas no sistema SIEM, você precisará seguir as seguintes etapas:

Etapa 1: Criar um aplicativo de terceiros

Etapa 2: obter tokens de acesso e atualização do locatário do cliente
 
Etapa 3: permitir seu aplicativo no Centro de Segurança do Microsoft Defender
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>Etapa 1: Criar um aplicativo no Azure Active Directory (Azure AD)
 
Você precisará criar um aplicativo e conceder permissões a ele para buscar alertas do locatário do Microsoft Defender para Ponto de Extremidade do seu cliente.

1. Entre no portal [do Azure AD.](https://aad.portal.azure.com/)

2. Selecione **Registros do Aplicativo do Azure Active Directory**  >  .
 
3. Clique **em Novo registro**.

4. Especifique os seguintes valores:

    - Nome: \<Tenant_name\> Conector do SIEM MSSP (substitua Tenant_name pelo nome de exibição do locatário)
 
    - Tipos de conta com suporte: Conta somente neste diretório organizacional 
    - URI de redirecionamento: selecione Web e digite `https://<domain_name>/SiemMsspConnector` (substitua <domain_name> pelo nome do locatário)

5. Clique em **Registrar**. O aplicativo é exibido na lista de aplicativos que você possui.

6. Selecione o aplicativo e clique em **Visão Geral**.

7. Copie o valor do campo ID do aplicativo **(cliente)** para um local seguro, você precisará disso na próxima etapa.

8. Selecione **Certificado & segredos** no novo painel de aplicativos.

9. Clique **em Novo segredo do cliente**.

    - Descrição: insira uma descrição da chave.
    - Expira: Selecionar **em 1 ano**

 
10. Clique **em Adicionar**, copie o valor do segredo do cliente para um local seguro, você precisará disso na próxima etapa.
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>Etapa 2: obter tokens de acesso e atualização do locatário do cliente
Esta seção orienta você sobre como usar um script do PowerShell para obter os tokens do locatário do cliente. Este script usa o aplicativo da etapa anterior para obter os tokens de acesso e atualização usando o Fluxo de Código de Autorização OAuth.

Depois de fornecer suas credenciais, você precisará conceder consentimento ao aplicativo para que o aplicativo seja provisionado no locatário do cliente.


1. Crie uma nova pasta e nomee-a: `MsspTokensAcquisition` .

2. Baixe o [módulo LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) e salve-o na `MsspTokensAcquisition` pasta.

    >[!NOTE]
    >Na linha 30, substitua `authorzationUrl` por `authorizationUrl` .

3. Crie um arquivo com o seguinte conteúdo e salve-o com o nome `MsspTokensAcquisition.ps1` na pasta:
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. Abra um prompt de comando do PowerShell com elevação na `MsspTokensAcquisition` pasta.

5. Execute o seguinte comando: `Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. Insira os seguintes comandos: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`
 
    - Substitua \<client_id\> pela **ID de aplicativo (cliente)** que você recebeu da etapa anterior.
    - Substitua \<app_key\> pelo Segredo do Cliente **criado** na etapa anterior.
    - Substitua \<customer_tenant_id\> pela ID de **Locatário do seu cliente.** 
 

7. Você será solicitado a fornecer suas credenciais e consentimento. Ignore o redirecionamento de página.

8. Na janela do PowerShell, você receberá um token de acesso e um token de atualização. Salve o token de atualização para configurar seu conector SIEM. 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a>Etapa 3: Permitir seu aplicativo no Centro de Segurança do Microsoft Defender
Você precisará permitir o aplicativo criado no Centro de Segurança do Microsoft Defender.
 
Você precisará ter a permissão **Gerenciar configurações do** sistema de portal para permitir o aplicativo. Caso contrário, você precisará solicitar que seu cliente permita o aplicativo para você.

1. Vá para `https://securitycenter.windows.com?tid=<customer_tenant_id>` (substitua \<customer_tenant_id\> pela ID de locatário do cliente.

2. Clique **em Configurações**  >  **SIEM**. 

3. Selecione a **guia MSSP.**

4. Insira a **ID do Aplicativo** na primeira etapa e a **ID do locatário.**

5. Clique **em Autorizar aplicativo**. 

 
Agora você pode baixar o arquivo de configuração relevante para seu SIEM e se conectar à API do Defender para Ponto de Extremidade. Para obter mais informações, consulte [Pull alerts to your SIEM tools](configure-siem.md).
 

- No arquivo de configuração arcSight/arquivo propriedades de autenticação Splunk, escreva a chave do aplicativo manualmente definindo o valor secreto.
- Em vez de adquirir um token de atualização no portal, use o script da etapa anterior para adquirir um token de atualização (ou adquiri-lo por outros meios).

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>Buscar alertas do locatário do cliente MSSP usando APIs
 
Para obter informações sobre como buscar alertas usando a API REST, consulte [Pull alerts using REST API](pull-alerts-using-rest-api.md).


## <a name="see-also"></a>Confira também
- [Conceder acesso MSSP ao portal](grant-mssp-access.md)
- [Acessar o portal do cliente MSSP](access-mssp-portal.md)
- [Configurar notificações de alerta](configure-mssp-notifications.md)
