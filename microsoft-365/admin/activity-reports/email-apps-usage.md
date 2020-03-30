---
title: Relatórios do Microsoft 365 no centro de administração-uso de aplicativos de email
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
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Saiba como obter o relatório de uso de aplicativos de email para saber mais sobre os aplicativos de email que se conectam ao Exchange Online e os usuários da versão do Outlook estão usando o.
ms.openlocfilehash: 5bdd62d150cf103cd3c3520cf5a0c593dceb8e66
ms.sourcegitcommit: 2b626a7924b4be08f6eb21181453b778e6fde418
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2020
ms.locfileid: "43046850"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Relatórios do Microsoft 365 no centro de administração-uso de aplicativos de email

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md). No relatório de uso de aplicativos de email, você pode ver quantos aplicativos de email estão se conectando ao Exchange Online. Você também pode ver as informações de versão dos aplicativos do Outlook que os usuários estão usando, que permitem o acompanhamento com aqueles que estão usando versões sem suporte para instalar versões com suporte do Outlook.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Como acessar o relatório de aplicativos de email

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione o **uso do aplicativo de email**do **Exchange** \> .
  
## <a name="interpret-the-email-apps-report"></a>Interpretar o relatório de aplicativos de email

Você pode obter uma visão da atividade aplicativos de email examinando os gráficos **usuários** e **clientes** . 
  
![Clientes de email usados](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |O relatório de **uso de aplicativos de email** pode ser exibido para tendências nos últimos sete dias, 30 dias, 90 dias ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |O modo de exibição **Usuários** mostra o número de usuários exclusivos conectados ao Exchange Online usando qualquer aplicativo de email.  <br/> |
|4.  <br/> |O modo de exibição de **Aplicativos** mostra o número de usuários únicos por aplicativo no intervalo de tempo selecionado.  <br/> |
|5.  <br/> |O modo de exibição de **versões** mostra o número de usuários exclusivos para cada versão do Outlook no Windows.  <br/> |
|6.  <br/> | No gráfico **Usuários**, o eixo Y é a contagem total de usuários exclusivos conectados a um aplicativo em um dia do período do relatório.  <br/>  No gráfico **Usuários**, o eixo X é o número de usuários exclusivos que usaram o aplicativo nesse período do relatório.  <br/>  No gráfico **Aplicativos**, o eixo Y é a contagem total de usuários únicos que usaram um aplicativo específico durante o período do relatório.  <br/>  No gráfico **Aplicativos**, o eixo X é a lista de aplicativos em sua organização.  <br/>  No gráfico **Versões**, o eixo Y é a contagem total de usuários exclusivos usando uma versão específica da área de trabalho do Outlook. Se o relatório não puder resolver o número de versão do Outlook, a quantidade mostrará como Indeterminada.  <br/>  No gráfico **Versões**, o eixo X é a lista de aplicativos em sua organização.  <br/> |
|7.  <br/> |Você pode filtrar a série que vê no gráfico por selectingan item na legenda. Por exemplo, no gráfico **usuários** , selecione **Mac mail** ou lista de clientes de email do **Outlook** ![. Selecione o cliente de email para obter mais dados de relatório no cliente.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) para ver apenas as informações relacionadas a cada um deles. Ao alterar essa seleção, as informações da tabela não mudam. Mac Mail, Outlook para Mac, Outlook Mobile, Outlook para área de trabalho e Outlook na Web são exemplos de aplicativos de email que talvez você tenha em sua organização.  <br/> |
|8.  <br/> | É possível que você não veja todos os itens da lista abaixo nas colunas até que os adicione.<br/> **Username** é o nome do proprietário do aplicativo de email.  <br/> A **data da última atividade** é a última data em que o usuário leu ou enviou uma mensagem de email.  <br/> **Mac mail**, **Outlook para Mac** e **Outlook**, **Outlook Mobile** e **Outlook na Web** são exemplos de aplicativos de email que talvez você tenha em sua organização.  <br/>  Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção **como ocultar detalhes de nível de usuário?** nos [relatórios de atividades no centro de administração do Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Selecione **gerenciar colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de uso de aplicativos de email-escolher colunas](../../media/c17b2a5c-db41-474a-8334-0e5a621b2f16.png)|
|10.  <br/> |Você também pode exportar os dados do relatório para um arquivo. csv do Excel, selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   

