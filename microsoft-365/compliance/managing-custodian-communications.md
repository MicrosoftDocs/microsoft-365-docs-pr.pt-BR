---
title: Trabalhar com comunicações em Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery facilita o gerenciamento do fluxo de trabalho de notificação de espera legal em torno da notificação de custodiantes em investigações legais.
ms.openlocfilehash: 28b719a83cbc1608ad5468e401a8b7946cb8da5f
ms.sourcegitcommit: bd51f626f0c7788c2a3cf89deee25264659aebd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "43551233"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a><span data-ttu-id="f0098-103">Trabalhar com comunicações em Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="f0098-103">Work with communications in Advanced eDiscovery</span></span>

<span data-ttu-id="f0098-104">Advanced eDiscovery permite que os departamentos jurídicos simplifiquem seus processos em torno do controle e distribuição de notificações de responsabilidade legal.</span><span class="sxs-lookup"><span data-stu-id="f0098-104">Advanced eDiscovery allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="f0098-105">A ferramenta de comunicações de custodiante permite que os departamentos jurídicos gerenciem e automatizem todo o processo de responsabilidade legal, desde notificações iniciais, até lembretes e escalonamentos, tudo em um único local.</span><span class="sxs-lookup"><span data-stu-id="f0098-105">The custodian communications tool enables legal departments to manage and automate the entire legal hold process, from initial notifications, to reminders, and to escalations, all in one location.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="f0098-106">O que é uma notificação de espera legal?</span><span class="sxs-lookup"><span data-stu-id="f0098-106">What is a legal hold notification?</span></span>

<span data-ttu-id="f0098-107">Uma notificação de ressarção legal (também conhecida como ressarção *de* litígio) é uma notificação enviada do departamento jurídico de uma organização para funcionários, funcionários contingentes ou custodiantes de dados que podem ser relevantes para uma investigação legal.</span><span class="sxs-lookup"><span data-stu-id="f0098-107">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or custodians of data that may be relevant to a legal investigation.</span></span> <span data-ttu-id="f0098-108">Essas notificações instruim os custodiantes a preservarem informações armazenadas eletronicamente, bem como qualquer conteúdo que possa ser relevante para uma questão jurídica ativa ou iminente.</span><span class="sxs-lookup"><span data-stu-id="f0098-108">These notifications instruct custodians to preserve electronically stored information as well as any content that may be relevant to an active or impending legal matter.</span></span> <span data-ttu-id="f0098-109">As equipes jurídicas devem saber que cada custodiante recebeu, leu, compreendeu e aceitou cumprir as instruções fornecidas.</span><span class="sxs-lookup"><span data-stu-id="f0098-109">Legal teams must know that each custodian has received, read, understood, and has agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="f0098-110">O processo de notificação de hold legal</span><span class="sxs-lookup"><span data-stu-id="f0098-110">The legal hold notification process</span></span>

<span data-ttu-id="f0098-111">Uma organização tem o dever de preservar informações relevantes quando aprende sobre um litígio ou investigação regulatória pendente.</span><span class="sxs-lookup"><span data-stu-id="f0098-111">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="f0098-112">Para atender aos requisitos de preservação de uma investigação, a organização deve informar imediatamente os possíveis custodiantes sobre seu dever de preservar informações relevantes.</span><span class="sxs-lookup"><span data-stu-id="f0098-112">To comply with the preservation requirements of an investigation, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span>

<span data-ttu-id="f0098-113">Com Advanced eDiscovery, as equipes legais podem criar e personalizar seu fluxo de trabalho de notificação de responsabilidade legal.</span><span class="sxs-lookup"><span data-stu-id="f0098-113">With Advanced eDiscovery, legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="f0098-114">A ferramenta de comunicações custodiada permite que as equipes legais configurem os seguintes avisos e fluxos de trabalho:</span><span class="sxs-lookup"><span data-stu-id="f0098-114">The custodian communications tool lets legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="f0098-115">**Aviso de emissão:** Um aviso de missão legal é emitido (ou iniciado) por uma notificação do departamento jurídico aos custodiantes que podem ter informações relevantes sobre o caso.</span><span class="sxs-lookup"><span data-stu-id="f0098-115">**Issuance notice:** A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who may have relevant information about the case matter.</span></span> <span data-ttu-id="f0098-116">Este aviso instrui os guardiões a preservarem todas as informações que possam ser necessárias para descoberta.</span><span class="sxs-lookup"><span data-stu-id="f0098-116">This notice instructs the custodians to preserve any information that may be needed for discovery.</span></span>

