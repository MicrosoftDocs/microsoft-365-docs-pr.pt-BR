---
title: Relatórios do Microsoft 365 no centro de administração - uso do site do SharePoint
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
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
- SPO160
- BSA160
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'Obter o relatório de uso do site do SharePoint para saber quantos arquivos os usuários armazenam em sites do SharePoint, quantos são usados ativamente e o armazenamento total consumido. '
ms.openlocfilehash: 7da72dccb4a90ed204ffa785040b1968ac70feb3
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688200"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Relatórios do Microsoft 365 no centro de administração - uso do site do SharePoint

Como administrador do Microsoft 365, o painel **Relatórios** mostra a visão geral das atividades em vários produtos em sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Por exemplo, você pode ter uma visão de alto nível do valor que está recebendo do SharePoint em termos do número total de arquivos armazenados pelos usuários nos sites do SharePoint, quantos arquivos estão sendo usados ativamente e o armazenamento consumido em todos esses sites. Em seguida, você pode analisar o relatório de uso do site do SharePoint para entender as tendências e os detalhes de acordo com o nível do site para todos os sites. 
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver os relatórios.
Os relatórios do Microsoft 365 no centro de administração não são suportados para locatários GCC High e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Como acessar o relatório de uso de site do SharePoint

1. No centro de administração, vá para **Uso de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Relatórios.</a>
    
2. Em **arquivos do SharePoint,** **clique em Exibir mais**. 

3. Ao lado **de Atividade do SharePoint,** clique na seta para baixo para abrir o menu.

4. Selecione o uso do Site do **SharePoint.** \> 
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Como interpretar o relatório de uso do site do SharePoint

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório **Uso do SharePoint** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório geralmente abrangem até as últimas 24 a 48 horas. <br/> |
|3.  <br/> |O **gráfico Sites** mostra o número total de sites ativos e totais, incluindo qualquer site no qual os usuários visualizaram, modificaram, carregaram, baixaram, compartilharam ou sincronizaram um arquivo ou visualizaram uma página dentro do período do relatório.  <br/> |
|4.  <br/> |O gráfico **Arquivos** mostra o número total de arquivos em todos os sites e o número de arquivos ativos. O número do total de arquivos inclui arquivos de usuário e arquivos de sistema. Um arquivo é considerado ativo se tiver sido salvo, sincronizado, modificado ou compartilhado dentro do período específico.  |
|5.  <br/> |O gráfico **Armazenamento** mostra a tendência de armazenamento alocado e consumido durante o período do relatório.  <br/> |
|6.  <br/> |O gráfico **Páginas** mostra o número de páginas exibidas em todos os sites.  <br/> |
|7.  <br/> |Você pode filtrar os gráficos que vê selecionando um item na legenda. Por exemplo, no gráfico **Arquivos,** selecione **Arquivos** ou **Arquivos Ativos.** No gráfico **Sites,** você pode selecionar **Total de sites ou** sites **ativos.** No gráfico **de** Armazenamento, você pode selecionar **Armazenamento alocado ou** Armazenamento **consumido.** Ao alterar essa seleção, as informações da tabela não mudam.  <br/> |
|8.  <br/> | A tabela mostra o detalhamento das atividades no nível do site.  <br/> ![Opções de coluna para relatório de uso](../../media/sharepointsite-usage.png)           <br/> **URL do site** é a URL completa do site.  <br/> **Excluída** é o status de exclusão do site. Leva pelo menos sete dias para os sites serem marcados como excluídos.  <br/> **Proprietário do site** é o nome de usuário do proprietário principal do site.  <br/>**O nome principal do proprietário** do site é o endereço de email do proprietário do site.  <br/> **Data da última atividade (UTC)** refere-se à data da última detecção de atividade do arquivo ou uma página foi visualizada no site.  <br/> **Arquivos** é o número de arquivos no site.  <br/> **Arquivos ativos** é o número de arquivos ativos no site.<br/> OBSERVAÇÃO: se os arquivos foram removidos durante o período de tempo especificado para o relatório, o número de arquivos ativos mostrados no relatório pode ser maior do que o número atual de arquivos no site.<br/>**Armazenamento utilizado (MB)** é a quantidade de armazenamento está sendo usada no momento no site.  <br/> **Armazenamento alocado (MB)** é a quantidade máxima de armazenamento alocado para o site.  <br/> **Modos de exibição de página** é o número de vezes que as páginas foram visualizadas no site.  <br/> **Páginas visitadas** é o número de páginas exclusivas que foram visitadas no site.  <br/> **Modelo da Web Raiz** é o modelo usado para criar o site.  <br/> OBSERVAÇÃO: se você quiser filtrar os dados por tipos de site diferentes, exporte os dados e use a coluna Modelo da Web Raiz. <br/>Se as políticas da sua organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **Como faço para ocultar detalhes no nível do usuário?** nos Relatórios de Atividades no centro de administração do Microsoft [365.](activity-reports.md)  <br/> |
|9.  <br/> |Selecione **Gerenciar colunas Gerenciar** ![ Colunas para adicionar ou remover ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) colunas do relatório.    <br/> |
|10.  <br/> |Você também pode exportar os dados do relatório para um  arquivo .csv do Excel, selecionando o ![ link Exportar ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) Exportação. Isso exporta os dados de todos os sites e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 sites, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 sites, para filtrar e classificar, você precisa exportar os dados.  <br/> OBSERVAÇÃO: quando os dados são exportados para um arquivo do Excel, observe que a data em que o relatório de conteúdo foi gerado é refletida no arquivo nos Dados **a partir da** coluna.      <br/>   |
|||
