---
title: API REST do modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex
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
description: Visão geral da API REST de compreensão de documentos do Microsoft Office SharePoint Online Syntex.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908084"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>API REST do modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex

Você pode usar a interface REST do Microsoft Office SharePoint Online para criar um modelo de compreensão de documento, aplicar ou remover o modelo em uma ou mais bibliotecas e obter ou atualizar informações sobre o modelo. 

O serviço REST do SharePoint Online (e o SharePoint 2016 e posterior no local) dá suporte à combinação de várias solicitações em uma única chamada para o serviço, usando a opção de consulta $batch do OData. 

Para obter detalhes e links de amostras de código, confira [Fazer solicitações em lote com APIs REST](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, verifique se está familiarizado com o seguinte:

- [Conheça o serviço REST do SharePoint](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [Realizar operações básicas usando os pontos de extremidade REST do SharePoint](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>Comandos REST

Os seguintes comandos REST estão disponíveis para trabalhar com modelos de compreensão de documentos da Syntex:

- [Criar modelo](rest-createmodel-method.md) – Cria um modelo e seu tipo de conteúdo associado.
- [GetByUniqueId](rest-getbyuniqueid-method.md) – Obtém ou atualiza informações sobre um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex.
- [GetByTitle](rest-getbytitle-method.md) – Obtém ou atualiza informações sobre um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex usando o título do modelo.
- [Aplicar modelo](rest-applymodel-method.md) – Aplica (ou sincroniza) um modelo treinado de compreensão de documento a uma ou mais bibliotecas.
- [Obter informações sobre modelos e bibliotecas](rest-getmodelandlibraryinfo.md) – Obtém informações sobre um modelo e a biblioteca na qual ele foi aplicado.
- [UpdateModelSettings](rest-updatemodelsettings-method.md) – Atualiza as configurações de modelos disponíveis (descrição de modelo e rótulo de retenção associado) para um modelo de compreensão de documento do Microsoft Office SharePoint Online Syntex.
- [BatchDelete](rest-batchdelete-method.md) – Remove um modelo de compreensão de documento aplicado de uma ou mais bibliotecas.
- [Criar solicitação de classificação](rest-createclassificationrequest.md) – Cria uma solicitação para classificar um arquivo ou arquivos especificados usando o modelo aplicado.

## <a name="scenarios"></a>Cenários

Observe os seguintes exemplos de cenário que não são intuitivos com base no nome do método. Para obter mais informações, consulte cada artigo.

O método criar modelo apenas cria o objeto de modelo e seu tipo de conteúdo associado. Será preciso primeiro treinar o modelo no centro de conteúdo antes que ele possa ser aplicado a uma biblioteca.

O método de modelo de aplicação é usado para configurar o modelo na biblioteca de destino para classificar documentos e, opcionalmente, extrair informações adicionais. Essa API também dá suporte à aplicação em lote do modelo a várias bibliotecas.

O método de remover modelo simplesmente remove o modelo de uma ou mais bibliotecas onde ele foi aplicado anteriormente. Se você quiser excluir o modelo, ele deverá primeiro ser removido de todas as bibliotecas onde ele foi aplicado.


## <a name="see-also"></a>Confira também

[Visão geral da compreensão de documentos](../document-understanding-overview.md)

