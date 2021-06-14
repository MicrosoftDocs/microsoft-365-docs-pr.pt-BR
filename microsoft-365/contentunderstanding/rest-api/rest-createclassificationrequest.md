---
title: Criar solicitação de classificação
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
description: Use a API REST para criar uma solicitação para classificar um ou mais arquivos usando um modelo de compreensão de documento treinado.
ms.openlocfilehash: 6a218db181368c2837d570062b6101bc3bacfb05
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904148"
---
# <a name="create-classification-request"></a>Criar solicitação de classificação

Cria uma solicitação para classificar um ou mais arquivos usando o modelo de compreensão de documento aplicado (consulte [exemplo](rest-createclassificationrequest.md#examples)).

O serviço REST do SharePoint Online (e o SharePoint 2016 e posterior local) dá suporte à combinação de várias solicitações. As solicitações são combinadas em uma única chamada de serviço, usando a opção de consulta OData $batch. Esse método pode ser usado para sequenciar itens do trabalho de classificação para centenas de documentos ao mesmo tempo.

## <a name="http-request"></a>Solicitação HTTP

```
POST /_api/machinelearning/workItems HTTP/1.1
```
## <a name="uri-parameters"></a>Parâmetros de URI

Nenhum

## <a name="request-headers"></a>Cabeçalhos de solicitação

| Cabeçalho | Valor |
|--------|-------|
|Aceitar|application/json;odata=verbose|
|Content-Type|application/json;odata=verbose;charset=utf-8|
|x-requestdigest|O resumo apropriado para o site atual|

## <a name="request-body"></a>Corpo da solicitação

|Nome    |Tipo   |Descrição |
|--------|-------|------------|
|_metadata|string |Definir o metadado do objeto no SPO. Sempre use o valor: {"tipo": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|TargetSiteId|guid|A ID do site onde o arquivo a ser classificado está localizado.|
|TargetWebId|guid|A ID da web onde o arquivo a ser classificado está localizado.|
|TargetUniqueId|guid|A ID do arquivo a ser classificado.|

## <a name="responses"></a>Respostas

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|201 Criado| |Êxito|

## <a name="examples"></a>Exemplos

### <a name="enqueue-a-request-to-classify-a-file-of-id-e6cff8b7-c90c-4564-b5b8-033449090932"></a>Solicitar a classificação de um arquivo "e6cff8b7-c90c-4564-b5b8-033449090932"

#### <a name="sample-request"></a>Solicitação de amostra

```
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "TargetSiteId": "f686e63b-aba7-48e5-97c7-68c4c1df292f",
    "TargetWebId": "66d6b64d-6f88-4dd9-b3db-47e6f00c53e8",
    "TargetUniqueId": "e6cff8b7-c90c-4564-b5b8-033449090932"
}
```

#### <a name="sample-response"></a>Resposta de amostra

**Código de status:** 201

## <a name="see-also"></a>Confira também

[API REST do modelo de compreensão de documentos do Syntex](syntex-model-rest-api.md)
