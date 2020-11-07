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
description: Saiba mais sobre a configuração de segurança por padrão no Exchange Online Protection (EOP)
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945325"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="bec4f-103">Seguro por padrão no Office 365</span><span class="sxs-lookup"><span data-stu-id="bec4f-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bec4f-104">"Seguro por padrão" é um termo usado para definir as configurações padrão mais seguras possível.</span><span class="sxs-lookup"><span data-stu-id="bec4f-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="bec4f-105">No entanto, a segurança precisa ser balanceada com produtividade.</span><span class="sxs-lookup"><span data-stu-id="bec4f-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="bec4f-106">Isso pode incluir o equilíbrio entre:</span><span class="sxs-lookup"><span data-stu-id="bec4f-106">This can include balancing across:</span></span>

- <span data-ttu-id="bec4f-107">Usabilidade: as configurações não devem obter o modo de produtividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="bec4f-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="bec4f-108">Risco: a segurança pode bloquear atividades importantes.</span><span class="sxs-lookup"><span data-stu-id="bec4f-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="bec4f-109">Configurações herdadas: algumas configurações de produtos e recursos antigos podem precisar ser mantidas por motivos comerciais, mesmo se novas configurações modernas forem aprimoradas.</span><span class="sxs-lookup"><span data-stu-id="bec4f-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="bec4f-110">As organizações 365 da Microsoft com caixas de correio no Exchange Online são protegidas pela proteção do Exchange Online (EOP).</span><span class="sxs-lookup"><span data-stu-id="bec4f-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="bec4f-111">Esta proteção inclui:</span><span class="sxs-lookup"><span data-stu-id="bec4f-111">This protection includes:</span></span>

1. <span data-ttu-id="bec4f-112">Email com malware suspeito será automaticamente colocado em quarentena e os destinatários serão notificados.</span><span class="sxs-lookup"><span data-stu-id="bec4f-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="bec4f-113">Consulte [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bec4f-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="bec4f-114">O email de phishing identificado como "alta confiança" será tratado de acordo com a ação da política antispam.</span><span class="sxs-lookup"><span data-stu-id="bec4f-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="bec4f-115">Consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bec4f-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="bec4f-116">Como a Microsoft deseja manter nossos clientes seguros por padrão, alguns locatários substituídos não são aplicados para phishing ou golpe de alta confiança.</span><span class="sxs-lookup"><span data-stu-id="bec4f-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="bec4f-117">Essas substituições incluem:</span><span class="sxs-lookup"><span data-stu-id="bec4f-117">These overrides include:</span></span>

- <span data-ttu-id="bec4f-118">Listas de remetentes permitidos ou listas de domínios permitidos (políticas antispam)</span><span class="sxs-lookup"><span data-stu-id="bec4f-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="bec4f-119">Remetentes confiáveis do Outlook</span><span class="sxs-lookup"><span data-stu-id="bec4f-119">Outlook Safe senders</span></span>
- <span data-ttu-id="bec4f-120">Lista de permissões de IP (filtragem de conexão)</span><span class="sxs-lookup"><span data-stu-id="bec4f-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="bec4f-121">Mais informações sobre essas substituições podem ser encontradas em [criar listas de remetentes seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="bec4f-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="bec4f-122">A segurança por padrão aqui não é uma configuração que possa ser ativada ou desativada, mas o modo como nossa filtragem funciona para manter mensagens potencialmente perigosas ou indesejadas fora de suas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="bec4f-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="bec4f-123">O malware e o Phish de alta confiança devem ser enviados para a quarentena.</span><span class="sxs-lookup"><span data-stu-id="bec4f-123">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="bec4f-124">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware ou phishing de alta confiança e também podem relatar falsos positivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bec4f-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="bec4f-125">Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="bec4f-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="bec4f-126">Exceptions</span><span class="sxs-lookup"><span data-stu-id="bec4f-126">Exceptions</span></span>

<span data-ttu-id="bec4f-127">As substituições que serão ignoradas por todos os filtros incluem:</span><span class="sxs-lookup"><span data-stu-id="bec4f-127">The only overrides that will bypass all filters include:</span></span>

- <span data-ttu-id="bec4f-128">Regras de fluxo de transporte do Exchange (ETR)/mail.</span><span class="sxs-lookup"><span data-stu-id="bec4f-128">Exchange Transport Rules (ETR)/mail flow rules.</span></span> <span data-ttu-id="bec4f-129">Use regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens no EOP.</span><span class="sxs-lookup"><span data-stu-id="bec4f-129">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="bec4f-130">Lista de permissões/bloqueios de locatários: gerenciar URLs e arquivos na lista de permissões/bloqueios de locatários.</span><span class="sxs-lookup"><span data-stu-id="bec4f-130">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="bec4f-131">Esses tipos de substituições são úteis para:</span><span class="sxs-lookup"><span data-stu-id="bec4f-131">These types of overrides are useful for:</span></span>

- <span data-ttu-id="bec4f-132">Simulações de phishing: ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real afete sua organização.</span><span class="sxs-lookup"><span data-stu-id="bec4f-132">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="bec4f-133">Segurança/caixas de correio do SecOps: caixas de correio dedicadas usadas pelo Security Teams para obter mensagens não filtradas (tanto boas quanto ruins).</span><span class="sxs-lookup"><span data-stu-id="bec4f-133">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="bec4f-134">O Microsoft Teams pode então revisar para ver se eles contêm conteúdo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="bec4f-134">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="bec4f-135">Filtros de terceiros: alguns fornecedores terceirizados recomendarão a desativação do EOP (SCL =-1), pois o filtro de terceiros gerenciará a filtragem de email.</span><span class="sxs-lookup"><span data-stu-id="bec4f-135">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="bec4f-136">A Microsoft não recomenda desativar o EOP como EOP é necessário para o defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="bec4f-136">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="bec4f-137">Falsos positivos: Talvez você queira permitir determinadas mensagens que ainda estão sendo analisadas pela Microsoft [por meio de envios de administrador](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="bec4f-137">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="bec4f-138">Assim como ocorre com todas as substituições, é recomendável que elas sejam temporárias.</span><span class="sxs-lookup"><span data-stu-id="bec4f-138">As with all overrides, it is recommended that they are temporary.</span></span>
