---
title: Acessar as APIs de proteção contra ameaças da Microsoft
description: Saiba como acessar as APIs de proteção contra ameaças da Microsoft
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
ms.openlocfilehash: bccf36f46121caceeb6dc6d97c126f48149d9426
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197876"
---
# <a name="access-the-microsoft-threat-protection-apis"></a>Acessar as APIs de proteção contra ameaças da Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.


 A proteção contra ameaças da Microsoft expõe muito de seus dados e ações por meio de um conjunto de APIs de programação. Essas APIs permitirão que você automatize os fluxos de trabalho e inovações com base nos recursos de proteção contra ameaças da Microsoft. O acesso à API requer autenticação do OAuth 2.0. Para obter mais informações, consulte [fluxo de código de autorização do OAuth 2,0](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).


Em geral, você precisará executar as seguintes etapas para usar as APIs:
- Criar um aplicativo AAD
- Obter um token de acesso usando este aplicativo
- Usar o token para acessar a API de proteção contra ameaças da Microsoft


Você pode acessar a API do Microsoft Threat Protection com **contexto do aplicativo** ou **contexto do usuário**.

- **Contexto do aplicativo: (recomendado)** <br>
    Usado por aplicativos que são executados sem um usuário conectado presente. por exemplo, aplicativos executados como serviços em segundo plano ou daemons.

    Etapas que precisam ser seguidas para acessar a API de proteção contra ameaças da Microsoft com contexto de aplicativo:

  1. Criar um aplicativo Web do AAD.
  2. Atribua a permissão desejada ao exemplo de applicationFor, **Incident. Read. All**, **AdvancedHunting. Read. All**. 
  3. Crie uma chave para este aplicativo.
  4. Obtém o token usando o aplicativo com sua chave.
  5. Usar o token para acessar a API de proteção contra ameaças da Microsoft

     Para obter mais informações, consulte [obter acesso com contexto de aplicativo](api-create-app-web.md).


- **Contexto do usuário:** <br>
    Usado para executar ações na API em nome de um usuário.

    Etapas que devem ser seguidas para acessar a API de proteção contra ameaças da Microsoft com contexto de aplicativo:
  1. Criar aplicativo nativo do AAD.
  2. Atribua a permissão desejada ao aplicativo. Por exemplo, **Incident. Read**, **AdvancedHunting. Read**.
  3. Obtém o token usando o aplicativo com credenciais do usuário.
  4. Usar o token para acessar a API de proteção contra ameaças da Microsoft

     Para obter mais informações, consulte [obter acesso com contexto de usuário](api-create-app-user-context.md).


## <a name="related-topics"></a>Tópicos relacionados
- [APIs de proteção contra ameaças da Microsoft](api-supported.md)
- [Acesso à proteção contra ameaças da Microsoft com contexto de aplicativo](api-create-app-web.md)
- [Acesso à proteção contra ameaças da Microsoft com contexto de usuário](api-create-app-user-context.md)
