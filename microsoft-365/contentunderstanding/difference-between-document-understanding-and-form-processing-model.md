---
title: Diferença entre modelo de compreensão de documentos e modelo de processamento de formulário
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Descreve as principais diferenças entre o modelo de compreensão de documentos e o modelo de processamento de formulário
ms.openlocfilehash: f57d220eb77a783de5ac352f3cf684364252a163
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975872"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Diferença entre modelo de compreensão de documentos e modelo de processamento de formulário 


A compreensão do conteúdo no Microsoft SharePoint Syntex permite que você identifique e classifique os documentos carregados nas bibliotecas de documentos do SharePoint e extraia informações relevantes de cada arquivo.  Por exemplo, conforme os arquivos são carregados em uma biblioteca de documentos do SharePoint, todos os arquivos identificados como *Pedidos de Compra* são classificados como tal e, em seguida, exibidos em um modo de exibição de biblioteca de documentos personalizado. Além disso, você pode inserir informações específicas de cada arquivo (por exemplo, *Número do PC* e *Total*) e exibi-las como uma coluna no modo de exibição da biblioteca de documentos. 

A compreensão de conteúdo permite que você crie *modelos* para identificar e extrair as informações necessárias. Os modelos têm valor para ajudar a resolver problemas de negócios para pesquisa, processos de negócios, conformidade e muitos outros.

Há dois tipos de modelo que você pode usar:

- [Modelos de compreensão de documentos](document-understanding-overview.md)
- [Modelos de processamento de formulário](form-processing-overview.md)

Embora os dois modelos sejam usados para a mesma finalidade, as principais diferenças listadas abaixo afetam quais podem ser usadas.

> [!NOTE]
> Confira [Adoção do SharePoint Syntex: guia de introdução](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) para saber mais sobre os exemplos de cenários de processamento de formulário e compreensão de documentos.


## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Conteúdo estruturado versus conteúdo não estruturado e semiestruturado

Utilize modelos de compreensão de documento para identificar e extrair dados de documentos não estruturados, como cartas ou contratos, onde as entidades de texto que você deseja extrair estão em frases ou regiões específicas do documento. Por exemplo, um documento não estruturado pode ser uma carta de renovação de contrato que pode ser escrita de maneiras diferentes. No entanto, as informações existem de forma consistente no corpo de cada documento de renovação de contrato, como a cadeia de texto *Data de início do serviço de* seguida de uma data real.

Use modelos de processamento de formulário para identificar arquivos e extrair dados de documentos estruturados e semiestruturados, como formulários ou faturas. Os modelos de processamento de formulário são treinados para entender o layout do seu formulário a partir de documentos de exemplo e aprender a procurar os dados que você precisa extrair de locais semelhantes. Os formulários geralmente têm um layout mais estruturado, onde as entidades estão no mesmo local (por exemplo, um número de previdência social em um formulário de imposto).

> [!NOTE]
> Você deve ter acesso a um site do centro de conteúdo para criar um modelo de compreensão de documentos ou aplicar um a uma biblioteca de documentos do SharePoint. 


## <a name="where-models-are-created"></a>Onde os modelos são criados

Os modelos de compreensão de documentos são criados e gerenciados em um site do centro de conteúdo do SharePoint. 

> [!NOTE]
> Para obter mais informações sobre documentos de entrada, confira [Requisitos e limitações do modelo de processamento de formulário](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

Os modelos de processamento de formulário são criados no PowerApps [Construtor AI](https://docs.microsoft.com/ai-builder/overview), mas a criação começa diretamente a partir de uma biblioteca de documentos do Microsoft Office SharePoint Online. Uma biblioteca de documentos deve ter a criação do modelo de processamento de formulário habilitada antes que um usuário possa criar um modelo de processamento de formulário para ela. Os administradores podem ativar a criação do modelo de processamento de formulário nas configurações de administração de compreensão de conteúdo. Os modelos de processamento de formulário usam fluxos do PowerAutomate para processar arquivos quando eles são carregados na biblioteca de documentos.

Ao criar um modelo de compreensão de documentos, você cria um novo [tipo de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que é salvo na galeria Tipos de Conteúdo do SharePoint. Ou você pode usar modelos de conteúdo existentes para definir seu modelo, se necessário.

Os modelos de processamento de formulário também criam novos [tipos de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) e também são armazenados na galeria Tipos de Conteúdo do SharePoint.

## <a name="where-they-can-be-applied"></a>Onde eles podem ser aplicados

Você pode aplicar os modelos de compreensão de documentos nas bibliotecas de documentos do SharePoint as quais você tem acesso. Use o centro de conteúdo para criar um modelo de compreensão de documentos e aplique-o em diferentes bibliotecas de documentos. O centro de conteúdo oferece um controle mais central de como os modelos de compreensão de documentos são utilizados e onde são aplicados. Observe que esta informações também devem ser acumuladas em um centro de conteúdo.

No momento, os modelos de processamento de formulário só podem ser aplicados à biblioteca de documentos do SharePoint a partir da qual eles foram criados. Isso permite que usuários licenciados com acesso ao site criem um modelo de processamento de formulário. Observe que um administrador precisa habilitar o processamento de formulários em uma biblioteca de documentos do Microsoft Office SharePoint Online para que esteja disponível para usuários licenciados.

 ## <a name="see-also"></a>Confira também
[Treinamento: melhore o desempenho de negócios com o Construtor AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)



[Visão geral da compreensão de documentos](document-understanding-overview.md)

[Visão geral do processamento de formulário](form-processing-overview.md)

[Introdução ao SharePoint Syntex](index.md)
