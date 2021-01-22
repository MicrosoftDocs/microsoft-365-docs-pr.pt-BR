---
title: Estender a cobertura de busca avançada com as configurações corretas
description: Verifique as configurações de auditoria em dispositivos Windows e outras configurações para ajudar a garantir que você receba os dados mais abrangentes na busca avançada
keywords: busca avançada, incidente, pivô, entidade, configurações de auditoria, gerenciamento de conta de usuário, gerenciamento de grupo de segurança, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, Microsoft 365, Proteção contra Ameaças da Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 9773658bea752175fe7988b9322fb26a9d5b7f05
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929581"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estender a cobertura de busca avançada com as configurações corretas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[A busca](advanced-hunting-overview.md) avançada depende de dados provenientes de várias fontes, incluindo seus dispositivos, seus espaços de trabalho do Office 365, o Azure AD e o Microsoft Defender for Identity. Para obter os dados mais abrangentes possíveis, verifique se você tem as configurações corretas nas fontes de dados correspondentes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoria de segurança avançada em dispositivos Windows
Abile essas configurações de auditoria avançadas para garantir que você receba dados sobre atividades em seus dispositivos, incluindo gerenciamento de contas locais, gerenciamento de grupo de segurança local e criação de serviços.

| Data | Descrição | Tabela de esquema | Como configurar |
| --- | --- | --- | --- |
| Account management | Eventos capturados como vários valores indicando criação, exclusão e outras atividades relacionadas `ActionType` à conta local | [Eventos do dispositivo](advanced-hunting-deviceevents-table.md) | - Implantar uma política de auditoria de segurança avançada: [Auditoria de Gerenciamento de Conta de Usuário](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Saiba mais sobre as políticas de auditoria de segurança avançada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Gerenciamento de grupos de segurança | Eventos capturados como vários `ActionType` valores indicando a criação de grupos de segurança local e outras atividades de gerenciamento de grupo local | [Eventos do dispositivo](advanced-hunting-deviceevents-table.md) | - Implantar uma política de auditoria de segurança avançada: [Auditoria de Gerenciamento de Grupo de Segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Saiba mais sobre as políticas de auditoria de segurança avançada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalação do serviço | Eventos capturados com `ActionType` o valor `ServiceInstalled` , indicando que um serviço foi criado | [Eventos do dispositivo](advanced-hunting-deviceevents-table.md) | - Implantar uma política de auditoria de segurança avançada: [Auditar Extensão do Sistema de Segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Saiba mais sobre as políticas de auditoria de segurança avançada](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Sensor de identidade do Microsoft Defender no controlador de domínio
Se você estiver executando o Active Directory no local, precisará instalar o sensor do Microsoft Defender for Identity no controlador de domínio para obter dados do Microsoft Defender para Identidade. Quando instalados e configurados corretamente, esses dados também são alimentados para busca avançada por meio do Microsoft Defender for Identity e fornece uma imagem mais holística de informações de identidade e eventos em sua rede. Esses dados também aprimora a capacidade do Microsoft Defender for Identity de gerar alertas relevantes que também são cobertos pela busca avançada. 

| Data | Descrição | Tabela de esquema | Como configurar |
| --- | --- | --- | --- |
| Controlador de domínio | Dados do Active Directory local enviados ao Microsoft Defender para identidade, enriquecendo informações relacionadas à identidade, como detalhes da conta, atividade de logon e consultas do Active Directory | Várias tabelas, [incluindo IdentityInfo](advanced-hunting-identityinfo-table.md), [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalar o sensor de identidade do Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step4)<br>- [Ativar eventos relevantes do Windows](https://docs.microsoft.com/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
