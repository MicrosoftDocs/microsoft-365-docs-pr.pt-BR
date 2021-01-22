---
title: Códigos de erro comuns da API REST do Microsoft 365 Defender
description: Saiba mais sobre os códigos de erro comuns da API REST do Microsoft 365 Defender
keywords: api, erro, códigos, erros comuns, mtp, códigos de erro de api
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
ms.openlocfilehash: 15eabc8ff28e7cc0313e2a1cb701403de0eab120
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928385"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de erro comuns da API REST do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Proteção contra Ameaças da Microsoft

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Os códigos de erro podem ser retornados por uma operação em qualquer uma das APIs do Microsoft 365 Defender. Cada resposta de erro conterá uma mensagem de erro, o que pode ajudar a resolver o problema. A coluna de mensagem de erro na seção de tabela fornece algumas mensagens de exemplo. O conteúdo das mensagens reais variará com base nos fatores que dispararam a resposta. O conteúdo variável é indicado na tabela por colchetes angulares.

## <a name="error-codes"></a>Códigos de erro

Código de erro | Código de status de HTTP | Mensagem
-|-|-
BadRequest | BadRequest (400) | General Bad Request error message.
ODataError | BadRequest (400) | Consulta OData URI \<the specific error is specified\> inválida.
InvalidInput | BadRequest (400) | Entrada \<the invalid input\> inválida.
InvalidRequestBody | BadRequest (400) | Corpo da solicitação inválido.
InvalidHashValue | BadRequest (400) | O valor de \<the invalid hash\> hash é inválido.
InvalidDomainName | BadRequest (400) | O nome do \<the invalid domain\> domínio é inválido.
InvalidIpAddress | BadRequest (400) | O endereço IP \<the invalid IP\> é inválido.
InvalidUrl | BadRequest (400) | A URL \<the invalid URL\> é inválida.
MaximumBatchSizeExceeded | BadRequest (400) | Tamanho máximo do lote excedido. Recebido: \<batch size received\> , permitido: {tamanho do lote permitido}.
MissingRequiredParameter | BadRequest (400) | O \<the missing parameter\> parâmetro está ausente.
OsPlatformNotSupported | BadRequest (400) | Não há \<the client OS Platform\> suporte para a plataforma do sistema operacional para essa ação.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> é suportado na versão do cliente \<supported client version\> e acima.
Não Autorizado (Unauthorized) | Não autorizado (401) | Não Autorizado (Unauthorized) <br /><br />*Observação: geralmente causada por um header de autorização inválido ou expirado.*
Proibido | Proibido (403) | Proibido <br /><br />*Observação: Token válido, mas permissão insuficiente para a ação.*
DisabledFeature | Proibido (403) | O recurso de locatário não está habilitado.
DisallowedOperation | Proibido (403) | \<the disallowed operation and the reason\>.
NotFound | Não Encontrado (404) | Mensagem de erro Geral Não Encontrado.
ResourceNotFound | Não Encontrado (404) | O \<the requested resource\> recurso não foi encontrado.
InternalServerError | Erro interno do servidor (500) | *Observação: nenhuma mensagem de erro, repetir a operação ou entrar em contato com a Microsoft se ela não for resolvida*

## <a name="examples"></a>Exemplos

```json
{
    "error": {
        "code": "ResourceNotFound",
        "message": "Machine 123123123 was not found",
        "target": "43f4cb08-8fac-4b65-9db1-745c2ae65f3a"
    }
}
```

```json
{
    "error": {
        "code": "InvalidRequestBody",
        "message": "Request body is incorrect",
        "target": "1fa66c0f-18bd-4133-b378-36d76f3a2ba0"
    }
}
```

## <a name="body-parameters"></a>Parâmetros de corpo

> [!IMPORTANT]
> Os parâmetros do corpo são sensíveis a minúsculas.

Se você tiver um *erro InvalidRequestBody* ou *MissingRequiredParameter,* ele poderá ser causado por um erro de digitação. Revise a documentação da API e verifique se os parâmetros enviados estão de acordo com o exemplo relevante.

## <a name="tracking-id"></a>ID de rastreamento

Cada resposta de erro contém um parâmetro de ID exclusivo para rastreamento. O nome da propriedade deste parâmetro é *o destino.* Ao entrar em contato conosco sobre um erro, anexar essa ID nos ajudará a encontrar a causa raiz do problema.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [APIs com suporte do Microsoft 365 Defender](api-supported.md)
- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
- [Saiba mais sobre limites e licenciamento de API](api-terms.md)
