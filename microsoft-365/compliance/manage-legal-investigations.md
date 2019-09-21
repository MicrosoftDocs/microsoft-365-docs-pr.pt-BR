---
title: Gerenciar investigações legais no Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e
description: Use casos de descoberta eletrônica no centro de conformidade & segurança no Office 365 para gerenciar a investigação legal da sua organização. Se você tiver uma assinatura e5, poderá analisar mais dados de caso usando a análise de texto, aprendizado de máquinas e recursos de codificação de descoberta eletrônica avançada.
ms.openlocfilehash: c6b5b3048039a8c92d120d2b9f46d6d22d9ccee0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072790"
---
# <a name="manage-legal-investigations-in-office-365"></a>Gerenciar investigações legais no Office 365

As organizações têm vários motivos para responder a um caso jurídico que envolve determinados executivos ou outros funcionários em sua organização. Isso pode envolver rapidamente a localização e a retenção de informações específicas de investigação em email, documentos, conversas de mensagens instantâneas e outros locais de conteúdo usados por pessoas em suas tarefas diárias de trabalho. Você pode executar essas e muitas outras atividades semelhantes usando as ferramentas de casos de descoberta eletrônica no centro de conformidade do & de segurança.
  
[Gerenciar investigações legais com ocorrências de descoberta eletrônica](#manage-legal-investigations-with-ediscovery-cases)
  
[Analisar dados de caso usando a descoberta eletrônica avançada do Office 365](#analyze-case-data-using-office-365-advanced-ediscovery)
  
**Deseja saber como a Microsoft gerencia suas investigações de eDiscovery?** Este é um [White paper técnico](https://go.microsoft.com/fwlink/?linkid=852161) que você pode baixar, que explica como usamos as mesmas ferramentas de pesquisa e investigação do Office 365 para gerenciar nosso fluxo de trabalho de descoberta eletrônica interna.
   
## <a name="manage-legal-investigations-with-ediscovery-cases"></a>Gerenciar investigações legais com ocorrências de descoberta eletrônica

as ocorrências de descoberta eletrônica permitem que você controle quem pode criar, acessar e gerenciar casos de descoberta eletrônica em sua organização. Casos de uso para adicionar membros e controlar os tipos de ações que eles podem executar, colocar em espera os locais de conteúdo relevantes para um caso jurídico e usar a ferramenta de pesquisa de conteúdo para pesquisar os locais em espera para o conteúdo que pode ser responsivo ao seu caso. Em seguida, você também pode exportar e baixar esses resultados para obter mais investigações por revisores externos. Se sua organização do Office 365 tem uma assinatura e5, você também pode preparar os resultados da pesquisa para análise na descoberta eletrônica avançada.
  
- [Gerencie seu fluxo de trabalho de descoberta eletrônica](ediscovery-cases.md) criando e usando casos de descoberta eletrônica para cada investigação legal que sua organização tenha para realizar 
    
- [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md) para controlar quem pode criar e gerenciar ocorrências de descoberta eletrônica em sua organização 
    
- [Configurar limites de conformidade](tagging-and-assessment-in-advanced-ediscovery.md) para controlar os locais de conteúdo do usuário que os gerentes de descoberta eletrônica podem pesquisar 
    
- [Pesquisar conteúdo](search-for-content.md) em sua organização 
    
- [Prepare o conteúdo de caso para a descoberta eletrônica avançada](prepare-search-results-for-advanced-ediscovery.md) para que você possa realizar a análise usando as ferramentas analíticas poderosas da descoberta eletrônica avançada, como reconhecimento óptico de caracteres, encadeamento de emails e codificação de previsão 
    
### <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para cenários avançados

Como a seção anterior que listava scripts para cenários de pesquisa de conteúdo, também criamos alguns scripts do PowerShell de segurança & centro de conformidade para ajudá-lo a gerenciar ocorrências de descoberta eletrônica.
  
- [Criar um relatório de retenção de descoberta eletrônica](create-a-report-on-holds-in-ediscovery-cases.md) que contenha informações sobre todas as isenções associadas a ocorrências de descoberta eletrônica em sua organização 
    
- [Adicionar caixas de correio e locais do onedrive](use-a-script-to-add-users-to-a-hold-in-ediscovery.md) para uma lista de usuários a uma retenção de descoberta eletrônica 
  
## <a name="analyze-case-data-using-office-365-advanced-ediscovery"></a>Analisar dados de caso usando a descoberta eletrônica avançada do Office 365

A descoberta eletrônica avançada do Office 365 cria a pesquisa de conteúdo e os recursos de descoberta eletrônica descritos nas seções anteriores. Depois de criar um caso de descoberta eletrônica, coloque os locais em espera e colete dados que possam ser responsivos para o caso, você pode analisar mais os dados usando a análise de texto, o Machine Learning e os recursos de codificação de previsão do Advanced descobertas. Isso pode ajudar sua organização a processar rapidamente milhares de mensagens de email, documentos e outros tipos de dados para localizar os itens que mais provavelmente são relevantes para um caso específico. E temos o gerenciamento unificado de casos e a descoberta eletrônica avançada para que você possa gerenciar o mesmo caso no centro de conformidade de segurança &.
  
> [!NOTE]
> Para analisar os dados de um usuário usando a descoberta eletrônica avançada, o usuário (o responsáveis dos dados) deve receber uma licença do Office 365 e5. Como alternativa, os usuários com uma licença do Office 365 E1 ou E3 podem receber uma licença autônoma de descoberta eletrônica avançada. Administradores e gerentes de conformidade atribuídos aos casos e usar a descoberta eletrônica avançada para analisar os dados não precisam de uma licença e5. 
  
### <a name="get-started"></a>Introdução

A maneira mais rápida de começar a usar a descoberta eletrônica avançada é criar um caso e preparar os resultados da pesquisa no centro de conformidade e segurança &, carregar os resultados na descoberta eletrônica avançada e, em seguida, executar a análise expressa para analisar esses dados de caso e exportar os resultados para revisão externa.
  
- [Obter uma visão geral rápida](quick-setup-for-advanced-ediscovery.md) do fluxo de trabalho de descoberta eletrônica avançada 
    
- [Configurar usuários e casos](set-up-users-and-cases-in-advanced-ediscovery.md) para descoberta eletrônica avançada criando um caso, atribuindo permissões de descoberta eletrônica e adicionando membros de caso, tudo usando o centro de conformidade de & de segurança 
    
- [Preparar e carregar dados de pesquisa](prepare-data-for-advanced-ediscovery.md) no caso da descoberta eletrônica avançada 
    
- [Carregar dados não-Office 365](import-non-office-365-data-into-advanced-ediscovery.md) em um caso para analisá-los na descoberta eletrônica avançada 
    
- [Usar a análise expressa](use-express-analysis-in-advanced-ediscovery.md) para analisar rapidamente os dados em um caso e, em seguida, exportar facilmente os resultados 
    
### <a name="analyze-data"></a>Analisar dados

Após o carregamento dos dados de pesquisa no caso da descoberta eletrônica avançada, você usará o módulo analyze para começar a analisá-lo. A primeira parte do processo de análise consiste em organizar os arquivos em grupos de arquivos exclusivos, duplicatas e quase duplicados (também conhecidos como semelhança de documento). Em seguida, você organizará os dados novamente em grupos de threads de email e temas hierarquicamente e, opcionalmente, definirá ignorar filtros de texto para excluir certos textos da análise. Em seguida, você executará a análise e exibirá os resultados.
  
- [Saiba mais sobre a similaridade de documentos](understand-document-similarity-in-advanced-ediscovery.md) para preparar você para a análise de dados na descoberta eletrônica avançada 
    
- [Configure as opções para a](set-analyze-options-in-advanced-ediscovery.md) duplicação próxima, temas e encadeamento de email e execute o módulo Analyze 
    
- [Configure ignorar filtros de texto](set-ignore-text-in-advanced-ediscovery.md) para excluir cadeias de texto e texto de serem analisadas; esses filtros também ignorarão texto ao executar análise de relevância 
    
- [Exibir os resultados](view-analyze-results-in-advanced-ediscovery.md) do processo de análise 
    
- [Definir configurações avançadas](set-analyze-advanced-settings-in-advanced-ediscovery.md) para o processo de análise 
    
### <a name="set-up-relevance-training"></a>Configurar treinamento de Relevância

A codificação preditiva (chamada de relevância) na descoberta eletrônica avançada permite que você treine o sistema no que você está procurando, permitindo tomar decisões (sobre se algo é relevante ou não) em um pequeno conjunto de documentos.
  
- [Saiba mais sobre como configurar o treinamento de relevância](manage-relevance-setup-in-advanced-ediscovery.md) , marcação de arquivos relevantes para um caso e definição de problemas de caso 
    
- [Definir problemas de caso](define-issues-and-assign-users.md) e atribuir cada problema a um usuário que treinará os arquivos 
    
- [Adicionar arquivos importados à carga atual ou nova](set-up-loads-to-add-imported-files.md) que será adicionada ao treinamento de relevância; uma carga é um novo lote de arquivos que são adicionados a um caso e usados para o treinamento de relevância 
    
- [Definir palavras-chave realçadas](define-highlighted-keywords-and-advanced-options.md) que podem ser adicionadas ao treinamento de relevância; Isso ajuda a identificar melhor os arquivos que são relevantes para um caso 
    
### <a name="run-the-relevance-module"></a>Executar o módulo de relevância

Após configurar o treinamento, você está pronto para executar o módulo de relevância e avaliar a eficácia das configurações de treinamento isso resulta em uma classificação de relevância que ajuda você a decidir se precisa realizar treinamento adicional ou se você está pronto para iniciar a marcação de arquivos como relevante para o seu caso.
  
- [Saiba mais sobre o processo de relevância](use-relevance-in-advanced-ediscovery.md) e o processo iterativo de avaliação, marcação, acompanhamento e re-treinamento com base em um conjunto de arquivos de amostra 
    
- [Saiba mais sobre a avaliação](assessment-in-relevance-in-advanced-ediscovery.md) , onde um especialista familiarizado com o caso revisa um conjunto de arquivos de caso e determina a eficácia do treinamento de relevância 
    
- [Avaliar casos de arquivos](tagging-and-assessment-in-advanced-ediscovery.md) para calcular a eficácia (chamada *riqueza* ) de configurações de treinamento e, em seguida, marcar arquivos como relevantes ou não relevantes para o seu caso; Isso ajuda a determinar se o treinamento atual é suficiente ou se você deve ajustar as configurações de treinamento. 
    
- [Execute o treinamento de relevância após a conclusão da](tagging-and-relevance-training-in-advanced-ediscovery.md) avaliação e, em seguida, marque novamente os arquivos conforme relevante ou não relevantes para os problemas que você definiu para o caso 
    
- [Acompanhe o processo de análise de relevância](track-relevance-analysis-in-advanced-ediscovery.md) para determinar se o treinamento de relevância alcançou seu alvo de avaliação (conhecido como um *status de treinamento estável* ) ou se mais treinamento é necessário; Você também pode exibir os resultados de relevância para cada problema de caso 
    
- [Tome decisões com base na análise de relevância](decision-based-on-the-results-in-advanced-ediscovery.md) para determinar o tamanho do conjunto resultante de arquivos de caso que podem ser exportados para revisão 
    
- [Testar a qualidade da análise de relevância](test-relevance-analysis-in-advanced-ediscovery.md) para validar as decisões de remoção feitas durante o processo de relevância 
    
### <a name="export-results"></a>Exportar resultados

A etapa final na análise de dados de caso na descoberta eletrônica avançada é exportar os resultados da análise para revisão externa.
  
- [Saiba mais sobre exportação de dados de ocorrência](export-case-data-in-advanced-ediscovery.md)
    
- [Exportar dados de ocorrência](export-results-in-advanced-ediscovery.md)
    
- [Exibir histórico em lotes e exportar resultados passados](view-batch-history-and-export-past-results.md)
    
- [Campos do relatório de exportação](export-report-fields-in-advanced-ediscovery.md)
    
### <a name="other-advanced-ediscovery-tools"></a>Outras ferramentas avançadas de descoberta eletrônica

A descoberta eletrônica avançada fornece ferramentas e recursos adicionais além de analisar dados de caso, análise de relevância e exportação de dados.
  
- [Executar relatórios de descoberta eletrônica avançados](run-reports-in-advanced-ediscovery.md)
    
- [Definir configurações de caso e de locatário](define-case-and-tenant-settings-in-advanced-ediscovery.md)
    
- [Utilitários de descoberta eletrônica avançada](use-advanced-ediscovery-utilities.md)
