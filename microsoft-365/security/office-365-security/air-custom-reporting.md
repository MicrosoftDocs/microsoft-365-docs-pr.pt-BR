---
title: Usando soluções de relatórios personalizadas com investigação e resposta automatizadas no Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Saiba como integrar a investigação e a resposta automatizada do Office 365 com uma solução de relatório personalizada ou de terceiros.
ms.openlocfilehash: 3df69c9118b3170924a99a1787761b1bb07aadfa
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175896"
---
# <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a>Usar a API de atividade de gerenciamento do Office 365 para soluções de relatórios personalizados ou de terceiros

Com a [proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), você obtém [informações detalhadas sobre investigações automatizadas](air-view-investigation-results.md). No entanto, algumas organizações também usam uma solução de relatório personalizada ou de terceiros. Se sua organização quiser integrar as informações sobre investigações automatizadas a essa solução, você poderá usar a API da atividade de gerenciamento do Office 365.

Use os seguintes recursos para configurar isso:

|Resource  |Descrição  |
|---------|---------|
|[Visão geral das APIs de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |A API da Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure Active Directory.         |
|[Introdução às APIs de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |A API de gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para que seu aplicativo acesse os dados do Office 365. Siga as etapas deste artigo para configurá-lo.          |
|[Referência da API da Atividade de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |Você pode usar a API de atividade de gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuário, administração, sistema e políticas dos logs de atividades do Office 365 e do Azure AD. Leia este artigo para saber mais sobre como isso funciona.        |
|[Esquema da API da Atividade de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |Obtenha uma visão geral do [esquema comum](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) e do [Office 365 ATP e o esquema de resposta](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) para conhecer os tipos específicos de dados disponíveis por meio da API de atividade de gerenciamento do Office 365.         |

## <a name="related-articles"></a>Artigos relacionados

- [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)

- [Saiba mais sobre a investigação e a resposta automatizadas no Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)