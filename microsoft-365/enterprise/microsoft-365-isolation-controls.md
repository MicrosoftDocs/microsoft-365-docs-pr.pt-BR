---
title: Controles de isolamento da Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Saiba como os controles de isolamento funcionam no Microsoft 365, permitindo que os serviços entrem em operação ou permaneçam autônomos conforme necessário.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15805c2fb57cbcaa33c5ba24dcbcaa378feea4bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687253"
---
# <a name="microsoft-365-isolation-controls"></a>Controles de isolamento da Microsoft 365 

A Microsoft funciona continuamente para garantir que a arquitetura de vários locatários do Microsoft 365 suporte a segurança de nível empresarial, confidencialidade, privacidade, integridade, local, internacional e [padrões](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)de disponibilidade. A escala e o escopo de serviços fornecidos pela Microsoft tornam difícil e não econômico gerenciar o Microsoft 365 com uma interação humana significativa. Os serviços 365 da Microsoft são fornecidos através de vários data centers distribuídos globalmente, cada um altamente automatizado com poucas operações que exigem um toque humano ou qualquer acesso ao conteúdo do cliente. Nossa equipe oferece suporte a esses serviços e data centers usando ferramentas automatizadas e acesso remoto altamente seguro. 

O Microsoft 365 é composto por vários serviços que fornecem funcionalidade comercial importante e contribuem para toda a experiência de 365 da Microsoft. Cada um desses serviços é autônomo e projetado para integração entre si.

O Microsoft 365 foi projetado com os seguintes princípios:

 - ** [Arquitetura orientada a serviços](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** design e desenvolvimento de software na forma de serviços de interoperabilidade que fornecem funcionalidade comercial bem definida.
 - **[Garantia de segurança operacional](https://www.microsoft.com/download/details.aspx?id=40872):** uma estrutura que incorpora o conhecimento obtido por meio de vários recursos exclusivos da Microsoft, incluindo o ciclo de [vida do desenvolvimento da segurança](https://www.microsoft.com/sdl/default.aspx)da Microsoft, o [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)e uma profunda percepção do panorama de ameaças do cybersecurity.

Os serviços do Microsoft 365 interoperam entre si, mas foram projetados e implementados para que possam ser implantados e operados como serviços autônomos, independentemente uns dos outros. A Microsoft segregou as obrigações e áreas de responsabilidade da Microsoft 365 para reduzir as oportunidades de modificação não autorizada ou involuntária ou o uso indevido dos ativos da organização. O Microsoft 365 Teams tem funções definidas como parte de um mecanismo abrangente de controle de acesso baseado em função.

## <a name="customer-content-isolation"></a>Isolamento de conteúdo do cliente

Todo o conteúdo do cliente em um locatário é isolado de outros locatários e de operações e dados de sistemas usados no gerenciamento do Microsoft 365. Várias formas de proteção são implementadas em todo o Microsoft 365 para minimizar o risco de comprometimento de qualquer serviço ou aplicativo do Microsoft 365. Várias formas de proteção também impedem o acesso não autorizado às informações de locatários ou ao próprio sistema Microsoft 365.

Para obter informações sobre como a Microsoft implementa o isolamento lógico de dados de locatário no Microsoft 365, consulte [isolamento de locatário no microsoft 365](microsoft-365-tenant-isolation-overview.md).
