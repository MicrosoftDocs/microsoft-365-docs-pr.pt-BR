---
title: Visão geral da compreensão do documento (versão prévia)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenha uma visão geral da compreensão do documento no Project Cortex.
ms.openlocfilehash: c1e4092164ee96d4f244f10be9ebab62a2c8da5b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950043"
---
# <a name="document-understanding-overview-preview"></a>Visão geral da compreensão do documento (versão prévia)
> [!Note] 
> O Project Cortex está atualmente em versão prévia. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

Noções básicas sobre documentos usa modelos AI para automatizar a classificação de arquivos e extração de informações. Ele funciona melhor com documentos não estruturados, como cartas ou contratos. Os documentos devem ter texto que possa ser identificado com base em frases ou padrões. O texto identificado pode designar o tipo de arquivo (sua classificação) e o que você gostaria de extrair (seus extratores).

Documentos entendendo modelos são criados e gerenciados em um tipo de site do SharePoint chamado de centro de conteúdo. Quando aplicado a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo que tem colunas para armazenar as informações extraídas. O tipo de conteúdo que você cria é armazenado na Galeria de tipos de conteúdo do SharePoint. Você também pode optar por usar tipos de conteúdo existentes para usar seu esquema.

Você pode adicionar *classificadores* e *extratores* ao seu documento entendendo modelos para fazer o seguinte: 

- Os classificadores são usados para identificar e classificar documentos que são carregados na biblioteca de documentos. Por exemplo, um classificador pode ser "treinado" para identificar todos os documentos de *renovação de contrato* que são carregados na biblioteca. O tipo de conteúdo de renovação de contrato é definido por você quando você cria o classificador.

- Os extratores recebem informações desses documentos. Por exemplo, para todos os documentos de renovação de contrato identificados na sua biblioteca de documentos, as colunas serão exibidas no modo de exibição que também mostrará a *data de início* e o  *cliente* para cada documento de renovação de contrato. 

Você usa arquivos de exemplo para treinar e testar classificadores e extratores no modelo. Arquivos de exemplo fornecem exemplos de modelo do que procurar ao tentar identificar e extrair dados de arquivos. Por exemplo, você treinaria os classificadores e os extratores de renovação de contrato com exemplos de documentos de renovação de contrato que sua empresa trabalha. Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.

Após publicar o modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.  


## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)</br>
[Criar um extrator](create-an-extractor.md)</br>
[Criar um centro](create-a-content-center.md) 
 de conteúdo [Criar um modelo de processamento de formulários](create-a-form-processing-model.md)</br>
[Aplicar um modelo](apply-a-model.md)   
[Diferença entre um documento entendendo e um modelo de processamento de formulário](difference-between-document-understanding-and-form-processing-model.md)  
[Visão geral do processamento de formulário](form-processing-overview.md)




