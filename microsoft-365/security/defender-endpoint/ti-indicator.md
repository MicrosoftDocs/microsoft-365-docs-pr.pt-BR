---
title: Tipo de recurso indicator
description: Especifique os detalhes da entidade e defina a expiração do indicador usando o Microsoft Defender para Ponto de Extremidade.
keywords: apis, apis com suporte, get, TiIndicator, Indicator, recent
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 75b62f1bada67c30dc05237a284f8b64c3c7072d
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771376"
---
# <a name="indicator-resource-type"></a>Tipo de recurso indicator

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- Consulte a página [Indicadores correspondentes](https://securitycenter.windows.com/preferences2/custom_ti_indicators/files) no portal. 

Método|Tipo de retorno |Descrição
:---|:---|:---
[Listar Indicadores](get-ti-indicators-collection.md) | [Indicador](ti-indicator.md) Coleção | Entidades [indicadoras](ti-indicator.md) de lista.
[Enviar indicador](post-ti-indicator.md) | [Indicador](ti-indicator.md) | Entidade Enviar ou atualizar [Indicador.](ti-indicator.md)
[Importar Indicadores](import-ti-indicators.md) | [Indicador](ti-indicator.md) Coleção | Enviar ou atualizar [entidades de indicadores.](ti-indicator.md)
[Excluir Indicador](delete-ti-indicator-by-id.md) | Sem Conteúdo | Exclui entidade [Indicator.](ti-indicator.md)


## <a name="properties"></a>Propriedades
Propriedade |  Tipo    |   Descrição
:---|:---|:---
id | Cadeia de caracteres | Identidade da entidade [Indicator.](ti-indicator.md)
indicatorValue | Cadeia de caracteres | O valor do [Indicador](ti-indicator.md).
indicatorType | Enum | Tipo do indicador. Os valores possíveis são: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url".
aplicação | Cadeia de caracteres | O aplicativo associado ao indicador. 
ação | Enum | A ação que será tomada se o indicador for descoberto na organização. Os valores possíveis são: "Alert", "AlertAndBlock" e "Allowed".
sourceType | Enum | "Usuário" caso o Indicador criado por um usuário (por exemplo, do portal), "AadApp" no caso de ter sido enviado usando aplicativo automatizado por meio da API.
source | cadeia de caracteres | O nome do usuário/aplicativo que enviou o indicador.
createdBy | Cadeia de caracteres | Identidade exclusiva do usuário/aplicativo que enviou o indicador.
lastUpdatedBy | Cadeia de caracteres | Identidade do usuário/aplicativo que atualizou o indicador pela última vez.
creationTimeDateTimeUtc | DateTimeOffset | A data e a hora em que o indicador foi criado.
expirationTime | DateTimeOffset | O tempo de expiração do indicador.
lastUpdateTime | DateTimeOffset | A última vez que o indicador foi atualizado.
severity | Enum | A gravidade do indicador. os valores possíveis são: "Informacional", "Baixo", "Médio" e "Alto".
title | Cadeia de caracteres | Título do indicador.
description | Cadeia de caracteres | Descrição do indicador.
recommendedActions | Cadeia de caracteres | Ações recomendadas para o indicador.
rbacGroupNames | Lista de cadeias de caracteres | Nomes de grupo de dispositivos RBAC onde o indicador é exposto e ativo. Lista vazia caso ela seja exposta a todos os dispositivos.


## <a name="json-representation"></a>Representação Json

```json
{
    "id": "994",
    "indicatorValue": "881c0f10c75e64ec39d257a131fcd531f47dd2cff2070ae94baa347d375126fd",
    "indicatorType": "FileSha256",
    "action": "AlertAndBlock",
    "application": null,
    "source": "user@contoso.onmicrosoft.com",
    "sourceType": "User",
    "createdBy": "user@contoso.onmicrosoft.com",
    "severity": "Informational",
    "title": "Michael test",
    "description": "test",
    "recommendedActions": "nothing",
    "creationTimeDateTimeUtc": "2019-12-19T09:09:46.9139216Z",
    "expirationTime": null,
    "lastUpdateTime": "2019-12-19T09:09:47.3358111Z",
    "lastUpdatedBy": null,
    "rbacGroupNames": ["team1"]
}
```
