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
ms.openlocfilehash: 270e38d65857de2f4d06460fb3bb77f72a165ecf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538958"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-103">Gerenciar a lista de Permissões/Bloqueios do Locatário</span><span class="sxs-lookup"><span data-stu-id="c6ee7-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c6ee7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-104">**Applies to**</span></span>
- [<span data-ttu-id="c6ee7-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c6ee7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c6ee7-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c6ee7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c6ee7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c6ee7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="c6ee7-108">Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="c6ee7-109">Se a sua organização não tiver os recursos de spoof conforme descrito neste artigo, consulte a experiência de gerenciamento de spoof mais antiga em Gerenciar envios com spoofed usando a política de inteligência de spoof e informações de inteligência de [spoof no EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="c6ee7-110">Não é possível configurar **a** URL ou os itens de arquivo permitidos na Lista de Locatários Permitidos/Bloqueados no momento.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="c6ee7-111">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, talvez você não concorde com o veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="c6ee7-112">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="c6ee7-113">A Lista de Locatários de & de Conformidade oferece uma maneira de substituir manualmente os Microsoft 365 de filtragem.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="c6ee7-114">A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="c6ee7-115">Você pode especificar os seguintes tipos de substituições:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="c6ee7-116">URLs a bloquear.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-116">URLs to block.</span></span>
- <span data-ttu-id="c6ee7-117">Arquivos a bloquear.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-117">Files to block.</span></span>
- <span data-ttu-id="c6ee7-118">Domínios de remetente de email em massa para permitir.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-118">Bulk mail sender domains to allow.</span></span> <span data-ttu-id="c6ee7-119">Para obter mais informações sobre email em massa, o nível de confiança em massa (BCL) e a filtragem de emails em massa por políticas anti-spam, consulte [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-119">For more information about bulk mail, the bulk confidence level (BCL), and bulk mail filtering by anti-spam policies, see [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>
- <span data-ttu-id="c6ee7-120">Envios com spoofed para permitir ou bloquear.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-120">Spoofed senders to allow or block.</span></span> <span data-ttu-id="c6ee7-121">Se você substituir o veredito de permitir ou bloquear no insight de inteligência de spoof , o remetente [spoofed](learn-about-spoof-intelligence.md)se tornará uma entrada manual de permitir ou bloquear que só aparece na guia **Spoof** na Lista de Locatários De Permitir/Bloquear.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-121">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="c6ee7-122">Você também pode criar manualmente entradas de permitir ou bloquear para os envios de spoofed aqui antes que eles são detectados pela inteligência spoof.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-122">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="c6ee7-123">Este artigo descreve como configurar entradas na Lista de Permitir/Bloquear Locatários no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-123">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c6ee7-124">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c6ee7-124">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c6ee7-125">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-125">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c6ee7-126">Para ir diretamente para a página **Lista de Locatários Permitir/Bloquear,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-126">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="c6ee7-127">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-127">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="c6ee7-128">Para encontrar o valor de hash SHA256 de um arquivo Windows, execute o seguinte comando em um Prompt de Comando:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-128">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="c6ee7-129">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-129">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="c6ee7-130">Os valores de hash perceptual (pHash) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-130">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="c6ee7-131">Os valores de URL disponíveis são descritos na sintaxe de URL da seção [Lista de Locatários/Bloqueios](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-131">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="c6ee7-132">A Lista de Permitir/Bloquear Locatários permite no máximo 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-132">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="c6ee7-133">O número máximo de caracteres para cada entrada é:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-133">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="c6ee7-134">Hashes de arquivo = 64</span><span class="sxs-lookup"><span data-stu-id="c6ee7-134">File hashes = 64</span></span>
  - <span data-ttu-id="c6ee7-135">URL = 250</span><span class="sxs-lookup"><span data-stu-id="c6ee7-135">URL = 250</span></span>

- <span data-ttu-id="c6ee7-136">Uma entrada deve estar ativa dentro de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-136">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="c6ee7-137">Por padrão, as entradas na Lista de Locatários Permitir/Bloquear expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-137">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="c6ee7-138">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-138">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="c6ee7-139">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-139">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c6ee7-140">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-140">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c6ee7-141">Você precisa de permissões em Exchange Online  antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-141">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c6ee7-142">**URLs, arquivos e permitir envios em massa:**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-142">**URLs, files, and allow bulk senders**:</span></span>
    - <span data-ttu-id="c6ee7-143">Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. </span><span class="sxs-lookup"><span data-stu-id="c6ee7-143">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="c6ee7-144">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-144">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="c6ee7-145">**Spoofing**: uma das seguintes combinações:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-145">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="c6ee7-146">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-146">**Organization Management**</span></span>
    - <span data-ttu-id="c6ee7-147">**Administrador de Segurança** <u>e</u> **Configuração somente exibição** ou **Gerenciamento de organização somente exibição.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-147">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="c6ee7-148">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-148">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="c6ee7-149">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-149">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c6ee7-150">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-150">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="c6ee7-151">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-151">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-152">Use o Centro de Conformidade & segurança para criar entradas de URL de bloqueio na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-152">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c6ee7-153">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c6ee7-154">Na página Lista de Locatários **Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-154">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="c6ee7-155">No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-155">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c6ee7-156">**Adicionar URLs para bloquear**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-156">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="c6ee7-157">Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-157">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="c6ee7-158">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-158">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c6ee7-159">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="c6ee7-159">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="c6ee7-160">ou</span><span class="sxs-lookup"><span data-stu-id="c6ee7-160">or</span></span>

     - <span data-ttu-id="c6ee7-161">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-161">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="c6ee7-163">.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-163">.</span></span>

   - <span data-ttu-id="c6ee7-164">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-164">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c6ee7-165">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-165">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-166">Use o Centro de Conformidade & segurança para criar entradas de arquivo de bloqueio na lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="c6ee7-166">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c6ee7-167">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-167">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c6ee7-168">Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Arquivos** e clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-168">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="c6ee7-169">No menu **Adicionar arquivos para bloquear o** sobrevoo que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-169">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c6ee7-170">**Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-170">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c6ee7-171">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-171">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c6ee7-172">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="c6ee7-172">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c6ee7-173">ou</span><span class="sxs-lookup"><span data-stu-id="c6ee7-173">or</span></span>

     - <span data-ttu-id="c6ee7-174">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-174">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="c6ee7-176">.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-176">.</span></span>

   - <span data-ttu-id="c6ee7-177">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-177">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c6ee7-178">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-178">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-179">Use o Centro de Conformidade & segurança para criar entradas de domínio de remetente de email em massa na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-179">Use the Security & Compliance Center to create allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c6ee7-180">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-180">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c6ee7-181">Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia Domínios do Remetente para bypass **BCL** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-181">On the **Tenant Allow/Block List** page, select the **Sender domains for BCL bypass** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="c6ee7-182">No **flyout Adicionar domínio de remetente para BCL** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-182">In the **Add sender domain for BCL bypass** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c6ee7-183">**Adicionar domínios de remetente para** bypass BCL : Insira um domínio de origem de um bom email em massa por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-183">**Add sender domains for BCL bypass**: Enter one source domain of good bulk mail per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c6ee7-184">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-184">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c6ee7-185">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="c6ee7-185">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c6ee7-186">ou</span><span class="sxs-lookup"><span data-stu-id="c6ee7-186">or</span></span>

     - <span data-ttu-id="c6ee7-187">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-187">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="c6ee7-189">.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-189">.</span></span>

4. <span data-ttu-id="c6ee7-190">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-190">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-191">Use o Centro de Conformidade & segurança para criar entradas de remetentes que permitem ou bloqueiem spoofed na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-191">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-192">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-192">**Notes**:</span></span>

- <span data-ttu-id="c6ee7-193">Somente a _combinação_ do usuário  com a infraestrutura de envio, conforme definido no par de domínios, é especificamente permitida ou bloqueada da spoofing.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-193">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="c6ee7-194">Quando você configura uma entrada de permitir ou bloquear para um par de domínios, as mensagens desse par de domínios não aparecem mais no insight de inteligência falsa.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-194">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="c6ee7-195">As entradas para os envios com spoofed nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-195">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="c6ee7-196">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c6ee7-197">Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Spoofing** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-197">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="c6ee7-198">No **flyout Adicionar novos pares de** domínio que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-198">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c6ee7-199">**Adicionar novos pares de domínio com caracteres curinga**: Insira um par de domínios por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-199">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="c6ee7-200">Para obter detalhes sobre a sintaxe para entradas de remetentes com spoofed, consulte a sintaxe de par de domínios para entradas de remetentes com [spoofed](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) na seção Lista de Locatários Permitir/Bloquear mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-200">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="c6ee7-201">**Tipo de spoof**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-201">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="c6ee7-202">**Interno**: o remetente spoofed está em um domínio que pertence à sua organização [(um domínio aceito](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-202">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="c6ee7-203">**Externo**: o remetente spoofed está em um domínio externo.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-203">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="c6ee7-204">**Ação**: Selecione **Permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-204">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="c6ee7-205">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-205">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-206">Use o Centro de Conformidade & segurança para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-206">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c6ee7-207">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-207">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c6ee7-208">Selecione a guia que você deseja.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-208">Select the tab you want.</span></span> <span data-ttu-id="c6ee7-209">As colunas disponíveis dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-209">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="c6ee7-210">**URLs**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-210">**URLs**:</span></span>
     - <span data-ttu-id="c6ee7-211">**Valor**: A URL.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-211">**Value**: The URL.</span></span>
     - <span data-ttu-id="c6ee7-212">**Ação**: o valor **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-212">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="c6ee7-213">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-213">**Last updated date**</span></span>
     - <span data-ttu-id="c6ee7-214">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-214">**Expiration date**</span></span>
     - <span data-ttu-id="c6ee7-215">**Observação**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-215">**Note**</span></span>

   - <span data-ttu-id="c6ee7-216">**Files**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-216">**Files**</span></span>
     - <span data-ttu-id="c6ee7-217">**Valor**: o hash do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-217">**Value**: The file hash.</span></span>
     - <span data-ttu-id="c6ee7-218">**Ação**: o valor **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-218">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="c6ee7-219">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-219">**Last updated date**</span></span>
     - <span data-ttu-id="c6ee7-220">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-220">**Expiration date**</span></span>
     - <span data-ttu-id="c6ee7-221">**Observação**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-221">**Note**</span></span>

   - <span data-ttu-id="c6ee7-222">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-222">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="c6ee7-223">**Valor**: O domínio do remetente de email em massa.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-223">**Value**: The bulk mail sender's domain.</span></span>
     - <span data-ttu-id="c6ee7-224">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-224">**Last updated date**</span></span>
     - <span data-ttu-id="c6ee7-225">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-225">**Expiration date**</span></span>

   - <span data-ttu-id="c6ee7-226">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-226">**Spoofing**</span></span>
     - <span data-ttu-id="c6ee7-227">**Usuário com spoofed**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-227">**Spoofed user**</span></span>
     - <span data-ttu-id="c6ee7-228">**Enviando infraestrutura**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-228">**Sending infrastructure**</span></span>
     - <span data-ttu-id="c6ee7-229">**Tipo de spoof**: o valor **Interno** ou **Externo**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-229">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="c6ee7-230">**Ação**: o valor **Bloquear** ou **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-230">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="c6ee7-231">Você pode clicar em um título de coluna para classificar em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-231">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="c6ee7-232">Você pode clicar **em Grupo** para agrupar os resultados.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-232">You can click **Group** to group the results.</span></span> <span data-ttu-id="c6ee7-233">Os valores disponíveis dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-233">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="c6ee7-234">**URLs**: Você pode agrupar os resultados por **Ação**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-234">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="c6ee7-235">**Arquivos**: Você pode agrupar os resultados por **Ação**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-235">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="c6ee7-236">**Domínios de remetente para bypass BCL**: **O** grupo não está disponível nesta guia.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-236">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="c6ee7-237">**Spoofing**: Você pode agrupar os resultados por **ação** ou tipo **Spoof**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-237">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="c6ee7-238">Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-238">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="c6ee7-239">Quando terminar, clique em Limpar o **ícone de pesquisa** Limpar pesquisa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-239">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="c6ee7-240">Clique **em Filtrar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-240">Click **Filter** to filter the results.</span></span> <span data-ttu-id="c6ee7-241">Os valores disponíveis no flyout **Filter** que aparece dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-241">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="c6ee7-242">**URLs**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-242">**URLs**</span></span>
     - <span data-ttu-id="c6ee7-243">**Action**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-243">**Action**</span></span>
     - <span data-ttu-id="c6ee7-244">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-244">**Never expire**</span></span>
     - <span data-ttu-id="c6ee7-245">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-245">**Last updated date**</span></span>
     - <span data-ttu-id="c6ee7-246">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-246">**Expiration date**</span></span>

   - <span data-ttu-id="c6ee7-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-247">**Files**</span></span>
     - <span data-ttu-id="c6ee7-248">**Action**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-248">**Action**</span></span>
     - <span data-ttu-id="c6ee7-249">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-249">**Never expire**</span></span>
     - <span data-ttu-id="c6ee7-250">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-250">**Last updated date**</span></span>
     - <span data-ttu-id="c6ee7-251">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-251">**Expiration date**</span></span>

   - <span data-ttu-id="c6ee7-252">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-252">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="c6ee7-253">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-253">**Never expire**</span></span>
     - <span data-ttu-id="c6ee7-254">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-254">**Last updated date**</span></span>
     - <span data-ttu-id="c6ee7-255">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-255">**Expiration date**</span></span>

   - <span data-ttu-id="c6ee7-256">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-256">**Spoofing**</span></span>
     - <span data-ttu-id="c6ee7-257">**Action**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-257">**Action**</span></span>
     - <span data-ttu-id="c6ee7-258">**Tipo de spoof**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-258">**Spoof type**</span></span>

   <span data-ttu-id="c6ee7-259">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-259">When you're finished, click **Apply**.</span></span> <span data-ttu-id="c6ee7-260">Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-260">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-261">Use o Centro de Conformidade & segurança para modificar entradas na lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="c6ee7-261">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c6ee7-262">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-262">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c6ee7-263">Selecione a guia que contém o tipo de entrada que você deseja modificar:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-263">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="c6ee7-264">**URLs**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-264">**URLs**</span></span>
   - <span data-ttu-id="c6ee7-265">**Files**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-265">**Files**</span></span>
   - <span data-ttu-id="c6ee7-266">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-266">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="c6ee7-267">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-267">**Spoofing**</span></span>

3. <span data-ttu-id="c6ee7-268">Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) editar.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-268">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="c6ee7-269">Os valores que você pode modificar no sobrevoo que aparece dependem da guia selecionada na etapa anterior:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-269">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="c6ee7-270">**URLs**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-270">**URLs**</span></span>
     - <span data-ttu-id="c6ee7-271">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-271">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="c6ee7-272">**Observação opcional**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-272">**Optional note**</span></span>

   - <span data-ttu-id="c6ee7-273">**Files**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-273">**Files**</span></span>
     - <span data-ttu-id="c6ee7-274">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-274">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="c6ee7-275">**Observação opcional**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-275">**Optional note**</span></span>

   - <span data-ttu-id="c6ee7-276">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-276">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="c6ee7-277">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-277">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="c6ee7-278">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-278">**Spoofing**</span></span>
     - <span data-ttu-id="c6ee7-279">**Ação**: você pode alterar o valor para **Permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-279">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="c6ee7-280">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-280">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-281">Use o Centro de Conformidade & segurança para remover entradas da lista de locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-281">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c6ee7-282">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-282">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c6ee7-283">Selecione a guia que contém o tipo de entrada que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-283">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="c6ee7-284">**URLs**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-284">**URLs**</span></span>
   - <span data-ttu-id="c6ee7-285">**Files**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-285">**Files**</span></span>
   - <span data-ttu-id="c6ee7-286">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-286">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="c6ee7-287">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-287">**Spoofing**</span></span>

3. <span data-ttu-id="c6ee7-288">Selecione a entrada que você deseja remover e clique em **Excluir** ![ ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-288">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="c6ee7-289">Na caixa de diálogo de aviso exibida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-289">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-290">Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-290">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-291">Use o PowerShell para adicionar entradas de arquivo de bloqueio ou URL à Lista de Locatários De Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-291">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-292">Para adicionar entradas de arquivo de bloqueio ou URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-292">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="c6ee7-293">Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-293">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="c6ee7-294">Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-294">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="c6ee7-295">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-295">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="c6ee7-296">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-296">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-bulk-mail-sender-domain-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-297">Use o PowerShell para adicionar entradas de domínio de remetente de email em massa à Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-297">Use PowerShell to add allow bulk mail sender domain entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-298">Para adicionar entradas de domínio de remetente de email em massa na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-298">To add allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType BulkSender -Block:$false -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="c6ee7-299">Este exemplo adiciona uma entrada de remetente em massa permitida para o domínio especificado que nunca expira.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-299">This example adds an allowed bulk sender entry for the specified domain that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType BulkSender -Block:$false -Entries contosodailydeals.com
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="c6ee7-300">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-300">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-301">Use o PowerShell para adicionar entradas de remetentes com spoofed ou de autorização ou bloqueio à Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-301">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-302">Para adicionar entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-302">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="c6ee7-303">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-303">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-304">Usar o PowerShell para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-304">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-305">Para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-305">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="c6ee7-306">Este exemplo retorna informações para o valor de hash de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-306">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="c6ee7-307">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-307">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="c6ee7-308">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-308">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-309">Use o PowerShell para exibir permitir entradas de domínio de remetente de email em massa na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-309">Use PowerShell to view allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-310">Para exibir as entradas de domínio de remetente de email em massa na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-310">To view allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender [-Entry <BulkSenderDomainValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="c6ee7-311">Este exemplo retorna todos os domínios permitidos de remetente de email em massa.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-311">This example returns all allowed bulk mail sender domains.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender
```

<span data-ttu-id="c6ee7-312">Este exemplo retorna informações para o domínio de remetente em massa especificado.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-312">This example returns information for the specified bulk sender domain.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "contosodailydeals.com"
```

<span data-ttu-id="c6ee7-313">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-313">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-314">Use o PowerShell para exibir as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-314">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-315">Para exibir entradas de remetentes com spoofed na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-315">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="c6ee7-316">Este exemplo retorna todas as entradas de remetentes com spoofed na Lista de Locatários de Permitir/Bloquear.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-316">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="c6ee7-317">Este exemplo retorna todas as entradas de remetentes com spoofed que são internas.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-317">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="c6ee7-318">Este exemplo retorna todas as entradas de remetentes com spoofed bloqueados que são externas.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-318">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="c6ee7-319">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-319">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-320">Usar o PowerShell para modificar as entradas de arquivo de bloqueio e URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-320">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-321">Para modificar entradas de arquivo de bloqueio e URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-321">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="c6ee7-322">Este exemplo altera a data de expiração da entrada da URL de bloco especificada.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-322">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="c6ee7-323">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-323">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-bulk-mail-sender-domain-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-324">Usar o PowerShell para modificar permitir entradas de domínio de remetente de email em massa na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-324">Use PowerShell to modify allow bulk mail sender domain entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-325">Para modificar permitir entradas de domínio de remetente de email em massa na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-325">To modify allow bulk mail sender domain entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType BulkSender -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="c6ee7-326">Este exemplo altera a expiração da entrada de domínio de remetente de email em massa especificada para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-326">This example changes the expiration of the specified allow bulk mail sender domain entry to never expire.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType BulkSender -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -NoExpiration
```

<span data-ttu-id="c6ee7-327">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-327">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-328">Use o PowerShell para modificar as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-328">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-329">Para modificar entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-329">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="c6ee7-330">Este exemplo altera a entrada de remetentes com spoofed de permitir o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-330">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="c6ee7-331">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-331">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-bulk-mail-sender-domain-file-and-domain-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-332">Use o PowerShell para remover o domínio, o arquivo e as entradas de domínio do remetente de email em massa da Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-332">Use PowerShell to remove bulk mail sender domain, file, and domain entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-333">Para remover permitir entradas de domínio de remetente de email em massa, bloquear entradas de arquivo e bloquear entradas de URL da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-333">To remove allow bulk mail sender domain entries, block file entries, and block URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <BulkSender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c6ee7-334">Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-334">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="c6ee7-335">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-335">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-336">Use o PowerShell para remover entradas de remetentes com spoofed ou de permitir ou bloquear da Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-336">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-337">Para remover as entradas de remetente de spoof ou de permitir ou bloquear da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-337">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c6ee7-338">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-338">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-339">Sintaxe de URL para a Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-339">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="c6ee7-340">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-340">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="c6ee7-341">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-341">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="c6ee7-342">Unicode não tem suporte, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-342">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="c6ee7-343">Os nomes de host são permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-343">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="c6ee7-344">O nomedo host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-344">The hostname contains a period.</span></span>
  - <span data-ttu-id="c6ee7-345">Há pelo menos um caractere à esquerda do período.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-345">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="c6ee7-346">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-346">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="c6ee7-347">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-347">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="c6ee7-348">Subpaths não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-348">Subpaths are not implied.</span></span>

  <span data-ttu-id="c6ee7-349">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-349">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="c6ee7-350">Os caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-350">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="c6ee7-351">Um curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-351">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="c6ee7-352">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-352">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="c6ee7-353">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-353">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="c6ee7-354">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-354">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="c6ee7-355">Todos os subcamadas não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-355">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="c6ee7-356">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-356">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="c6ee7-357">`*.com*` é inválido (não é um domínio resolvêvel e o caractere curinga direito não segue uma barra de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-357">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="c6ee7-358">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-358">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="c6ee7-359">O caractere tilde (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-359">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="c6ee7-360">Um bloco esquerdo implica um domínio e todos os subdomas.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-360">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="c6ee7-361">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-361">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="c6ee7-362">As entradas de URL que contêm protocolos (por exemplo, , , ou ) falharão, pois as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-362">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="c6ee7-363">Um nome de usuário ou senha não é suportado ou necessário.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-363">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="c6ee7-364">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-364">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="c6ee7-365">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-365">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="c6ee7-366">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="c6ee7-366">URL entry scenarios</span></span>

<span data-ttu-id="c6ee7-367">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-367">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="c6ee7-368">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="c6ee7-368">Scenario: No wildcards</span></span>

<span data-ttu-id="c6ee7-369">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-369">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="c6ee7-370">**Permitir match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-370">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="c6ee7-371">**Permitir não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-371">**Allow not matched**:</span></span>

  - <span data-ttu-id="c6ee7-372">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-372">abc-contoso.com</span></span>
  - <span data-ttu-id="c6ee7-373">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-373">contoso.com/a</span></span>
  - <span data-ttu-id="c6ee7-374">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-374">payroll.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-375">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-375">test.com/contoso.com</span></span>
  - <span data-ttu-id="c6ee7-376">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-376">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c6ee7-377">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-377">www.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-378">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-378">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c6ee7-379">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-379">**Block match**:</span></span>

  - <span data-ttu-id="c6ee7-380">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-380">contoso.com</span></span>
  - <span data-ttu-id="c6ee7-381">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-381">contoso.com/a</span></span>
  - <span data-ttu-id="c6ee7-382">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-382">payroll.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-383">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-383">test.com/contoso.com</span></span>
  - <span data-ttu-id="c6ee7-384">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-384">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c6ee7-385">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-385">www.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-386">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-386">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c6ee7-387">**Bloquear não corresponder :** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-387">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="c6ee7-388">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="c6ee7-388">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="c6ee7-389">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-389">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="c6ee7-390">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c6ee7-391">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-391">www.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-392">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-392">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c6ee7-393">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-393">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c6ee7-394">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-394">123contoso.com</span></span>
  - <span data-ttu-id="c6ee7-395">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-395">contoso.com</span></span>
  - <span data-ttu-id="c6ee7-396">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-396">test.com/contoso.com</span></span>
  - <span data-ttu-id="c6ee7-397">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c6ee7-397">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="c6ee7-398">Cenário: curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="c6ee7-398">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="c6ee7-399">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-399">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="c6ee7-400">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-400">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c6ee7-401">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="c6ee7-401">contoso.com/a/b</span></span>
  - <span data-ttu-id="c6ee7-402">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c6ee7-402">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c6ee7-403">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-403">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="c6ee7-404">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-404">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c6ee7-405">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-405">contoso.com</span></span>
  - <span data-ttu-id="c6ee7-406">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-406">contoso.com/a</span></span>
  - <span data-ttu-id="c6ee7-407">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-407">www.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-408">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-408">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="c6ee7-409">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="c6ee7-409">Scenario: Left tilde</span></span>

<span data-ttu-id="c6ee7-410">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-410">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="c6ee7-411">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-411">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c6ee7-412">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-412">contoso.com</span></span>
  - <span data-ttu-id="c6ee7-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-413">www.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-414">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-414">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c6ee7-415">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-415">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c6ee7-416">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-416">123contoso.com</span></span>
  - <span data-ttu-id="c6ee7-417">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c6ee7-417">contoso.com/abc</span></span>
  - <span data-ttu-id="c6ee7-418">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c6ee7-418">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="c6ee7-419">Cenário: sufixo curinga correto</span><span class="sxs-lookup"><span data-stu-id="c6ee7-419">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="c6ee7-420">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-420">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="c6ee7-421">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-421">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c6ee7-422">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-422">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="c6ee7-423">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-423">contoso.com/a</span></span>
  - <span data-ttu-id="c6ee7-424">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c6ee7-424">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c6ee7-425">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c6ee7-425">contoso.com/ab</span></span>
  - <span data-ttu-id="c6ee7-426">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c6ee7-426">contoso.com/b</span></span>
  - <span data-ttu-id="c6ee7-427">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c6ee7-427">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c6ee7-428">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c6ee7-428">contoso.com/ba</span></span>

- <span data-ttu-id="c6ee7-429">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-429">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="c6ee7-430">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="c6ee7-430">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="c6ee7-431">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-431">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="c6ee7-432">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-432">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c6ee7-433">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c6ee7-433">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="c6ee7-434">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c6ee7-434">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c6ee7-435">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-435">www.contoso.com/a</span></span>
  - <span data-ttu-id="c6ee7-436">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c6ee7-436">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c6ee7-437">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c6ee7-437">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="c6ee7-438">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c6ee7-438">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="c6ee7-439">Cenário: bloco esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="c6ee7-439">Scenario: Left and right tilde</span></span>

<span data-ttu-id="c6ee7-440">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-440">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="c6ee7-441">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-441">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c6ee7-442">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-442">contoso.com</span></span>
  - <span data-ttu-id="c6ee7-443">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-443">contoso.com/a</span></span>
  - <span data-ttu-id="c6ee7-444">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-444">www.contoso.com</span></span>
  - <span data-ttu-id="c6ee7-445">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c6ee7-445">www.contoso.com/b</span></span>
  - <span data-ttu-id="c6ee7-446">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-446">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c6ee7-447">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-447">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c6ee7-448">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-448">123contoso.com</span></span>
  - <span data-ttu-id="c6ee7-449">contoso.org</span><span class="sxs-lookup"><span data-stu-id="c6ee7-449">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="c6ee7-450">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="c6ee7-450">Scenario: IP address</span></span>

<span data-ttu-id="c6ee7-451">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-451">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="c6ee7-452">**Permitir match** e **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c6ee7-452">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="c6ee7-453">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-453">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c6ee7-454">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-454">1.2.3.4/a</span></span>
  - <span data-ttu-id="c6ee7-455">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c6ee7-455">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="c6ee7-456">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="c6ee7-456">IP address with right wildcard</span></span>

<span data-ttu-id="c6ee7-457">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="c6ee7-457">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="c6ee7-458">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-458">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c6ee7-459">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="c6ee7-459">1.2.3.4/b</span></span>
  - <span data-ttu-id="c6ee7-460">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="c6ee7-460">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="c6ee7-461">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="c6ee7-461">Examples of invalid entries</span></span>

<span data-ttu-id="c6ee7-462">As seguintes entradas são inválidas:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-462">The following entries are invalid:</span></span>

- <span data-ttu-id="c6ee7-463">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-463">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="c6ee7-464">contoso</span><span class="sxs-lookup"><span data-stu-id="c6ee7-464">contoso</span></span>
  - <span data-ttu-id="c6ee7-465">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-465">\*.contoso.\*</span></span>
  - <span data-ttu-id="c6ee7-466">\*.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-466">\*.com</span></span>
  - <span data-ttu-id="c6ee7-467">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="c6ee7-467">\*.pdf</span></span>

- <span data-ttu-id="c6ee7-468">**Caractere curinga em texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-468">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="c6ee7-469">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-469">\*contoso.com</span></span>
  - <span data-ttu-id="c6ee7-470">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-470">contoso.com\*</span></span>
  - <span data-ttu-id="c6ee7-471">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c6ee7-471">\*1.2.3.4</span></span>
  - <span data-ttu-id="c6ee7-472">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-472">1.2.3.4\*</span></span>
  - <span data-ttu-id="c6ee7-473">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-473">contoso.com/a\*</span></span>
  - <span data-ttu-id="c6ee7-474">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-474">contoso.com/ab\*</span></span>

- <span data-ttu-id="c6ee7-475">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-475">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="c6ee7-476">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="c6ee7-476">contoso.com:443</span></span>
  - <span data-ttu-id="c6ee7-477">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="c6ee7-477">abc.contoso.com:25</span></span>

- <span data-ttu-id="c6ee7-478">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-478">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="c6ee7-479">\*.\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-479">\*.\*</span></span>

- <span data-ttu-id="c6ee7-480">**Caracteres curinga intermediários**:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-480">**Middle wildcards**:</span></span>

  - <span data-ttu-id="c6ee7-481">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-481">conto\*so.com</span></span>
  - <span data-ttu-id="c6ee7-482">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-482">conto~so.com</span></span>

- <span data-ttu-id="c6ee7-483">**Caracteres curinga duplos**</span><span class="sxs-lookup"><span data-stu-id="c6ee7-483">**Double wildcards**</span></span>

  - <span data-ttu-id="c6ee7-484">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-484">contoso.com/\*\*</span></span>
  - <span data-ttu-id="c6ee7-485">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="c6ee7-485">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c6ee7-486">Sintaxe de par de domínios para entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="c6ee7-486">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c6ee7-487">Um par de domínios para um remetente com spoofed na Lista de Locatários de Permitir/Bloquear usa a seguinte sintaxe: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="c6ee7-487">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="c6ee7-488">**Usuário com spoofed**: esse valor envolve o endereço de email do usuário que é exibido na caixa **De** em clientes de email.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-488">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="c6ee7-489">Esse endereço também é conhecido como `5322.From` endereço.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-489">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="c6ee7-490">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-490">Valid values include:</span></span>
  - <span data-ttu-id="c6ee7-491">Um endereço de email individual (por exemplo, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-491">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="c6ee7-492">Um domínio de email (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-492">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="c6ee7-493">O caractere curinga (por exemplo, \* ).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-493">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="c6ee7-494">**Infraestrutura de** envio : esse valor indica a origem das mensagens do usuário espouado.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-494">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="c6ee7-495">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-495">Valid values include:</span></span>
  - <span data-ttu-id="c6ee7-496">O domínio encontrado em um registro DNS reverso (registro PTR) do endereço IP do servidor de email de origem (por exemplo, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-496">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="c6ee7-497">Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="c6ee7-497">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="c6ee7-498">Aqui estão alguns exemplos de pares de domínio válidos para identificar os envios com spoofed:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-498">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="c6ee7-499">Adicionar um par de domínios  só permite ou bloqueia a combinação do usuário e da *infraestrutura* de envio.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-499">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="c6ee7-500">Ele não permite emails do usuário com spoofed de qualquer origem, nem permite emails da fonte de infraestrutura de envio para qualquer usuário com spoofed.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-500">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span>

<span data-ttu-id="c6ee7-501">Por exemplo, você adiciona uma entrada de autorização para o seguinte par de domínio:</span><span class="sxs-lookup"><span data-stu-id="c6ee7-501">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="c6ee7-502">**Domínio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-502">**Domain**: gmail.com</span></span>
- <span data-ttu-id="c6ee7-503">**Infraestrutura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="c6ee7-503">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="c6ee7-504">Somente as mensagens desse domínio *e o* par de infraestrutura de envio podem ser falsas.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-504">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="c6ee7-505">Outros senders que tentam gmail.com não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-505">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="c6ee7-506">As mensagens de senders em outros domínios provenientes tms.mx.com são verificadas por inteligência falsa.</span><span class="sxs-lookup"><span data-stu-id="c6ee7-506">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
