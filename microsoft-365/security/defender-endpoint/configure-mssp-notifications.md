---
title: Configurar notificações de alerta enviadas para MSSPs
description: Configurar notificações de alerta enviadas para MSSPs
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166048"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Configurar notificações de alerta enviadas para MSSPs 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>Esta etapa pode ser feita pelo cliente MSSP ou pelo MSSP. Os MSSPs devem ter as permissões apropriadas para configurá-lo em nome do cliente MSSP.

Depois que o acesso ao portal é concedido, as regras de notificação de alerta podem ser criadas para que os emails sejam enviados aos MSSPs quando os alertas associados ao locatário são criados e as condições definidas são atendidas.

 
Para obter mais informações, [consulte Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).
 

Essas caixas de seleção devem ser verificadas:
- **Incluir nome da organização** - O nome do cliente será adicionado às notificações de email
- **Incluir link de portal** específico do locatário - A URL do link de alerta terá parâmetro específico de locatário (tid=target_tenant_id) que permite acesso direto ao portal de locatários de destino


## <a name="related-topics"></a>Tópicos relacionados
- [Conceder acesso MSSP ao portal](grant-mssp-access.md)
- [Acessar o portal do cliente MSSP](access-mssp-portal.md)
- [Buscar alertas do locatário do cliente](fetch-alerts-mssp.md)
