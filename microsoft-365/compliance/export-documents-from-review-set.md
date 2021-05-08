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
description: Saiba como selecionar e exportar conteúdo de um conjunto de Advanced eDiscovery para apresentações ou avaliações externas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 76865ae92d3b3090ae2bba01c9b3e9e0f1f86366
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244351"
---
# <a name="export-documents-from-a-review-set-in-advanced-ediscovery"></a>Exportar documentos de um conjunto de revisão em Advanced eDiscovery

Exportar permite que os usuários personalizem o conteúdo incluído no pacote de download quando você exporta documento de um conjunto de revisão em Advanced eDiscovery.

Para exportar documentos de um conjunto de revisão:

1. No centro Microsoft 365 de conformidade, abra o caso Advanced eDiscovery, selecione a guia Revisar conjuntos e selecione o conjunto de revisão que você deseja exportar. 

2. No conjunto de revisão, clique em **Ação**  >  **Exportar**.

   A ferramenta Exportar exibe a página de sobrevoo com as configurações para configurar a exportação. Algumas opções são selecionadas por padrão, mas você pode alterá-los. Consulte a seção a seguir para ver descrições das opções de exportação que você pode configurar.

   ![Opções de configuração para exportar itens de um conjunto de revisão](../media/bcfc72c7-4a01-4697-9e16-2965b7f04fdb.png)

3. Depois de configurar a exportação, clique em **Exportar** para iniciar o processo de exportação. Dependendo da opção selecionada  na seção Opções de saída, você pode acessar os arquivos de exportação por download direto ou na conta do Azure Armazenamento da sua organização.

> [!NOTE]
> Os trabalhos de exportação são mantidos durante a vida útil do caso. No entanto, você deve baixar o conteúdo de um trabalho de exportação dentro de 30 dias após a conclusão do trabalho de exportação.

## <a name="export-options"></a>Opções de exportação

Use as opções a seguir para configurar a exportação. Nem todas as opções são permitidas para algumas opções de saída, mais notadamente, a exportação de arquivos de texto e PDFs redacted não são permitidas ao exportar para o formato PST.

- **Nome da** exportação : nome do trabalho de exportação. Isso será usado para nomear os arquivos ZIP que serão baixados.

- **Descrição**: campo de texto livre para você adicionar uma descrição.

- **Exportar esses documentos**

  - Somente documentos selecionados: essa opção exporta apenas os documentos selecionados no momento. Essa opção só estará disponível quando os itens forem selecionados em um conjunto de revisão.
  - Todos os documentos filtrados: essa opção exporta os documentos em um filtro ativo. Essa opção só estará disponível quando um filtro for aplicado ao conjunto de revisão.
  - Todos os documentos no conjunto de revisão: Essa opção exporta todos os documentos no conjunto de revisão.

