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
ms.openlocfilehash: 856f61aac8e7297f1b5dfb3aadc46da06cb16289
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907211"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estender a cobertura de busca avançada com as configurações corretas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

[A busca avançada](advanced-hunting-overview.md) depende de dados provenientes de várias fontes, incluindo seus dispositivos, seus espaços de trabalho do Office 365, o Azure AD e o Microsoft Defender para Identidade. Para obter os dados mais abrangentes possíveis, verifique se você tem as configurações corretas nas fontes de dados correspondentes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoria avançada de segurança em dispositivos Windows
A opção Ativar essas configurações avançadas de auditoria para garantir que você receba dados sobre atividades em seus dispositivos, incluindo gerenciamento de contas locais, gerenciamento de grupo de segurança local e criação de serviço.

| Data | Descrição | Tabela de esquema | Como configurar |
| --- | --- | --- | --- |
| Account management | Eventos capturados como vários `ActionType` valores indicando criação, exclusão e outras atividades relacionadas à conta local | [Eventos do dispositivo](advanced-hunting-deviceevents-table.md) | - Implantar uma política avançada de auditoria de segurança: [Auditar o Gerenciamento de Contas de Usuário](/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Saiba mais sobre políticas avançadas de auditoria de segurança](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Gerenciamento de grupo de segurança | Eventos capturados como vários valores indicando a criação de grupos `ActionType` de segurança local e outras atividades de gerenciamento de grupo locais | [Eventos do dispositivo](advanced-hunting-deviceevents-table.md) | - Implantar uma política avançada de auditoria de segurança: [Auditar o Gerenciamento de Grupo de Segurança](/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Saiba mais sobre políticas avançadas de auditoria de segurança](/windows/security/threat-protection/auditing/advanced-security-auditing) |
| Instalação do serviço | Eventos capturados com `ActionType` o `ServiceInstalled` valor , indicando que um serviço foi criado | [Eventos do dispositivo](advanced-hunting-deviceevents-table.md) | - Implantar uma política avançada de auditoria de segurança: [Auditar a Extensão do Sistema de Segurança](/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Saiba mais sobre políticas avançadas de auditoria de segurança](/windows/security/threat-protection/auditing/advanced-security-auditing) |

## <a name="microsoft-defender-for-identity-sensor-on-the-domain-controller"></a>Sensor do Microsoft Defender para Identidade no controlador de domínio
Se você estiver executando o Active Directory no local, precisará instalar o sensor do Microsoft Defender for Identity no controlador de domínio para obter dados para o Microsoft Defender for Identity. Quando instalados e configurados corretamente, esses dados também se alimentam de busca avançada por meio do Microsoft Defender para Identidade e fornece uma imagem mais holística das informações e eventos de identidade em sua rede. Esses dados também aprimoram a capacidade do Microsoft Defender for Identity de gerar alertas relevantes que também são abordados pela busca avançada. 

| Data | Descrição | Tabela de esquema | Como configurar |
| --- | --- | --- | --- |
| Controlador de domínio | Dados do Active Directory local enviados ao Microsoft Defender para Identidade, enriquecendo informações relacionadas à identidade, como detalhes da conta, atividade de logon e consultas do Active Directory | Várias tabelas, incluindo [IdentityInfo,](advanced-hunting-identityinfo-table.md) [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)e [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)  | - [Instalar o sensor do Microsoft Defender for Identity](/azure-advanced-threat-protection/install-atp-step4)<br>- [Ativar eventos relevantes do Windows](/azure-advanced-threat-protection/configure-event-collection) |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)