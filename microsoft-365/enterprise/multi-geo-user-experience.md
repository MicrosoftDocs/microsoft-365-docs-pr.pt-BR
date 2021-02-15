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
ms.openlocfilehash: 558e5a1f7ff2f6f5485a9f32d6e2b43b552b7f17
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749566"
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

Os aplicativos do Office como o Word, o Excel e o PowerPoint detectarão automaticamente a localização geográfica correta do OneDrive for Business para todos os usuários ao entrarem. Os usuários não precisa inserir a URL geográfica específica dos sites do SharePoint ou OneDrive.

## <a name="onedrive-for-business-sync-client"></a>Cliente de sincronização do OneDrive for Business

O cliente de sincronização do OneDrive for Business (versão 17.3.6943.0625 e posteriores) detectará automaticamente a localização geográfica correta do OneDrive for Business para o usuário. O suporte ao cliente de sincronização inclui a capacidade de sincronizar sites baseados em grupos, independentemente de sua localização geográfica. Observe que para o cliente de sincronização do Groove não há suporte para multigeográfico. 

## <a name="onedrive-for-business-location"></a>Localização do OneDrive for Business

Os usuários terão o OneDrive for Business provisionado em sua localização dados preferida. Se um usuário navegar para uma URL do OneDrive com uma localização geográfica incorreta (por exemplo, um indicador de uma localização geográfica anterior), eles serão redirecionados automaticamente para o OneDrive na localização geográfica adequada.

## <a name="onedrive-ios-and-android"></a>OneDrive para iOS e Android 

Os aplicativos móveis do OneDrive para iOS e Android mostrarão os seus arquivos do OneDrive e arquivos compartilhados com você, independentemente da localização geográfica deles. A pesquisa dos aplicativos móveis do OneDrive mostrará resultados relevantes de todas as localizações geográficas. Baixe a versão mais recente desses aplicativos.

Confira mais informações em [Usar o OneDrive para iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) e [Usar o OneDrive para Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36).

## <a name="onedrive-mobile-client"></a>Cliente móvel do OneDrive 

O Cliente Móvel do OneDrive é multigeográfico ciente e exibirá conteúdo e resultados pertinentes de todas as localizações geográficas.

## <a name="search"></a>Pesquisa

Cada localização geográfica tem o seu próprio índice de pesquisa e Centro de pesquisa. Quando um usuário faz uma pesquisa, a consulta é enviada a todas as localizações geográficas e os resultados retornados são mesclados e, depois, classificados de modo que o usuário obtenha resultados unificados. Os usuários obtêm resultados de todas as localizações geográfica independentemente da sua própria localização. Leia informações específicas em [Configurar a pesquisa do OneDrive for Business com Funcionalidade Multigeográfica](configure-search-for-multi-geo.md).

Há suporte para os seguintes clientes de pesquisa:

-   OneDrive for Business

-   Delve

-   Página inicial do SharePoint

-   O Centro de Pesquisa

-   Aplicativos de pesquisa personalizada que usam a API de pesquisa do SharePoint

## <a name="sharepoint-home"></a>Página inicial do SharePoint 

No SharePoint Multigeográfico a página inicial do SharePoint está hospedada no local onde o usuário reside de acordo com a localização do OneDrive for business. Por exemplo: se o usuário tiver seu próprio OneDrive hospedado em um local de satélite na Europa, a página inicial do SharePoint será renderizada na Europa. A página inicial do SharePoint inclui todo o conteúdo relevante para o usuário independentemente de sua localização geográfica. 

**Sites Seguidos, Notícias de Sites, Sites Recentes, Sites Frequentes e Sites sugeridos**

Todos os componentes aparecerão para o usuário independentemente da localização geográfica onde o conteúdo estiver hospedado, desde que o usuário tenha permissões para esse conteúdo. 

**Links de Recursos**

Os administradores podem configurar links de Recursos na página inicial do SharePoint de acordo com cada localização geográfica. Isso permite que o administrador disponha na pagina inicial SP os links apropriados para os usuários na região. 

## <a name="sharepoint-mobile-client"></a>Cliente móvel do SharePoint 

O Cliente Móvel do SharePoint é multigeográfico ciente e exibirá o conteúdo e resultados pertinentes de todas as localizações geográficas.

## <a name="sharing"></a>Compartilhamento

A experiência do Seletor de Pessoas mostra todos os usuários independentemente da localização geográfica. Isso permite que um usuário compartilhe com outro usuário em sua mesma localização geográfica ou em outras localizações geográficas do locatário. O conteúdo de localizações geográficas diferentes será exibidos em **Compartilhado comigo** no OneDrive for Business do usuário e pode ser acessado com uma experiência de logon única independentemente de qual localização geográfica estiver hospedado.

## <a name="teams-experience"></a>Experiência do Teams

O Teams é multigeográfico ciente. Arquivos do OneDrive e arquivos visualizados recentemente são mostrados independentemente da localização geográfica do usuário. @ menções funcionam com usuários de todas as localizações geográficas.

## <a name="user-profiles"></a>Perfis de usuário

As informações de perfil de usuário são controladas na localização geográfica do usuário. Ao selecionar um usuário, você será direcionado para a localização geográfica adequada do usuário, onde você verá os detalhes do perfil completos dele.

Se o Delve estiver desativado, você verá a experiência de perfil clássica no SharePoint, que não reconhece diferentes localizações geográficas.


