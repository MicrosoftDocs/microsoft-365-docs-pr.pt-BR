---
title: Relatórios do Microsoft 365 no centro de administração-atividade de formulários
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Saiba como obter um relatório de atividades do Microsoft Forms usando o painel de relatórios do Microsoft 365 no centro de administração do Microsoft 365.
ms.openlocfilehash: 843548e77067c7598cfa78ba6fac985237f6f62c
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841108"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Relatórios do Microsoft 365 no centro de administração-atividade de formulários

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para usar o Microsoft Forms examinando sua interação com formulários. Ele também ajuda você a entender o nível de colaboração acontecendo examinando o número de formulários criados e formulários aos quais o usuário respondeu.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Como obter o relatório de atividades de formulários

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione atividade de **formulários** \> **activity** .

## <a name="interpret-the-forms-activity-report"></a>Interpretar o relatório de atividades de formulários

Você pode obter uma visão da atividade formulários do usuário examinando os gráficos **atividade** e **usuários** . 

![Relatório de atividades de formulários](../../media/adminformsactivity.png)

|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório de **atividades de formulários** pode ser exibido para tendências nos últimos sete dias, 30 dias, 90 dias ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |O modo de exibição **usuários** ajuda você a entender a tendência no número de usuários de formulários ativos. Um usuário é considerado ativo se ele ou ela executou uma atividade ao redor de um formulário (criar, editar, exibir, etc.) ou responder a um formulário dentro do período de tempo específico.  <br/> |
|4.  <br/> |O modo de exibição **atividade** ajuda a entender a tendência no número de usuários ativos. Um usuário é considerado ativo quando executa uma atividade de arquivo (salvar, sincronizar, modificar ou compartilhar) ou visita uma página dentro do período específico.<br/> Observação: uma atividade pode ocorrer várias vezes para um único Formulário, mas contará apenas como um formulário ativo. Por exemplo, você pode criar um formulário e continuar a editar o mesmo formulário várias vezes em um período de tempo especificado, mas ele contará apenas como um único Formulário. No entanto, se um usuário enviou várias respostas para o mesmo formulário, cada resposta ainda seria uma resposta individual e, portanto, será contado várias vezes. <br/> |
|5.<br/>|No gráfico **usuários** , o eixo Y é o número de usuários exclusivos. O eixo X é a data em que os usuários exclusivos estão ativos. As legendas são:<br/><br/>**Designers** significa que o usuário criou ou editou um formulário.<br/>**Respondentes** significa que o usuário enviou resposta (s) para um formulário.<br/> **Total de usuários** significa que qualquer pessoa na empresa que tenha sido um designer ou respondente.<br/><br/> No gráfico **atividade** , o eixo Y é a contagem de formulários ou respostas exclusivas. O eixo X é a data em que o formulário ou a atividade de resposta ocorreu. As legendas são:<br/><br/>**Formulários criados** é a contagem de formulários exclusivos que os usuários criaram.<br/> **Respostas** de entrada a contagem de respostas conectadas que os usuários da organização receberam.<br/> **Respostas anônimas** é a contagem de respostas anônimas que os usuários da organização receberam.<br/><br/>|
|6.<br/>|Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico usuários, selecione designers, respondentes ou total de usuários para ver apenas as informações relacionadas a cada um. A alteração dessa seleção não altera as informações na tabela de grade abaixo dela.|
|7.<br/>|A tabela mostra uma divisão das atividades no nível por usuário. As legendas são:<br/><br/>**Username** é o endereço de email do usuário que realizou a atividade no Microsoft Forms.<br/>**Data da última atividade (UTC)** é a última data em que uma atividade de formulário foi executada pelo usuário para o intervalo de datas selecionado. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.<br/><br/>Isso filtrará a tabela para exibir os dados de atividade de arquivo somente para os usuários que realizaram a atividade nesse dia específico.<br/><br/>**Número de formulários criados** é o número de formulários que o usuário criou.<br/> **Número de formulários respondidos** é o número de formulários para os quais o usuário enviou respostas.|
|8.<br/>|Selecione o ícone **gerenciar colunas** para adicionar ou remover colunas do relatório.|
|9.<br/>|Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você faça agregação, classificação e filtragem simples para análise adicional. Se você tiver menos de 100 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 100 usuários, para filtrar e classificar, será necessário exportar os dados.|