---
title: Revisar alertas no Microsoft Defender para Ponto de Extremidade
description: Revise as informações de alerta, incluindo um artigo de alerta visualizado e detalhes para cada etapa da cadeia.
keywords: incidentes, incidentes, máquinas, dispositivos, usuários, alertas, alertas, investigação, gráfico, evidência
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b791f2b62cb4a3f8062c80ceeb04ccfa72f704bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052867"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fb1a3-104">Revisar alertas no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="fb1a3-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fb1a3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fb1a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="fb1a3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="fb1a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="fb1a3-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="fb1a3-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fb1a3-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="fb1a3-109">A página de alerta no Microsoft Defender para Ponto de Extremidade fornece contexto completo ao alerta, combinando sinais de ataque e alertas relacionados ao alerta selecionado, para construir um histórico de alerta detalhado.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="fb1a3-110">Triagem rápida, investigação e tomar medidas eficazes em alertas que afetam sua organização.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="fb1a3-111">Entenda por que eles foram disparados e seu impacto de um local.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="fb1a3-112">Saiba mais nesta visão geral.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="fb1a3-113">Como começar com um alerta</span><span class="sxs-lookup"><span data-stu-id="fb1a3-113">Getting started with an alert</span></span>

<span data-ttu-id="fb1a3-114">Selecionar o nome de um alerta no Defender para Ponto de Extremidade o fará parar em sua página de alerta.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="fb1a3-115">Na página de alerta, todas as informações serão mostradas no contexto do alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="fb1a3-116">Cada página de alerta consiste em 4 seções:</span><span class="sxs-lookup"><span data-stu-id="fb1a3-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="fb1a3-117">**O título do alerta** mostra o nome do alerta e está lá para lembrar qual alerta iniciou sua investigação atual, independentemente do que você selecionou na página.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="fb1a3-118">[**Os ativos**](#review-affected-assets) afetados listam cartões de dispositivos e usuários afetados por esse alerta que podem ser clicados para obter mais informações e ações.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="fb1a3-119">O **artigo de alerta** exibe todas as entidades relacionadas ao alerta, interconectadas por uma exibição em árvore.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="fb1a3-120">O alerta no título será aquele em foco quando você chegar pela primeira vez na página do alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="fb1a3-121">As entidades no histórico de alerta são expansíveis e clicáveis, para fornecer informações adicionais e acelerar a resposta, permitindo que você tome ações diretamente no contexto da página de alerta.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="fb1a3-122">Use o artigo de alerta para iniciar sua investigação.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="fb1a3-123">Saiba como em [Investigar alertas no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span><span class="sxs-lookup"><span data-stu-id="fb1a3-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="fb1a3-124">O **painel de detalhes** mostrará os detalhes do alerta selecionado no início, com detalhes e ações relacionadas a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="fb1a3-125">Se você selecionar qualquer um dos ativos ou entidades afetados no histórico de alertas, o painel de detalhes mudará para fornecer informações contextuais e ações para o objeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="fb1a3-126">Observe o status de detecção do alerta.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="fb1a3-127">Impedido – A tentativa de ação suspeita foi evitada.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="fb1a3-128">Por exemplo, um arquivo não foi gravado em disco ou executado.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="fb1a3-129">![Uma página de alerta mostrando ameaça foi impedida](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="fb1a3-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="fb1a3-130">Bloqueado – Comportamento suspeito foi executado e bloqueado.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="fb1a3-131">Por exemplo, um processo foi executado, mas como ele exibiu comportamentos suspeitos posteriormente, o processo foi encerrado.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="fb1a3-132">![Uma página de alerta mostrando ameaça foi bloqueada](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="fb1a3-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="fb1a3-133">Detectado – um ataque foi detectado e possivelmente ainda está ativo.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="fb1a3-134">![Uma página de alerta mostrando ameaça foi detectada](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="fb1a3-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="fb1a3-135">Em seguida, você  também pode revisar os detalhes de investigação automatizados no painel de detalhes do seu alerta, para ver quais ações já foram tomadas, bem como ler a descrição do alerta para ações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![Um trecho do painel de detalhes com a descrição do alerta e as seções de investigação automática realçadas](images/alert-air-and-alert-description.png)

<span data-ttu-id="fb1a3-137">Outras informações disponíveis no painel de detalhes quando o alerta é aberto incluem técnicas MITRE, origem e detalhes contextuais adicionais.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="fb1a3-138">Revisar ativos afetados</span><span class="sxs-lookup"><span data-stu-id="fb1a3-138">Review affected assets</span></span>

<span data-ttu-id="fb1a3-139">Selecionar um dispositivo ou um cartão de usuário nas seções de ativos afetados alterna para os detalhes do dispositivo ou do usuário no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="fb1a3-140">**Para dispositivos,** o painel de detalhes exibirá informações sobre o próprio dispositivo, como Domínio, Sistema Operacional e IP.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="fb1a3-141">Alertas ativos e os usuários conectados nesse dispositivo também estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="fb1a3-142">Você pode executar uma ação imediata isolando o dispositivo, restringindo a execução do aplicativo ou executando uma verificação antivírus.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="fb1a3-143">Como alternativa, você pode coletar um pacote de investigação, iniciar uma investigação automatizada ou ir até a página do dispositivo para investigar do ponto de vista do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![Um trecho do painel de detalhes quando um dispositivo é selecionado](images/device-page-details.png)

- <span data-ttu-id="fb1a3-145">Para **usuários,** o painel de detalhes exibirá informações detalhadas do usuário, como o nome SAM e SID do usuário, bem como os tipos de logon executados por esse usuário e quaisquer alertas e incidentes relacionados a ele.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="fb1a3-146">Você pode selecionar *Abrir página do usuário* para continuar a investigação do ponto de vista desse usuário.</span><span class="sxs-lookup"><span data-stu-id="fb1a3-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![Um trecho do painel de detalhes quando um usuário é selecionado](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="fb1a3-148">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="fb1a3-148">Related topics</span></span>

- [<span data-ttu-id="fb1a3-149">Exibir e organizar a fila de incidentes</span><span class="sxs-lookup"><span data-stu-id="fb1a3-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="fb1a3-150">Investigar incidentes</span><span class="sxs-lookup"><span data-stu-id="fb1a3-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="fb1a3-151">Gerenciar incidentes</span><span class="sxs-lookup"><span data-stu-id="fb1a3-151">Manage incidents</span></span>](manage-incidents.md)
