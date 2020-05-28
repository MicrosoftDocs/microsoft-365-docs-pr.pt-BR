---
title: Relatórios do Microsoft 365 no centro de administração-relatório de atividades de grupos do Yammer
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.assetid: 94dd92ec-ea73-43c6-b51f-2a11fd78aa31
description: Obtenha o relatório de atividades de grupos do Yammer para saber mais sobre o número de grupos do Yammer que estão sendo criados e usados na sua organização, além de suas atividades.
ms.openlocfilehash: a5a9d3d8820241cc3d99a4a08e647bd05dafd5ef
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387436"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-groups-activity-report"></a>Relatórios do Microsoft 365 no centro de administração-relatório de atividades de grupos do Yammer

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md). No relatório de atividades de grupos do Yammer, é possível obter informações sobre as atividades de grupos do Yammer em sua organização e ver quantos grupos do Yammer estão sendo criados e usados.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.  

## <a name="how-to-get-to-the-yammer-groups-activity-report"></a>Como acessar o relatório de atividades de grupos do Yammer

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione atividade de **Yammer** \> **grupos**do Yammer.
  
## <a name="interpret-the-yammer-groups-activity-report"></a>Interpretar o relatório de atividades de grupos do Yammer

Você pode verificar as atividades de grupos do Yammer, examinando os gráficos **Grupos** e **Atividades**.<br/>![Yammer groups activity chart](../../media/4ba4ea03-2f74-4d86-8c63-2b18477c9769.png)
  
|||
|:-----|:-----|
|1.  <br/> |O relatório **Atividades de grupos do Yammer** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas. <br/> |
|3.  <br/> |O modo de exibição **Grupos** mostra o número total de grupos que existiam e quantos realizaram atividades de conversa de grupo.  <br/> |
|4.  <br/> |O modo de exibição **Atividades** mostra o número de mensagens do Yammer que foram postadas, lidas e curtidas em grupos.  <br/> |
|5.  <br/> | No gráfico **Grupos**, o eixo Y é a quantidade de grupos ativos ou totais.  <br/>  No gráfico **Atividades**, o eixo Y é a contagem de atividade especificadas para grupos do Yammer.  <br/>  O eixo X em todos os três gráficos é o intervalo de datas selecionado para esse relatório específico.  <br/> |
|6.  <br/> |Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **grupos** **, selecione total** ou total de ícones **ativos** ![ e ativos ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) para ver apenas as informações relacionadas a cada um.   Ao alterar essa seleção, as informações da tabela não mudam.  <br/> |
|7.  <br/> | A lista de grupos a ser mostrada é determinada pelo conjunto de todos os grupos que existiram (que não foram excluídos) no mais amplo período de relatório (180 dias). A contagem de atividades (mensagens recebidas) variará de acordo com a seleção de data.  <br/> Observação: Talvez você não veja todos os itens da lista abaixo nas colunas até que os adicione.<br/>**Nome do grupo** é o nome do grupo.  <br/> **Administrador de grupo** é o nome do administrador ou proprietário do grupo.  <br/> **Excluídos** é o número de grupos do Yammer que foram excluídos. Se o grupo for excluído, mas tiver atividades no período do relatório, elas serão exibidas na grade com esse sinalizador definido como true.  <br/> **Tipo** é o tipo de grupo: público ou privado.  <br/> **Conectado ao Office 365** indica se o grupo Yammer também é um grupo do Microsoft 365.  <br/> A **data da última atividade** é a última data em que uma mensagem foi lida, postada ou curtida pelo grupo.  <br/> **Membros** é o número de membros do grupo.  <br/> **Postadas** é o número de mensagens postadas no grupo do Yammer durante o período do relatório.  <br/> **Lidas** é o número de mensagens lidas no grupo do Yammer durante o período do relatório.  <br/> **Curtidas** é o número de mensagens curtidas no grupo do Yammer durante o período do relatório.  <br/>  Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção **como ocultar detalhes de nível de usuário?** em [relatórios de atividades no centro de administração do Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Selecione **colunas** para adicionar ou remover colunas do relatório.  <br/> ![Yammer groups activity - choose columns](../../media/31bd549b-363d-4888-a45d-7af6fedb3588.png)|
|9.  <br/> |Você também pode exportar os dados do relatório para um arquivo. csv do Excel, selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   

