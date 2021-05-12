---
title: Fazer a opção de uma solução de ponto de extremidade que não seja da Microsoft para o Microsoft Defender para Ponto de Extremidade
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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.technology: mde
ms.openlocfilehash: 0a8e1f11cdb9d7363e6b47d1e671c546e5eac9b4
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327497"
---
# <a name="make-the-switch-from-a-non-microsoft-endpoint-solution-to-microsoft-defender-for-endpoint"></a>Fazer a opção de uma solução de ponto de extremidade que não seja da Microsoft para o Microsoft Defender para Ponto de Extremidade

Se você estiver planejando mudar de uma solução de proteção de ponto de extremidade que não seja da Microsoft para o [Microsoft Defender para](microsoft-defender-endpoint.md) Ponto de Extremidade (Defender para Ponto de Extremidade), você está no lugar certo. Use este artigo como um guia.

:::image type="content" source="images/nonms-mde-migration.png" alt-text="Visão geral da migração para o Defender para Ponto de Extremidade":::

Quando você faz a mudança para o Defender para Ponto de Extremidade, você começa com sua solução não Microsoft no modo ativo, configura o Defender para Ponto de Extremidade no modo passivo, integra o Defender para Ponto de Extremidade e define o Defender para Ponto de Extremidade como modo ativo e remove a solução que não é da Microsoft.

> [!TIP]
> - Se você estiver usando o McAfee Endpoint Security (McAfee), consulte [Migrate from McAfee to Microsoft Defender for Endpoint](mcafee-to-microsoft-defender-migration.md).
> - Se você estiver usando a Symantec Endpoint Protection (Symantec), consulte [Migrate from Symantec to Microsoft Defender for Endpoint](symantec-to-microsoft-defender-endpoint-migration.md).

## <a name="the-migration-process"></a>O processo de migração

Quando você alterna para o Microsoft Defender para Ponto de Extremidade, você segue um processo que pode ser dividido em três fases, conforme descrito na tabela a seguir:

![Fases de migração - preparar, configurar, integração](images/phase-diagrams/migration-phases.png)

|Fase |Descrição |
|--|--|
|[Prepare-se para sua migração](switch-to-microsoft-defender-prepare.md) |Durante a fase [ **Preparar,**](switch-to-microsoft-defender-prepare.md)atualize os dispositivos da sua organização, receba o Microsoft Defender para Ponto de Extremidade, planeje suas funções e permissões e conceda acesso ao Centro de Segurança do Microsoft Defender. Você também configura o proxy do dispositivo e as configurações da Internet para habilitar a comunicação entre os dispositivos da sua organização e o Microsoft Defender para o Ponto de Extremidade. |
|[Configurar o Microsoft Defender para Ponto de Extremidade](switch-to-microsoft-defender-setup.md) |Durante [a fase **de** Instalação,](switch-to-microsoft-defender-setup.md)habilita o Microsoft Defender Antivírus e garante que ele está no modo passivo. Você também configura configurações & exclusões para o Microsoft Defender Antivírus e sua solução de proteção de ponto de extremidade existente. Em seguida, você cria seus grupos de dispositivos, coleções e unidades organizacionais. Por fim, você configura suas políticas antimalware e configurações de proteção em tempo real.|
|[Integração ao Microsoft Defender para Ponto de Extremidade](switch-to-microsoft-defender-onboard.md) |Durante [a fase **Onboard**](switch-to-microsoft-defender-onboard.md), você integra seus dispositivos ao Microsoft Defender para Ponto de Extremidade e verifica se esses dispositivos estão se comunicando com o Microsoft Defender para Ponto de Extremidade. Por fim, desinstale sua solução de proteção de ponto de extremidade existente e certifique-se de que a proteção por meio do Microsoft Defender Antivírus & o Microsoft Defender para Ponto de Extremidade está no modo ativo. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>O que está incluído no Microsoft Defender para Ponto de Extremidade?

Neste guia de migração, nos concentramos nos recursos de detecção e resposta de proteção e ponto de extremidade de próxima geração como ponto de partida para migrar para o Microsoft Defender para o Ponto de Extremidade. [](microsoft-defender-antivirus-in-windows-10.md) [](overview-endpoint-detection-response.md) No entanto, o Microsoft Defender para Ponto de Extremidade inclui muito mais do que proteção de antivírus e ponto de extremidade. O Microsoft Defender ATP é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta. A tabela a seguir resume recursos e recursos no Microsoft Defender para Ponto de Extremidade. 

| Recurso/Funcionalidade | Descrição |
|---|---|
| [Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md) | Os & gerenciamento de vulnerabilidades ajudam a identificar, avaliar e remediar as deficiências em seus pontos de extremidade (como dispositivos). |
| [Redução de superfície de ataque](overview-attack-surface-reduction.md) | As regras de redução de superfície de ataque ajudam a proteger os dispositivos e aplicativos da sua organização contra ameaças cibernéticas e ataques. |
| [Proteção de última geração](microsoft-defender-antivirus-in-windows-10.md) | A proteção de última geração inclui o Microsoft Defender Antivírus para ajudar a bloquear ameaças e malware. |
| [Detecção de ponto de extremidade e resposta](overview-endpoint-detection-response.md) | Os recursos de detecção e resposta do ponto de extremidade detectam, investigam e respondem a tentativas de intrusão e violações ativas.  |
| [Busca avançada](advanced-hunting-overview.md) | Os recursos avançados de busca permitem que sua equipe de operações de segurança localize indicadores e entidades de ameaças conhecidas ou potenciais. |
| [Bloqueio e contenção comportamental](behavioral-blocking-containment.md) | Os recursos de bloqueio comportamental e de contenção ajudam a identificar e parar ameaças, com base em seus comportamentos e no processo de árvores, mesmo quando a ameaça iniciou a execução. |
| [Investigação e correção automatizadas](automated-investigations.md) | Os recursos automatizados de investigação e resposta examinam alertas e tomarão medidas imediatas de correção para resolver violações. |
| [Serviço de busca de ameaças](microsoft-threat-experts.md) (Especialistas em Ameaças da Microsoft) | Os serviços de busca de ameaças fornecem às equipes de operações de segurança monitoramento e análise de nível especializado e ajudam a garantir que as ameaças críticas não sejam perdidas. |

**Quer saber mais? Consulte [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Próxima etapa

- Prossiga [para Preparar sua migração](switch-to-microsoft-defender-prepare.md).
