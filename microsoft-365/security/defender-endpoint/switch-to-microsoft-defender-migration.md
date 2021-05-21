---
title: Fazer a opção de proteção de ponto de extremidade que não seja da Microsoft para o Microsoft Defender para Ponto de Extremidade
description: Alternar para o Microsoft Defender para Ponto de Extremidade. Leia este artigo para uma visão geral.
keywords: migração, proteção avançada do ponto de extremidade do Windows Defender, para Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
- m365solution-overview
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 2a2b78089486b432ebf9492de26396b2bb96f94d
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593496"
---
# <a name="make-the-switch-from-non-microsoft-endpoint-protection-to-microsoft-defender-for-endpoint"></a>Fazer a opção de proteção de ponto de extremidade que não seja da Microsoft para o Microsoft Defender para Ponto de Extremidade

Se você estiver pensando em mudar de sua proteção de ponto de extremidade não Microsoft para [o Microsoft Defender para Ponto](microsoft-defender-endpoint.md) de Extremidade (Defender para Ponto de Extremidade), você está no lugar certo. Use este artigo como um guia.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Visão geral da migração para o Defender para Ponto de Extremidade":::

Quando você faz a opção para Defender para Ponto de Extremidade, você começa com sua solução não Microsoft operando no modo ativo, configura o Defender para Ponto de Extremidade no modo passivo, integra o Defender para Ponto de Extremidade, define o Defender para o Ponto de Extremidade como modo ativo e remove a solução que não é da Microsoft.

> [!TIP]
> - Se você estiver usando o McAfee Endpoint Security (McAfee), consulte [Migrate from McAfee to Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).
> - Se você estiver usando a Symantec Endpoint Protection (Symantec), consulte Migrate from [Symantec to Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).

## <a name="the-migration-process"></a>O processo de migração

O processo de migração para o Defender para Ponto de Extremidade pode ser dividido em três fases, conforme descrito na tabela a seguir:

![Fases de migração - preparar, configurar, integração](images/phase-diagrams/migration-phases.png)

|Fase |Descrição |
|--|--|
|[Prepare-se para sua migração](switch-to-microsoft-defender-prepare.md) |Durante [a **fase Preparar:**](switch-to-microsoft-defender-prepare.md) <p>1. Atualize os dispositivos da sua organização. <p>2. Obter o Defender para o Ponto de Extremidade. <p>3. Planeje suas funções e permissões e conceda acesso ao Central de Segurança do Microsoft Defender. <p>4. Configure suas configurações de proxy de dispositivo e internet para habilitar a comunicação entre os dispositivos da sua organização e o Defender para o Ponto de Extremidade. |
|[Configurar o Defender para Ponto de Extremidade](switch-to-microsoft-defender-setup.md) |Durante [a fase de **Instalação:**](switch-to-microsoft-defender-setup.md) <p>1. Habilitar/reinstalar Microsoft Defender Antivírus. <p>2. Configure o Defender para o Ponto de Extremidade. <p>3. Adicione o Defender para Ponto de Extremidade à lista de exclusão da solução existente. <p>4. Adicione sua solução existente à lista de exclusão para Microsoft Defender Antivírus. <p>5. Configurar seus grupos de dispositivos, coleções e unidades organizacionais. <p>6. Configure suas políticas antimalware e configurações de proteção em tempo real.|
|[Onboard to Defender for Endpoint](switch-to-microsoft-defender-onboard.md) |Durante [a **fase Onboard**](switch-to-microsoft-defender-onboard.md): <p>1. A integração de seus dispositivos ao Defender para Ponto de Extremidade. <p>2. Execute um teste de detecção. <p>3. Confirme se Microsoft Defender Antivírus está sendo executado no modo passivo. <p>4. Obter atualizações para Microsoft Defender Antivírus. <p>5. Desinstale sua solução de proteção de ponto de extremidade existente. <p>6. Certifique-se de que o Defender para Ponto de Extremidade está funcionando corretamente. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>O que está incluído no Microsoft Defender para Ponto de Extremidade?

Neste guia de migração, nos concentramos na proteção de próxima geração e detecção e resposta de ponto de extremidade [recursos](overview-endpoint-detection-response.md) como ponto de partida para mover para o Defender para o Ponto de Extremidade. [](microsoft-defender-antivirus-in-windows-10.md) No entanto, o Defender para Ponto de Extremidade inclui muito mais do que proteção contra antivírus e ponto de extremidade. O Defender for Endpoint é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta. A tabela a seguir resume recursos e recursos no Defender para Ponto de Extremidade. 

| Recurso/Funcionalidade | Descrição |
|---|---|
| [Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md) | Os & Gerenciamento de Vulnerabilidades de ameaças ajudam a identificar, avaliar e remediar as deficiências em seus pontos de extremidade (como dispositivos). |
| [Redução de superfície de ataque](overview-attack-surface-reduction.md) | As regras de redução de superfície de ataque ajudam a proteger os dispositivos e aplicativos da sua organização contra ameaças cibernéticas e ataques. |
| [Proteção de última geração](microsoft-defender-antivirus-in-windows-10.md) | A proteção de próxima geração inclui Microsoft Defender Antivírus para ajudar a bloquear ameaças e malware. |
| [Detecção de ponto de extremidade e resposta](overview-endpoint-detection-response.md) | Os recursos de detecção e resposta do ponto de extremidade detectam, investigam e respondem a tentativas de intrusão e violações ativas.  |
| [Busca avançada](advanced-hunting-overview.md) | Os recursos avançados de busca permitem que sua equipe de operações de segurança localize indicadores e entidades de ameaças conhecidas ou potenciais. |
| [Bloqueio e contenção comportamental](behavioral-blocking-containment.md) | Os recursos de bloqueio comportamental e de contenção ajudam a identificar e parar ameaças, com base em seus comportamentos e no processo de árvores, mesmo quando a ameaça iniciou a execução. |
| [Investigação e correção automatizadas](automated-investigations.md) | Os recursos automatizados de investigação e resposta examinam alertas e tomarão medidas imediatas de correção para resolver violações. |
| [Serviço de busca de](microsoft-threat-experts.md) ameaças (Especialistas em Ameaças da Microsoft) | Os serviços de busca de ameaças fornecem às equipes de operações de segurança monitoramento e análise de nível especializado e ajudam a garantir que as ameaças críticas não sejam perdidas. |

**Quer saber mais? Consulte [Defender para Ponto de Extremidade](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Próxima etapa

- Prossiga [para Preparar sua migração](switch-to-microsoft-defender-prepare.md).
