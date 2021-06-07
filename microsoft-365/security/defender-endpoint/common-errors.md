---
title: Erros comuns da API do Microsoft Defender para Ponto de Extremidade
description: Lista de erros comuns da API do Microsoft Defender para Ponto de Extremidade com descrições.
keywords: APIs, API do Microsoft Defender para Ponto de Extremidade, erros, solução de problemas
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
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c2e52b7074dcd15e7f6852a11ccb7793572cd9b5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771004"
---
# <a name="common-rest-api-error-codes"></a>Códigos de erro comuns da API REST

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


* Os códigos de erro listados na tabela a seguir podem ser retornados por uma operação em qualquer uma das APIs do Microsoft Defender para Ponto de Extremidade.
* Além do código de erro, cada resposta de erro contém uma mensagem de erro, que pode ajudar a resolver o problema.
* A mensagem é um texto livre que pode ser alterado.
* Na parte inferior da página, você pode encontrar exemplos de resposta.

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Código de erro |Código de status de HTTP |Mensagem 
:---|:---|:---
BadRequest | BadRequest (400) | Mensagem de erro de Solicitação Geral de Erro.
ODataError | BadRequest (400) | Consulta OData URI inválida (o erro específico é especificado).
InvalidInput | BadRequest (400) | Entrada inválida {a entrada inválida}.
InvalidRequestBody | BadRequest (400) | Corpo da solicitação inválido.
InvalidHashValue | BadRequest (400) | O valor de hash {o hash inválido} é inválido.
InvalidDomainName | BadRequest (400) | O nome de domínio {o domínio inválido} é inválido.
InvalidIpAddress | BadRequest (400) | O endereço IP {o IP inválido} é inválido.
InvalidUrl | BadRequest (400) | URL {a URL inválida} é inválida.
MaximumBatchSizeExceeded | BadRequest (400) | Tamanho máximo do lote excedido. Recebido: {tamanho do lote recebido}, permitido: {tamanho do lote permitido}.
MissingRequiredParameter | BadRequest (400) | O parâmetro {o parâmetro ausente} está ausente.
OsPlatformNotSupported | BadRequest (400) | A plataforma do sistema operacional {a Plataforma do sistema operacional do cliente} não é suportada para essa ação.
ClientVersionNotSupported | BadRequest (400) | {A ação solicitada} é suportada na versão do cliente {versão do cliente suportada} e acima.
Não Autorizado (Unauthorized) | Não autorizado (401) | Não autorizado (header de autorização inválido ou expirado).
Proibido | Proibido (403) | Proibido (token válido, mas permissão insuficiente para a ação).
DisabledFeature | Proibido (403) | O recurso locatário não está habilitado.
DisallowedOperation | Proibido (403) | {a operação não permitido e o motivo}.
NotFound | Não encontrado (404) | Mensagem de erro Geral Não Encontrada.
ResourceNotFound | Não encontrado (404) | O recurso {o recurso solicitado} não foi encontrado.
InternalServerError | Erro interno do servidor (500) | (Nenhuma mensagem de erro, repetir a operação)
TooManyRequests | Solicitações demais (429) | A resposta representará atingir o limite de cota por número de solicitações ou pela CPU.

## <a name="body-parameters-are-case-sensitive"></a>Os parâmetros body são sensíveis a minúsculas

No momento, os parâmetros do corpo enviado são sensíveis a minúsculas.
<br>Se você experimentar um **erro InvalidRequestBody** ou **MissingRequiredParameter,** ele pode ser causado por uma maiúscula de parâmetro errada ou letra de maiúsculas e maiúsculas de maiúsculas e baixos.
<br>Revise a página de documentação da API e verifique se os parâmetros enviados corresponderão ao exemplo relevante.

## <a name="correlation-request-id"></a>ID da solicitação de correlação

Cada resposta de erro contém um parâmetro de ID exclusivo para rastreamento.
<br>O nome da propriedade desse parâmetro é "target".
<br>Ao entrar em contato conosco sobre um erro, anexar essa ID ajudará a encontrar a causa raiz do problema.

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
