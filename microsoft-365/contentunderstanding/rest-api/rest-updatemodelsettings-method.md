---
title: UpdateModelSettings
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
description: Use a API REST para atualizar as configurações de modelos disponíveis para um modelo de compreensão de documentos.
ms.openlocfilehash: f24fc8428adbf22ded2ca6d7a49cabc84b385770
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904153"
---
# <a name="updatemodelsettings"></a>UpdateModelSettings

Atualiza as configurações de modelos disponíveis (descrição de modelo e rótulo de retenção associado) para um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex (consulte [exemplo](rest-updatemodelsettings-method.md#examples)).

## <a name="http-request"></a>Solicitação HTTP

```HTTP
POST /_api/machinelearning/models/updatemodelsettings HTTP/1.1
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

|Nome    |Tipo   |Descrição |
|--------|-------|-------|
|ModelSettings|string|Configurações do modelo JSON.|
|Descrição|string|A descrição do modelo.|
|RetentionLabel| |Informações do rótulo associado (ID do rótulo e nome).|

## <a name="responses"></a>Respostas

| Nome   | Tipo  | Descrição|
|--------|-------|------------|
|200 OK| |Êxito|

## <a name="examples"></a>Exemplos

### <a name="update-model-settings-for-contoso-contract"></a>Atualizar as configurações do modelo para o Contrato da Contoso

Nesse exemplo, a descrição do modelo e o rótulo de retenção "Standard Hold" são atualizados. A ID do rótulo de retenção é `27c5fcba-abfd-4c34-823d-0b4a48f7ffe6`.

#### <a name="sample-request"></a>Solicitação de amostra

```HTTP
{
    "ModelSettings": "{\"Description\":\"This model is used to set files classified as Contoso Contracts with a standard hold retention.\", \"RetentionLabel\":{\"Id\":\"27c5fcba-abfd-4c34-823d-0b4a48f7ffe6\",\"Name\":\"Standard Hold\"}}"
}

```

#### <a name="sample-response"></a>Resposta de amostra

**Código de status:** 200

## <a name="see-also"></a>Confira também

[API REST do modelo de compreensão de documentos do Syntex](syntex-model-rest-api.md)
