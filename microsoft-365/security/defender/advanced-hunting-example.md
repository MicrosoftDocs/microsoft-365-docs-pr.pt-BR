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
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="efb02-104">Exemplo de busca avançada para o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="efb02-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="efb02-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="efb02-105">**Applies to:**</span></span>
- <span data-ttu-id="efb02-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="efb02-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="efb02-107">Deseja começar a procurar ameaças de email usando a busca avançada?</span><span class="sxs-lookup"><span data-stu-id="efb02-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="efb02-108">Tente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="efb02-108">Try this:</span></span>

<span data-ttu-id="efb02-109">A seção [Introdução](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) do [artigo do Microsoft Defender para Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) tem blocos de configuração iniciais lógicos com a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="efb02-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="efb02-110">Configure tudo com 'Anti' no nome.</span><span class="sxs-lookup"><span data-stu-id="efb02-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="efb02-111">Antimalware</span><span class="sxs-lookup"><span data-stu-id="efb02-111">Anti-malware</span></span>
   - <span data-ttu-id="efb02-112">Anti-phishing</span><span class="sxs-lookup"><span data-stu-id="efb02-112">Anti-phishing</span></span>
   - <span data-ttu-id="efb02-113">Antispam</span><span class="sxs-lookup"><span data-stu-id="efb02-113">Anti-spam</span></span>
2. <span data-ttu-id="efb02-114">Configurar tudo com "Cofre" no nome.</span><span class="sxs-lookup"><span data-stu-id="efb02-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="efb02-115">Links seguros</span><span class="sxs-lookup"><span data-stu-id="efb02-115">Safe Links</span></span>
   - <span data-ttu-id="efb02-116">Anexos seguros</span><span class="sxs-lookup"><span data-stu-id="efb02-116">Safe Attachments</span></span>
3. <span data-ttu-id="efb02-117">Defenda as cargas de trabalho (por exemplo,</span><span class="sxs-lookup"><span data-stu-id="efb02-117">Defend the workloads (ex.</span></span> <span data-ttu-id="efb02-118">SharePoint Online, OneDrive e Teams).</span><span class="sxs-lookup"><span data-stu-id="efb02-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="efb02-119">Proteja com limpeza automática zero hora.</span><span class="sxs-lookup"><span data-stu-id="efb02-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="efb02-120">Junto com um [link](../office-365-security/protect-against-threats.md) para começar imediatamente a configuração no 1º Dia.</span><span class="sxs-lookup"><span data-stu-id="efb02-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="efb02-121">A última etapa na **Introdução** é proteger os usuários com a **Limpeza Automática Zero Hora**, também conhecida como ZAP.</span><span class="sxs-lookup"><span data-stu-id="efb02-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="efb02-122">Saber se seus esforços para limpar um email suspeito ou mal-intencionado após a entrega foram bem-sucedidos pode ser muito importantes.</span><span class="sxs-lookup"><span data-stu-id="efb02-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="efb02-123">Navegar rapidamente para a linguagem de consulta Kusto para buscar problemas é uma das vantagens de converter esses dois centros de segurança.</span><span class="sxs-lookup"><span data-stu-id="efb02-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="efb02-124">As equipes de segurança podem monitorar as faltas do ZAP, dando suas próximas etapas [aqui](https://security.microsoft.com/advanced-hunting), em **Hunting** \> **Advanced Hunting**.</span><span class="sxs-lookup"><span data-stu-id="efb02-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="efb02-125">Na página Busca Avançada, clique **em Consulta**.</span><span class="sxs-lookup"><span data-stu-id="efb02-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="efb02-126">Copie a consulta a seguir na janela de consultas.</span><span class="sxs-lookup"><span data-stu-id="efb02-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="efb02-127">Selecione **Executar consulta**.</span><span class="sxs-lookup"><span data-stu-id="efb02-127">Select **Run query**.</span></span>

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

<span data-ttu-id="efb02-129">Os dados desta consulta aparecerão no painel de resultados, abaixo da própria consulta.</span><span class="sxs-lookup"><span data-stu-id="efb02-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="efb02-130">Os resultados incluem informações como 'DeviceName', 'AccountDisplayName' e 'ZapTime' em um conjunto de resultados personalizável.</span><span class="sxs-lookup"><span data-stu-id="efb02-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="efb02-131">Os resultados também podem ser exportados para os seus registros.</span><span class="sxs-lookup"><span data-stu-id="efb02-131">Results can also be exported for your records.</span></span> <span data-ttu-id="efb02-132">Se você precisar dessa consulta novamente, selecione **Salvar** > **Salvar Como** e adicione a consulta à sua lista de consultas compartilhadas ou consultas da comunidade.</span><span class="sxs-lookup"><span data-stu-id="efb02-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="efb02-133">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="efb02-133">Related information</span></span>
- [<span data-ttu-id="efb02-134">Práticas recomendadas de busca avançada</span><span class="sxs-lookup"><span data-stu-id="efb02-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="efb02-135">Visão geral - Busca avançada</span><span class="sxs-lookup"><span data-stu-id="efb02-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
