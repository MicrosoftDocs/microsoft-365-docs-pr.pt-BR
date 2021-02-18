---
title: Resposta a incidentes de segurança
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Esta solução informa qual pode ser a aparência dos ataques de segurança cibernética mais comuns no Microsoft 365 e como responder a eles
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d37fb232b717485c40218fd8a3c3117ba9b8322b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287636"
---
# <a name="security-incident-response"></a><span data-ttu-id="a2b8b-103">Resposta a incidentes de segurança</span><span class="sxs-lookup"><span data-stu-id="a2b8b-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a2b8b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a2b8b-104">**Applies to**</span></span>
- [<span data-ttu-id="a2b8b-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a2b8b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a2b8b-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a2b8b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a2b8b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2b8b-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="a2b8b-108">**Resumo:** Esta solução informa quais são os indicadores para os ataques mais comuns de segurança cibernética no Office 365, como confirmar positivamente qualquer ataque determinado e como responder a ele.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="a2b8b-109">Saiba como responder a ataques cibernéticos</span><span class="sxs-lookup"><span data-stu-id="a2b8b-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="a2b8b-110">Nem todos os ataques cibernéticos podem ser impedidas.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="a2b8b-111">Os invasores estão constantemente procurando novos pontos fracos em sua estratégia estratégica ou estão explorando as antigas.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="a2b8b-112">Saber como reconhecer um ataque permite que você responda a ele mais rapidamente, o que reduz a duração do incidente de segurança.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="a2b8b-113">Esta série de artigos ajuda você a entender a aparência de um determinado tipo de ataque no Microsoft 365 e fornece as etapas que você pode seguir para responder.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="a2b8b-114">Eles são pontos de entrada rápidos para entender:</span><span class="sxs-lookup"><span data-stu-id="a2b8b-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="a2b8b-115">O que é o ataque e como ele funciona.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="a2b8b-116">Sinais, chamados de indicadores de comprometimento (IOC), para procurar e como procurar por eles.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="a2b8b-117">Como confirmar positivamente o ataque.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="a2b8b-118">Etapas a serem tomadas para cortar o ataque e proteger melhor sua organização no futuro.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="a2b8b-119">Links para informações detalhadas sobre cada tipo de ataque.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="a2b8b-120">Verifique aqui mensalmente, pois mais artigos serão adicionados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="a2b8b-121">Detectar e remediar artigos</span><span class="sxs-lookup"><span data-stu-id="a2b8b-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="a2b8b-122">Detectar e corrigir a concessão de autorização ilícita no Office 365</span><span class="sxs-lookup"><span data-stu-id="a2b8b-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="a2b8b-123">Detectar e Corrigir Ataques de Injeção a Regras do Outlook e Formulários Personalizados no Office 365</span><span class="sxs-lookup"><span data-stu-id="a2b8b-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="a2b8b-124">Artigos de resposta a incidentes</span><span class="sxs-lookup"><span data-stu-id="a2b8b-124">Incident response articles</span></span>

- [<span data-ttu-id="a2b8b-125">Responder a uma Conta de Email Comprometida no Office 365</span><span class="sxs-lookup"><span data-stu-id="a2b8b-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="a2b8b-126">Proteja o Microsoft 365 como um profissional de segurança cibernética</span><span class="sxs-lookup"><span data-stu-id="a2b8b-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="a2b8b-127">Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="a2b8b-128">Use o roteiro de segurança do Microsoft 365 – principais prioridades para os primeiros [30 dias, 90](security-roadmap.md) dias e depois de implementar as práticas recomendadas pela Microsoft para proteger sua organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="a2b8b-129">Tarefas a realizar nos primeiros 30 dias.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="a2b8b-130">Estas têm efeito imediato e baixo impacto para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="a2b8b-131">Tarefas para realizar em 90 dias.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="a2b8b-132">Eles levam um pouco mais de tempo para planejar e implementar, mas melhoram muito a postura de segurança</span><span class="sxs-lookup"><span data-stu-id="a2b8b-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="a2b8b-133">Além de 90 dias.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-133">Beyond 90 days.</span></span> <span data-ttu-id="a2b8b-134">Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a2b8b-134">These enhancements build in your first 90 days work.</span></span>
