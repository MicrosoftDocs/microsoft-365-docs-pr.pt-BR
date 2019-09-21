---
title: Exibir resultados de análise na descoberta eletrônica avançada do Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 'Entenda onde exibir os resultados do processo de análise na descoberta eletrônica avançada do Office 365, incluindo as definições das opções de tarefa exibidas.  '
ms.openlocfilehash: 092daa506316b5eb1ef1f5c466055b29e350dc18
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073309"
---
# <a name="view-analyze-results-in-office-365-advanced-ediscovery"></a>Exibir resultados de análise na descoberta eletrônica avançada do Office 365

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Na descoberta eletrônica avançada, o andamento e os resultados do processo de análise podem ser exibidos em uma variedade de exibições, conforme descrito abaixo.
  
## <a name="view-analyze-task-status"></a>Exibir o status da tarefa de análise

Em **preparar \> o \> status \> da tarefa de análise de resultados**, o status é exibido durante e após analisar a execução do processo. 
  
![Status de tarefa de análise](media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
As tarefas exibidas podem variar dependendo das opções selecionadas. 
  
- **ND/et: configuração**: prepara para a execução, por exemplo, define os parâmetros Run e case.
    
- **ND/et: o cálculo**: processa a análise quase duplicada de arquivos.
    
- **ND/et: et cálculo**: realiza análise de thread de email em todo o conjunto de emails.
    
- **ND/et: pivôs e semelhanças**: realiza o processamento dinâmico e de similaridade de arquivos.
    
- **ND/et: atualização de metadados**: finaliza os novos dados coletados nos arquivos do banco de dados.
    
- **Temas: cálculo de temas**: executa a análise de temas. (Exibido somente se selecionado).
    
- **Status da tarefa**: essa linha é exibida após a conclusão da tarefa. Enquanto as tarefas estão em execução, a duração da execução é exibida.
    
> [!NOTE]
> Os resultados da análise de quase duplicatas e threads de email (ND e ED) se aplicam ao número de documentos a serem processados. Ele não inclui arquivos duplicados exatos. 
  
## <a name="view-near-duplicates-and-email-threads-status"></a>Exibir o status de duplicidades e threads de email

Os resultados da população de **destino** exibem o número de documentos, emails, anexos e erros na população de destino. 
  
Os resultados dos **documentos** exibem o número de pivôs, únicos duplicatas ou arquivos duplicados exatos. 
  
Os resultados da mensagem de **email** exibem o número de cópias inclusivas, incluindo menos, inclusive, e o restante das mensagens de email. Os diferentes tipos de resultados de email são: 
  
- **Inclusive**: um email inclusivo é o nó de terminação em um thread de email e contém todos os históricos anteriores desse thread. Como resultado, o revisor pode focalizar com segurança o email inclusivo, sem a necessidade de ler as mensagens anteriores no thread. 
    
- **Inclusive menos**: um email inclusivo é designado como incluindo menos, se houver um ou mais anexos diferentes associados aos pais da mensagem inclusiva. Neste contexto, o termo pai é usado para mensagens localizadas no final do thread de email ou conversas incluídas nesse email inclusivo específico. Um revisor pode usar a indicação de menos, incluindo um sinal que, embora talvez não seja necessário revisar o conteúdo dos pais de email inclusivos, pode ser útil revisar os anexos associados aos pais de caminho inclusivos. 
    
- **Cópia inclusiva**: um email inclusivo é designado como uma cópia inclusiva, se for a cópia de outra mensagem marcada como inclusiva ou inclusive menos. Em outras palavras, esta mensagem tem o mesmo assunto e corpo de outra mensagem inclusiva e, como tal, reside no mesmo nó. Como as mensagens de cópia inclusiva contêm o mesmo conteúdo, elas normalmente podem ser ignoradas no processo de revisão. 
    
- **O restante**: indica email que não contém conteúdo exclusivo e, portanto, não se enquadram em nenhuma das três categorias anteriores. Essas mensagens de email não precisam ser revisadas. Se uma mensagem contiver um anexo que não esteja em um email inclusive mais recente, talvez seja necessário revisar o anexo. Isso é indicado pela existência de um email inclusive menos um dentro do thread.
    
Os resultados de **anexos** exibem o número de anexos, de acordo com esse tipo como exclusivo e duplicado. 
  
![Quase duplicatas e threads de email](media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre a similaridade de documentos](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configuração das opções de análise](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuração ignorar texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Configuração analisar configurações avançadas](view-analyze-results-in-advanced-ediscovery.md)