- **Opções de** saída : O conteúdo exportado está disponível para download diretamente por meio de um navegador da Web ou pode ser enviado para uma conta do Azure Armazenamento. As duas primeiras opções habilitam o download direto.
  
  - Somente relatórios: somente o arquivo de resumo e carga são criados.
  - Arquivos soltos e PSTs (o email é adicionado a PSTs quando possível): Os arquivos são exportados em um formato que se parece com a estrutura de diretório original vista pelos usuários em seus aplicativos nativos.  Para obter mais informações, consulte a seção Arquivos Soltos e estrutura de [exportação PST.](#loose-files-and-pst-export-structure)
  - Estrutura de diretório condensado: Os arquivos são exportados e incluídos no download.
  - Estrutura de diretório condensada exportada para sua conta do Azure Armazenamento: Os arquivos são exportados para a conta de Armazenamento do Azure da sua organização. Para essa opção, você precisa fornecer a URL do contêiner em sua conta do Azure Armazenamento exportar os arquivos para. Você também precisa fornecer o token de assinatura de acesso compartilhado (SAS) para sua conta do Azure Armazenamento. Para obter mais informações, [consulte Export documents in a review set to an Azure Armazenamento account](download-export-jobs.md).

- **Include**
  - Marcas: Quando selecionadas, as informações de marcação são incluídas no arquivo de carga.
  - Arquivos de texto: essa opção inclui as versões de texto extraídas de arquivos nativos na exportação.
  - Substitua os nativos redacted por PDFs convertidos: se os arquivos PDF redacted são gerados durante a revisão, esses arquivos estarão disponíveis para exportação. Você pode optar por exportar apenas os arquivos nativos que foram editados (não selecionando essa opção) ou pode selecionar essa opção para exportar os arquivos PDF que contêm as redação reais.

## <a name="the-following-sections-describe-the-folder-structure-for-loose-files-and-condensed-directory-structure-options"></a>As seções a seguir descrevem a estrutura de pastas para arquivos soltos e opções de estrutura de diretório condensada

As exportações são particionadas em arquivos ZIP com um tamanho máximo de conteúdo não compactado de 75 GB. Se o tamanho de exportação for menor que 75 GB, a exportação consistirá em um arquivo de resumo e um único arquivo ZIP. Para exportações superiores a 75 GB de dados não compactados, vários arquivos ZIP serão criados. Depois de baixados, os arquivos ZIP podem ser descompactados em um único local para recriar a exportação completa.

### <a name="loose-files-and-pst-export-structure"></a>Arquivos soltos e estrutura de exportação PST

Se você selecionar essa opção de exportação, o conteúdo exportado será organizado na seguinte estrutura:

- Summary.csv: inclui um resumo do conteúdo exportado do conjunto de revisão
- Pasta raiz: essa pasta em nome de [Nome de Exportação] x de z.zip e será repetida para cada partição de arquivo ZIP.
  - Export_load_file_x de z.csv: o arquivo de metadados.
  - Avisos e erros x de z.csv: este arquivo inclui informações sobre erros encontrados ao tentar exportar do conjunto de revisão.
  - Exchange: essa pasta contém todo o conteúdo Exchange armazenado em arquivos PST. Arquivos PDF redacted não podem ser incluídos com essa opção. Se um anexo estiver selecionado no conjunto de revisão, o email pai será exportado com o anexo anexado.
  - SharePoint: essa pasta contém todo o conteúdo nativo SharePoint em um formato de arquivo nativo. Arquivos PDF redacted não podem ser incluídos com essa opção.

### <a name="condensed-directory-structure"></a>Estrutura de diretório condensado

- Summary.csv: inclui um resumo do conteúdo exportado do conjunto de revisão
- Pasta raiz: essa pasta em nome de [Nome de Exportação] x de z.zip e será repetida para cada partição de arquivo ZIP.
  - Export_load_file_x de z.csv: o arquivo de metadados e também inclui o local de cada arquivo armazenado no arquivo ZIP.
  - Avisos e erros x de z.csv: este arquivo inclui informações sobre erros encontrados ao tentar exportar do conjunto de revisão.
  - NativeFiles: esta pasta contém todos os arquivos nativos que foram exportados. Os arquivos nativos serão substituídos por PDFs redacionados se você tiver selecionado a opção Substituir nativos *redacted por PDFs convertidos.*
  - Error_files: esta pasta contém arquivos que tiveram extração ou outro erro de processamento. Os arquivos serão colocados em pastas separadas, extractionError ou ProcessingError. Esses arquivos estão listados no arquivo de carga.
  - Extracted_text_files: esta pasta contém todos os arquivos de texto extraídos que foram gerados no processamento.

### <a name="condensed-directory-structure-exported-to-your-azure-storage-account"></a>Estrutura de diretório condensada exportada para sua conta do Azure Armazenamento

Essa opção usa a mesma estrutura geral que a estrutura de diretório condensado *,* no entanto, o conteúdo não é zipped e os dados são salvos em sua conta do Azure Armazenamento. Essa opção geralmente é usada ao trabalhar com um provedor de Descoberta eDiscovery de terceiros. Para obter detalhes sobre como usar essa opção, consulte [Export documents in a review set to an Azure Armazenamento account](download-export-jobs.md).
