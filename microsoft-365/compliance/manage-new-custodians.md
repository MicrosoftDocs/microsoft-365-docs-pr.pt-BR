---
title: Gerenciar custodiantes em um caso de Descoberta Avançada
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
description: Saiba como exibir detalhes, editar e editar em massa a lista de custodiantes em um caso de Descoberta Avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739864"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Gerenciar custodiantes em um caso de Descoberta Avançada

A página Custodians na guia **Fontes** em um caso de Descoberta Avançada contém uma lista de todos os custodiantes que foram adicionados à ocorrência. Depois de adicionar custodiantes a uma ocorrência, os detalhes sobre cada custodiante são coletados automaticamente do Azure Active Directory e podem ser visualizados na Descoberta Automática Avançada.

![Gerenciar custodiantes](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Exibir detalhes custodiados

Para exibir os detalhes sobre um custodiante, clique no custodiante na lista na **guia Custodiantes.** Uma página de flyout é exibida e contém as seguintes informações sobre o custodiatário:

- Informações de contato

  - **Nome para Exibição** - O nome exibido no livro de endereços do custodiatário. Geralmente, essa é a combinação do nome, da inicial do meio e do sobrenome do custodiante.
  
   - **Email/SMTP** - O endereço SMTP principal do custodiante, por exemplo, brianj@contoso.onmicrosoft.com. O upN (nome upn) do usuário custodiante também está listado.

  - **Cargo** - O cargo do custodiatário.

  - **Departamento** - O nome do departamento no qual o custodiatário trabalha.

  - **Gerente** - O gerente do custodiante. O gerente designado receberá as comunicações de escalonamento desse custodiante.
  
- Informações de localização

  - **Cidade** - A cidade em que o custodiatário está localizado.

  - **Estado** - O estado ou província no endereço do custodiatário.

  - **País/região** - O país/região onde o custodiatário está localizado.

  - **Office** - O local do escritório no local de trabalho do custodiatário.

- Informações sobre a ocorrência

  - **Status de** espera - Indica se o custodiatário foi colocado em espera. 

  - **Status de** comunicação: indica se o custodiatário recebeu um aviso de espera. Se o custodiante tiver sido emitido um aviso, esse valor dessa propriedade será **Publicado.** Se o custodiante não tiver sido emitido um aviso, o status será **Não Publicado.** 

  - **Status** - O status do custodiante dentro da ocorrência. Um status **ativo** indica que o custodiante faz parte do caso. Se um custodiante for liberado de uma ocorrência, o status será alterado para **Liberado.** 

- Fontes de dados e informações de indexação

    - **Fontes de** dados – mostra a contagem e o tipo de fontes de dados (caixas de correio, sites e Teams) que estão associadas ao custodiante e fazem parte do caso.

    - **Tempo de atualização do** índice - Indica a hora e a data de quando o trabalho de indexação avançada foi disparado pela última vez. Essa propriedade também indicará quando o processo avançado de indexação está em andamento.


## <a name="edit-a-custodian"></a>Editar um custodiatário

À medida que seu caso progride, você pode descobrir que pode haver fontes de dados adicionais relevantes para um custodiante & seu caso. Em outros cenários, talvez você queira remover determinadas fontes de dados que foram revisadas e consideradas não relevantes.

Para atualizar as fontes de dados associadas a um custodiante:

1. Vá para  **a Descoberta > eDiscovery Avançada** e abra a ocorrência.
  
2. Clique na **guia** Fontes.
  
3. Na página **Custodiantes,** selecione um custodiante na lista e clique em **Editar** na página do flyout.

    ![Editar Fontes de Dados](../media/EditCustodianDataSource.PNG)
  
4. Clique **na guia Escolher fontes** de dados para alterar as configurações da caixa de correio do Exchange do custodiante e da conta do OneDrive, clique em Escolher fontes de **dados.**
  
5. Clique na **guia Selecionar fontes de dados adicionais** para adicionar ou remover caixas de correio do Teams, SharePoint ou Exchange associadas ao custodiante. 

    Para obter mais informações sobre fontes de dados associadas a um custodiante, consulte [Adicionar custodiantes a uma ocorrência.](add-custodians-to-case.md) 
  
6. Clique **em Colocar reter custodiante** para habilitar ou desabilitar a espera do custodiante.

## <a name="re-index-custodian-data"></a>Re-indexar dados custodiante

Na maioria dos fluxos de trabalho de Descoberta Eletrônico para investigações legais, um subconjunto de dados de um custodiante é pesquisado depois que o custodiante é adicionado a um caso jurídico. Devido a tamanhos de arquivo muito grandes ou possível corrupção de dados, alguns itens nas fontes de dados associadas a um custodiante podem ser parcialmente indexados. Usando o recurso de [indexação](indexing-custodian-data.md) avançada na Descoberta Automática Avançada, os itens mais parcialmente indexados podem ser automaticamente remediados pela indexação desses itens sob demanda.

Quando um custodiante é adicionado a uma ocorrência, os dados localizados nas fontes de dados associadas ao custodiante são indexados automaticamente (pelo processo avançado de indexação). Isso significa que você pode deixar os dados no local em vez de ter que baixá-los e remedia-los e, em seguida, pesquisá-los offline). No entanto, durante o ciclo de vida de um caso jurídico, novas fontes de dados podem ser associadas a um custodiante. Nesse caso, você pode indexar os dados do custodiante executando o processo de indexação avançado para remediar todos os itens parcialmente indexados e atualizar o índice dos dados do custodiante.

