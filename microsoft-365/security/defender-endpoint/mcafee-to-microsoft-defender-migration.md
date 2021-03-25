---
title: Migrar da McAfee para o Microsoft Defender para o Ponto de Extremidade
description: Faça a mudança da McAfee para o Microsoft Defender para o Ponto de Extremidade. Leia este artigo para uma visão geral.
keywords: migração, proteção avançada contra ameaças do Windows Defender, atp, edr
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
ms.topic: conceptual
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 53d9e68fa357d07cf70ab2282de9cee9fc0bd90d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185630"
---
# <a name="migrate-from-mcafee-to-microsoft-defender-for-endpoint"></a>Migrar da McAfee para o Microsoft Defender para o Ponto de Extremidade

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se você estiver planejando mudar do McAfee Endpoint Security (McAfee) para [o Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) Ponto de Extremidade (Microsoft Defender para Ponto de Extremidade), você está no lugar certo. Use este artigo como um guia.


:::image type="content" source="images/mcafee-mde-migration.png" alt-text="Visão geral da migração da McAfee para o Defender para o Ponto de Extremidade":::

Quando você faz a mudança da McAfee para o Defender para o Ponto de Extremidade, você começa com sua solução McAfee no modo ativo, configura o Defender para o Ponto de Extremidade no modo passivo, integra o Defender para Ponto de Extremidade e define o Defender para o Ponto de Extremidade como modo ativo e remove a McAfee.

## <a name="the-migration-process"></a>O processo de migração

Quando você alterna da McAfee para o Microsoft Defender para o Ponto de Extremidade, você segue um processo que pode ser dividido em três fases: Preparar, Configurar e Integração. 

![Fases de migração - preparar a instalação interna](images/phase-diagrams/migration-phases.png)

|Fase |Descrição |
|--|--|
|[Prepare-se para sua migração](mcafee-to-microsoft-defender-prepare.md) |Durante a fase [**Preparar,**](mcafee-to-microsoft-defender-prepare.md) atualize os dispositivos da sua organização, receba o Microsoft Defender para Ponto de Extremidade, planeje suas funções e permissões e conceda acesso ao Centro de Segurança do Microsoft Defender. Você também configura o proxy do dispositivo e as configurações da Internet para habilitar a comunicação entre os dispositivos da sua organização e o Microsoft Defender para o Ponto de Extremidade. |
|[Configurar o Microsoft Defender para Ponto de Extremidade](mcafee-to-microsoft-defender-setup.md) |Durante [](mcafee-to-microsoft-defender-setup.md) a fase de Instalação, você habilita o Microsoft Defender Antivírus e garante que ele está no modo passivo e configura as configurações & exclusões para o Microsoft Defender Antivírus, o Microsoft Defender para o Ponto de Extremidade e a McAfee. Você também cria grupos de dispositivos, coleções e unidades organizacionais. Por fim, você configura suas políticas antimalware e configurações de proteção em tempo real.|
|[Integração ao Microsoft Defender para Ponto de Extremidade](mcafee-to-microsoft-defender-onboard.md) |Durante a [**fase Onboard,**](mcafee-to-microsoft-defender-onboard.md) você integra seus dispositivos no Microsoft Defender para Ponto de Extremidade e verifica se esses dispositivos estão se comunicando com o Microsoft Defender para Ponto de Extremidade. Por fim, desinstale a McAfee e certifique-se de que a proteção por meio do Microsoft Defender Antivírus & o Microsoft Defender para Ponto de Extremidade está no modo ativo. |

## <a name="whats-included-in-microsoft-defender-for-endpoint"></a>O que está incluído no Microsoft Defender para Ponto de Extremidade?

Neste guia de migração, nos concentramos nos recursos de detecção e resposta de proteção e ponto de extremidade de próxima geração como ponto de partida para migrar para o Microsoft Defender para o Ponto de Extremidade. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) No entanto, o Microsoft Defender para Ponto de Extremidade inclui muito mais do que proteção de antivírus e ponto de extremidade. O Microsoft Defender ATP é uma plataforma unificada para proteção preventiva, detecção pós-violação, investigação automatizada e resposta. A tabela a seguir resume recursos e recursos no Microsoft Defender para Ponto de Extremidade. 

| Recurso/Funcionalidade | Descrição |
|---|---|
| [Gerenciamento de & de vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) | Os & gerenciamento de vulnerabilidades ajudam a identificar, avaliar e remediar as deficiências em seus pontos de extremidade (como dispositivos). |
| [Redução da superfície do ataque.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-attack-surface-reduction) | As regras de redução de superfície de ataque ajudam a proteger os dispositivos e aplicativos da sua organização contra ameaças cibernéticas e ataques. |
| [Proteção de última geração](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) | A proteção de última geração inclui o Microsoft Defender Antivírus para ajudar a bloquear ameaças e malware. |
| [Detecção e resposta do terminal.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) | Os recursos de detecção e resposta do ponto de extremidade detectam, investigam e respondem a tentativas de intrusão e violações ativas.  |
| [Busca avançada](advanced-hunting-overview.md) | Os recursos avançados de busca permitem que sua equipe de operações de segurança localize indicadores e entidades de ameaças conhecidas ou potenciais. |
| [Bloqueio comportamental e contenção](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) | Os recursos de bloqueio comportamental e de contenção ajudam a identificar e parar ameaças, com base em seus comportamentos e no processo de árvores, mesmo quando a ameaça iniciou a execução. |
| [Investigação e correção automatizadas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations) | Os recursos automatizados de investigação e resposta examinam alertas e tomarão medidas imediatas de correção para resolver violações. |
| [Serviço de busca de ameaças](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-threat-experts) (Especialistas em Ameaças da Microsoft) | Os serviços de busca de ameaças fornecem às equipes de operações de segurança monitoramento e análise de nível especializado e ajudam a garantir que as ameaças críticas não sejam perdidas. |

**Quer saber mais? Consulte [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).**

## <a name="next-step"></a>Próxima etapa

- Prossiga [para Preparar sua migração](mcafee-to-microsoft-defender-prepare.md).
