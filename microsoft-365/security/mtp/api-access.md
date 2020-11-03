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
ms.openlocfilehash: bf7a6a70cefda7bfac83d42f8e8dd6355c479914
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845007"
---
# <a name="access-the-microsoft-365-defender-apis"></a>Acessar as APIs do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


 O Microsoft 365 defender expõe grande parte de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs permitirão que você automatize os fluxos de trabalho e inovações com base nos recursos do Microsoft 365 defender. O acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


Em geral, você precisará executar as seguintes etapas para usar as APIs:
- Criar um aplicativo AAD
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API do Microsoft 365 defender


Você pode acessar a API do Microsoft 365 defender com **contexto do aplicativo** ou **contexto do usuário**.

- **Contexto do aplicativo: (recomendado)** <br>
    Usado por aplicativos que são executados sem um usuário conectado presente. por exemplo, aplicativos executados como serviços em segundo plano ou daemons.

    Etapas que precisam ser executadas para acessar a API do Microsoft 365 defender com contexto de aplicativo:

  1. Criar um aplicativo Web do AAD.
  2. Atribua a permissão desejada ao exemplo de applicationFor, **Incident. Read. All** , **AdvancedHunting. Read. All**. 
  3. Crie uma chave para este aplicativo.
  4. Obtém o token usando o aplicativo com sua chave.
  5. Usar o token para acessar a API do Microsoft 365 defender

     Para obter mais informações, consulte [obter acesso com contexto de aplicativo](api-create-app-web.md).


- **Contexto do usuário:** <br>
    Usado para executar ações na API em nome de um usuário.

    Etapas que devem ser seguidas para acessar a API do Microsoft 365 defender com contexto de aplicativo:
  1. Criar aplicativo nativo do AAD.
  2. Atribua a permissão desejada ao aplicativo. Por exemplo, **Incident. Read** , **AdvancedHunting. Read**.
  3. Obtém o token usando o aplicativo com credenciais do usuário.
  4. Usar o token para acessar a API do Microsoft 365 defender

     Para obter mais informações, consulte [obter acesso com contexto de usuário](api-create-app-user-context.md).


## <a name="related-topics"></a>Tópicos relacionados
- [APIs do Microsoft 365 defender](api-supported.md)
- [Acessar o Microsoft 365 defender com contexto de aplicativo](api-create-app-web.md)
- [Acessar o Microsoft 365 defender com contexto de usuário](api-create-app-user-context.md)
