---
title: Visão geral da compreensão de documentos
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
description: Obtenha uma visão geral da compreensão de documentos no Microsoft SharePoint Syntex.
ms.openlocfilehash: d2bf581468eeee008d09a242876bed5ad07ae01f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242405"
---
# <a name="document-understanding-overview"></a>Visão geral da compreensão de documentos


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSu7] 

</br>

A compreensão de documentos usa modelos de inteligência artificial (IA) para automatizar a classificação de arquivos e a extração de informações. Ele funciona melhor com documentos não estruturados, como cartas ou contratos. Esses documentos devem ter texto que pode ser identificado com base em frases ou padrões. O texto identificado designa o tipo de arquivo (sua classificação) e o que você deseja extrair (suas extrações).

> [!NOTE]
> Confira [Adoção do SharePoint Syntex: guia de introdução](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#document-understanding-scenario-example) para saber mais sobre os exemplos de cenários da compreensão de documentos.

Os modelos de compreensão de documentos são criados e gerenciados em um tipo de site do SharePoint chamado *centro de conteúdo*. Quando aplicada a uma biblioteca de documentos do SharePoint, o modelo é associado a um tipo de conteúdo que possui colunas para armazenar as informações que estão sendo extraídas. O tipo de conteúdo que você cria é armazenado na galeria de tipos de conteúdo do SharePoint. Você também pode optar por usar os tipos de conteúdo existentes para usar o esquema.

> [!NOTE]
> Tipos de conteúdo selados ou somente leitura não podem ser atualizados e, assim, não podem ser usados em um modelo.

Adicione se *Classificadores* e *Extratores* ao seu modelo de compreensão de documentos para fazer o seguinte: 

- Os classificadores são usados para identificar e classificar os documentos que são carregados na biblioteca de documentos. Por exemplo, um classificador pode ser "treinado" para identificar toda a renovação de *documentos que são carregados na biblioteca*. O tipo de conteúdo de renovação de contrato é definido por você quando você cria seu classificador.

- Os extratores recebem informações desses documentos. Por exemplo, para todos os documentos de renovação de contrato identificados na biblioteca de documentos, as colunas são exibidas no modo de exibição que também mostram a *Data de início do serviço* e  *Cliente* para cada documento de renovação de contrato. 

Você pode usar os arquivos de exemplo para treinar e testar seus separadores e extrações em seu modelo. Os arquivos de exemplo fornecem exemplos ao seu modelo sobre o que procurar ao tentar identificar e extrair dados de arquivos. Por exemplo, você treina os classificadores e os extratores da renovação de contrato com exemplos de documentos de renovação de contrato que a sua empresa usa. Você também pode usar arquivos de exemplo para testar a eficácia do seu modelo.

Depois de publicar seu modelo, use o centro de conteúdo para aplicá-lo a qualquer biblioteca de documentos do SharePoint à qual você tenha acesso.  

### <a name="file-limitations"></a>Limitações de arquivo

Os modelos de compreensão de documentos usam a tecnologia reconhecimento óptico de caracteres (OCR) para digitalizar PDFs, imagens e arquivos TIFF, tanto quando você treina um modelo com arquivos de exemplo como quando executa o modelo em arquivos em uma biblioteca de documentos.

Observe as seguintes diferenças em relação aos arquivos baseados em texto do Microsoft Office e arquivos digitalizados por OCR (PDF, imagem ou TIFF):

- Arquivos do Office: truncamos em 64000 caracteres (no treinamento e quando executado em arquivos em uma biblioteca de documentos).
- Arquivos digitalizados por OCR: há um limite de 20 páginas.  

#### <a name="supported-file-types"></a>Tipos de arquivo compatíveis

Os modelos de compreensão de documentos são compatíveis com os seguintes tipos de arquivo:

- doc
- docx
- eml
- HEIC
- HEIF
- htm
- HTML
- JPEG
- jpg
- Markdown
- md
- msg
- pdf
- PNG
- ppt
- pptx
- rtf
- tif
- tiff
- txt
- xls
- xlsx



## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)

[Criar um extrator](create-an-extractor.md)

[Criar um centro de conteúdo](create-a-content-center.md)

[Criar um modelo de processamento de formulário](create-a-form-processing-model.md)

[Aplicar um modelo](apply-a-model.md)   

[Diferença entre um modelo de compreensão de documentos e um modelo de processamento de formulário](difference-between-document-understanding-and-form-processing-model.md)
  
[Visão geral do processamento de formulário](form-processing-overview.md)

[Modo de acessibilidade do SharePoint Syntex](accessibility-mode.md)
