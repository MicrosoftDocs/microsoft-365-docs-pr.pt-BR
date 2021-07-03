---
title: Criar um modelo
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
description: Use a API REST para criar um modelo e seu tipo de conteúdo associado.
ms.openlocfilehash: 1c5bd84c777774edc1aa0c2419181f7b84aa4707
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287240"
---
# <a name="create-model"></a>Criar um modelo

Cria um modelo e seu tipo de conteúdo associado. Observe que isso apenas cria o modelo. Ele ainda precisará ser treinado no centro de conteúdo (consulte [exemplos](rest-createmodel-method.md#examples)).

## <a name="http-request"></a>Solicitação HTTP

```http
POST /_api/machinelearning/models HTTP/1.1
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
|_metadata|  |Definir o metadado do objeto no SPO. Sempre use o valor: {"tipo": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"}. |
|ContentTypeGroup|string|O grupo de tipo de conteúdo associado ao modelo. Padrão para "Tipos de Conteúdo de Documento Inteligente".|
|ContentTypeName|string|O nome do tipo de conteúdo associado. O arquivo de modelo criado terá o mesmo nome.|

## <a name="responses"></a>Respostas

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|201 Criado| |Êxito|

## <a name="examples"></a>Exemplos

### <a name="create-a-new-document-understanding-model-called-contoso-contract"></a>Criar um novo modelo de compreensão de documento chamado "Contrato Contoso"

#### <a name="sample-request"></a>Solicitação de amostra

```json
{
    "__metadata": {
        "type": "Microsoft.Office.Server.ContentCenter.SPMachineLearningModelEntityData"
    },
    "ContentTypeGroup": "Intelligent Document Content Types",
    "ContentTypeName": "Contoso Contract"
}
```

#### <a name="sample-response"></a>Resposta de amostra

**Código de status:** 201

## <a name="see-also"></a>Confira também

[API REST do modelo de compreensão de documentos do Syntex](syntex-model-rest-api.md)
