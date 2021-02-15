---
title: Baixar trabalhos de exportação para um caso de Descoberta Descoberta Avançada
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
ROBOTS: NOINDEX, NOFOLLOW
ms.custom: seo-marvel-mar2020
description: Instale e use o Azure Storage Explorer para baixar documentos que foram exportados de um conjunto de revisão no Advanced eDiscovery.
ms.openlocfilehash: 094dcb4ecc8b1ca73a7ec0238ed20b27d4c16e72
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751288"
---
# <a name="download-export-jobs-in-an-advanced-ediscovery-case"></a>Baixar trabalhos de exportação em um caso de Descoberta Avançada

Quando você exporta documentos de um conjunto de revisão em um caso de Descoberta Avançada, os documentos são carregados para um local de Armazenamento do Azure fornecido pela Microsoft ou para um local de Armazenamento do Azure gerenciado pela sua organização. O tipo de local de armazenamento do Azure usado depende de qual opção foi selecionada quando os documentos foram exportados.

Este artigo fornece instruções sobre como usar o Microsoft Azure Storage Explorer para se conectar a um local de armazenamento do Azure para procurar e baixar os documentos exportados. Para obter mais informações sobre o Azure Storage Explorer, consulte [Guia de início rápido: Use o Azure Storage Explorer.](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer)

## <a name="step-1-install-the-azure-storage-explorer"></a>Etapa 1: Instalar o Azure Storage Explorer

