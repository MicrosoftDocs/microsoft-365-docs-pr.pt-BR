---
title: Executar o módulo de processo e carregar dados na descoberta eletrônica avançada
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
ms.assetid: c87bb0e5-301c-4d1d-958e-aabeb7990f44
description: 'Saiba como usar o centro de &amp; conformidade de segurança para acessar a descoberta eletrônica avançada e executar o módulo de processo para um caso.  '
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 47614e8bc25a376f9b51068c151a71e025e2f264
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818900"
---
# <a name="run-the-process-module-and-load-data-in-advanced-ediscovery-classic"></a>Executar o módulo de processo e carregar dados na descoberta eletrônica avançada (clássico)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Esta seção descreve a funcionalidade do módulo de processo de descoberta eletrônica avançada. 
  
Além dos dados de arquivo, os metadados como tipo de arquivo, extensão, local ou caminho, data e hora de criação, autor, responsáveis e assunto podem ser carregados na descoberta eletrônica avançada e salvos para cada caso. Alguns metadados são calculados pela descoberta eletrônica avançada, por exemplo, quando os arquivos nativos são carregados. 
  
A descoberta eletrônica avançada fornece valores de metadados do sistema, como agrupamento Near-Duplicate ou pontuações de relevância. Outros metadados, como anotações de arquivo, podem ser adicionados pelo administrador. 
  
## <a name="running-process"></a>Processo em execução

> [!NOTE]
> Os números de lote são atribuídos a um arquivo durante o processo para permitir o controle de arquivos. O número de lote também permite a identificação de lotes de processos para reprocessamento de opções. Filtros adicionais estão disponíveis para filtragem por número de lote e sessões. 
  
Execute as etapas a seguir para executar o processo.
  
1. [Abrir a segurança &amp; Centro de conformidade](go-to-the-securitycompliance-center.md) . 
    
2. Vá para ** &amp; ** \> **descoberta eletrônica** de investigação e clique em **ir para descoberta eletrônica avançada**.
    
3. Em descoberta eletrônica avançada, selecione o caso apropriado na página **casos** exibidos e clique em **ir para o caso**.
    
4. Na **configuração preparar** \> **processo** \> **Setup**, selecione um contêiner na lista de contêineres disponíveis.
    
    ![Clique em processar para adicionar os resultados da pesquisa ao caso](../media/50bdc55c-d378-4881-b302-31ef785fa359.png)
  
5. Clique em **Configurações avançadas...** se você deseja adicionar o contêiner como arquivos semente ou como arquivos previamente marcados. 
    
    Use arquivos semente para acelerar o treinamento para problemas com riqueza baixa (geralmente 2% ou menos). Para arquivos semente, é recomendável que você selecione uma variedade de arquivos distintomente relevantes e processe cerca de 20-50 sementes por problema (muitos arquivos semente podem distorcer os resultados de relevância). Os arquivos semente devem ser revisados pela mesma pessoa que vai treinar o problema.
    
    Use arquivos previamente marcados para automatizar o treinamento de relevância. Você deve marcar pelo menos 1.500 arquivos e manter a proporção de arquivos que não são relevantes o mesmo que o da coleção adicionado à relevância. Esses arquivos devem ser marcados manualmente e você deve ter certeza na qualidade da marcação.
    
    ![Captura de tela da página de configurações avançadas para processar arquivos em lotes](../media/3c25cb78-4484-41e5-bd34-3753c7ab6cf2.jpg)
  
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
    
7. Opcion Se for necessário atribuir fontes de dados a um determinado, você poderá adicionar e editar os nomes **dos responsáveis pelo** \> **Gerenciamento** e atribuir os responsáveis pela **Custodians** \> **atribuição**de responsáveis. 
    
Se você adicionar à ocorrência, então poderá processar novamente.
  
## <a name="related-topics"></a>Tópicos relacionados

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Exibir resultados do módulo de processo](view-process-module-results-in-advanced-ediscovery.md)

