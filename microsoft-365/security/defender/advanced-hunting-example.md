---
title: Exemplo de busca avançada para o Microsoft Defender para Office 365
description: Começar a pesquisar ameaças de email usando a busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965136"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Exemplo de busca avançada para o Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Deseja começar a procurar ameaças de email usando a busca avançada? Tente o seguinte:

A seção [Introdução](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) do [artigo do Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) tem blocos de configuração iniciais lógicos com a seguinte aparência:

1. Configure tudo com 'Anti' no nome.
   - Antimalware
   - Anti-phishing
   - Antispam
2. Configurar tudo com "Cofre" no nome.
   - Links seguros
   - Anexos seguros
3. Defenda as cargas de trabalho (por exemplo, SharePoint Online, OneDrive e Teams).
4. Proteja com limpeza automática zero hora.

Junto com um [link](../office-365-security/protect-against-threats.md) para começar imediatamente a configuração no 1º Dia.

A última etapa na **Introdução** é proteger os usuários com a **Limpeza Automática Zero Hora**, também conhecida como ZAP. Saber se seus esforços para limpar um email suspeito ou mal-intencionado após a entrega foram bem-sucedidos pode ser muito importantes.

Navegar rapidamente para a linguagem de consulta Kusto para buscar problemas é uma das vantagens de converter esses dois centros de segurança. As equipes de segurança podem monitorar as faltas do ZAP, dando suas próximas etapas [aqui](https://security.microsoft.com/advanced-hunting), em **Hunting** \> **Advanced Hunting**.

1. Na página Busca Avançada, clique **em Consulta**.
1. Copie a consulta a seguir na janela de consultas.
1. Selecione **Executar consulta**.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="A página de busca avançada (em Busca) com Consulta selecionada na parte superior do painel de consulta e a execução de uma consulta Kusto para capturar ações zap nos últimos 7 dias.":::

Os dados desta consulta aparecerão no painel de resultados, abaixo da própria consulta. Os resultados incluem informações como 'DeviceName', 'AccountDisplayName' e 'ZapTime' em um conjunto de resultados personalizável. Os resultados também podem ser exportados para os seus registros. Se você precisar dessa consulta novamente, selecione **Salvar** > **Salvar Como** e adicione a consulta à sua lista de consultas compartilhadas ou consultas da comunidade.

## <a name="related-information"></a>Informações relacionadas
- [Práticas recomendadas de busca avançada](advanced-hunting-best-practices.md)
- [Visão geral - Busca avançada](advanced-hunting-overview.md)
