---
title: Acessar as APIs do Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Saiba como usar AS APIs para automatizar fluxos de trabalho e inovar com base nos recursos do Microsoft Defender for Endpoint
keywords: apis, api, wdatp, api aberta, microsoft defender para endpoint api, microsoft defender atp, api pública, apis suportados, alertas, dispositivo, usuário, domínio, ip, arquivo, caça avançada, consulta
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571824"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a>Acessar as APIs do Microsoft Defender para Ponto de Extremidade 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


**Aplica-se a:** 
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

> Quer experimentar o Microsoft Defender para endpoint? [Inscreva-se para um teste gratuito.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



O Defender for Endpoint expõe grande parte de seus dados e ações através de um conjunto de APIs programáticas. Essas APIs permitirão automatizar fluxos de trabalho e inovar com base nos recursos do Defender para Endpoint. O acesso à API requer autenticação OAuth2.0. Para obter mais informações, consulte [OAuth 2.0 Código de Autorização Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).

Assista a este vídeo para uma rápida visão geral do Defender para as APIs do Endpoint. 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

Em geral, você precisará tomar as seguintes medidas para usar as APIs:
- Crie um [aplicativo AAD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)
- Obtenha um token de acesso usando este aplicativo
- Use o token para acessar o Defender para API endpoint


Você pode acessar o Defender for Endpoint API com **contexto de aplicativo** ou contexto do **usuário**.

- **Contexto da aplicação: (Recomendado)** <br>
    Usado por aplicativos que são executados sem um usuário conectado presente. por exemplo, aplicativos que são executados como serviços de segundo plano ou daemons.

    Medidas que precisam ser tomadas para acessar o Defender for Endpoint API com o contexto do aplicativo:

  1. Crie um aplicativo web AAD.
  2. Atribua a permissão desejada ao aplicativo, por exemplo, 'Leia alertas', 'Máquinas isoladas'. 
  3. Crie uma chave para este Aplicativo.
  4. Obtenha token usando o aplicativo com sua chave.
  5. Use o token para acessar o Microsoft Defender para API endpoint

     Para obter mais informações, consulte [Obter acesso com o contexto do aplicativo](exposed-apis-create-app-webapp.md).


- **Contexto do Usuário:** <br>
    Usado para realizar ações na API em nome de um usuário.

    Medidas a serem tomadas para acessar o Defender para API endpoint com o contexto do aplicativo:

  1. Criar aplicação nativa AAD.
  2. Atribua a permissão desejada ao aplicativo, por exemplo, 'Leia alertas', 'Máquinas isoladas' etc. 
  3. Obtenha token usando o aplicativo com credenciais de usuário.
  4. Use o token para acessar o Microsoft Defender para API endpoint

     Para obter mais informações, consulte [Obter acesso com o contexto do usuário](exposed-apis-create-app-nativeapp.md).


## <a name="related-topics"></a>Tópicos relacionados
- [Microsoft Defender para APIs endpoint](exposed-apis-list.md)
- [Acesse o Microsoft Defender para endpoint com o contexto do aplicativo](exposed-apis-create-app-webapp.md)
- [Acesse o Microsoft Defender para endpoint com o contexto do usuário](exposed-apis-create-app-nativeapp.md)
