---
title: Visão geral da compreensão de documentos
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Obtenha uma visão geral da compreensão de documentos no Microsoft SharePoint Syntex.
ms.openlocfilehash: 3f2c463d3713048ffff7c20f2fcf6220d55d6a32
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321768"
---
# <a name="document-understanding-overview"></a>Visão geral da compreensão de documentos


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

A compreensão de documentos usa modelos de inteligência artificial (IA) para automatizar a classificação de arquivos e a extração de informações. Ele funciona melhor com documentos não estruturados, como cartas ou contratos. Esses documentos devem ter texto que pode ser identificado com base em frases ou padrões. O texto identificado designa o tipo de arquivo (sua classificação) e o que você deseja extrair (suas extrações).

Os modelos de compreensão de documentos são criados e gerenciados em um tipo de site do SharePoint chamado *centro de conteúdo*. Quando aplicada a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo que possui colunas para armazenar as informações que estão sendo extraídas. O tipo de conteúdo que você cria é armazenado na galeria de tipos de conteúdo do SharePoint. Você também pode optar por usar os tipos de conteúdo existentes para usar o esquema.

Adicione se *Classificadores* e *Extratores* ao seu modelo de compreensão de documentos para fazer o seguinte: 

- Os classificadores são usados para identificar e classificar os documentos que são carregados na biblioteca de documentos. Por exemplo, um classificador pode ser "treinado" para identificar toda a renovação de *documentos que são carregados na biblioteca*. O tipo de conteúdo de renovação de contrato é definido por você quando você cria seu classificador.

- Os extratores recebem informações desses documentos. Por exemplo, para todos os documentos de renovação de contrato identificados na biblioteca de documentos, as colunas são exibidas no modo de exibição que também mostram a *Data de início do serviço* e  *Cliente* para cada documento de renovação de contrato. 

Você pode usar os arquivos de exemplo para treinar e testar seus separadores e extrações em seu modelo. Os arquivos de exemplo fornecem exemplos ao seu modelo sobre o que procurar ao tentar identificar e extrair dados de arquivos. Por exemplo, você treina os classificadores e os extratores da renovação de contrato com exemplos de documentos de renovação de contrato que a sua empresa usa. Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.

Depois de publicar seu modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.  



## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)

[Criar um extrator](create-an-extractor.md)

[Criar um centro de conteúdo](create-a-content-center.md)

[Criar um modelo de processamento de formulário](create-a-form-processing-model.md)

[Aplicar um modelo](apply-a-model.md)   

[Diferença entre um modelo de compreensão de documentos e um modelo de processamento de formulário](difference-between-document-understanding-and-form-processing-model.md)
  
[Visão geral do processamento de formulário](form-processing-overview.md)
