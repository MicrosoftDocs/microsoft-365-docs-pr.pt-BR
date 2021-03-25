---
title: Acessar o portal do cliente do Centro de Segurança do Microsoft Defender MSSP
description: Acessar o portal do cliente do Centro de Segurança do Microsoft Defender MSSP
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164852"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a>Acessar o portal do cliente do Centro de Segurança do Microsoft Defender MSSP

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Esses conjunto de etapas são direcionados para o MSSP. 

Por padrão, os clientes MSSP acessam seu locatário do Centro de Segurança do Microsoft Defender por meio da seguinte URL: `https://securitycenter.windows.com` .
 

No entanto, os MSSPs precisarão usar uma URL específica do locatário no seguinte formato: para acessar  `https://securitycenter.windows.com?tid=customer_tenant_id` o portal do cliente MSSP. 

Em geral, os MSSPs precisarão ser adicionados a cada um dos Azure AD do cliente MSSP que pretendem gerenciar.


Use as etapas a seguir para obter a ID do locatário do cliente MSSP e, em seguida, usar a ID para acessar a URL específica do locatário:

1. Como um MSSP, faça logon no Azure AD com suas credenciais. 

2. Alternar o diretório para o locatário do cliente MSSP.

3.  Selecione **Propriedades do Azure Active Directory >**. Você encontrará a ID do locatário no campo ID do Diretório. 

4. Acesse o portal do cliente MSSP substituindo `customer_tenant_id` o valor na seguinte URL: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Tópicos relacionados
- [Conceder acesso MSSP ao portal](grant-mssp-access.md)
- [Configurar notificações de alerta](configure-mssp-notifications.md)
- [Buscar alertas do locatário do cliente](fetch-alerts-mssp.md)
