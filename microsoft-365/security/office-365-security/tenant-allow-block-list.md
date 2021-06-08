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
ms.openlocfilehash: 12139708fc5cde133819713fd7185435e594a1a9
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809174"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="78940-103">Gerenciar a lista de Permissões/Bloqueios do Locatário</span><span class="sxs-lookup"><span data-stu-id="78940-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="78940-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="78940-104">**Applies to**</span></span>
- [<span data-ttu-id="78940-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="78940-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="78940-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="78940-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="78940-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="78940-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="78940-108">Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="78940-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="78940-109">Se a sua organização não tiver os recursos de spoof conforme descrito neste artigo, consulte a experiência de gerenciamento de spoof mais antiga em Gerenciar envios com spoofed usando a política de inteligência de spoof e informações de inteligência de [spoof no EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="78940-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="78940-110">Não é possível configurar **a** URL ou os itens de arquivo permitidos na Lista de Locatários Permitidos/Bloqueados no momento.</span><span class="sxs-lookup"><span data-stu-id="78940-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="78940-111">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, talvez você não concorde com o veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="78940-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="78940-112">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="78940-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="78940-113">A Lista de Locatários de & de Conformidade oferece uma maneira de substituir manualmente os Microsoft 365 de filtragem.</span><span class="sxs-lookup"><span data-stu-id="78940-113">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="78940-114">A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário.</span><span class="sxs-lookup"><span data-stu-id="78940-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="78940-115">Você pode especificar os seguintes tipos de substituições:</span><span class="sxs-lookup"><span data-stu-id="78940-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="78940-116">URLs a bloquear.</span><span class="sxs-lookup"><span data-stu-id="78940-116">URLs to block.</span></span>
- <span data-ttu-id="78940-117">Arquivos a bloquear.</span><span class="sxs-lookup"><span data-stu-id="78940-117">Files to block.</span></span>
- <span data-ttu-id="78940-118">Envios com spoofed para permitir ou bloquear.</span><span class="sxs-lookup"><span data-stu-id="78940-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="78940-119">Se você substituir o veredito de permitir ou bloquear no insight de inteligência de spoof , o remetente [spoofed](learn-about-spoof-intelligence.md)se tornará uma entrada manual de permitir ou bloquear que só aparece na guia **Spoof** na Lista de Locatários De Permitir/Bloquear.</span><span class="sxs-lookup"><span data-stu-id="78940-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="78940-120">Você também pode criar manualmente entradas de permitir ou bloquear para os envios de spoofed aqui antes que eles são detectados pela inteligência spoof.</span><span class="sxs-lookup"><span data-stu-id="78940-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="78940-121">Este artigo descreve como configurar entradas na Lista de Permitir/Bloquear Locatários no Centro de Conformidade de Segurança & ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).</span><span class="sxs-lookup"><span data-stu-id="78940-121">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="78940-122">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="78940-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="78940-123">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="78940-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="78940-124">Para ir diretamente para a página **Lista de Locatários Permitir/Bloquear,** use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="78940-124">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="78940-125">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="78940-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="78940-126">Para encontrar o valor de hash SHA256 de um arquivo Windows, execute o seguinte comando em um Prompt de Comando:</span><span class="sxs-lookup"><span data-stu-id="78940-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="78940-127">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="78940-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="78940-128">Os valores de hash perceptual (pHash) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="78940-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="78940-129">Os valores de URL disponíveis são descritos na sintaxe de URL da seção [Lista de Locatários/Bloqueios](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="78940-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="78940-130">A Lista de Permitir/Bloquear Locatários permite no máximo 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="78940-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="78940-131">O número máximo de caracteres para cada entrada é:</span><span class="sxs-lookup"><span data-stu-id="78940-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="78940-132">Hashes de arquivo = 64</span><span class="sxs-lookup"><span data-stu-id="78940-132">File hashes = 64</span></span>
  - <span data-ttu-id="78940-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="78940-133">URL = 250</span></span>

- <span data-ttu-id="78940-134">Uma entrada deve estar ativa dentro de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="78940-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="78940-135">Por padrão, as entradas na Lista de Locatários Permitir/Bloquear expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="78940-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="78940-136">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="78940-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="78940-137">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="78940-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="78940-138">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="78940-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="78940-139">Você precisa de permissões em Exchange Online  antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="78940-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="78940-140">**URLs e arquivos**:</span><span class="sxs-lookup"><span data-stu-id="78940-140">**URLs and files**:</span></span>
    - <span data-ttu-id="78940-141">Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. </span><span class="sxs-lookup"><span data-stu-id="78940-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="78940-142">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="78940-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="78940-143">**Spoofing**: uma das seguintes combinações:</span><span class="sxs-lookup"><span data-stu-id="78940-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="78940-144">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="78940-144">**Organization Management**</span></span>
    - <span data-ttu-id="78940-145">**Administrador de Segurança** <u>e</u> **Configuração somente exibição** ou **Gerenciamento de organização somente exibição.**</span><span class="sxs-lookup"><span data-stu-id="78940-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="78940-146">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="78940-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="78940-147">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="78940-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="78940-148">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="78940-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="78940-149">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="78940-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-150">Use o Centro de Conformidade & segurança para criar entradas de URL de bloqueio na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-150">Use the Security & Compliance Center to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="78940-151">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="78940-151">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="78940-152">Na página Lista de Locatários **Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="78940-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="78940-153">No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="78940-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="78940-154">**Adicionar URLs para bloquear**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="78940-154">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="78940-155">Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="78940-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="78940-156">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="78940-156">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="78940-157">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="78940-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="78940-158">ou</span><span class="sxs-lookup"><span data-stu-id="78940-158">or</span></span>

     - <span data-ttu-id="78940-159">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="78940-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="78940-161">.</span><span class="sxs-lookup"><span data-stu-id="78940-161">.</span></span>

   - <span data-ttu-id="78940-162">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="78940-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="78940-163">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="78940-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-164">Use o Centro de Conformidade & segurança para criar entradas de arquivo de bloqueio na lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="78940-164">Use the Security & Compliance Center to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="78940-165">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="78940-165">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="78940-166">Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Arquivos** e clique em **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="78940-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="78940-167">No menu **Adicionar arquivos para bloquear o** sobrevoo que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="78940-167">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="78940-168">**Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="78940-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="78940-169">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="78940-169">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="78940-170">Verifique se a configuração está desligada ( Alternar ) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="78940-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="78940-171">ou</span><span class="sxs-lookup"><span data-stu-id="78940-171">or</span></span>

     - <span data-ttu-id="78940-172">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="78940-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="78940-174">.</span><span class="sxs-lookup"><span data-stu-id="78940-174">.</span></span>

   - <span data-ttu-id="78940-175">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="78940-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="78940-176">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="78940-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-177">Use o Centro de Conformidade & segurança para criar entradas de remetentes que permitem ou bloqueiem spoofed na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-177">Use the Security & Compliance Center to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-178">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="78940-178">**Notes**:</span></span>

- <span data-ttu-id="78940-179">Somente a _combinação_ do usuário  com a infraestrutura de envio, conforme definido no par de domínios, é especificamente permitida ou bloqueada da spoofing.</span><span class="sxs-lookup"><span data-stu-id="78940-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="78940-180">Quando você configura uma entrada de permitir ou bloquear para um par de domínios, as mensagens desse par de domínios não aparecem mais no insight de inteligência falsa.</span><span class="sxs-lookup"><span data-stu-id="78940-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="78940-181">As entradas para os envios com spoofed nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="78940-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="78940-182">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="78940-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="78940-183">Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Spoofing** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="78940-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="78940-184">No **flyout Adicionar novos pares de** domínio que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="78940-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="78940-185">**Adicionar novos pares de domínio com caracteres curinga**: Insira um par de domínios por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="78940-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="78940-186">Para obter detalhes sobre a sintaxe para entradas de remetentes com spoofed, consulte a sintaxe de par de domínios para entradas de remetentes com [spoofed](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) na seção Lista de Locatários Permitir/Bloquear mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="78940-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>

   - <span data-ttu-id="78940-187">**Tipo de spoof**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="78940-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="78940-188">**Interno**: o remetente spoofed está em um domínio que pertence à sua organização [(um domínio aceito](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span><span class="sxs-lookup"><span data-stu-id="78940-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="78940-189">**Externo**: o remetente spoofed está em um domínio externo.</span><span class="sxs-lookup"><span data-stu-id="78940-189">**External**: The spoofed sender is in an external domain.</span></span>

   - <span data-ttu-id="78940-190">**Ação**: Selecione **Permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="78940-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="78940-191">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="78940-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-192">Use o Centro de Conformidade & segurança para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-192">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="78940-193">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="78940-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="78940-194">Selecione a guia que você deseja.</span><span class="sxs-lookup"><span data-stu-id="78940-194">Select the tab you want.</span></span> <span data-ttu-id="78940-195">As colunas disponíveis dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="78940-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="78940-196">**URLs**:</span><span class="sxs-lookup"><span data-stu-id="78940-196">**URLs**:</span></span>
     - <span data-ttu-id="78940-197">**Valor**: A URL.</span><span class="sxs-lookup"><span data-stu-id="78940-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="78940-198">**Ação**: o valor **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="78940-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="78940-199">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="78940-199">**Last updated date**</span></span>
     - <span data-ttu-id="78940-200">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="78940-200">**Expiration date**</span></span>
     - <span data-ttu-id="78940-201">**Observação**</span><span class="sxs-lookup"><span data-stu-id="78940-201">**Note**</span></span>

   - <span data-ttu-id="78940-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="78940-202">**Files**</span></span>
     - <span data-ttu-id="78940-203">**Valor**: o hash do arquivo.</span><span class="sxs-lookup"><span data-stu-id="78940-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="78940-204">**Ação**: o valor **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="78940-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="78940-205">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="78940-205">**Last updated date**</span></span>
     - <span data-ttu-id="78940-206">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="78940-206">**Expiration date**</span></span>
     - <span data-ttu-id="78940-207">**Observação**</span><span class="sxs-lookup"><span data-stu-id="78940-207">**Note**</span></span>

   - <span data-ttu-id="78940-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="78940-208">**Spoofing**</span></span>
     - <span data-ttu-id="78940-209">**Usuário com spoofed**</span><span class="sxs-lookup"><span data-stu-id="78940-209">**Spoofed user**</span></span>
     - <span data-ttu-id="78940-210">**Enviando infraestrutura**</span><span class="sxs-lookup"><span data-stu-id="78940-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="78940-211">**Tipo de spoof**: o valor **Interno** ou **Externo**.</span><span class="sxs-lookup"><span data-stu-id="78940-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="78940-212">**Ação**: o valor **Bloquear** ou **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="78940-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="78940-213">Você pode clicar em um título de coluna para classificar em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="78940-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="78940-214">Você pode clicar **em Grupo** para agrupar os resultados.</span><span class="sxs-lookup"><span data-stu-id="78940-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="78940-215">Os valores disponíveis dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="78940-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="78940-216">**URLs**: Você pode agrupar os resultados por **Ação**.</span><span class="sxs-lookup"><span data-stu-id="78940-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="78940-217">**Arquivos**: Você pode agrupar os resultados por **Ação**.</span><span class="sxs-lookup"><span data-stu-id="78940-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="78940-218">**Domínios de remetente para bypass BCL**: **O** grupo não está disponível nesta guia.</span><span class="sxs-lookup"><span data-stu-id="78940-218">**Sender domains for BCL bypass**: **Group** is not available on this tab.</span></span>
   - <span data-ttu-id="78940-219">**Spoofing**: Você pode agrupar os resultados por **ação** ou tipo **Spoof**.</span><span class="sxs-lookup"><span data-stu-id="78940-219">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="78940-220">Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="78940-220">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="78940-221">Quando terminar, clique em Limpar o **ícone de pesquisa** Limpar pesquisa ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="78940-221">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

   <span data-ttu-id="78940-222">Clique **em Filtrar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="78940-222">Click **Filter** to filter the results.</span></span> <span data-ttu-id="78940-223">Os valores disponíveis no flyout **Filter** que aparece dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="78940-223">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="78940-224">**URLs**</span><span class="sxs-lookup"><span data-stu-id="78940-224">**URLs**</span></span>
     - <span data-ttu-id="78940-225">**Action**</span><span class="sxs-lookup"><span data-stu-id="78940-225">**Action**</span></span>
     - <span data-ttu-id="78940-226">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="78940-226">**Never expire**</span></span>
     - <span data-ttu-id="78940-227">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="78940-227">**Last updated date**</span></span>
     - <span data-ttu-id="78940-228">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="78940-228">**Expiration date**</span></span>

   - <span data-ttu-id="78940-229">**Files**</span><span class="sxs-lookup"><span data-stu-id="78940-229">**Files**</span></span>
     - <span data-ttu-id="78940-230">**Action**</span><span class="sxs-lookup"><span data-stu-id="78940-230">**Action**</span></span>
     - <span data-ttu-id="78940-231">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="78940-231">**Never expire**</span></span>
     - <span data-ttu-id="78940-232">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="78940-232">**Last updated date**</span></span>
     - <span data-ttu-id="78940-233">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="78940-233">**Expiration date**</span></span>

   - <span data-ttu-id="78940-234">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="78940-234">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="78940-235">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="78940-235">**Never expire**</span></span>
     - <span data-ttu-id="78940-236">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="78940-236">**Last updated date**</span></span>
     - <span data-ttu-id="78940-237">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="78940-237">**Expiration date**</span></span>

   - <span data-ttu-id="78940-238">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="78940-238">**Spoofing**</span></span>
     - <span data-ttu-id="78940-239">**Action**</span><span class="sxs-lookup"><span data-stu-id="78940-239">**Action**</span></span>
     - <span data-ttu-id="78940-240">**Tipo de spoof**</span><span class="sxs-lookup"><span data-stu-id="78940-240">**Spoof type**</span></span>

   <span data-ttu-id="78940-241">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="78940-241">When you're finished, click **Apply**.</span></span> <span data-ttu-id="78940-242">Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="78940-242">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-243">Use o Centro de Conformidade & segurança para modificar entradas na lista De permitir/bloquear locatários</span><span class="sxs-lookup"><span data-stu-id="78940-243">Use the Security & Compliance Center to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="78940-244">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="78940-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="78940-245">Selecione a guia que contém o tipo de entrada que você deseja modificar:</span><span class="sxs-lookup"><span data-stu-id="78940-245">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="78940-246">**URLs**</span><span class="sxs-lookup"><span data-stu-id="78940-246">**URLs**</span></span>
   - <span data-ttu-id="78940-247">**Files**</span><span class="sxs-lookup"><span data-stu-id="78940-247">**Files**</span></span>
   - <span data-ttu-id="78940-248">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="78940-248">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="78940-249">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="78940-249">**Spoofing**</span></span>

3. <span data-ttu-id="78940-250">Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) editar.</span><span class="sxs-lookup"><span data-stu-id="78940-250">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span> <span data-ttu-id="78940-251">Os valores que você pode modificar no sobrevoo que aparece dependem da guia selecionada na etapa anterior:</span><span class="sxs-lookup"><span data-stu-id="78940-251">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>

   - <span data-ttu-id="78940-252">**URLs**</span><span class="sxs-lookup"><span data-stu-id="78940-252">**URLs**</span></span>
     - <span data-ttu-id="78940-253">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="78940-253">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="78940-254">**Observação opcional**</span><span class="sxs-lookup"><span data-stu-id="78940-254">**Optional note**</span></span>

   - <span data-ttu-id="78940-255">**Files**</span><span class="sxs-lookup"><span data-stu-id="78940-255">**Files**</span></span>
     - <span data-ttu-id="78940-256">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="78940-256">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="78940-257">**Observação opcional**</span><span class="sxs-lookup"><span data-stu-id="78940-257">**Optional note**</span></span>

   - <span data-ttu-id="78940-258">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="78940-258">**Sender domains for BCL bypass**</span></span>
     - <span data-ttu-id="78940-259">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="78940-259">**Never expire** and/or expiration date.</span></span>

   - <span data-ttu-id="78940-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="78940-260">**Spoofing**</span></span>
     - <span data-ttu-id="78940-261">**Ação**: você pode alterar o valor para **Permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="78940-261">**Action**: You can change the value to **Allow** or **Block**.</span></span>

