---
title: Aumentar a velocidade de download ao exportar os resultados da pesquisa de descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: Saiba como configurar o registro do Windows para aumentar a taxa de transferência de dados ao baixar os resultados da pesquisa e dados de pesquisa do centro de conformidade e segurança & e descoberta eletrônica avançada.
ms.openlocfilehash: a5e08f2fe7d8840cfe8f176080c90b8b40d16af6
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943350"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results"></a>Aumentar a velocidade de download ao exportar os resultados da pesquisa de descoberta eletrônica

Ao usar a ferramenta de exportação de descoberta eletrônica para baixar os resultados de uma pesquisa de conteúdo no centro de conformidade do & de segurança ou baixar dados da descoberta eletrônica avançada, a ferramenta inicia um determinado número de operações de exportação simultâneas para baixar os dados para o computador local. Por padrão, o número de operações simultâneas é definido como 8 vezes o número de núcleos no computador que você está usando para baixar os dados. Por exemplo, se você tiver um computador dual core (ou seja, duas unidades de processamento central em um único chip), o número padrão de operações de exportação simultâneas será 16. Para aumentar a taxa de transferência e acelerar o processo de download, é possível aumentar o número de operações simultâneas Configurando uma configuração do registro do Windows no computador que você usa para baixar os resultados da pesquisa. Para acelerar o processo de download, recomendamos que você comece com uma configuração de 24 operações simultâneas.
  
Se você baixar os resultados da pesquisa por uma rede de baixa largura de banda, aumentar essa configuração poderá ter um impacto negativo. Como alternativa, é possível aumentar a configuração para mais de 24 operações simultâneas em uma rede de alta largura de banda (o número máximo de operações simultâneas é 48). Depois de definir essa configuração do registro, talvez seja necessário alterá-la para encontrar o número ideal de operações simultâneas para seu ambiente.
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>Criar uma configuração de registro para alterar o número de operações simultâneas ao exportar dados

Execute o procedimento a seguir no computador que você usará para baixar os resultados da pesquisa do centro de conformidade & segurança ou dos dados da descoberta eletrônica avançada.
  
1. Feche a ferramenta de exportação de descoberta eletrônica, se ela estiver aberta. 
    
2. Salve o seguinte texto em um arquivo de registro de janela usando um sufixo de nome de arquivo. reg; por exemplo, ConcurrentOperations. reg. 
    
    ```text
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    Como explicado anteriormente, recomendamos que você comece com 24 operações simultâneas e, em seguida, altere essa configuração conforme apropriado.
    
3. No Windows Explorer, clique ou clique duas vezes no arquivo. reg que você criou na etapa anterior.
    
4. Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração. 
    
5. Quando for solicitado a continuar, clique em **Sim**.
    
    O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.
    
6. Você pode repetir as etapas 2-5 para alterar o valor da `DownloadConcurrency` configuração do registro. 
    
    > [!IMPORTANT]
    > Após criar ou alterar a `DownloadConcurrency` configuração do registro, certifique-se de criar um novo trabalho de exportação ou reinicie um trabalho de exportação existente para os resultados de pesquisa ou os dados que você deseja baixar. Consulte a seção [mais informações](#more-information) para obter mais detalhes. 
  
## <a name="more-information"></a>Mais informações

- Uma nova chave de registro é criada na primeira vez que você executa o arquivo. reg que você criou neste procedimento. Em seguida `DownloadConcurrency` , a configuração do registro será editada sempre que você alterar e executar novamente o arquivo. reg Edit. 
    
- A ferramenta de exportação de descoberta eletrônica usa o [utilitário AzCopy do Azure](https://go.microsoft.com/fwlink/?linkid=849949) para baixar dados de pesquisa do centro de conformidade & segurança ou da descoberta eletrônica avançada. Definir a `DownloadConcurrency` configuração do registro é semelhante a usar o parâmetro **/NC** ao executar o utilitário AzCopy. Portanto, a configuração do `"DownloadConcurrency=24"` registro de teria o mesmo efeito que usar o valor do `/NC:24` parâmetro de com o utilitário AzCopy. 
    
- Se você parar um download de exportação que está em andamento e reiniciá-lo (tentando baixar os resultados da pesquisa novamente), a ferramenta de exportação de descoberta eletrônica tentará retomar o mesmo download. Portanto, se você iniciar um download, interrompa-o e, em seguida `DownloadConcurrency` , altere a configuração do registro, o download provavelmente falhará se você reiniciá-lo (clicando em **baixar resultados exportados**). Isso ocorre porque a ferramenta de exportação tentará retomar o download anterior usando configurações que não são válidas, pois você alterou a configuração do registro.
    
    Portanto, depois de alterar a `DownloadConcurrency` configuração do registro, certifique-se de reiniciar o trabalho de exportação (clicando em **reiniciar exportação**) no centro de conformidade de & de segurança. Em seguida, você pode baixar os resultados exportados. Para obter mais informações sobre como exportar dados e resultados de pesquisa, consulte:
    
  - [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)
    
  - [Exportar resultados na descoberta eletrônica avançada](export-results-in-advanced-ediscovery.md)
    
