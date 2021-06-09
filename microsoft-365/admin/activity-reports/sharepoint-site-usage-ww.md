---
title: Microsoft 365 Relatórios no centro de administração - SharePoint uso do site
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
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obter o SharePoint de uso do site para saber quantos arquivos os usuários armazenam em sites SharePoint, quantos são usados ativamente e o armazenamento total consumido.
ms.openlocfilehash: 62bf01c867b7e9217d25e655af6633a72773caa1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241863"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 Relatórios no centro de administração - SharePoint uso do site

Como administrador Microsoft 365, o painel **Relatórios** mostra a visão geral da atividade em vários produtos em sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Por exemplo, você pode ter uma visão de alto nível do valor que está recebendo do SharePoint em termos do número total de arquivos armazenados pelos usuários nos sites do SharePoint, quantos arquivos estão sendo usados ativamente e o armazenamento consumido em todos esses sites. Em seguida, você pode analisar o relatório de uso do site do SharePoint para entender as tendências e os detalhes de acordo com o nível do site para todos os sites. 
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um Exchange, SharePoint, serviço Teams, comunicações Teams ou Skype for Business para ver relatórios.
Microsoft 365 Relatórios no centro de administração não são suportados para GCC locatários High e DoD.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Como acessar o relatório de uso de site do SharePoint

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão SharePoint.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Interpretar o relatório SharePoint de uso do site

Você pode exibir o uso do site no relatório de SharePoint escolhendo a **guia Uso do** site.<br/>![Microsoft 365 relatórios - Relatório de uso SharePoint site da Microsoft.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![SharePoint relatório de uso do site - escolha colunas](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

Você também pode exportar os dados do relatório para um arquivo Excel .csv selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|URL do site  <br/> |A URL completa do site. <br/> |
|Excluída  <br/> |O status de exclusão do site. Leva pelo menos sete dias para os sites serem marcados como excluídos.  <br/> |
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