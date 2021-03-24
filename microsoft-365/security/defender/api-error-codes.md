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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ab564ddb0263b501b6aca979f2148dfb5cf92758
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054509"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de erro comuns da API REST do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Proteção contra Ameaças da Microsoft

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

Os códigos de erro podem ser retornados por uma operação em qualquer uma das APIs do Microsoft 365 Defender. Cada resposta de erro conterá uma mensagem de erro, o que pode ajudar a resolver o problema. A coluna mensagem de erro na seção tabela fornece algumas mensagens de exemplo. O conteúdo das mensagens reais variará com base nos fatores que dispararam a resposta. O conteúdo variável é indicado na tabela por colchetes de ângulo.

## <a name="error-codes"></a>Códigos de erro

Código de erro | Código de status de HTTP | Mensagem
-|-|-
BadRequest | BadRequest (400) | Mensagem de erro de Solicitação Geral de Erro.
ODataError | BadRequest (400) | Consulta OData URI inválida \<the specific error is specified\> .
InvalidInput | BadRequest (400) | Entrada inválida \<the invalid input\> .
InvalidRequestBody | BadRequest (400) | Corpo da solicitação inválido.
InvalidHashValue | BadRequest (400) | O valor hash \<the invalid hash\> é inválido.
InvalidDomainName | BadRequest (400) | O nome \<the invalid domain\> de domínio é inválido.
InvalidIpAddress | BadRequest (400) | O endereço IP \<the invalid IP\> é inválido.
InvalidUrl | BadRequest (400) | A URL \<the invalid URL\> é inválida.
MaximumBatchSizeExceeded | BadRequest (400) | Tamanho máximo do lote excedido. Recebido: \<batch size received\> , permitido: {tamanho do lote permitido}.
MissingRequiredParameter | BadRequest (400) | O \<the missing parameter\> parâmetro está faltando.
OsPlatformNotSupported | BadRequest (400) | A Plataforma \<the client OS Platform\> do sistema operacional não tem suporte para essa ação.
ClientVersionNotSupported | BadRequest (400) | \<The requested action\> tem suporte na versão do cliente \<supported client version\> e acima.
Não Autorizado (Unauthorized) | Não autorizado (401) | Não Autorizado (Unauthorized) <br /><br />*Observação: geralmente causada por um header de autorização inválido ou expirado.*
Proibido | Proibido (403) | Proibido <br /><br />*Observação: Token válido, mas permissão insuficiente para a ação*.
DisabledFeature | Proibido (403) | O recurso locatário não está habilitado.
DisallowedOperation | Proibido (403) | \<the disallowed operation and the reason\>.
NotFound | Não encontrado (404) | Mensagem de erro Geral Não Encontrada.
ResourceNotFound | Não encontrado (404) | O \<the requested resource\> recurso não foi encontrado.
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

Se você experimentar um *erro InvalidRequestBody* ou *MissingRequiredParameter,* ele pode ser causado por um erro de digitação. Revise a documentação da API e verifique se os parâmetros enviados corresponderão ao exemplo relevante.

## <a name="tracking-id"></a>ID de rastreamento

Cada resposta de erro contém um parâmetro de ID exclusivo para rastreamento. O nome da propriedade desse parâmetro é *target*. Ao entrar em contato conosco sobre um erro, anexar essa ID nos ajudará a encontrar a causa raiz do problema.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral das APIs do Microsoft 365 Defender](api-overview.md)
- [APIs com suporte do Microsoft 365 Defender](api-supported.md)
- [Acessar as APIs do Microsoft 365 Defender](api-access.md)
- [Saiba mais sobre limites de API e licenciamento](api-terms.md)
