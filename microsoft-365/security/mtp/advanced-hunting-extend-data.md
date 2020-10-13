---
title: Estender a cobertura de busca avançada com as configurações corretas
description: Verifique as configurações de auditoria em dispositivos Windows e outras configurações para ajudar a garantir que você obtenha os dados mais abrangentes em busca avançada
keywords: busca avançada, incidentes, pivô, entidade, configurações de auditoria, gerenciamento de contas de usuário, gerenciamento de grupo de segurança, busca de ameaças, busca de ameaças no cyber, pesquisa, consulta, telemetria, Microsoft 365, proteção contra ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 223ef56d7d0d61cd4ae8d90bce974d4086227286
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430371"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estender a cobertura de busca avançada com as configurações corretas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A [caça avançada](advanced-hunting-overview.md) depende dos dados provenientes de várias fontes, incluindo seus dispositivos, seus espaços de trabalho do Office 365, o Azure AD e o Azure ATP. Para obter os dados mais abrangentes possíveis, verifique se você tem as configurações corretas nas fontes de dados correspondentes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoria de segurança avançada em dispositivos Windows
Ative essas configurações de auditoria avançadas para garantir que você obtenha dados sobre as atividades em seus dispositivos, incluindo gerenciamento de conta local, gerenciamento de grupo de segurança local e criação de serviço.

| Data | Descrição | Tabela de esquema | Como configurar |
| --- | --- | --- | --- |
| Account management | Eventos capturados como vários `ActionType` valores indicando a criação, exclusão e outras atividades relacionadas à conta local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Implantar uma política de auditoria de segurança avançada: [auditoria de gerenciamento de contas de usuário](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Saiba mais sobre as políticas de auditoria de segurança avançada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Gerenciamento de grupo de segurança | Eventos capturados como vários `ActionType` valores indicando a criação de um grupo de segurança local e outras atividades de gerenciamento de grupo local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Implantar uma política de auditoria de segurança avançada: [auditoria de gerenciamento de grupo de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Saiba mais sobre as políticas de auditoria de segurança avançada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalação de serviço | Eventos capturados com o `ActionType` valor `ServiceInstalled` , indicando que um serviço foi criado | [DeviceEvents](advanced-hunting-deviceevents-table.md) | – Implantar uma política de auditoria de segurança avançada: [auditoria de extensão do sistema de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Saiba mais sobre as políticas de auditoria de segurança avançada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="azure-atp-sensor-on-the-domain-controller"></a>Sensor ATP do Azure no controlador de domínio
Se você estiver executando o Active Directory no local, precisará instalar o sensor ATP do Azure no controlador de domínio para obter dados para a ATP do Azure. Quando instalado e configurado adequadamente, esses dados também são alimentados na busca avançada por meio do Azure ATP e oferece uma visão mais holística de informações de identidade e eventos em sua rede. Esses dados também aprimoram a capacidade do Azure ATP de gerar alertas relevantes que também são cobertos pela busca avançada. 

| Data | Descrição | Tabela de esquema | Como configurar |
| --- | --- | --- | --- |
| Controlador de domínio | Dados do Active Directory local enviados para o Azure ATP, aprimorando informações relacionadas à identidade, como detalhes da conta, atividade de logon e consultas do Active Directory | Várias tabelas, incluindo [IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalar o sensor ATP do Azure](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Ativar eventos relevantes do Windows](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
