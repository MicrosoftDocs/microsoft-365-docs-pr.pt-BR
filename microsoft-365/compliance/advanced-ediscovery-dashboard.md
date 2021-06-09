---
title: Advanced eDiscovery painel para conjuntos de revisão
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
description: Use o painel Advanced eDiscovery para conjuntos de revisão para analisar rapidamente seu corpus para identificar tendências ou estatísticas importantes que ajudarão você a desenvolver sua estratégia de revisão.
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741701"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Advanced eDiscovery painel para conjuntos de revisão

Em alguns casos, Advanced eDiscovery, você pode ter um grande volume de documentos e mensagens de email que precisam ser revisadas. Antes de iniciar o processo de revisão, talvez você queira analisar rapidamente seu corpus para identificar tendências ou estatísticas importantes que ajudarão você a desenvolver sua estratégia de revisão. Para fazer isso, você pode usar o painel de Advanced eDiscovery para conjuntos de revisão para analisar rapidamente seu corpus.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Etapa 1: Criar um widget no painel do conjunto de revisão

1. No Centro de Conformidade & segurança, vá para **a > Advanced eDiscovery** de Descoberta > Advanced eDiscovery para exibir a lista de casos em sua organização.
  
2. Selecione um caso existente.
  
3. Clique na **guia Revisar Conjunto** e selecione um conjunto de revisão.
  
4. Na lista **Resultados individuais e na** menu suspenso, clique em **de exibição Pesquisar perfil**. 

   ![DashbordPivot](../media/dashboardpivot.png)

   A **página de exibição de** perfil de pesquisa é exibida; na primeira vez que você exibe essa página, três widgets padrão são exibidos.

   ![Painel](../media/dashboardonly.png)
  
5. Clique no **novo widget** e selecione um dos seguintes itens:

   ![Nova lista de menus suspensos do widget](../media/NewWidgetDropdownBox.png)

   - **Escolha na biblioteca:** Exibe uma biblioteca padrão de widgets. Clique em um widget e clique em **Adicionar** para adicioná-lo aos widgets na **página de exibição de perfil de** pesquisa.
  
   - **Criar widget personalizado:** Exibe uma página de sobrevoo que você pode usar para configurar um widget personalizado. 

6. Para criar um widget personalizado, faça o seguinte na página **Adicionar um flyout** do widget:

   ![Criar Widget](../media/addwidget.png)

    a. Digite um nome para o widget, que é exibido na barra de título do widget. É necessário nomear um widget, mas é útil identificar os dados do widget.

    b. Selecione uma propriedade na lista **suspenso Escolher** pivô que será usada para os dados do widget. Os itens nesta lista são as propriedades pesquisáveis para os itens no conjunto de revisão. Para uma descrição dessas propriedades, consulte [Document metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). As opções dinâmicas do widget estão listadas na coluna **Nome do campo** Pesquisável neste tópico.

    c. Selecione um tipo de gráfico para exibir os dados da propriedade pivô selecionada.

  6. Clique **em Adicionar** para criar o widget personalizado e exibi-lo na página De **exibição de perfil de** pesquisa.

## <a name="step-2-create-a-review-set-search-query"></a>Etapa 2: Criar uma consulta de pesquisa de conjunto de revisão

1. Clique **em ...** na barra de título do widget e clique em Aplicar **condição**.

   ![Painel](../media/searchprofilehome.png)

2. Na página de sobrevoo, clique em um elemento na chave do widget ou no gráfico do widget para criar um filtro.

   ![CreateFilter](../media/applyconditionfilter.png)

3. Repita as etapas 1 a 2 para outros widgets múltiplos widgets. 

4. Quando terminar, clique em **Salvar como consulta** para salvar suas condições como uma nova consulta de pesquisa para o conjunto de revisão.

   ![Consulta](../media/savequery.png)

5. Feche o **exibição de perfil de** pesquisa para retornar ao exibição de resultados da pesquisa.

   Se você tiver criado quaisquer filtros visuais, a consulta resultante será aplicada aos resultados da pesquisa exibidas e a consulta de pesquisa salva na etapa 4 será exibida em Consultas **salvas**. Para obter mais informações sobre consultas de conjunto de revisão, consulte [Query the data in a review set](review-set-search.md).
