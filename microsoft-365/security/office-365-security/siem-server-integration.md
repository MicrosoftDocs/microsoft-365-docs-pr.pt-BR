---
title: " Integração do servidor de gerenciamento de eventos e informações de segurança (SIEM) com serviços e aplicativos do Microsoft 365"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Obtenha uma visão geral da integração do servidor de gerenciamento de eventos e informações de segurança (SIEM) com seus serviços e aplicativos em nuvem da Microsoft 365
ms.openlocfilehash: d5adf0a72ac78475cb47f06732375ce01c0d72be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082190"
---
#  <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integração do servidor de gerenciamento de eventos e informações de segurança (SIEM) com serviços e aplicativos do Microsoft 365

## <a name="summary"></a>Resumo

Sua organização está usando ou planejando obter um servidor de gerenciamento de informações e de segurança (SIEM)? Você pode estar se perguntando como ele se integra ao Microsoft 365 ou ao Office 365. Este artigo fornece uma lista de recursos que você pode usar para integrar seu servidor SIEM com serviços e aplicativos do Microsoft 365.

> [!TIP]
> Se você ainda não tiver um servidor SIEM e estiver explorando suas opções, considere o **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Preciso de um servidor SIEM?

Se você precisa de um servidor SIEM depende de vários fatores, como os requisitos de segurança da sua organização e onde seus dados residem. O Microsoft 365 inclui uma ampla variedade de recursos de segurança que atendem às necessidades de segurança de várias organizações sem servidores adicionais, como um servidor SIEM. Algumas organizações têm circunstâncias especiais que exigem o uso de um servidor SIEM. Aqui estão alguns exemplos:

- A *Fabrikam* tem alguns conteúdos e aplicativos locais e alguns na nuvem (eles têm uma implantação de nuvem híbrida). Para obter relatórios de segurança em todos os seus aplicativos e conteúdo, a Fabrikam implementou um servidor SIEM. 

- A *contoso* é uma organização de serviços financeiros que tem requisitos de segurança especialmente rígidos. Eles adicionaram um servidor SIEM ao seu ambiente para aproveitar a proteção extra de segurança de que precisam.

## <a name="siem-server-integration-with-microsoft-365"></a>Integração do servidor SIEM com o Microsoft 365

Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365. A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com entradas e recursos do servidor SIEM para saber mais. 

| Serviço ou aplicativo Microsoft 365 | Entradas/métodos do servidor SIEM | Recursos para saber mais |
| --- | --- | --- |
| [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)  | Logs de auditoria | [Integração do SIEM com a proteção avançada contra ameaças do Office 365](siem-integration-with-office-365-ti.md) |
| [Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) | Ponto de extremidade HTTPS hospedado no Azure <br/>API REST| [Extrair alertas para suas ferramentas SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integração de log | [Integração do SIEM com o Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> Dê uma olhada no [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview). O Azure Sentinel vem com conectores para soluções da Microsoft. Esses conectores estão disponíveis "prontos para uso" e fornecem integração em tempo real. Você pode usar o Azure Sentinel com suas soluções de proteção contra ameaças da Microsoft e serviços do Microsoft 365, incluindo o Office 365, o Azure AD, o Azure ATP, o Microsoft Cloud app Security e muito mais.

### <a name="audit-logging-must-be-turned-on"></a>O log de auditoria deve estar ativado

Certifique-se de que o log de auditoria está ativado antes de configurar a integração com o servidor SIEM. 

- Para o SharePoint Online, OneDrive for Business e Azure Active Directory, [o log de auditoria está ativado no centro de conformidade de & de segurança](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Para o Exchange Online, o [log de auditoria é ativado com o Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="more-resources"></a>Mais recursos

[Integrar soluções de segurança na central de segurança do Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar alertas da API de Segurança do Microsoft Graph com um SIEM](https://docs.microsoft.com/graph/security-integration)
