---
title: Gerenciar suas URLs permitidas e bloqueadas na lista de permissões/bloqueios de locatários
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar entradas de URL na lista de permissões/bloqueios de locatários no centro de conformidade de & de segurança.
ms.openlocfilehash: 5ff34cca922f18a015bd9da847facc8177cf8790
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552545"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-103">Gerenciar URLs na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-103">Manage URLs in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="64ae6-104">Os recursos descritos neste tópico estão em visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="64ae6-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="64ae6-105">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredicto de filtragem EOP.</span><span class="sxs-lookup"><span data-stu-id="64ae6-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="64ae6-106">Por exemplo, uma boa mensagem pode ser marcada como ruim (falso positivo) ou uma mensagem inválida pode ser permitida por meio de (falso negativo).</span><span class="sxs-lookup"><span data-stu-id="64ae6-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="64ae6-107">A lista de permissões/bloqueios de locatários no centro de conformidade do & de segurança oferece uma maneira de substituir manualmente o Microsoft 365 Filtering verdicts.</span><span class="sxs-lookup"><span data-stu-id="64ae6-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="64ae6-108">A lista de permissões/bloqueios de locatários é usada durante o fluxo de emails e no momento em que o usuário clica.</span><span class="sxs-lookup"><span data-stu-id="64ae6-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="64ae6-109">Você pode especificar URLs para permitir ou bloquear a lista de permissões/bloqueios de locatários.</span><span class="sxs-lookup"><span data-stu-id="64ae6-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="64ae6-110">Este tópico descreve como configurar entradas na lista de permissões/bloqueios de locatário no centro de conformidade & segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; autônomo do EOP PowerShell para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="64ae6-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="64ae6-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="64ae6-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="64ae6-112">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="64ae6-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="64ae6-113">Para ir diretamente para a página **lista de permissões/bloqueios de locatários** , use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="64ae6-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="64ae6-114">Os valores de URL disponíveis são descritos na [sintaxe da URL para a seção lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="64ae6-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="64ae6-115">A lista de permissões/bloqueios de locatários permite um máximo de 500 entradas para URLs.</span><span class="sxs-lookup"><span data-stu-id="64ae6-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLss.</span></span>

- <span data-ttu-id="64ae6-116">Uma entrada deve estar ativa em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="64ae6-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="64ae6-117">As entradas de bloco têm precedência sobre as entradas de permissão.</span><span class="sxs-lookup"><span data-stu-id="64ae6-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="64ae6-118">Por padrão, as entradas na lista de permissões/bloqueios de locatários expirarão após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="64ae6-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="64ae6-119">Você pode especificar uma data ou defini-las para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="64ae6-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="64ae6-120">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="64ae6-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="64ae6-121">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="64ae6-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="64ae6-122">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="64ae6-122">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="64ae6-123">Para adicionar e remover valores da lista de permissões/bloqueios de locatário, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="64ae6-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="64ae6-124">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="64ae6-124">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="64ae6-125">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="64ae6-125">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="64ae6-126">Para acesso somente leitura à lista de permissões/bloqueios de locatário, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="64ae6-126">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="64ae6-127">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="64ae6-127">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="64ae6-128">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="64ae6-128">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-129">Usar o centro de conformidade de & de segurança para criar entradas de URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-129">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="64ae6-130">Para obter detalhes sobre a sintaxe das entradas de URL, consulte a sintaxe da URL da seção [lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="64ae6-130">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="64ae6-131">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="64ae6-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="64ae6-132">Na página **lista de permissões/bloqueios de locatários** , verifique se a guia **URLs** está selecionada e clique em **Adicionar**</span><span class="sxs-lookup"><span data-stu-id="64ae6-132">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="64ae6-133">No submenu **adicionar novas URLs** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="64ae6-133">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="64ae6-134">**Adicionar URLs com curingas**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="64ae6-134">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="64ae6-135">**Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** as URLs especificadas.</span><span class="sxs-lookup"><span data-stu-id="64ae6-135">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="64ae6-136">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="64ae6-136">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="64ae6-137">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.</span><span class="sxs-lookup"><span data-stu-id="64ae6-137">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="64ae6-138">ou</span><span class="sxs-lookup"><span data-stu-id="64ae6-138">or</span></span>

     - <span data-ttu-id="64ae6-139">Mova a opção para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="64ae6-139">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="64ae6-141">.</span><span class="sxs-lookup"><span data-stu-id="64ae6-141">.</span></span>

   - <span data-ttu-id="64ae6-142">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="64ae6-142">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="64ae6-143">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-143">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-144">Usar o centro de conformidade de & de segurança para exibir entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-144">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="64ae6-145">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="64ae6-145">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="64ae6-146">Selecione a guia **URLs** .</span><span class="sxs-lookup"><span data-stu-id="64ae6-146">Select the **URLs** tab.</span></span>

<span data-ttu-id="64ae6-147">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="64ae6-147">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="64ae6-148">**Valor**</span><span class="sxs-lookup"><span data-stu-id="64ae6-148">**Value**</span></span>
- <span data-ttu-id="64ae6-149">**Ação**: **Bloquear** ou **permitir**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-149">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="64ae6-150">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="64ae6-150">**Last updated date**</span></span>
- <span data-ttu-id="64ae6-151">**Data de vencimento**</span><span class="sxs-lookup"><span data-stu-id="64ae6-151">**Expiration date**</span></span>
- <span data-ttu-id="64ae6-152">**Observação**</span><span class="sxs-lookup"><span data-stu-id="64ae6-152">**Note**</span></span>

<span data-ttu-id="64ae6-153">Clique em **Agrupar** para agrupar as entradas **por ação** (**Bloquear** ou **permitir**) ou **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-153">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="64ae6-154">Clique em **Pesquisar**, insira todo ou parte de um valor e pressione ENTER para localizar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="64ae6-154">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="64ae6-155">Quando tiver terminado, clique em **limpar** o ![ ícone pesquisa limpar pesquisa ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="64ae6-155">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="64ae6-156">Clique em **filtro**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-156">Click **Filter**.</span></span> <span data-ttu-id="64ae6-157">No submenu de **filtro** que aparece, configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="64ae6-157">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="64ae6-158">**Ação**: selecione **permitir**, **Bloquear** ou ambos.</span><span class="sxs-lookup"><span data-stu-id="64ae6-158">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="64ae6-159">**Nunca expirar**: selecione Desativado (desativar ![ ](../../media/scc-toggle-off.png) ) ou ativado ( ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="64ae6-159">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="64ae6-160">**Última atualização**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="64ae6-160">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="64ae6-161">**Data de validade**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="64ae6-161">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="64ae6-162">Quando tiver concluído, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-162">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="64ae6-163">Para limpar filtros existentes, clique em **Filtrar**e, no submenu de **filtro** que aparece, clique em **limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-163">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-164">Usar o centro de conformidade de & de segurança para modificar as entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-164">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="64ae6-165">Você não pode modificar o próprio valor de URL.</span><span class="sxs-lookup"><span data-stu-id="64ae6-165">You can't modify the URL value itself.</span></span> <span data-ttu-id="64ae6-166">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="64ae6-166">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="64ae6-167">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="64ae6-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="64ae6-168">Selecione a guia **URLs** .</span><span class="sxs-lookup"><span data-stu-id="64ae6-168">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="64ae6-169">Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="64ae6-169">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="64ae6-170">No submenu exibido, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="64ae6-170">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="64ae6-171">**Bloquear/permitir**: selecione **permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-171">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="64ae6-172">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="64ae6-172">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="64ae6-173">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento da entrada.</span><span class="sxs-lookup"><span data-stu-id="64ae6-173">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="64ae6-174">ou</span><span class="sxs-lookup"><span data-stu-id="64ae6-174">or</span></span>

     - <span data-ttu-id="64ae6-175">Mova a opção para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="64ae6-175">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="64ae6-177">.</span><span class="sxs-lookup"><span data-stu-id="64ae6-177">.</span></span>

   - <span data-ttu-id="64ae6-178">**Observação opcional**: insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="64ae6-178">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="64ae6-179">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-179">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-180">Usar o centro de conformidade de & de segurança para remover entradas da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-180">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="64ae6-181">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="64ae6-181">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="64ae6-182">Selecione a guia **URLs** .</span><span class="sxs-lookup"><span data-stu-id="64ae6-182">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="64ae6-183">Selecione a entrada que você deseja remover e clique em **excluir** ![ excluir ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="64ae6-183">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="64ae6-184">Na caixa de diálogo de aviso que aparece, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="64ae6-184">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-185">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar a lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-185">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-186">Usar o PowerShell para adicionar entradas à lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-186">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="64ae6-187">Para adicionar entradas na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="64ae6-187">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="64ae6-188">Este exemplo adiciona uma entrada de bloco de URL para contoso.com e todos os subdomínios (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="64ae6-188">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="64ae6-189">Como não usamos os parâmetros ExpirationDate ou noexpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="64ae6-189">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="64ae6-190">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="64ae6-190">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-191">Usar o PowerShell para exibir entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-191">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="64ae6-192">Para exibir as entradas na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="64ae6-192">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="64ae6-193">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="64ae6-193">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="64ae6-194">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="64ae6-194">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-195">Usar o PowerShell para modificar entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-195">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="64ae6-196">Você não pode modificar o próprio valor de URL.</span><span class="sxs-lookup"><span data-stu-id="64ae6-196">You can't modify the URL value itself.</span></span> <span data-ttu-id="64ae6-197">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="64ae6-197">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="64ae6-198">Para modificar as entradas na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="64ae6-198">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="64ae6-199">Este exemplo altera a data de vencimento da entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="64ae6-199">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="64ae6-200">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="64ae6-200">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-201">Usar o PowerShell para remover entradas da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="64ae6-201">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="64ae6-202">Para remover entradas da lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="64ae6-202">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="64ae6-203">Este exemplo remove a entrada de URL especificada da lista de permissões/bloqueios de locatário.</span><span class="sxs-lookup"><span data-stu-id="64ae6-203">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="64ae6-204">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="64ae6-204">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="64ae6-205">Sintaxe da URL para a lista de permissões/bloqueios de locatário</span><span class="sxs-lookup"><span data-stu-id="64ae6-205">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="64ae6-206">Os endereços IPv6 e IP4v são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="64ae6-206">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="64ae6-207">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="64ae6-207">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="64ae6-208">Unicode não é suportado, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="64ae6-208">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="64ae6-209">Os nomes de host são permitidos se todas as instruções a seguir forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="64ae6-209">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="64ae6-210">O nome do host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="64ae6-210">The hostname contains a period.</span></span>
  - <span data-ttu-id="64ae6-211">Há pelo menos um caractere à esquerda do ponto.</span><span class="sxs-lookup"><span data-stu-id="64ae6-211">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="64ae6-212">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="64ae6-212">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="64ae6-213">Por exemplo, `t.co` é permitido; `.com` ou `contoso.` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="64ae6-213">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="64ae6-214">Os subcaminhos não são inferidos.</span><span class="sxs-lookup"><span data-stu-id="64ae6-214">Subpaths are not implied.</span></span>

  <span data-ttu-id="64ae6-215">Por exemplo, não `contoso.com` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="64ae6-215">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="64ae6-216">Caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="64ae6-216">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="64ae6-217">Um caractere curinga à esquerda deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="64ae6-217">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="64ae6-218">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="64ae6-218">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="64ae6-219">Um caractere curinga à direita deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="64ae6-219">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="64ae6-220">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou `contoso.com/ab*` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="64ae6-220">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="64ae6-221">Todos os subcaminhos não são inferidos por um caractere curinga correto.</span><span class="sxs-lookup"><span data-stu-id="64ae6-221">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="64ae6-222">Por exemplo, não `contoso.com/*` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="64ae6-222">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="64ae6-223">`*.com*`é inválido (não é um domínio resolvível e o caractere curinga correto não segue uma barra).</span><span class="sxs-lookup"><span data-stu-id="64ae6-223">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="64ae6-224">Curingas não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="64ae6-224">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="64ae6-225">O caractere til (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="64ae6-225">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="64ae6-226">Um til esquerdo implica um domínio e todos os subdomínios.</span><span class="sxs-lookup"><span data-stu-id="64ae6-226">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="64ae6-227">Por exemplo `~contoso.com` inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="64ae6-227">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="64ae6-228">As entradas de URL que contêm protocolos (por exemplo,, `http://` `https://` ou `ftp://` ) falharão, porque as entradas de URL se aplicam a todos os protocolos.</span><span class="sxs-lookup"><span data-stu-id="64ae6-228">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="64ae6-229">Um nome de usuário ou senha não são suportados ou necessários.</span><span class="sxs-lookup"><span data-stu-id="64ae6-229">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="64ae6-230">Aspas ("ou") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="64ae6-230">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="64ae6-231">Uma URL deve incluir todos os redirecionamentos onde for possível.</span><span class="sxs-lookup"><span data-stu-id="64ae6-231">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="64ae6-232">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="64ae6-232">URL entry scenarios</span></span>

<span data-ttu-id="64ae6-233">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="64ae6-233">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="64ae6-234">Cenário: sem curingas</span><span class="sxs-lookup"><span data-stu-id="64ae6-234">Scenario: No wildcards</span></span>

<span data-ttu-id="64ae6-235">**Entrada**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="64ae6-235">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="64ae6-236">**Permitir correspondência**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-236">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="64ae6-237">**Permitir não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-237">**Allow not matched**:</span></span>

  - <span data-ttu-id="64ae6-238">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-238">abc-contoso.com</span></span>
  - <span data-ttu-id="64ae6-239">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-239">contoso.com/a</span></span>
  - <span data-ttu-id="64ae6-240">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-240">payroll.contoso.com</span></span>
  - <span data-ttu-id="64ae6-241">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-241">test.com/contoso.com</span></span>
  - <span data-ttu-id="64ae6-242">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-242">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="64ae6-243">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-243">www.contoso.com</span></span>
  - <span data-ttu-id="64ae6-244">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="64ae6-244">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="64ae6-245">**Correspondência de bloco**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-245">**Block match**:</span></span>

  - <span data-ttu-id="64ae6-246">contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-246">contoso.com</span></span>
  - <span data-ttu-id="64ae6-247">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-247">contoso.com/a</span></span>
  - <span data-ttu-id="64ae6-248">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-248">payroll.contoso.com</span></span>
  - <span data-ttu-id="64ae6-249">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-249">test.com/contoso.com</span></span>
  - <span data-ttu-id="64ae6-250">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-250">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="64ae6-251">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-251">www.contoso.com</span></span>
  - <span data-ttu-id="64ae6-252">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="64ae6-252">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="64ae6-253">**Bloquear não correspondente**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-253">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="64ae6-254">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="64ae6-254">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="64ae6-255">**Entrada**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="64ae6-255">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="64ae6-256">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-256">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="64ae6-257">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-257">www.contoso.com</span></span>
  - <span data-ttu-id="64ae6-258">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-258">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="64ae6-259">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-259">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="64ae6-260">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-260">123contoso.com</span></span>
  - <span data-ttu-id="64ae6-261">contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-261">contoso.com</span></span>
  - <span data-ttu-id="64ae6-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="64ae6-263">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="64ae6-263">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="64ae6-264">Cenário: caractere curinga à direita na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="64ae6-264">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="64ae6-265">**Entrada**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="64ae6-265">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="64ae6-266">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-266">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="64ae6-267">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="64ae6-267">contoso.com/a/b</span></span>
  - <span data-ttu-id="64ae6-268">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="64ae6-268">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="64ae6-269">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="64ae6-269">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="64ae6-270">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-270">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="64ae6-271">contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-271">contoso.com</span></span>
  - <span data-ttu-id="64ae6-272">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-272">contoso.com/a</span></span>
  - <span data-ttu-id="64ae6-273">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-273">www.contoso.com</span></span>
  - <span data-ttu-id="64ae6-274">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="64ae6-274">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="64ae6-275">Cenário: til esquerdo</span><span class="sxs-lookup"><span data-stu-id="64ae6-275">Scenario: Left tilde</span></span>

<span data-ttu-id="64ae6-276">**Entrada**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="64ae6-276">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="64ae6-277">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="64ae6-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-278">contoso.com</span></span>
  - <span data-ttu-id="64ae6-279">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-279">www.contoso.com</span></span>
  - <span data-ttu-id="64ae6-280">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-280">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="64ae6-281">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-281">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="64ae6-282">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-282">123contoso.com</span></span>
  - <span data-ttu-id="64ae6-283">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="64ae6-283">contoso.com/abc</span></span>
  - <span data-ttu-id="64ae6-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="64ae6-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="64ae6-285">Cenário: sufixo curinga à direita</span><span class="sxs-lookup"><span data-stu-id="64ae6-285">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="64ae6-286">**Entrada**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="64ae6-286">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="64ae6-287">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="64ae6-288">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="64ae6-288">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="64ae6-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-289">contoso.com/a</span></span>
  - <span data-ttu-id="64ae6-290">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="64ae6-290">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="64ae6-291">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="64ae6-291">contoso.com/ab</span></span>
  - <span data-ttu-id="64ae6-292">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="64ae6-292">contoso.com/b</span></span>
  - <span data-ttu-id="64ae6-293">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="64ae6-293">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="64ae6-294">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="64ae6-294">contoso.com/ba</span></span>

- <span data-ttu-id="64ae6-295">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-295">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="64ae6-296">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="64ae6-296">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="64ae6-297">**Entrada**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="64ae6-297">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="64ae6-298">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="64ae6-299">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="64ae6-299">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="64ae6-300">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="64ae6-300">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="64ae6-301">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-301">www.contoso.com/a</span></span>
  - <span data-ttu-id="64ae6-302">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="64ae6-302">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="64ae6-303">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="64ae6-303">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="64ae6-304">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="64ae6-304">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="64ae6-305">Cenário: til esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="64ae6-305">Scenario: Left and right tilde</span></span>

<span data-ttu-id="64ae6-306">**Entrada**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="64ae6-306">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="64ae6-307">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="64ae6-308">contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-308">contoso.com</span></span>
  - <span data-ttu-id="64ae6-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-309">contoso.com/a</span></span>
  - <span data-ttu-id="64ae6-310">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-310">www.contoso.com</span></span>
  - <span data-ttu-id="64ae6-311">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="64ae6-311">www.contoso.com/b</span></span>
  - <span data-ttu-id="64ae6-312">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-312">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="64ae6-313">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-313">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="64ae6-314">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-314">123contoso.com</span></span>
  - <span data-ttu-id="64ae6-315">contoso.org</span><span class="sxs-lookup"><span data-stu-id="64ae6-315">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="64ae6-316">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="64ae6-316">Scenario: IP address</span></span>

<span data-ttu-id="64ae6-317">**Entrada**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="64ae6-317">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="64ae6-318">**Permitir** correspondência de correspondência e **bloqueio**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="64ae6-318">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="64ae6-319">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-319">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="64ae6-320">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-320">1.2.3.4/a</span></span>
  - <span data-ttu-id="64ae6-321">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="64ae6-321">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="64ae6-322">Endereço IP com caractere curinga direito</span><span class="sxs-lookup"><span data-stu-id="64ae6-322">IP address with right wildcard</span></span>

<span data-ttu-id="64ae6-323">**Entrada**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="64ae6-323">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="64ae6-324">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="64ae6-325">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="64ae6-325">1.2.3.4/b</span></span>
  - <span data-ttu-id="64ae6-326">1.2.3.4/Baaaa</span><span class="sxs-lookup"><span data-stu-id="64ae6-326">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="64ae6-327">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="64ae6-327">Examples of invalid entries</span></span>

<span data-ttu-id="64ae6-328">As entradas a seguir são inválidas:</span><span class="sxs-lookup"><span data-stu-id="64ae6-328">The following entries are invalid:</span></span>

- <span data-ttu-id="64ae6-329">**Valores de domínio ausentes ou inválidos**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-329">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="64ae6-330">contoso</span><span class="sxs-lookup"><span data-stu-id="64ae6-330">contoso</span></span>
  - <span data-ttu-id="64ae6-331">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-331">\*.contoso.\*</span></span>
  - <span data-ttu-id="64ae6-332">\*. com</span><span class="sxs-lookup"><span data-stu-id="64ae6-332">\*.com</span></span>
  - <span data-ttu-id="64ae6-333">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="64ae6-333">\*.pdf</span></span>

- <span data-ttu-id="64ae6-334">**Curinga no texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-334">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="64ae6-335">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-335">\*contoso.com</span></span>
  - <span data-ttu-id="64ae6-336">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-336">contoso.com\*</span></span>
  - <span data-ttu-id="64ae6-337">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="64ae6-337">\*1.2.3.4</span></span>
  - <span data-ttu-id="64ae6-338">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-338">1.2.3.4\*</span></span>
  - <span data-ttu-id="64ae6-339">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-339">contoso.com/a\*</span></span>
  - <span data-ttu-id="64ae6-340">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-340">contoso.com/ab\*</span></span>

- <span data-ttu-id="64ae6-341">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-341">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="64ae6-342">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="64ae6-342">contoso.com:443</span></span>
  - <span data-ttu-id="64ae6-343">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="64ae6-343">abc.contoso.com:25</span></span>

- <span data-ttu-id="64ae6-344">**Curingas não descritivos**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-344">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="64ae6-345">\*.\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-345">\*.\*</span></span>

- <span data-ttu-id="64ae6-346">**Curingas médios**:</span><span class="sxs-lookup"><span data-stu-id="64ae6-346">**Middle wildcards**:</span></span>

  - <span data-ttu-id="64ae6-347">conta \* so.com</span><span class="sxs-lookup"><span data-stu-id="64ae6-347">conto\*so.com</span></span>
  - <span data-ttu-id="64ae6-348">cont ~ so. com</span><span class="sxs-lookup"><span data-stu-id="64ae6-348">conto~so.com</span></span>

- <span data-ttu-id="64ae6-349">**Curingas duplos**</span><span class="sxs-lookup"><span data-stu-id="64ae6-349">**Double wildcards**</span></span>

  - <span data-ttu-id="64ae6-350">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-350">contoso.com/\*\*</span></span>
  - <span data-ttu-id="64ae6-351">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="64ae6-351">contoso.com/\*/\*</span></span>
