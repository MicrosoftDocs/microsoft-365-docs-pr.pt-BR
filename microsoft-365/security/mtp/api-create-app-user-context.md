---
title: Criar um aplicativo para acessar as APIs do Microsoft 365 Defender em nome de um usuário
description: Saiba como acessar as APIs do Microsoft 365 Defender em nome de um usuário.
keywords: access, em nome do usuário, api, aplicativo, usuário, token de acesso, token,
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
ms.openlocfilehash: d443334a00b5247525a2cdba98a11cfe0f515193
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928448"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Criar um aplicativo para acessar as APIs do Microsoft 365 Defender em nome de um usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 Defender em nome de um único usuário.

Se você precisar de acesso programático ao Microsoft 365 Defender sem um usuário definido (por exemplo, se você estiver escrevendo um aplicativo ou daemon em segundo plano), consulte Criar um aplicativo para acessar o [Microsoft 365 Defender](api-create-app-web.md)sem um usuário. Se você precisar fornecer acesso a vários locatários — por exemplo, se você estiver servindo uma grande organização ou um grupo de clientes — consulte Criar um aplicativo com acesso de parceiro às APIs do [Microsoft 365 Defender.](api-partner-access.md) Se você não tiver certeza de que tipo de acesso precisa, confira [Começar.](api-access.md)

O Microsoft 365 Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas. Essas APIs ajudam a automatizar fluxos de trabalho e usar os recursos do Microsoft 365 Defender. Esse acesso à API requer autenticação OAuth2.0. Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Em geral, você precisará seguir as seguintes etapas para usar essas APIs:

- Crie um aplicativo do Azure Active Directory (Azure AD).
- Obter um token de acesso usando este aplicativo.
- Use o token para acessar a API do Microsoft 365 Defender.

Este artigo explica como:

- Criar um aplicativo do Azure AD
- Obter um token de acesso para o Microsoft 365 Defender
- Validar o token

> [!NOTE]
> Ao acessar a API do Microsoft 365 Defender em nome de um usuário, você precisará das permissões de aplicativo e permissões de usuário corretas.

> [!TIP]
> Se você tiver permissão para executar uma ação no portal, terá permissão para executar a ação na API.

## <a name="create-an-app"></a>Criar um aplicativo

1. Entre no [Azure como um](https://portal.azure.com) usuário com a função de Administrador **Global.**

2. Navegue até registros de aplicativo **do Azure Active Directory** Novo  >    >  **registro.**

   ![Imagem do Microsoft Azure e navegação para o registro do aplicativo](../../media/atp-azure-new-app2.png)

3. In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.

   ![Imagem da janela Criar aplicativo](../../media/nativeapp-create2.PNG)

   - **Tipo de aplicativo:** Cliente público
   - **URI de redirecionamento:**https://portal.azure.com

4. Na página do seu aplicativo, selecione Permissões de API Adicionar **APIs** de permissão que minha organização usa >, digite Proteção contra Ameaças da Microsoft e selecione  >    >   Proteção contra Ameaças **da Microsoft.**  Seu aplicativo agora pode acessar o Microsoft 365 Defender.

   > [!TIP]
   > *A Proteção contra* Ameaças da Microsoft é um nome antigo do Microsoft 365 Defender e não aparecerá na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparecer.

   ![Imagem da seleção de permissão da API](../../media/apis-in-my-org-tab.PNG)

   - Escolha **permissões delegadas**. Escolha as permissões relevantes para seu cenário (por **exemplo, Incident.Read**) e, em seguida, **selecione Adicionar permissões**.

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Você precisa selecionar as permissões relevantes para seu cenário. *Ler todos os incidentes* é apenas um exemplo. Para determinar de que permissão você precisa, consulte a seção **Permissões** na API que você deseja chamar.
    >
    > Por exemplo, para [executar consultas avançadas,](api-advanced-hunting.md)selecione a permissão "Executar consultas avançadas"; para [isolar um dispositivo,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)selecione a permissão "Isolar máquina".

5. Selecione **Conceder consentimento de administrador.** Sempre que adicionar uma permissão, você deve selecionar Conceder **consentimento de administrador** para que ela entre em vigor.

   ![Imagem de conceder permissões](../../media/grant-consent-delegated.PNG)

6. Grave sua ID de aplicativo e sua ID de locatário em algum lugar seguro. Eles estão listados em **Visão Geral** na página do aplicativo.

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Obter um token de acesso

Para saber mais sobre tokens do Azure Active Directory, confira o [tutorial do Azure AD.](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)

### <a name="get-an-access-token-using-powershell"></a>Obter um token de acesso usando o PowerShell

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>Validar o token

1. Copie e colar o token no [JWT](https://jwt.ms) para decodificá-lo.
1. Certifique-se de *que a* declaração de funções dentro do token decodificado contém as permissões desejadas.

Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, com ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` , e ```AdvancedHunting.Read.All``` permissões:

![Imagem de validação de token](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>Usar o token para acessar a API do Microsoft 365 Defender

1. Escolha a API que você deseja usar (incidentes ou busca avançada). Para saber mais, confira [AS APIs do Microsoft 365 Defender com suporte.](api-supported.md)
2. Na solicitação http que você está prestes a enviar, de definir o cabeçalho de autorização como , portador sendo o esquema de autorização e token sendo `"Bearer" <token>` seu token  validado. 
3. O token expirará dentro de uma hora. Você pode enviar mais de uma solicitação durante esse período com o mesmo token.

O exemplo a seguir mostra como enviar uma solicitação para obter uma lista de incidentes **usando C#**.

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
- [Criar um aplicativo "Hello world"](api-hello-world.md)
- [Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário](api-create-app-web.md)
- [Criar um aplicativo com acesso de parceiro multi-locatário às APIs do Microsoft 365 Defender](api-partner-access.md)
- [Saiba mais sobre limites e licenciamento da API](api-terms.md)
- [Noções sobre códigos de erro](api-error-codes.md)
- [Autorização do OAuth 2.0 para entrada do usuário e acesso à API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
