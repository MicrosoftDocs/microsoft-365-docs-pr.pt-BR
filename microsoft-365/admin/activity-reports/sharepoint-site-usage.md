---
title: Relatórios do Microsoft 365 no centro de administração-uso do site do SharePoint
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
description: 'Obtenha o relatório de uso do site do SharePoint para saber quantos arquivos os usuários armazenam em sites do SharePoint, quantas são usadas ativamente e o armazenamento total consumido. '
ms.openlocfilehash: 8c2428a49a42a1d259c69297feff13e5c00a9b8e
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948851"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Relatórios do Microsoft 365 no centro de administração-uso do site do SharePoint

Como um administrador do Microsoft 365, o painel **relatórios** mostra a visão geral das atividades em vários produtos da sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Por exemplo, você pode ter uma visão de alto nível do valor que está recebendo do SharePoint em termos do número total de arquivos armazenados pelos usuários nos sites do SharePoint, quantos arquivos estão sendo usados ativamente e o armazenamento consumido em todos esses sites. Em seguida, você pode analisar o relatório de uso do site do SharePoint para entender as tendências e os detalhes de acordo com o nível do site para todos os sites. 
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.
Os relatórios do Microsoft 365 no centro de administração não têm suporte para locatários GCC altos e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Como acessar o relatório de uso de site do SharePoint

1. No centro de administração, vá para **relatórios** de \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">uso</a>.

    
2. No menu suspenso **selecionar um relatório** , selecione uso **do site do SharePoint** \> **Site usage**.
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Como interpretar o relatório de uso do site do SharePoint

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório **Uso do SharePoint** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas. <br/> |
|3.  <br/> |O gráfico de **sites** mostra o número total e os sites ativos, incluindo qualquer site no qual os usuários tenham visto, modificado, carregado, baixado, compartilhado ou sincronizado um arquivo ou exibido uma página dentro do período de relatório.  <br/> |
|4.  <br/> |O gráfico **Arquivos** mostra o número total de arquivos em todos os sites e o número de arquivos ativos. O número do total de arquivos inclui arquivos de usuário e arquivos de sistema. Um arquivo é considerado ativo se tiver sido salvo, sincronizado, modificado ou compartilhado dentro do período específico.  |
|5.  <br/> |O gráfico **Armazenamento** mostra a tendência de armazenamento alocado e consumido durante o período do relatório.  <br/> |
|6.  <br/> |O gráfico **Páginas** mostra o número de páginas exibidas em todos os sites.  <br/> |
|7.  <br/> |Você pode filtrar gráficos que vê selecionando um item na legenda. Por exemplo, no gráfico **arquivos** , selecione **arquivos** ou **arquivos ativos**. No gráfico de **sites** , você pode selecionar **total de sites** ou **sites ativos**. No gráfico de **armazenamento** , você pode selecionar **Armazenamento alocado** ou **armazenamento consumido.** Ao alterar essa seleção, as informações da tabela não mudam.  <br/> |
|8.  <br/> | A tabela mostra o detalhamento das atividades no nível do site.  <br/> ![Opções de coluna para relatório de uso](../../media/sharepointsite-usage.png)           <br/> **URL do site** é a URL completa do site.  <br/> **Excluída** é o status de exclusão do site. Leva pelo menos sete dias para os sites serem marcados como excluídos.  <br/> **Proprietário do site** é o nome de usuário do proprietário principal do site.  <br/>**Nome principal do proprietário do site** é o endereço de email do proprietário do site.  <br/> **Data da última atividade (UTC)** refere-se à data da última detecção de atividade do arquivo ou uma página foi visualizada no site.  <br/> **Arquivos** é o número de arquivos no site.  <br/> **Arquivos ativos** é o número de arquivos ativos no site.<br/> Observação: se os arquivos foram removidos durante o período de tempo especificado para o relatório, o número de arquivos ativos mostrados no relatório pode ser maior do que o número atual de arquivos no site.<br/>**Armazenamento utilizado (MB)** é a quantidade de armazenamento está sendo usada no momento no site.  <br/> **Armazenamento alocado (MB)** é a quantidade máxima de armazenamento alocado para o site.  <br/> **Modos de exibição de página** é o número de vezes que as páginas foram visualizadas no site.  <br/> **Páginas visitadas** é o número de páginas exclusivas que foram visitadas no site.  <br/> **Modelo da Web Raiz** é o modelo usado para criar o site.  <br/> Observação: se você deseja filtrar os dados por diferentes tipos de site, exporte os dados e use a coluna modelo da Web raiz. <br/>Se as políticas da sua organização impedem você de exibir relatórios onde as informações do usuário são identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção **como ocultar detalhes de nível de usuário?** nos [relatórios de atividades no centro de administração do Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Selecione **gerenciar colunas** ![ gerenciar colunas ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) para adicionar ou remover colunas do relatório.    <br/> |
|10.  <br/> |Você também pode exportar os dados do relatório para um arquivo. csv do Excel, selecionando **o** ![ link exportar exportar ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) . Isso exporta os dados de todos os sites e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 sites, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 sites, para filtrar e classificar, você precisa exportar os dados.  <br/> Observação: quando os dados são exportados para um arquivo do Excel, observe que a data em que o relatório de conteúdo foi gerado é refletida no arquivo nos **dados** da coluna.      <br/>   |
|||
