---
title: Exibir resultados do módulo de processo na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c6f016cb-409f-4ae9-911c-1395cf0c86ea
description: Saiba mais sobre como localizar os resultados de um módulo de processo executado na descoberta eletrônica avançada, incluindo o status da tarefa e o resumo do processo.
ms.openlocfilehash: 73699d77e305055f6c2dc444fff00fb714b458cd
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663251"
---
# <a name="view-process-module-results-in-advanced-ediscovery-classic"></a>Exibir resultados do módulo de processo na descoberta eletrônica avançada (clássico)

Depois  \> que o **processo** de preparação é iniciado, você pode exibir o progresso e os resultados. 
  
> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="process-task-status"></a>Status da tarefa de processo

Nos resultados do processo de **preparação** \>  \> , a página mostra o status atual (se o processo estiver em execução no momento) ou o status da tarefa de status do último processo, conforme mostrado no exemplo a seguir.
  
![Status da tarefa do módulo de processamento](../media/9430f9e7-a4dd-47c7-ac2e-2c6a60fc948b.png)
  
As tarefas exibidas podem variar dependendo das opções de processo selecionadas. 
  
- **Inventory**: a descoberta eletrônica avançada repete todos os arquivos selecionados para o processo e executa uma coleção de dados básica.
    
- **Calculate Signatures**: calcula as assinaturas digitais MD5.
    
- **Extração de compostos**: extrai arquivos internos ou contidos recursivamente de arquivos compostos (por exemplo, PST, zip, msg). Os arquivos extraídos são armazenados na pasta de casos do caso.
    
- **Sincronizando banco de dados**: processo de banco de dados interno.
    
- **Cópia de arquivo**: copia arquivos de processo. Essa tarefa sempre é exibida, mesmo quando a opção de cópia avançada de arquivos está selecionada.
    
- **Extração de texto**: quando há arquivos nativos, a descoberta eletrônica avançada extrai o texto desses arquivos usando o DTSearch. O texto extraído desses arquivos é armazenado como arquivos de texto na pasta de caso.
    
- **Atualizando metadados**: processa os metadados carregados. 
    
- **Finalizando**: o processamento interno que finaliza os dados de arquivos de caso carregados (por exemplo, identificar arquivos de erro e de êxito). 
    
Status da tarefa: exibido após a conclusão da tarefa. Enquanto as tarefas estão em execução, a duração da execução é exibida.
  
> [!NOTE]
> As tarefas concluídas também podem incluir totais de arquivos que concluiram o processamento ou arquivos com erros. 
  
> [!TIP]
> "Cancelar" oferece uma opção de reversão para interromper a execução do processo e reverter para o preenchimento de dados anterior ou os dados processados salvos. Rollback limpa todos os dados processados. Se você não quiser que os dados processados sejam perdidos (por exemplo, você planeja recarregar esses arquivos), selecione a opção "Cancelar" nesta janela para escolher não reverter. 
  
## <a name="process-summary"></a>Resumo do processo

No \> \> Resumo do processo de preparação dos resultados do processo \> , uma divisão dos resultados do arquivo carregado é exibida de acordo com o processamento de arquivos bem-sucedido e resultados de erros.
  
Os painéis apresentam uma exibição gráfica das estatísticas de arquivo importadas, da seguinte maneira:
  
- **Resumo do processo acumula** d: todos os arquivos no caso.
    
- **Resumo do processo por último**: arquivos carregados da última sessão ou ação. 
    
- **Famílias por último**: informações da família no caso (se houver).
    
- Se os arquivos **semente** foram adicionados, o número de arquivos semente é listado por problema definido para os arquivos. 
    
    Se a marcação de arquivos de **propagação** falhar, isso também será observado. 
    
- Se forem adicionados arquivos **previamente marcados** , o número de arquivos previamente marcados será listado por problema definido para os arquivos. 
    
    Se a marcação de arquivos **previamente marcados** falhou, isso também é observado. 
    
![Resumo do módulo de processamento](../media/2086a691-9e3d-4117-beb2-a5c3a9a4cc94.png)
  
## <a name="process-summary-accumulated-and-last-charts"></a>Resumo do processo acumulado e últimos gráficos

A barra esquerda inclui arquivos de origem + extraídos: que são todos os arquivos encontrados. 
  
A barra direita, processada, inclui:
  
- Arquivos com erros de carregamento
    
- Arquivos carregados com êxito, que podem incluir: 
    
  - **Existentes**: arquivos que foram carregados antes e agora são carregados novamente (incluindo duplicatas).
    
  - **Text**: arquivos exclusivos com texto.
    
  - **Não texto**: Arquivos de texto vazios, arquivos de texto nativo vazios, arquivos de não-texto nativo. 
    
  - **Duplicar** s: duplicar arquivos com texto.
    
## <a name="last-process-errors"></a>Erros do último processo

Em preparar \> \> resultados \> do processo últimos erros de processo, os detalhes dos erros na última sessão ou ação executada são exibidos.
  
![Erros do módulo de processamento](../media/4771d0f4-4217-445a-9ba4-8b6541c5ad09.png)
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Executando o módulo de processo e carregando dados](run-the-process-module-and-load-data-in-advanced-ediscovery.md)

