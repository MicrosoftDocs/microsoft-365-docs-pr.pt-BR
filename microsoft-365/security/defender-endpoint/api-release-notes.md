---
title: Notas de versão da API do Microsoft Defender para Ponto de Extremidade
description: Notas de versão para atualizações feitas no conjunto de APIs do Microsoft Defender for Endpoint.
keywords: Notas de versão da API do Microsoft Defender para Ponto de Extremidade, mde, APIs, API do Microsoft Defender para Ponto de Extremidade, atualizações, anotações, versão
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5c8e9d8e1c8ec020b4d742f61d276c93f6730bec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245547"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Notas de versão da API do Microsoft Defender para Ponto de Extremidade

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

As informações a seguir listam as atualizações feitas para as APIs do Microsoft Defender para Ponto de Extremidade e as datas em que foram feitas.

> [!TIP]
> RSS feed: seja notificado quando esta página for atualizada copiando e colar a SEGUINTE URL no leitor de feeds:
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Notas de versão - mais recente para mais antiga (dd.mm.yyyy)

### <a name="03052021"></a>03.05.2021

- Adicionada nova API: métodos e propriedades de atividade [de correção.](get-remediation-methods-properties.md)

### <a name="10022021"></a>10.02.2021

- Adicionada nova API: [alertas de atualização em lotes.](batch-update-alerts.md)

### <a name="25012021"></a>25.01.2021

- Limitações de taxa atualizadas para [a API de Busca Avançada](run-advanced-query-api.md) de 15 a 45 solicitações por minuto.

### <a name="21012021"></a>21.01.2021

- Adicionada nova API: [Encontre dispositivos por marca](machine-tags.md).
- Adicionada nova API: [Indicadores de importação](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Evidência de alerta atualizada: adicionadas ***detectionStatus** _, _*_parentProcessFilePath_*_ e _ *_parentProcessFileName_** propriedades.
- Entidade [Alerta Atualizada](alerts.md): adicionada a propriedade ***detectorId.***

### <a name="15122020"></a>15.12.2020

- Entidade [Do dispositivo](machine.md) atualizada: adicionada a lista ***IpInterfaces.*** Consulte [Listar dispositivos](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Adicionada nova API: [definir o valor do dispositivo](set-device-value.md).
- Entidade [Device](machine.md) atualizada: adicionada a ***propriedade deviceValue.***

### <a name="01092020"></a>01.09.2020

- Opção adicionada para expandir a entidade Alert com suas evidências relacionadas. Consulte [List Alerts](get-alerts.md).
