---
title: Integração do servidor SIEM com o Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 'Resumo: Leia este artigo para obter uma visão geral da integração do SIEM Server com o Microsoft 365.'
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073840"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integração com o servidor SIEM com serviços e aplicativos da Microsoft 365

## <a name="overview"></a>Visão geral

Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM) ou se você estiver planejando obter um servidor SIEM em breve, talvez esteja se perguntando como ele se integrará ao seu Microsoft 365, incluindo o Office 365 e5. Se você precisa de um servidor SIEM depende de vários fatores, como os requisitos de segurança da sua organização. A Microsoft 365 oferece uma variedade de recursos de segurança; no entanto, se sua organização tiver conteúdo e aplicativos locais e na nuvem (como no caso de uma implantação de nuvem híbrida), você pode considerar a adição de um servidor SIEM para proteção adicional. Ou, se sua organização tiver requisitos de segurança especialmente rigorosos que você deve atender, você pode considerar adicionar um servidor SIEM ao seu ambiente.

## <a name="siem-server-integration-microsoft-365"></a>Integração com o servidor SIEM Microsoft 365

Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365. A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com as entradas do servidor SIEM e onde obter mais informações sobre a integração do SIEM Server. 

| Serviço ou aplicativo Microsoft 365 | Entradas do servidor SIEM | Recursos para saber mais |
| --- | --- | --- |
| [Proteção Avançada contra Ameaças do Office 365](office-365-atp.md) <br/>ou<br/>[Office 365 Threat Intelligence](office-365-ti.md) | Logs de auditoria | [Integração do SIEM com a proteção avançada contra ameaças do Office 365](siem-integration-with-office-365-ti.md) |
| [Segurança no Aplicativo da Nuvem da Microsoft](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integração de log | [Integração do SIEM com o Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security/siem) |
| [Proteção contra ameaças da Microsoft](https://docs.microsoft.com/windows/security/threat-protection/) | Integração de log | [Extrair alertas para suas ferramentas SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Central de segurança do Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Proteção contra ameaças e detecção de ameaças) | Alertas | [Exportação de dados de segurança do Azure para configuração de pipeline SIEM-visualização](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[Análises avançadas de ameaças do Azure](https://docs.microsoft.com/azure/security/azure-threat-detection) | Azure monitor | [Escrever Usar o Azure monitor para se integrar às ferramentas SIEM](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[Proteção de identidade do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |Integração de log |[Integrar alertas da API de Segurança do Microsoft Graph com um SIEM](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a>O log de auditoria deve estar ativado

Certifique-se de que o registro em log de auditoria está ativado antes de configurar a integração do servidor SIEM. 

- Para o SharePoint Online, OneDrive for Business e Azure Active Directory, [o log de auditoria está ativado no centro de conformidade de & de segurança](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Para o Exchange Online, o [log de auditoria é ativado com o Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="see-also"></a>Confira também

[Adoção da nuvem e soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[Guias do Laboratório de Teste (TLGs) para adoção de nuvem](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


