---
title: Aplicar modelo
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
ms.openlocfilehash: d4cadad3c45dd7af0cdaeb4e1b367426289db870
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904175"
---
# <a name="apply-model"></a>Aplicar modelo

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
|ModelUniqueId|sim|string|A ID exclusiva do arquivo de modelo.|
TargetSiteUrl|sim|string|A URL completa do site da biblioteca de destino.|
TargetWebServerRelativeUrl|sim|string|A URL relativa do servidor da Web para a biblioteca de destino.|
TargetLibraryServerRelativeUrl|sim|string|A URL relativa do servidor da biblioteca de destino.|
Viewoption|não|string|Especifica se o novo modo de exibição de modelo deve ser definido como o padrão da biblioteca.|

## <a name="response"></a>Resposta

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|200 OK| |Êxito|
|201 Criado| |Observe que como essa API dá suporte à aplicação de modelo a várias bibliotecas, um 201 pode ser retornado mesmo se houver uma falha aplicando o modelo a uma das bibliotecas. <br>Verifique o corpo da resposta para compreender se o modelo foi aplicado com êxito a todas as bibliotecas especificadas. Consulte [Solicitar corpo](rest-applymodel-method.md#request-body) para obter detalhes.|

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

[API REST do modelo de compreensão de documento Syntex](syntex-model-rest-api.md)
