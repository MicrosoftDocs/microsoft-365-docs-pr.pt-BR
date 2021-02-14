---
title: Fechar ou excluir uma ocorrência
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
description: Saiba o que acontece quando uma investigação ou um caso jurídico suportado por um caso de Descoberta Avançada é fechado ou excluído.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419057"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a>Fechar ou excluir uma ocorrência de Descoberta Avançada

Quando o caso jurídico ou a investigação suportado por um caso de Descoberta Avançada for concluído, você poderá fechar ou excluir uma ocorrência. Você também pode reabrir um caso fechado.

## <a name="close-a-case"></a>Fechar uma ocorrência

Veja o que acontece quando você fecha um caso de Descoberta Avançada:

- Se o caso contiver qualquer local de conteúdo em espera, essas regiões serão desligadas. Depois que a espera é desligada, um período de carência de 30 dias (chamado de espera de *atraso)* é aplicado a locais de conteúdo que estavam em espera. Isso ajuda a evitar que o conteúdo seja imediatamente excluído e oferece aos administradores a oportunidade de pesquisar ou recuperar conteúdo que será excluído permanentemente após o período de espera de atraso expirar. Para obter mais informações, [consulte Removendo locais de conteúdo de um eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- Fechar uma ocorrência só desliga as retém associadas a esse caso. Se outras retenções ocorrerem em um local de conteúdo (como uma Responsabilidade de Litígio, Uma Espera principal de Descoberta eDiscovery ou uma responsabilidade de um caso de Descoberta eDiscovery Avançada diferente), essas retenções ainda serão mantidas.

- A ocorrência ainda está listada na página de Descobertas EDiscovery no centro de conformidade do Microsoft 365. Os detalhes, retidos, pesquisas e membros de um caso fechado são mantidos.

- Você pode editar uma ocorrência depois que ela for fechada. Por exemplo, você pode adicionar ou remover membros, criar pesquisas, exportar resultados de pesquisa e preparar resultados de pesquisa para análise na Descoberta Avançada. A principal diferença entre os casos ativos e fechados é que as retém são desligadas quando um caso é fechado.

Para fechar um caso:

1. Na página **Descobertas Avançadas,** selecione a ocorrência que você deseja fechar.

2. Na guia **Configurações,** em Informações **da Ocorrência,** clique em **Selecionar.**

3. Clique **em Fechar caso.**

   Pode levar até 60 minutos para que o processo de fechamento seja concluído.

## <a name="reopen-a-closed-case"></a>Reabrir um caso fechado

Quando você reabrir um caso de Descoberta Automática Avançada, todas as resuspensão que estavam no local quando o caso foi fechado não serão automaticamente restabelecimento. Depois que o caso for reaberto, você terá que ir para a guia **Isões** e ativar as retém anteriores. Para ativar uma espera, selecione-a para exibir a página do flyout e, em seguida, de definir a **alternância de Status** para **Ativar.**

Para reabrir um caso fechado:

1. Na página **Descoberta Avançada,** selecione a ocorrência que você deseja reabrir.

2. Na guia **Configurações,** em Informações **da Ocorrência,** clique em **Selecionar.**

3. Clique **em Caso de Reabertura.**

   Pode levar até 60 minutos para que o processo de reabertura seja concluído.

## <a name="delete-a-case"></a>Excluir uma ocorrência

Você pode excluir ocorrências de Descobertas Avançadas ativas e fechadas. Quando você exclui uma ocorrência, todos os componentes associados à ocorrência, como a lista de custodiantes, comunicações, pesquisas, conjuntos de revisão e trabalho de exportação são excluídos. O caso é removido da lista de casos na **página Descobertas Avançadas** no centro de conformidade do Microsoft 365. Não é possível recuperar ou reabrir um caso excluído.

> [!NOTE]
> Em cenários de vazamento de dados, a única maneira de remover itens em um conjunto de revisão é excluir o caso de Descoberta Avançada. Outros métodos de "pesquisa e limpeza" não removem itens de um conjunto de revisão.

Antes de excluir uma ocorrência (se ela está ativa  ou fechada), primeiro você deve excluir todas as retém associadas à ocorrência. Isso inclui a exclusão de retém com um status **de Desligado**.

Para excluir retém associadas a uma ocorrência:

1. Vá para **a** guia Retém no caso de Descoberta eDiscovery Avançada que você deseja excluir.

2. Clique na espera que você deseja excluir.

3. Na página do flyout, clique em **Excluir bloqueio.**

Para excluir uma ocorrência:

1. Na página **Descobertas Avançadas,** selecione a ocorrência que você deseja excluir.

2. Na guia **Configurações,** em Informações **da Ocorrência,** clique em **Selecionar.**

3. Clique **em Excluir caso.**
