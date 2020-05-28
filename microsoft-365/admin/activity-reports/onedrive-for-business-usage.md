---
title: Relatórios do Microsoft 365 no centro de administração-uso do OneDrive for Business
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: 'Obter o relatório de uso do OneDrive for Business para saber mais sobre o número total de arquivos e armazenamento usados em toda a organização. '
ms.openlocfilehash: 84c76e564067f2580455296a1ed4d1159de7d44c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387544"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Relatórios do Microsoft 365 no centro de administração-uso do OneDrive for Business

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, o cartão do OneDrive no painel oferece uma visão geral de alto nível do valor que você obtém do OneDrive for Business em termos de armazenamento e número total de arquivos usados em sua organização. Você pode então aprofundar-se para entender as tendências de contas ativas do OneDrive, com quantos arquivos os usuários interagem, bem como o armazenamento utilizado. Ele também fornece detalhes de cada usuário do OneDrive.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Como posso obter o relatório de uso do OneDrive?

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione uso do **onedrive** \> **Usage**. 
  
## <a name="interpret-the-onedrive-usage-report"></a>Entenda o relatório de uso do OneDrive

Você pode obter uma visão de uso do OneDrive for Business examinando as exibições **Sites**, **Arquivos** e **Armazenamento**. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|||
|:-----|:-----|
|1.  <br/> |O relatório de **Uso do OneDrive** mostra as tendências nos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas. <br/>|
|3.  <br/> |A visualização **Contas** mostra a tendência no número de contas do OneDrive total e ativas. "Contas ativas" são aquelas em que os usuários visualizam, modificam, carregam, baixam, compartilham ou sincronizam arquivos.  <br/> |
|4.  <br/> |A visualização **Arquivos** mostra o número de arquivos total e ativos. Um arquivo será considerado ativo se tiver sido salvo, sincronizado, modificado ou compartilhado dentro do período de tempo específico.  <br/> Observação: uma atividade de arquivo pode ocorrer várias vezes para um único arquivo, mas contará somente como um arquivo ativo. Por exemplo, você pode salvar e sincronizar o mesmo arquivo várias vezes durante um período especificado, mas isso contará somente como um único arquivo ativo e um único arquivo sincronizado nos dados.           |
|5.  <br/> |A visualização **Armazenamento** mostra a tendência na quantidade de armazenamento que você está utilizando no OneDrive.  <br/> > Observação: o tamanho inclui qualquer versão e metadados associados aos arquivos.           |
|6.  <br/> | No gráfico **Contas**, o eixo Y é o número de contas do OneDrive.  <br/>  No gráfico **Arquivos**, o eixo Y é o número de arquivos armazenados no OneDrive.  <br/>  No gráfico **Armazenamento**, o eixo Y é a quantidade de armazenamento usado para contas do OneDrive.  <br/>  O eixo X em todos os gráficos é o intervalo de datas selecionado para esse relatório específico.  <br/> |
|7.  <br/> |Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **arquivos** , selecione **total de arquivos** ou **arquivos ativos**. No gráfico **contas** , selecione **total de contas** ou **contas ativas**. Ou no gráfico de **armazenamento** , selecione **armazenamento usado**. Alterar sua seleção não modifica as informações na tabela.  <br/> |
|8.  <br/> | A tabela mostra um detalhamento de dados para cada OneDrive do usuário. Para aparecer na tabela, um usuário precisa ter uma licença de produto que inclua o OneDrive, e também precisa ter o SharePoint Online ligado. O usuário também tem que fazer login no cliente de sincronização do OneDrive ou ir até o OneDrive por meio de um navegador da web.  <br/>  Se o OneDrive tiver atividade de arquivo, ele apresentará a data mais recente em que a atividade foi executada. As linhas na tabela são ordenadas pela **Data da última atividade**, de modo que o OneDrive com a atividade de arquivo mais recente aparecerá no topo da lista.  <br/>  Você pode adicionar ou remover colunas da tabela.  <br/> ![Opções de coluna](../../media/onedriveusage-columns.png)  <br/> **URL** é o endereço da Web para o onedrive do usuário.  <br/> **Excluído** é o status de exclusão do OneDrive. Demora pelo menos 7 dias para as contas serem marcadas como excluídas.  <br/> **Proprietário** é o nome de usuário do administrador principal do OneDrive.  <br/> **Nome principal do proprietário** é o endereço de email do proprietário do onedrive.  <br/> **Data da última atividade (UTC)** é a data mais recente em que uma atividade foi realizada no OneDrive. Se o OneDrive não teve atividade de arquivo, o valor ficará em branco.  <br/> **Arquivos** é o número de arquivos no OneDrive.  <br/> **Arquivos ativos** é o número de arquivos ativos em um período de tempo. Um arquivo será considerado ativo se tiver sido salvo, sincronizado, modificado ou compartilhado dentro do período de tempo selecionado.  <br/> Observação: uma atividade de arquivo pode ocorrer várias vezes para um único arquivo, mas contará somente como um arquivo ativo. Por exemplo, você pode salvar e sincronizar o mesmo arquivo várias vezes durante um período especificado, mas isso contará somente como um único arquivo ativo e um único arquivo sincronizado nos dados. >  Se os arquivos tiverem sido removidos durante o período de tempo especificado para o relatório, o número de arquivos ativos mostrados no relatório poderá ser maior do que o número atual de arquivos no OneDrive. >  Usuários excluídos continuarão a ser exibidos em relatórios por 180 dias.<br/>**Armazenamento utilizado (MB)** é o montante de armazenamento em MB que o OneDrive utiliza. Isto inclui todas as versões e metadados associadas aos arquivos.  <br/>  Se as políticas da sua organização impedem você de exibir relatórios onde as informações do usuário são identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **como ocultar detalhes de nível de usuário?** nos [relatórios de atividades no centro de administração do Microsoft 365 Preview](activity-reports.md).  <br/> |
|9.  <br/> |Selecione o ícone **gerenciar colunas** ![ gerenciar colunas ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) para adicionar ou remover colunas do relatório.  <br/> |
|10.  <br/> |Você também pode exportar os dados do relatório para um arquivo. csv do Excel, selecionando o link de **exportação** . Isso exporta os dados de cada OneDrive e permite que você realize uma classificação e filtragem simples para análises adicionais. Se você tiver menos de 2000 contas OneDrive, poderá classificar e filtrar dentro da tabela, no próprio relatório. Se você tiver mais de 2000 contas OneDrive, precisará exportar os dados para filtrar e classificar.  <br/> Observação: quando os dados são exportados para um arquivo do Excel, observe que a data em que o relatório de conteúdo foi gerado é refletida no arquivo nos **dados** da coluna.  <br/> |
|||
   

