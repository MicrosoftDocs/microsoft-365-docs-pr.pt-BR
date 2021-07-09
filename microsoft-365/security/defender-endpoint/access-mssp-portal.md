---
title: Acessar o portal Microsoft 365 Defender cliente MSSP
description: Acessar o portal Microsoft 365 Defender cliente MSSP
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339581"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Acessar o portal Microsoft 365 Defender cliente MSSP

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Esses conjunto de etapas são direcionados para o MSSP. 

Por padrão, os clientes MSSP acessam seus Central de Segurança do Microsoft Defender locatários por meio da seguinte URL: `https://securitycenter.windows.com` .
 

No entanto, os MSSPs precisarão usar uma URL específica do locatário no seguinte formato: para acessar  `https://securitycenter.windows.com?tid=customer_tenant_id` o portal do cliente MSSP. 

Em geral, os MSSPs precisarão ser adicionados a cada um dos Azure AD do cliente MSSP que pretendem gerenciar.


Use as etapas a seguir para obter a ID do locatário do cliente MSSP e, em seguida, usar a ID para acessar a URL específica do locatário:

1. Como um MSSP, faça logon no Azure AD com suas credenciais. 

2. Alternar o diretório para o locatário do cliente MSSP.

3.  Selecione **Azure Active Directory > Propriedades**. Você encontrará a ID do locatário no campo ID do Diretório. 

4. Acesse o portal do cliente MSSP substituindo `customer_tenant_id` o valor na seguinte URL: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Tópicos relacionados
- [Conceder acesso MSSP ao portal](grant-mssp-access.md)
- [Configurar notificações de alerta](configure-mssp-notifications.md)
- [Buscar alertas do locatário do cliente](fetch-alerts-mssp.md)
