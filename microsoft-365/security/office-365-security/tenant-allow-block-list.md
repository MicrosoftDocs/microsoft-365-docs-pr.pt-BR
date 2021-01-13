---
title: Gerenciar suas autorizações e blocos na Lista de Bloqueios/Permitir Locatários
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
description: Os administradores podem aprender a configurar os bloqueios e as autorizações na Lista de Bloqueios/Permitir Locatários no portal de Segurança.
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799708"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-103">Gerenciar permite e bloqueia na Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-103">Managing allows and blocks in the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="4b9e8-104">Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-104">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="4b9e8-105">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode não concordar com o veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="4b9e8-106">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="4b9e8-107">A Lista de Bloqueio & s/Bloqueios de Locatários no Centro de Conformidade e Segurança oferece uma maneira de substituir manualmente os vereditos de filtragem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="4b9e8-108">A Lista de Bloqueios/Permitir Locatários é usada durante o fluxo de emails e no momento em que o usuário clica.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="4b9e8-109">Você pode especificar URLs para permitir ou bloquear na Lista de Bloqueios/Bloqueios de Locatários.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-109">You can specify URLs to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="4b9e8-110">Este tópico descreve como configurar entradas na Lista de Bloqueios/Permitir Locatários no Centro de Conformidade do & de Segurança ou no PowerShell (Organizações do PowerShell do Exchange Online para Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4b9e8-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="4b9e8-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4b9e8-112">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4b9e8-113">Para ir diretamente para a página **Permitir/Bloquear Lista** de Locatários, use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="4b9e8-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="4b9e8-114">Os valores de URL disponíveis são descritos na sintaxe da URL para a seção [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-114">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="4b9e8-115">A Lista de Bloqueios/Permitir Locatários permite um máximo de 500 entradas para URLs.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-115">The Tenant Allow/Block List allows a maximum of 500 entries for URLs.</span></span>

- <span data-ttu-id="4b9e8-116">Uma entrada deve estar ativa dentro de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-116">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="4b9e8-117">As entradas de bloco têm precedência sobre as entradas de autorização.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-117">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="4b9e8-118">Por padrão, as entradas na Lista de Bloqueios/Bloqueios de Locatários expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-118">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="4b9e8-119">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-119">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="4b9e8-120">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="4b9e8-121">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="4b9e8-122">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-122">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="4b9e8-123">Para adicionar e remover valores da Lista de Bloqueios/Permitir  Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-123">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="4b9e8-124">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-124">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="4b9e8-125">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-125">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="4b9e8-126">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-126">**Notes**:</span></span>

  - <span data-ttu-id="4b9e8-127">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-127">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4b9e8-128">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-128">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="4b9e8-129">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-129">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-130">Usar o Centro de Conformidade & segurança para criar entradas de URL na Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="4b9e8-131">Para obter detalhes sobre a sintaxe para entradas de URL, consulte a sintaxe da URL para a seção [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="4b9e8-132">No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="4b9e8-133">Na página **Permitir/Bloquear Lista** de Locatários, verifique se a **guia URLs** está selecionada e clique em **Adicionar**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="4b9e8-134">No menu Defina as seguintes configurações no menu Adicionar novas **URLs:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="4b9e8-135">**Adicione URLs com caracteres curinga:** insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="4b9e8-136">**Bloquear/Permitir:** selecione se deseja **permitir** ou **bloquear** as URLs especificadas.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="4b9e8-137">**Nunca expirar:** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="4b9e8-138">Verifique se a configuração está desligada ( Alternar) e use a caixa Expira na caixa Para especificar a data de expiração ![ ](../../media/scc-toggle-off.png) para as entradas. </span><span class="sxs-lookup"><span data-stu-id="4b9e8-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="4b9e8-139">ou</span><span class="sxs-lookup"><span data-stu-id="4b9e8-139">or</span></span>

     - <span data-ttu-id="4b9e8-140">Mova o alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="4b9e8-142">.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-142">.</span></span>

   - <span data-ttu-id="4b9e8-143">**Observação opcional:** insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="4b9e8-144">Quando terminar, clique em **Adicionar.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-145">Usar o Centro de Conformidade & segurança para exibir entradas na Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-145">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="4b9e8-146">No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="4b9e8-147">Selecione a **guia URLs.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-147">Select the **URLs** tab.</span></span>

