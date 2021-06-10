---
title: Exemplo de um ataque de email de phishing
description: Passo a passo de uma análise de exemplo de um ataque de phishing.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 41a2c73ce5e1c3060d88572f4fa7afe63e193f46
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299983"
---
# <a name="example-of-a-phishing-email-attack"></a><span data-ttu-id="6a9be-104">Exemplo de um ataque de email de phishing</span><span class="sxs-lookup"><span data-stu-id="6a9be-104">Example of a phishing email attack</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6a9be-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6a9be-105">**Applies to:**</span></span>
- <span data-ttu-id="6a9be-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6a9be-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6a9be-107">Microsoft 365 O Defender pode ajudar a detectar anexos mal-intencionados entregues por email.</span><span class="sxs-lookup"><span data-stu-id="6a9be-107">Microsoft 365 Defender can help detect malicious attachments delivered via email.</span></span> <span data-ttu-id="6a9be-108">Como [](https://protection.office.com/) Office 365 Central de Conformidade e Segurança se integra ao Microsoft 365 Defender, os analistas de segurança podem ter visibilidade sobre as ameaças que vêm do Office 365, como por meio de anexos de email.</span><span class="sxs-lookup"><span data-stu-id="6a9be-108">Since the [Office 365 Security and Compliance Center](https://protection.office.com/) integrates with Microsoft 365 Defender, security analysts can have visibility on threats coming in from Office 365, such as through email attachments.</span></span>

<span data-ttu-id="6a9be-109">Por exemplo, um analista foi atribuído a um incidente de vários estágios.</span><span class="sxs-lookup"><span data-stu-id="6a9be-109">For example, an analyst was assigned a multi-stage incident.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Exemplo de um incidente em vários estágios"::: 

<span data-ttu-id="6a9be-111">Na guia **Alertas** do incidente, os alertas do Defender para Office 365 e Microsoft Cloud App Security são exibidos.</span><span class="sxs-lookup"><span data-stu-id="6a9be-111">In the **Alerts** tab of the incident, alerts from Defender for Office 365 and Microsoft Cloud App Security are displayed.</span></span> <span data-ttu-id="6a9be-112">O analista pode detalhar o Defender para Office 365 alertas selecionando os alertas de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="6a9be-112">The analyst can drill down into the Defender for Office 365 alerts by selecting the email messages alerts.</span></span> <span data-ttu-id="6a9be-113">Os detalhes do alerta são exibidos no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="6a9be-113">The details of the alert are displayed on the side pane.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Exemplo de um alerta de email":::
 
<span data-ttu-id="6a9be-115">Ao rolar para baixo, mais informações são exibidas, mostrando os arquivos mal-intencionados e o usuário afetado.</span><span class="sxs-lookup"><span data-stu-id="6a9be-115">By scrolling down further, more information is displayed, showing the malicious files and user that was impacted.</span></span>

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Exemplo de impacto de usuário e arquivo de um alerta de email":::
  
<span data-ttu-id="6a9be-117">Selecionar **a página Abrir alerta** leva você ao alerta específico onde várias informações podem ser exibidas com mais detalhes selecionando o link.</span><span class="sxs-lookup"><span data-stu-id="6a9be-117">Selecting **Open alert page** takes you to the specific alert where various information can be viewed in greater detail by selecting the link.</span></span> <span data-ttu-id="6a9be-118">A mensagem de email real pode ser exibida selecionando **Exibir mensagens** no Explorer em direção à parte inferior do painel.</span><span class="sxs-lookup"><span data-stu-id="6a9be-118">The actual email message can be viewed by selecting **View messages in Explorer** toward the bottom of the panel.</span></span>
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Exemplo dos detalhes de um alerta"::: 

<span data-ttu-id="6a9be-120">Isso leva o analista para a página Gerenciamento de Ameaças onde o assunto de email, Destinatário, Remetente e outras informações são exibidos.</span><span class="sxs-lookup"><span data-stu-id="6a9be-120">This takes the analyst to the Threat Management page where the email Subject, Recipient, Sender, and other information are displayed.</span></span> <span data-ttu-id="6a9be-121">**O ZAP** **em Ações Especiais** informa ao analista que o recurso de limpeza automática de hora zero foi implementado.</span><span class="sxs-lookup"><span data-stu-id="6a9be-121">**ZAP** under **Special Actions** tells the analyst that the Zero-hour auto purge feature was implemented.</span></span> <span data-ttu-id="6a9be-122">O ZAP detecta e remove automaticamente mensagens mal-intencionadas e de spam de caixas de correio em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="6a9be-122">ZAP automatically detects and removes malicious and spam messages from mailboxes across the organization.</span></span> <span data-ttu-id="6a9be-123">Para obter mais informações, consulte Zap (limpeza automática de hora [zero) no Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span><span class="sxs-lookup"><span data-stu-id="6a9be-123">For more information, see [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).</span></span>

<span data-ttu-id="6a9be-124">Outras ações podem ser tomadas em mensagens específicas selecionando **Ações**.</span><span class="sxs-lookup"><span data-stu-id="6a9be-124">Other actions can be taken on specific messages by selecting **Actions**.</span></span> 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Exemplo das outras ações podem ser tomadas em mensagens de email"::: 

## <a name="next-step"></a><span data-ttu-id="6a9be-126">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6a9be-126">Next step</span></span>

<span data-ttu-id="6a9be-127">Consulte o [caminho de investigação de ataque baseado](first-incident-path-identity.md) em identidade.</span><span class="sxs-lookup"><span data-stu-id="6a9be-127">See the [identity-based attack](first-incident-path-identity.md) investigation path.</span></span>

## <a name="see-also"></a><span data-ttu-id="6a9be-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="6a9be-128">See also</span></span>

- [<span data-ttu-id="6a9be-129">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="6a9be-129">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6a9be-130">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="6a9be-130">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="6a9be-131">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="6a9be-131">Manage incidents</span></span>](manage-incidents.md)
