---
title: API Explorer no Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Use o Explorador de API para criar e fazer consultas de API, testar e enviar solicitações para qualquer API disponível
keywords: api, explorer, send, request, get, post,
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
ms.topic: conceptual
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 6a5684d71d34b3efdfe915ae674b4fcb90342154
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769792"
---
# <a name="api-explorer"></a>Explorador de API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)


O Microsoft Defender for Endpoint API Explorer é uma ferramenta que ajuda você a explorar várias APIs do Defender para Ponto de Extremidade interativamente. 

O Explorador de API facilita a construção e o desenvolvimento de consultas, testes e solicitações de API para qualquer ponto de extremidade da API do Defender para Ponto de Extremidade disponível. Use o Explorador de API para tomar ações ou encontrar dados que ainda não estão disponíveis por meio da interface do usuário.

A ferramenta é útil durante o desenvolvimento de aplicativos. Ele permite que você execute consultas de API que respeitem as configurações de acesso do usuário, reduzindo a necessidade de gerar tokens de acesso.

Você também pode usar a ferramenta para explorar a galeria de consultas de exemplo, copiar exemplos de código de resultado e gerar informações de depuração.

Com o Explorador de API, você pode:

- Executar solicitações para qualquer método e ver respostas em tempo real
- Navegue rapidamente pelos exemplos de API e saiba quais parâmetros eles suportam
- Fazer chamadas de API com facilidade; não é necessário autenticar além do portal de gerenciamento entrar

## <a name="access-api-explorer"></a>Explorador de API do Access

No menu de navegação esquerdo, selecione **Parceiros & APIs API**  >  **Explorer**.

## <a name="supported-apis"></a>APIs com suporte

O Api Explorer dá suporte a todas as APIs oferecidas pelo Defender para Ponto de Extremidade.
  
A lista de APIs com suporte está disponível na documentação [de APIs](apis-intro.md). 

## <a name="get-started-with-the-api-explorer"></a>Começar com o Explorador de API

1. No painel esquerdo, há uma lista de solicitações de exemplo que você pode usar. 
2. Siga os links e clique em **Executar consulta**. 

Alguns dos exemplos podem exigir a especificação de um parâmetro na URL, por exemplo, {machine-ID}.

## <a name="faq"></a>Perguntas frequentes

**Preciso ter um token de API para usar o Explorador de API?** <br>
Credenciais para acessar uma API não são necessárias. O Explorador de API usa o token do portal de gerenciamento do Defender for Endpoint sempre que faz uma solicitação.

A credencial de autenticação de usuário conectado é usada para verificar se o Explorador de API está autorizado a acessar dados em seu nome.

Solicitações de API específicas são limitadas com base em seus privilégios RBAC. Por exemplo, uma solicitação para "Enviar indicador" está limitada à função de administrador de segurança. 
