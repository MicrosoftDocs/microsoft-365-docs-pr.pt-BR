---
title: Importar conteúdo não-Microsoft 365 para análise de descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.openlocfilehash: daafcf003ded35868413d99c11ec1bf3941dca9f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634153"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Importar conteúdo não-Microsoft 365 para análise de descoberta eletrônica avançada (clássico)

Nem todos os documentos que você pode precisar analisar com a descoberta eletrônica avançada residirão no Microsoft 365. Com o recurso de importação de conteúdo não-Microsoft 365 na descoberta eletrônica avançada, é possível carregar documentos que não estão no Microsoft 365 (exceto arquivos PST) em um caso vinculado, BLOB de armazenamento do Azure e analisá-los com a descoberta eletrônica avançada. Este procedimento mostra como trazer documentos que não são da Microsoft 365 para a descoberta eletrônica avançada para análise.
  
> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Você pode adquirir uma assinatura de complemento de armazenamento de dados de descoberta eletrônica avançada para seu conteúdo que não seja da Microsoft 365. Isso está disponível exclusivamente para conteúdo que deve ser analisado com a descoberta eletrônica avançada. Siga as etapas em [comprar ou editar um complemento para o Microsoft 365 for Business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) e adquirir o complemento avançado de armazenamento de descoberta eletrônica. 
  
## <a name="before-you-begin"></a>Antes de começar

O uso do recurso de upload que não é do Office 365 conforme descrito neste procedimento exige que você tenha:
  
- Um Office 365 E3 com um complemento de conformidade avançada ou uma assinatura e5
    
- Todos os responsáveis cujo conteúdo que não seja do Office 365 será carregado deverá ter E3 com o complemento avançado de conformidade ou licenças e5
    
- Uma ocorrência de descoberta eletrônica existente
    
- Todos os arquivos para carregamento são coletados em pastas onde há uma pasta por responsáveis e o nome das pastas está nesse formato *alias@domainname* . O *alias@domainname* deve ser Users alias e Domain do Office 365. Você pode coletar todas as pastas de *alias@domainname* em uma pasta raiz. A pasta raiz pode conter apenas as pastas *alias@domainname* , não deve haver arquivos soltos na pasta raiz 
    
- Uma conta que seja um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica
    
- [Ferramentas de armazenamento do Microsoft Azure](https://aka.ms/downloadazcopy) instaladas em um computador que tem acesso à estrutura de pasta de conteúdo não-Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Carregar conteúdo que não seja do Office 365 na descoberta eletrônica avançada


1. Como um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica, abra o **eDiscovery**e abra o caso em que os dados não-Office 365 serão carregados. Se você precisar criar uma ocorrência, consulte [gerenciar casos de descoberta eletrônica no centro &amp; de conformidade de segurança](ediscovery-cases.md)
    
2. Clique em **alternar para descoberta eletrônica avançada**
    
3. Em **tipo de origem** , selecione **dados não-Office 365**.
    
4. Clique em **Adicionar contêiner**. Nomeie o contêiner e adicione uma descrição.
    
5. Selecione o contêiner recém-adicionado na lista de contêineres e copie a URL que aparece no painel de detalhes do contêiner e, em seguida, feche o painel
    
6. Abra um prompt de comando como administrador e altere o diretório para a pasta em que você tem o AzCopy instalado..
    
7. Construa a linha de comando AzCopy para carregar os arquivos da seguinte maneira:
    
    AzCopy/Source: " *caminho completo para a pasta raiz na máquina local* "/dest: " *URL do contêiner até mas não incluindo o?*  "/DestSAS:" *restante da URL do contêiner do? ao final* "/S. 
    
    Por exemplo, usando estes valores: 
    
  - pasta raiz-dados de C:\Collected 
    
  - URL do contêiner https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp-; Sr =&amp;c si = NonOfficeData15%&amp;7C0 SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D
    
    a sintaxe da linha de comando do AzCopy seria:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Para obter mais informações sobre a sintaxe do Azcopy, consulte [transferir dados com o Azcopy no Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Deve haver uma pasta raiz por usuário e o nome da pasta deve estar no formato *alias@domainname* . 
  
8. Depois que as pastas terminarem o carregamento, volte para a descoberta eletrônica avançada. O conteúdo das pastas carregadas agora está pronto para ser processado na descoberta eletrônica avançada. Selecione o contêiner e clique no botão processo. Para obter mais detalhes sobre o processamento de descoberta eletrônica avançado, confira [executar o módulo de processo e carregar dados na descoberta eletrônica avançada](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > Depois que o contêiner for processado com êxito na descoberta eletrônica avançada, você não poderá mais adicionar novo conteúdo ao armazenamento SAS no Azure. Se você coletar conteúdo adicional e quiser adicioná-lo ao caso da análise de descoberta eletrônica avançada, você deve criar um novo contêiner de **dados que não seja do Office 365** e repetir este procedimento. 
  
    > [!NOTE]
    > Se o contêiner *não for processado com êxito devido a problemas de nomenclatura de pasta* e você corrigir os problemas, ainda será necessário criar um novo contêiner e reconectar e carregar novamente usando os procedimentos deste artigo.
