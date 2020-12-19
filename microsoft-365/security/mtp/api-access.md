---
title: Acessar as APIs do Microsoft 365 defender
description: Saiba como acessar as APIs do Microsoft 365 defender
keywords: acesso, APIs, contexto de aplicativo, contexto de usuário, aplicativo AAD, token de acesso
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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719233"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Acessar as APIs do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs ajudam a automatizar os fluxos de trabalho e a fazer uso completo dos recursos do Microsoft 365 defender.

Em geral, você precisará executar as seguintes etapas para usar as APIs:

- Criar um aplicativo do Azure Active Directory
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API do Microsoft 365 defender

> [!NOTE]
> O acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Depois de concluir essas etapas, você estará pronto para acessar a API do Microsoft 365 defender usando um contexto específico.

## <a name="application-context-recommended"></a>Contexto do aplicativo (recomendado)

Use este contexto para aplicativos que são executados sem um usuário conectado, como serviços de segundo plano ou daemons.

1. Criar um aplicativo Web do Azure Active Directory.
2. Atribua as permissões desejadas ao aplicativo.
3. Crie uma chave para o aplicativo.
4. Obtenha um token de segurança usando o aplicativo e sua chave.
5. Use o token para acessar a API do Microsoft 365 defender.

Para obter mais informações, consulte **[criar um aplicativo para acessar o Microsoft 365 defender sem um usuário](api-create-app-web.md)**.

## <a name="user-context"></a>Contexto de usuário

Use este contexto para executar ações em nome de um único usuário.

1. Criar um aplicativo nativo do Azure Active Directory.
2. Atribua a permissão desejada ao aplicativo.
3. Obtenha um token de segurança usando as credenciais do usuário para o aplicativo.
4. Use o token para acessar a API do Microsoft 365 defender.

Para obter mais informações, consulte **[criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário](api-create-app-user-context.md)**.

## <a name="partner-context"></a>Contexto de parceiro

Use este contexto quando precisar fornecer um aplicativo a muitos usuários em [vários locatários](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).

1. Criar um aplicativo de vários locatários do Azure Active Directory.
2. Atribua a permissão desejada ao aplicativo.
3. Obter o [consentimento do administrador](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) para o aplicativo de cada locatário.
4. Obter um token de segurança usando credenciais de usuário com base na ID de locatário do cliente.
5. Use o token para acessar a API do Microsoft 365 defender.

Para obter mais informações, consulte **[criar um aplicativo com acesso de parceiro às APIs do Microsoft 365 defender](api-partner-access.md)**.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 defender](api-overview.md)
- [Autorização OAuth 2,0 para entrada de usuário e acesso à API](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [Gerenciar segredos em seus aplicativos de servidor com o Azure Key Vault](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [Criar um aplicativo de "Hello World" que acessa as APIs do Microsoft 365](api-hello-world.md)
