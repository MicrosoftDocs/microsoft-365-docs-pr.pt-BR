---
title: Criar um grupo do Microsoft 365 com um PDL específico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Saiba como criar um grupo do Microsoft 365 com um local de dados preferencial especificado em um ambiente multi-geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f02a5eb6d8b30e8381c65d4735812675d35af2b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923739"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Criar um grupo do Microsoft 365 com um PDL específico

Quando os usuários em um ambiente multi-geo criam um Grupo do Microsoft 365, o local de dados preferencial do grupo é automaticamente definido como o do usuário. Os administradores globais, do SharePoint e do Exchange podem criar grupos em qualquer região que selecionarem. 

Se precisar criar um grupo com uma PDL específica, você pode fazer isso através do centro do administração do SharePoint ou através do cmdlet do novo PowerShell do Microsoft Exchange Online UnifiedGroup. Quando você fizer isso, a caixa de correio de grupo e o site do SharePoint associados ao grupo serão provisionados na PDL especificada.

Para criar um Grupo do Microsoft 365 com o PDL especificado, vá para o Centro de administração do SharePoint na localização geográfica onde você deseja criar o site do grupo.

Por exemplo:

Se você quer criar um site de grupo no seu local na Austrália, pode ir para https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement

1. Selecione **+ Criar**.
2. Siga o processo para criar um site de grupo.

O seu site de grupo será provisionado na localização geográfica correspondente ao centro de administração do SharePoint no qual você iniciou a solicitação de criação de site. 

Usando o PowerShell do Exchange 

Conecte-se ao PowerShell do Exchange Online e passe o parâmetro *-MailBoxRegion* com o código de localização geográfica.

Por exemplo: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![O Cmdlet do PowerShell de captura de tela do novo UnifiedGroup com sintaxe](../media/multi-geo-new-group-with-pdl-powershell.png)

Observe que o provisionamento de sites de grupo do SharePoint é sob demanda. O site será configurado a primeira vez que um membro ou proprietário do grupo tentar acessá-lo.

## <a name="geo-location-codes"></a>Códigos de localização geográfica

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Tópicos relacionados

[Conectar-se ao PowerShell do Exchange Online ](/powershell/exchange/connect-to-exchange-online-powershell)