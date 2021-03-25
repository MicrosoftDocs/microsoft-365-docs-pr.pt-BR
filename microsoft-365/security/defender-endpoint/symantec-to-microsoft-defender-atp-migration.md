---
title: Migrar da Symantec para o Microsoft Defender para o Ponto de Extremidade
description: Obter uma visão geral de como fazer a mudança da Symantec para o Microsoft Defender para o Ponto de Extremidade
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
- m365solution-symantecmigrate
- m365solution-overview
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 6517359c805bb449d075e401283a79a791461630
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198976"
---
# <a name="migrate-from-symantec-to-microsoft-defender-for-endpoint"></a>Migrar da Symantec para o Microsoft Defender para o Ponto de Extremidade
Se você estiver planejando mudar do Symantec Endpoint Protection (Symantec) para o [Microsoft Defender para](https://docs.microsoft.com/windows/security/threat-protection) Ponto de Extremidade (Microsoft Defender para Ponto de Extremidade), você está no lugar certo. Use este artigo como um guia.

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

:::image type="content" source="images/symantec-mde-migration.png" alt-text="Visão geral da migração da Symantec para o Defender para o Ponto de Extremidade":::

Quando você faz a mudança da Symantec para o Defender para o Ponto de Extremidade, você começa com sua solução Symantec no modo ativo, configura o Defender para o Ponto de Extremidade no modo passivo, integra o Defender para o Ponto de Extremidade e define o Defender para o Ponto de Extremidade como modo ativo e remove a Symantec.

## <a name="the-migration-process"></a>O processo de migração

Quando você alterna da Symantec para o Microsoft Defender para o Ponto de Extremidade, você segue um processo que pode ser dividido em três fases, conforme descrito na tabela a seguir:

![Fases de migração - preparar, configurar, integração](images/phase-diagrams/migration-phases.png)

|Fase |Descrição |
|--|--|
|[Prepare-se para sua migração](symantec-to-microsoft-defender-atp-prepare.md) |Durante a **fase Preparar,** você recebe o Microsoft Defender para Ponto de Extremidade, planeja suas funções e permissões e concede acesso ao Centro de Segurança do Microsoft Defender. Você também configura o proxy do dispositivo e as configurações da Internet para habilitar a comunicação entre os dispositivos da sua organização e o Microsoft Defender para o Ponto de Extremidade. |
|[Configurar o Microsoft Defender para Ponto de Extremidade](symantec-to-microsoft-defender-atp-setup.md) |Durante a **fase de** Instalação, você configura configurações e exclusões para Microsoft Defender Antivírus, Microsoft Defender para Ponto de Extremidade e Proteção de Ponto de Extremidade da Symantec. Você também cria grupos de dispositivos, coleções e unidades organizacionais. Por fim, você configura suas políticas antimalware e configurações de proteção em tempo real.|
|[Integração ao Microsoft Defender para Ponto de Extremidade](symantec-to-microsoft-defender-atp-onboard.md) |Durante a **fase Onboard,** você integra seus dispositivos no Microsoft Defender para Ponto de Extremidade e verifica se esses dispositivos estão se comunicando com o Microsoft Defender para Ponto de Extremidade. Por fim, desinstale a Symantec e certifique-se de que a proteção por meio do Microsoft Defender para Ponto de Extremidade está no modo ativo. |

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

- Prossiga [para Preparar sua migração](symantec-to-microsoft-defender-atp-prepare.md).
