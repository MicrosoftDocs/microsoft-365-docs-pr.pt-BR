---
title: Níveis de automação em investigação e correção automatizadas
description: Obter uma visão geral dos níveis de automação e como eles funcionam no Microsoft Defender para Ponto de Extremidade
keywords: automated, investigation, level, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 10/22/2020
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 013e01e9f84cae01258afc6ba139b7b5ada5912f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934112"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Níveis de automação em recursos automatizados de investigação e correção

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Os recursos automatizados de investigação e correção (AIR) no Microsoft Defender para Endpoint podem ser configurados para um dos vários níveis de automação. Seu nível de automação afeta se as ações de correção após as investigações air são realizadas automaticamente ou somente após aprovação.  
- *A automação* completa (recomendada) significa que as ações de correção são tomadas automaticamente em artefatos determinados como mal-intencionados.
- *A semi automação* significa que algumas ações de correção são realizadas automaticamente, mas outras ações de correção aguardam aprovação antes de serem tomadas. (Consulte a tabela em [Níveis de automação](#levels-of-automation).)
- Todas as ações de correção, pendentes ou concluídas, são controladas no Centro de Ações ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 

> [!TIP]
> Para melhores resultados, recomendamos o uso de automação completa quando você [configura AIR](configure-automated-investigations-remediation.md). Os dados coletados e analisados no último ano mostram que os clientes que estão usando a automação completa tiveram 40% mais amostras de malware de alta confiança removidas do que os clientes que estão usando níveis inferiores de automação. A automação completa pode ajudar a liberar seus recursos de operações de segurança para se concentrar mais em suas iniciativas estratégicas.

## <a name="levels-of-automation"></a>Níveis de automação

A tabela a seguir descreve cada nível de automação e como ela funciona.

|Nível de automação | Descrição|
|:---|:---|
|**Completo - correção de ameaças automaticamente** <br/>(também conhecido como *automação completa*)| Com a automação completa, as ações de correção são executadas automaticamente. Todas as ações de correção realizadas podem ser exibidas na [Central de Ações](auto-investigation-action-center.md) na **guia** Histórico. Se necessário, uma ação de correção pode ser desfeita.<br/><br/>**_A automação_* completa é recomendada e selecionada por padrão para locatários criados em ou após 16 de agosto de 2020 com o Microsoft Defender para Ponto de Extremidade, sem grupos de dispositivos definidos ainda.*  |
|**Semi - exigir aprovação para qualquer correção** <br/>(também conhecido como *semi-automação*)| Com esse nível de semi automação, a aprovação é necessária para *qualquer* ação de correção. Essas ações pendentes podem ser exibidas e aprovadas na [Central de](auto-investigation-action-center.md)Ações , na **guia Pendente.**<br/><br/>*Esse nível de semi automação é selecionado por padrão para locatários criados antes de 16 de agosto de 2020 com o Microsoft Defender para Ponto de Extremidade, sem grupos de dispositivos definidos.*|
|**Semi - exigir aprovação para correção de pastas principais** <br/>(também um tipo de *semi-automação*)  | Com esse nível de semi automação, a aprovação é necessária para todas as ações de correção necessárias em arquivos ou executáveis que estão em pastas principais. As pastas principais incluem diretórios do sistema operacional, como o **Windows** ( `\windows\*` ).<br/><br/>As ações de correção podem ser executadas automaticamente em arquivos ou executáveis que estão em outras pastas (não essenciais). <br/><br/>Ações pendentes para arquivos ou executáveis em pastas principais podem ser exibidas e aprovadas no Centro de Ações [,](auto-investigation-action-center.md)na **guia** Pendente. <br/><br/>As ações realizadas em arquivos ou executáveis em outras pastas podem ser exibidas na Central de Ações [,](auto-investigation-action-center.md) **na** guia Histórico. |
|**Semi - exigir aprovação para correção de pastas não temporárias** <br/>(também um tipo de *semi-automação*)| Com esse nível de semi automação, a aprovação é necessária para todas as ações de correção necessárias em arquivos ou executáveis que não *estão* em pastas temporárias. <br/><br/>Pastas temporárias podem incluir os seguintes exemplos: <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>As ações de correção podem ser executadas automaticamente em arquivos ou executáveis que estão em pastas temporárias. <br/><br/>Ações pendentes para arquivos ou executáveis que não estão em pastas temporárias podem ser exibidas e aprovadas na Central de Ações [,](auto-investigation-action-center.md)na **guia** Pendente.<br/><br/>As ações realizadas em arquivos ou executáveis em pastas temporárias podem ser exibidas e aprovadas na Central de Ações [,](auto-investigation-action-center.md)na guia **Histórico.**   |
|**Nenhuma resposta automatizada** <br/>(também conhecido como sem *automação*) | Sem automação, a investigação automatizada não é executado nos dispositivos da sua organização. Como resultado, nenhuma ação de correção é tomada ou pendente como resultado de uma investigação automatizada. No entanto, outros recursos [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)de proteção contra ameaças, como a proteção contra aplicativos potencialmente indesejados, podem estar em vigor, dependendo de como seus recursos de proteção antivírus e de última geração estão configurados.<br/><br/>***Não é *recomendável*** usar a opção sem automação, pois reduz a postura de segurança dos dispositivos da sua organização. [Considere configurar seu nível de automação para automação completa (ou pelo menos semi-automação)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups)*. |

## <a name="important-points-about-automation-levels"></a>Pontos importantes sobre níveis de automação

- A automação completa se mostrou confiável, eficiente e segura e é recomendada para todos os clientes. A automação completa libera seus recursos críticos de segurança para que eles possam se concentrar mais em suas iniciativas estratégicas.

- Os novos locatários (que incluem locatários criados em ou após 16 de agosto de 2020) com o Microsoft Defender para Ponto de Extremidade são definidos como automação completa por padrão.

- Se sua equipe de segurança definiu grupos de dispositivos com um nível de automação, essas configurações não serão alteradas pelas novas configurações padrão que estão sendo implantadas. 

- Você pode manter suas configurações de automação padrão ou alterá-las de acordo com suas necessidades organizacionais. Para alterar suas configurações, [de definir seu nível de automação](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups).

## <a name="next-steps"></a>Próximas etapas

- [Configurar recursos automatizados de investigação e correção no Microsoft Defender para Ponto de Extremidade](configure-automated-investigations-remediation.md)

- [Visite o Centro de Ações](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
