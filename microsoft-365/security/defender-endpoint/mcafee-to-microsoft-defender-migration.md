---
title: Migrar da McAfee para o Microsoft Defender para o Ponto de Extremidade
description: Faça a mudança da McAfee para o Microsoft Defender para o Ponto de Extremidade. Leia este artigo para uma visão geral.
keywords: migração, Microsoft Defender para Ponto de Extremidade, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
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
- m365solution-mcafeemigrate
- m365solution-overview
ms.topic: article
ms.custom: migrationguides
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 5bbcf885ec160204916507aee60398aee35e470b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538046"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Migrar da McAfee para o Microsoft Defender para o Ponto de Extremidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se você estiver planejando mudar do McAfee Endpoint Security (McAfee) para [o Microsoft Defender para](microsoft-defender-endpoint.md) Ponto de Extremidade (Microsoft Defender para Ponto de Extremidade), você está no lugar certo. Use este artigo como um guia.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Visão geral da migração da McAfee para o Defender para o Ponto de Extremidade":::

Quando você faz a mudança da McAfee para o Defender para o Ponto de Extremidade, você começa com sua solução McAfee no modo ativo, configura o Defender para o Ponto de Extremidade no modo passivo, integra o Defender para Ponto de Extremidade e define o Defender para o Ponto de Extremidade como modo ativo e remove a McAfee.

## <a name="the-migration-process"></a>O processo de migração

Quando você alterna da McAfee para o Microsoft Defender para o Ponto de Extremidade, você segue um processo que pode ser dividido em três fases: Preparar, Configurar e Integração. 

![Fases de migração - preparar a instalação interna](images/phase-diagrams/migration-phases.png)

|Fase |Descrição |
|--|--|
|[Prepare-se para sua migração](mcafee-to-microsoft-defender-prepare.md) |Durante a [**fase Preparar,**](mcafee-to-microsoft-defender-prepare.md) atualize os dispositivos da sua organização, receba o Microsoft Defender para Ponto de Extremidade, planeje suas funções e permissões e conceda acesso ao Central de Segurança do Microsoft Defender. Você também configura o proxy do dispositivo e as configurações da Internet para habilitar a comunicação entre os dispositivos da sua organização e o Microsoft Defender para o Ponto de Extremidade. |
|[Configurar o Microsoft Defender para Ponto de Extremidade](mcafee-to-microsoft-defender-setup.md) |Durante a [**fase de**](mcafee-to-microsoft-defender-setup.md) Instalação, você Microsoft Defender Antivírus e defini-lo como modo passivo. Você também configura configurações & exclusões para Microsoft Defender Antivírus e sua solução de proteção de ponto de extremidade existente. Em seguida, você cria seus grupos de dispositivos, coleções e unidades organizacionais. Por fim, você configura suas políticas antimalware e configurações de proteção em tempo real.|
|[Integração ao Microsoft Defender para Ponto de Extremidade](mcafee-to-microsoft-defender-onboard.md) |Durante [](mcafee-to-microsoft-defender-onboard.md) a fase Onboard, você integra seus dispositivos no Microsoft Defender para Ponto de Extremidade, confirma se o Microsoft Defender Antivírus está sendo executado no modo passivo e verifique se seus pontos de extremidade estão se comunicando com o Defender para Ponto de Extremidade. Em seguida, desinstale a McAfee e certifique-se de que o Defender for Endpoint está funcionando corretamente. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>O que está incluído no Microsoft Defender para Ponto de Extremidade?

Neste guia de migração, nos concentramos na proteção de próxima geração e detecção e resposta de ponto de extremidade [recursos](overview-endpoint-detection-response.md) como ponto de partida para mover para o Microsoft Defender para o Ponto de Extremidade. [](microsoft-defender-antivirus-in-windows-10.md) No entanto, o Microsoft Defender para Ponto de Extremidade inclui muito mais do que proteção de antivírus e ponto de extremidade. O Microsoft Defender ATP é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta. A tabela a seguir resume recursos e recursos no Microsoft Defender para Ponto de Extremidade. 

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

**Quer saber mais? Consulte [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).**

## <a name="next-step"></a>Próxima etapa

- Prossiga [para Preparar sua migração](mcafee-to-microsoft-defender-prepare.md).
