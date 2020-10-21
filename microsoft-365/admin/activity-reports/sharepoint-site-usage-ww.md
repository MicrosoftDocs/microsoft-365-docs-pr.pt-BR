---
title: Relatórios do Microsoft 365 no centro de administração-uso do site do SharePoint
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obtenha o relatório de uso do site do SharePoint para saber quantos arquivos os usuários armazenam em sites do SharePoint, quantas são usadas ativamente e o armazenamento total consumido.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649729"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Relatórios do Microsoft 365 no centro de administração-uso do site do SharePoint

Como um administrador do Microsoft 365, o painel **relatórios** mostra a visão geral das atividades em vários produtos da sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Por exemplo, você pode ter uma visão de alto nível do valor que está recebendo do SharePoint em termos do número total de arquivos armazenados pelos usuários nos sites do SharePoint, quantos arquivos estão sendo usados ativamente e o armazenamento consumido em todos esses sites. Em seguida, você pode analisar o relatório de uso do site do SharePoint para entender as tendências e os detalhes de acordo com o nível do site para todos os sites. 
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.
Os relatórios do Microsoft 365 no centro de administração não têm suporte para locatários GCC altos e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Como acessar o relatório de uso de site do SharePoint

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão do SharePoint.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretar o relatório de uso do site do SharePoint

Você pode exibir o uso do site no relatório do SharePoint escolhendo a guia **uso do site** .<br/>![Microsoft 365 Reports-relatório de uso do site do Microsoft SharePoint.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Selecione **escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de uso do site do SharePoint-escolher colunas](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|URL do site  <br/> |A URL completa do site. <br/> |
|Deleted  <br/> |O status de exclusão do site. Leva pelo menos sete dias para os sites serem marcados como excluídos.  <br/> |
|Proprietário do site  <br/> |O nome de usuário do proprietário principal do site.   <br/> |
|Nome principal do proprietário do site  <br/> |O endereço de email do proprietário do site. <br/> |
|Data da última atividade (UTC)  <br/> | A data da última vez em que a atividade do arquivo foi detectada ou uma página foi visualizada no site.  <br/> |
|Arquivos  <br/> |O número de arquivos no site. <br/>|
|Arquivos ativos  <br/> | O número de arquivos ativos no site.<br/> Observação: se os arquivos foram removidos durante o período de tempo especificado para o relatório, o número de arquivos ativos mostrados no relatório pode ser maior do que o número atual de arquivos no site.  <br/> |
|Armazenamento usado (MB)  <br/> |A quantidade de armazenamento que está sendo usada no site.  <br/>|
|Armazenamento alocado (MB)  <br/> |A quantidade máxima de armazenamento alocada para o site.  <br/>|
|Exibições de página  <br/> |O número de vezes que as páginas foram exibidas no site.  <br/>|
|Páginas visitadas  <br/> |O número de páginas exclusivas que foram visitadas no site.  <br/>|
|Modelo de Web raiz  <br/> |O modelo usado para criar o site.  <br/> Observação: se você deseja filtrar os dados por diferentes tipos de site, exporte os dados e use a coluna modelo da Web raiz. |
|||