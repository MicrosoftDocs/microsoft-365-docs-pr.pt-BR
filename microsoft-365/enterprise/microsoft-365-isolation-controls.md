---
title: Controles de isolamento do Microsoft 365
ms.author: robmazz
author: robmazz
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
description: Saiba como os controles de isolamento funcionam no Microsoft 365, permitindo que os serviços interoperem ou permaneçam autônomos conforme necessário.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918937"
---
# <a name="microsoft-365-isolation-controls"></a>Controles de isolamento do Microsoft 365 

A Microsoft trabalha continuamente para garantir que a arquitetura de vários locatários do Microsoft 365 dê suporte a padrões de segurança, confidencialidade, privacidade, integridade, local, internacional e disponibilidade no nível [empresarial.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) A escala e o escopo dos serviços fornecidos pela Microsoft dificultam e não são econômicos gerenciar o Microsoft 365 com interação humana significativa. Os serviços do Microsoft 365 são fornecidos por meio de vários data centers distribuídos globalmente, cada um altamente automatizado com poucas operações que exigem um toque humano ou qualquer acesso ao conteúdo do cliente. Nossa equipe dá suporte a esses serviços e data centers usando ferramentas automatizadas e acesso remoto altamente seguro. 

O Microsoft 365 é composto por vários serviços que fornecem funcionalidades comerciais importantes e contribuem para toda a experiência do Microsoft 365. Cada um desses serviços é autoconstruido e projetado para se integrar uns aos outros.

O Microsoft 365 foi projetado com os seguintes princípios:

 - **[Arquitetura orientada para serviço](/previous-versions/aa480021(v=msdn.10)):** projetando e desenvolvendo software na forma de serviços interoperáveis que proporcionam funcionalidades de negócios bem definidas.
 - **[Garantia](https://www.microsoft.com/download/details.aspx?id=40872)** de Segurança Operacional : uma estrutura que incorpora o conhecimento obtido por meio de vários recursos exclusivos da [Microsoft,](https://www.microsoft.com/sdl/default.aspx)incluindo o Ciclo de Vida do Desenvolvimento de Segurança da [Microsoft,](https://technet.microsoft.com/library/dn440717.aspx)o Centro de Resposta à Segurança da Microsoft e a percepção profunda do cenário de ameaças de segurança cibernética.

Os serviços do Microsoft 365 interagem entre si, mas são projetados e implementados para que possam ser implantados e operados como serviços autônomos, independentemente uns dos outros. A Microsoft segrega funções e áreas de responsabilidade do Microsoft 365 para reduzir oportunidades de modificação não autorizada ou não intencional ou uso indevido dos ativos da organização. As equipes do Microsoft 365 têm funções definidas como parte de um mecanismo abrangente de controle de acesso baseado em função.

## <a name="customer-content-isolation"></a>Isolamento de conteúdo do cliente

Todo o conteúdo do cliente em um locatário é isolado de outros locatários e de dados de operações e sistemas usados no gerenciamento do Microsoft 365. Várias formas de proteção são implementadas em todo o Microsoft 365 para minimizar o risco de comprometimento de qualquer serviço ou aplicativo do Microsoft 365. Várias formas de proteção também impedem o acesso não autorizado às informações dos locatários ou do próprio sistema do Microsoft 365.

Para obter informações sobre como a Microsoft implementa o isolamento lógico de dados de locatários no Microsoft 365, consulte [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).