2. <span data-ttu-id="f0098-117">**Aviso de reemissão:** Durante um caso, os custodiantes podem ser necessários para preservar conteúdo adicional (ou menos conteúdo) do que foi solicitado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f0098-117">**Re-Issuance notice:** During a case, custodians may be required to preserve additional content (or less content) than was previously requested.</span></span> <span data-ttu-id="f0098-118">Para esse cenário, você pode atualizar o aviso de espera existente e reemissão para os custodiantes.</span><span class="sxs-lookup"><span data-stu-id="f0098-118">For this scenario, you can update the existing hold notice and re-issue it to custodians.</span></span>

3. <span data-ttu-id="f0098-119">**Aviso de lançamento:** Quando um assunto é resolvido e o custodiante não está mais sujeito a um requisito de preservação, o custodiante pode ser liberado do caso.</span><span class="sxs-lookup"><span data-stu-id="f0098-119">**Release notice:** Once a matter is resolved and the custodian is no longer subject to a preservation requirement, the custodian can be released from the case.</span></span> <span data-ttu-id="f0098-120">Além disso, você pode notificar o custodiante de que eles não são mais necessários para preservar o conteúdo e fornecer instruções sobre como retomar suas atividades de trabalho normais em relação aos dados.</span><span class="sxs-lookup"><span data-stu-id="f0098-120">Additionally, you can notify the custodian that they are no longer required to preserve content, and provide instructions about how to resume their normal work activity with regard to their data.</span></span>

4. <span data-ttu-id="f0098-121">**Lembretes e escalonamentos:** Em alguns casos, apenas a emissão de um aviso não é suficiente para atender aos requisitos de descoberta legal.</span><span class="sxs-lookup"><span data-stu-id="f0098-121">**Reminders and escalations:** In some instances, just issuing a notice isn't enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="f0098-122">A cada notificação, as equipes jurídicas podem agendar um conjunto de fluxos de trabalho de lembretes e escalonamento para acompanhar automaticamente com guardiões não responsivas.</span><span class="sxs-lookup"><span data-stu-id="f0098-122">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow up with unresponsive custodians.</span></span>

   - <span data-ttu-id="f0098-123">**Lembretes:** Depois que um aviso de espera legal for emitido ou re-emitido para um conjunto de custodiantes, uma organização pode configurar lembretes para alertar os custodiantes não responsivos.</span><span class="sxs-lookup"><span data-stu-id="f0098-123">**Reminders:** After a legal hold notice has been issued or re-issued to a set of custodians, an organization can set up reminders to alert unresponsive custodians.</span></span>

   - <span data-ttu-id="f0098-124">**Escalações:** Em alguns casos, se um custodiante permanecer sem resposta mesmo após um conjunto de lembretes por um período de tempo, a equipe jurídica pode configurar um fluxo de trabalho de escalonamento para notificar os custodiantes não responsivos e seu gerente.</span><span class="sxs-lookup"><span data-stu-id="f0098-124">**Escalations:** In some cases, if a custodian remains unresponsive even after a set of reminders over a period of time, the legal team can set up an escalation workflow to notify unresponsive custodians and their manager.</span></span>

<span data-ttu-id="f0098-125">Para obter mais informações sobre como gerenciar o processo de comunicação do custodiante, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f0098-125">For more information about managing the custodian communication process, see the following:</span></span> 

- [<span data-ttu-id="f0098-126">Criar um aviso de espera legal</span><span class="sxs-lookup"><span data-stu-id="f0098-126">Create a legal hold notice</span></span>](create-hold-notification.md)

- [<span data-ttu-id="f0098-127">Usar o editor de comunicações</span><span class="sxs-lookup"><span data-stu-id="f0098-127">Use the communications editor</span></span>](using-communications-editor.md)

- [<span data-ttu-id="f0098-128">Gerenciar as notificações de retenção</span><span class="sxs-lookup"><span data-stu-id="f0098-128">Manage hold notifications</span></span>](manage-hold-notification.md)

- [<span data-ttu-id="f0098-129">Confirmar uma notificação de retenção</span><span class="sxs-lookup"><span data-stu-id="f0098-129">Acknowledge a hold notification</span></span>](acknowledge-hold-notification.md)