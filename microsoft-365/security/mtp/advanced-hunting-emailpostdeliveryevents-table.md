---
title: Tabela EmailPostDeliveryEvents no esquema de busca avançada
description: Saiba mais sobre as ações de envio realizadas nos emails do Microsoft 365 na tabela EmailPostDeliveryEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, EmailPostDeliveryEvents, ID da mensagem de rede, remetente, destinatário, ID de anexo, nome do anexo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: d9d3ffad156d5a27f1931c3b6ec295b022dea296
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198008"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="83719-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="83719-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="83719-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="83719-105">**Applies to:**</span></span>
- <span data-ttu-id="83719-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="83719-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="83719-107">A `EmailPostDeliveryEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as ações de envio realizadas em mensagens de email processadas pelo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83719-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="83719-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="83719-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="83719-109">Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.</span><span class="sxs-lookup"><span data-stu-id="83719-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="83719-110">Para obter mais informações sobre mensagens de email individuais, você também pode usar o [`EmailEvents`](advanced-hunting-emailevents-table.md) , o [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) e as [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabelas.</span><span class="sxs-lookup"><span data-stu-id="83719-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="83719-111">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="83719-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="83719-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="83719-112">Column name</span></span> | <span data-ttu-id="83719-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="83719-113">Data type</span></span> | <span data-ttu-id="83719-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="83719-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="83719-115">datetime</span><span class="sxs-lookup"><span data-stu-id="83719-115">datetime</span></span> | <span data-ttu-id="83719-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="83719-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="83719-117">string</span><span class="sxs-lookup"><span data-stu-id="83719-117">string</span></span> | <span data-ttu-id="83719-118">Identificador exclusivo do evento</span><span class="sxs-lookup"><span data-stu-id="83719-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="83719-119">string</span><span class="sxs-lookup"><span data-stu-id="83719-119">string</span></span> | <span data-ttu-id="83719-120">Identificador exclusivo do email, gerado pelo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83719-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="83719-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="83719-121">string</span></span> | <span data-ttu-id="83719-122">Identificador público do email definido pelo seu sistema de envio</span><span class="sxs-lookup"><span data-stu-id="83719-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="83719-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="83719-123">string</span></span> | <span data-ttu-id="83719-124">Ação tomada na entidade</span><span class="sxs-lookup"><span data-stu-id="83719-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="83719-125">string</span><span class="sxs-lookup"><span data-stu-id="83719-125">string</span></span> | <span data-ttu-id="83719-126">Tipo de atividade que disparou o evento: correção manual, "phishing ZAP, malware ZAP"</span><span class="sxs-lookup"><span data-stu-id="83719-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="83719-127">string</span><span class="sxs-lookup"><span data-stu-id="83719-127">string</span></span> | <span data-ttu-id="83719-128">Indica se uma ação foi disparada por um administrador (manualmente ou por meio da aprovação de uma ação automática pendente) ou por algum mecanismo especial, como uma entrega de ZAP ou dinâmica</span><span class="sxs-lookup"><span data-stu-id="83719-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="83719-129">string</span><span class="sxs-lookup"><span data-stu-id="83719-129">string</span></span> | <span data-ttu-id="83719-130">Resultado da ação</span><span class="sxs-lookup"><span data-stu-id="83719-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="83719-131">string</span><span class="sxs-lookup"><span data-stu-id="83719-131">string</span></span> | <span data-ttu-id="83719-132">Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="83719-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="83719-133">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="83719-133">string</span></span> | <span data-ttu-id="83719-134">Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos</span><span class="sxs-lookup"><span data-stu-id="83719-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="83719-135">Tipos de eventos com suporte</span><span class="sxs-lookup"><span data-stu-id="83719-135">Supported event types</span></span>
<span data-ttu-id="83719-136">Esta tabela captura eventos com os seguintes `ActionType` valores:</span><span class="sxs-lookup"><span data-stu-id="83719-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="83719-137">**Correção manual** – um administrador executou uma ação manualmente em uma mensagem de email após sua entrega à caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="83719-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="83719-138">Isso inclui ações realizadas manualmente por meio do [Explorador de ameaças](../office-365-security/threat-explorer.md) ou aprovações de [ações de investigação e resposta (ar) automatizadas](mtp-autoir-actions.md).</span><span class="sxs-lookup"><span data-stu-id="83719-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="83719-139">**Phish zap** – o [descarte automático de zero horas (zap)](../office-365-security/zero-hour-auto-purge.md) executou uma ação em um email de phishing após a entrega.</span><span class="sxs-lookup"><span data-stu-id="83719-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="83719-140">**Malware zap** – o descarte automático de zero horas (zap) executou uma ação em uma mensagem de email encontrada contendo malware após a entrega.</span><span class="sxs-lookup"><span data-stu-id="83719-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="83719-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="83719-141">Related topics</span></span>
- [<span data-ttu-id="83719-142">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="83719-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="83719-143">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="83719-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="83719-144">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="83719-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="83719-145">Procure em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="83719-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="83719-146">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="83719-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="83719-147">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="83719-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
