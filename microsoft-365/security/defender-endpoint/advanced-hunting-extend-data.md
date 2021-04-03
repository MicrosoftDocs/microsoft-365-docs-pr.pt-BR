---
title: Estender a cobertura de busca avançada com as configurações corretas
description: Verifique as configurações de auditoria em dispositivos Windows e outras configurações para ajudar a garantir que você receba os dados mais abrangentes na busca avançada
keywords: busca avançada, incidente, pivô, entidade, configurações de auditoria, gerenciamento de contas de usuário, gerenciamento de grupo de segurança, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, mdatp, Microsoft Defender ATP, Microsoft Defender para Ponto de Extremidade, Windows Defender, Windows Defender ATP, Windows Defender Proteção Avançada contra Ameaças
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: ea2524cb214d3cf7c784162a472722727cf0d57c
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500611"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a>Estender a cobertura de busca avançada com as configurações corretas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[A busca avançada](advanced-hunting-overview.md) depende dos dados provenientes de toda a sua organização. Para obter os dados mais abrangentes possíveis, verifique se você tem as configurações corretas nas fontes de dados correspondentes.

## <a name="advanced-security-auditing-on-windows-devices"></a>Auditoria avançada de segurança em dispositivos Windows

A opção Ativar essas configurações avançadas de auditoria para garantir que você receba dados sobre atividades em seus dispositivos, incluindo gerenciamento de contas locais, gerenciamento de grupo de segurança local e criação de serviço.

Data | Descrição | Tabela de esquema | Como configurar
-|-|-|-
Account management | Eventos capturados como vários `ActionType` valores indicando criação, exclusão e outras atividades relacionadas à conta local | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implantar uma política avançada de auditoria de segurança: [Auditar o Gerenciamento de Contas de Usuário](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)<br> - [Saiba mais sobre políticas avançadas de auditoria de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Gerenciamento de grupo de segurança | Eventos capturados como vários valores indicando a criação de grupos `ActionType` de segurança local e outras atividades de gerenciamento de grupo locais | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implantar uma política avançada de auditoria de segurança: [Auditar o Gerenciamento de Grupo de Segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)<br> - [Saiba mais sobre políticas avançadas de auditoria de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)
Instalação do serviço | Eventos capturados com `ActionType` o `ServiceInstalled` valor , indicando que um serviço foi criado | [DeviceEvents](advanced-hunting-deviceevents-table.md) | - Implantar uma política avançada de auditoria de segurança: [Auditar a Extensão do Sistema de Segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)<br> - [Saiba mais sobre políticas avançadas de auditoria de segurança](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](overview-custom-detections.md)
