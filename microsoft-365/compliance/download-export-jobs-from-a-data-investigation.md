---
title: Baixar trabalhos de exportação para uma investigação
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
description: Instale e use o Azure Storage Explorer para baixar documentos que foram exportados de evidências em uma investigação de dados.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b9f3ee173fd9068f459e10b95fd497b7cf5015fc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035683"
---
# <a name="download-export-jobs"></a>Baixar trabalhos de exportação

Quando você exporta documentos de evidências em uma investigação de dados, os documentos são carregados em um local de armazenamento do Azure fornecido pela Microsoft ou em um local de armazenamento do Azure gerenciado por sua organização. O tipo de local de armazenamento do Azure usado depende de qual opção foi selecionada quando os documentos foram exportados. 

Este artigo fornece instruções sobre como usar o Microsoft Azure Storage Explorer para se conectar a um local de armazenamento do Azure para navegar e baixar os documentos exportados. Para obter mais informações sobre o Azure Storage Explorer, consulte [QuickStart: Use Azure Storage Explorer](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-storage-explorer).

## <a name="step-1-install-the-azure-storage-explorer"></a>Etapa 1: instalar o Azure Storage Explorer

A primeira etapa é baixar e instalar o Gerenciador de armazenamento do Azure. Para obter instruções, consulte [Azure Storage Explorer Tool](https://go.microsoft.com/fwlink/p/?LinkId=544842). Use essa ferramenta para se conectar e baixar os documentos exportados na etapa 3.

## <a name="step-2-obtain-the-sas-url-from-the-export-job"></a>Etapa 2: obter a URL SAS do trabalho de exportação

A próxima etapa é obter a URL de assinatura de acesso compartilhado (SAS) gerada quando você criou o trabalho de exportação para [exportar documentos de um conjunto de revisão](export-documents-from-review-set.md). Você pode copiar a URL SAS para documentos que são carregados para um local de armazenamento do Azure fornecido pela Microsoft ou um local de armazenamento do Azure gerenciado por sua organização. Em ambos os casos, você usa a URL SAS para se conectar ao local de armazenamento do Azure na etapa 3.

1. Na página **investigações de dados** , vá para a investigação e clique na guia **exportações** .

2. Na guia **exportações** , clique no trabalho de exportação que você deseja baixar.

3. Na página do menu suspenso, em **locais**, copie a URL SAS que é exibida. Se necessário, você pode salvá-lo em um arquivo para que possa acessá-lo na etapa 3.
 
   ![Copiar a URL SAS exibida em locais](../media/eDiscoExportJob.png)

## <a name="step-3-connect-to-the-azure-storage-location"></a>Etapa 3: conectar-se ao local de armazenamento do Azure

A etapa final é usar o Gerenciador de armazenamento do Azure e a URL SAS para se conectar ao local de armazenamento do Azure e baixar os documentos que você exportou para um computador local.

1.  Abra o Azure Storage Explorer que você instalou na etapa 1.

2. Clique no ícone **adicionar conta** . Como alternativa, você pode clicar com o botão direito do mouse em **contas de armazenamento**.

   ![Clique no ícone Adicionar conta](../media/AzureStorageConnect.png)

3.  Na página **conectar ao Azure Storage** , clique em **usar um URI de assinatura de acesso compartilhado (SAS)** e, em seguida, clique em **Avançar**.

    ![Clique em usar um URI de assinatura de acesso compartilhado (SAS) e clique em avançar](../media/AzureStorageConnect2.png)

4.  Na página **anexar com URI SAS** , clique na caixa URI e cole a URL SAS obtida na etapa 2. 

    ![Colar a URL SAS na caixa URI](../media/AzureStorageConnect3.png)

    Observe que uma parte da URL SAS é exibida na caixa **nome para exibição** . Ele será usado como o nome de exibição do contêiner que é criado nas contas de **armazenamento** depois que você se conecta ao local de armazenamento. Esse nome consiste na identificação da investigação dos dados e em um identificador exclusivo. Você pode manter o nome de exibição padrão ou alterá-lo. Se você alterá-lo, o nome para exibição deverá ser exclusivo.

5.  Clique em **Avançar**.

    A página de **Resumo de conexão** é exibida.
   
    ![Clique em conectar na página Resumo de conexão para se conectar ao local de armazenamento do Azure](../media/AzureStorageConnect4.png)

6. Na página **Resumo da conexão** , revise as informações de conexão e clique em **conectar**. 

    O **nó contêineres blob** (em **contas** > **de armazenamento (contêineres anexados)** \> é aberto. 

    ![Exportar trabalhos no nó contêineres de BLOBs](../media/AzureStorageConnect5.png)

    Ele contém um contêiner nomeado com o nome de exibição da etapa 4. Este contêiner contém uma pasta para cada trabalho de exportação que você criou. Essas pastas são nomeadas com uma ID que corresponde à ID do trabalho de exportação. Você pode encontrar essas IDs de exportação (e o nome da exportação) em **informações de suporte** na página de menu para cada um dos **dados de preparação do trabalho de exportação** listados na guia **trabalhos** .

7. Clique duas vezes na pasta de trabalho de exportação para abri-la.

   Uma lista de pastas e relatórios de exportação é exibida.
   
    ![A pasta de exportação contém arquivos exportados e relatórios de exportação](../media/AzureStorageConnect6.png)

   A pasta de trabalho de exportação contém os itens a seguir. Os itens reais na pasta de exportação são determinados pelas opções de exportação configuradas quando o trabalho de exportação foi criado. Para obter mais informações, consulte [exportar documentos de um conjunto de revisão](export-documents-from-review-set.md).

    - Export_load_file. csv: este arquivo CSV é um relatório de exportação de detalhes que contém informações sobre cada documento exportado. O arquivo consiste em uma coluna para cada propriedade de metadados de um documento. Para obter uma lista e uma descrição dos metadados incluídos neste relatório, confira a coluna **nome do campo exportado** na tabela em [campos de metadados do documento na descoberta eletrônica avançada](document-metadata-fields.md).
    
    - Summary. txt: um arquivo de texto que contém um resumo da exportação, incluindo as estatísticas de exportação.
    
    - Extracted_text_files: esta pasta contém uma versão de arquivo de texto de cada documento exportado.
     
    - NativeFiles: esta pasta contém uma versão de arquivo nativo de cada documento exportado.
    
    - Error_files: esta pasta inclui os seguintes itens quando o trabalho de exportação contém qualquer arquivo de erro: 
        
      - ExtractionError. csv: este arquivo CSV contém os metadados disponíveis para arquivos que não foram extraídos corretamente de seu item pai.
        
      - ProcessingError: esta pasta contém documentos com erros de processamento. Esse conteúdo está em um nível de item, o que significa que, se um anexo tiver um erro de processamento, o documento que contém o anexo também será incluído nessa pasta.
 
8. Para exportar todo o conteúdo da exportação, selecione a pasta exportar e clique em **baixar**.

9. Especifique o local onde você deseja baixar os arquivos exportados e clique em **Selecionar pasta**.

    O explorador de armazenamento do Azure inicia o processo de exportação. O status do download dos itens exportados é exibido no painel de **atividades** . Uma mensagem é exibida quando o download é concluído.

    ![Uma mensagem é exibida quando o download é concluído](../media/AzureStorageConnect8.png)

> [!NOTE]
> Em vez de baixar todo o trabalho de exportação, você pode selecionar itens específicos para baixar. E, em vez de baixar itens, você pode clicar duas vezes em um item para exibi-lo.

