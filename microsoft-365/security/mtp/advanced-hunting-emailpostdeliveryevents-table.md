---
title: Tabela EmailPostDeliveryEvents no esquema de busca avançada
description: Saiba mais sobre ações pós-entrega realizadas nos emails do Microsoft 365 na tabela EmailPostDeliveryEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailPostDeliveryEvents, id da mensagem de rede, remetente, destinatário, id do anexo, nome do anexo, veredito de malware, veredito de phishing, contagem de anexos, contagem de links, contagem de URL
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
ms.openlocfilehash: 774676e15e9018b13674149b6a2e147a91000814
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145494"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="57622-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="57622-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="57622-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="57622-105">**Applies to:**</span></span>
- <span data-ttu-id="57622-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="57622-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="57622-107">A tabela no esquema de busca avançada contém informações sobre ações pós-entrega realizadas em mensagens `EmailPostDeliveryEvents` de email processadas pelo Microsoft 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="57622-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="57622-108">Use essa referência para criar consultas que retornam informações dessa tabela.</span><span class="sxs-lookup"><span data-stu-id="57622-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="57622-109">Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="57622-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="57622-110">Para obter mais informações sobre mensagens de email individuais, você também pode usar [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) o e as [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabelas.</span><span class="sxs-lookup"><span data-stu-id="57622-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="57622-111">Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="57622-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="57622-112">Nome da coluna</span><span class="sxs-lookup"><span data-stu-id="57622-112">Column name</span></span> | <span data-ttu-id="57622-113">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="57622-113">Data type</span></span> | <span data-ttu-id="57622-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="57622-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="57622-115">datetime</span><span class="sxs-lookup"><span data-stu-id="57622-115">datetime</span></span> | <span data-ttu-id="57622-116">A data e a hora em que o evento foi gravado</span><span class="sxs-lookup"><span data-stu-id="57622-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="57622-117">string</span><span class="sxs-lookup"><span data-stu-id="57622-117">string</span></span> | <span data-ttu-id="57622-118">Identificador exclusivo do email, gerado pelo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="57622-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="57622-119">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="57622-119">string</span></span> | <span data-ttu-id="57622-120">Identificador público do email definido pelo seu sistema de envio</span><span class="sxs-lookup"><span data-stu-id="57622-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="57622-121">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="57622-121">string</span></span> | <span data-ttu-id="57622-122">Ação tomada na entidade</span><span class="sxs-lookup"><span data-stu-id="57622-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="57622-123">string</span><span class="sxs-lookup"><span data-stu-id="57622-123">string</span></span> | <span data-ttu-id="57622-124">Tipo de atividade que disparou o evento: Correção manual, ZAP de phishing, ZAP de malware</span><span class="sxs-lookup"><span data-stu-id="57622-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="57622-125">string</span><span class="sxs-lookup"><span data-stu-id="57622-125">string</span></span> | <span data-ttu-id="57622-126">Indica se uma ação foi disparada por um administrador (manualmente ou por meio da aprovação de uma ação automatizada pendente) ou por algum mecanismo especial, como uma ZAP ou entrega dinâmica</span><span class="sxs-lookup"><span data-stu-id="57622-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="57622-127">string</span><span class="sxs-lookup"><span data-stu-id="57622-127">string</span></span> | <span data-ttu-id="57622-128">Resultado da ação</span><span class="sxs-lookup"><span data-stu-id="57622-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="57622-129">string</span><span class="sxs-lookup"><span data-stu-id="57622-129">string</span></span> | <span data-ttu-id="57622-130">Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="57622-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="57622-131">cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="57622-131">string</span></span> | <span data-ttu-id="57622-132">Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos</span><span class="sxs-lookup"><span data-stu-id="57622-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="57622-133">long</span><span class="sxs-lookup"><span data-stu-id="57622-133">long</span></span> | <span data-ttu-id="57622-134">Identificador de evento baseado em um contador de repetição.</span><span class="sxs-lookup"><span data-stu-id="57622-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="57622-135">Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp.</span><span class="sxs-lookup"><span data-stu-id="57622-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="57622-136">Tipos de eventos com suporte</span><span class="sxs-lookup"><span data-stu-id="57622-136">Supported event types</span></span>
<span data-ttu-id="57622-137">Esta tabela captura eventos com os seguintes `ActionType` valores:</span><span class="sxs-lookup"><span data-stu-id="57622-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="57622-138">**Correção manual** – Um administrador manualmente tomou medidas em uma mensagem de email depois que ela foi entregue à caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="57622-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="57622-139">Isso inclui ações realizadas manualmente por meio do [Explorador](../office-365-security/threat-explorer.md) de Ameaças ou aprovações de ações automatizadas de investigação [e resposta (AIR).](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="57622-139">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="57622-140">**ZAP de phishing** [– A ZAP (Limpeza](../office-365-security/zero-hour-auto-purge.md) Automática Zero Hora) tomou medidas em um email de phishing após a entrega.</span><span class="sxs-lookup"><span data-stu-id="57622-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="57622-141">**ZAP de malware** – A ZAP (Limpeza Automática Zero Hora) tomou medidas em uma mensagem de email encontrada contendo malware após a entrega.</span><span class="sxs-lookup"><span data-stu-id="57622-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="57622-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="57622-142">Related topics</span></span>
- [<span data-ttu-id="57622-143">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="57622-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="57622-144">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="57622-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="57622-145">Usar consultas compartilhadas</span><span class="sxs-lookup"><span data-stu-id="57622-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="57622-146">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="57622-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="57622-147">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="57622-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="57622-148">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="57622-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
