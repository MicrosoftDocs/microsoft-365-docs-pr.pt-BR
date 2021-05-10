---
title: Noções básicas do Explorador de Ameaças e detecções em tempo real no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Use detecções do Explorer ou em tempo real para investigar e responder a ameaças com eficiência.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300092"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>Noções básicas sobre o Explorador de Ameaças e Detecções em Tempo Real

Neste artigo:

- [Diferenças entre o Explorador de Ameaças e detecções em tempo real](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [Licenças e permissões necessárias](#required-licenses-and-permissions)

> [!NOTE]
> Isso faz parte de uma série de 3 artigos no Explorador de Ameaças **(Explorer),** segurança de **email** e noções **básicas** de detecções do Explorer e em tempo real (como diferenças entre as ferramentas e permissões necessárias para operá-las).  Os outros dois artigos desta série são Busca de ameaças no [Explorador de Ameaças](threat-hunting-in-threat-explorer.md) e Segurança de Email com o Explorador de [Ameaças.](email-security-in-microsoft-defender.md)

Este artigo explica a diferença entre a exploração de ameaças e o relatório de detecções em tempo real e as licenças e permissões necessárias.

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se sua organização tiver o [Microsoft Defender](defender-for-office-365.md)para Office 365 , e você tiver as permissões [,](#required-licenses-and-permissions)você poderá usar o **Explorador** de Ameaças (chamado Explorer **)** ou detecções em tempo **real** para detectar e remediar ameaças.

No Centro **de Conformidade & segurança,** vá para Gerenciamento de ameaças **e** escolha **Explorer** _ou_ Detecções em tempo **real.**

<br>

****

|Com o Microsoft Defender para Office 365 Plano 2, você verá:|Com o Microsoft Defender para Office 365 Plano 1, consulte:|
|---|---|
|![Explorador de ameaças](../../media/threatmgmt-explorer.png)|![Detecções em tempo real](../../media/threatmgmt-realtimedetections.png)|
|

Com essas ferramentas, você pode:

- Consulte malware detectado por Microsoft 365 segurança.
- Exibir URL de phishing e clicar em dados de veredito.
- Inicie um processo automatizado de investigação e resposta a partir de uma exibição no Explorer.
- Investigar emails mal-intencionados e muito mais.

Para obter mais informações, consulte [Segurança de email com o Explorador de Ameaças.](email-security-in-microsoft-defender.md)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>Diferenças entre o Explorador de Ameaças e detecções em tempo real

- *Detecções em tempo* real é uma ferramenta de relatório disponível no Defender para Office 365 Plano 1. *O Explorador* de Ameaças é uma ferramenta de busca e correção de ameaças disponível no Defender para Office 365 Plano 2.
- O relatório de detecções em tempo real permite que você veja detecções em tempo real. O Explorador de Ameaças também faz isso, mas fornece detalhes adicionais para um determinado ataque, como realçamento de campanhas de ataque, e oferece às equipes de operações de segurança a capacidade de correção de ameaças (incluindo a acionamento de uma investigação de Investigação e Resposta Automatizada [).](automated-investigation-response-office.md)
- Uma *exibição de todos* os emails está disponível no Explorador de Ameaças, mas não está incluída no relatório de detecções em tempo real.
- Recursos avançados de filtragem e ações de correção estão incluídos no Explorador de Ameaças. Para obter mais informações, consulte [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

## <a name="required-licenses-and-permissions"></a>Licenças e permissões necessárias

Você deve ter [o Microsoft Defender para Office 365](defender-for-office-365.md) usar detecções do Explorer ou em tempo real:

- Mas o Explorer só está incluído no Defender para Office 365 Plano 2.
- O relatório de detecções em tempo real está incluído no Defender para Office 365 Plano 1.

As equipes de Operações de Segurança precisam atribuir licenças para todos os usuários que devem ser protegidos pelo Defender para Office 365 e estar cientes de que as detecções do Explorer e em tempo real mostram dados de detecção para usuários licenciados.

Para exibir e usar *detecções do* Explorer ou em tempo real, você deve ter o seguinte:

- Para o Centro de Conformidade & segurança:

  - Gerenciamento de Organização
  - Administrador de Segurança (isso pode ser atribuído no Azure Active Directory de administração ( <https://aad.portal.azure.com> )
  - Leitor de segurança

- Para Exchange Online:

  - Gerenciamento de Organização
  - Gerenciamento de Organização Somente Exibição
  - Destinatários Somente para Exibição
  - Gerenciamento de Conformidade

Para saber mais sobre funções e permissões, consulte os seguintes recursos:

- [Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)
- [Permissões de recursos no Exchange Online](/exchange/permissions-exo/feature-permissions)
- [PowerShell do Exchange Online](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>Mais informações
- [O Explorador de Ameaças coleta detalhes de email na página entidade de email](mdo-email-entity-page.md)
- [Localizar e investigar emails mal-intencionados entregues](investigate-malicious-email-that-was-delivered.md)
- [Exibir arquivos mal-intencionados detectados no SharePoint Online, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Investigação e resposta automatizadas na Proteção contra Ameaças da Microsoft](automated-investigation-response-office.md)