---
title: Gerenciar os responsáveis em uma ocorrência de descoberta eletrônica avançada
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
description: ''
ms.openlocfilehash: 0b6776571f4abafaf8e050fa6c31311df452d90e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582910"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Gerenciar os responsáveis em uma ocorrência de descoberta eletrônica avançada

A guia responsáveis em descoberta eletrônica avançada contém uma lista de todos os responsáveis que foram adicionados ao caso. Depois de adicionar os responsáveis a um caso, os detalhes sobre cada um são coletados automaticamente do Azure Active Directory e são exibidos na descoberta eletrônica avançada.

![Gerenciar responsáveis](media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Exibir detalhes do responsáveis

Para exibir os detalhes sobre um responsáveis, clique no responsáveis da lista na guia **responsáveis** . Uma página de submenu é exibida e contém as seguintes informações sobre os responsáveis:

- Informações de contato

  - **Nome para exibição** : o nome exibido no catálogo de endereços para os responsáveis. Isso geralmente é a combinação do nome do responsáveis, da inicial do meio e do sobrenome.
  
   - **Mail/SMTP** -o endereço SMTP principal para os responsáveis, por exemplo, brianj@contoso.onmicrosoft.com. Observe que o nome principal do usuário (UPN) do responsáveis também está listado.

  - **Título** -o cargo do profissional.

  - **Departamento** -o nome do departamento no qual os responsáveis funciona.

  - **Gerente** -gerente do responsáveis. O gerente designado receberá qualquer comunicação de escalonamento para este responsáveis.
  
- Informações de local

  - **Cidade** -a cidade na qual o responsáveis está localizado.

  - **State** -o estado ou província no endereço do responsáveis.

  - **País/região** -o país/região onde o responsáveis está localizado.

  - **Office** – o local do escritório no local de trabalho do responsáveis.

- Informações sobre o caso

  - **Status de retenção** : indica se os responsáveis foram colocados em espera. 

  - **Status de Comunicação**: indica se os responsáveis foram emitidos um aviso de espera. Se o objecttiver sido emitido um aviso, esse valor dessa propriedade será **publicado**. Se não tiver sido emitido um aviso aos responsáveis, o status será **cancelado**. 

  - **Status** -o status dos responsáveis dentro do caso. Um status **ativo** indica que o responsáveis faz parte do caso. Se um responsáveis for liberado de um caso, o status será alterado para **liberado**. 

- Fontes de dados e informações de indexação

    - **Fontes de dados** : mostra a contagem e o tipo de fontes de dados (caixas de correio, sites e equipes) que estão associados aos responsáveis e fazem parte do caso.

    - **Tempo atualizado de índice** -indica a hora e a data de quando o trabalho de indexação avançada foi disparado pela última vez. Esta propriedade também indicará quando o processo de indexação avançada estiver em andamento.


## <a name="edit-a-custodian"></a>Editar um responsáveis

À medida que seu caso avança, você pode descobrir que pode haver fontes de dados adicionais relevantes para um determinado local & seu caso. Em outros cenários, talvez você queira remover determinadas fontes de dados que foram revisadas e consideradas não relevantes.

Para atualizar as fontes de dados associadas a um responsáveis:

1. Vá para **descoberta eletrônica > descoberta eletrônica avançada** e abra o caso.
  
2. Clique na guia **responsáveis** .
  
3. Selecione um responsáveis na lista e clique em **Editar** na página do menu suspenso.

    ![Editar fontes de dados](media/EditCustodianDataSource.PNG)
  
4. Clique em escolher a guia **fontes de dados** para alterar as configurações da caixa de correio do Exchange e da conta do onedrive do responsáveis, clique em **escolher fontes de dados**.
  
5. Clique na guia **selecionar fontes de dados adicionais** para adicionar ou remover as caixas de correio do Teams, SharePoint ou Exchange associadas aos responsáveis. 

    Para obter mais informações sobre fontes de dados associadas a um funcionário, consulte "etapa 3: associar fontes de dados adicionais a um funcionário" em [Adicionar responsáveis a um caso](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian). 
  
6. Clique em **colocar custodial isenções** para habilitar ou desabilitar a retenção para os responsáveis.

## <a name="resolve-custodian-processing-errors"></a>Resolver erros de processamento de responsáveis

Na maioria dos fluxos de trabalho de descoberta eletrônica para investigações legais, um subconjunto dos dados de um dos responsáveis é pesquisado depois que os responsáveis são adicionados a um caso jurídico. Por causa de tamanhos de arquivo muito grandes ou possíveis corrupção de dados, alguns itens nas fontes de dados associados a um membro podem ser parcialmente indexados. Usando a capacidade de [indexação avançada](indexing-custodian-data.md) na descoberta eletrônica avançada, os itens parcialmente indexados podem ser corrigidos automaticamente pela reindexação desses itens sob demanda.

Quando um Objecté adicionado a uma ocorrência, os dados localizados nas fontes de dados associadas ao responsáveis são automaticamente re-indexado (pelo processo de indexação avançado). Isso significa que você pode deixar os dados no local em vez de precisar baixar e corrigi-los e, em seguida, procurá-los offline). No entanto, durante o ciclo de vida de um caso jurídico, novas fontes de dados podem ser associadas a um. Nesse caso, é possível reindexar os dados dos responsáveis executando novamente o processo de indexação avançada para corrigir quaisquer itens parcialmente indexados e atualizar o índice para os dados do responsáveis.

