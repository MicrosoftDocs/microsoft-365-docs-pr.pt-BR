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
description: Saiba como selecionar e exportar conteúdo de um conjunto de revisão de Descoberta Externa Avançada para apresentações ou avaliações externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 0752c5272d078e75e3bdbfb9cf7af7e49c78e65c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581010"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportar documentos de um conjunto de revisão em Descoberta Avançada

Exportar permite que os usuários personalizem o conteúdo incluído no pacote de download quando você exporta o documento de um conjunto de revisão em Descoberta Avançada.

Para exportar documentos de um conjunto de revisão:

1. No Centro de conformidade do Microsoft 365, abra o  caso Descoberta Avançada, selecione a guia Revisar conjuntos e selecione o conjunto de revisão que você deseja exportar.

2. No conjunto de revisão, clique em **Ação**  >  **Exportar**.

   A ferramenta Exportar exibe a página de sobrevoo com as configurações para configurar a exportação. Algumas opções são selecionadas por padrão, mas você pode alterá-los. Consulte a seção a seguir para ver descrições das opções de exportação que você pode configurar.

   ![Opções de configuração para exportar itens de um conjunto de revisão](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Depois de configurar a exportação, clique em **Exportar** para iniciar o processo de exportação. Dependendo da opção selecionada  na seção Opções de saída, você pode acessar os arquivos de exportação por download direto ou na conta de Armazenamento do Azure da sua organização.

> [!NOTE]
> Os trabalhos de exportação são mantidos durante a vida útil do caso. No entanto, você deve baixar o conteúdo de um trabalho de exportação dentro de 30 dias após a conclusão do trabalho de exportação.

## <a name="export-options"></a>Opções de exportação

Use as opções a seguir para configurar a exportação.

- **Nome da** exportação : nome do trabalho de exportação.

- **Descrição**: campo de texto livre para você adicionar uma descrição.

- **Exportar esses documentos**

  - **Somente documentos selecionados:** essa opção exporta apenas os documentos selecionados no momento.
  
  - **Todos os documentos no conjunto de revisão**: Essa opção exporta todos os documentos no conjunto de revisão.

- **Metadados**
  
  - **Arquivo de carga**: este arquivo contém metadados para cada arquivo. Normalmente, esse arquivo pode ser ingerido por ferramentas de Descoberta eDiscovery de terceiros. Para obter mais informações sobre quais campos estão incluídos, consulte [Campos de metadados de documento em Descoberta Avançada de eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).
  
  - **Marcas**: Quando selecionada, as informações de marcação são incluídas no arquivo de carga.

- **Conteúdo**
  
  - **Arquivos nativos**: selecione essa caixa de seleção para incluir os arquivos nativos dos documentos no conjunto de revisão. Se você optar por exportar arquivos nativos, terá as seguintes opções para exportar conversas de chat.
  
  - **Opções de conversa**

    - **Arquivos de conversa**: essa opção exporta conversas de chat reconstruídas. Esse formato apresenta conversas em um formulário que se parece com o que os usuários veem no aplicativo nativo.

    - **Mensagens de chat individuais**: essa opção exporta os arquivos de conversa originais à medida que são armazenados no Microsoft 365.

- **Opções**

  - **Arquivos de** texto : - Essa opção inclui as versões de texto extraídas de arquivos nativos na exportação.
  
  - **Substitua os nativos redacted por PDFs convertidos**: se os arquivos PDF redacted são gerados durante a revisão, esses arquivos estão disponíveis para exportação. Você pode optar por exportar apenas os arquivos nativos que foram editados (não selecionando essa opção) ou pode selecionar essa opção para exportar os arquivos PDF que contêm as redação reais.

- **Opções de** saída : O conteúdo exportado está disponível para download diretamente por meio de um navegador da Web ou pode ser enviado para uma conta de Armazenamento do Azure. As duas primeiras opções habilitam o download direto.
  
  - **Arquivos soltos e PSTs (o email** é adicionado a PSTs quando possível) : Os arquivos são exportados em um formato que se parece com a estrutura de diretório original vista pelos usuários em seus aplicativos nativos.  Para obter mais informações, consulte a seção Arquivos Soltos e estrutura de [exportação PST.](#loose-files-and-pst-export-structure)
  
  - **Estrutura de diretório condensado**: Os arquivos são exportados e incluídos no download.
  
  - **Estrutura de diretório condensada exportada para** sua conta de Armazenamento do Azure : Os arquivos são exportados para a conta de Armazenamento do Azure da sua organização. Para essa opção, você precisa fornecer a URL do contêiner em sua conta de Armazenamento do Azure para exportar os arquivos. Você também precisa fornecer o token de assinatura de acesso compartilhado (SAS) para sua conta de Armazenamento do Azure. Para obter mais informações, [consulte Export documents in a review set to an Azure Storage account](download-export-jobs.md).

As seções a seguir descrevem a estrutura de pastas para arquivos soltos e opções de estrutura de diretório condensada.

### <a name="loose-files-and-pst-export-structure"></a>Arquivos soltos e estrutura de exportação PST

Se você selecionar essa opção de exportação, o conteúdo exportado será organizado na seguinte estrutura:

- Pasta raiz: esta pasta no nome ExportName.zip
  
  - Export_load_file.csv: o arquivo de metadados.
  
  - Summary.csv: um arquivo de resumo que também contém estatísticas de exportação.
  
  - Exchange: essa pasta contém todo o conteúdo do Exchange no formato de arquivo nativo. Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**
  
  - SharePoint: essa pasta contém todo o conteúdo nativo do SharePoint em um formato de arquivo nativo. Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos **redacted por PDFs convertidos.**

### <a name="condensed-directory-structure"></a>Estrutura de diretório condensado

- Pasta raiz: essa pasta é chamada ExportName.zip
  
  - Export_load_file.csv: o arquivo de metadados.
  
  - Summary.txt: um arquivo de resumo que também contém estatísticas de exportação.
  
  - NativeFiles: esta pasta contém todos os arquivos nativos que foram exportados. Se você exportar arquivos PDF editados, eles não serão colocados em arquivos PST. Em vez disso, eles são adicionados a uma pasta separada.
  
  - Error_files: esta pasta contém os seguintes arquivos de erro, se eles são incluídos na exportação:

    - ExtractionError: um arquivo CSV que contém todos os metadados disponíveis de arquivos que não foram extraídos corretamente dos arquivos pai.

    - ProcessingError: este arquivo contém uma lista de documentos com erros de processamento. Esse conteúdo é de nível de item, ou seja, se um anexo resultou em um erro de processamento, a mensagem de email que contém o anexo será incluída nessa pasta.
  
  - Extracted_text_files: esta pasta contém todos os arquivos de texto extraídos que foram gerados no processamento.
