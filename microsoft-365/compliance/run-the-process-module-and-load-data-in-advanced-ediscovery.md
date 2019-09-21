---
title: Executar o módulo de processo e carregar dados na descoberta eletrônica avançada do Office 365
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Saiba como usar o centro de conformidade de &amp; segurança do Office 365 para acessar a descoberta eletrônica avançada do Office 365 e executar o módulo de processo para um caso.  '
ms.openlocfilehash: 89a4be9bf56f35d9d9cbd88494bcae5a5a10fe7a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073169"
---
# <a name="run-the-process-module-and-load-data-in-office-365-advanced-ediscovery"></a>Executar o módulo de processo e carregar dados na descoberta eletrônica avançada do Office 365

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Esta seção descreve a funcionalidade do módulo de processo de descoberta eletrônica avançada. 
  
Além dos dados de arquivo, os metadados como tipo de arquivo, extensão, local ou caminho, data e hora de criação, autor, responsáveis e assunto podem ser carregados na descoberta eletrônica avançada e salvos para cada caso. Alguns metadados são calculados pela descoberta eletrônica avançada, por exemplo, quando os arquivos nativos são carregados. 
  
A descoberta eletrônica avançada fornece valores de metadados do sistema, como agrupamento Near-Duplicate ou pontuações de relevância. Outros metadados, como anotações de arquivo, podem ser adicionados pelo administrador. 
  
## <a name="running-process"></a>Processo em execução

> [!NOTE]
> Os números de lote são atribuídos a um arquivo durante o processo para permitir o controle de arquivos. O número de lote também permite a identificação de lotes de processos para reprocessamento de opções. Filtros adicionais estão disponíveis para filtragem por número de lote e sessões. 
  
Execute as etapas a seguir para executar o processo.
  
1. [Abra o centro de conformidade &amp; de segurança do Office 365](go-to-the-securitycompliance-center.md) . 
    
2. Vá para \> **descoberta eletrônica** de ** &amp; investigação** e clique em **ir para descoberta eletrônica avançada**.
    
3. Em descoberta eletrônica avançada, selecione o caso apropriado na página **casos** exibidos e clique em **ir para o caso**.
    
4. Na **configuração** **preparar** \> **processo** \> , selecione um contêiner na lista de contêineres disponíveis.
    
    ![Clique em processar para adicionar os resultados da pesquisa ao caso](media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. Clique em **Configurações avançadas...** se você deseja adicionar o contêiner como arquivos semente ou como arquivos previamente marcados. 
    
    Use arquivos semente para acelerar o treinamento para problemas com riqueza baixa (geralmente 2% ou menos). Para arquivos semente, é recomendável que você selecione uma variedade de arquivos distintomente relevantes e processe cerca de 20-50 sementes por problema (muitos arquivos semente podem distorcer os resultados de relevância). Os arquivos semente devem ser revisados pela mesma pessoa que vai treinar o problema.
    
    Use arquivos previamente marcados para automatizar o treinamento de relevância. Você deve marcar pelo menos 1.500 arquivos e manter a proporção de arquivos que não são relevantes o mesmo que o da coleção adicionado à relevância. Esses arquivos devem ser marcados manualmente e você deve ter certeza na qualidade da marcação.
    
    ![Captura de tela da página de configurações avançadas para processar arquivos em lotes](media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
  - Na seção **propagação** : 
    
    Escolha **Marcar como arquivos semente** para marcar o contêiner como arquivos semente. Você também precisa optar por atribuí-los por problema no menu suspenso **para o problema** . Escolha **relevante** ou **não relevante** na lista suspensa **marca** . 
    
    > [!NOTE]
    > Depois de definir os arquivos como **semente**, você não pode marcá-los como **previamente marcados**. 
  
  - Na seção **arquivos previamente marcados** : 
    
    Escolha **Marcar como arquivos previamente marcados** para marcar o contêiner como arquivos previamente marcados. Você também precisará atribuí-los por problema no menu suspenso **para o problema** . Escolha **relevante** ou **não relevante** na lista suspensa **marca** . 
    
    > [!NOTE]
    > Depois de definir os arquivos como **previamente marcados**, você não pode marcá-los como **semente**. 
  
  - Na seção **marcação de emails** . defina qual parte de um email processado deve ser marcada como semente ou pré-selecionado. 
    
6. Para começar, clique em **processar**. Quando concluído, os resultados do processo são exibidos.
    
7. Opcion Se for necessário atribuir fontes de dados a um determinado, você poderá adicionar e editar os nomes **dos** \> responsáveis pelo **Gerenciamento** **e atribuir os** \> responsáveis pela **atribuição**de responsáveis. 
    
Se você adicionar à ocorrência, então poderá processar novamente.
  
## <a name="see-also"></a>Confira também

[Descoberta Eletrônica Avançada do Office 365](office-365-advanced-ediscovery.md)
  
[Exibir resultados do módulo de processo](view-process-module-results-in-advanced-ediscovery.md)

