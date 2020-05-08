---
title: Recursos de investigação e resposta automatizados no Microsoft Threat Protection
description: Obter uma visão geral dos recursos de investigação e resposta automatizados na Proteção contra Ameaça da Microsoft
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 6ac6d74b027cc533f689c1d67c7fce246c73984f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166156"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Recursos de investigação e resposta automatizados (AIR) na proteção contra ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Como os alertas de segurança são disparados, a equipe de operações de segurança pode examinar os alertas e realizar etapas para proteger sua organização. Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento. As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas. Os recursos de investigação e resposta automatizada (AIR) no Microsoft Threat Protection podem ajudar. O AIR é como ter um analista virtual em seu centro de operações de segurança.

## <a name="your-virtual-analyst"></a>Seu analista virtual

Imagine ter um analista virtual em sua equipe de operações de segurança do Nível 1 / Nível 2. O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças. O assistente virtual pode funcionar 24 horas e assumir uma carga significativa de investigações e correções de ameaças. Esse assistente virtual pode reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outros projetos estratégicos importantes. Se este cenário soa como ficção científica, não é! Esse analista virtual faz parte do seu pacote de Proteção contra Ameaças da Microsoft e seu nome é *investigação e resposta automatizadas* (AIR).

O AIR permite à sua equipe de operações de segurança aumentar drasticamente a capacidade da sua organização para lidar com alertas e incidentes de segurança. Com o AIR, você pode reduzir o custo de lidar com atividades de investigação e correção e aproveitar ao máximo o pacote de proteção contra ameaças. O AIR ajuda sua equipe de operações de segurança:

1. Determinar se uma ameaça requer ação;
2. Executar (ou recomendar) todas as ações de correção necessárias;
3. Determinar quais investigações adicionais devem ocorrer; e
4. Repetir o processo conforme necessário para outros alertas.

## <a name="the-automated-investigation-process"></a>O processo de investigação automatizada

**Alerta** > **incidente** > **investigação automatizada** > **veredito** > **ação de correção**

Um alerta disparado cria um incidente, que pode iniciar uma investigação automatizada. Essa investigação pode resultar em uma ou mais ações de correção. Na Proteção contra Ameaças da Microsoft, cada investigação automatizada correlaciona sinais entre a Proteção Avançada contra Ameaças do Azure (Azure ATP), a Proteção Avançada contra Ameaças do Microsoft Defender (Microsoft Defender ATP) e a Proteção Avançada contra Ameaças do Office 365 (Office 365 ATP), conforme resumido na tabela a seguir: 

|Entidades |Serviços de proteção contra ameaças  |
|---------|---------|
|Dispositivos (também chamados de pontos de extremidade)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Conteúdo de email (arquivos e mensagens nas caixas de correio)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Cada investigação gera verdicts (*mal-intencionado*, *suspeito*ou *nenhuma ameaça encontrada*) para cada evidência investigada. Dependendo do tipo de ameaça e veredicto resultante, as ações de correção ocorrerão automaticamente ou após a aprovação da equipe de operações de segurança da sua organização. As ações pendentes e concluídas estão listadas na [Central de ações](mtp-action-center.md).

> [!TIP]
> Se você acha que algo foi perdido ou detectado incorretamente por recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft, vamos nos lembrar! Veja [como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados (Air) no Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída. Se uma entidade incriminada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade, e um manual geral de segurança será executado. 

> [!NOTE]
> Nem todo alerta aciona uma investigação automatizada e nem toda investigação resulta em ações de correção automatizadas; tudo isso depende de como o AIR está configurado para sua organização. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Requisitos do AIR na Proteção contra Ameaças da Microsoft

| | |
|--|--|
|Requisitos de assinatura |Uma das seguintes opções: <br/>-Microsoft 365 e5 <br/>-Microsoft 365 a5 <br/>– Segurança da Microsoft 365 e5<br/>– Segurança da Microsoft 365 a5<br/>– Office 365 E5 Plus Enterprise Mobility + Security E5 mais Windows e5<br/><br/>Consulte [requisitos de licenciamento do Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Requisitos de rede |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) habilitado<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configurado<br/>- [MCAS integrado ao Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisitos de máquina do Windows |– Windows 10, versão 1709 ou posterior instalado (consulte [informações sobre a versão do Windows 10](https://docs.microsoft.com/windows/release-information/)) com os seguintes serviços de proteção contra ameaças configurados:<br/>- [Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Antivírus do Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Proteção para arquivos de conteúdo de email e do Office |[Proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) configurada |
|Permissões |- Para configurar a AIR, você deve ter a função de Administrador Global ou Administrador de Segurança, atribuída no Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) ou no centro de administração do Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)).<br/><br/>Para usar os recursos da AIR, confira [Permissões necessárias para as tarefas da Central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Próximas etapas

- [Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas](mtp-autoir-actions.md)
- [Saiba mais sobre a Central de Ações](mtp-action-center.md)
