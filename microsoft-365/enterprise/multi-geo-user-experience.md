---
title: Experiência do usuário em um ambiente multigeográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Saiba mais sobre a experiência do usuário do SharePoint, OneDrive e Exchange em um ambiente multigeográfico para o Microsoft 365.
ms.openlocfilehash: 4e752581f4ca692f9fecc5019f8e34543ebf7067
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362373"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>Experiência do usuário em um ambiente multigeográfico

Aqui está o que os usuários verão em uma configuração multigeográfica do OneDrive:

## <a name="exchange-mailbox"></a>Caixa de correio do Exchange

A caixa de correio do Exchange do usuário é provisionada para o local de dados preferencial e é automaticamente reposicionada se o PDL muda. Os usuários podem usar o Outlook e o Outlook na web normalmente sem nenhuma alteração na experiência do usuário em um ambiente multigeográfico.

## <a name="hub-sites"></a>Sites do hub

Sites do Hub do SharePoint aprimora a descoberta e a interação com o conteúdo para funcionários, ao criar uma representação consistente e completa de projetos, departamentos ou regiões. Em um ambiente multigeográfico, sites de locais de satélite podem facilmente ser associadas com um site do hub independentemente da localização geográfica do site do hub. Os usuários podem pesquisar e obter resultados em hub em uma experiência de pesquisa única, independentemente da localização geográfica dos sites.

## <a name="microsoft-365-app-launcher"></a>Inicializador de aplicativos do Microsoft 365

O inicializador de aplicativos é ciente da multigeografia e direcionará cada bloco para a localização geográfica apropriada da carga de trabalho. Os blocos do SharePoint e OneDrive apontarão o usuário para a localização correspondente à localização geográfica provisionada pelo usuário. Isso significa que se o usuário tiver o OneDrive em uma localização central, o bloco do SharePoint apontará para SP Home na localização central, mas o site do grupo não será provisionado na localização correspondente ao PDL. 

## <a name="office-applications"></a>Aplicativos do Office

Office aplicativos como Word, Excel e PowerPoint detectarão automaticamente OneDrive localização geográfica correta para cada usuário quando fizer logon. Os usuários não precisa inserir a URL geográfica específica dos sites do SharePoint ou OneDrive.

## <a name="onedrive-sync-app"></a>Sincronização do OneDrive app

O aplicativo Sincronização do OneDrive (versão 17.3.6943.0625 e posterior) detectará automaticamente a localização geográfica correta OneDrive o usuário. O suporte ao aplicativo de sincronização inclui a capacidade de sincronizar sites baseados em grupos independentemente de sua localização geográfica. Observe que para o cliente de sincronização do Groove não há suporte para multigeográfico. 

## <a name="onedrive-location"></a>OneDrive local

Os usuários terão suas OneDrive provisionadas em seu local de dados preferencial. Se um usuário navega até uma URL OneDrive que contém uma localização geográfica incorreta (como um indicador de uma localização geográfica anterior), ele é redirecionado automaticamente para o OneDrive na localização geográfica apropriada.

## <a name="onedrive-ios-and-android"></a>OneDrive para iOS e Android 

Os aplicativos móveis do OneDrive para iOS e Android mostrarão os seus arquivos do OneDrive e arquivos compartilhados com você, independentemente da localização geográfica deles. A pesquisa dos aplicativos móveis do OneDrive mostrará resultados relevantes de todas as localizações geográficas. Baixe a versão mais recente desses aplicativos.

Confira mais informações em [Usar o OneDrive para iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) e [Usar o OneDrive para Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36).

## <a name="onedrive-mobile-client"></a>Cliente móvel do OneDrive 

O Cliente Móvel do OneDrive é multigeográfico ciente e exibirá conteúdo e resultados pertinentes de todas as localizações geográficas.

## <a name="search"></a>Pesquisa

Cada localização geográfica tem seu próprio índice de pesquisa e Centro de Pesquisa. Quando um usuário pesquisa, a consulta é enviada para todas as localizações geográficas e os resultados retornados são mesclados e classificados para que o usuário obtém resultados unificados. Os usuários obterão resultados de todas as localizações geográficas, independentemente de sua própria localização geográfica. Consulte [Configure Search for OneDrive Multi-Geo](configure-search-for-multi-geo.md) for specifics.

Há suporte para os seguintes clientes de pesquisa:

-   OneDrive

-   Delve

-   Página inicial do SharePoint

-   O Centro de Pesquisa

-   Aplicativos de pesquisa personalizada que usam a API de pesquisa do SharePoint

## <a name="sharepoint-home"></a>Página inicial do SharePoint 

Em SharePoint Multi-Geo sua SharePoint está hospedada no local onde o usuário reside, conforme determinado por seu OneDrive local. Por exemplo: se o usuário tiver seu próprio OneDrive hospedado em um local de satélite na Europa, a página inicial do SharePoint será renderizada na Europa. A página inicial do SharePoint inclui todo o conteúdo relevante para o usuário independentemente de sua localização geográfica. 

**Sites Seguidos, Notícias de Sites, Sites Recentes, Sites Frequentes e Sites sugeridos**

Todos os componentes aparecerão para o usuário independentemente da localização geográfica onde o conteúdo estiver hospedado, desde que o usuário tenha permissões para esse conteúdo. 

**Links de Recursos**

Os administradores podem configurar links de Recursos na página inicial do SharePoint de acordo com cada localização geográfica. Isso permite que o administrador disponha na pagina inicial SP os links apropriados para os usuários na região. 

## <a name="sharepoint-mobile-client"></a>Cliente móvel do SharePoint 

O Cliente Móvel do SharePoint é multigeográfico ciente e exibirá o conteúdo e resultados pertinentes de todas as localizações geográficas.

## <a name="sharing"></a>Compartilhamento

A experiência do Seletor de Pessoas mostra todos os usuários independentemente da localização geográfica. Isso permite que um usuário compartilhe com outro usuário em sua mesma localização geográfica ou em outras localizações geográficas do locatário. O conteúdo de diferentes localizações  geográficas será apresentado no modo de exibição Compartilhado comigo no OneDrive do usuário e poderá ser acessado com a experiência de Sign-On única, independentemente da localização geográfica em que ele está hospedado.

## <a name="teams-experience"></a>Experiência do Teams

Teams é um serviço multi-geo. Arquivos do OneDrive e arquivos visualizados recentemente são mostrados independentemente da localização geográfica do usuário. @ menções funcionam com usuários de todas as localizações geográficas.

## <a name="user-profiles"></a>Perfis de usuário

As informações de perfil de usuário são controladas na localização geográfica do usuário. Ao selecionar um usuário, você será direcionado para a localização geográfica adequada do usuário, onde você verá os detalhes do perfil completos dele.

Se o Delve estiver desativado, você verá a experiência de perfil clássica no SharePoint, que não reconhece diferentes localizações geográficas.


