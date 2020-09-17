---
title: Relatórios do Microsoft 365 no centro de administração – atividade do Forms pro
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
description: Saiba como obter um relatório de atividades do Microsoft Forms pro usando o painel de relatórios do Microsoft 365 no centro de administração do Microsoft 365.
ms.openlocfilehash: 58c7a76c49b7c925a4e7851f7e81c7f47d465d3a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949187"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-pro-activity"></a>Relatórios do Microsoft 365 no centro de administração – atividade do Forms pro

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para usar o Microsoft Forms pro examinando suas interações com o Forms pro. Ele também ajuda você a entender o nível de colaboração que está acontecendo observando o número de pesquisas de pro criadas e pro pesquisas às quais os usuários responderam. 
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Como obter o relatório de atividades do Forms pro

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione atividade do **Forms pro** \> **activity**.

## <a name="interpret-the-forms-activity-report"></a>Interpretar o relatório de atividades de formulários

Você pode obter um modo de exibição da atividade de formulários do seu usuário, examinando os gráficos de **atividade** e **usuários** . 

![Relatório de atividades de formulários](../../media/formsproactivity.png)

|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório de atividades do **Forms pro** pode ser exibido para tendências nos últimos sete dias, 30 dias, 90 dias ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).   <br/> |
|2.  <br/> |Os dados em cada relatório normalmente são tão recentes quanto as últimas 48 horas.  <br/> |
|3.  <br/> |O modo de exibição **usuários** ajuda você a entender a tendência no número de usuários do Active Forms pro. Um usuário é considerado ativo se ele tiver executado uma atividade em uma pesquisa pro (criar, editar, exibir, etc.) dentro do período de tempo específico.  <br/> |
|4.  <br/> |O modo de exibição **atividade** ajuda a entender a tendência no número de usuários ativos. Um usuário é considerado ativo quando executa uma atividade de arquivo (salvar, sincronizar, modificar ou compartilhar) ou visita uma página dentro do período específico.<br/> Observação: uma atividade pode ocorrer várias vezes para uma única pesquisa, mas contará apenas como uma pesquisa ativa. Por exemplo, você pode criar uma pesquisa pro e continuar a editar a mesma pesquisa várias vezes em um período de tempo especificado, ela contará apenas como uma única pesquisa. <br>|
|5.<br/>|No gráfico **usuários** , o eixo Y é o número de usuários exclusivos. O eixo X é a data em que os usuários exclusivos estão ativos. As legendas são:<br/><br/>**Designers** significa que o usuário criou ou editou uma pesquisa do Forms pro.<br><br>No gráfico **atividade** , o eixo Y é a contagem de respostas de formulários pro por pesquisa. O eixo X é a data em que a pesquisa ou a atividade de resposta ocorreu. As legendas são:<br/><br/>As **pesquisas criadas** são a contagem de pesquisas únicas de formulários pro que os usuários criaram<br>**Respostas** é a contagem de respostas anônimas ou não anônimas que os usuários que receberam a pesquisa enviaram. |
|6.<br/>|Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico usuários, selecione designers, respondentes ou total de usuários para ver apenas as informações relacionadas a cada um. A alteração dessa seleção não altera as informações na tabela de grade abaixo dela.|
|7.<br/>|A tabela mostra uma divisão das atividades no nível por usuário. As legendas são:<br/><br/>**Username** é o endereço de email do usuário que realizou a atividade no Microsoft Forms.<br/>**Data da última atividade (UTC)** é a última data em que uma atividade de formulário foi executada pelo usuário para o intervalo de datas selecionado. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.<br/>Isso filtrará a tabela para exibir os dados de atividade de arquivo somente para os usuários que realizaram a atividade nesse dia específico.<br/><br/>**Número de pesquisas criadas** é o número de pesquisas criadas pelo usuário.<br/> **Número de respostas da pesquisa** é o número de respostas de respondentes aos quais a pesquisa foi distribuída.|
|8.<br/>|Selecione o ícone **gerenciar colunas** para adicionar ou remover colunas do relatório.|
|9.<br/>|Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você faça agregação, classificação e filtragem simples para análise adicional. Se você tiver menos de 100 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 100 usuários, para filtrar e classificar, será necessário exportar os dados.|