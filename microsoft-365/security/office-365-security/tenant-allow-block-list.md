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
ms.openlocfilehash: 55116ddac8fa25b63e50b7fba73f668855e2858d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203306"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-103">Gerenciar a lista de Permissões/Bloqueios do Locatário</span><span class="sxs-lookup"><span data-stu-id="7b066-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7b066-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="7b066-104">**Applies to**</span></span>
- [<span data-ttu-id="7b066-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b066-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7b066-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7b066-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7b066-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b066-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="7b066-108">Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="7b066-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="7b066-109">Não é possível **configurar itens** permitidos na Lista de Locatários Permitidos/Bloqueados no momento.</span><span class="sxs-lookup"><span data-stu-id="7b066-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="7b066-110">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="7b066-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="7b066-111">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="7b066-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="7b066-112">A Lista de Permitir/Bloquear Locatários no Centro de Conformidade & segurança oferece uma maneira de substituir manualmente os vereditos de filtragem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b066-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="7b066-113">A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário.</span><span class="sxs-lookup"><span data-stu-id="7b066-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="7b066-114">Você pode especificar URLs ou arquivos a ser sempre bloqueados.</span><span class="sxs-lookup"><span data-stu-id="7b066-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="7b066-115">Este artigo descreve como configurar entradas na Lista de Locatários Permitir/Bloquear no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="7b066-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7b066-116">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="7b066-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7b066-117">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7b066-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7b066-118">Para ir diretamente para a página **Lista de Locatários Permitir/Bloquear,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="7b066-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="7b066-119">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="7b066-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="7b066-120">Para encontrar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um Prompt de Comando:</span><span class="sxs-lookup"><span data-stu-id="7b066-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="7b066-121">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="7b066-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="7b066-122">Os valores de hash perceptual (pHash) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="7b066-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="7b066-123">Os valores de URL disponíveis são descritos na sintaxe de URL da seção [Lista de Locatários/Bloqueios](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7b066-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="7b066-124">A Lista de Permitir/Bloquear Locatários permite no máximo 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7b066-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="7b066-125">O número máximo de caracteres para cada entrada é:</span><span class="sxs-lookup"><span data-stu-id="7b066-125">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="7b066-126">Hashes de arquivo = 64</span><span class="sxs-lookup"><span data-stu-id="7b066-126">File hashes = 64</span></span>
  - <span data-ttu-id="7b066-127">URL = 250</span><span class="sxs-lookup"><span data-stu-id="7b066-127">URL = 250</span></span>

- <span data-ttu-id="7b066-128">Uma entrada deve estar ativa dentro de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="7b066-128">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="7b066-129">Por padrão, as entradas na Lista de Locatários Permitir/Bloquear expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="7b066-129">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="7b066-130">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="7b066-130">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="7b066-131">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b066-131">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="7b066-132">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7b066-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7b066-133">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="7b066-133">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7b066-134">Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. </span><span class="sxs-lookup"><span data-stu-id="7b066-134">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="7b066-135">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="7b066-135">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7b066-136">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="7b066-136">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  > 
  > - <span data-ttu-id="7b066-137">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7b066-137">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7b066-138">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7b066-138">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  > - <span data-ttu-id="7b066-139">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="7b066-139">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-140">Use o Centro de Conformidade & segurança para criar entradas de URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-140">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7b066-141">Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7b066-141">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="7b066-142">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="7b066-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7b066-143">Na página Lista de Locatários **Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="7b066-143">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="7b066-144">No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7b066-144">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7b066-145">**Adicionar URLs para bloquear**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="7b066-145">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="7b066-146">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7b066-146">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="7b066-147">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="7b066-147">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="7b066-148">ou</span><span class="sxs-lookup"><span data-stu-id="7b066-148">or</span></span>

     - <span data-ttu-id="7b066-149">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="7b066-149">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="7b066-151">.</span><span class="sxs-lookup"><span data-stu-id="7b066-151">.</span></span>

   - <span data-ttu-id="7b066-152">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="7b066-152">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="7b066-153">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7b066-153">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-154">Use o Centro de Conformidade & segurança para criar entradas de arquivo na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-154">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="7b066-155">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="7b066-155">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7b066-156">Na página **Lista de Locatários Permitir/Bloquear,** selecione **Arquivos** e clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="7b066-156">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="7b066-157">No menu **Adicionar arquivos para bloquear o** sobrevoo que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7b066-157">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7b066-158">**Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="7b066-158">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="7b066-159">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7b066-159">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="7b066-160">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="7b066-160">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="7b066-161">ou</span><span class="sxs-lookup"><span data-stu-id="7b066-161">or</span></span>

     - <span data-ttu-id="7b066-162">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="7b066-162">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="7b066-164">.</span><span class="sxs-lookup"><span data-stu-id="7b066-164">.</span></span>

   - <span data-ttu-id="7b066-165">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="7b066-165">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="7b066-166">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7b066-166">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-167">Use o Centro de Conformidade & segurança para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-167">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="7b066-168">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="7b066-168">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7b066-169">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="7b066-169">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="7b066-170">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="7b066-170">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="7b066-171">**Valor**: a URL ou o hash de arquivo.</span><span class="sxs-lookup"><span data-stu-id="7b066-171">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="7b066-172">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="7b066-172">**Last updated date**</span></span>
- <span data-ttu-id="7b066-173">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="7b066-173">**Expiration date**</span></span>
- <span data-ttu-id="7b066-174">**Observação**</span><span class="sxs-lookup"><span data-stu-id="7b066-174">**Note**</span></span>

<span data-ttu-id="7b066-175">Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="7b066-175">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="7b066-176">Quando terminar, clique em Limpar o **ícone de pesquisa** Limpar pesquisa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="7b066-176">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="7b066-177">Clique **em Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="7b066-177">Click **Filter**.</span></span> <span data-ttu-id="7b066-178">No flyout **Filter** exibido, configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7b066-178">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="7b066-179">**Nunca expire**: selecione off: ![ Alternar ](../../media/scc-toggle-off.png) ou desligar: ![ Alternar em ](../../media/scc-toggle-on.png) .</span><span class="sxs-lookup"><span data-stu-id="7b066-179">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="7b066-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="7b066-180">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="7b066-181">**Data de** expiração : selecione uma data de início (**De**), uma data de término (**Para**) ou ambos.</span><span class="sxs-lookup"><span data-stu-id="7b066-181">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="7b066-182">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="7b066-182">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="7b066-183">Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="7b066-183">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-184">Use o Centro de Conformidade & segurança para modificar entradas de bloco na lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="7b066-184">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7b066-185">Não é possível modificar a URL ou os valores de arquivo bloqueados existentes em uma entrada.</span><span class="sxs-lookup"><span data-stu-id="7b066-185">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="7b066-186">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="7b066-186">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="7b066-187">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="7b066-187">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7b066-188">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="7b066-188">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="7b066-189">Selecione a entrada de bloco que você deseja modificar e clique em **Editar** ![ ícone editar ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="7b066-189">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="7b066-190">No sobrevoo exibido, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7b066-190">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="7b066-191">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7b066-191">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="7b066-192">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data ![ ](../../media/scc-toggle-off.png) de expiração da entrada. </span><span class="sxs-lookup"><span data-stu-id="7b066-192">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

       <span data-ttu-id="7b066-193">ou</span><span class="sxs-lookup"><span data-stu-id="7b066-193">or</span></span>

     - <span data-ttu-id="7b066-194">Mova a alternância para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="7b066-194">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="7b066-196">.</span><span class="sxs-lookup"><span data-stu-id="7b066-196">.</span></span>

   - <span data-ttu-id="7b066-197">**Observação opcional**: insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="7b066-197">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="7b066-198">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7b066-198">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-199">Use o Centro de Conformidade & segurança para remover entradas de bloqueio da lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="7b066-199">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="7b066-200">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="7b066-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="7b066-201">Selecione a **guia URLs** ou a **guia Arquivos.**</span><span class="sxs-lookup"><span data-stu-id="7b066-201">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="7b066-202">Selecione a entrada de bloco que você deseja remover e clique em **Excluir** ![ ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Excluir.</span><span class="sxs-lookup"><span data-stu-id="7b066-202">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="7b066-203">Na caixa de diálogo de aviso exibida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="7b066-203">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-204">Use o PowerShell do Exchange Online ou o EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-204">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-205">Usar o PowerShell para adicionar entradas de bloco à lista de locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-205">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="7b066-206">Para adicionar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7b066-206">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="7b066-207">Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7b066-207">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="7b066-208">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="7b066-208">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="7b066-209">Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="7b066-209">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="7b066-210">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="7b066-210">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-211">Usar o PowerShell para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-211">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7b066-212">Para exibir entradas na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7b066-212">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="7b066-213">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="7b066-213">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="7b066-214">Este exemplo retorna informações para o valor de hash de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="7b066-214">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="7b066-215">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="7b066-215">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-216">Usar o PowerShell para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-216">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="7b066-217">Não é possível modificar a URL ou os valores de arquivo existentes em uma entrada de bloco.</span><span class="sxs-lookup"><span data-stu-id="7b066-217">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="7b066-218">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="7b066-218">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="7b066-219">Para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7b066-219">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="7b066-220">Este exemplo altera a data de expiração da entrada de bloco especificada.</span><span class="sxs-lookup"><span data-stu-id="7b066-220">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="7b066-221">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="7b066-221">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-222">Usar o PowerShell para remover entradas de bloco da lista De locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-222">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="7b066-223">Para remover entradas de bloco da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7b066-223">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="7b066-224">Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.</span><span class="sxs-lookup"><span data-stu-id="7b066-224">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="7b066-225">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="7b066-225">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="7b066-226">Sintaxe de URL para a Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="7b066-226">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="7b066-227">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="7b066-227">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="7b066-228">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="7b066-228">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="7b066-229">Unicode não tem suporte, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="7b066-229">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="7b066-230">Os nomes de host são permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="7b066-230">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="7b066-231">O nomedo host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="7b066-231">The hostname contains a period.</span></span>
  - <span data-ttu-id="7b066-232">Há pelo menos um caractere à esquerda do período.</span><span class="sxs-lookup"><span data-stu-id="7b066-232">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="7b066-233">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="7b066-233">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="7b066-234">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="7b066-234">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="7b066-235">Subpaths não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="7b066-235">Subpaths are not implied.</span></span>

  <span data-ttu-id="7b066-236">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="7b066-236">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="7b066-237">Os caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="7b066-237">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="7b066-238">Um curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="7b066-238">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="7b066-239">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="7b066-239">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="7b066-240">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="7b066-240">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="7b066-241">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="7b066-241">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="7b066-242">Todos os subcamadas não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="7b066-242">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="7b066-243">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="7b066-243">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="7b066-244">`*.com*` é inválido (não é um domínio resolvêvel e o caractere curinga direito não segue uma barra de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="7b066-244">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="7b066-245">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="7b066-245">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="7b066-246">O caractere tilde (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="7b066-246">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="7b066-247">Um bloco esquerdo implica um domínio e todos os subdomas.</span><span class="sxs-lookup"><span data-stu-id="7b066-247">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="7b066-248">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="7b066-248">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="7b066-249">As entradas de URL que contêm protocolos (por exemplo, , , ou ) falharão, pois as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="7b066-249">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="7b066-250">Um nome de usuário ou senha não é suportado ou necessário.</span><span class="sxs-lookup"><span data-stu-id="7b066-250">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="7b066-251">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="7b066-251">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="7b066-252">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="7b066-252">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="7b066-253">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="7b066-253">URL entry scenarios</span></span>

<span data-ttu-id="7b066-254">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="7b066-254">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="7b066-255">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="7b066-255">Scenario: No wildcards</span></span>

<span data-ttu-id="7b066-256">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="7b066-256">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="7b066-257">**Permitir match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-257">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="7b066-258">**Permitir não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="7b066-258">**Allow not matched**:</span></span>

  - <span data-ttu-id="7b066-259">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-259">abc-contoso.com</span></span>
  - <span data-ttu-id="7b066-260">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7b066-260">contoso.com/a</span></span>
  - <span data-ttu-id="7b066-261">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-261">payroll.contoso.com</span></span>
  - <span data-ttu-id="7b066-262">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-262">test.com/contoso.com</span></span>
  - <span data-ttu-id="7b066-263">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-263">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="7b066-264">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-264">www.contoso.com</span></span>
  - <span data-ttu-id="7b066-265">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-265">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="7b066-266">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-266">**Block match**:</span></span>

  - <span data-ttu-id="7b066-267">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-267">contoso.com</span></span>
  - <span data-ttu-id="7b066-268">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7b066-268">contoso.com/a</span></span>
  - <span data-ttu-id="7b066-269">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-269">payroll.contoso.com</span></span>
  - <span data-ttu-id="7b066-270">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-270">test.com/contoso.com</span></span>
  - <span data-ttu-id="7b066-271">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-271">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="7b066-272">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-272">www.contoso.com</span></span>
  - <span data-ttu-id="7b066-273">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-273">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="7b066-274">**Bloquear não corresponder :** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-274">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="7b066-275">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="7b066-275">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="7b066-276">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="7b066-276">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="7b066-277">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-277">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7b066-278">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-278">www.contoso.com</span></span>
  - <span data-ttu-id="7b066-279">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-279">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="7b066-280">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="7b066-280">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7b066-281">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-281">123contoso.com</span></span>
  - <span data-ttu-id="7b066-282">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-282">contoso.com</span></span>
  - <span data-ttu-id="7b066-283">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-283">test.com/contoso.com</span></span>
  - <span data-ttu-id="7b066-284">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="7b066-284">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="7b066-285">Cenário: curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="7b066-285">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="7b066-286">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="7b066-286">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="7b066-287">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-287">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7b066-288">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="7b066-288">contoso.com/a/b</span></span>
  - <span data-ttu-id="7b066-289">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="7b066-289">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="7b066-290">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="7b066-290">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="7b066-291">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="7b066-291">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7b066-292">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-292">contoso.com</span></span>
  - <span data-ttu-id="7b066-293">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7b066-293">contoso.com/a</span></span>
  - <span data-ttu-id="7b066-294">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-294">www.contoso.com</span></span>
  - <span data-ttu-id="7b066-295">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-295">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="7b066-296">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="7b066-296">Scenario: Left tilde</span></span>

<span data-ttu-id="7b066-297">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="7b066-297">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="7b066-298">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-298">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7b066-299">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-299">contoso.com</span></span>
  - <span data-ttu-id="7b066-300">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-300">www.contoso.com</span></span>
  - <span data-ttu-id="7b066-301">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-301">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="7b066-302">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="7b066-302">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7b066-303">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-303">123contoso.com</span></span>
  - <span data-ttu-id="7b066-304">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="7b066-304">contoso.com/abc</span></span>
  - <span data-ttu-id="7b066-305">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="7b066-305">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="7b066-306">Cenário: sufixo curinga correto</span><span class="sxs-lookup"><span data-stu-id="7b066-306">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="7b066-307">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="7b066-307">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="7b066-308">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-308">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7b066-309">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="7b066-309">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="7b066-310">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7b066-310">contoso.com/a</span></span>
  - <span data-ttu-id="7b066-311">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="7b066-311">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="7b066-312">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="7b066-312">contoso.com/ab</span></span>
  - <span data-ttu-id="7b066-313">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="7b066-313">contoso.com/b</span></span>
  - <span data-ttu-id="7b066-314">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="7b066-314">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="7b066-315">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="7b066-315">contoso.com/ba</span></span>

- <span data-ttu-id="7b066-316">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-316">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="7b066-317">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="7b066-317">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="7b066-318">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="7b066-318">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="7b066-319">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-319">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7b066-320">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="7b066-320">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="7b066-321">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="7b066-321">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="7b066-322">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7b066-322">www.contoso.com/a</span></span>
  - <span data-ttu-id="7b066-323">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="7b066-323">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="7b066-324">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="7b066-324">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="7b066-325">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="7b066-325">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="7b066-326">Cenário: bloco esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="7b066-326">Scenario: Left and right tilde</span></span>

<span data-ttu-id="7b066-327">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="7b066-327">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="7b066-328">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-328">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7b066-329">contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-329">contoso.com</span></span>
  - <span data-ttu-id="7b066-330">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="7b066-330">contoso.com/a</span></span>
  - <span data-ttu-id="7b066-331">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-331">www.contoso.com</span></span>
  - <span data-ttu-id="7b066-332">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="7b066-332">www.contoso.com/b</span></span>
  - <span data-ttu-id="7b066-333">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-333">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="7b066-334">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="7b066-334">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7b066-335">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-335">123contoso.com</span></span>
  - <span data-ttu-id="7b066-336">contoso.org</span><span class="sxs-lookup"><span data-stu-id="7b066-336">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="7b066-337">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="7b066-337">Scenario: IP address</span></span>

<span data-ttu-id="7b066-338">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="7b066-338">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="7b066-339">**Permitir match** e **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="7b066-339">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="7b066-340">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="7b066-340">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="7b066-341">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="7b066-341">1.2.3.4/a</span></span>
  - <span data-ttu-id="7b066-342">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="7b066-342">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="7b066-343">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="7b066-343">IP address with right wildcard</span></span>

<span data-ttu-id="7b066-344">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="7b066-344">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="7b066-345">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="7b066-345">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="7b066-346">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="7b066-346">1.2.3.4/b</span></span>
  - <span data-ttu-id="7b066-347">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="7b066-347">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="7b066-348">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="7b066-348">Examples of invalid entries</span></span>

<span data-ttu-id="7b066-349">As seguintes entradas são inválidas:</span><span class="sxs-lookup"><span data-stu-id="7b066-349">The following entries are invalid:</span></span>

- <span data-ttu-id="7b066-350">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="7b066-350">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="7b066-351">contoso</span><span class="sxs-lookup"><span data-stu-id="7b066-351">contoso</span></span>
  - <span data-ttu-id="7b066-352">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="7b066-352">\*.contoso.\*</span></span>
  - <span data-ttu-id="7b066-353">\*.com</span><span class="sxs-lookup"><span data-stu-id="7b066-353">\*.com</span></span>
  - <span data-ttu-id="7b066-354">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="7b066-354">\*.pdf</span></span>

- <span data-ttu-id="7b066-355">**Caractere curinga em texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="7b066-355">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="7b066-356">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="7b066-356">\*contoso.com</span></span>
  - <span data-ttu-id="7b066-357">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="7b066-357">contoso.com\*</span></span>
  - <span data-ttu-id="7b066-358">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="7b066-358">\*1.2.3.4</span></span>
  - <span data-ttu-id="7b066-359">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="7b066-359">1.2.3.4\*</span></span>
  - <span data-ttu-id="7b066-360">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="7b066-360">contoso.com/a\*</span></span>
  - <span data-ttu-id="7b066-361">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="7b066-361">contoso.com/ab\*</span></span>

- <span data-ttu-id="7b066-362">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="7b066-362">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="7b066-363">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="7b066-363">contoso.com:443</span></span>
  - <span data-ttu-id="7b066-364">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="7b066-364">abc.contoso.com:25</span></span>

- <span data-ttu-id="7b066-365">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="7b066-365">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="7b066-366">\*.\*</span><span class="sxs-lookup"><span data-stu-id="7b066-366">\*.\*</span></span>

- <span data-ttu-id="7b066-367">**Caracteres curinga intermediários**:</span><span class="sxs-lookup"><span data-stu-id="7b066-367">**Middle wildcards**:</span></span>

  - <span data-ttu-id="7b066-368">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="7b066-368">conto\*so.com</span></span>
  - <span data-ttu-id="7b066-369">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="7b066-369">conto~so.com</span></span>

- <span data-ttu-id="7b066-370">**Caracteres curinga duplos**</span><span class="sxs-lookup"><span data-stu-id="7b066-370">**Double wildcards**</span></span>

  - <span data-ttu-id="7b066-371">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="7b066-371">contoso.com/\*\*</span></span>
  - <span data-ttu-id="7b066-372">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="7b066-372">contoso.com/\*/\*</span></span>