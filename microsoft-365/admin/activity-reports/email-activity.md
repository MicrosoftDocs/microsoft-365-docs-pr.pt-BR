---
title: Relatórios do Microsoft 365 no centro de administração-atividade de email
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1cbe2c00-ca65-4fb9-9663-1bbfa58ebe44
description: Saiba como obter um relatório de atividade de email usando o painel de relatórios do Microsoft 365 no centro de administração do Microsoft 365.
ms.openlocfilehash: 2cdf20014b04010e1912fbc41ec6f4ce61eaaca1
ms.sourcegitcommit: 2b626a7924b4be08f6eb21181453b778e6fde418
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2020
ms.locfileid: "43046826"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-activity"></a>Relatórios do Microsoft 365 no centro de administração-atividade de email

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, você pode obter uma visão de alto nível do tráfego de email dentro de sua organização na página Relatórios e, depois, pode analisar para o widget de Atividade de email para entender as tendências e detalhes da atividade de email de cada usuário em sua organização.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios. 

## <a name="how-to-get-to-the-email-activity-report"></a>Como acessar o relatório de atividade de email

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione **atividade de email**do **Exchange** \> .
  
## <a name="interpret-the-email-activity-report"></a>Interpretar o relatório de atividade de email

Você pode observar a atividade de email do usuário examinando os gráficos **Atividade** e **Usuários**. 
  
![Relatório de atividade de email](../../media/21c1e082-317e-4b5e-b736-661ca5744def.png)
  
|||
|:-----|:-----|
|1.  <br/> |O relatório **Atividade de email** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |O gráfico **Atividade** permite que você entenda a tendência da quantidade de atividade de email ocorrendo em sua organização. Você pode entender a divisão de atividades de envio, leitura ou recebimento de email.  <br/> |
|4.  <br/> |O gráfico **Usuário** permite que você entenda a tendência da quantidade de usuários exclusivos que estão gerando as atividades de email. Você pode examinar a tendência de usuários que estão executando atividades de envio, leitura ou recebimento de email.  <br/> |
|5.  <br/> | No gráfico **Atividade**, o eixo Y é a contagem de atividade do tipo email enviado, email recebido e email lido.  <br/>  No gráfico de atividade **Usuários**, o eixo Y é o usuário que está executando a atividade do tipo email enviado, email recebido e email lido.  <br/>  O eixo X em ambos os gráficos é o intervalo de datas selecionado para esse relatório específico.  <br/> |
|6.  <br/> |Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico de **atividade** , selecione **Enviar**, **receber**ou **ler** ![gráficos de filtro para dados](../../media/a3a9cb3d-b8b1-4c6a-9f6f-18aebf74c3a0.png) relacionados específicos para ver apenas as informações relacionadas a cada um. Ao alterar essa seleção, as informações da tabela não mudam.  <br/> |
|7.  <br/> | A tabela mostra uma divisão das atividades de email para cada usuário. Isso mostra todos os usuários com um produto do Exchange atribuído e suas atividades de email. <br/> <br/> **Nome de usuário** é o endereço de email do usuário.  <br/> **Nome para exibição** é o nome completo, se o usuário.  <br/> **Excluído** refere-se ao usuário cujo estado atual é excluído, mas esteve ativo durante uma parte do período do relatório.  <br/> **Data de exclusão** é a data em que o usuário foi excluído.  <br/> **Data da última atividade** refere-se à última vez que o usuário executou uma atividade de leitura ou envio de email.  <br/> **Ações de envio** é o número de vezes que uma ação de envio de email foi gravada para o usuário.  <br/> **Ações de recebimento** é o número de vezes que uma ação de recebimento de email foi gravada para o usuário.  <br/> **Ações de leitura** é o número de vezes que uma ação de leitura de email foi gravada para o usuário.  <br/> **Produto atribuído** são os produtos atribuídos a esse usuário.  <br/>  Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção **como ocultar detalhes de nível de usuário?** nos [relatórios de atividades no centro de administração do Microsoft 365](activity-reports.md).  <br/> |
|8.  <br/> |Você também pode exportar os dados do relatório para um arquivo. csv do Excel, selecionando o link](../../media/816a224b-6ca7-4967-a135-4f6427f64dc8.JPG) de botão **Exportar** ![exportação. Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   
Observação: o relatório de atividade de email está disponível somente para caixas de correio associadas a usuários que têm licenças.