4. <span data-ttu-id="78940-262">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="78940-262">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="78940-263">Use o Centro de Conformidade & segurança para remover entradas da lista de locatários permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-263">Use the Security & Compliance Center to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="78940-264">No Centro de Conformidade & Segurança, vá para **Lista** de Locatários de Política de Gerenciamento de \>  \> **Ameaças/Listas de Bloqueio.**</span><span class="sxs-lookup"><span data-stu-id="78940-264">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="78940-265">Selecione a guia que contém o tipo de entrada que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="78940-265">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="78940-266">**URLs**</span><span class="sxs-lookup"><span data-stu-id="78940-266">**URLs**</span></span>
   - <span data-ttu-id="78940-267">**Files**</span><span class="sxs-lookup"><span data-stu-id="78940-267">**Files**</span></span>
   - <span data-ttu-id="78940-268">**Domínios de remetente para bypass BCL**</span><span class="sxs-lookup"><span data-stu-id="78940-268">**Sender domains for BCL bypass**</span></span>
   - <span data-ttu-id="78940-269">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="78940-269">**Spoofing**</span></span>

3. <span data-ttu-id="78940-270">Selecione a entrada que você deseja remover e clique em **Excluir** ![ ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="78940-270">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="78940-271">Na caixa de diálogo de aviso exibida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="78940-271">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="78940-272">Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-272">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="78940-273">Use o PowerShell para adicionar entradas de arquivo de bloqueio ou URL à Lista de Locatários De Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-273">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-274">Para adicionar entradas de arquivo de bloqueio ou URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-274">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="78940-275">Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="78940-275">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="78940-276">Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78940-276">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="78940-277">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="78940-277">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="78940-278">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="78940-278">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="78940-279">Use o PowerShell para adicionar entradas de remetentes com spoofed ou de autorização ou bloqueio à Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-279">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-280">Para adicionar entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-280">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="78940-281">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="78940-281">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-282">Usar o PowerShell para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-282">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-283">Para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-283">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="78940-284">Este exemplo retorna informações para o valor de hash de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="78940-284">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="78940-285">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="78940-285">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="78940-286">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="78940-286">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-287">Use o PowerShell para exibir as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-287">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-288">Para exibir entradas de remetentes com spoofed na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-288">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="78940-289">Este exemplo retorna todas as entradas de remetentes com spoofed na Lista de Locatários de Permitir/Bloquear.</span><span class="sxs-lookup"><span data-stu-id="78940-289">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="78940-290">Este exemplo retorna todas as entradas de remetentes com spoofed que são internas.</span><span class="sxs-lookup"><span data-stu-id="78940-290">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="78940-291">Este exemplo retorna todas as entradas de remetentes com spoofed bloqueados que são externas.</span><span class="sxs-lookup"><span data-stu-id="78940-291">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="78940-292">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="78940-292">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-293">Usar o PowerShell para modificar as entradas de arquivo de bloqueio e URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-293">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-294">Para modificar entradas de arquivo de bloqueio e URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-294">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="78940-295">Este exemplo altera a data de expiração da entrada da URL de bloco especificada.</span><span class="sxs-lookup"><span data-stu-id="78940-295">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="78940-296">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="78940-296">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-297">Use o PowerShell para modificar as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-297">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-298">Para modificar entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-298">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="78940-299">Este exemplo altera a entrada de remetentes com spoofed de permitir o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="78940-299">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="78940-300">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="78940-300">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="78940-301">Use o PowerShell para remover entradas de URL ou arquivo da Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-301">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-302">Para remover entradas de arquivo e URL da Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-302">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="78940-303">Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.</span><span class="sxs-lookup"><span data-stu-id="78940-303">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="78940-304">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="78940-304">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="78940-305">Use o PowerShell para remover entradas de remetentes com spoofed ou de permitir ou bloquear da Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-305">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-306">Para remover as entradas de remetente de spoof ou de permitir ou bloquear da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="78940-306">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="78940-307">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="78940-307">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="78940-308">Sintaxe de URL para a Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-308">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="78940-309">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="78940-309">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="78940-310">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="78940-310">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="78940-311">Unicode não tem suporte, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="78940-311">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="78940-312">Os nomes de host são permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="78940-312">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="78940-313">O nomedo host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="78940-313">The hostname contains a period.</span></span>
  - <span data-ttu-id="78940-314">Há pelo menos um caractere à esquerda do período.</span><span class="sxs-lookup"><span data-stu-id="78940-314">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="78940-315">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="78940-315">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="78940-316">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="78940-316">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="78940-317">Subpaths não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="78940-317">Subpaths are not implied.</span></span>

  <span data-ttu-id="78940-318">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="78940-318">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="78940-319">Os caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="78940-319">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="78940-320">Um curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="78940-320">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="78940-321">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="78940-321">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="78940-322">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="78940-322">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="78940-323">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="78940-323">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="78940-324">Todos os subcamadas não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="78940-324">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="78940-325">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="78940-325">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="78940-326">`*.com*` é inválido (não é um domínio resolvêvel e o caractere curinga direito não segue uma barra de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="78940-326">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="78940-327">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="78940-327">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="78940-328">O caractere tilde (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="78940-328">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="78940-329">Um bloco esquerdo implica um domínio e todos os subdomas.</span><span class="sxs-lookup"><span data-stu-id="78940-329">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="78940-330">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="78940-330">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="78940-331">As entradas de URL que contêm protocolos (por exemplo, , , ou ) falharão, pois as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="78940-331">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="78940-332">Um nome de usuário ou senha não é suportado ou necessário.</span><span class="sxs-lookup"><span data-stu-id="78940-332">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="78940-333">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="78940-333">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="78940-334">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="78940-334">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="78940-335">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="78940-335">URL entry scenarios</span></span>

<span data-ttu-id="78940-336">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="78940-336">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="78940-337">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="78940-337">Scenario: No wildcards</span></span>

<span data-ttu-id="78940-338">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="78940-338">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="78940-339">**Permitir match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-339">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="78940-340">**Permitir não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="78940-340">**Allow not matched**:</span></span>

  - <span data-ttu-id="78940-341">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-341">abc-contoso.com</span></span>
  - <span data-ttu-id="78940-342">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="78940-342">contoso.com/a</span></span>
  - <span data-ttu-id="78940-343">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-343">payroll.contoso.com</span></span>
  - <span data-ttu-id="78940-344">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-344">test.com/contoso.com</span></span>
  - <span data-ttu-id="78940-345">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-345">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="78940-346">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-346">www.contoso.com</span></span>
  - <span data-ttu-id="78940-347">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-347">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="78940-348">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-348">**Block match**:</span></span>

  - <span data-ttu-id="78940-349">contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-349">contoso.com</span></span>
  - <span data-ttu-id="78940-350">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="78940-350">contoso.com/a</span></span>
  - <span data-ttu-id="78940-351">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-351">payroll.contoso.com</span></span>
  - <span data-ttu-id="78940-352">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-352">test.com/contoso.com</span></span>
  - <span data-ttu-id="78940-353">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-353">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="78940-354">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-354">www.contoso.com</span></span>
  - <span data-ttu-id="78940-355">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-355">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="78940-356">**Bloquear não corresponder :** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-356">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="78940-357">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="78940-357">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="78940-358">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="78940-358">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="78940-359">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-359">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="78940-360">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-360">www.contoso.com</span></span>
  - <span data-ttu-id="78940-361">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-361">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="78940-362">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="78940-362">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="78940-363">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-363">123contoso.com</span></span>
  - <span data-ttu-id="78940-364">contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-364">contoso.com</span></span>
  - <span data-ttu-id="78940-365">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-365">test.com/contoso.com</span></span>
  - <span data-ttu-id="78940-366">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="78940-366">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="78940-367">Cenário: curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="78940-367">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="78940-368">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="78940-368">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="78940-369">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-369">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="78940-370">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="78940-370">contoso.com/a/b</span></span>
  - <span data-ttu-id="78940-371">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="78940-371">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="78940-372">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="78940-372">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="78940-373">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="78940-373">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="78940-374">contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-374">contoso.com</span></span>
  - <span data-ttu-id="78940-375">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="78940-375">contoso.com/a</span></span>
  - <span data-ttu-id="78940-376">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-376">www.contoso.com</span></span>
  - <span data-ttu-id="78940-377">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-377">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="78940-378">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="78940-378">Scenario: Left tilde</span></span>

<span data-ttu-id="78940-379">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="78940-379">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="78940-380">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-380">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="78940-381">contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-381">contoso.com</span></span>
  - <span data-ttu-id="78940-382">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-382">www.contoso.com</span></span>
  - <span data-ttu-id="78940-383">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-383">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="78940-384">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="78940-384">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="78940-385">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-385">123contoso.com</span></span>
  - <span data-ttu-id="78940-386">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="78940-386">contoso.com/abc</span></span>
  - <span data-ttu-id="78940-387">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="78940-387">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="78940-388">Cenário: sufixo curinga correto</span><span class="sxs-lookup"><span data-stu-id="78940-388">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="78940-389">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="78940-389">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="78940-390">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-390">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="78940-391">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="78940-391">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="78940-392">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="78940-392">contoso.com/a</span></span>
  - <span data-ttu-id="78940-393">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="78940-393">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="78940-394">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="78940-394">contoso.com/ab</span></span>
  - <span data-ttu-id="78940-395">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="78940-395">contoso.com/b</span></span>
  - <span data-ttu-id="78940-396">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="78940-396">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="78940-397">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="78940-397">contoso.com/ba</span></span>

- <span data-ttu-id="78940-398">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-398">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="78940-399">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="78940-399">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="78940-400">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="78940-400">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="78940-401">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="78940-402">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="78940-402">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="78940-403">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="78940-403">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="78940-404">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="78940-404">www.contoso.com/a</span></span>
  - <span data-ttu-id="78940-405">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="78940-405">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="78940-406">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="78940-406">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="78940-407">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="78940-407">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="78940-408">Cenário: bloco esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="78940-408">Scenario: Left and right tilde</span></span>

<span data-ttu-id="78940-409">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="78940-409">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="78940-410">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-410">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="78940-411">contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-411">contoso.com</span></span>
  - <span data-ttu-id="78940-412">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="78940-412">contoso.com/a</span></span>
  - <span data-ttu-id="78940-413">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-413">www.contoso.com</span></span>
  - <span data-ttu-id="78940-414">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="78940-414">www.contoso.com/b</span></span>
  - <span data-ttu-id="78940-415">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-415">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="78940-416">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="78940-416">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="78940-417">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-417">123contoso.com</span></span>
  - <span data-ttu-id="78940-418">contoso.org</span><span class="sxs-lookup"><span data-stu-id="78940-418">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="78940-419">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="78940-419">Scenario: IP address</span></span>

<span data-ttu-id="78940-420">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="78940-420">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="78940-421">**Permitir match** e **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="78940-421">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="78940-422">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="78940-422">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="78940-423">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="78940-423">1.2.3.4/a</span></span>
  - <span data-ttu-id="78940-424">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="78940-424">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="78940-425">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="78940-425">IP address with right wildcard</span></span>

<span data-ttu-id="78940-426">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="78940-426">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="78940-427">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="78940-427">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="78940-428">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="78940-428">1.2.3.4/b</span></span>
  - <span data-ttu-id="78940-429">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="78940-429">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="78940-430">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="78940-430">Examples of invalid entries</span></span>

<span data-ttu-id="78940-431">As seguintes entradas são inválidas:</span><span class="sxs-lookup"><span data-stu-id="78940-431">The following entries are invalid:</span></span>

- <span data-ttu-id="78940-432">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="78940-432">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="78940-433">contoso</span><span class="sxs-lookup"><span data-stu-id="78940-433">contoso</span></span>
  - <span data-ttu-id="78940-434">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="78940-434">\*.contoso.\*</span></span>
  - <span data-ttu-id="78940-435">\*.com</span><span class="sxs-lookup"><span data-stu-id="78940-435">\*.com</span></span>
  - <span data-ttu-id="78940-436">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="78940-436">\*.pdf</span></span>

- <span data-ttu-id="78940-437">**Caractere curinga em texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="78940-437">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="78940-438">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="78940-438">\*contoso.com</span></span>
  - <span data-ttu-id="78940-439">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="78940-439">contoso.com\*</span></span>
  - <span data-ttu-id="78940-440">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="78940-440">\*1.2.3.4</span></span>
  - <span data-ttu-id="78940-441">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="78940-441">1.2.3.4\*</span></span>
  - <span data-ttu-id="78940-442">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="78940-442">contoso.com/a\*</span></span>
  - <span data-ttu-id="78940-443">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="78940-443">contoso.com/ab\*</span></span>

- <span data-ttu-id="78940-444">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="78940-444">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="78940-445">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="78940-445">contoso.com:443</span></span>
  - <span data-ttu-id="78940-446">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="78940-446">abc.contoso.com:25</span></span>

- <span data-ttu-id="78940-447">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="78940-447">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="78940-448">\*.\*</span><span class="sxs-lookup"><span data-stu-id="78940-448">\*.\*</span></span>

- <span data-ttu-id="78940-449">**Caracteres curinga intermediários**:</span><span class="sxs-lookup"><span data-stu-id="78940-449">**Middle wildcards**:</span></span>

  - <span data-ttu-id="78940-450">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="78940-450">conto\*so.com</span></span>
  - <span data-ttu-id="78940-451">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="78940-451">conto~so.com</span></span>

- <span data-ttu-id="78940-452">**Caracteres curinga duplos**</span><span class="sxs-lookup"><span data-stu-id="78940-452">**Double wildcards**</span></span>

  - <span data-ttu-id="78940-453">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="78940-453">contoso.com/\*\*</span></span>
  - <span data-ttu-id="78940-454">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="78940-454">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="78940-455">Sintaxe de par de domínios para entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="78940-455">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="78940-456">Um par de domínios para um remetente com spoofed na Lista de Locatários de Permitir/Bloquear usa a seguinte sintaxe: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="78940-456">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="78940-457">**Usuário com spoofed**: esse valor envolve o endereço de email do usuário que é exibido na caixa **De** em clientes de email.</span><span class="sxs-lookup"><span data-stu-id="78940-457">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="78940-458">Esse endereço também é conhecido como `5322.From` endereço.</span><span class="sxs-lookup"><span data-stu-id="78940-458">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="78940-459">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="78940-459">Valid values include:</span></span>
  - <span data-ttu-id="78940-460">Um endereço de email individual (por exemplo, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78940-460">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="78940-461">Um domínio de email (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78940-461">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="78940-462">O caractere curinga (por exemplo, \* ).</span><span class="sxs-lookup"><span data-stu-id="78940-462">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="78940-463">**Infraestrutura de** envio : esse valor indica a origem das mensagens do usuário espouado.</span><span class="sxs-lookup"><span data-stu-id="78940-463">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="78940-464">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="78940-464">Valid values include:</span></span>
  - <span data-ttu-id="78940-465">O domínio encontrado em um registro DNS reverso (registro PTR) do endereço IP do servidor de email de origem (por exemplo, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="78940-465">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="78940-466">Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="78940-466">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="78940-467">Aqui estão alguns exemplos de pares de domínio válidos para identificar os envios com spoofed:</span><span class="sxs-lookup"><span data-stu-id="78940-467">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="78940-468">O número máximo de entradas de remetentes com spoofed é 1000.</span><span class="sxs-lookup"><span data-stu-id="78940-468">The maximum number of spoofed sender entries is 1000.</span></span> 

<span data-ttu-id="78940-469">Adicionar um par de domínios  só permite ou bloqueia a combinação do usuário e da *infraestrutura* de envio.</span><span class="sxs-lookup"><span data-stu-id="78940-469">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="78940-470">Ele não permite emails do usuário com spoofed de qualquer origem, nem permite emails da fonte de infraestrutura de envio para qualquer usuário com spoofed.</span><span class="sxs-lookup"><span data-stu-id="78940-470">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="78940-471">Por exemplo, você adiciona uma entrada de autorização para o seguinte par de domínio:</span><span class="sxs-lookup"><span data-stu-id="78940-471">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="78940-472">**Domínio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="78940-472">**Domain**: gmail.com</span></span>
- <span data-ttu-id="78940-473">**Infraestrutura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="78940-473">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="78940-474">Somente as mensagens desse domínio *e o* par de infraestrutura de envio podem ser falsas.</span><span class="sxs-lookup"><span data-stu-id="78940-474">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="78940-475">Outros senders que tentam gmail.com não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="78940-475">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="78940-476">As mensagens de senders em outros domínios provenientes tms.mx.com são verificadas por inteligência falsa.</span><span class="sxs-lookup"><span data-stu-id="78940-476">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
