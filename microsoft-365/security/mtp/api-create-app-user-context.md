---
title: Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário
description: Saiba como acessar as APIs do Microsoft 365 defender em nome de um usuário.
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
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719411"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Esta página descreve como criar um aplicativo para obter acesso programático ao Microsoft 365 defender em nome de um único usuário.

Se você precisar de acesso programático ao Microsoft 365 defender sem um usuário definido (por exemplo, se você estiver criando um aplicativo de plano de fundo ou daemon), confira [criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md). Se você precisar fornecer acesso para vários locatários — por exemplo, se estiver servindo uma grande organização ou um grupo de clientes, confira [criar um aplicativo com acesso para parceiros às APIs do Microsoft 365 defender](api-partner-access.md). Se você não tiver certeza sobre qual tipo de acesso precisa, consulte [introdução](api-access.md).

O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs ajudam a automatizar os fluxos de trabalho e a usar os recursos do Microsoft 365 defender. Este acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Em geral, você precisará executar as seguintes etapas para usar estas APIs:

- Criar um aplicativo do Azure Active Directory (Azure AD).
- Obtenha um token de acesso usando este aplicativo.
- Use o token para acessar a API do Microsoft 365 defender.

Este artigo explica como:

- Criar um aplicativo do Azure AD
- Obter um token de acesso para o Microsoft 365 defender
- Validar o token

> [!NOTE]
> Ao acessar a API do Microsoft 365 defender em nome de um usuário, você precisará das permissões de aplicativo e permissões de usuário corretas.

> [!TIP]
> Se você tem a permissão para executar uma ação no portal, você tem a permissão para executar a ação na API.

## <a name="create-an-app"></a>Criar um aplicativo

1. Entre no [Azure](https://portal.azure.com) como um usuário com a função de **administrador global** .

2. Navegue até registro de aplicativo **do Azure Active Directory**  >    >  **novo registro**.

   ![Imagem do Microsoft Azure e de navegação para o registro de aplicativo](../../media/atp-azure-new-app2.png)

3. No formulário, escolha um nome para o seu aplicativo e insira as seguintes informações para o URI de redirecionamento e, em seguida, selecione **registrar**.

   ![Imagem da janela de criação de aplicativo](../../media/nativeapp-create2.PNG)

   - **Tipo de aplicativo:** Cliente público
   - **URI de redirecionamento:**https://portal.azure.com

4. Na página do aplicativo, selecione **permissões de API**  >  **Adicionar**  >  **APIs de permissão minha organização usa** >, digite **proteção contra ameaças da Microsoft** e selecione **proteção contra ameaças da Microsoft**. Seu aplicativo agora pode acessar o Microsoft 365 defender.

   > [!TIP]
   > A *proteção contra ameaças da Microsoft* é um nome anterior para o Microsoft 365 defender e não aparecerá na lista original. Você precisa começar a escrever seu nome na caixa de texto para vê-lo aparece.

   ![Imagem da seleção de permissão de API](../../media/apis-in-my-org-tab.PNG)

   - Escolha **permissões delegadas**. Escolha as permissões relevantes para o seu cenário (por exemplo, **incidente. ler**) e selecione **adicionar permissões**.

   ![Imagem de acesso à API e seleção de API](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > Você precisa selecionar as permissões relevantes para o seu cenário. *Ler todos os incidentes* é apenas um exemplo. Para determinar qual permissão você precisa, consulte a seção **permissões** na API que você deseja chamar.
    >
    > Por exemplo, para [executar consultas avançadas](api-advanced-hunting.md), selecione a permissão "executar consultas avançadas"; para [isolar um dispositivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine), selecione a permissão "isolar máquina".

5. Selecione **conceder consentimento do administrador**. Toda vez que você adicionar uma permissão, deverá selecionar **conceder consentimento de administrador** para que ela entre em vigor.

   ![Imagem de conceder permissões](../../media/grant-consent-delegated.PNG)

6. Registre a ID do aplicativo e sua ID de locatário em algum lugar seguro. Eles estão listados em **visão geral** na página do aplicativo.

   ![Imagem da ID do aplicativo criado](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>Obter um token de acesso

Para obter mais informações sobre tokens do Azure Active Directory, consulte o [tutorial do Azure ad](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds).

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

1. Copie e cole o token em [JWT](https://jwt.ms) para decodificá-lo.
1. Certifique-se de que a declaração de *funções* dentro do token decodificado contenha as permissões desejadas.

Na imagem a seguir, você pode ver um token decodificado adquirido de um aplicativo, ```Incidents.Read.All``` com ```Incidents.ReadWrite.All``` ```AdvancedHunting.Read.All``` as permissões e:

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
- [Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md)
- [Criar um aplicativo com acesso de parceiro multilocatário às APIs do Microsoft 365 defender](api-partner-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
- [Entender códigos de erro](api-error-codes.md)
- [Autorização OAuth 2,0 para entrada de usuário e acesso à API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
