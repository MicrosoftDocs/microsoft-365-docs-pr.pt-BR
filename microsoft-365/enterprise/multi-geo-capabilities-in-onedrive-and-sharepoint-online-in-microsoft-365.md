---
title: Funcionalidades multigeográficas no OneDrive e no SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Expanda sua presença no Microsoft 365 para várias regiões geográficas com recursos multigeográficos no OneDrive Online.
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995904"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>Funcionalidades multigeográficas no OneDrive e no SharePoint Online

Recursos multi-geo no OneDrive e no SharePoint Online permitem o controle de recursos compartilhados, como sites de equipe SharePoint e caixas de correio do Microsoft 365 Group armazenadas em repouso em um país ou região.

Cada usuário, caixa de correio do Grupo e site do SharePoint possui uma Localização Preferencial do Dados (PDL) que indica a localização geográfica onde os dados relacionados devem ser armazenados. Os dados pessoais do usuário (caixa de correio do Exchange e do OneDrive), juntamente com os grupos do Microsoft 365 ou sites do SharePoint criados por eles, podem ser armazenados em uma localização geográfica especificada para atender aos requisitos de residência dos dados. Você pode [especificar administradores diferentes para cada localização geográfica](add-a-sharepoint-geo-admin.md).

Os usuários têm uma experiência perfeita ao usar os serviços do Microsoft 365, incluindo os aplicativos do Office, OneDrive e Pesquisa. Para obter mais detalhes, confira [Experiência do usuário em um ambiente Multi-Geo](multi-geo-user-experience.md).

## <a name="onedrive"></a>OneDrive

Cada usuário do OneDrive pode ser provisionado ou [movido por um administrador](move-onedrive-between-geo-locations.md) em um localização por satélite de acordo com PDL do usuário. Os arquivos pessoais são mantidos nessa localização geográfica, embora eles possam ser compartilhados com usuários em outras localizações geográficas.

## <a name="sharepoint-sites-and-groups"></a>Sites e Grupos do SharePoint

O gerenciamento de recursos multigeográficos está disponível por meio do Centro de administração do SharePoint. Informações detalhadas podem ser encontradas em [postagem de blog correspondentes](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).

Quando um usuário cria um site conectado a um grupo do SharePoint no ambiente multigeográfico, o PDL é usado para determinar a localização geográfica onde o site e sua caixa de correio de Grupo associada foram criados. (Se o valor PDL do usuário ainda não foi definida ou foi definida em uma localização geográfica que ainda não foi configurada como uma localização por satélite, os sites e as caixas de correio são criados em uma localização central.)

Os serviços do Microsoft 365, diferentes do Exchange, OneDrive, e SharePoint, não são multigeográficos. No entanto, os grupos do Microsoft 365 que são criados por esses serviços, serão marcados com a PDL do criador e sua caixa de correio do grupo do Exchange e do site do grupo do SharePoint O365 provisionados na localização geográfica correspondente. 

## <a name="managing-the-multi-geo-environment"></a>Gerenciar o ambiente multigeográfico

A configuração e o gerenciamento do ambiente multigeográfico são feitos pelo centro de administração do SharePoint. 

![Captura de tela da página de localizações geográficas do centro de administração SharePoint](../media/sharepoint-multi-geo-admin-center.png)

(Algumas ações, como mover um site do SharePoint ou um site do OneDrive necessitam do Microsoft PowerShell.)

## <a name="see-also"></a>Confira também

[Várias regiões nos grupos do SharePoint e do Microsoft 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[Administrar um ambiente multigeográfico](administering-a-multi-geo-environment.md)

[Cotas de armazenamento do SharePoint em ambientes multigeográficos](sharepoint-multi-geo-storage-quota.md)

[Administrar caixas de correio do Exchange Online em um ambiente multigeográfico](administering-exchange-online-multi-geo.md)
