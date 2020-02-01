---
title: Usar os utilitários de descoberta eletrônica avançada do Office 365
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: 'Saiba mais sobre os utilitários na descoberta eletrônica avançada do Office 365, incluindo log de caso, dados claros, erros de processo, modificar relevância e análise de transparência.  '
ms.openlocfilehash: 3952d1ec58b3f55f997079cec16f16ddb301ed89
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601328"
---
# <a name="use-office-365-advanced-ediscovery-utilities"></a>Usar os utilitários de descoberta eletrônica avançada do Office 365

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Os utilitários que são exibidos e estão disponíveis na descoberta eletrônica avançada dependem de contexto e funções de usuário.
  
## <a name="case-log"></a>Log de caso

O log de caso fornece uma lista detalhada das atividades de processamento do aplicativo, que podem ser usadas para controlar, solucionar problemas e para endereçar erros e avisos. O log pode ser gerado e armazenado localmente no host ou servidor ou enviado diretamente para um endereço de email.
  
O arquivo de log também pode ser baixado no computador do cliente. A opção de download do cliente pode ser habilitada ou desabilitada de acordo com a configuração e a função do usuário.
  
1. Na barra de menus, clique no ícone **engrenagem** . 
    
2. Na guia **utilitários de configurações \> e utilitários** , selecione **a configuração \> de log de caso**.
    
3. Selecione o **nível de log** da seguinte maneira: 
    
  - **Padrão**: inclui os dados de log básicos. Essa opção geralmente é necessária para monitoramento e deve ser usada, a menos que o contrário seja recomendado.
    
  - **Mínimo**: usado em casos muito grandes e retorna apenas os dados mais recentes.
    
4. Clique em **executar log de caso**. O log é gerado e o caminho é exibido. As informações de progresso da tarefa para a tarefa atual e a última são exibidas no painel de status da tarefa.
    
## <a name="clear-data"></a>Limpar dados

Se for necessário excluir ou reinicializar os dados da ocorrência, a instância do banco de dados deverá ser inicializada. O utilitário limpar dados exclui todas as entradas especificadas do banco de dados de casos, arquivos de texto, pastas de casos e resultados acumulados. A função só pode ser executada por um administrador.
  
> [!IMPORTANT]
> Esta ação não é reversível e desmarcará toda a marcação e análise de relevância executada pelo especialista. Salve um backup de dados, se necessário. Use essa opção com extrema cautela. Excluir arquivos marcados e classificados pode afetar os resultados de relevância. 
  
1. Na barra de menus, clique no ícone **engrenagem** . 
    
2. Na guia **utilitários de configurações \> e utilitários** , selecione **limpar configuração \> de dados**.
    
3. Selecione uma opção para que as informações sejam inicializadas:
    
  - **Relevância**: exclui todo o trabalho realizado de relevância, incluindo a definição de cargas e Associação de arquivos a serem carregados. Ele exclui todos os exemplos e marcação.
    
  - **Duplicatas e threads de email**: exclui todas as informações de análise de quase duplicatas e threads de email.
    
  - **Themes**: exclui os dados relacionados a temas.
    
  - **Export History**: Exclui informações de histórico de lotes de exportação.
    
4. Clique em **limpar dados**. Os dados de caso são limpos. As informações de progresso da tarefa para a tarefa atual e a última são exibidas no painel de **status da tarefa** . 
    
## <a name="modify-relevance"></a>Modificar relevância

Esta seção descreve como ignorar ou reverter uma amostra de relevância.
  
1. Na barra de menus, clique no ícone **engrenagem** . 
    
2. Na guia **utilitários de configurações \> e utilitários** , selecione **Modificar relevância**.
    
3. Selecione dentre as opções: 
    
  - **Ignorar amostra atual-para usuário atual**: isso marcará, como **ignorar**, todos os arquivos não marcados no exemplo de caso aberto do usuário que está executando o utilitário. O processamento de relevância não será executado em arquivos marcados como **Skip**.
    
  - **Ignorar amostra atual-todos os exemplos abertos**: isso marcará, como **ignorar**, todos os arquivos não marcados em todos os exemplos abertos de todos os usuários. Essa opção não é recomendada se os usuários estiverem atualmente em uma marcação de amostra.
    
  - **Reverter último exemplo**: a última amostra de treinamento de relevância será revertida, independentemente de estar antes ou após o processo de "cálculo". A reversão de um exemplo de atualização não é permitida.
    
4. Clique em **executar** para executar. 
    
## <a name="transparency-analysis"></a>Análise de transparência

O utilitário de análise transparência permite uma visão detalhada dos arquivos e a pontuação de relevância atribuída. O relatório pode ser usado como uma verificação de sanidade ou para comparar a relevância de um arquivo definido por um revisor humano em comparação à relevância atribuída pela descoberta eletrônica avançada. 
  
Além da Pontuação de relevância, a descoberta eletrônica avançada calcula e atribui pesos de palavras-chave que consideram o contexto da palavra-chave. A mesma palavra em um arquivo pode ser atribuída a diferentes pesos, dependendo do contexto e local. Cada palavra-chave é marcada usando uma escala crescente de intensidade de cor variando de amarelo para laranja escuro e tons de cinza variados. A codificação de cores é usada para indicar visualmente a contribuição positiva ou negativa relativa do Word à pontuação de relevância. 
  
Em um cenário de caso de vários problemas, um relatório de análise de transparência pode ser gerado para cada problema.
  
1. Na barra de menus, clique no ícone **engrenagem** . 
    
2. Na guia **utilitários de configurações \> e utilitários** , selecione **configuração de \> análise de transparência**.
    
3. Em * * ID de arquivo * *, insira a ID de arquivo do arquivo a ser processado.
    
4. Na lista **problema** , selecione o problema pertinente. 
    
5. Clique em **análise de transparência**. Após a conclusão, o relatório de análise de transparência do arquivo é exibido, mostrando como as cores de palavra-chave marcadas são correlacionadas à pontuação de relevância geral.
    
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Definindo configurações de caso e de locatário](define-case-and-tenant-settings-in-advanced-ediscovery.md)