A primeira etapa é baixar e instalar o Azure Storage Explorer. Para obter instruções, confira [a ferramenta Do Azure Storage Explorer.](https://go.microsoft.com/fwlink/p/?LinkId=544842) Use essa ferramenta para se conectar e baixar os documentos exportados na Etapa 3.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Etapa 2: Obter a URL SAS do trabalho de exportação

A próxima etapa é obter a URL de assinatura de acesso compartilhado (SAS) gerada quando você criou o trabalho de exportação para exportar documentos de um conjunto [de revisão.](export-documents-from-review-set.md) Você pode copiar a URL do SAS para documentos carregados em um local de Armazenamento do Azure fornecido pela Microsoft ou em um local de Armazenamento do Azure gerenciado pela sua organização. Em ambos os casos, use a URL SAS para se conectar ao local de armazenamento do Azure na Etapa 3.

1. Na página **Descobertas Avançadas,** vá para a ocorrência e clique na **guia** Exportações.

2. Na guia **Exportações,** clique no trabalho de exportação que você deseja baixar.

3. On the flyout page, under **Locations**, copy the SAS URL that's displayed. Se necessário, você pode salvá-lo em um arquivo para poder acessá-lo na Etapa 3.
 
   ![Copiar a URL SAS exibida em Locais](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>Etapa 3: Conectar-se ao local de armazenamento do Azure

A etapa final é usar o Explorador de Armazenamento do Azure e a URL SAS para se conectar ao local de armazenamento do Azure e baixar os documentos que você exportou para um computador local.

1. Abra o Azure Storage Explorer que você instalou na Etapa 1.

2. Clique no **ícone Adicionar** conta. Como alternativa, você pode clicar com o botão direito do mouse **em Contas de Armazenamento.**

   ![Clique no ícone Adicionar conta](../media/AzureStorageConnect.png)

3. Na página **Conectar-se ao Armazenamento do Azure,** clique em Usar um URI de assinatura de acesso **compartilhado (SAS)** e clique em **Próximo.**

    ![Clique em Usar um URI de assinatura de acesso compartilhado (SAS) e clique em Próximo](../media/AzureStorageConnect2.png)

4. Na página **Anexar com URI SAS,** clique na caixa URI e, em seguida, colar a URL SAS obtida na Etapa 2. 

    ![Colar a URL SAS na caixa URI](../media/AzureStorageConnect3.png)

    Observe que uma parte da URL SAS é exibida na caixa **Nome de** exibição. Isso será usado como o nome de exibição do contêiner criado sob as contas **de** Armazenamento depois que você se conectar ao local de armazenamento. Esse nome consiste na ID da ocorrência da Descoberta Avançada e em um identificador exclusivo. Você pode manter o nome de exibição padrão ou alterá-lo. Se você alterá-lo, o nome de exibição deverá ser exclusivo.

5. Clique em **Avançar**.

    A **página de resumo** de conexão é exibida.

    ![Clique em Conectar na página de resumo de conexão para se conectar ao local de armazenamento do Azure](../media/AzureStorageConnect4.png)

6. Na página **Resumo da** conexão, revise as informações de conexão e clique em **Conectar.**

    O **nó de contêineres de Blob** (em **Contas de Armazenamento**  >  **(Contêineres Anexados)** \> é aberto.

    ![Exportar trabalhos no nó de contêineres de Blobs](../media/AzureStorageConnect5.png)

    Ele contém um contêiner nomeado com o nome de exibição da etapa 4. Esse contêiner contém uma pasta para cada trabalho de exportação que você criou. Essas pastas são nomeadas com uma ID que corresponde à ID do trabalho de exportação. Você pode encontrar essas IDs de exportação (e o nome da exportação) em Informações de suporte na página do sub80 para cada preparação de dados para o trabalho de exportação listado na guia **Trabalhos.**  

7. Clique duas vezes na pasta de trabalho de exportação para abri-la.

   Uma lista de pastas e relatórios de exportação é exibida.
   
    ![A pasta de exportação contém arquivos exportados e relatórios de exportação](../media/AzureStorageConnect6.png)

   A pasta de trabalho de exportação contém os itens a seguir. Os itens reais na pasta de exportação são determinados pelas opções de exportação configuradas quando o trabalho de exportação foi criado. Para obter mais informações, [consulte Exportar documentos de um conjunto de revisão.](export-documents-from-review-set.md)

    - Export_load_file.csv: esse arquivo CSV é um relatório de exportação detalhado que contém informações sobre cada documento exportado. O arquivo consiste em uma coluna para cada propriedade de metadados de um documento. Para uma lista e uma descrição dos metadados  incluídos neste relatório, consulte a coluna Nome do campo exportado na tabela nos campos de metadados do documento na [Descoberta eDiscovery Avançada.](document-metadata-fields-in-advanced-ediscovery.md)
    
    - Summary.txt: um arquivo de texto que contém um resumo da exportação, incluindo estatísticas de exportação.
    
    - Extracted_text_files: essa pasta contém uma versão de arquivo de texto de cada documento exportado.
     
    - NativeFiles: essa pasta contém uma versão de arquivo nativa de cada documento exportado.
    
    - Error_files: essa pasta inclui os seguintes itens quando o trabalho de exportação contém arquivos de erro: 
        
      - ExtractionError.csv: esse arquivo CSV contém os metadados disponíveis para arquivos que não foram extraídos corretamente do item pai.
        
      - ProcessingError: Esta pasta contém documentos com erros de processamento. Esse conteúdo está em um nível de item, o que significa que se um anexo tiver um erro de processamento, o documento que contém o anexo também será incluído nessa pasta.
 
8. Para exportar todo o conteúdo na exportação, selecione a pasta de exportação e clique em **Baixar.**

9. Especifique o local onde você deseja baixar os arquivos exportados e clique em Selecionar pasta.

    O Explorador de Armazenamento do Azure inicia o processo de exportação. O status do download dos itens exportados é exibido no **painel** Atividades. Uma mensagem é exibida quando o download é concluído.

    ![Uma mensagem é exibida quando o download é concluído](../media/AzureStorageConnect8.png)

> [!NOTE]
> Em vez de baixar todo o trabalho de exportação, você pode selecionar itens específicos para baixar. E, em vez de baixar itens, você pode clicar duas vezes em um item para exibi-lo.
