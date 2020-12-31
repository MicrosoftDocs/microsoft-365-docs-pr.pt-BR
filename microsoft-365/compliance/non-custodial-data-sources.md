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
description: Você pode adicionar fontes de dados não-custodial a um caso de descoberta eletrônica avançada e colocar uma retenção na fonte de dados. As fontes de dados que não são do custodial são reindexada, de forma que qualquer conteúdo que foi marcado como parcialmente indexado é reprocessado para torná-la totalmente e rapidamente pesquisável.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740348"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a>Adicionar fontes de dados não custodial a uma ocorrência de descoberta eletrônica avançada

Em casos de descoberta eletrônica avançada, nem sempre atende às suas necessidades para associar uma fonte de dados do Microsoft 365 a um funcionário no caso. Mas talvez você ainda precise associar esses dados a um caso para que possa procurá-los, adicioná-los a um conjunto de análise e analisá-los e examiná-los. O recurso na descoberta eletrônica avançada é chamado de *fontes de dados não-custodial* e permite que você adicione dados a um caso sem precisar associá-lo a um funcionário. Ele também aplica a mesma funcionalidade de descoberta eletrônica avançada a dados não-custodial que estão disponíveis para dados associados aos usuários. Duas das coisas mais úteis que você pode aplicar a dados não-custodial estão colocando-o em espera e processando-o usando [indexação avançada](indexing-custodian-data.md).

## <a name="add-a-non-custodial-data-source"></a>Adicionar uma fonte de dados não custodial

Siga estas etapas para adicionar e gerenciar fontes de dados não custodial em uma ocorrência de descoberta eletrônica avançada.

1. Na home page de **descoberta eletrônica avançada** , clique na ocorrência à qual você deseja adicionar os dados.

2. Clique na guia **fontes de dados** e, em seguida, clique em **Adicionar fonte de dados**  >  **Adicionar locais de dados**.

3. Na página novo submenu de **locais de dados não custodial** , escolha as fontes de dados que você deseja adicionar ao caso. Você pode adicionar várias caixas de correio e sites expandindo as seções do **SharePoint** ou do **Exchange** e clicando em **Editar**.

   ![Adicionar sites do SharePoint e caixas de correio do Exchange como fontes de dados não custodial](../media/NonCustodialDataSources1.png)

   - **SharePoint** – clique em **Editar** para adicionar sites. Selecione um site na lista ou você pode pesquisar um site digitando a URL do site na barra de pesquisa. Selecione os sites que você deseja adicionar como fontes de dados não responsáveis e clique em **Adicionar**.

   - **Exchange** -clique em **Editar** para adicionar caixas de correio. Digite um nome ou alias (no mínimo três caracteres) na caixa de pesquisa para caixas de correio ou grupos de distribuição. Selecione as caixas de correio que você deseja adicionar como fontes de dados não responsáveis e clique em **Adicionar**.

   > [!NOTE]
   > Você pode usar as seções do **SharePoint** e do **Exchange** para adicionar sites e caixas de correio associadas a uma equipe ou a um grupo do Yammer como fontes de dados não custodial. Você precisa adicionar separadamente a caixa de correio e o site associados a uma equipe ou a um grupo do Yammer.

4. Após adicionar fontes de dados não-custodial, você tem a opção de colocar esses locais em espera ou não. Marque ou desmarque a caixa de seleção **reter** ao lado da fonte de dados para colocá-la em espera.

5. Clique em **Adicionar** na parte inferior da página do submenu **novo locais de dados não-custodial** para adicionar as fontes de dados ao caso.

   Cada fonte de dados não-custodial adicionada é listada na página **fontes de dados** . Fontes de dados não custodial são identificadas pelo valor de **local dos dados** na coluna **tipo de fonte** .

   ![Fontes de dados não custodial na guia fontes de dados](../media/NonCustodialDataSources2.png)

Após adicionar fontes de dados não-custodial ao caso, um trabalho chamado *reindexação de dados não-custodial* é criado e exibido na guia **trabalhos** da ocorrência. Depois que o trabalho é criado, o processo de indexação avançada em iniciado e as fontes de dados são reindexados.

## <a name="manage-the-hold-for-non-custodial-data-sources"></a>Gerenciar a retenção de fontes de dados não custodial

Depois de colocar uma retenção em uma fonte de dados não custodial, uma política de retenção que contém as fontes de dados não custodial para o caso é criada automaticamente. Quando você coloca outras fontes de dados não-custodial em espera, elas são adicionadas a essa política de retenção.

1. Abra o caso de descoberta eletrônica avançada e selecione a guia **reter** .

2. Clique em **NCDSHold \<GUID\> -**, onde o valor de GUID é exclusivo do caso.

   A página de submenu exibe informações e estatísticas sobre as fontes de dados não custodial em espera.

   ![A página de submenu de fontes de dados não custodial exibe as estatísticas](../media/NonCustodialDataSourcesHoldFlyout.png)

3. Clique em **Editar retenção** para exibir as fontes de dados não custodial colocadas em espera e execute as seguintes tarefas de gerenciamento:

   - Na página **locais** , você pode liberar uma fonte de dados não custodial removendo-a da isenção. Liberar uma fonte de dados não remove a fonte de dados não custodial da ocorrência. Ela apenas remove a retenção que foi colocada na fonte de dados.

   - Na página **consulta** , você pode editar a isenção para criar uma retenção baseada em consulta que é aplicada a todas as fontes de dados não-custodial do tha no caso.
