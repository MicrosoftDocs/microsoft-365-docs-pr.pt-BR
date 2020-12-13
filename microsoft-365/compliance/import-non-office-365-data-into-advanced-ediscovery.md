---
title: Importar conteúdo não-Microsoft 365 para análise de descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Como as etapas para importar o conteúdo que não está armazenado no Microsoft 365 em um blob do Azure para que ele possa ser analisado com o AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662896"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Importar conteúdo não-Microsoft 365 para análise de descoberta eletrônica avançada (clássico)

Nem todos os documentos que você pode precisar analisar com a descoberta eletrônica avançada residirão no Microsoft 365. Com o recurso de importação de conteúdo não-Microsoft 365 na descoberta eletrônica avançada, é possível carregar documentos que não estão no Microsoft 365 (exceto arquivos PST) em um caso vinculado, BLOB de armazenamento do Azure e analisá-los com a descoberta eletrônica avançada. Este procedimento mostra como trazer documentos que não são da Microsoft 365 para a descoberta eletrônica avançada para análise.
  
> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Você pode adquirir uma assinatura de complemento de armazenamento de dados de descoberta eletrônica avançada para seu conteúdo que não seja da Microsoft 365. Isso está disponível exclusivamente para conteúdo que deve ser analisado com a descoberta eletrônica avançada. Siga as etapas em [comprar ou editar um complemento para o Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) e adquirir o complemento avançado de armazenamento de descoberta eletrônica. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Requisitos para carregar conteúdo não-Office 365

O uso do recurso de upload que não é do Office 365 conforme descrito neste procedimento exige que você tenha:
  
- Um Office 365 E3 com um complemento de conformidade avançada ou uma assinatura e5.
    
- Todos os responsáveis cujo conteúdo que não seja do Office 365 será carregado precisarão ter E3 com o complemento de conformidade avançada ou com licenças e5.
    
- Uma ocorrência de descoberta eletrônica existente.
    
- Todos os arquivos para carregamento são coletados em pastas onde há uma pasta por responsáveis e o nome das pastas está nesse formato  *alias@domainname*  . O  *alias@domainname*  deve ser Users alias e Domain do Office 365. Você pode coletar todas as pastas de  *alias@domainname*  em uma pasta raiz. A pasta raiz pode conter apenas as pastas  *alias@domainname*  , não deve haver arquivos soltos na pasta raiz.
    
- Uma conta que seja um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica.
    
- [Ferramentas de armazenamento do Microsoft Azure](https://aka.ms/downloadazcopy) instaladas em um computador que tem acesso à estrutura de pasta de conteúdo não-Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Carregar conteúdo que não seja do Office 365 na descoberta eletrônica avançada


1. Como um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica, abra o **eDiscovery** e abra o caso em que os dados não-Office 365 serão carregados. Se você precisar criar uma ocorrência, consulte [gerenciar casos de descoberta eletrônica no &amp; centro de conformidade de segurança](ediscovery-cases.md).
    
2. Clique em **alternar para descoberta eletrônica avançada**.

3. Selecione **conjuntos de revisão** no menu.

4. Selecione um conjunto de revisão existente ou escolha **Adicionar conjunto de revisão**.

5. Selecione **gerenciar conjunto de revisão**.

6. No cartão de dados não-Office 365, selecione **Exibir uploads**.

7. Escolha **carregar arquivos** para iniciar o assistente de carregamento de arquivos.

8. A primeira guia é **1. Preparar etapa**. Selecione **Avançar: carregar arquivos**.

9. No **2. Guia carregar arquivos** você será solicitado a baixar AzCopy.exe se ainda não tiver feito isso e, em seguida, fornecer o caminho para o local do arquivo. Por exemplo, fornecerá `C:\Upload`  o comando para executar AzCopy.exe. Usando o `C:\Upload` , você verá:

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. Abra uma janela de prompt de comando e execute o comando AzCopy.exe para importar os dados para o Azure. Depois de carregar todos os dados, selecione **Avançar: processar arquivos**.

11. A próxima guia é **3. Processe arquivos** em que você verá os responsáveis que têm dados associados a eles e também mostrará o progresso dos dados que estão sendo importados.
        
    Para obter mais informações sobre a sintaxe Azcopy, consulte [transferir dados com o Azcopy no Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy). 
    
    Para obter mais detalhes sobre o processamento avançado de descoberta eletrônica, consulte [executar o módulo de processo e carregar dados na descoberta eletrônica avançada (clássico)](run-the-process-module-and-load-data-in-advanced-ediscovery.md). 
    
    > [!IMPORTANT]
    > Deve haver uma pasta raiz por usuário e o nome da pasta deve estar no formato <b>alias@domainname</b>  . 
   
    > [!IMPORTANT]
    > Depois que o contêiner for processado com êxito na descoberta eletrônica avançada, você não poderá mais adicionar novo conteúdo ao armazenamento SAS no Azure. Se você coletar conteúdo adicional e quiser adicioná-lo ao caso da análise de descoberta eletrônica avançada, você deve criar um novo contêiner de **dados que não seja do Office 365** e repetir este procedimento. 
  
    > [!NOTE]
    > Se o contêiner  *não for processado com êxito devido a problemas de nomenclatura de pasta*  e você corrigir os problemas, ainda será necessário criar um novo contêiner e reconectar e carregar novamente usando os procedimentos deste artigo.
