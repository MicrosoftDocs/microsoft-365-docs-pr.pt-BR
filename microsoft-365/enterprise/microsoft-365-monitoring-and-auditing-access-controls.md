---
title: Controles de acesso de monitoramento e auditoria da Microsoft 365
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
description: 'Resumo: um resumo dos vários controles de acesso de monitoramento e auditoria disponíveis no Microsoft 365.'
ms.openlocfilehash: ba79ba2263940e5677ada412f467a429e584b8ff
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332287"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a>Monitoramento e auditoria de controles de acesso no Microsoft 365

A Microsoft executa monitoramento e auditoria abrangentes de todos os privilégios, delegação e operações que ocorrem no Microsoft 365. O controle de acesso do Microsoft 365 é um processo automatizado baseado no princípio de privilégios mínimos e na incorporação de controles e auditorias de acesso a dados:

- Todo o acesso permitido é rastreável para um usuário exclusivo. Os administradores são responsáveis por lidar com o conteúdo do cliente.
- Solicitações de controle de acesso, aprovações e logs de operações administrativas são capturadas para análise de segurança e eventos mal-intencionados.
- Os níveis de acesso são analisados quase em tempo real com base na associação de grupo de segurança para garantir que apenas usuários com justificativas de negócios autorizadas e atendam aos requisitos de qualificação tenham acesso aos sistemas.
- O Microsoft 365, seus controles de acesso e serviços de suporte, incluindo o Azure Active Directory e datacenters físicos, são auditados regularmente por terceiros independentes para conformidade com [ISO/iec 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001), [ISO/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018), [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC), [FedRAMP](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)e outros [padrões](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).
- Os engenheiros da Microsoft 365 devem fazer treinamento de segurança anual, examinar os melhores procedimentos de acesso elevado e confirmar as políticas de segurança e privacidade da Microsoft para manter os direitos para o serviço.

O gatilho automatizado avisa quando é detectada atividade suspeita, como vários logons com falha dentro de um curto período de tempo. A equipe de resposta de segurança da Microsoft 365 usa o Machine Learning e a grande análise de dados para analisar e analisar a atividade, procurar padrões de acesso irregular e responder proativamente a atividades anômalas e ilícitas. A Microsoft também emprega uma equipe dedicada de testadores de penetração e participa da equipe vermelha periódica e de exercícios de equipe azuis para encontrar problemas de segurança e controle de acesso no serviço. Os clientes podem verificar a eficácia dos sistemas de controle de acesso usando os relatórios de auditoria e a API de atividade de gerenciamento fornecida pelo Microsoft 365.

Para obter mais informações, consulte referência e auditoria da [API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) e [relatórios no Microsoft 365](microsoft-365-auditing-and-reporting-overview.md).
