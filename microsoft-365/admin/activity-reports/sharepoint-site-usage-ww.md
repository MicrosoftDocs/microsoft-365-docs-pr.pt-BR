---
title: Relatórios do Microsoft 365 no centro de administração - Uso do site do SharePoint
f1.keywords:
- NOCSH
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obter o relatório de uso do site do SharePoint para saber quantos arquivos os usuários armazenam em sites do SharePoint, quantos são usados ativamente e o armazenamento total consumido.
ms.openlocfilehash: cfae7e1fc02d769328af46f75fdafc143467630b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579501"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Relatórios do Microsoft 365 no centro de administração - Uso do site do SharePoint

Como administrador do Microsoft 365, o **painel** Relatórios mostra a visão geral da atividade em vários produtos em sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Por exemplo, você pode ter uma visão de alto nível do valor que está recebendo do SharePoint em termos do número total de arquivos armazenados pelos usuários nos sites do SharePoint, quantos arquivos estão sendo usados ativamente e o armazenamento consumido em todos esses sites. Em seguida, você pode analisar o relatório de uso do site do SharePoint para entender as tendências e os detalhes de acordo com o nível do site para todos os sites. 
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver relatórios.
Os Relatórios do Microsoft 365 no centro de administração não são suportados para locatários GCC High e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Como acessar o relatório de uso de site do SharePoint

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão do SharePoint.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretar o relatório de uso do site do SharePoint

Você pode exibir o uso do site no relatório do SharePoint escolhendo a **guia Uso do** site.<br/>![Relatórios do Microsoft 365 - Relatório de uso do site do Microsoft SharePoint.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de uso do site do SharePoint - escolha colunas](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|URL do site  <br/> |A URL completa do site. <br/> |
|Deleted  <br/> |O status de exclusão do site. Leva pelo menos sete dias para os sites serem marcados como excluídos.  <br/> |
|Proprietário do site  <br/> |O nome de usuário do proprietário principal do site.   <br/> |
|Nome principal do proprietário do site  <br/> |O endereço de email do proprietário do site. <br/> |
|Data da última atividade (UTC)  <br/> | A data da última atividade de arquivo foi detectada ou uma página foi exibida no site.  <br/> |
|ID do rótulo de sensibilidade do site  <br/> | O rótulo de sensibilidade no site.  <br/> |
|Compartilhamento externo  <br/> | As configurações externas compartilháveis no site.  <br/> |
|Política de dispositivo sem gestão  <br/> | A política de acesso ao site para dispositivos não autorizados.  <br/> |
|Localização geográfica  <br/> | A localização geográfica do site.  <br/> |
|Arquivos  <br/> |O número de arquivos no site. <br/>|
|Arquivos ativos  <br/> | O número de arquivos ativos no site.<br/> OBSERVAÇÃO: se os arquivos foram removidos durante o período especificado para o relatório, o número de arquivos ativos mostrados no relatório pode ser maior do que o número atual de arquivos no site.  <br/> |
|Armazenamento usado (MB)  <br/> |A quantidade de armazenamento atualmente sendo usada no site.  <br/>|
|Armazenamento alocado (MB)  <br/> |A quantidade máxima de armazenamento alocado para o site.  <br/>|
|Exibições de página  <br/> |O número de vezes que as páginas foram exibidas no site.  <br/>|
|Páginas visitadas  <br/> |O número de páginas exclusivas que foram visitadas no site.  <br/>|
|Contagem de links anônimos  <br/> |O número de vezes que documentos ou pastas são compartilhados usando "Qualquer pessoa com o link" no site.  <br/>|
|Contagem de links da empresa  <br/> |O número de vezes que documentos ou pastas são compartilhados usando "Pessoas em organização com o link" no site.  <br/>|
|Link seguro para contagem de convidados  <br/> |O número de vezes que documentos ou pastas são compartilhados usando "pessoas específicas" no site.  <br/>|
|Link seguro para contagem de membros  <br/> |O número de vezes que documentos ou pastas são compartilhados usando "pessoas específicas" no site.  <br/>|
|Modelo de Web raiz  <br/> |O modelo usado para criar o site.  <br/> OBSERVAÇÃO: se você quiser filtrar os dados por diferentes tipos de site, exporte os dados e use a coluna Modelo Da Web Raiz. |
|||