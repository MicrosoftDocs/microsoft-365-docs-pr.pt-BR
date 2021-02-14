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
description: Saiba como os controles de isolamento funcionam no Microsoft 365, permitindo que os serviços inter operem ou permaneçam autônomos conforme necessário.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bb0989f19002267ab92bf184a12a4076f753580e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332371"
---
# <a name="microsoft-365-isolation-controls"></a>Controles de isolamento do Microsoft 365 

A Microsoft trabalha continuamente para garantir que a arquitetura de vários locatários do Microsoft 365 dê suporte a padrões de segurança, confidencialidade, privacidade, integridade, locais, internacionais e de disponibilidade de nível [empresarial.](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons) A escala e o escopo dos serviços fornecidos pela Microsoft dificultam e não são econômicos gerenciar o Microsoft 365 com interação humana significativa. Os serviços do Microsoft 365 são fornecidos por meio de vários data centers distribuídos globalmente, cada um com poucas operações que exigem um toque humano ou qualquer acesso ao conteúdo do cliente. Nossa equipe dá suporte a esses serviços e data centers usando ferramentas automatizadas e acesso remoto altamente seguro. 

O Microsoft 365 é composto por vários serviços que fornecem funcionalidades comerciais importantes e contribuem para toda a experiência do Microsoft 365. Cada um desses serviços é independente e projetado para integrar um ao outro.

O Microsoft 365 foi projetado com os seguintes princípios:

 - **[Arquitetura orientada ao serviço:](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10))** projetando e desenvolvendo software na forma de serviços interoperáveis que proporcionam funcionalidade comercial bem definida.
 - **[Garantia](https://www.microsoft.com/download/details.aspx?id=40872)** de Segurança Operacional : uma estrutura que incorpora o conhecimento obtido por meio de vários recursos exclusivos da [Microsoft,](https://www.microsoft.com/sdl/default.aspx)incluindo o Ciclo de Vida de Desenvolvimento de Segurança da [Microsoft,](https://technet.microsoft.com/library/dn440717.aspx)o Centro de Resposta de Segurança da Microsoft e reconhecimento profundo do panorama das ameaças à segurança cibernética.

Os serviços do Microsoft 365 interagem entre si, mas são projetados e implementados para que possam ser implantados e operados como serviços autônomos, independentemente uns dos outros. A Microsoft segrega direitos e áreas de responsabilidade do Microsoft 365 para reduzir as oportunidades de modificação não autorizada ou não intencional ou uso indevido dos ativos da organização. As equipes do Microsoft 365 definiram funções como parte de um mecanismo abrangente de controle de acesso baseado em função.

## <a name="customer-content-isolation"></a>Isolamento de conteúdo do cliente

Todo o conteúdo do cliente em um locatário é isolado de outros locatários e dos dados de operações e sistemas usados no gerenciamento do Microsoft 365. Várias formas de proteção são implementadas em todo o Microsoft 365 para minimizar o risco de comprometimento de qualquer serviço ou aplicativo do Microsoft 365. Várias formas de proteção também impedem o acesso não autorizado às informações dos locatários ou do próprio sistema do Microsoft 365.

Para saber mais sobre como a Microsoft implementa o isolamento lógico de dados de locatários no Microsoft 365, confira o isolamento de [locatários no Microsoft 365.](microsoft-365-tenant-isolation-overview.md)
