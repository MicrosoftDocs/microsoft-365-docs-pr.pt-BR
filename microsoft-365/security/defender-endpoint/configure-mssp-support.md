---
title: Configurar o suporte ao provedor de serviços de segurança gerenciado
description: Tomar as etapas necessárias para configurar a integração do MSSP com o Microsoft Defender para Ponto de Extremidade
keywords: provedor de serviços de segurança gerenciado, mssp, configurar, integração
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339353"
---
# <a name="configure-managed-security-service-provider-integration"></a>Configurar a integração do provedor de serviços de segurança gerenciada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

Você precisará seguir as etapas de configuração a seguir para habilitar a integração do provedor de serviços de segurança gerenciado (MSSP).

>[!NOTE]
>Os seguintes termos são usados neste artigo para distinguir entre o provedor de serviços e o consumidor de serviço:
> - MSSPs: organizações de segurança que oferecem para monitorar e gerenciar dispositivos de segurança para uma organização.
> - Clientes MSSP: Organizações que envolvem os serviços de MSSPs.

A integração permitirá que os MSSPs tomem as seguintes ações:

- Obter acesso ao portal de Microsoft 365 Defender do cliente MSSP
- Obter notificações por email e 
- Buscar alertas por meio de informações de segurança e ferramentas de gerenciamento de eventos (SIEM)

Antes que os MSSPs possam tomar essas ações, o cliente MSSP precisará conceder acesso ao locatário do Defender para Ponto de Extremidade para que o MSSP possa acessar o portal. 
 

Normalmente, os clientes do MSSP têm as etapas iniciais de configuração para conceder acesso aos MSSPs ao seu locatário Windows Defender Central de Segurança. Depois que o acesso é concedido, outras etapas de configuração podem ser feitas pelo cliente MSSP ou pelo MSSP.


Em geral, as etapas de configuração a seguir precisam ser tomadas:


- **Conceder ao MSSP acesso a Microsoft 365 Defender** <br>
Essa ação precisa ser feita pelo cliente MSSP. Ele concede ao MSSP acesso ao locatário defender para ponto de extremidade do cliente MSSP.
 

- **Configurar notificações de alerta enviadas para MSSPs** <br>
Essa ação pode ser tomada pelo cliente MSSP ou pelo MSSP. Isso permite que os MSSPs saibam quais alertas precisam ser endereços para o cliente MSSP.

- **Buscar alertas do locatário do cliente MSSP para o sistema SIEM** <br> Essa ação é tomada pelo MSSP. Ele permite que os MSSPs busquem alertas em ferramentas SIEM.

- **Buscar alertas do locatário do cliente MSSP usando APIs** <br>
Essa ação é tomada pelo MSSP. Ele permite que os MSSPs busquem alertas usando APIs.

## <a name="multi-tenant-access-for-mssps"></a>Acesso de vários locatários para MSSPs
Para obter informações sobre como implementar um acesso delegado de vários locatários, consulte [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).



## <a name="related-topics"></a>Tópicos relacionados
- [Conceder acesso MSSP ao portal](grant-mssp-access.md)
- [Acessar o portal do cliente MSSP](access-mssp-portal.md)
- [Configurar notificações de alerta](configure-mssp-notifications.md)
- [Buscar alertas do locatário do cliente](fetch-alerts-mssp.md)

