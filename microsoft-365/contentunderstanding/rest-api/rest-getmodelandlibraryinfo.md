---
title: Obter informações sobre modelo e biblioteca
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
description: Use a API REST para obter informações sobre um modelo e a biblioteca onde ele foi aplicado.
ms.openlocfilehash: 6cd61364ed3b360ef235aaba21a2735002fe481e
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904152"
---
# <a name="get-model-and-library-information"></a>Obter informações sobre modelo e biblioteca

Obtém informações sobre um modelo e a biblioteca onde ele foi aplicado (veja o [exemplo](rest-getmodelandlibraryinfo.md#examples)).

## <a name="http-request"></a>Solicitação HTTP

```HTTP
GET /_api/machinelearning/publications/getbyuniqueid(‘{modelUniqueId}’) HTTP/1.1
```

## <a name="uri-parameters"></a>Parâmetros de URI

| Nome | Em | Obrigatório | Tipo | Descrição |
|--------|-------|--------|------------|
|ModelUniqueId|consulta|True|GUID|A ID exclusiva do arquivo de modelo.|

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Cabeçalho | Valor |
|--------|-------|
|Aceitar|application/json;odata=verbose|


## <a name="request-body"></a>Corpo da solicitação

| Nome | Obrigatório | Tipo | Descrição |
|--------|-------|--------|------------|
|ModelUniqueId|sim|cadeia de caracteres|A ID exclusiva do arquivo de modelo.|
|TargetSiteUrl|sim|cadeia de caracteres|A URL completa do site da biblioteca de destino.|
|TargetWebServerRelativeUrl|sim|cadeia de caracteres|A URL relativa do servidor da Web para a biblioteca de destino.|
|TargetLibraryServerRelativeUrl|sim|cadeia de caracteres|A URL relativa do servidor da biblioteca de destino.|
|TargetLibraryRemoved|sim|int|O sinalizador que indica se a biblioteca de destino foi removida ou não.|

## <a name="response"></a>Resposta

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|200 OK| |Sucesso|
|201 criado| |Observe que, como esta API oferece suporte à aplicação do modelo a várias bibliotecas, um 201 pode ser retornado mesmo se houver uma falha ao aplicar o modelo a uma das bibliotecas. <br>Verifique o corpo da resposta para saber se o modelo foi aplicado com sucesso a todas as bibliotecas especificadas. Confira o [Corpo da solicitação](rest-getmodelandlibraryinfo.md#request-body) para obter detalhes.|

## <a name="examples"></a>Exemplos

### <a name="get-information-about-the-contracts-model-and-primed-document-library-in-the-repository-site"></a>Obtenha informações sobre o modelo de contratos e biblioteca de documentos preparados no site do repositório

Neste exemplo, a ID do modelo de compreensão de documentos do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

#### <a name="sample-request"></a>Solicitação de amostra

```HTTP
GET /sites/TestCC/_api/machinelearning/publications/getbymodeluniqueid(‘{7645e69d-21fb-4a24-a17a-9bdfa7cb63dc}’) HTTP/1.1
```
#### <a name="sample-response"></a>Resposta de amostra

**Código de status:** 200

```JSON
{
    "@odata.context": "https://contoso.sharepoint.com/sites/TestCC/_api/$metadata#publications",
    "value": [
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com/sites/repository /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,94\"",
            "@odata.editLink": " https://contoso.sharepoint.com/sites/TestCC /_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-04-27T03:05:25Z",
            "CreatedBy": "i:0#.f|membership|meganb@contoso.com",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 26,
            "ModelId": 16,
            "ModelName": "contosocontract.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T17:56:42Z",
            "ModifiedBy": "i:0#.f|membership|joedoe@contoso.com",
            "ObjectId": "01ZBWEM5FZRILGLXTEB5CZ2NNNSCTWBJMQ",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/repository/contracts",
            "TargetLibraryUrl": " https://contoso.sharepoint.com/sites/repository/contracts",
            "TargetSiteUrl": "https://contoso.sharepoint.com/sites/repository",
            "TargetWebServerRelativeUrl": "/sites/repository",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        },
        {
            "@odata.type": "#Microsoft.Office.Server.ContentCenter.SPMachineLearningPublication",
            "@odata.id": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "@odata.etag": "\"7645e69d-21fb-4a24-a17a-9bdfa7cb63dc,101\"",
            "@odata.editLink": "https://contoso.sharepoint.com /sites/legal/_api/machinelearning/publications/getbyuniqueId('7645e69d-21fb-4a24-a17a-9bdfa7cb63dc')",
            "Created": "2021-01-27T03:17:44Z",
            "CreatedBy": "i:0#.f|membership|esherman@contoso.com ",
            "DriveId": "b!O-aG9qer5UiXx2jEwd8pL0221maIb9lNs9tH5vAMU-gPy9BrxT7GTrtXtdtv1Uzb",
            "ID": 27,
            "ModelId": 16,
            "ModelName": "dispositions.classifier",
            "ModelType": 0,
            "ModelUniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ModelVersion": "8.0",
            "Modified": "2021-03-17T23:17:46Z",
            "ModifiedBy": "i:0#.f|membership|esherman@contoso.com ",
            "ObjectId": "01ZBWEM5B3ERSZK4PAARGLFZ7JP6GMXG2R",
            "PublicationType": 1,
            "TargetLibraryRemoved": false,
            "TargetLibraryServerRelativeUrl": "/sites/legal/dispositions",
            "TargetLibraryUrl": "https://contoso.sharepoint.com/sites/legal/dispositions",
            "TargetSiteUrl": " https://contoso.sharepoint.com/sites/legal",
            "TargetWebServerRelativeUrl": "/sites/legal",
            "UniqueId": "7645e69d-21fb-4a24-a17a-9bdfa7cb63dc",
            "ViewOption": "NewViewAsDefault"
        }
    ]
}```
```

## <a name="see-also"></a>Confira também

[API REST do modelo de compreensão de documentos do Syntex](syntex-model-rest-api.md)
