---
title: Acessar as APIs Microsoft 365 Defender
description: Saiba como acessar as APIs Microsoft 365 Defender
keywords: access, apis, application context, user context, aad application, access token
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
ms.openlocfilehash: 1fbba132e664f4773496eac7123a0a408db5b3bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053514"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Acessar as APIs Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Microsoft 365 O Defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas. Essas APIs ajudam você a automatizar fluxos de trabalho e usar Microsoft 365 recursos do Defender.

Em geral, você precisará seguir as seguintes etapas para usar as APIs:

- Criar um Azure Active Directory aplicativo
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API Microsoft 365 Defender

> [!NOTE]
> O acesso à API requer autenticação OAuth2.0. Para obter mais informações, consulte [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Depois de realizar essas etapas, você estará pronto para acessar a API Microsoft 365 Defender usando um contexto específico.

## <a name="application-context-recommended"></a>Contexto do aplicativo (recomendado)

Use esse contexto para aplicativos que são executados sem um usuário in-locado presente, como serviços em segundo plano ou daemons.

1. Crie um Azure Active Directory web.
2. Atribua as permissões desejadas ao aplicativo.
3. Crie uma chave para o aplicativo.
4. Obter um token de segurança usando o aplicativo e sua chave.
5. Use o token para acessar Microsoft 365 API do Defender.

Para obter mais informações, **[consulte Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.

## <a name="user-context"></a>Contexto do usuário

Use esse contexto para executar ações em nome de um único usuário.

1. Crie um Azure Active Directory nativo.
2. Atribua a permissão desejada ao aplicativo.
3. Obter um token de segurança usando as credenciais do usuário para o aplicativo.
4. Use o token para acessar Microsoft 365 API do Defender.

Para obter mais informações, **[consulte Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Contexto do parceiro

Use esse contexto quando precisar fornecer um aplicativo para muitos usuários em [vários locatários.](/azure/active-directory/develop/single-and-multi-tenant-apps)

1. Crie um Azure Active Directory de vários locatários.
2. Atribua a permissão desejada ao aplicativo.
3. Obter [consentimento do administrador](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para o aplicativo de cada locatário.
4. Obter um token de segurança usando credenciais de usuário com base na ID de locatário de um cliente.
5. Use o token para acessar Microsoft 365 API do Defender.

Para obter mais informações, **[consulte Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.

## <a name="related-articles"></a>Artigos relacionados

- [Microsoft 365 Visão geral das APIs do Defender](api-overview.md)
- [Autorização OAuth 2.0 para entrada do usuário e acesso à API](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](/learn/modules/manage-secrets-with-azure-key-vault/)
- [Criar um aplicativo 'Hello world' que acessa as APIs Microsoft 365](api-hello-world.md)