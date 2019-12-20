---
title: Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft
description: Obter uma visão geral dos recursos de investigação e resposta automatizados na Proteção contra Ameaça da Microsoft
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: ea3201838e625969a239aee4339e0de605d95c55
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808606"
---
# <a name="automated-investigation-and-response-air-in-microsoft-threat-protection"></a>Investigação e resposta automatizadas (AIR) na Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

## <a name="your-virtual-analyst"></a>Seu analista virtual

À medida que os alertas de segurança são disparados, cabe à sua equipe de operações de segurança examinar esses alertas e executar etapas para proteger sua organização. Priorizar e investigar alertas pode consumir muito tempo, especialmente quando novos alertas continuam chegando enquanto uma investigação está em andamento. As equipes de operações de segurança podem se sentir sobrecarregadas pelo simples volume de ameaças que devem ser monitoradas e protegidas. 

Imagine ter um analista virtual em sua equipe de operações de segurança do Nível 1 / Nível 2. O analista virtual imita as etapas ideais que as operações de segurança poderiam executar para investigar e corrigir ameaças. O assistente virtual pode funcionar 24 horas e assumir uma carga significativa de investigações e correções de ameaças. Esse assistente virtual pode reduzir significativamente o tempo de resposta, liberando sua equipe de operações de segurança para outros projetos estratégicos importantes. Se esse cenário parece ficção científica, não é! Esse analista virtual faz parte do seu pacote de Proteção contra Ameaças da Microsoft e seu nome é *investigação e resposta automatizadas* (AIR).

O AIR permite à sua equipe de operações de segurança aumentar drasticamente a capacidade da sua organização para lidar com alertas e incidentes de segurança. Com o AIR, você pode reduzir o custo de lidar com atividades de investigação e correção e aproveitar ao máximo o pacote de proteção contra ameaças. O AIR ajuda sua equipe de operações de segurança:

1.  Determinar se uma ameaça requer ação;
2.  Executar (ou recomendar) todas as ações de correção necessárias;
3.  Determinar quais investigações adicionais devem ocorrer; e
4.  Repetir o processo conforme necessário para outros alertas.

## <a name="the-automated-investigation-process"></a>O processo de investigação automatizada

**Alerta** > **incidente** > **investigação automatizada** > **veredito** > **ação de correção**

Em um nível alto, um alerta disparado cria um incidente, que pode iniciar uma investigação automática. Essa investigação pode resultar em uma ou mais ações de correção. Na Proteção contra Ameaças da Microsoft, cada investigação automatizada correlaciona sinais entre a Proteção Avançada contra Ameaças do Azure (Azure ATP), a Proteção Avançada contra Ameaças do Microsoft Defender (Microsoft Defender ATP) e a Proteção Avançada contra Ameaças do Office 365 (Office 365 ATP), conforme resumido na tabela a seguir: 

|Entidades |Serviços de proteção contra ameaças  |
|---------|---------|
|Dispositivos (também chamados de pontos de extremidade)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|Conteúdo de email (arquivos e mensagens nas caixas de correio)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |


Cada investigação gera verditos (*Malicioso*, *Suspeito* ou *Limpo*) para cada evidência investigada. Dependendo do tipo de ameaça e veredito resultante, as ações de correção ocorrem automaticamente ou mediante aprovação da equipe de operações de segurança da sua organização. As ações pendentes e concluídas estão listadas na [Central de ações](mtp-action-center.md).

Enquanto uma investigação está em execução, quaisquer outros alertas relacionados que surgirem são adicionados à investigação até que ela seja concluída. Se uma entidade incriminada for vista em outro lugar, a investigação automatizada expandirá seu escopo para incluir essa entidade, e um manual geral de segurança será executado. 

> [!NOTE]
> Nem todo alerta aciona uma investigação automatizada e nem toda investigação resulta em ações de correção automatizadas; tudo isso depende de como o AIR está configurado para sua organização. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Requisitos do AIR na Proteção contra Ameaças da Microsoft

| | |
|--|--|
|Requisitos de assinatura |-Microsoft 365 E5 ou Microsoft 365 E3 juntamente com Proteção contra Identidade e Ameaças<br/>- Confira [planos do Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans)|
|Requisitos de rede |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) habilitado<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) configurado<br/>- [MCAS integrado ao Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Requisitos de máquina do Windows |- Windows 10, versão 1709 ou posterior instalado (Confira[Informações sobre a versão do Windows 10](https://docs.microsoft.com/windows/release-information/))<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) configurado <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) configurado |
|Permissões |- Para *configurar* a AIR, você deve ter a função de **Administrador Global** ou **Administrador de Segurança**, atribuída no Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) ou no centro de administração do Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com)).<br/><br/>Para *usar* os recursos da AIR, confira [Permissões necessárias para as tarefas da Central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks). |

## <a name="next-steps"></a>Próximas etapas

- [Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas](mtp-autoir-actions.md)
- [Saiba mais sobre a Central de Ações](mtp-action-center.md)
