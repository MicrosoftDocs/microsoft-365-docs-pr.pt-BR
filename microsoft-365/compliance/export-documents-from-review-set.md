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
description: Saiba como selecionar e exportar o conteúdo de um conjunto de revisão para apresentações ou revisões externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b3be21d4c90c861c83acf612e9aadc373189f7ba
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285357"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportar documentos de um conjunto de revisão na descoberta eletrônica avançada

Exportar permite que os usuários personalizem o conteúdo que está incluído no pacote de download. A ferramenta de exportação fornece uma página de configuração com as seguintes configurações:

![Opções para exportar itens de um conjunto de revisão](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

## <a name="export-options"></a>Opções de exportação

- Nome para exportação: o nome do trabalho de exportação.

- Descrição: campo de texto livre para que você adicione uma descrição.

- Exportar estes documentos:

  - Somente documentos selecionados-exporta somente os documentos que estão atualmente selecionados.
  
  - Todos os documentos no conjunto de revisão-exporta todos os documentos no conjunto de revisão

- Metadata
  
  - Carregar arquivo-esse arquivo contém metadados para cada arquivo. Confira [campos de metadados de documentos na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md) para obter mais informações sobre quais campos estão incluídos. Normalmente, esse arquivo pode ser ingerido por ferramentas de descoberta eletrônica de terceiros.
  
  - Marcas-quando selecionadas, as informações de marcação serão incluídas no arquivo de carregamento.

- Conteúdo
  
  - Arquivos nativos-Marque esta caixa de seleção para incluir os arquivos nativos.
  
  - Opções de conversa
    
    - Arquivos de conversa-exportar mensagens de chat reconstruídas. Este formato apresenta as conversas em um formulário que se assemelham ao que os usuários vêem no aplicativo nativo.
    
    - Mensagens de chat individuais-exporte os arquivos de conversa originais conforme eles são armazenados no Microsoft 365.

- Opções

  - Arquivos de texto: inclui versões de texto extraídas de arquivos nativos.
  
  - Substituir os nativos recriados por PDFs convertidos, se forem gerados arquivos PDF revisados durante a revisão, esses arquivos estarão disponíveis para exportação. Você pode optar por exportar somente os arquivos nativos que foram redigidos (sem selecionar essa opção) ou pode selecionar essa opção para exportar os arquivos PDF que contêm as redaçãos reais.

- As opções de saída (o conteúdo exportado estão disponíveis para download diretamente por meio de um navegador da Web ou podem ser enviadas para uma conta de armazenamento do Azure. As duas primeiras opções habilitam o download direto.)
  
  - Arquivos soltos e PSTs (email é adicionado a PSTs quando possível)-os arquivos são exportados em um formato semelhante à estrutura de diretório original vista pelos usuários em seus aplicativos nativos.  Para obter mais informações, consulte a seção [arquivos soltos e estrutura de exportação de PST](#loose-files-and-pst-export-structure) .
  
  - Estrutura de diretório condensada-os arquivos são exportados e incluídos no download.
  
  - Estrutura de diretório condensada exportada para sua conta de armazenamento do Azure-os arquivos são exportados para o repositório de armazenamento do Azure da sua organização accouunt.

## <a name="loose-files-and-pst-export-structure"></a>Estrutura de exportação de arquivos soltos e de PST

Se você selecionar essa opção de exportação, o conteúdo exportado será organizado na seguinte estrutura:

- Pasta raiz – esta pasta em nome ExportName.zip
  
  - Arquivo de metadados Export_load_file.csv.
  
  - Summary.csv-um arquivo de resumo que também contém estatísticas de exportação.
  
  - Exchange-esta pasta contém todo o conteúdo do Exchange no formato de arquivo nativo. Os arquivos nativos são substituídos por PDFs redigidos se você selecionou a opção **substituir nativos redigidos por PDFs convertidos** .
  
  - SharePoint = esta pasta contém todo o conteúdo nativo do SharePoint em um formato de arquivo nativo. Os arquivos nativos são substituídos por PDFs redigidos se você selecionou a opção **substituir nativos redigidos por PDFs convertidos** .

## <a name="condensed-directory-structure"></a>Estrutura de diretório condensada

- Pasta raiz-esta pasta é nomeada ExportName.zip
  
  - Arquivo de metadados Export_load_file.csv.
  
  - Summary.txt-um arquivo de resumo que também contém estatísticas de exportação.
  
  - Input_or_native_files-esta pasta contém todos os arquivos nativos que foram exportados. Se você exportar arquivos PDF redigidos, eles não serão colocados em arquivos PST. Em vez disso, eles são adicionados a uma pasta separada.
  
  - Error_files-esta pasta contém os seguintes arquivos de erro, se eles estiverem incluídos na exportação:
    
    - ExtractionError. Um arquivo CSV que contém metadados disponíveis de arquivos que não foram extraídos corretamente de arquivos pai.
    
    - ProcessingError – este arquivo contém uma lista de documentos com erros de processamento. Esse conteúdo é de nível de item, ou seja, se um anexo resultar em um erro de processamento, a mensagem de email que contém o anexo será incluída nessa pasta.
  
  - Extracted_text_files-esta pasta contém todos os arquivos de texto extraídos que foram gerados no processamento.

> [!NOTE]
> Os trabalhos de exportação são mantidos durante a vida útil do caso e podem ser baixados, desde que o caso não seja excluído.
