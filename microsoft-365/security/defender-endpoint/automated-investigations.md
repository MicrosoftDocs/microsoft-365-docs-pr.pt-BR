---
title: Usar investigações automatizadas para investigar e remediar ameaças
description: Entenda o fluxo de investigação automatizado no Microsoft Defender para Ponto de Extremidade.
keywords: automated, investigation, detection, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: e52471e1b3e9ee3a410de493b536f9d360d60624
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844437"
---
# <a name="overview-of-automated-investigations"></a>Visão geral das investigações automatizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Quer ver como funciona? Assista ao seguinte vídeo: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

A tecnologia na investigação automatizada usa vários algoritmos de inspeção e se baseia em processos usados por analistas de segurança. Os recursos AIR foram projetados para examinar alertas e tomar medidas imediatas para resolver violações. Os recursos air reduzem significativamente o volume de alerta, permitindo que as operações de segurança se concentrem em ameaças mais sofisticadas e em outras iniciativas de alto valor. Todas as ações de correção, pendentes ou concluídas, são controladas no [Centro de Ações](auto-investigation-action-center.md). No Centro de ações, as ações pendentes são aprovadas (ou rejeitadas) e as ações concluídas podem ser desfeitas, se necessário.

Este artigo fornece uma visão geral do AIR e inclui links para as próximas etapas e recursos adicionais.

> [!TIP]
> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).

## <a name="how-the-automated-investigation-starts"></a>Como a investigação automatizada é iniciada

Uma investigação automatizada pode começar quando um alerta é disparado ou quando um operador de segurança inicia a investigação.

|Situação  |O que acontece  |
|---------|---------|
|Um alerta é disparado     | Em geral, uma investigação automatizada é iniciada quando um [alerta](review-alerts.md) é disparado e [um incidente](view-incidents-queue.md) é criado. Por exemplo, suponha que um arquivo mal-intencionado reside em um dispositivo. Quando esse arquivo é detectado, um alerta é disparado e um incidente é criado. Um processo de investigação automatizado começa no dispositivo. Como outros alertas são gerados devido ao mesmo arquivo em outros dispositivos, eles são adicionados ao incidente associado e à investigação automatizada.         |
|Uma investigação é iniciada manualmente     | Uma investigação automatizada pode ser iniciada manualmente pela sua equipe de operações de segurança. Por exemplo, suponha que um operador de segurança está revendo uma lista de dispositivos e observe que um dispositivo tem um nível de alto risco. O operador de segurança pode selecionar o dispositivo na lista para abrir seu sobrevoo e, em seguida, **selecionar Iniciar Investigação Automatizada**. |

## <a name="how-an-automated-investigation-expands-its-scope"></a>Como uma investigação automatizada expande seu escopo

Enquanto uma investigação está em execução, quaisquer outros alertas gerados do dispositivo são adicionados a uma investigação automatizada em andamento até que essa investigação seja concluída. Além disso, se a mesma ameaça for vista em outros dispositivos, esses dispositivos serão adicionados à investigação.

Se uma entidade for vista em outro dispositivo, o processo de investigação automatizada expandirá seu escopo para incluir esse dispositivo e uma playbook de segurança geral será iniciada nesse dispositivo. Se 10 ou mais dispositivos são encontrados durante esse processo de expansão da mesma entidade, essa ação de expansão requer uma aprovação e fica visível na guia Ações **pendentes.**

## <a name="how-threats-are-remediated"></a>Como as ameaças são remediadas

À medida que os alertas são disparados e uma investigação automatizada é executado, um veredito é gerado para cada parte das evidências investigadas. Os vereditos podem ser 
- *Mal-intencionado;*
- *Suspeito;* ou 
- *Nenhuma ameaça encontrada*. 

À medida que os vereditos são atingidos, investigações automatizadas podem resultar em uma ou mais ações de correção. Exemplos de ações de correção incluem o envio de um arquivo para a quarentena, a interrupção de um serviço, a remoção de uma tarefa agendada e muito mais. Para saber mais, confira [Ações de correção.](manage-auto-investigation.md#remediation-actions)  

Dependendo do [](automation-levels.md) nível de automação definido para sua organização, bem como de outras configurações de segurança, as ações de correção podem ocorrer automaticamente ou somente após a aprovação pela sua equipe de operações de segurança. As configurações de segurança adicionais que podem afetar a correção automática incluem [proteção contra](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) aplicativos potencialmente indesejados (PUA). 

Todas as ações de correção, pendentes ou concluídas, são controladas no [Centro de Ações](auto-investigation-action-center.md). Se necessário, sua equipe de operações de segurança pode desfazer uma ação de correção. Para saber mais, confira Revisar e aprovar ações [de correção após uma investigação automatizada.](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

> [!TIP]
> Confira a nova página de investigação unificada no centro Microsoft 365 segurança. Para saber mais, consulte [(NEW!) Página de investigação unificada](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).


## <a name="requirements-for-air"></a>Requisitos para AIR

Sua organização deve ter o Defender para Ponto de Extremidade (consulte [Requisitos mínimos para o Microsoft Defender para Ponto de Extremidade](minimum-requirements.md)).

Atualmente, o AIR dá suporte apenas às seguintes versões do sistema operacional:
- Windows Server 2019
- Windows 10, versão 1709 (Build 16299.1085 com [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) ou posterior
- Windows 10, versão 1803 (build 17134.704 do sistema operacional com [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) ou posterior
- Windows 10, versão [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) ou posterior

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre níveis de automação](automation-levels.md)
- [Consulte o guia interativo: Investigar e correção de ameaças com o Microsoft Defender para Ponto de Extremidade](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Configurar recursos automatizados de investigação e correção no Microsoft Defender para Ponto de Extremidade](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Confira também

- [Proteção PUA](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Investigação e resposta automatizadas no Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/office-365-air)
- [Investigação e resposta automatizadas no Microsoft 365 Defender](/microsoft-365/security/defender/mtp-autoir)
