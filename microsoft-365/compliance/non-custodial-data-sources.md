---
title: Adicionar fontes de dados não custodial a um caso de Descoberta Avançada
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
description: Você pode adicionar fontes de dados não custodial a um caso de Descoberta eDiscovery Avançada e colocar em espera a fonte de dados. Fontes de dados não custodial são reindexadas, portanto, qualquer conteúdo marcado como parcialmente indexado é reprocessado para torná-lo completamente e rapidamente pesquisável.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740348"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Adicionar fontes de dados não custodial a um caso de Descoberta Avançada

Em casos de Descoberta Avançada, nem sempre ela atenderá às suas necessidades de associar uma fonte de dados do Microsoft 365 a um custodiante no caso. Mas talvez ainda seja necessário associar esses dados a uma ocorrência para que você possa pesquisá-los, adicioná-los a um conjunto de revisão e analisá-los e revisá-los. O recurso na Descoberta Avançada  é chamado de fontes de dados não custodial e permite adicionar dados a uma ocorrência sem precisar associá-los a um custodiante. Também se aplica a mesma funcionalidade de Descoberta Avançada a dados não custodial que estão disponíveis para dados associados ao custodiante. Duas das coisas mais úteis que você pode aplicar a dados não custodial é colocá-los em espera e processá-los usando [indexação avançada.](indexing-custodian-data.md)

## <a name="add-a-non-custodial-data-source"></a>Adicionar uma fonte de dados não custodial

Siga estas etapas para adicionar e gerenciar fontes de dados não custodial em um caso de Descoberta Avançada.

1. Na home page **Da Descoberta Avançada,** clique na ocorrência à que você deseja adicionar os dados.

2. Clique na **guia Fontes de dados** e clique em Adicionar fonte de **dados** Adicionar locais  >  **de dados.**

3. Na página do sub-subconsiência Novos locais de dados sem custodiante, escolha as fontes de dados que você deseja adicionar à ocorrência.  Você pode adicionar várias caixas de correio e sites expandindo as seções **do SharePoint** ou **do Exchange** e clicando em **Editar.**

   ![Adicionar sites do SharePoint e caixas de correio do Exchange como fontes de dados não custodial](../media/NonCustodialDataSources1.png)

   - **SharePoint** - Clique **em Editar** para adicionar sites. Selecione um site na lista ou pesquise um site digitando a URL do site na barra de pesquisa. Selecione os sites que você deseja adicionar como fontes de dados não custodiante e clique em **Adicionar**.

   - **Exchange** - Clique **em Editar** para adicionar caixas de correio. Digite um nome ou alias (no mínimo três caracteres) na caixa de pesquisa para caixas de correio ou grupos de distribuição. Selecione as caixas de correio que você deseja adicionar como fontes de dados não custodiante e clique em **Adicionar**.

   > [!NOTE]
   > Você pode usar as seções do **SharePoint** e do **Exchange** para adicionar sites e caixas de correio associadas a uma equipe ou grupo do Yammer como fontes de dados não custodial. Você precisa adicionar separadamente a caixa de correio e o site associados a uma equipe ou grupo do Yammer.

4. Depois de adicionar fontes de dados não custodial, você tem a opção de colocar esses locais em espera ou não. Marque ou desmarque a **caixa de** seleção De espera ao lado da fonte de dados para mantê-la em espera.

5. Clique **em Adicionar** na parte inferior da página **do** sub-menu Novos locais de dados sem custodiante para adicionar as fontes de dados à ocorrência.

   Cada fonte de dados não custodial que você adicionou está listada na **página Fontes de** dados. As fontes de dados não custodial são identificadas pelo valor **do** local dos dados na coluna **Tipo de** origem.

   ![Fontes de dados não custodial na guia Fontes de dados](../media/NonCustodialDataSources2.png)

Depois de adicionar fontes de dados não custodial ao caso, um trabalho chamado *Reindexação* de dados não custodial é criado e exibido na guia Trabalhos do caso.  Depois que o trabalho é criado, o processo de indexação Avançada é iniciado e as fontes de dados são reindexadas.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Gerenciar a responsabilidade por fontes de dados não custodial

Depois de colocar em espera uma fonte de dados não custodial, uma política de suspensão que contém as fontes de dados não custodial para o caso é criada automaticamente. Quando você coloca outras fontes de dados não custodial em espera, elas são adicionadas a essa política de espera.

1. Abra a ocorrência de Descoberta Avançada e selecione **a** guia Espera.

2. Clique **em NCDSHold- \<GUID\>**, onde o valor de GUID é exclusivo para a ocorrência.

   A página de subconsiência exibe informações e estatísticas sobre as fontes de dados não custodial em espera.

   ![A página de subconsiência para fontes de dados não custodial em espera exibe estatísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Clique **em Editar espera** para exibir as fontes de dados não custodial colocadas em espera e executar as seguintes tarefas de gerenciamento:

   - Na página **Locais,** você pode liberar uma fonte de dados não custodial removendo-a da espera. Liberar uma fonte de dados não remove a fonte de dados não custodial do caso. Ela apenas remove a espera que foi colocada na fonte de dados.

   - Na página **Consulta,** você pode editar a isenção para criar uma isenção baseada em consulta que é aplicada a todas as fontes de dados não custodial no caso.
