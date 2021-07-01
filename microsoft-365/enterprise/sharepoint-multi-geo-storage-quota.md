---
title: Cotas de armazenamento do SharePoint em ambientes multigeográficos
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Saiba mais SharePoint cotas de armazenamento em ambientes multi-geo e como as cotas podem ser gerenciadas pelo administrador SharePoint Online.
ms.openlocfilehash: 0843407e7926027e28cdd1f5893c4aafec4e1cd5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230086"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a>Cotas de armazenamento do SharePoint em ambientes multigeográficos

Por padrão, todas as localizações geográficas de um ambiente multigeográfico compartilham a cota de armazenamento disponível do locatário.

Com as configurações de cota de armazenamento geográfico do SharePoint é possível gerenciar a cota de armazenamento para cada localização geográfica. Ao alocar a cota de armazenamento de uma localização geográfica, ela torna-se a quantidade máxima de armazenamento disponível daquela localização geográfica e será deduzida da cota de armazenamento disponível do locatário. A cota de armazenamento do locatário disponível restante é, em seguida, compartilhada entre as localizações geográficas configuradas para as quais uma cota de armazenamento específica não foi alocada.

A cota de armazenamento do SharePoint de qualquer localização geográfica pode ser alocada pelo administrador do SharePoint Online ao conectar-se à localização central. Administradores geográficos para localizações via satélite podem exibir a cota de armazenamento, mas não podem alocá-la.

## <a name="configure-a-storage-quota-for-a-geo-location"></a>Definir uma cota de armazenamento para uma localização geográfica

Use o [Módulo do Microsoft SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588) e conecte-se a uma localização central para alocar a cota de armazenamento de uma localização geográfica.

Para alocar uma Cota de Armazenamento para um localização, execute o cmdlet:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>
```

Para exibir a Cota de Armazenamento da localização geográfica atual, execute:

```powershell
Get-SPOGeoStorageQuota
```

![Captura de tela da janela do PowerShell mostrando o cmdlet Get SPOGeoStorageQuota](../media/multi-geo-storage-quota.png)

Para exibir a Cota de Armazenamento para todas as localizações geográficas, execute:

```powershell
Get-SPOGeoStorageQuota -AllLocations
```

Para remover a cota de armazenamento alocado para uma localização geográfica, defina `StorageQuota value = 0`:

```powershell
Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0
```
