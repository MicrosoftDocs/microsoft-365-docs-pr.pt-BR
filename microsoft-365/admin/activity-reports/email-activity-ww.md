---
title: Relatórios do Microsoft 365 no centro de administração - Atividade de email
ms.author: kwekua
author: kwekua
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
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Saiba como obter um relatório de atividades de email usando o painel relatórios do Microsoft 365 no centro de administração do Microsoft 365.
ms.openlocfilehash: 65ef74ccd05aa4b55fc127985c03a490bb109b4b
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921916"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Relatórios do Microsoft 365 no centro de administração - Atividade de email

O painel Relatórios  do Microsoft 365 mostra a visão geral das atividades em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, você pode obter uma visão de alto nível do tráfego de email dentro de sua organização na página Relatórios e, depois, pode analisar para o widget de Atividade de email para entender as tendências e detalhes da atividade de email de cada usuário em sua organização.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver os relatórios. 

## <a name="how-to-get-to-the-email-activity-report"></a>Como acessar o relatório de atividade de email

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.
2. Selecione **Exibir Mais** em Atividade de **email.** 
3. Na lista drop-down atividade de **email,** selecione atividade de email do **Exchange** \> .
  
## <a name="interpret-the-email-activity-report"></a>Interpretar o relatório de atividade de email

Você pode observar a atividade de email do usuário examinando os gráficos **Atividade** e **Usuários**. 
  
![Relatório de atividades de email](../../media/5eb1d9e9-8106-4843-acb7-c0238c0da816.png)
  
|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório **Atividade de email** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório geralmente abrangem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |O gráfico **Atividade** permite que você entenda a tendência da quantidade de atividade de email ocorrendo em sua organização. Você pode entender a divisão de envio de email, leitura de email, email recebido, reunião criada ou atividades interagedas da reunião.  <br/> |
|4.  <br/> |O gráfico **Usuário** permite que você entenda a tendência da quantidade de usuários exclusivos que estão gerando as atividades de email. Você pode olhar para a tendência de usuários que estão executando o envio de emails, a leitura de emails, o recebimento de emails, a criação de reuniões ou as atividades de interação da reunião.  <br/> |
|5.  <br/> | No gráfico **Atividade,** o eixo Y é a contagem de atividades do tipo de email enviado, email recebido, email lido, reunião criada e reunião interagido.  <br/>  No gráfico **de atividades** Usuários, o eixo Y é a atividade de execução do usuário do tipo email enviado, email recebido, leitura de email, reunião criada ou reunião interagido.  <br/>  O eixo X em ambos os gráficos é o intervalo de datas selecionado para esse relatório específico.  <br/> |
|6.  <br/> |Você pode filtrar a série que vê no gráfico selecionando um item na legenda.  <br/> |
|7.  <br/> | A tabela mostra uma divisão das atividades de email para cada usuário. Isso mostra todos os usuários com um produto do Exchange atribuído e suas atividades de email. <br/> <br/> **Nome de usuário** é o endereço de email do usuário.  <br/> **O nome** para exibição será o nome completo se o usuário.  <br/> **Excluído** refere-se ao usuário cujo estado atual é excluído, mas esteve ativo durante uma parte do período do relatório.  <br/> **Data de exclusão** é a data em que o usuário foi excluído.  <br/> **Data da última atividade** refere-se à última vez que o usuário executou uma atividade de leitura ou envio de email.  <br/> **Ações de envio** é o número de vezes que uma ação de envio de email foi gravada para o usuário.  <br/> **Ações de recebimento** é o número de vezes que uma ação de recebimento de email foi gravada para o usuário.  <br/> **Ações de leitura** é o número de vezes que uma ação de leitura de email foi gravada para o usuário.  <br/> **Ações criadas de** reunião é o número de vezes que uma ação de envio de solicitação de reunião foi gravada para o usuário.  <br/> **Ações interagedas de** reunião é o número de vezes que uma ação de aceitar, provisão, recusar ou cancelar de uma reunião foi registrada para o usuário.  <br/> **Produto atribuído são** os produtos atribuídos a esse usuário.  <br/>  Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção **Como faço para ocultar detalhes no nível do usuário?** nos Relatórios de Atividades no centro de administração do Microsoft [365.](activity-reports.md)  <br/> |
|8.  <br/> |Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de atividades de email - escolher colunas](../../media/80ffa0ad-61c5-4a6f-8a1d-5f6730ff7da9.png)|
|9.  <br/> |Você também pode exportar os dados do relatório para um arquivo .csv do Excel, selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   
> [!NOTE]
> O relatório de atividades de email só está disponível para caixas de correio associadas a usuários que possuem licenças.
