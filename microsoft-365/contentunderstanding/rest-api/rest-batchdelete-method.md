---
title: BatchDelete
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Use a API REST para remover um modelo de compreensão de documentos aplicado de uma ou mais bibliotecas.
ms.openlocfilehash: e95c0583b1b0e2f5de08228afbf161c339544047
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177232"
---
# <a name="batchdelete"></a>BatchDelete

Remove um modelo de compreensão de documentos aplicado de uma ou mais bibliotecas. Observe que um modelo deve ser removido de todas as bibliotecas antes de poder ser excluído (consulte [exemplo](rest-batchdelete-method.md#examples)).

## <a name="http-request"></a>Solicitação HTTP

```HTTP
POST /_api/machinelearning/publications/batchdelete HTTP/1.1
```

## <a name="uri-parameters"></a>Parâmetros de URI

Nenhum

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Cabeçalho | Valor |
|--------|-------|
|Aceitar|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|O resumo apropriado para o site atual.|

## <a name="request-body"></a>Corpo da solicitação

| Nome | Obrigatório | Tipo | Descrição |
|--------|-------|--------|------------|
|Publicações|sim|MachineLearningPublicationEntityData[]|A coleção do MachineLearningPublicationEntityData de cada um deles especifica o modelo e a biblioteca de documentos de destino.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Nome | Obrigatório | Tipo | Descrição |
|--------|-------|--------|------------|
|ModelUniqueId|sim|cadeia de caracteres|A ID exclusiva do arquivo de modelo.|
|TargetSiteUrl|sim|cadeia de caracteres|A URL completa do site da biblioteca de destino.|
|TargetWebServerRelativeUrl|sim|cadeia de caracteres|A URL relativa do servidor da web para a biblioteca de destino.|
|TargetLibraryServerRelativeUrl|sim|cadeia de caracteres|A URL relativa do servidor da biblioteca de destino.|

## <a name="response"></a>Resposta

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|200 OK||Esta é uma API personalizada para dar suporte à remoção de um modelo de bibliotecas de documentos múltiplos. No caso de êxito parcial, ainda é possível retornar 200 OK e o chamador precisa inspecionar o corpo da resposta para entender se o modelo foi removido com êxito de uma biblioteca de documentos.|

## <a name="response-body"></a>Corpo da resposta
| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|TotalSuccesses|int|O número total de um modelo que está sendo removido com êxito de uma biblioteca de documentos.|
|TotalFailures|int|O número total de um modelo que não foi removido de uma biblioteca de documentos.|
|Detalhes|MachineLearningPublicationResult[]|A coleção do MachineLearningPublicationResult de cada um deles especifica o resultado detalhado da remoção do modelo de uma biblioteca de documentos.|

### <a name="machinelearningpublicationresult"></a>MachineLearningPublicationResult
| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|StatusCode|int|O código de status HTTP.|
|ErrorMessage|string|A mensagem de erro que informa o que há de errado ao aplicar o modelo à biblioteca de documentos.|
|Publicação|MachineLearningPublicationEntityData|Especifica as informações do modelo e a biblioteca de documentos de destino.| 

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData
| Nome | Tipo | Descrição |
|--------|--------|------------|
|ModelUniqueId|cadeia de caracteres|A ID exclusiva do arquivo de modelo.|
|TargetSiteUrl|cadeia de caracteres|A URL completa do site da biblioteca de destino.|
|TargetWebServerRelativeUrl|cadeia de caracteres|A URL relativa do servidor da web para a biblioteca de destino.|
|TargetLibraryServerRelativeUrl|cadeia de caracteres|A URL relativa do servidor da biblioteca de destino.|

## <a name="examples"></a>Exemplos

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Remover um modelo da biblioteca de documentos de contratos no site de repositório

Nesse exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Solicitação de amostra

```HTTP
{ 
    "publications": [ 
        { 
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc", 
            "TargetSiteUrl": "https://constco.sharepoint-df.com/sites/docsite", 
            "TargetWebServerRelativeUrl": "/sites/docsite ", 
            "TargetLibraryServerRelativeUrl": "/sites/dcocsite/joedcos" 
        } 
    ] 
} 
```


#### <a name="sample-response"></a>Resposta de amostra

Na resposta, TotalFailures e TotalSuccesses se referem ao número de falhas e sucessos do modelo que está sendo removido das bibliotecas especificadas.

**Código de status:** 200

```JSON
{
    "Details": [
        {
            "ErrorMessage": null,
            "Publication": {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            },
            "StatusCode": 200
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Confira também

[API REST do modelo de compreensão de documentos do Syntex](syntex-model-rest-api.md)
