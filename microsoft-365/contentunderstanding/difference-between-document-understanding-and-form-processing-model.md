---
title: Diferença entre modelos de processamento de formulários e compreensão de documentos
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Descreve a principal diferença entre modelos de processamento de formulários e compreensão de documentos
ms.openlocfilehash: 268a2fa4a0381e5822c17e5df22566c931d37f3c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294743"
---
# <a name="difference-between-document-understanding-and-form-processing-models"></a>Diferença entre modelos de processamento de formulários e compreensão de documentos 

O conteúdo deste artigo é para a visualização privada do projeto Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

Compreensão do conteúdo no Project Cortex permite que você identifique e Classifique documentos que são carregados em bibliotecas de documentos do SharePoint, bem como extraia informações relevantes de cada arquivo.  Por exemplo, à medida que os arquivos são carregados para uma biblioteca de documentos do SharePoint, todos os arquivos identificados como *ordens de compra* são classificados como tal e, em seguida, exibidos em um modo de exibição de biblioteca de documentos personalizado. Além disso, você pode extrair informações específicas de cada arquivo (por exemplo, *número de OC* e *total*) e exibi-las como uma coluna no modo de exibição de biblioteca de documentos. 

A compreensão do conteúdo permite que você crie *modelos* para identificar e extrair as informações necessárias. Estes são dois tipos de modelo que podem ser usados:

- [Modelos de compreensão de documentos](document-understanding-overview.md)
- [Modelos de processamento de formulário](form-processing-overview.md)

Embora os dois modelos sejam geralmente usados com o mesmo objetivo, as principais diferenças listadas abaixo afetam quais podem ser usadas.

## <a name="structured-versus-unstructured-and-semi-structured-content"></a>Conteúdo estruturado versus não estruturado e semi-estruturados

Use documentos entendendo modelos para identificar e extrair dados de documentos não estruturados, como cartas ou contratos, onde as entidades de texto que você deseja extrair residem em frases ou regiões específicas do documento. Por exemplo, um documento não estruturado pode ser uma carta de renovação de contrato que pode ser escrita de diferentes maneiras. No entanto, as informações existem consistentemente no corpo de cada documento de renovação de contrato, como a cadeia de caracteres de texto "data de início do serviço" seguida de uma data real.   

Use modelos de processamento de formulário para identificar arquivos e extrair dados de documentos estruturados ou semi-estruturados, como formulários ou faturas. Esses documentos devem ter pares de chave-valor claro (por exemplo, *Date: 10/1/2020*) * ou Table Data. Por exemplo, um bom candidato para processamento de formulários é o formulário de solicitação de pedido de uma empresa que os clientes precisam para fornecer informações para campos específicos que estão localizados na mesma área do layout do documento, como *nome*, *número de telefone*, *custo total*, etc.  Um formulário de impostos é um bom exemplo de um documento estruturado. 

## <a name="where-they-are-created"></a>Onde são criados

Documentos entendendo modelos são criados e gerenciados em um site do centro de conteúdo do SharePoint. 

> [!NOTE]
> Você deve ter acesso a um site de centro de conteúdo para criar um documento que compreenda o modelo ou aplicar um a uma biblioteca de documentos do SharePoint. 

Modelos de processamento de formulário são criados no [Construtor de ai](https://docs.microsoft.com/ai-builder/overview)do PowerApps, mas a criação é iniciada diretamente de uma biblioteca de documentos do SharePoint. A criação do modelo de processamento de formulários precisa estar habilitada na biblioteca de documentos para que um usuário possa criar um modelo de processamento de formulário para ele, e um administrador pode fazer isso no conteúdo entendendo as configurações de administração. Os modelos de processamento de formulários usam fluxos PowerAutomate para processar arquivos quando são carregados na biblioteca de documentos.

Ao criar um documento que compreenda o modelo, você cria um novo [tipo de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978) que é salvo na Galeria de tipos de conteúdo do SharePoint. Ou você pode usar tipos de conteúdo existentes para definir seu modelo, se necessário.

Modelos de processamento de formulário são criados no [Construtor de ai](https://docs.microsoft.com/ai-builder/overview)do PowerApps, mas a criação é iniciada diretamente de uma biblioteca de documentos do SharePoint. A criação do modelo de processamento de formulários precisa estar habilitada na biblioteca de documentos para que um usuário crie um modelo de processamento de formulários para ele. Ou um administrador pode fazer isso no conteúdo noções básicas sobre configurações de administração. Os modelos de processamento de formulários usam fluxos PowerAutomate para processar arquivos quando são carregados na biblioteca de documentos.

Os modelos de processamento de formulários também criam novos [tipos de conteúdo do SharePoint](https://support.microsoft.com/office/use-content-types-to-manage-content-consistently-on-a-site-48512bcb-6527-480b-b096-c03b7ec1d978)e também são armazenados na Galeria de tipos de conteúdo do SharePoint.

## <a name="where-they-can-be-applied"></a>Onde podem ser aplicados

Você pode aplicar modelos de compreensão de documento às bibliotecas de documentos do SharePoint às quais você tem acesso. Use o centro de conteúdo para criar um documento que compreenda o modelo e aplique-o a diferentes bibliotecas de documentos. O centro de conteúdo oferece um controle mais centralizado sobre como o documento entende modelos são usados e onde eles são aplicados. Observação essas informações também devem ser acumuladas em um centro de conteúdo.

No momento, os modelos de processamento de formulário só podem ser aplicados à biblioteca de documentos do SharePoint a partir da qual foram criados. Isso permite que usuários licenciados com acesso ao site possam criar um modelo de processamento de formulários.

 ## <a name="see-also"></a>Confira também
[Treinamento: aprimore o desempenho de negócios com o Construtor AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
[Criar um classificador](create-a-classifier.md)</br>
[Criar um extrator](create-an-extractor.md)</br>
[Aplicar um documento entendendo o modelo](apply-a-model.md)</br>
[Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</br>
