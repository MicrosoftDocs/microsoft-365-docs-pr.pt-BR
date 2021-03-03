---
title: Gerenciar suas autorizações e bloqueios na Lista de Locatários Permitir/Bloquear
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar as permites e os bloqueios na Lista de Locatários de Permitir/Bloquear no portal de Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 960fbf26b610485fb46c935b04aedcc593b85752
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407245"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-103">Gerenciar a lista de Permissões/Bloqueios do Locatário</span><span class="sxs-lookup"><span data-stu-id="e4611-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e4611-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e4611-104">**Applies to**</span></span>
- [<span data-ttu-id="e4611-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e4611-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e4611-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e4611-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="e4611-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4611-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="e4611-108">Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="e4611-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="e4611-109">Não é possível **configurar itens** permitidos na Lista de Locatários Permitidos/Bloqueados no momento.</span><span class="sxs-lookup"><span data-stu-id="e4611-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="e4611-110">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="e4611-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="e4611-111">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="e4611-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="e4611-112">A Lista de Permitir/Bloquear Locatários no Centro de Conformidade & segurança oferece uma maneira de substituir manualmente os vereditos de filtragem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4611-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="e4611-113">A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário.</span><span class="sxs-lookup"><span data-stu-id="e4611-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="e4611-114">Você pode especificar URLs ou arquivos a ser sempre bloqueados.</span><span class="sxs-lookup"><span data-stu-id="e4611-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="e4611-115">Este artigo descreve como configurar entradas na Lista de Locatários Permitir/Bloquear no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="e4611-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e4611-116">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="e4611-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e4611-117">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e4611-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e4611-118">Para ir diretamente para a página **Lista de Locatários Permitir/Bloquear,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="e4611-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="e4611-119">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="e4611-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="e4611-120">Para encontrar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um Prompt de Comando:</span><span class="sxs-lookup"><span data-stu-id="e4611-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="e4611-121">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="e4611-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="e4611-122">Os valores de hash perceptual (pHash) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="e4611-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="e4611-123">Os valores de URL disponíveis são descritos na sintaxe de URL da seção [Lista de Locatários/Bloqueios](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e4611-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="e4611-124">A Lista de Permitir/Bloquear Locatários permite no máximo 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e4611-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="e4611-125">Uma entrada deve estar ativa dentro de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="e4611-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="e4611-126">Por padrão, as entradas na Lista de Locatários Permitir/Bloquear expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e4611-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="e4611-127">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="e4611-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="e4611-128">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4611-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e4611-129">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e4611-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e4611-130">Você precisa ter permissões atribuídas no **Exchange Online** antes de poder fazer os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="e4611-130">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e4611-131">Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. </span><span class="sxs-lookup"><span data-stu-id="e4611-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e4611-132">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="e4611-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e4611-133">Para obter mais informações, confira [Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="e4611-133">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="e4611-134">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="e4611-134">**Notes**:</span></span>

  - <span data-ttu-id="e4611-135">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração  do Microsoft 365 fornece aos usuários as permissões e permissões necessárias para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4611-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e4611-136">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="e4611-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="e4611-137">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="e4611-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-138">Use o Centro de Conformidade & segurança para criar entradas de URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e4611-139">Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e4611-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="e4611-140">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="e4611-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e4611-141">Na página Lista de Locatários **Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="e4611-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="e4611-142">No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e4611-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e4611-143">**Adicionar URLs para bloquear**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="e4611-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="e4611-144">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e4611-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="e4611-145">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="e4611-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="e4611-146">ou</span><span class="sxs-lookup"><span data-stu-id="e4611-146">or</span></span>

     - <span data-ttu-id="e4611-147">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="e4611-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="e4611-149">.</span><span class="sxs-lookup"><span data-stu-id="e4611-149">.</span></span>

   - <span data-ttu-id="e4611-150">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="e4611-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="e4611-151">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e4611-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-152">Use o Centro de Conformidade & segurança para criar entradas de arquivo na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="e4611-153">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="e4611-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e4611-154">Na página **Lista de Locatários Permitir/Bloquear,** selecione **Arquivos** e clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="e4611-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="e4611-155">No menu **Adicionar arquivos para bloquear o** sobrevoo que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e4611-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e4611-156">**Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="e4611-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="e4611-157">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e4611-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="e4611-158">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="e4611-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="e4611-159">ou</span><span class="sxs-lookup"><span data-stu-id="e4611-159">or</span></span>

     - <span data-ttu-id="e4611-160">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="e4611-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="e4611-162">.</span><span class="sxs-lookup"><span data-stu-id="e4611-162">.</span></span>

   - <span data-ttu-id="e4611-163">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="e4611-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="e4611-164">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e4611-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-165">Use o Centro de Conformidade & segurança para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="e4611-166">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="e4611-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e4611-167">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="e4611-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="e4611-168">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="e4611-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="e4611-169">**Valor**: a URL ou o hash de arquivo.</span><span class="sxs-lookup"><span data-stu-id="e4611-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="e4611-170">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="e4611-170">**Last updated date**</span></span>
- <span data-ttu-id="e4611-171">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="e4611-171">**Expiration date**</span></span>
- <span data-ttu-id="e4611-172">**Observação**</span><span class="sxs-lookup"><span data-stu-id="e4611-172">**Note**</span></span>

<span data-ttu-id="e4611-173">Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="e4611-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="e4611-174">Quando terminar, clique em Limpar o **ícone de pesquisa** Limpar pesquisa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="e4611-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="e4611-175">Clique **em Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="e4611-175">Click **Filter**.</span></span> <span data-ttu-id="e4611-176">No flyout **Filter** exibido, configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e4611-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="e4611-177">**Nunca expire**: selecione off: ![ Alternar ](../../media/scc-toggle-off.png) ou desligar: ![ Alternar em ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="e4611-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="e4611-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="e4611-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="e4611-179">**Data de** expiração : selecione uma data de início (**De**), uma data de término (**Para**) ou ambos.</span><span class="sxs-lookup"><span data-stu-id="e4611-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="e4611-180">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="e4611-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="e4611-181">Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="e4611-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-182">Use o Centro de Conformidade & segurança para modificar entradas de bloco na lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="e4611-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e4611-183">Não é possível modificar a URL ou os valores de arquivo bloqueados existentes em uma entrada.</span><span class="sxs-lookup"><span data-stu-id="e4611-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="e4611-184">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="e4611-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="e4611-185">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="e4611-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e4611-186">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="e4611-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="e4611-187">Selecione a entrada de bloco que você deseja modificar e clique em **Editar** ![ ícone editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="e4611-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="e4611-188">No sobrevoo exibido, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="e4611-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e4611-189">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e4611-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="e4611-190">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data ![ ](../../media/scc-toggle-off.png) de expiração da entrada. </span><span class="sxs-lookup"><span data-stu-id="e4611-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="e4611-191">ou</span><span class="sxs-lookup"><span data-stu-id="e4611-191">or</span></span>

     - <span data-ttu-id="e4611-192">Mova a alternância para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="e4611-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="e4611-194">.</span><span class="sxs-lookup"><span data-stu-id="e4611-194">.</span></span>

   - <span data-ttu-id="e4611-195">**Observação opcional**: insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="e4611-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="e4611-196">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e4611-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-197">Use o Centro de Conformidade & segurança para remover entradas de bloqueio da lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="e4611-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="e4611-198">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="e4611-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="e4611-199">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="e4611-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="e4611-200">Selecione a entrada de bloco que você deseja remover e clique em **Excluir** ![ ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Excluir.</span><span class="sxs-lookup"><span data-stu-id="e4611-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="e4611-201">Na caixa de diálogo de aviso exibida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e4611-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-202">Use o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-203">Usar o PowerShell para adicionar entradas de bloco à lista de locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="e4611-204">Para adicionar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e4611-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="e4611-205">Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e4611-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="e4611-206">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e4611-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="e4611-207">Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="e4611-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="e4611-208">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="e4611-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-209">Usar o PowerShell para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e4611-210">Para exibir entradas na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e4611-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="e4611-211">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="e4611-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="e4611-212">Este exemplo retorna informações para o valor de hash de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="e4611-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="e4611-213">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="e4611-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-214">Usar o PowerShell para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="e4611-215">Não é possível modificar a URL ou os valores de arquivo existentes em uma entrada de bloco.</span><span class="sxs-lookup"><span data-stu-id="e4611-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="e4611-216">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="e4611-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="e4611-217">Para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e4611-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="e4611-218">Este exemplo altera a data de expiração da entrada de bloco especificada.</span><span class="sxs-lookup"><span data-stu-id="e4611-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="e4611-219">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="e4611-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-220">Usar o PowerShell para remover entradas de bloco da lista De locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="e4611-221">Para remover entradas de bloco da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e4611-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="e4611-222">Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.</span><span class="sxs-lookup"><span data-stu-id="e4611-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="e4611-223">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="e4611-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="e4611-224">Sintaxe de URL para a Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="e4611-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="e4611-225">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="e4611-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="e4611-226">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="e4611-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="e4611-227">Unicode não tem suporte, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="e4611-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="e4611-228">Os nomes de host são permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="e4611-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="e4611-229">O nomedo host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="e4611-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="e4611-230">Há pelo menos um caractere à esquerda do período.</span><span class="sxs-lookup"><span data-stu-id="e4611-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="e4611-231">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="e4611-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="e4611-232">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="e4611-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="e4611-233">Subpaths não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="e4611-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="e4611-234">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="e4611-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="e4611-235">Os caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="e4611-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="e4611-236">Um curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="e4611-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="e4611-237">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="e4611-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="e4611-238">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="e4611-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="e4611-239">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="e4611-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="e4611-240">Todos os subcamadas não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="e4611-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="e4611-241">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="e4611-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="e4611-242">`*.com*` é inválido (não é um domínio resolvêvel e o caractere curinga direito não segue uma barra de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="e4611-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="e4611-243">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="e4611-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="e4611-244">O caractere tilde (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="e4611-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="e4611-245">Um bloco esquerdo implica um domínio e todos os subdomas.</span><span class="sxs-lookup"><span data-stu-id="e4611-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="e4611-246">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="e4611-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="e4611-247">As entradas de URL que contêm protocolos (por exemplo, , , ou ) falharão, pois as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="e4611-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="e4611-248">Um nome de usuário ou senha não é suportado ou necessário.</span><span class="sxs-lookup"><span data-stu-id="e4611-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="e4611-249">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="e4611-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="e4611-250">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="e4611-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="e4611-251">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="e4611-251">URL entry scenarios</span></span>

<span data-ttu-id="e4611-252">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="e4611-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="e4611-253">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="e4611-253">Scenario: No wildcards</span></span>

<span data-ttu-id="e4611-254">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="e4611-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="e4611-255">**Permitir match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="e4611-256">**Permitir não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="e4611-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="e4611-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-257">abc-contoso.com</span></span>
  - <span data-ttu-id="e4611-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e4611-258">contoso.com/a</span></span>
  - <span data-ttu-id="e4611-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="e4611-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="e4611-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="e4611-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-262">www.contoso.com</span></span>
  - <span data-ttu-id="e4611-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="e4611-264">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-264">**Block match**:</span></span>

  - <span data-ttu-id="e4611-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-265">contoso.com</span></span>
  - <span data-ttu-id="e4611-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e4611-266">contoso.com/a</span></span>
  - <span data-ttu-id="e4611-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="e4611-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="e4611-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="e4611-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-270">www.contoso.com</span></span>
  - <span data-ttu-id="e4611-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="e4611-272">**Bloquear não corresponder :** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="e4611-273">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="e4611-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="e4611-274">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="e4611-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="e4611-275">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e4611-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-276">www.contoso.com</span></span>
  - <span data-ttu-id="e4611-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="e4611-278">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="e4611-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e4611-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-279">123contoso.com</span></span>
  - <span data-ttu-id="e4611-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-280">contoso.com</span></span>
  - <span data-ttu-id="e4611-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="e4611-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="e4611-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="e4611-283">Cenário: curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="e4611-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="e4611-284">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="e4611-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="e4611-285">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e4611-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="e4611-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="e4611-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="e4611-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="e4611-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="e4611-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="e4611-289">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="e4611-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e4611-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-290">contoso.com</span></span>
  - <span data-ttu-id="e4611-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e4611-291">contoso.com/a</span></span>
  - <span data-ttu-id="e4611-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-292">www.contoso.com</span></span>
  - <span data-ttu-id="e4611-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="e4611-294">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="e4611-294">Scenario: Left tilde</span></span>

<span data-ttu-id="e4611-295">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="e4611-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="e4611-296">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e4611-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-297">contoso.com</span></span>
  - <span data-ttu-id="e4611-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-298">www.contoso.com</span></span>
  - <span data-ttu-id="e4611-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="e4611-300">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="e4611-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e4611-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-301">123contoso.com</span></span>
  - <span data-ttu-id="e4611-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="e4611-302">contoso.com/abc</span></span>
  - <span data-ttu-id="e4611-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="e4611-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="e4611-304">Cenário: sufixo curinga correto</span><span class="sxs-lookup"><span data-stu-id="e4611-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="e4611-305">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="e4611-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="e4611-306">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e4611-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="e4611-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="e4611-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e4611-308">contoso.com/a</span></span>
  - <span data-ttu-id="e4611-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="e4611-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="e4611-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="e4611-310">contoso.com/ab</span></span>
  - <span data-ttu-id="e4611-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="e4611-311">contoso.com/b</span></span>
  - <span data-ttu-id="e4611-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="e4611-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="e4611-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="e4611-313">contoso.com/ba</span></span>

- <span data-ttu-id="e4611-314">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="e4611-315">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="e4611-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="e4611-316">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="e4611-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="e4611-317">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e4611-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="e4611-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="e4611-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="e4611-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="e4611-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e4611-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="e4611-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="e4611-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="e4611-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="e4611-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="e4611-323">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="e4611-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="e4611-324">Cenário: bloco esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="e4611-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="e4611-325">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="e4611-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="e4611-326">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e4611-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-327">contoso.com</span></span>
  - <span data-ttu-id="e4611-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="e4611-328">contoso.com/a</span></span>
  - <span data-ttu-id="e4611-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-329">www.contoso.com</span></span>
  - <span data-ttu-id="e4611-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="e4611-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="e4611-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="e4611-332">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="e4611-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e4611-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-333">123contoso.com</span></span>
  - <span data-ttu-id="e4611-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="e4611-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="e4611-335">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="e4611-335">Scenario: IP address</span></span>

<span data-ttu-id="e4611-336">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="e4611-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="e4611-337">**Permitir match** e **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="e4611-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="e4611-338">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="e4611-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="e4611-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="e4611-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="e4611-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="e4611-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="e4611-341">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="e4611-341">IP address with right wildcard</span></span>

<span data-ttu-id="e4611-342">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="e4611-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="e4611-343">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="e4611-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="e4611-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="e4611-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="e4611-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="e4611-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="e4611-346">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="e4611-346">Examples of invalid entries</span></span>

<span data-ttu-id="e4611-347">As seguintes entradas são inválidas:</span><span class="sxs-lookup"><span data-stu-id="e4611-347">The following entries are invalid:</span></span>

- <span data-ttu-id="e4611-348">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="e4611-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="e4611-349">contoso</span><span class="sxs-lookup"><span data-stu-id="e4611-349">contoso</span></span>
  - <span data-ttu-id="e4611-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="e4611-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="e4611-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="e4611-351">\*.com</span></span>
  - <span data-ttu-id="e4611-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="e4611-352">\*.pdf</span></span>

- <span data-ttu-id="e4611-353">**Caractere curinga em texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="e4611-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="e4611-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="e4611-354">\*contoso.com</span></span>
  - <span data-ttu-id="e4611-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="e4611-355">contoso.com\*</span></span>
  - <span data-ttu-id="e4611-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="e4611-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="e4611-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="e4611-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="e4611-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="e4611-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="e4611-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="e4611-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="e4611-360">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="e4611-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="e4611-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="e4611-361">contoso.com:443</span></span>
  - <span data-ttu-id="e4611-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="e4611-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="e4611-363">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="e4611-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="e4611-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="e4611-364">\*.\*</span></span>

- <span data-ttu-id="e4611-365">**Caracteres curinga intermediários**:</span><span class="sxs-lookup"><span data-stu-id="e4611-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="e4611-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="e4611-366">conto\*so.com</span></span>
  - <span data-ttu-id="e4611-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="e4611-367">conto~so.com</span></span>

- <span data-ttu-id="e4611-368">**Caracteres curinga duplos**</span><span class="sxs-lookup"><span data-stu-id="e4611-368">**Double wildcards**</span></span>

  - <span data-ttu-id="e4611-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="e4611-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="e4611-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="e4611-370">contoso.com/\*/\*</span></span>
