---
title: Modelo de aplicação em lote
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
description: Use a API REST para aplicar um modelo de compreensão de documento a uma ou mais bibliotecas.
ms.openlocfilehash: 04f1dfdb0c16110c9ba7de12f5f0735d498d50cf
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286532"
---
# <a name="batch-apply-model"></a>Modelo de Aplicação em lote

Aplica (ou sincroniza) um modelo treinado de compreensão de documento a uma ou mais bibliotecas (consulte o [exemplo](rest-applymodel-method.md#examples)).

## <a name="http-request"></a>Solicitação HTTP

```HTTP
POST /_api/machinelearning/publications HTTP/1.1
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
|__metadata|sim|string|Definir o metadado do objeto no SPO. Sempre use o valor: {"type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningPublicationsEntityData"}.|
|Publicações|sim|MachineLearningPublicationEntityData[]|A coleção do MachineLearningPublicationEntityData de cada um deles especifica o modelo e a biblioteca de documentos de destino.|

### <a name="machinelearningpublicationentitydata"></a>MachineLearningPublicationEntityData

| Nome | Obrigatório | Tipo | Descrição |
|--------|-------|--------|------------|
|ModelUniqueId|sim|string|A ID exclusiva do arquivo de modelo.|
|TargetSiteUrl|sim|string|A URL completa do site da biblioteca de destino.|
|TargetWebServerRelativeUrl|sim|string|A URL relativa do servidor da web para a biblioteca de destino.|
|TargetLibraryServerRelativeUrl|sim|string|A URL relativa do servidor da biblioteca de destino.|
|ViewOption|não|string|Especifica se o novo modo de exibição de modelo deve ser definido como o padrão da biblioteca.|

## <a name="response"></a>Resposta

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|201 Criado||Essa é uma API personalizada para dar suporte à aplicação de um modelo a várias bibliotecas de documentos. No caso de êxito parcial, o 201 criado ainda pode ser retornado e o chamador precisa inspecionar o corpo da resposta para entender se o modelo foi aplicado com êxito a uma biblioteca de documentos.|

## <a name="response-body"></a>Corpo da resposta

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|TotalSuccesses|int|O número total de um modelo que está sendo aplicado com êxito de uma biblioteca de documentos.|
|TotalFailures|int|O número total de um modelo que não foi aplicado a uma biblioteca de documentos.|
|Detalhes|MachineLearningPublicationResult[]|A coleção do MachineLearningPublicationResult de cada um deles especifica o resultado detalhado da aplicação do modelo à uma biblioteca de documentos.|

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

### <a name="apply-a-model-to-the-contracts-document-library-in-the-repository-site"></a>Aplicar um modelo à biblioteca de documentos de contratos no site de repositório

Neste exemplo, a ID do modelo de compreensão de documento do Contrato da Contoso é `7645e69d-21fb-4a24-a17a-9bdfa7cb63dc`.

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

**Código de status:** 201

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
            "StatusCode": 201
        }
    ],
    "TotalFailures": 0,
    "TotalSuccesses": 1
}
```

## <a name="see-also"></a>Confira também

[API REST do modelo de compreensão de documentos do Syntex](syntex-model-rest-api.md)
