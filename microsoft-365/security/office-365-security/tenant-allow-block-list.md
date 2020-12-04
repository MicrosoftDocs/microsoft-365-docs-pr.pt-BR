---
title: Gerenciar suas URLs permitidas e bloqueadas na lista de permissões/bloqueios de locatários
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar entradas de URL na lista de permissões/bloqueios de locatários no centro de conformidade de & de segurança.
ms.openlocfilehash: 1aae54ffd6026a7fc131017a10f9676d96be9b69
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572629"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a><span data-ttu-id="95135-103">Gerenciar URLs na Lista de Permissões/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="95135-103">Manage URLs in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="95135-104">Os recursos descritos neste tópico estão em visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="95135-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="95135-105">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredicto de filtragem EOP.</span><span class="sxs-lookup"><span data-stu-id="95135-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="95135-106">Por exemplo, uma boa mensagem pode ser marcada como ruim (falso positivo) ou uma mensagem inválida pode ser permitida por meio de (falso negativo).</span><span class="sxs-lookup"><span data-stu-id="95135-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="95135-107">A lista de permissões/bloqueios de locatários no centro de conformidade do & de segurança oferece uma maneira de substituir manualmente o Microsoft 365 Filtering verdicts.</span><span class="sxs-lookup"><span data-stu-id="95135-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="95135-108">A lista de permissões/bloqueios de locatários é usada durante o fluxo de emails e no momento em que o usuário clica.</span><span class="sxs-lookup"><span data-stu-id="95135-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="95135-109">Você pode especificar URLs para permitir ou bloquear a lista de permissões/bloqueios de locatários.</span><span class="sxs-lookup"><span data-stu-id="95135-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="95135-110">Este tópico descreve como configurar entradas na lista de permissões/bloqueios de locatário no centro de conformidade & segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; autônomo do EOP PowerShell para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="95135-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95135-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="95135-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95135-112">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="95135-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="95135-113">Para ir diretamente para a página **lista de permissões/bloqueios de locatários** , use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="95135-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="95135-114">Os valores de URL disponíveis são descritos na [sintaxe da URL para a seção lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="95135-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="95135-115">A lista de permissões/bloqueios de locatários permite um máximo de 500 entradas para URLs.</span><span class="sxs-lookup"><span data-stu-id="95135-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="95135-116">Uma entrada deve estar ativa em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="95135-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="95135-117">As entradas de bloco têm precedência sobre as entradas de permissão.</span><span class="sxs-lookup"><span data-stu-id="95135-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="95135-118">Por padrão, as entradas na lista de permissões/bloqueios de locatários expirarão após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="95135-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="95135-119">Você pode especificar uma data ou defini-las para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="95135-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="95135-120">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="95135-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="95135-121">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="95135-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="95135-122">Você precisa receber permissões no centro de conformidade & de segurança antes de realizar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="95135-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="95135-123">Para adicionar e remover valores da lista de permissões/bloqueios de locatário, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** .</span><span class="sxs-lookup"><span data-stu-id="95135-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="95135-124">Para acesso somente leitura à lista de permissões/bloqueios de locatário, você precisa ser membro dos grupos de função **leitor global** ou **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="95135-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="95135-125">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="95135-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="95135-126">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="95135-126">**Notes**:</span></span>

  - <span data-ttu-id="95135-127">A adição de usuários à função do Azure Active Directory correspondente no centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no centro de conformidade _e_ segurança & para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95135-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="95135-128">Para obter mais informações, confira [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="95135-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="95135-129">O grupo de função de **Gerenciamento de organização somente exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="95135-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="95135-130">Usar o centro de conformidade de & de segurança para criar entradas de URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="95135-131">Para obter detalhes sobre a sintaxe das entradas de URL, consulte a sintaxe da URL da seção [lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="95135-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="95135-132">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários** de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="95135-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="95135-133">Na página **lista de permissões/bloqueios de locatários** , verifique se a guia **URLs** está selecionada e clique em **Adicionar**</span><span class="sxs-lookup"><span data-stu-id="95135-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="95135-134">No submenu **adicionar novas URLs** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95135-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="95135-135">**Adicionar URLs com curingas**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="95135-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="95135-136">**Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** as URLs especificadas.</span><span class="sxs-lookup"><span data-stu-id="95135-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="95135-137">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="95135-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="95135-138">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.</span><span class="sxs-lookup"><span data-stu-id="95135-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="95135-139">ou</span><span class="sxs-lookup"><span data-stu-id="95135-139">or</span></span>

     - <span data-ttu-id="95135-140">Mova a opção para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="95135-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="95135-142">.</span><span class="sxs-lookup"><span data-stu-id="95135-142">.</span></span>

   - <span data-ttu-id="95135-143">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="95135-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="95135-144">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="95135-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="95135-145">Usar o centro de conformidade de & de segurança para exibir entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="95135-146">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários** de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="95135-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="95135-147">Selecione a guia **URLs** .</span><span class="sxs-lookup"><span data-stu-id="95135-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="95135-148">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="95135-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="95135-149">**Valor**</span><span class="sxs-lookup"><span data-stu-id="95135-149">**Value**</span></span>
- <span data-ttu-id="95135-150">**Ação**: **Bloquear** ou **permitir**.</span><span class="sxs-lookup"><span data-stu-id="95135-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="95135-151">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="95135-151">**Last updated date**</span></span>
- <span data-ttu-id="95135-152">**Data de vencimento**</span><span class="sxs-lookup"><span data-stu-id="95135-152">**Expiration date**</span></span>
- <span data-ttu-id="95135-153">**Observação**</span><span class="sxs-lookup"><span data-stu-id="95135-153">**Note**</span></span>

<span data-ttu-id="95135-154">Clique em **Agrupar** para agrupar as entradas **por ação** (**Bloquear** ou **permitir**) ou **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="95135-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="95135-155">Clique em **Pesquisar**, insira todo ou parte de um valor e pressione ENTER para localizar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="95135-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="95135-156">Quando tiver terminado, clique em **limpar** o ![ ícone pesquisa limpar pesquisa ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="95135-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="95135-157">Clique em **filtro**.</span><span class="sxs-lookup"><span data-stu-id="95135-157">Click **Filter**.</span></span> <span data-ttu-id="95135-158">No submenu de **filtro** que aparece, configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95135-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="95135-159">**Ação**: selecione **permitir**, **Bloquear** ou ambos.</span><span class="sxs-lookup"><span data-stu-id="95135-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="95135-160">**Nunca expirar**: selecione Desativado (desativar ![ ](../../media/scc-toggle-off.png) ) ou ativado ( ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="95135-160">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="95135-161">**Última atualização**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="95135-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="95135-162">**Data de validade**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="95135-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="95135-163">Quando tiver concluído, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="95135-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="95135-164">Para limpar filtros existentes, clique em **Filtrar** e, no submenu de **filtro** que aparece, clique em **limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="95135-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="95135-165">Usar o centro de conformidade de & de segurança para modificar as entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="95135-166">Você não pode modificar o próprio valor de URL.</span><span class="sxs-lookup"><span data-stu-id="95135-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="95135-167">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="95135-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="95135-168">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários** de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="95135-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="95135-169">Selecione a guia **URLs** .</span><span class="sxs-lookup"><span data-stu-id="95135-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="95135-170">Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="95135-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="95135-171">No submenu exibido, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95135-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="95135-172">**Bloquear/permitir**: selecione **permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="95135-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="95135-173">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="95135-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="95135-174">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento da entrada.</span><span class="sxs-lookup"><span data-stu-id="95135-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="95135-175">ou</span><span class="sxs-lookup"><span data-stu-id="95135-175">or</span></span>

     - <span data-ttu-id="95135-176">Mova a opção para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="95135-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="95135-178">.</span><span class="sxs-lookup"><span data-stu-id="95135-178">.</span></span>

   - <span data-ttu-id="95135-179">**Observação opcional**: insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="95135-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="95135-180">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="95135-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="95135-181">Usar o centro de conformidade de & de segurança para remover entradas da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="95135-182">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários** de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="95135-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="95135-183">Selecione a guia **URLs** .</span><span class="sxs-lookup"><span data-stu-id="95135-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="95135-184">Selecione a entrada que você deseja remover e clique em **excluir** ![ excluir ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="95135-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="95135-185">Na caixa de diálogo de aviso que aparece, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="95135-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="95135-186">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar a lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="95135-187">Usar o PowerShell para adicionar entradas à lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="95135-188">Para adicionar entradas na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="95135-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="95135-189">Este exemplo adiciona uma entrada de bloco de URL para contoso.com e todos os subdomínios (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="95135-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="95135-190">Como não usamos os parâmetros ExpirationDate ou noexpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="95135-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="95135-191">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="95135-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="95135-192">Usar o PowerShell para exibir entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="95135-193">Para exibir as entradas na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="95135-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="95135-194">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="95135-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="95135-195">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="95135-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="95135-196">Usar o PowerShell para modificar entradas na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="95135-197">Você não pode modificar o próprio valor de URL.</span><span class="sxs-lookup"><span data-stu-id="95135-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="95135-198">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="95135-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="95135-199">Para modificar as entradas na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="95135-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="95135-200">Este exemplo altera a data de vencimento da entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="95135-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="95135-201">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="95135-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="95135-202">Usar o PowerShell para remover entradas da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="95135-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="95135-203">Para remover entradas da lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="95135-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="95135-204">Este exemplo remove a entrada de URL especificada da lista de permissões/bloqueios de locatário.</span><span class="sxs-lookup"><span data-stu-id="95135-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="95135-205">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="95135-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="95135-206">Sintaxe da URL para a lista de permissões/bloqueios de locatário</span><span class="sxs-lookup"><span data-stu-id="95135-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="95135-207">Os endereços IPv6 e IP4v são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="95135-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="95135-208">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="95135-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="95135-209">Unicode não é suportado, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="95135-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="95135-210">Os nomes de host são permitidos se todas as instruções a seguir forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="95135-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="95135-211">O nome do host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="95135-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="95135-212">Há pelo menos um caractere à esquerda do ponto.</span><span class="sxs-lookup"><span data-stu-id="95135-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="95135-213">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="95135-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="95135-214">Por exemplo, `t.co` é permitido; `.com` ou `contoso.` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="95135-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="95135-215">Os subcaminhos não são inferidos.</span><span class="sxs-lookup"><span data-stu-id="95135-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="95135-216">Por exemplo, não `contoso.com` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="95135-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="95135-217">Caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="95135-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="95135-218">Um caractere curinga à esquerda deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="95135-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="95135-219">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="95135-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="95135-220">Um caractere curinga à direita deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="95135-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="95135-221">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou `contoso.com/ab*` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="95135-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="95135-222">Todos os subcaminhos não são inferidos por um caractere curinga correto.</span><span class="sxs-lookup"><span data-stu-id="95135-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="95135-223">Por exemplo, não `contoso.com/*` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="95135-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="95135-224">`*.com*` é inválido (não é um domínio resolvível e o caractere curinga correto não segue uma barra).</span><span class="sxs-lookup"><span data-stu-id="95135-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="95135-225">Curingas não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="95135-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="95135-226">O caractere til (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="95135-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="95135-227">Um til esquerdo implica um domínio e todos os subdomínios.</span><span class="sxs-lookup"><span data-stu-id="95135-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="95135-228">Por exemplo `~contoso.com` inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="95135-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="95135-229">As entradas de URL que contêm protocolos (por exemplo,, `http://` `https://` ou `ftp://` ) falharão, porque as entradas de URL se aplicam a todos os protocolos.</span><span class="sxs-lookup"><span data-stu-id="95135-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="95135-230">Um nome de usuário ou senha não são suportados ou necessários.</span><span class="sxs-lookup"><span data-stu-id="95135-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="95135-231">Aspas ("ou") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="95135-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="95135-232">Uma URL deve incluir todos os redirecionamentos onde for possível.</span><span class="sxs-lookup"><span data-stu-id="95135-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="95135-233">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="95135-233">URL entry scenarios</span></span>

<span data-ttu-id="95135-234">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="95135-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="95135-235">Cenário: sem curingas</span><span class="sxs-lookup"><span data-stu-id="95135-235">Scenario: No wildcards</span></span>

<span data-ttu-id="95135-236">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="95135-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="95135-237">**Permitir correspondência**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="95135-238">**Permitir não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="95135-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="95135-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-239">abc-contoso.com</span></span>
  - <span data-ttu-id="95135-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="95135-240">contoso.com/a</span></span>
  - <span data-ttu-id="95135-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="95135-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="95135-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="95135-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-244">www.contoso.com</span></span>
  - <span data-ttu-id="95135-245">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="95135-245">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="95135-246">**Correspondência de bloco**:</span><span class="sxs-lookup"><span data-stu-id="95135-246">**Block match**:</span></span>

  - <span data-ttu-id="95135-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-247">contoso.com</span></span>
  - <span data-ttu-id="95135-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="95135-248">contoso.com/a</span></span>
  - <span data-ttu-id="95135-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="95135-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="95135-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="95135-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-252">www.contoso.com</span></span>
  - <span data-ttu-id="95135-253">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="95135-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="95135-254">**Bloquear não correspondente**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="95135-255">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="95135-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="95135-256">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="95135-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="95135-257">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="95135-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="95135-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-258">www.contoso.com</span></span>
  - <span data-ttu-id="95135-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="95135-260">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="95135-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="95135-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-261">123contoso.com</span></span>
  - <span data-ttu-id="95135-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-262">contoso.com</span></span>
  - <span data-ttu-id="95135-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="95135-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="95135-264">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="95135-265">Cenário: caractere curinga à direita na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="95135-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="95135-266">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="95135-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="95135-267">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="95135-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="95135-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="95135-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="95135-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="95135-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="95135-270">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="95135-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="95135-271">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="95135-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="95135-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-272">contoso.com</span></span>
  - <span data-ttu-id="95135-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="95135-273">contoso.com/a</span></span>
  - <span data-ttu-id="95135-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-274">www.contoso.com</span></span>
  - <span data-ttu-id="95135-275">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="95135-275">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="95135-276">Cenário: til esquerdo</span><span class="sxs-lookup"><span data-stu-id="95135-276">Scenario: Left tilde</span></span>

<span data-ttu-id="95135-277">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="95135-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="95135-278">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="95135-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="95135-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-279">contoso.com</span></span>
  - <span data-ttu-id="95135-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-280">www.contoso.com</span></span>
  - <span data-ttu-id="95135-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="95135-282">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="95135-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="95135-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-283">123contoso.com</span></span>
  - <span data-ttu-id="95135-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="95135-284">contoso.com/abc</span></span>
  - <span data-ttu-id="95135-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="95135-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="95135-286">Cenário: sufixo curinga à direita</span><span class="sxs-lookup"><span data-stu-id="95135-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="95135-287">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="95135-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="95135-288">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="95135-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="95135-289">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="95135-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="95135-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="95135-290">contoso.com/a</span></span>
  - <span data-ttu-id="95135-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="95135-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="95135-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="95135-292">contoso.com/ab</span></span>
  - <span data-ttu-id="95135-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="95135-293">contoso.com/b</span></span>
  - <span data-ttu-id="95135-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="95135-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="95135-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="95135-295">contoso.com/ba</span></span>

- <span data-ttu-id="95135-296">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="95135-297">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="95135-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="95135-298">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="95135-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="95135-299">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="95135-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="95135-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="95135-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="95135-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="95135-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="95135-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="95135-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="95135-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="95135-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="95135-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="95135-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="95135-305">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="95135-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="95135-306">Cenário: til esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="95135-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="95135-307">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="95135-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="95135-308">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="95135-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="95135-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-309">contoso.com</span></span>
  - <span data-ttu-id="95135-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="95135-310">contoso.com/a</span></span>
  - <span data-ttu-id="95135-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-311">www.contoso.com</span></span>
  - <span data-ttu-id="95135-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="95135-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="95135-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="95135-314">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="95135-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="95135-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-315">123contoso.com</span></span>
  - <span data-ttu-id="95135-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="95135-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="95135-317">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="95135-317">Scenario: IP address</span></span>

<span data-ttu-id="95135-318">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="95135-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="95135-319">**Permitir** correspondência de correspondência e **bloqueio**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="95135-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="95135-320">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="95135-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="95135-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="95135-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="95135-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="95135-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="95135-323">Endereço IP com caractere curinga direito</span><span class="sxs-lookup"><span data-stu-id="95135-323">IP address with right wildcard</span></span>

<span data-ttu-id="95135-324">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="95135-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="95135-325">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="95135-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="95135-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="95135-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="95135-327">1.2.3.4/Baaaa</span><span class="sxs-lookup"><span data-stu-id="95135-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="95135-328">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="95135-328">Examples of invalid entries</span></span>

<span data-ttu-id="95135-329">As entradas a seguir são inválidas:</span><span class="sxs-lookup"><span data-stu-id="95135-329">The following entries are invalid:</span></span>

- <span data-ttu-id="95135-330">**Valores de domínio ausentes ou inválidos**:</span><span class="sxs-lookup"><span data-stu-id="95135-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="95135-331">contoso</span><span class="sxs-lookup"><span data-stu-id="95135-331">contoso</span></span>
  - <span data-ttu-id="95135-332">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="95135-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="95135-333">\*. com</span><span class="sxs-lookup"><span data-stu-id="95135-333">\*.com</span></span>
  - <span data-ttu-id="95135-334">\*. pdf</span><span class="sxs-lookup"><span data-stu-id="95135-334">\*.pdf</span></span>

- <span data-ttu-id="95135-335">**Curinga no texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="95135-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="95135-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="95135-336">\*contoso.com</span></span>
  - <span data-ttu-id="95135-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="95135-337">contoso.com\*</span></span>
  - <span data-ttu-id="95135-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="95135-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="95135-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="95135-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="95135-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="95135-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="95135-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="95135-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="95135-342">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="95135-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="95135-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="95135-343">contoso.com:443</span></span>
  - <span data-ttu-id="95135-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="95135-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="95135-345">**Curingas não descritivos**:</span><span class="sxs-lookup"><span data-stu-id="95135-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="95135-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="95135-346">\*.\*</span></span>

- <span data-ttu-id="95135-347">**Curingas médios**:</span><span class="sxs-lookup"><span data-stu-id="95135-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="95135-348">conta \* so.com</span><span class="sxs-lookup"><span data-stu-id="95135-348">conto\*so.com</span></span>
  - <span data-ttu-id="95135-349">cont ~ so. com</span><span class="sxs-lookup"><span data-stu-id="95135-349">conto~so.com</span></span>

- <span data-ttu-id="95135-350">**Curingas duplos**</span><span class="sxs-lookup"><span data-stu-id="95135-350">**Double wildcards**</span></span>

  - <span data-ttu-id="95135-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="95135-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="95135-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="95135-352">contoso.com/\*/\*</span></span>
