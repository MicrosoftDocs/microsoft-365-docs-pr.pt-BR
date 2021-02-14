---
title: Exportar documentos de um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba como selecionar e exportar conteúdo de um conjunto de revisão para apresentações ou avaliações externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285357"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportar documentos de um conjunto de revisão na Descoberta Avançada

A exportação permite que os usuários personalizem o conteúdo incluído no pacote de download. A ferramenta Exportar fornece uma página de configuração com as seguintes configurações:

![Opções para exportar itens de um conjunto de revisão](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>Opções de exportação

- Nome da exportação: Nome do trabalho de exportação.

- Descrição: campo de texto livre para adicionar uma descrição.

- Exporte estes documentos:

  - Somente documentos selecionados - Exporta somente os documentos selecionados no momento.
  
  - Todos os documentos no conjunto de revisão - Exporta todos os documentos no conjunto de revisão

- Metadata
  
  - Carregar arquivo – Esse arquivo contém metadados para cada arquivo. consulte [Campos de metadados do documento na Descoberta eDiscovery Avançada](document-metadata-fields-in-Advanced-eDiscovery.md) para obter mais informações sobre quais campos estão incluídos. Normalmente, esse arquivo pode ser ingerido por ferramentas de Descoberta eDiscovery de terceiros.
  
  - Marcas - Quando selecionada, as informações de marcação serão incluídas no arquivo de carregamento.

- Conteúdo
  
  - Arquivos nativos - Marque essa caixa de seleção para incluir os arquivos nativos.
  
  - Opções de conversa
    
    - Arquivos de conversa - Exportar mensagens de chat reconstruídas. Esse formato apresenta conversas em um formato semelhante ao que os usuários veem no aplicativo nativo.
    
    - Mensagens de chat individuais - Exporte os arquivos de conversa originais à medida que são armazenados no Microsoft 365.

- Opções

  - Arquivos de texto – Inclua versões de texto extraídas de arquivos nativos.
  
  - Substituir nativos redacted por PDFs convertidos - se os arquivos PDF redacted são gerados durante a revisão, esses arquivos estão disponíveis para exportação. Você pode optar por exportar somente os arquivos nativos que foram editados (não selecionando essa opção) ou pode selecionar essa opção para exportar os arquivos PDF que contêm as redação reais.

- Opções de saída (o conteúdo exportado está disponível para download diretamente por meio de um navegador da Web ou pode ser enviado para uma conta de Armazenamento do Azure. As duas primeiras opções habilitam o download direto.)
  
  - Arquivos soltos e PSTs (o email é adicionado a PSTs quando possível) - Os arquivos são exportados em um formato semelhante à estrutura de diretório original vista pelos usuários em seus aplicativos nativos.  Para obter mais informações, consulte a [seção Arquivos soltos e estrutura de exportação de PST.](#loose-files-and-pst-export-structure)
  
  - Estrutura de diretórios condensados - Os arquivos são exportados e incluídos no download.
  
  - Estrutura de diretório condensada exportada para sua conta de Armazenamento do Azure : os arquivos são exportados para o adcouunt do Armazenamento do Azure da sua organização.

## <a name="loose-files-and-pst-export-structure"></a>Arquivos soltos e estrutura de exportação PST

Se você selecionar essa opção de exportação, o conteúdo exportado será organizado na seguinte estrutura:

- Pasta raiz – essa pasta no nome ExportName.zip
  
  - Export_load_file.csv - Arquivo de metadados.
  
  - Summary.csv - Um arquivo de resumo que também contém estatísticas de exportação.
  
  - Exchange – Essa pasta contém todo o conteúdo do Exchange no formato de arquivo nativo. Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**
  
  - SharePoint = Esta pasta contém todo o conteúdo nativo do SharePoint em um formato de arquivo nativo. Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**

## <a name="condensed-directory-structure"></a>Estrutura de diretórios condensados

- Pasta raiz - Essa pasta é denominada ExportName.zip
  
  - Export_load_file.csv - Arquivo de metadados.
  
  - Summary.txt - Um arquivo de resumo que também contém estatísticas de exportação.
  
  - Input_or_native_files - Essa pasta contém todos os arquivos nativos que foram exportados. Se você exportar arquivos PDF editados, eles não serão colocados em arquivos PST. Em vez disso, eles são adicionados a uma pasta separada.
  
  - Error_files - Esta pasta contém os seguintes arquivos de erro, se eles estão incluídos na exportação:
    
    - ExtractionError. Um arquivo CSV que contém todos os metadados disponíveis de arquivos que não foram extraídos corretamente dos arquivos pai.
    
    - ProcessingError – Este arquivo contém uma lista de documentos com erros de processamento. Esse conteúdo é de nível de item, ou seja, se um anexo resultou em um erro de processamento, a mensagem de email que contém o anexo será incluída nessa pasta.
  
  - Extracted_text_files - Essa pasta contém todos os arquivos de texto extraídos que foram gerados no processamento.

> [!NOTE]
> Os trabalhos de exportação são mantidos durante a vida útil do caso e podem ser baixados, desde que o caso não seja excluído.