<span data-ttu-id="4b9e8-148">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-148">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="4b9e8-149">**Valor**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-149">**Value**</span></span>
- <span data-ttu-id="4b9e8-150">**Ação:** **Bloquear** ou **Permitir.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-150">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="4b9e8-151">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-151">**Last updated date**</span></span>
- <span data-ttu-id="4b9e8-152">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-152">**Expiration date**</span></span>
- <span data-ttu-id="4b9e8-153">**Observação**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-153">**Note**</span></span>

<span data-ttu-id="4b9e8-154">Clique **em** Grupo para agrupar as entradas **por Ação** (**Bloquear** ou **Permitir**) ou **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-154">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="4b9e8-155">Clique **em** Pesquisar, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-155">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="4b9e8-156">Quando terminar, clique em Limpar ícone **Limpar** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-156">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="4b9e8-157">Clique **em Filtro**.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-157">Click **Filter**.</span></span> <span data-ttu-id="4b9e8-158">No  menu desdopante Filtro exibido, de configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-158">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="4b9e8-159">**Ação:** selecione **Permitir**, **Bloquear** ou ambos.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-159">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="4b9e8-160">**Nunca expirar**: Selecione desligado: ![ Alternar ](../../media/scc-toggle-off.png) ou desligar: ![ ](../../media/scc-toggle-on.png) Alternar.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-160">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="4b9e8-161">**Last updated:** Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-161">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="4b9e8-162">**Data de expiração:** selecione uma data de início (**De**), uma data de término (**Para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-162">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="4b9e8-163">Quando terminar, clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-163">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="4b9e8-164">Para limpar os filtros existentes, clique em **Filtro** e, no flyout **Filtro** exibido, clique em **Limpar filtros.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-164">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-165">Usar o Centro de Conformidade & segurança para modificar entradas na Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-165">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="4b9e8-166">Você não pode modificar o valor da URL em si.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-166">You can't modify the URL value itself.</span></span> <span data-ttu-id="4b9e8-167">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-167">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="4b9e8-168">No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="4b9e8-169">Selecione a **guia URLs.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-169">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="4b9e8-170">Selecione a entrada que você deseja modificar e clique em **Editar** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-170">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="4b9e8-171">No menu desdopo que aparece, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-171">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="4b9e8-172">**Bloquear/Permitir:** Selecionar **Permitir** ou **Bloquear.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-172">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="4b9e8-173">**Nunca expirar:** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-173">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="4b9e8-174">Verifique se a configuração está desligada ( Alternar) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração da entrada. </span><span class="sxs-lookup"><span data-stu-id="4b9e8-174">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="4b9e8-175">ou</span><span class="sxs-lookup"><span data-stu-id="4b9e8-175">or</span></span>

     - <span data-ttu-id="4b9e8-176">Mova o alternância para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-176">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="4b9e8-178">.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-178">.</span></span>

   - <span data-ttu-id="4b9e8-179">**Observação opcional:** insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-179">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="4b9e8-180">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-180">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-181">Usar o Centro de Conformidade & segurança para remover entradas da Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-181">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="4b9e8-182">No Centro de Conformidade e Segurança &, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="4b9e8-183">Selecione a **guia URLs.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-183">Select the **URLs** tab.</span></span>

3. <span data-ttu-id="4b9e8-184">Selecione a entrada que você deseja remover e clique em **Excluir** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-184">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="4b9e8-185">Na caixa de diálogo de aviso exibida, clique em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-185">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-186">Usar o PowerShell do Exchange Online ou o PowerShell do EOP autônomo para configurar a Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-186">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-187">Usar o PowerShell para adicionar entradas na Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-187">Use PowerShell to add entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="4b9e8-188">Para adicionar entradas na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-188">To add entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="4b9e8-189">Este exemplo adiciona uma entrada de bloco de URL para contoso.com e todos os sub-contoso.com (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-189">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="4b9e8-190">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-190">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

<span data-ttu-id="4b9e8-191">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-191">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-192">Usar o PowerShell para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="4b9e8-192">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="4b9e8-193">Para exibir entradas na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-193">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="4b9e8-194">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-194">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="4b9e8-195">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-195">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-196">Usar o PowerShell para modificar entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="4b9e8-196">Use PowerShell to modify entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="4b9e8-197">Você não pode modificar o valor da URL em si.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-197">You can't modify the URL value itself.</span></span> <span data-ttu-id="4b9e8-198">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-198">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="4b9e8-199">Para modificar entradas na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-199">To modify entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="4b9e8-200">Este exemplo altera a data de expiração da entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-200">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="4b9e8-201">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-201">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-202">Usar o PowerShell para remover entradas da Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="4b9e8-202">Use PowerShell to remove entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="4b9e8-203">Para remover entradas da Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-203">To remove entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="4b9e8-204">Este exemplo remove a entrada de URL especificada da Lista de Bloqueios/Permitir Locatários.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-204">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="4b9e8-205">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-205">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="4b9e8-206">Sintaxe de URL para a Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="4b9e8-206">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="4b9e8-207">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-207">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="4b9e8-208">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-208">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="4b9e8-209">Unicode não é suportado, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-209">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="4b9e8-210">Os nomes de host serão permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-210">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="4b9e8-211">O nome do host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-211">The hostname contains a period.</span></span>
  - <span data-ttu-id="4b9e8-212">Há pelo menos um caractere à esquerda do ponto.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-212">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="4b9e8-213">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-213">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="4b9e8-214">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-214">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="4b9e8-215">Os subcaminhos não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-215">Subpaths are not implied.</span></span>

  <span data-ttu-id="4b9e8-216">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="4b9e8-216">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="4b9e8-217">Caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-217">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="4b9e8-218">Um caractere curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-218">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="4b9e8-219">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-219">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="4b9e8-220">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-220">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="4b9e8-221">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-221">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="4b9e8-222">Todos os subcaminhos não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-222">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="4b9e8-223">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="4b9e8-223">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="4b9e8-224">`*.com*` é inválido (não é um domínio que pode ser resolvido e o curinga direito não segue uma barra).</span><span class="sxs-lookup"><span data-stu-id="4b9e8-224">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="4b9e8-225">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-225">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="4b9e8-226">O caractere til (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-226">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="4b9e8-227">Um til à esquerda implica em um domínio e em todos os sub-domínios.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-227">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="4b9e8-228">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="4b9e8-228">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="4b9e8-229">Entradas de URL que contêm protocolos (por exemplo, , ou ) falharão, porque as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-229">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="4b9e8-230">Um nome de usuário ou senha não tem suporte ou é necessário.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-230">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="4b9e8-231">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-231">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="4b9e8-232">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-232">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="4b9e8-233">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="4b9e8-233">URL entry scenarios</span></span>

<span data-ttu-id="4b9e8-234">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="4b9e8-234">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="4b9e8-235">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="4b9e8-235">Scenario: No wildcards</span></span>

<span data-ttu-id="4b9e8-236">**Entrada:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-236">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="4b9e8-237">**Permitir a combinação**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-237">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="4b9e8-238">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-238">**Allow not matched**:</span></span>

  - <span data-ttu-id="4b9e8-239">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-239">abc-contoso.com</span></span>
  - <span data-ttu-id="4b9e8-240">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-240">contoso.com/a</span></span>
  - <span data-ttu-id="4b9e8-241">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-241">payroll.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-242">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-242">test.com/contoso.com</span></span>
  - <span data-ttu-id="4b9e8-243">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-243">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="4b9e8-244">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-244">www.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-245">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-245">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="4b9e8-246">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-246">**Block match**:</span></span>

  - <span data-ttu-id="4b9e8-247">contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-247">contoso.com</span></span>
  - <span data-ttu-id="4b9e8-248">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-248">contoso.com/a</span></span>
  - <span data-ttu-id="4b9e8-249">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-249">payroll.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-250">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-250">test.com/contoso.com</span></span>
  - <span data-ttu-id="4b9e8-251">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-251">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="4b9e8-252">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-252">www.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-253">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-253">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="4b9e8-254">**Bloqueio não corresponder**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-254">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="4b9e8-255">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="4b9e8-255">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="4b9e8-256">**Entrada:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-256">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="4b9e8-257">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-257">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="4b9e8-258">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-258">www.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-259">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-259">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="4b9e8-260">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-260">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="4b9e8-261">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-261">123contoso.com</span></span>
  - <span data-ttu-id="4b9e8-262">contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-262">contoso.com</span></span>
  - <span data-ttu-id="4b9e8-263">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-263">test.com/contoso.com</span></span>
  - <span data-ttu-id="4b9e8-264">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="4b9e8-264">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="4b9e8-265">Cenário: caractere curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="4b9e8-265">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="4b9e8-266">**Entrada:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-266">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="4b9e8-267">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-267">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="4b9e8-268">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="4b9e8-268">contoso.com/a/b</span></span>
  - <span data-ttu-id="4b9e8-269">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="4b9e8-269">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="4b9e8-270">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-270">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="4b9e8-271">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-271">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="4b9e8-272">contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-272">contoso.com</span></span>
  - <span data-ttu-id="4b9e8-273">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-273">contoso.com/a</span></span>
  - <span data-ttu-id="4b9e8-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-274">www.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-275">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-275">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="4b9e8-276">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="4b9e8-276">Scenario: Left tilde</span></span>

<span data-ttu-id="4b9e8-277">**Entrada:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-277">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="4b9e8-278">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-278">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="4b9e8-279">contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-279">contoso.com</span></span>
  - <span data-ttu-id="4b9e8-280">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-280">www.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-281">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-281">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="4b9e8-282">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-282">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="4b9e8-283">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-283">123contoso.com</span></span>
  - <span data-ttu-id="4b9e8-284">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="4b9e8-284">contoso.com/abc</span></span>
  - <span data-ttu-id="4b9e8-285">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="4b9e8-285">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="4b9e8-286">Cenário: sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="4b9e8-286">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="4b9e8-287">**Entrada:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-287">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="4b9e8-288">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-288">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="4b9e8-289">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-289">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="4b9e8-290">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-290">contoso.com/a</span></span>
  - <span data-ttu-id="4b9e8-291">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="4b9e8-291">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="4b9e8-292">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="4b9e8-292">contoso.com/ab</span></span>
  - <span data-ttu-id="4b9e8-293">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="4b9e8-293">contoso.com/b</span></span>
  - <span data-ttu-id="4b9e8-294">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="4b9e8-294">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="4b9e8-295">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="4b9e8-295">contoso.com/ba</span></span>

- <span data-ttu-id="4b9e8-296">**Allow not matched** and **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-296">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="4b9e8-297">Cenário: subdomínio de curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="4b9e8-297">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="4b9e8-298">**Entrada:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-298">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="4b9e8-299">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-299">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="4b9e8-300">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="4b9e8-300">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="4b9e8-301">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="4b9e8-301">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="4b9e8-302">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-302">www.contoso.com/a</span></span>
  - <span data-ttu-id="4b9e8-303">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="4b9e8-303">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="4b9e8-304">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="4b9e8-304">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="4b9e8-305">**Allow not matched** and **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="4b9e8-305">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="4b9e8-306">Cenário: til esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="4b9e8-306">Scenario: Left and right tilde</span></span>

<span data-ttu-id="4b9e8-307">**Entrada:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-307">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="4b9e8-308">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="4b9e8-309">contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-309">contoso.com</span></span>
  - <span data-ttu-id="4b9e8-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-310">contoso.com/a</span></span>
  - <span data-ttu-id="4b9e8-311">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-311">www.contoso.com</span></span>
  - <span data-ttu-id="4b9e8-312">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="4b9e8-312">www.contoso.com/b</span></span>
  - <span data-ttu-id="4b9e8-313">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-313">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="4b9e8-314">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-314">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="4b9e8-315">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-315">123contoso.com</span></span>
  - <span data-ttu-id="4b9e8-316">contoso.org</span><span class="sxs-lookup"><span data-stu-id="4b9e8-316">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="4b9e8-317">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="4b9e8-317">Scenario: IP address</span></span>

<span data-ttu-id="4b9e8-318">**Entrada:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-318">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="4b9e8-319">**Permitir match** e **Block match:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="4b9e8-319">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="4b9e8-320">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-320">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="4b9e8-321">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-321">1.2.3.4/a</span></span>
  - <span data-ttu-id="4b9e8-322">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="4b9e8-322">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="4b9e8-323">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="4b9e8-323">IP address with right wildcard</span></span>

<span data-ttu-id="4b9e8-324">**Entrada:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="4b9e8-324">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="4b9e8-325">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-325">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="4b9e8-326">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="4b9e8-326">1.2.3.4/b</span></span>
  - <span data-ttu-id="4b9e8-327">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="4b9e8-327">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="4b9e8-328">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="4b9e8-328">Examples of invalid entries</span></span>

<span data-ttu-id="4b9e8-329">As entradas a seguir são inválidas:</span><span class="sxs-lookup"><span data-stu-id="4b9e8-329">The following entries are invalid:</span></span>

- <span data-ttu-id="4b9e8-330">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-330">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="4b9e8-331">contoso</span><span class="sxs-lookup"><span data-stu-id="4b9e8-331">contoso</span></span>
  - <span data-ttu-id="4b9e8-332">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-332">\*.contoso.\*</span></span>
  - <span data-ttu-id="4b9e8-333">\*.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-333">\*.com</span></span>
  - <span data-ttu-id="4b9e8-334">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="4b9e8-334">\*.pdf</span></span>

- <span data-ttu-id="4b9e8-335">**Caractere curinga no texto ou sem caracteres de espaçamento:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-335">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="4b9e8-336">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-336">\*contoso.com</span></span>
  - <span data-ttu-id="4b9e8-337">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-337">contoso.com\*</span></span>
  - <span data-ttu-id="4b9e8-338">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="4b9e8-338">\*1.2.3.4</span></span>
  - <span data-ttu-id="4b9e8-339">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-339">1.2.3.4\*</span></span>
  - <span data-ttu-id="4b9e8-340">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-340">contoso.com/a\*</span></span>
  - <span data-ttu-id="4b9e8-341">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-341">contoso.com/ab\*</span></span>

- <span data-ttu-id="4b9e8-342">**Endereços IP com portas:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-342">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="4b9e8-343">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="4b9e8-343">contoso.com:443</span></span>
  - <span data-ttu-id="4b9e8-344">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="4b9e8-344">abc.contoso.com:25</span></span>

- <span data-ttu-id="4b9e8-345">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-345">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="4b9e8-346">\*.\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-346">\*.\*</span></span>

- <span data-ttu-id="4b9e8-347">**Curingas intermediários:**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-347">**Middle wildcards**:</span></span>

  - <span data-ttu-id="4b9e8-348">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-348">conto\*so.com</span></span>
  - <span data-ttu-id="4b9e8-349">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="4b9e8-349">conto~so.com</span></span>

- <span data-ttu-id="4b9e8-350">**Curingas duplos**</span><span class="sxs-lookup"><span data-stu-id="4b9e8-350">**Double wildcards**</span></span>

  - <span data-ttu-id="4b9e8-351">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-351">contoso.com/\*\*</span></span>
  - <span data-ttu-id="4b9e8-352">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="4b9e8-352">contoso.com/\*/\*</span></span>
