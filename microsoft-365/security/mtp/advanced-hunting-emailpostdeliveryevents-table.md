---
title: Tabela EmailPostDeliveryEvents no esquema de busca avançado
description: Saiba mais sobre ações pós-entrega realizadas em emails do Microsoft 365 na tabela EmailPostDeliveryEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailPostDeliveryEvents, id de mensagem de rede, remetente, destinatário, id de anexo, nome do anexo, veredito de malware, veredito de phishing, contagem de anexos, contagem de links, contagem de url
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6e12ddfc402f1bd420f57369cc6d54f2e670d710
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712373"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="2744b-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="2744b-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2744b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2744b-105">**Applies to:**</span></span>
- <span data-ttu-id="2744b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2744b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2744b-107">A tabela no esquema de busca avançado contém informações sobre ações pós-entrega realizadas em mensagens de email processadas `EmailPostDeliveryEvents` pelo Microsoft [](advanced-hunting-overview.md) 365.</span><span class="sxs-lookup"><span data-stu-id="2744b-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="2744b-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="2744b-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="2744b-109">Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.</span><span class="sxs-lookup"><span data-stu-id="2744b-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="2744b-110">Para obter mais informações sobre mensagens de email individuais, você também pode usar [`EmailEvents`](advanced-hunting-emailevents-table.md) o , e as [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabelas.</span><span class="sxs-lookup"><span data-stu-id="2744b-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="2744b-111">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="2744b-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2744b-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="2744b-112">Column name</span></span> | <span data-ttu-id="2744b-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="2744b-113">Data type</span></span> | <span data-ttu-id="2744b-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="2744b-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2744b-115">datetime</span><span class="sxs-lookup"><span data-stu-id="2744b-115">datetime</span></span> | <span data-ttu-id="2744b-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="2744b-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="2744b-117">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-117">string</span></span> | <span data-ttu-id="2744b-118">Identificador exclusivo do email, gerado pelo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2744b-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="2744b-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-119">string</span></span> | <span data-ttu-id="2744b-120">Identificador público do email definido pelo seu sistema de envio</span><span class="sxs-lookup"><span data-stu-id="2744b-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="2744b-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-121">string</span></span> | <span data-ttu-id="2744b-122">Ação realizada na entidade</span><span class="sxs-lookup"><span data-stu-id="2744b-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="2744b-123">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-123">string</span></span> | <span data-ttu-id="2744b-124">Tipo de atividade que disparou o evento: Correção manual, PHISH ZAP, MALWARE ZAP</span><span class="sxs-lookup"><span data-stu-id="2744b-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="2744b-125">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-125">string</span></span> | <span data-ttu-id="2744b-126">Indica se uma ação foi disparada por um administrador (manualmente ou por meio da aprovação de uma ação automatizada pendente) ou por algum mecanismo especial, como um ZAP ou Entrega Dinâmica</span><span class="sxs-lookup"><span data-stu-id="2744b-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="2744b-127">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-127">string</span></span> | <span data-ttu-id="2744b-128">Resultado da ação</span><span class="sxs-lookup"><span data-stu-id="2744b-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="2744b-129">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-129">string</span></span> | <span data-ttu-id="2744b-130">Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="2744b-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="2744b-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="2744b-131">string</span></span> | <span data-ttu-id="2744b-132">Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos</span><span class="sxs-lookup"><span data-stu-id="2744b-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="2744b-133">long</span><span class="sxs-lookup"><span data-stu-id="2744b-133">long</span></span> | <span data-ttu-id="2744b-134">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="2744b-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="2744b-135">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="2744b-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="2744b-136">Tipos de eventos com suporte</span><span class="sxs-lookup"><span data-stu-id="2744b-136">Supported event types</span></span>
<span data-ttu-id="2744b-137">Esta tabela captura eventos com os seguintes `ActionType` valores:</span><span class="sxs-lookup"><span data-stu-id="2744b-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="2744b-138">**Correção manual** – Um administrador tomou medidas manualmente em uma mensagem de email depois que ela foi entregue à caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="2744b-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="2744b-139">Isso inclui ações realizadas manualmente por meio do [Explorador](../office-365-security/threat-explorer.md) de Ameaças ou aprovações de ações automatizadas de investigação e resposta [(AIR).](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="2744b-139">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="2744b-140">**Phish ZAP** – [O ZAP (limpeza automática](../office-365-security/zero-hour-auto-purge.md) de hora zero) entrou em ação em um email de phishing após a entrega.</span><span class="sxs-lookup"><span data-stu-id="2744b-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="2744b-141">**MALWARE ZAP** – O ZAP (limpeza automática de hora zero) entrou em ação em uma mensagem de email encontrada contendo malware após a entrega.</span><span class="sxs-lookup"><span data-stu-id="2744b-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2744b-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2744b-142">Related topics</span></span>
- [<span data-ttu-id="2744b-143">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="2744b-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2744b-144">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="2744b-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2744b-145">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="2744b-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2744b-146">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="2744b-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2744b-147">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="2744b-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2744b-148">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="2744b-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
