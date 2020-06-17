---
title: Painel de descoberta eletrônica avançado para conjuntos de análise
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
description: Use o painel avançado de descoberta eletrônica para conjuntos de análise para analisar rapidamente seus corpus para identificar tendências ou estatísticas importantes que ajudarão você a desenvolver sua estratégia de análise.
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741701"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Painel de descoberta eletrônica avançado para conjuntos de análise

Para alguns casos na descoberta eletrônica avançada, você pode ter um grande volume de documentos e mensagens de email que precisam ser revisados. Antes de iniciar o processo de revisão, talvez você queira analisar rapidamente seu corpus para identificar tendências ou estatísticas importantes que ajudarão você a desenvolver sua estratégia de análise. Para fazer isso, você pode usar o painel de descoberta eletrônica avançado para conjuntos de revisão para analisar rapidamente seus corpus.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Etapa 1: criar um widget no painel de análise de revisão

1. No centro de conformidade de & de segurança, acesse **descoberta eletrônica avançada > eDiscovery** para exibir a lista de casos em sua organização.
  
2. Selecione um caso existente.
  
3. Clique na guia **conjunto de revisão** e selecione um conjunto de revisão.
  
4. Na lista suspensa de **resultados individuais** , clique em **modo de exibição de perfil de pesquisa**. 

   ![DashbordPivot](../media/dashboardpivot.png)

   A página de **exibição do perfil de pesquisa** é exibida; na primeira vez que você exibir esta página, três widgets padrão serão exibidos.

   ![Painel](../media/dashboardonly.png)
  
5. Clique no **widget novo** e selecione um dos seguintes itens:

   ![Nova lista suspensa de widget](../media/NewWidgetDropdownBox.png)

   - **Escolha na biblioteca:** Exibe uma biblioteca de widgets padrão. Você clica em um widget e, em seguida, clica em **Adicionar** para adicioná-lo aos widgets na página de **exibição do perfil de pesquisa** .
  
   - **Criar widget personalizado:** Exibe uma página de submenu que você pode usar para configurar um widget personalizado. 

6. Para criar um widget personalizado, faça o seguinte na página **Adicionar** submenu do widget:

   ![Criar widget](../media/addwidget.png)

    a. Digite um nome para o widget, que é exibido na barra de título do widget. É necessário nomear um widget, mas é útil identificar os dados do widget.

    b. Selecione uma propriedade na lista suspensa **Escolher tabela** suspensa que será usada para os dados do widget. Os itens nesta lista são as propriedades pesquisáveis para os itens no conjunto de revisão. Para obter uma descrição dessas propriedades, confira [campos de metadados de documentos na descoberta eletrônica avançada](document-metadata-fields-in-Advanced-eDiscovery.md). As opções de tabela dinâmica do widget estão listadas na coluna **nome do campo pesquisável** neste tópico.

    c. Selecione um tipo de gráfico para exibir os dados da propriedade dinâmica selecionada.

  6. Clique em **Adicionar** para criar o widget personalizado e exibi-lo na página **Exibir Perfil de pesquisa** .

## <a name="step-2-create-a-review-set-search-query"></a>Etapa 2: criar uma consulta de pesquisa do conjunto de análise

1. Clique em **...** na barra de título do widget e, em seguida, clique em **aplicar condição**.

   ![Painel](../media/searchprofilehome.png)

2. Na página do menu suspenso, clique em um elemento na chave do widget ou no gráfico de widget para criar um filtro.

   ![Createfilter](../media/applyconditionfilter.png)

3. Repita as etapas 1-2 para outros widgets vários widgets. 

4. Quando tiver concluído, clique em **salvar como consulta** para salvar suas condições como uma nova consulta de pesquisa para o conjunto de análise.

   ![Consulta](../media/savequery.png)

5. Feche o **modo de exibição perfil de pesquisa** para retornar ao modo de exibição resultados da pesquisa.

   Se você tiver criado filtros visuais, a consulta resultante será aplicada aos resultados da pesquisa exibidos, e a consulta de pesquisa salva na etapa 4 será exibida em **consultas salvas**. Para obter mais informações sobre as consultas de análise de revisão, consulte [consultar os dados em um conjunto de revisão](review-set-search.md).
