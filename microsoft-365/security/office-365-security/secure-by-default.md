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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Saiba como localizar e usar relatórios de segurança de email da sua organização. Relatórios de segurança de email estão disponíveis no centro de conformidade e segurança &.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944408"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="585e1-104">Seguro por padrão no Office 365</span><span class="sxs-lookup"><span data-stu-id="585e1-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="585e1-105">"Seguro por padrão" é um termo usado para definir as configurações padrão mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="585e1-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="585e1-106">No entanto, a segurança precisa ser balanceada com produtividade.</span><span class="sxs-lookup"><span data-stu-id="585e1-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="585e1-107">Isso pode incluir o equilíbrio entre:</span><span class="sxs-lookup"><span data-stu-id="585e1-107">This can include balancing across:</span></span>
- <span data-ttu-id="585e1-108">Usabilidade: as configurações não devem obter o modo de produtividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="585e1-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="585e1-109">Risco: a segurança pode bloquear atividades importantes.</span><span class="sxs-lookup"><span data-stu-id="585e1-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="585e1-110">Configurações herdadas: algumas configurações de produtos e recursos antigos podem precisar ser mantidas por motivos comerciais, mesmo se novas configurações modernas forem aprimoradas.</span><span class="sxs-lookup"><span data-stu-id="585e1-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="585e1-111">As organizações 365 da Microsoft com caixas de correio no Exchange Online são protegidas pela proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="585e1-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="585e1-112">Esta proteção inclui:</span><span class="sxs-lookup"><span data-stu-id="585e1-112">This  protection includes:</span></span>
1. <span data-ttu-id="585e1-113">Email com malware suspeito será automaticamente colocado em quarentena e os destinatários serão notificados.</span><span class="sxs-lookup"><span data-stu-id="585e1-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="585e1-114">Consulte [Configure anti-malware Policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="585e1-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="585e1-115">O email de phishing identificado como "alta confiança" será tratado de acordo com a ação da política antispam.</span><span class="sxs-lookup"><span data-stu-id="585e1-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="585e1-116">Consulte [Configure anti-spam Policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="585e1-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="585e1-117">Como a Microsoft deseja manter nossos clientes seguros por padrão, alguns locatários substituídos não são aplicados para phishing ou golpe de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="585e1-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="585e1-118">Essas substituições incluem:</span><span class="sxs-lookup"><span data-stu-id="585e1-118">These overrides include:</span></span>
- <span data-ttu-id="585e1-119">Listas de remetentes permitidos ou listas de domínios permitidos (políticas antispam)</span><span class="sxs-lookup"><span data-stu-id="585e1-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="585e1-120">Remetentes confiáveis do Outlook</span><span class="sxs-lookup"><span data-stu-id="585e1-120">Outlook Safe senders</span></span>
- <span data-ttu-id="585e1-121">Lista de permissões de IP (filtragem de conexão)</span><span class="sxs-lookup"><span data-stu-id="585e1-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="585e1-122">Mais informações sobre essas substituições podem ser encontradas em [criar listas de remetentes seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="585e1-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="585e1-123">A segurança por padrão aqui não é uma configuração que possa ser ativada ou desativada, mas o modo como nossa filtragem funciona para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="585e1-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="585e1-124">O malware e o Phish de alta confiança devem ser enviados para a quarentena.</span><span class="sxs-lookup"><span data-stu-id="585e1-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="585e1-125">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware ou phishing de alta confiança e também podem relatar falsos positivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="585e1-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="585e1-126">Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="585e1-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="585e1-127">Exceptions</span><span class="sxs-lookup"><span data-stu-id="585e1-127">Exceptions</span></span>
<span data-ttu-id="585e1-128">As substituições que serão ignoradas por todos os filtros incluem:</span><span class="sxs-lookup"><span data-stu-id="585e1-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="585e1-129">Regras de fluxo de transporte do Exchange (ETR)/mail.</span><span class="sxs-lookup"><span data-stu-id="585e1-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="585e1-130">Use regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens no EOP.</span><span class="sxs-lookup"><span data-stu-id="585e1-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="585e1-131">Lista de permissões/bloqueios de locatários: gerenciar URLs e arquivos na lista de permissões/bloqueios de locatários.</span><span class="sxs-lookup"><span data-stu-id="585e1-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="585e1-132">Esses tipos de substituições são úteis para:</span><span class="sxs-lookup"><span data-stu-id="585e1-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="585e1-133">Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real afete sua organização.</span><span class="sxs-lookup"><span data-stu-id="585e1-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="585e1-134">Segurança/caixas de correio do SecOps: caixas de correio dedicadas usadas pelo Security Teams para obter mensagens não filtradas (tanto boas quanto ruins).</span><span class="sxs-lookup"><span data-stu-id="585e1-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="585e1-135">O Microsoft Teams pode então revisar para ver se eles contêm conteúdo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="585e1-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="585e1-136">Filtros de terceiros: alguns fornecedores terceirizados recomendarão a desativação do EOP (SCL =-1), pois o filtro de terceiros gerenciará a filtragem de email.</span><span class="sxs-lookup"><span data-stu-id="585e1-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="585e1-137">A Microsoft não recomenda desativar o EOP como EOP é necessário para o defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="585e1-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="585e1-138">Falsos positivos: Talvez você queira permitir determinadas mensagens que ainda estão sendo analisadas pela Microsoft [por meio de envios de administrador](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="585e1-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="585e1-139">Assim como ocorre com todas as substituições, é recomendável que elas sejam temporárias.</span><span class="sxs-lookup"><span data-stu-id="585e1-139">As with all overrides, it is recommended that they are temporary.</span></span>
