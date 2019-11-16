---
title: Integração com o servidor SIEM com serviços e aplicativos da Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Leia este artigo para obter uma visão geral da integração do SIEM Server com o Microsoft 365.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677504"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integração com o servidor SIEM com serviços e aplicativos da Microsoft 365

## <a name="summary"></a>Resumo

Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM) ou se você estiver planejando obter um servidor SIEM em breve, talvez esteja se perguntando como ele se integrará com o Microsoft 365 ou o Office 365. Este artigo fornece uma lista de recursos que você pode usar para configurar a integração do SIEM Server com seus serviços e aplicativos do Microsoft 365.

> [!TIP]
> Se você ainda não tiver um servidor SIEM e estiver explorando suas opções, considere o **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Preciso de um servidor SIEM?

Se você precisa de um servidor SIEM depende de vários fatores, como os requisitos de segurança da sua organização e onde seus dados residem. O Microsoft 365 inclui uma ampla variedade de recursos de segurança que atendem às necessidades de segurança de várias organizações sem servidores adicionais, como um servidor SIEM. Algumas organizações têm circunstâncias especiais que exigem o uso de um servidor SIEM. Aqui estão alguns exemplos:

- A *Fabrikam* tem alguns conteúdos e aplicativos locais e alguns na nuvem (eles têm uma implantação de nuvem híbrida). Para obter relatórios de segurança em todos os seus aplicativos e conteúdo, a Fabrikam implementou um servidor SIEM. 

- A *contoso* é uma organização de serviços financeiros que tem requisitos de segurança especialmente rígidos. Eles adicionaram um servidor SIEM ao seu ambiente para aproveitar a proteção extra de segurança de que precisam.

## <a name="siem-server-integration-with-microsoft-365"></a>Integração do servidor SIEM com o Microsoft 365

Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365. A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com as entradas do servidor SIEM, e os recursos para saber mais sobre a integração do SIEM Server. 

| Serviço ou aplicativo Microsoft 365 | Entradas do servidor SIEM | Recursos para saber mais |
| --- | --- | --- |
| [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)  | Logs de auditoria | [Integração do SIEM com a proteção avançada contra ameaças do Office 365](siem-integration-with-office-365-ti.md) |
| [Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/) | Ponto de extremidade HTTPS hospedado no Azure <br/>API REST| [Extrair alertas para suas ferramentas SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Segurança no Aplicativo da Nuvem da Microsoft](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integração de log | [Integração do SIEM com o Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> Dê uma olhada no [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), que vem com vários conectores para soluções da Microsoft, disponível prontos para uso e fornecendo integração em tempo real, incluindo soluções de proteção contra ameaças da Microsoft e fontes do Microsoft 365, incluindo o Office 365, o Azure AD, o Azure ATP e o Microsoft Cloud app Security e muito mais.

### <a name="audit-logging-must-be-turned-on"></a>O log de auditoria deve estar ativado

Certifique-se de que o registro em log de auditoria está ativado antes de configurar a integração do servidor SIEM. 

- Para o SharePoint Online, OneDrive for Business e Azure Active Directory, [o log de auditoria está ativado no centro de conformidade de & de segurança](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Para o Exchange Online, o [log de auditoria é ativado com o Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="additional-resources"></a>Recursos adicionais

[Integrar soluções de segurança na central de segurança do Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrar alertas da API de Segurança do Microsoft Graph com um SIEM](https://docs.microsoft.com/graph/security-integration)