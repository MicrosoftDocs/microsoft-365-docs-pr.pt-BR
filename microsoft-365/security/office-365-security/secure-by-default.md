---
title: Seguro por padrão no Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Saiba mais sobre a configuração segura por padrão no Exchange Online Protection (EOP)
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f1b495a9c985077dfc88d1da7a221bb60ca10df9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203042"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="a63fc-103">Seguro por padrão no Office 365</span><span class="sxs-lookup"><span data-stu-id="a63fc-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a63fc-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a63fc-104">**Applies to**</span></span>
- [<span data-ttu-id="a63fc-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a63fc-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a63fc-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a63fc-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a63fc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a63fc-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a63fc-108">"Seguro por padrão" é um termo usado para definir as configurações padrão mais seguras possíveis.</span><span class="sxs-lookup"><span data-stu-id="a63fc-108">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="a63fc-109">No entanto, a segurança precisa ser equilibrada com a produtividade.</span><span class="sxs-lookup"><span data-stu-id="a63fc-109">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="a63fc-110">Isso pode incluir o balanceamento entre:</span><span class="sxs-lookup"><span data-stu-id="a63fc-110">This can include balancing across:</span></span>

- <span data-ttu-id="a63fc-111">**Usabilidade**: as configurações não devem ficar no caminho da produtividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="a63fc-111">**Usability**: Settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="a63fc-112">**Risco**: a segurança pode bloquear atividades importantes.</span><span class="sxs-lookup"><span data-stu-id="a63fc-112">**Risk**: Security might block important activities.</span></span>
- <span data-ttu-id="a63fc-113">**Configurações herdadas**: Algumas configurações para produtos e recursos mais antigos podem precisar ser mantidas por motivos comerciais, mesmo que novas configurações modernas sejam aprimoradas.</span><span class="sxs-lookup"><span data-stu-id="a63fc-113">**Legacy settings**: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="a63fc-114">As organizações do Microsoft 365 com caixas de correio no Exchange Online são protegidas pela Proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="a63fc-114">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a63fc-115">Essa proteção inclui:</span><span class="sxs-lookup"><span data-stu-id="a63fc-115">This protection includes:</span></span>

- <span data-ttu-id="a63fc-116">Email com malware suspeito será automaticamente colocado em quarentena e os destinatários serão notificados.</span><span class="sxs-lookup"><span data-stu-id="a63fc-116">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="a63fc-117">Consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a63fc-117">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
- <span data-ttu-id="a63fc-118">Os emails identificados como phishing de alta confiança serão manipulados de acordo com a ação de política anti-spam.</span><span class="sxs-lookup"><span data-stu-id="a63fc-118">Email identified as high confidence phishing will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="a63fc-119">Consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a63fc-119">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a63fc-120">Para obter mais informações sobre o EOP, consulte [Visão geral da Proteção do Exchange Online.](exchange-online-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a63fc-120">For more information about EOP, see [Exchange Online Protection overview](exchange-online-protection-overview.md).</span></span>

<span data-ttu-id="a63fc-121">Como a Microsoft deseja manter nossos clientes seguros por padrão, algumas substituições de locatários não são aplicadas a malware ou phishing de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="a63fc-121">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="a63fc-122">Essas substituições incluem:</span><span class="sxs-lookup"><span data-stu-id="a63fc-122">These overrides include:</span></span>

- <span data-ttu-id="a63fc-123">Listas de remetentes permitidas ou listas de domínio permitidos (políticas anti-spam)</span><span class="sxs-lookup"><span data-stu-id="a63fc-123">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="a63fc-124">Senders seguros do Outlook</span><span class="sxs-lookup"><span data-stu-id="a63fc-124">Outlook Safe Senders</span></span>
- <span data-ttu-id="a63fc-125">Lista de IDS (filtragem de conexão)</span><span class="sxs-lookup"><span data-stu-id="a63fc-125">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="a63fc-126">Mais informações sobre essas substituições podem ser encontradas em [Criar listas de remetentes seguros.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a63fc-126">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a63fc-127">Estamos no processo de preterindo  a ação Mover mensagem para Lixo Eletrônico para um veredito de email de **phishing** de alta confiança em políticas anti-spam do EOP.</span><span class="sxs-lookup"><span data-stu-id="a63fc-127">We're in the process of deprecating the **Move message to Junk Email folder** action for a **High confidence phishing email** verdict in EOP anti-spam policies.</span></span> <span data-ttu-id="a63fc-128">Políticas anti-spam que usam essa ação para mensagens de phishing de alta confiança serão convertidas em **mensagem de quarentena**.</span><span class="sxs-lookup"><span data-stu-id="a63fc-128">Anti-spam policies that use this action for high confidence phishing messages will be converted to **Quarantine message**.</span></span> <span data-ttu-id="a63fc-129">A **ação Redirecionar mensagem para endereço de email** para mensagens de phishing de alta confiança não é afetada.</span><span class="sxs-lookup"><span data-stu-id="a63fc-129">The **Redirect message to email address** action for high confidence phishing messages is unaffected.</span></span>

<span data-ttu-id="a63fc-130">A segurança por padrão não é uma configuração que pode ser ativas ou desligadas, mas é a maneira como nossa filtragem funciona fora da caixa para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="a63fc-130">Secure by default is not a setting that can be turned on or off, but is the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="a63fc-131">As mensagens de malware e phishing de alta confiança devem ser colocadas em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a63fc-131">Malware and high confidence phishing messages should be quarantined.</span></span> <span data-ttu-id="a63fc-132">Somente os administradores podem gerenciar mensagens que estão em quarentena como malware ou phishing de alta confiança e também podem relatar falsos positivos para a Microsoft a partir daí.</span><span class="sxs-lookup"><span data-stu-id="a63fc-132">Only admins can manage messages that are quarantined as malware or high confidence phishing, and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="a63fc-133">Para obter mais informações, consulte [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="a63fc-133">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="more-on-why-were-doing-this"></a><span data-ttu-id="a63fc-134">Mais informações sobre o motivo pelo qual estamos fazendo isso</span><span class="sxs-lookup"><span data-stu-id="a63fc-134">More on why we're doing this</span></span>

<span data-ttu-id="a63fc-135">O espírito de estar seguro por padrão é: estamos tomando a mesma ação na mensagem que você tomaria se você sabia que a mensagem era mal-intencionada, mesmo quando uma exceção configurada permitia que a mensagem fosse entregue.</span><span class="sxs-lookup"><span data-stu-id="a63fc-135">The spirit of being secure by default is: we're taking the same action on the message that you would take if you knew the message malicious, even when a configured exception would otherwise allow the message to be delivered.</span></span> <span data-ttu-id="a63fc-136">Essa é a mesma abordagem que sempre fizemos em malware e agora estamos estendendo esse mesmo comportamento para mensagens de phishing de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="a63fc-136">This is the same approach that we've always used on malware, and now we're extending this same behavior to high confidence phishing messages.</span></span>

<span data-ttu-id="a63fc-137">Nossos dados indicam que um usuário tem 30 vezes mais probabilidade de clicar em um link mal-intencionado em mensagens na pasta Lixo Eletrônico versus Quarentena.</span><span class="sxs-lookup"><span data-stu-id="a63fc-137">Our data indicates that a user is 30 times more likely to click a malicious link in messages in the Junk Email folder versus Quarantine.</span></span> <span data-ttu-id="a63fc-138">Nossos dados também indicam que a taxa de falsos positivos (boas mensagens marcadas como ruins) para mensagens de phishing de alta confiança é muito baixa, e os administradores podem resolver falsos positivos com envios de administrador.</span><span class="sxs-lookup"><span data-stu-id="a63fc-138">Our data also indicates that the false positive rate (good messages marked as bad) for high confidence phishing messages is very low, and admins can resolve any false positives with admin submissions.</span></span>

<span data-ttu-id="a63fc-139">Também determinamos que os remetentes permitidos e listas de domínio permitidos em políticas anti-spam e Remetentes Seguros no Outlook eram muito amplos e estavam causando mais danos do que bons.</span><span class="sxs-lookup"><span data-stu-id="a63fc-139">We also determined that the allowed sender and allowed domain lists in anti-spam policies and Safe Senders in Outlook were too broad and were causing more harm than good.</span></span>

<span data-ttu-id="a63fc-140">Para colocá-lo de outra maneira: como um serviço de segurança, estamos agindo em seu nome para impedir que seus usuários seja comprometidos.</span><span class="sxs-lookup"><span data-stu-id="a63fc-140">To put it another way: as a security service, we're acting on your behalf to prevent your users from being compromised.</span></span> 

## <a name="exceptions"></a><span data-ttu-id="a63fc-141">Exceptions</span><span class="sxs-lookup"><span data-stu-id="a63fc-141">Exceptions</span></span>

<span data-ttu-id="a63fc-142">A única substituição que permite que a mensagem de phishing de alta confiança ignore a filtragem são as regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="a63fc-142">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a63fc-143">Para usar regras de fluxo de emails para ignorar a filtragem, consulte [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a63fc-143">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="a63fc-144">Você só deve considerar o uso de substituições nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="a63fc-144">You should only consider using overrides in the following scenarios:</span></span>

- <span data-ttu-id="a63fc-145">Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes de um ataque real afetar sua organização.</span><span class="sxs-lookup"><span data-stu-id="a63fc-145">Phishing simulations: Simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="a63fc-146">Caixas de correio de Segurança/SecOps: caixas de correio dedicadas usadas pelas equipes de segurança para receber mensagens não filtradas (boas e ruins).</span><span class="sxs-lookup"><span data-stu-id="a63fc-146">Security/SecOps mailboxes: Dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="a63fc-147">Em seguida, o Teams pode revisar para ver se eles contêm conteúdo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="a63fc-147">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="a63fc-148">Filtros de terceiros: Seguro por padrão não se aplica quando o registro MX do domínio não aponta para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="a63fc-148">Third-party filters: Secure by default does not apply when the domain's MX record does not point to Office 365.</span></span>
- <span data-ttu-id="a63fc-149">Falsos positivos: talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft [por meio de envios de administrador.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a63fc-149">False positives: You might want to temporarily allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="a63fc-150">Como com todas as substituições, é recomendável que sejam temporárias.</span><span class="sxs-lookup"><span data-stu-id="a63fc-150">As with all overrides, it is recommended that they are temporary.</span></span>
