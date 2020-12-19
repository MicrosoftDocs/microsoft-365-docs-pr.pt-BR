---
title: Códigos de erro comuns da API REST do Microsoft 365 defender
description: Saiba mais sobre os códigos de erro comuns da API REST do Microsoft 365 defender
keywords: API, erro, códigos, erros comuns, MTP, códigos de erro de API
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
ms.openlocfilehash: 0df741efb7555d587a6033acc23716e93f542d5e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719209"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de erro comuns da API REST do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Proteção contra Ameaças da Microsoft

> [!IMPORTANT]
> Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Os códigos de erro podem ser retornados por uma operação em qualquer uma das APIs do Microsoft 365 defender. Cada resposta de erro conterá uma mensagem de erro, que pode ajudar a resolver o problema. A coluna mensagem de erro na seção tabela fornece algumas mensagens de amostra. O conteúdo das mensagens reais irá variar com base nos fatores que acionaram a resposta. O conteúdo da variável é indicado na tabela por colchetes angulares.

## <a name="error-codes"></a>Códigos de erro

Código de erro | Código de status de HTTP | Mensagem
-|-|-
BadRequest | BadRequest (400) | Mensagem geral de erro de solicitação incorreta.
ODataError | BadRequest (400) | Consulta de URI do OData inválida \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Entrada inválida \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Corpo de solicitação inválido.
InvalidHashValue | BadRequest (400) | O valor de hash \<the invalid hash\> é inválido.
InvalidDomainName | BadRequest (400) | O nome de domínio \<the invalid domain\> é inválido.
InvalidIpAddress | BadRequest (400) | O endereço IP \<the invalid IP\> é inválido.
InvalidUrl | BadRequest (400) | A URL \<the invalid URL\> é inválida.
MaximumBatchSizeExceeded | BadRequest (400) | Tamanho máximo do lote excedido. Recebido: \<batch size received\> , permitido: {tamanho do lote permitido}.
MissingRequiredParameter | BadRequest (400) | O parâmetro \<the missing parameter\> está ausente.
OsPlatformNotSupported | BadRequest (400) | A plataforma \<the client OS Platform\> de so não é suportada para esta ação.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> tem suporte na versão do cliente \<supported client version\> e acima.
Não Autorizado (Unauthorized) | Não autorizado (401) | Não Autorizado (Unauthorized) <br /><br />*Observação: normalmente causado por um cabeçalho de autorização inválido ou expirado.*
Proibido | Proibido (403) | Proibido <br /><br />*Observação: token válido, mas permissão insuficiente para a ação*.
DisabledFeature | Proibido (403) | O recurso de locatário não está habilitado.
DisallowedOperation | Proibido (403) | \<the disallowed operation and the reason\>.
Não encontrado | Não encontrado (404) | Mensagem de erro geral não encontrado.
ResourceNotFound | Não encontrado (404) | Recurso \<the requested resource\> não encontrado.
InternalServerError | Erro interno do servidor (500) | *Observação: nenhuma mensagem de erro, tente executar a operação novamente ou contate a Microsoft se ela não for resolvida*

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
> Os parâmetros de corpo diferenciam maiúsculas de minúsculas.

Se houver um erro de *InvalidRequestBody* ou *MissingRequiredParameter* , ele poderá ser causado por um erro de digitação. Revise a documentação da API e verifique se os parâmetros enviados correspondem ao exemplo relevante.

## <a name="tracking-id"></a>ID de acompanhamento

Cada resposta de erro contém um parâmetro de ID exclusivo para controle. O nome da propriedade desse parâmetro é *target*. Ao entrar em contato conosco sobre um erro, a anexação dessa ID nos ajudará a encontrar a causa raiz do problema.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 defender](api-overview.md)
- [APIs com suporte do Microsoft 365 Defender](api-supported.md)
- [Acessar as APIs do Microsoft 365 defender](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
