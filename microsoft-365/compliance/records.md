---
title: Saiba mais sobre os registros
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre os registros para ajudá-lo na implementação de uma solução de gerenciamento de registros no Microsoft 365.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685437"
---
# <a name="learn-about-records"></a><span data-ttu-id="309ad-103">Saiba mais sobre os registros</span><span class="sxs-lookup"><span data-stu-id="309ad-103">Learn about records</span></span>

><span data-ttu-id="309ad-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="309ad-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="309ad-105">O gerenciamento de registros no Microsoft 365 ajuda a organização a cumprir políticas corporativas, e obrigações legais ou regulamentares, além de reduzir riscos e responsabilidades legais.</span><span class="sxs-lookup"><span data-stu-id="309ad-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="309ad-106">Quando o conteúdo é marcado como registro:</span><span class="sxs-lookup"><span data-stu-id="309ad-106">When content is marked as a record:</span></span>

- <span data-ttu-id="309ad-107">Restrições são colocadas nos itens em termos de quais [ações são permitidas ou bloqueadas](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="309ad-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="309ad-108">Atividades adicionais sobre o item são registradas.</span><span class="sxs-lookup"><span data-stu-id="309ad-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="309ad-109">Você tem prova de disposição quando os itens são excluídos no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="309ad-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="309ad-110">Você usa [rótulos de retenção](retention.md#retention-labels) para marcar conteúdos como registros.</span><span class="sxs-lookup"><span data-stu-id="309ad-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="309ad-111">É possível publicar esses rótulos para que usuários e administradores possam aplicá-los manualmente ou automaticamente ao conteúdo que você deseja classificar como registro.</span><span class="sxs-lookup"><span data-stu-id="309ad-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="309ad-112">Usando rótulos de retenção para marcar o conteúdo como registro, você pode implementar uma estratégia única e consistente para gerenciar registros no ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="309ad-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="309ad-113">Comparar restrições para quais ações são permitidas ou bloqueadas</span><span class="sxs-lookup"><span data-stu-id="309ad-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="309ad-114">Use a tabela a seguir para identificar quais restrições são impostas ao conteúdo como resultado da aplicação de um rótulo de retenção padrão e rótulos de retenção que marcam o conteúdo como registro.</span><span class="sxs-lookup"><span data-stu-id="309ad-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="309ad-115">Um rótulo de retenção padrão tem a configuração de retenção de dados sem marcar o conteúdo como registro.</span><span class="sxs-lookup"><span data-stu-id="309ad-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="309ad-116">Para garantir a integridade, a tabela inclui colunas para um registro bloqueado e desbloqueado, aplicável ao SharePoint e OneDrive, mas não ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="309ad-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="309ad-117">A capacidade de bloquear e desbloquear um registro usa o [controle de versão do registro](record-versioning.md) que não tem suporte para itens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="309ad-117">The ability to lock and unlock a record uses [record versioning](record-versioning.md) that isn't supported for Exchange items.</span></span> <span data-ttu-id="309ad-118">Portanto, para todos os itens do Exchange marcados como registro, o comportamento é mapeado para a coluna **Registro - bloqueado** e a coluna **Registro - desbloqueado** não é relevante.</span><span class="sxs-lookup"><span data-stu-id="309ad-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="309ad-119">Action</span><span class="sxs-lookup"><span data-stu-id="309ad-119">Action</span></span>| <span data-ttu-id="309ad-120">Rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="309ad-120">Retention label</span></span> |<span data-ttu-id="309ad-121">Registro - bloqueado</span><span class="sxs-lookup"><span data-stu-id="309ad-121">Record - locked</span></span>| <span data-ttu-id="309ad-122">Registro - desbloqueado</span><span class="sxs-lookup"><span data-stu-id="309ad-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="309ad-123">Editar conteúdo</span><span class="sxs-lookup"><span data-stu-id="309ad-123">Edit contents</span></span>|<span data-ttu-id="309ad-124">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-124">Allowed</span></span> | <span data-ttu-id="309ad-125">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="309ad-125">**Blocked**</span></span> | <span data-ttu-id="309ad-126">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-126">Allowed</span></span>|
|<span data-ttu-id="309ad-127">Editar propriedades, incluindo renomear</span><span class="sxs-lookup"><span data-stu-id="309ad-127">Edit properties, including rename</span></span>|<span data-ttu-id="309ad-128">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-128">Allowed</span></span> |<span data-ttu-id="309ad-129">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-129">Allowed</span></span> | <span data-ttu-id="309ad-130">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-130">Allowed</span></span>|
|<span data-ttu-id="309ad-131">Excluir</span><span class="sxs-lookup"><span data-stu-id="309ad-131">Delete</span></span>|<span data-ttu-id="309ad-132">Permitido <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="309ad-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="309ad-133">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="309ad-133">**Blocked**</span></span> | <span data-ttu-id="309ad-134">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="309ad-134">**Blocked**</span></span>|
|<span data-ttu-id="309ad-135">Copiar</span><span class="sxs-lookup"><span data-stu-id="309ad-135">Copy</span></span>|<span data-ttu-id="309ad-136">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-136">Allowed</span></span> |<span data-ttu-id="309ad-137">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-137">Allowed</span></span> | <span data-ttu-id="309ad-138">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-138">Allowed</span></span>|
|<span data-ttu-id="309ad-139">Mover dentro do contêiner <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="309ad-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="309ad-140">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-140">Allowed</span></span> |<span data-ttu-id="309ad-141">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-141">Allowed</span></span> | <span data-ttu-id="309ad-142">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-142">Allowed</span></span>|
|<span data-ttu-id="309ad-143">Mover entre contêineres <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="309ad-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="309ad-144">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-144">Allowed</span></span> |<span data-ttu-id="309ad-145">Permitido se nunca desbloqueado</span><span class="sxs-lookup"><span data-stu-id="309ad-145">Allowed if never unlocked</span></span> | <span data-ttu-id="309ad-146">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-146">Allowed</span></span>|
|<span data-ttu-id="309ad-147">Abrir/Ler</span><span class="sxs-lookup"><span data-stu-id="309ad-147">Open/Read</span></span>|<span data-ttu-id="309ad-148">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-148">Allowed</span></span> |<span data-ttu-id="309ad-149">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-149">Allowed</span></span> | <span data-ttu-id="309ad-150">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-150">Allowed</span></span>|
|<span data-ttu-id="309ad-151">Alterar rótulo</span><span class="sxs-lookup"><span data-stu-id="309ad-151">Change label</span></span>|<span data-ttu-id="309ad-152">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-152">Allowed</span></span> |<span data-ttu-id="309ad-153">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="309ad-153">Allowed - container admin only</span></span> | <span data-ttu-id="309ad-154">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="309ad-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="309ad-155">Remover rótulo</span><span class="sxs-lookup"><span data-stu-id="309ad-155">Remove label</span></span>|<span data-ttu-id="309ad-156">Permitido</span><span class="sxs-lookup"><span data-stu-id="309ad-156">Allowed</span></span> |<span data-ttu-id="309ad-157">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="309ad-157">Allowed - container admin only</span></span> | <span data-ttu-id="309ad-158">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="309ad-158">Allowed - container admin only</span></span>|

<span data-ttu-id="309ad-159">Notas de rodapé:</span><span class="sxs-lookup"><span data-stu-id="309ad-159">Footnotes:</span></span>

<span data-ttu-id="309ad-160"><sup>1</sup> Com suporte do OneDrive e Exchange, mantendo uma cópia em um local seguro, mas bloqueado pelo SharePoint.</span><span class="sxs-lookup"><span data-stu-id="309ad-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="309ad-161">Mensagem que um usuário vê se tentar excluir um documento rotulado no SharePoint:</span><span class="sxs-lookup"><span data-stu-id="309ad-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Mensagem informando que o item não foi excluído do SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="309ad-163"><sup>2</sup> Os contêineres incluem bibliotecas de documentos do SharePoint e caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="309ad-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="309ad-164">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="309ad-164">Next steps</span></span>

<span data-ttu-id="309ad-165">Se você ainda não tiver rótulos de retenção para usar o gerenciamento de registros, confira [Introdução aos rótulos de retenção e políticas de retenção](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="309ad-165">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="309ad-166">Para marcar o conteúdo como registro, confira [Declarar registros usando rótulos de retenção](declare-records.md).</span><span class="sxs-lookup"><span data-stu-id="309ad-166">To mark content as a record, see [Declare records by using retention labels](declare-records.md).</span></span>
