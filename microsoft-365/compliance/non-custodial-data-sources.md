---
title: Adicionar fontes de dados não custodial a uma ocorrência de descoberta eletrônica avançada
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
ROBOTS: NOINDEX, NOFOLLOW
description: Você pode adicionar fontes de dados não-custodial a um caso de descoberta eletrônica avançada e colocar uma retenção na fonte de dados. As fontes de dados não custodial são indexadas novamente, de forma que qualquer conteúdo considerado parcialmente indexado é reprocessado para torná-la totalmente e rapidamente pesquisável.
ms.openlocfilehash: 618d39bfb7be6cd260c88cdf4c57501747f440f1
ms.sourcegitcommit: b03a7ad0a80f8b839f40b8d396ab3a049491a12f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44695493"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Adicionar fontes de dados não custodial a uma ocorrência de descoberta eletrônica avançada

Em casos de descoberta eletrônica avançada, nem sempre atende às suas necessidades para associar uma fonte de dados do Microsoft 365 a um funcionário no caso. Mas talvez ainda seja necessário associar esses dados a um caso para que você pesquise, adicione-o ao conjunto de revisão e revise-o. O novo recurso chamado de *fontes de dados não-custodial* permite que você adicione dados a um caso sem precisar associar os dados a um funcionário. Ele também aplica a mesma funcionalidade de descoberta eletrônica avançada a dados não-custodial que estão disponíveis para dados associados aos usuários. Dois dos recursos mais úteis que você pode aplicar a dados não custodial estão colocando-o em espera e processando-o usando [indexação avançada](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Adicionar uma fonte de dados não custodial

Siga estas etapas para adicionar e gerenciar fontes de dados não custodial em uma ocorrência de descoberta eletrônica avançada.

1. Na home page de **descoberta eletrônica avançada** , clique na ocorrência à qual você deseja adicionar os dados.

2. Na página **fontes** , clique na guia **locais dos dados** e, em seguida, clique em **Adicionar local de dados**.

3. Clique em **Adicionar local de dados** e escolha as fontes de dados que você deseja adicionar ao caso. Você pode adicionar várias caixas de correio e sites.

4. Na página **escolher locais** no assistente, adicione caixas de correio ou sites (ou ambos) como fontes de dados não-custodial ao caso.

5. Após adicionar as fontes de dados, clique em **Avançar**.

6. Na página **local** , escolha as fontes de dados que você deseja colocar em espera marcando ou desmarcando a caixa de seleção associada.

7. Verifique as seleções de retenção e clique em **Enviar**.

   Cada fonte de dados não-custodial adicionada é listada na página **fontes de dados** .

   Além disso, um trabalho chamado *reindexação de dados não-custodial* é criado e exibido na guia **trabalhos** do caso. Depois que o trabalho é criado, o processo de indexação avançada em iniciado e as fontes de dados são re-indexado.

## <a name="managing-the-hold-on-non-custodial-data-sources"></a>Gerenciando a espera em fontes de dados não-custodial

Depois que você coloca uma retenção em uma fonte de dados não custodial, uma política de retenção que contém todas as fontes de dados não custodial para o caso é criada automaticamente. Quando você coloca outras fontes de dados não-custodial em espera, elas são adicionadas a essa política de retenção.

1. Na **Home** Page do caso, clique na guia **isenções** .

2. Na página **isenções** , clique em **NCDSHold- \<GUID\> **, onde o valor de GUID é exclusivo do caso.

3. Na página do menu suspenso, clique em **Editar retenção** para exibir todas as fontes de dados não custodial que são colocadas em espera.

Você pode executar a seguinte tarefa de gerenciamento em fontes de dados não-custodial:

- Você pode editar a isenção para criar uma retenção baseada em consulta que é aplicada a todas as fontes de dados não-custodial no caso.

- Você pode liberar uma fonte de dados não custodial da isenção. Liberar uma fonte de dados não remove a fonte de dados não custodial da ocorrência. Ela apenas remove a retenção que foi colocada na fonte de dados.
