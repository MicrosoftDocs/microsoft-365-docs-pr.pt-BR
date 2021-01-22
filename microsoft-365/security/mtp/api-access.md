---
title: Acessar as APIs do Microsoft 365 Defender
description: Saiba como acessar as APIs do Microsoft 365 Defender
keywords: access, apis, contexto de aplicativo, contexto de usuário, aplicativo aad, token de acesso
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
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932149"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Acessar as APIs do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

O Microsoft 365 Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas. Essas APIs ajudam a automatizar fluxos de trabalho e usar totalmente os recursos do Microsoft 365 Defender.

Em geral, você precisará seguir as seguintes etapas para usar as APIs:

- Criar um aplicativo do Azure Active Directory
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API do Microsoft 365 Defender

> [!NOTE]
> O acesso à API requer autenticação OAuth2.0. Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Depois de realizar essas etapas, você estará pronto para acessar a API do Microsoft 365 Defender usando um contexto específico.

## <a name="application-context-recommended"></a>Contexto de aplicativo (recomendado)

Use esse contexto para aplicativos que são executados sem um usuário entrar, como serviços em segundo plano ou daemons.

1. Crie um aplicativo Web do Azure Active Directory.
2. Atribua as permissões desejadas ao aplicativo.
3. Crie uma chave para o aplicativo.
4. Obter um token de segurança usando o aplicativo e sua chave.
5. Use o token para acessar a API do Microsoft 365 Defender.

Para obter mais informações, **[consulte Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário.](api-create-app-web.md)**

## <a name="user-context"></a>Contexto do usuário

Use esse contexto para executar ações em nome de um único usuário.

1. Crie um aplicativo nativo do Azure Active Directory.
2. Atribua a permissão desejada ao aplicativo.
3. Obter um token de segurança usando as credenciais do usuário para o aplicativo.
4. Use o token para acessar a API do Microsoft 365 Defender.

Para obter mais informações, consulte Criar um aplicativo para acessar as APIs do **[Microsoft 365 Defender em nome de um usuário.](api-create-app-user-context.md)**

## <a name="partner-context"></a>Contexto de parceiro

Use esse contexto quando precisar fornecer um aplicativo para vários usuários em [vários locatários.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Crie um aplicativo multi-locatário do Azure Active Directory.
2. Atribua a permissão desejada ao aplicativo.
3. Obter [consentimento do administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para o aplicativo de cada locatário.
4. Obter um token de segurança usando credenciais de usuário com base na ID de locatário do cliente.
5. Use o token para acessar a API do Microsoft 365 Defender.

Para saber mais, confira **[Criar um aplicativo com acesso de parceiro às APIs do Microsoft 365 Defender.](api-partner-access.md)**

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [Autorização do OAuth 2.0 para entrada do usuário e acesso à API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Criar um aplicativo "Hello world" que acesse as APIs do Microsoft 365](api-hello-world.md)
