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
ms.openlocfilehash: 103ddc9aa0858f9203582ac07a655fd7f5506cf3
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587582"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-103">Gerenciar a lista de Permissões/Bloqueios do Locatário</span><span class="sxs-lookup"><span data-stu-id="3b698-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3b698-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="3b698-104">**Applies to**</span></span>
- [<span data-ttu-id="3b698-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3b698-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3b698-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3b698-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3b698-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3b698-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="3b698-108">Não é possível **configurar itens** permitidos na Lista de Locatários Permitidos/Bloqueados no momento.</span><span class="sxs-lookup"><span data-stu-id="3b698-108">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="3b698-109">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="3b698-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="3b698-110">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="3b698-110">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="3b698-111">A Lista de Permitir/Bloquear Locatários no Centro de Conformidade & segurança oferece uma maneira de substituir manualmente os vereditos de filtragem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b698-111">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="3b698-112">A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário.</span><span class="sxs-lookup"><span data-stu-id="3b698-112">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="3b698-113">Você pode especificar URLs ou arquivos a ser sempre bloqueados.</span><span class="sxs-lookup"><span data-stu-id="3b698-113">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="3b698-114">Este artigo descreve como configurar entradas na Lista de Locatários Permitir/Bloquear no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="3b698-114">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3b698-115">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3b698-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3b698-116">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3b698-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3b698-117">Para ir diretamente para a página **Lista de Locatários Permitir/Bloquear,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="3b698-117">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="3b698-118">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b698-118">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="3b698-119">Para encontrar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um Prompt de Comando:</span><span class="sxs-lookup"><span data-stu-id="3b698-119">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="3b698-120">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="3b698-120">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="3b698-121">Os valores de hash perceptual (pHash) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="3b698-121">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="3b698-122">Os valores de URL disponíveis são descritos na sintaxe de URL da seção [Lista de Locatários/Bloqueios](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3b698-122">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="3b698-123">A Lista de Permitir/Bloquear Locatários permite no máximo 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b698-123">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="3b698-124">O número máximo de caracteres para cada entrada é:</span><span class="sxs-lookup"><span data-stu-id="3b698-124">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="3b698-125">Hashes de arquivo = 64</span><span class="sxs-lookup"><span data-stu-id="3b698-125">File hashes = 64</span></span>
  - <span data-ttu-id="3b698-126">URL = 250</span><span class="sxs-lookup"><span data-stu-id="3b698-126">URL = 250</span></span>

- <span data-ttu-id="3b698-127">Uma entrada deve estar ativa dentro de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="3b698-127">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="3b698-128">Por padrão, as entradas na Lista de Locatários Permitir/Bloquear expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="3b698-128">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="3b698-129">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="3b698-129">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="3b698-130">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3b698-130">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3b698-131">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3b698-131">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3b698-132">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="3b698-132">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="3b698-133">Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. </span><span class="sxs-lookup"><span data-stu-id="3b698-133">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="3b698-134">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="3b698-134">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="3b698-135">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="3b698-135">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="3b698-136">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b698-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="3b698-137">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3b698-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="3b698-138">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="3b698-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-139">Use o Centro de Conformidade & segurança para criar entradas de URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-139">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3b698-140">Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3b698-140">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="3b698-141">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="3b698-141">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3b698-142">Na página Lista de Locatários **Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="3b698-142">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="3b698-143">No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3b698-143">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3b698-144">**Adicionar URLs para bloquear**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="3b698-144">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="3b698-145">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3b698-145">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="3b698-146">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="3b698-146">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="3b698-147">ou</span><span class="sxs-lookup"><span data-stu-id="3b698-147">or</span></span>

     - <span data-ttu-id="3b698-148">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="3b698-148">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="3b698-150">.</span><span class="sxs-lookup"><span data-stu-id="3b698-150">.</span></span>

   - <span data-ttu-id="3b698-151">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="3b698-151">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="3b698-152">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3b698-152">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-153">Use o Centro de Conformidade & segurança para criar entradas de arquivo na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-153">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="3b698-154">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="3b698-154">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3b698-155">Na página **Lista de Locatários Permitir/Bloquear,** selecione **Arquivos** e clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="3b698-155">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="3b698-156">No menu **Adicionar arquivos para bloquear o** sobrevoo que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3b698-156">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3b698-157">**Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="3b698-157">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="3b698-158">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3b698-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="3b698-159">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="3b698-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="3b698-160">ou</span><span class="sxs-lookup"><span data-stu-id="3b698-160">or</span></span>

     - <span data-ttu-id="3b698-161">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="3b698-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="3b698-163">.</span><span class="sxs-lookup"><span data-stu-id="3b698-163">.</span></span>

   - <span data-ttu-id="3b698-164">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="3b698-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="3b698-165">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3b698-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-166">Use o Centro de Conformidade & segurança para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-166">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="3b698-167">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="3b698-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3b698-168">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="3b698-168">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="3b698-169">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="3b698-169">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="3b698-170">**Valor**: a URL ou o hash de arquivo.</span><span class="sxs-lookup"><span data-stu-id="3b698-170">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="3b698-171">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="3b698-171">**Last updated date**</span></span>
- <span data-ttu-id="3b698-172">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="3b698-172">**Expiration date**</span></span>
- <span data-ttu-id="3b698-173">**Observação**</span><span class="sxs-lookup"><span data-stu-id="3b698-173">**Note**</span></span>

<span data-ttu-id="3b698-174">Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="3b698-174">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="3b698-175">Quando terminar, clique em Limpar o **ícone de pesquisa** Limpar pesquisa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="3b698-175">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="3b698-176">Clique **em Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="3b698-176">Click **Filter**.</span></span> <span data-ttu-id="3b698-177">No flyout **Filter** exibido, configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3b698-177">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="3b698-178">**Nunca expire**: selecione off: ![ Alternar ](../../media/scc-toggle-off.png) ou desligar: ![ Alternar em ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="3b698-178">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="3b698-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="3b698-179">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="3b698-180">**Data de** expiração : selecione uma data de início (**De**), uma data de término (**Para**) ou ambos.</span><span class="sxs-lookup"><span data-stu-id="3b698-180">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="3b698-181">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3b698-181">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="3b698-182">Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="3b698-182">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-183">Use o Centro de Conformidade & segurança para modificar entradas de bloco na lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="3b698-183">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3b698-184">Não é possível modificar a URL ou os valores de arquivo bloqueados existentes em uma entrada.</span><span class="sxs-lookup"><span data-stu-id="3b698-184">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="3b698-185">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="3b698-185">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="3b698-186">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="3b698-186">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3b698-187">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="3b698-187">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="3b698-188">Selecione a entrada de bloco que você deseja modificar e clique em **Editar** ![ ícone editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="3b698-188">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="3b698-189">No sobrevoo exibido, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3b698-189">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3b698-190">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3b698-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="3b698-191">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data ![ ](../../media/scc-toggle-off.png) de expiração da entrada. </span><span class="sxs-lookup"><span data-stu-id="3b698-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="3b698-192">ou</span><span class="sxs-lookup"><span data-stu-id="3b698-192">or</span></span>

     - <span data-ttu-id="3b698-193">Mova a alternância para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="3b698-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="3b698-195">.</span><span class="sxs-lookup"><span data-stu-id="3b698-195">.</span></span>

   - <span data-ttu-id="3b698-196">**Observação opcional**: insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="3b698-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="3b698-197">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3b698-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-198">Use o Centro de Conformidade & segurança para remover entradas de bloqueio da lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="3b698-198">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="3b698-199">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="3b698-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="3b698-200">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="3b698-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="3b698-201">Selecione a entrada de bloco que você deseja remover e clique em **Excluir** ![ ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Excluir.</span><span class="sxs-lookup"><span data-stu-id="3b698-201">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="3b698-202">Na caixa de diálogo de aviso exibida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="3b698-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-203">Use o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-204">Usar o PowerShell para adicionar entradas de bloco à lista de locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-204">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="3b698-205">Para adicionar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3b698-205">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="3b698-206">Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="3b698-206">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="3b698-207">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="3b698-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="3b698-208">Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="3b698-208">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="3b698-209">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="3b698-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-210">Usar o PowerShell para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-210">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3b698-211">Para exibir entradas na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3b698-211">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="3b698-212">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="3b698-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="3b698-213">Este exemplo retorna informações para o valor de hash de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="3b698-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="3b698-214">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="3b698-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-215">Usar o PowerShell para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-215">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="3b698-216">Não é possível modificar a URL ou os valores de arquivo existentes em uma entrada de bloco.</span><span class="sxs-lookup"><span data-stu-id="3b698-216">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="3b698-217">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="3b698-217">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="3b698-218">Para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3b698-218">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="3b698-219">Este exemplo altera a data de expiração da entrada de bloco especificada.</span><span class="sxs-lookup"><span data-stu-id="3b698-219">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="3b698-220">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="3b698-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-221">Usar o PowerShell para remover entradas de bloco da lista De locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-221">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="3b698-222">Para remover entradas de bloco da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="3b698-222">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="3b698-223">Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.</span><span class="sxs-lookup"><span data-stu-id="3b698-223">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="3b698-224">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="3b698-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="3b698-225">Sintaxe de URL para a Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="3b698-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="3b698-226">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="3b698-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="3b698-227">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="3b698-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="3b698-228">Unicode não tem suporte, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="3b698-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="3b698-229">Os nomes de host são permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="3b698-229">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="3b698-230">O nomedo host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="3b698-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="3b698-231">Há pelo menos um caractere à esquerda do período.</span><span class="sxs-lookup"><span data-stu-id="3b698-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="3b698-232">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="3b698-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="3b698-233">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="3b698-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="3b698-234">Subpaths não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="3b698-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="3b698-235">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="3b698-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="3b698-236">Os caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="3b698-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="3b698-237">Um curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="3b698-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="3b698-238">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="3b698-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="3b698-239">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="3b698-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="3b698-240">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="3b698-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="3b698-241">Todos os subcamadas não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="3b698-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="3b698-242">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="3b698-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="3b698-243">`*.com*` é inválido (não é um domínio resolvêvel e o caractere curinga direito não segue uma barra de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="3b698-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="3b698-244">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="3b698-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="3b698-245">O caractere tilde (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="3b698-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="3b698-246">Um bloco esquerdo implica um domínio e todos os subdomas.</span><span class="sxs-lookup"><span data-stu-id="3b698-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="3b698-247">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="3b698-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="3b698-248">As entradas de URL que contêm protocolos (por exemplo, , , ou ) falharão, pois as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="3b698-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="3b698-249">Um nome de usuário ou senha não é suportado ou necessário.</span><span class="sxs-lookup"><span data-stu-id="3b698-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="3b698-250">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="3b698-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="3b698-251">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="3b698-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="3b698-252">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="3b698-252">URL entry scenarios</span></span>

<span data-ttu-id="3b698-253">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="3b698-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="3b698-254">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="3b698-254">Scenario: No wildcards</span></span>

<span data-ttu-id="3b698-255">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="3b698-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="3b698-256">**Permitir match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="3b698-257">**Permitir não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="3b698-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="3b698-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-258">abc-contoso.com</span></span>
  - <span data-ttu-id="3b698-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3b698-259">contoso.com/a</span></span>
  - <span data-ttu-id="3b698-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="3b698-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="3b698-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="3b698-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-263">www.contoso.com</span></span>
  - <span data-ttu-id="3b698-264">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-264">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="3b698-265">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-265">**Block match**:</span></span>

  - <span data-ttu-id="3b698-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-266">contoso.com</span></span>
  - <span data-ttu-id="3b698-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3b698-267">contoso.com/a</span></span>
  - <span data-ttu-id="3b698-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="3b698-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="3b698-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="3b698-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-271">www.contoso.com</span></span>
  - <span data-ttu-id="3b698-272">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="3b698-273">**Bloquear não corresponder :** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="3b698-274">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="3b698-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="3b698-275">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="3b698-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="3b698-276">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3b698-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-277">www.contoso.com</span></span>
  - <span data-ttu-id="3b698-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="3b698-279">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="3b698-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3b698-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-280">123contoso.com</span></span>
  - <span data-ttu-id="3b698-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-281">contoso.com</span></span>
  - <span data-ttu-id="3b698-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="3b698-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="3b698-283">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="3b698-284">Cenário: curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="3b698-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="3b698-285">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="3b698-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="3b698-286">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3b698-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="3b698-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="3b698-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="3b698-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="3b698-289">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="3b698-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="3b698-290">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="3b698-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3b698-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-291">contoso.com</span></span>
  - <span data-ttu-id="3b698-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3b698-292">contoso.com/a</span></span>
  - <span data-ttu-id="3b698-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-293">www.contoso.com</span></span>
  - <span data-ttu-id="3b698-294">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-294">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="3b698-295">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="3b698-295">Scenario: Left tilde</span></span>

<span data-ttu-id="3b698-296">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="3b698-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="3b698-297">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3b698-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-298">contoso.com</span></span>
  - <span data-ttu-id="3b698-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-299">www.contoso.com</span></span>
  - <span data-ttu-id="3b698-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="3b698-301">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="3b698-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3b698-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-302">123contoso.com</span></span>
  - <span data-ttu-id="3b698-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="3b698-303">contoso.com/abc</span></span>
  - <span data-ttu-id="3b698-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="3b698-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="3b698-305">Cenário: sufixo curinga correto</span><span class="sxs-lookup"><span data-stu-id="3b698-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="3b698-306">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="3b698-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="3b698-307">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3b698-308">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3b698-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="3b698-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3b698-309">contoso.com/a</span></span>
  - <span data-ttu-id="3b698-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="3b698-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="3b698-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="3b698-311">contoso.com/ab</span></span>
  - <span data-ttu-id="3b698-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="3b698-312">contoso.com/b</span></span>
  - <span data-ttu-id="3b698-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="3b698-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="3b698-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="3b698-314">contoso.com/ba</span></span>

- <span data-ttu-id="3b698-315">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="3b698-316">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="3b698-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="3b698-317">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="3b698-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="3b698-318">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3b698-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="3b698-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="3b698-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="3b698-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="3b698-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3b698-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="3b698-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="3b698-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="3b698-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="3b698-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="3b698-324">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="3b698-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="3b698-325">Cenário: bloco esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="3b698-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="3b698-326">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="3b698-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="3b698-327">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3b698-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-328">contoso.com</span></span>
  - <span data-ttu-id="3b698-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="3b698-329">contoso.com/a</span></span>
  - <span data-ttu-id="3b698-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-330">www.contoso.com</span></span>
  - <span data-ttu-id="3b698-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="3b698-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="3b698-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="3b698-333">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="3b698-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3b698-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-334">123contoso.com</span></span>
  - <span data-ttu-id="3b698-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="3b698-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="3b698-336">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="3b698-336">Scenario: IP address</span></span>

<span data-ttu-id="3b698-337">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="3b698-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="3b698-338">**Permitir match** e **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="3b698-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="3b698-339">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="3b698-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="3b698-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="3b698-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="3b698-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="3b698-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="3b698-342">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="3b698-342">IP address with right wildcard</span></span>

<span data-ttu-id="3b698-343">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="3b698-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="3b698-344">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="3b698-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="3b698-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="3b698-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="3b698-346">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="3b698-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="3b698-347">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="3b698-347">Examples of invalid entries</span></span>

<span data-ttu-id="3b698-348">As seguintes entradas são inválidas:</span><span class="sxs-lookup"><span data-stu-id="3b698-348">The following entries are invalid:</span></span>

- <span data-ttu-id="3b698-349">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="3b698-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="3b698-350">contoso</span><span class="sxs-lookup"><span data-stu-id="3b698-350">contoso</span></span>
  - <span data-ttu-id="3b698-351">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="3b698-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="3b698-352">\*.com</span><span class="sxs-lookup"><span data-stu-id="3b698-352">\*.com</span></span>
  - <span data-ttu-id="3b698-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="3b698-353">\*.pdf</span></span>

- <span data-ttu-id="3b698-354">**Caractere curinga em texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="3b698-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="3b698-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b698-355">\*contoso.com</span></span>
  - <span data-ttu-id="3b698-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="3b698-356">contoso.com\*</span></span>
  - <span data-ttu-id="3b698-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="3b698-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="3b698-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="3b698-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="3b698-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="3b698-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="3b698-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="3b698-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="3b698-361">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="3b698-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="3b698-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="3b698-362">contoso.com:443</span></span>
  - <span data-ttu-id="3b698-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="3b698-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="3b698-364">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="3b698-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="3b698-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="3b698-365">\*.\*</span></span>

- <span data-ttu-id="3b698-366">**Caracteres curinga intermediários**:</span><span class="sxs-lookup"><span data-stu-id="3b698-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="3b698-367">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="3b698-367">conto\*so.com</span></span>
  - <span data-ttu-id="3b698-368">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="3b698-368">conto~so.com</span></span>

- <span data-ttu-id="3b698-369">**Caracteres curinga duplos**</span><span class="sxs-lookup"><span data-stu-id="3b698-369">**Double wildcards**</span></span>

  - <span data-ttu-id="3b698-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="3b698-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="3b698-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="3b698-371">contoso.com/\*/\*</span></span>
