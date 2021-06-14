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
ms.openlocfilehash: 8c7aeb449da161fe49050631643c63c93268a13f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904147"
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
|ModelUniqueId|sim|string|A ID exclusiva do arquivo de modelo.|
TargetSiteUrl|sim|string|A URL completa do site da biblioteca de destino.|
TargetWebServerRelativeUrl|sim|string|A URL relativa do servidor da web para a biblioteca de destino.|
TargetLibraryServerRelativeUrl|sim|string|A URL relativa do servidor da biblioteca de destino.|
ViewOption|não|string|Especifica se o novo modo de exibição de modelo deve ser definido como o padrão da biblioteca.|

## <a name="response"></a>Resposta

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|200 OK| |Êxito|


## <a name="examples"></a>Exemplos

### <a name="remove-a-model-from-the-contracts-document-library-in-the-repository-site"></a>Remover um modelo da biblioteca de documentos de contratos no site de repositório

Nesse exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Solicitação de amostra

```HTTP
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"
    },
    "Publications": {
        "results": [
            {
                "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
                "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository/",
                "TargetWebServerRelativeUrl": "/sites/repository",
                "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
                "ViewOption": "NewViewAsDefault"
            }
        ]
    }
}
```


#### <a name="sample-response"></a>Resposta de amostra

Na resposta, TotalFailures e TotalSuccesses se referem ao número de falhas e sucessos do modelo que está sendo aplicado às bibliotecas especificadas.

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
