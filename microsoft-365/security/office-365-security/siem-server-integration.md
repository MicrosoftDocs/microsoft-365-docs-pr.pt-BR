---
title: Integração do servidor SIEM com aplicativos e serviços do Microsoft 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Obter uma visão geral da integração do servidor SIEM (Gerenciamento de Eventos e Informações de Segurança) com seus aplicativos e serviços de nuvem do Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290376"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integração do servidor de Gerenciamento de Eventos e Informações de Segurança (SIEM) com aplicativos e serviços do Microsoft 365

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Resumo

Sua organização está usando ou planejando obter um servidor de Gerenciamento de Eventos e Informações de Segurança (SIEM) ? Você deve estar se perguntando como ele se integra ao Microsoft 365 ou Office 365. Este artigo fornece uma lista de recursos que você pode usar para integrar seu servidor SIEM aos serviços e aplicativos do Microsoft 365.

> [!TIP]
> Se você ainda não tiver um servidor SIEM e estiver explorando suas opções, considere **[o Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Preciso de um servidor SIEM?

Se você precisa de um servidor SIEM depende de muitos fatores, como os requisitos de segurança da sua organização e onde seus dados residem. O Microsoft 365 inclui uma ampla variedade de recursos de segurança que atendem às necessidades de segurança de muitas organizações sem servidores adicionais, como um servidor SIEM. Algumas organizações têm circunstâncias especiais que exigem o uso de um servidor SIEM. Aqui estão alguns exemplos:

- *A Fabrikam* tem alguns conteúdos e aplicativos no local e alguns na nuvem (eles têm uma implantação híbrida na nuvem). Para obter relatórios de segurança em todo o conteúdo e aplicativos, a Fabrikam implementou um servidor SIEM.

- *A Contoso* é uma organização de serviços financeiros que tem requisitos de segurança particularmente rigorosos. Eles adicionaram um servidor SIEM ao seu ambiente para aproveitar a proteção de segurança extra necessária.

## <a name="siem-server-integration-with-microsoft-365"></a>Integração do servidor SIEM com o Microsoft 365

Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365. A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com entradas de servidor SIEM e recursos para saber mais.

****

|Serviço ou aplicativo do Microsoft 365|Entradas/métodos do servidor SIEM|Recursos para saber mais|
|---|---|---|
|[Obter o Microsoft Defender para Office 365](office-365-atp.md)|Logs de auditoria|[Integração siEM com o Microsoft Defender para Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/)|Ponto de extremidade HTTPS hospedado no Azure <p> API REST|[Pull alerts to your SIEM tools](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Integração de log|[Integração do SIEM com o Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Dê uma olhada no [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview) O Azure Sentinel vem com conectores para soluções da Microsoft. Esses conectores estão disponíveis "imediatamente" e oferecem integração em tempo real. Você pode usar o Azure Sentinel com as soluções do Microsoft 365 Defender e os serviços do Microsoft 365, incluindo o Office 365, o Azure AD, o Microsoft Defender for Identity, o Microsoft Cloud App Security e muito mais.

### <a name="audit-logging-must-be-turned-on"></a>O log de auditoria deve estar ligado

Certifique-se de que o log de auditoria está ligado antes de configurar a integração com o servidor SIEM.

- Para o SharePoint Online, o OneDrive for Business e o Azure Active Directory, o log de auditoria está ativado no Centro de Conformidade & [Segurança.](../../compliance/turn-audit-log-search-on-or-off.md)

- Para o Exchange Online, consulte [Gerenciar auditoria de caixa de correio.](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>Mais recursos

[Integrar soluções de segurança no Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar alertas da API de Segurança do Microsoft Graph com um SIEM](https://docs.microsoft.com/graph/security-integration)