Para acionar o processo de reindexação para lidar com itens parcialmente indexados:

1. Vá para **descoberta eletrônica > descoberta eletrônica avançada** e abra o caso.

2. Clique na **guia responsáveis**e selecione um dos responsáveis cujos dados devem ser reindexados. 

3. Na página do menu suspenso, clique em **Atualizar índice**.

   Uma caixa de diálogo é exibida informando que o trabalho de índice foi criado.

A reindexação dos dados dos responsáveis é um processo de execução demorada; o trabalho correspondente criado é chamado **de reindexação dos dados dos responsáveis**. Você pode acompanhar o progresso na guia **trabalhos** ou na guia **responsáveis** monitorando o status na coluna **status do trabalho de indexação** .

Para saber mais, confira:

- [Trabalhar com erros de processamento](processing-data-for-case.md)

- [Gerenciar tarefas](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Liberar um dos casos

Um dos responsáveis é liberado em situações em que um caso é fechado, o desejo não está mais sob obrigação de preservar o conteúdo de um caso ou quando é considerado que não é mais relevante para o caso. 

Se você liberar um dos responsáveis após um aviso de isenção ter sido publicado, um aviso de lançamento será enviado para o seu. Além disso, todas as isenções colocadas em fontes de dados que foram associadas com os responsáveis serão removidas. Se os responsáveis foram colocados em um *bloqueio silencioso*, onde não foram emitidos notificações de bloqueio legal, um aviso de lançamento não será enviado, mas todas as isenções feitas nas fontes de dados que foram associadas a esses responsáveis serão removidas.

Para liberar um responsáveis: 

1. Vá para **descoberta eletrônica > descoberta eletrônica avançada** e abra o caso.

2.  Vá para a guia **responsáveis** .

3.  Clique na **guia responsáveis**e selecione os responsáveis que estão sendo liberados do caso.

4. Na página do menu suspenso, clique em **liberar responsáveis**.

   Uma página de aviso é exibida explicando que, se uma retenção for colocada em uma fonte de dados associada aos responsáveis, a retenção será removida e que qualquer outro bloqueio associado a um caso de descoberta eletrônica diferente ainda será aplicado. Isso inclui outros tipos de recursos de preservação e retenção no Office 365 (como uma política de retenção do Office 365).

5. Clique em **Sim** para confirmar que você deseja liberar os responsáveis. 

    Observe que o status desse usuário na guia **responsáveis** é definido como **liberado** e o status de **retenção** na página do submenu é alterado para **false**. 

> [!NOTE]
> Os responsáveis podem estar simultaneamente envolvidos em vários casos jurídicos. Quando um dos responsáveis é liberado de uma ocorrência, as isenções e notificações em outras questões não serão afetadas.

## <a name="bulk-edit-custodians"></a>Editar os responsáveis em massa

Você pode usar o editor em massa para editar vários responsáveis ao mesmo tempo. Para fazer isso, basta selecionar dois ou mais responsáveis na guia **responsáveis** para exibir o editor em massa e clicar em uma das tarefas.

![Página de submenu para editar as configurações de vários responsáveis](media/AeDBulkEditCustodians.png)