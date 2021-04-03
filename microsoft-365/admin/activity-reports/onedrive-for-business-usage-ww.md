---
title: Relatórios do Microsoft 365 no centro de administração - Uso do OneDrive for Business
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
description: 'Obter o Relatório de Uso do OneDrive for Business para saber sobre o número total de arquivos e armazenamento usados em toda a sua organização. '
ms.openlocfilehash: 54a3b1e041ee6155b5ce89d6cd5bc73233d1f69b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579537"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Relatórios do Microsoft 365 no centro de administração - Uso do OneDrive for Business

O painel Relatórios  do Microsoft 365 mostra a visão geral da atividade em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, o cartão do OneDrive no painel oferece uma visão geral de alto nível do valor que você obtém do OneDrive for Business em termos de armazenamento e número total de arquivos usados em sua organização. Você pode então aprofundar-se para entender as tendências de contas ativas do OneDrive, com quantos arquivos os usuários interagem, bem como o armazenamento utilizado. Ele também fornece detalhes de cada usuário do OneDrive.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver relatórios.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Como posso obter o relatório de atividades do OneDrive?

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão OneDrive.
  
## <a name="interpret-the-onedrive-usage-report"></a>Entenda o relatório de uso do OneDrive

Você pode exibir o uso no relatório do OneDrive escolhendo a **guia Uso.**<br/>![Relatórios do Microsoft 365 - Relatório de uso do Microsoft OneDrive.](../../media/3cdaf2fb-1817-479b-a0e1-2afa228690cf.png)

Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de uso do OneDrive - escolha colunas](../../media/9ee80f25-cfe3-411d-8e31-08f1507d18c1.png)

Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|URL  <br/> |O endereço da Web do OneDrive do usuário. <br/> |
|Deleted  <br/> |O status de exclusão do OneDrive. Demora pelo menos 7 dias para as contas serem marcadas como excluídas.  <br/> |
|Proprietário  <br/> |O nome de usuário do administrador principal do OneDrive.   <br/> |
|Nome principal do proprietário  <br/> |O endereço de email do proprietário do OneDrive. <br/> |
|Data da última atividade (UTC)  <br/> | A data mais recente em que uma atividade de arquivo foi executada no OneDrive. Se o OneDrive não teve atividade de arquivo, o valor ficará em branco.  <br/> |
|Arquivos  <br/> |O número de arquivos no OneDrive. <br/>|
|Arquivos ativos  <br/> | O número de arquivos ativos dentro do período de tempo.<br/> OBSERVAÇÃO: se os arquivos foram removidos durante o período especificado para o relatório, o número de arquivos ativos mostrados no relatório pode ser maior do que o número atual de arquivos no OneDrive. >  Usuários excluídos continuarão a ser exibidos em relatórios por 180 dias.  <br/> |
|Armazenamento usado (MB)  <br/> |A quantidade de armazenamento que o OneDrive usa em MB. |
|||