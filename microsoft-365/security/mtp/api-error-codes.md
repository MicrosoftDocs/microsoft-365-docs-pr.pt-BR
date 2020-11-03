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
ms.openlocfilehash: aceb376662f2b27397aa2332f8929a57d5a3ee03
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846003"
---
# <a name="common-microsoft-365-defender-rest-api-error-codes"></a>Códigos de erro comuns da API REST do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

>[!IMPORTANT] 
>Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

Os códigos de erro listados na tabela a seguir podem ser retornados por uma operação em qualquer uma das APIs do Microsoft 365 defender.

Cada resposta de erro contém uma mensagem de erro, que pode ajudar a resolver o problema.

A mensagem é um texto livre que pode ser alterado.

Na parte inferior da página, você pode encontrar exemplos de resposta.

Código de erro |Código de status de HTTP |Mensagem 
:---|:---|:---
BadRequest | BadRequest (400) | Mensagem geral de erro de solicitação incorreta.
ODataError | BadRequest (400) | Consulta de URI de OData inválida (o erro específico foi especificado).
InvalidInput | BadRequest (400) | Entrada inválida {a entrada inválida}.
InvalidRequestBody | BadRequest (400) | Corpo de solicitação inválido.
InvalidHashValue | BadRequest (400) | O valor de hash {o hash inválido} é inválido.
InvalidDomainName | BadRequest (400) | Nome do domínio {o domínio inválido} é inválido.
InvalidIpAddress | BadRequest (400) | Endereço IP {o IP inválido} é inválido.
InvalidUrl | BadRequest (400) | URL {a URL inválida} é inválida.
MaximumBatchSizeExceeded | BadRequest (400) | Tamanho máximo do lote excedido. Recebido: {tamanho do lote recebido}, permitido: {tamanho do lote permitido}.
MissingRequiredParameter | BadRequest (400) | Parâmetro {o parâmetro ausente} está ausente.
OsPlatformNotSupported | BadRequest (400) | Plataforma do sistema operacional {a plataforma do sistema operacional do cliente não tem suporte para esta ação.
ClientVersionNotSupported | BadRequest (400) | {A ação solicitada} é suportada na versão do cliente {versão do cliente com suporte} e acima.
Não Autorizado (Unauthorized) | Não autorizado (401) | Não autorizado (cabeçalho de autorização geralmente inválido ou expirado).
Proibido | Proibido (403) | Proibido (token válido, mas permissão insuficiente para a ação).
DisabledFeature | Proibido (403) | O recurso de locatário não está habilitado.
DisallowedOperation | Proibido (403) | {a operação não permitido e o motivo}.
Não encontrado | Não encontrado (404) | Mensagem de erro geral não encontrado.
ResourceNotFound | Não encontrado (404) | Recurso {o recurso solicitado} não foi encontrado.
InternalServerError | Erro interno do servidor (500) | (Sem mensagem de erro, repita a operação ou fale conosco se não for resolvido)

## <a name="body-parameters-are-case-sensitive"></a>Os parâmetros de corpo diferenciam maiúsculas de minúsculas

Os parâmetros de corpo enviados diferenciam maiúsculas de minúsculas.
<br>Se você tiver erros de **InvalidRequestBody** ou **MissingRequiredParameter** , ele poderá ser causado por uma letra maiúscula ou minúscula de parâmetro incorreto.
<br>Recomendamos que você revise a página de documentação da API e verifique se os parâmetros enviados correspondem ao exemplo relevante.

## <a name="correlation-request-id"></a>ID de solicitação de correlação

Cada resposta de erro contém um parâmetro de ID exclusivo para controle.
<br>O nome da propriedade desse parâmetro é "target".
<br>Ao entrar em contato conosco sobre um erro, a anexação dessa ID ajudará a encontrar a causa raiz do problema.

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

