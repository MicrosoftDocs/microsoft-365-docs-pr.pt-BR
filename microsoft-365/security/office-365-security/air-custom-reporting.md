---
title: Soluções de relatórios personalizadas com investigação e resposta automatizadas
keywords: SIEM, API, AIR, autoIR, ATP, investigação automatizada, integração, relatório personalizado
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba como integrar investigação e resposta automatizadas com uma solução de relatórios personalizada ou de terceiros.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a66a89a13182570259bcb8be4134c21d13e22391
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175806"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a>Soluções de relatórios personalizadas ou de terceiros para o Microsoft Defender para Office 365

Com [o Microsoft Defender para Office 365,](office-365-atp.md)você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md) No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros. Se sua organização deseja integrar informações sobre [investigações automatizadas](office-365-air.md) com essa solução, você pode usar a API da Atividade de Gerenciamento do Office 365.

**Aplica-se a**
- [Microsoft Defender para Office 365 plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Com [o Microsoft Defender para Office 365,](office-365-atp.md)você recebe informações [detalhadas sobre investigações automatizadas.](air-view-investigation-results.md) No entanto, algumas organizações também usam uma solução de relatórios personalizada ou de terceiros. Se sua organização deseja integrar informações sobre investigações automatizadas com essa solução, você pode usar a API da Atividade de Gerenciamento do Office 365.

|Recurso|Descrição|
|:---|:---|
|[Visão geral das APIs de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|A API da Atividade de Gerenciamento do Office 365 fornece informações sobre várias ações e eventos de usuários, administradores, sistemas e políticas dos logs de atividades do Microsoft 365 e do Azure Active Directory.|
|[Introdução às APIs de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|A API de Gerenciamento do Office 365 usa o Azure AD para fornecer serviços de autenticação para que seu aplicativo acesse os dados do Microsoft 365. Siga as etapas neste artigo para configurar isso.|
|[Referência da API da Atividade de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|Você pode usar a API da Atividade de Gerenciamento do Office 365 para recuperar informações sobre ações e eventos de usuários, administradores, sistemas e políticas dos logs de atividades do Microsoft 365 e do Azure AD. Leia este artigo para saber mais sobre como isso funciona.|
|[Esquema da API da Atividade de Gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|Obter uma visão [](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) geral do esquema Comum e do [Defender para Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) e esquema de investigação e resposta de ameaças para saber mais sobre tipos específicos de dados disponíveis por meio da API da Atividade de Gerenciamento do Office 365.|
|

## <a name="see-also"></a>Confira também

- [Microsoft Defender para Office 365](office-365-atp.md)
- [Investigação e resposta automatizadas no Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
