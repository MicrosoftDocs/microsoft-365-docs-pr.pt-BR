---
title: Microsoft 365 de isolamento
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
description: Saiba como os controles de isolamento funcionam Microsoft 365, permitindo que os serviços interoperem ou permaneçam autônomos conforme necessário.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918937"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 de isolamento 

A Microsoft trabalha continuamente para garantir que a arquitetura de vários locatários do Microsoft 365 dê suporte à segurança, confidencialidade, privacidade, integridade, padrões locais, internacionais e de disponibilidade no nível [da empresa.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) A escala e o escopo dos serviços fornecidos pela Microsoft dificultam e não são econômicos gerenciar Microsoft 365 com interação humana significativa. Microsoft 365 serviços são fornecidos por meio de vários data centers distribuídos globalmente, cada um altamente automatizado com poucas operações que exigem um toque humano ou qualquer acesso ao conteúdo do cliente. Nossa equipe dá suporte a esses serviços e data centers usando ferramentas automatizadas e acesso remoto altamente seguro. 

Microsoft 365 é composto por vários serviços que fornecem funcionalidades comerciais importantes e contribuem para toda Microsoft 365 experiência. Cada um desses serviços é autoconstruido e projetado para se integrar uns aos outros.

Microsoft 365 é projetado com os seguintes princípios:

 - **[Arquitetura orientada para serviço](/previous-versions/aa480021(v=msdn.10)):** projetando e desenvolvendo software na forma de serviços interoperáveis que proporcionam funcionalidades de negócios bem definidas.
 - **[Garantia](https://www.microsoft.com/download/details.aspx?id=40872)** de Segurança Operacional : uma estrutura que incorpora o conhecimento obtido por meio de vários recursos exclusivos da [Microsoft,](https://www.microsoft.com/sdl/default.aspx)incluindo o Ciclo de Vida do Desenvolvimento de Segurança da [Microsoft,](https://technet.microsoft.com/library/dn440717.aspx)o Centro de Resposta à Segurança da Microsoft e a percepção profunda do cenário de ameaças de segurança cibernética.

Microsoft 365 os serviços interagem entre si, mas são projetados e implementados para que possam ser implantados e operados como serviços autônomos, independentemente uns dos outros. A Microsoft segrega direitos e áreas de responsabilidade Microsoft 365 reduzir oportunidades de modificação não autorizada ou não intencional ou uso indevido dos ativos da organização. Microsoft 365 equipes têm funções definidas como parte de um mecanismo de controle de acesso baseado em função abrangente.

## <a name="customer-content-isolation"></a>Isolamento de conteúdo do cliente

Todo o conteúdo do cliente em um locatário é isolado de outros locatários e de dados de operações e sistemas usados no gerenciamento de Microsoft 365. Várias formas de proteção são implementadas em Microsoft 365 para minimizar o risco de comprometimento de qualquer serviço ou aplicativo Microsoft 365 ou aplicativo. Várias formas de proteção também impedem o acesso não autorizado às informações de locatários ou Microsoft 365 sistema em si.

Para obter informações sobre como a Microsoft implementa o isolamento lógico de dados de locatários Microsoft 365, consulte [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).