Para disparar o processo de indexação para lidar com itens parcialmente indexados:

1. Vá para  **a Descoberta > eDiscovery Avançada** e abra a ocorrência.

2. Clique na **guia** Fontes.

3. Na página **Custodiantes,** selecione um custodiante cujos dados devem ser reindexados.

4. Na página do flyout, clique em **Atualizar índice.**

   Uma caixa de diálogo é exibida dizendo que o trabalho de índice foi criado.

A indexação de dados custodiante é um processo de longa execução; o trabalho correspondente criado é denominado **re-indexação de dados custodiante**. Você pode acompanhar o progresso na guia **Trabalhos** ou na guia **Custodiantes** monitorando o status na coluna Status do **trabalho de Indexação.**

Para saber mais, confira:

- [Trabalhar com erros de processamento](processing-data-for-case.md)

- [Gerenciar tarefas](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Liberar um custodiante de uma ocorrência

Um custodiante é liberado em situações em que um caso é fechado, o custodiante não está mais sob a obrigação de preservar o conteúdo de uma ocorrência ou quando o custodiante é considerado não mais relevante para o caso. 

Se você liberar um custodiante após a publicação de um aviso de espera, uma notificação de liberação será enviada ao custodiante. Além disso, todas as reteres colocadas em fontes de dados que foram associadas ao custodiante serão removidas. Se o custodiante foi colocado em uma espera silenciosa *,* onde não foram emitidas notificações de responsabilidade legal, uma notificação de liberação não será enviada, mas todas as reteres colocadas em fontes de dados que foram associadas a esse custodiante serão removidas.

Para liberar um custodiatário: 

1. Vá para  **a Descoberta > eDiscovery Avançada** e abra a ocorrência.

2. Clique na **guia** Fontes.

3. Na página **Custodians** e selecione o custodiante que está sendo liberado da ocorrência.

4. Na página do flyout, clique em **Liberar custodiante.**

   Uma página de aviso é exibida explicando que, se uma isenção for aplicada a uma fonte de dados associada ao custodiante, a isenção será removida e que qualquer outra isenção associada a um caso de Descoberta Avançada diferente ainda será aplicada. Isso inclui outros tipos de recursos de preservação e retenção (como uma política de retenção do Microsoft 365).

5. Clique **em Sim** para confirmar que você deseja liberar o custodiatário. 

    O status desse usuário na guia **Custodians** é definido como Liberado e o **status** de Espera na página do flyout é alterado para **False**.  

> [!NOTE]
> Um custodiatário pode estar envolvido simultaneamente em vários casos legais. Quando um custodiante é liberado de uma ocorrência, as iseções e notificações em outras questões não serão impactadas.

## <a name="bulk-edit-custodians"></a>Custodiantes de edição em massa

Você pode usar o editor em massa para editar vários custodiantes ao mesmo tempo. Para fazer isso, basta selecionar dois ou mais custodiantes na guia **Custodiantes** para exibir o editor em massa e clicar em uma das tarefas.

![Página de flyout para editar configurações de vários custodiantes](../media/AeDBulkEditCustodians.png)
