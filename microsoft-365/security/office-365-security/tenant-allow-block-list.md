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
ms.openlocfilehash: 67c3badb86f1cfb9bf644cc202ed67e3163a6772
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933150"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="83545-103">Gerenciar a lista de Permissões/Bloqueios do Locatário</span><span class="sxs-lookup"><span data-stu-id="83545-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="83545-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="83545-104">**Applies to**</span></span>
- [<span data-ttu-id="83545-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="83545-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="83545-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="83545-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="83545-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="83545-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> <span data-ttu-id="83545-108">Os recursos descritos neste artigo estão em Visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="83545-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>  <span data-ttu-id="83545-109">Se a sua organização não tiver os recursos de spoof conforme descrito neste artigo, consulte a experiência de gerenciamento de spoof mais antiga em Gerenciar envios com spoofed usando a política de inteligência de spoof e informações de inteligência de [spoof no EOP](walkthrough-spoof-intelligence-insight.md).</span><span class="sxs-lookup"><span data-stu-id="83545-109">If your organization does not have the spoof features as described in this article, see the older spoof management experience at [Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).</span></span>
>
> <span data-ttu-id="83545-110">Não é possível configurar **a** URL ou os itens de arquivo permitidos na Lista de Locatários Permitidos/Bloqueados no momento.</span><span class="sxs-lookup"><span data-stu-id="83545-110">You can't **configure** allowed URL or file items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="83545-111">Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, talvez você não concorde com o veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="83545-111">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="83545-112">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida através (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="83545-112">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="83545-113">A Lista de locatários de Microsoft 365 portal do Defender oferece uma maneira de substituir manualmente os Microsoft 365 de filtragem.</span><span class="sxs-lookup"><span data-stu-id="83545-113">The Tenant Allow/Block List in the Microsoft 365 Defender portal gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="83545-114">A Lista de Locatários Permite/Bloquear é usada durante o fluxo de emails e no momento dos cliques do usuário.</span><span class="sxs-lookup"><span data-stu-id="83545-114">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="83545-115">Você pode especificar os seguintes tipos de substituições:</span><span class="sxs-lookup"><span data-stu-id="83545-115">You can specify the following types of overrides:</span></span>

- <span data-ttu-id="83545-116">URLs a bloquear.</span><span class="sxs-lookup"><span data-stu-id="83545-116">URLs to block.</span></span>
- <span data-ttu-id="83545-117">Arquivos a bloquear.</span><span class="sxs-lookup"><span data-stu-id="83545-117">Files to block.</span></span>
- <span data-ttu-id="83545-118">Envios com spoofed para permitir ou bloquear.</span><span class="sxs-lookup"><span data-stu-id="83545-118">Spoofed senders to allow or block.</span></span> <span data-ttu-id="83545-119">Se você substituir o veredito de permitir ou bloquear no insight de inteligência de spoof , o remetente [spoofed](learn-about-spoof-intelligence.md)se tornará uma entrada manual de permitir ou bloquear que só aparece na guia **Spoof** na Lista de Locatários De Permitir/Bloquear.</span><span class="sxs-lookup"><span data-stu-id="83545-119">If you override the allow or block verdict in the [spoof intelligence insight](learn-about-spoof-intelligence.md), the spoofed sender becomes a manual allow or block entry that only appears on the **Spoof** tab in the Tenant Allow/Block List.</span></span> <span data-ttu-id="83545-120">Você também pode criar manualmente entradas de permitir ou bloquear para os envios de spoofed aqui antes que eles são detectados pela inteligência spoof.</span><span class="sxs-lookup"><span data-stu-id="83545-120">You can also manually create allow or block entries for spoofed senders here before they're detected by spoof intelligence.</span></span>

<span data-ttu-id="83545-121">Este artigo descreve como configurar entradas na Lista de Locatários Permitir/Bloquear no portal do defender do Microsoft 365 ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).</span><span class="sxs-lookup"><span data-stu-id="83545-121">This article describes how to configure entries in the Tenant Allow/Block List in the Microsoft 365 Defender portal or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="83545-122">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="83545-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="83545-123">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="83545-123">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="83545-124">Para ir diretamente para a página **Listas de Locatários/Bloqueios,** use <https://security.microsoft.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="83545-124">To go directly to the **Tenant Allow/Block Lists** page, use <https://security.microsoft.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="83545-125">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="83545-125">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="83545-126">Para encontrar o valor de hash SHA256 de um arquivo Windows, execute o seguinte comando em um Prompt de Comando:</span><span class="sxs-lookup"><span data-stu-id="83545-126">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="83545-127">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="83545-127">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="83545-128">Os valores de hash perceptual (pHash) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="83545-128">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="83545-129">Os valores de URL disponíveis são descritos na sintaxe de URL da seção [Lista de Locatários/Bloqueios](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="83545-129">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="83545-130">A Lista de Permitir/Bloquear Locatários permite no máximo 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="83545-130">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="83545-131">O número máximo de caracteres para cada entrada é:</span><span class="sxs-lookup"><span data-stu-id="83545-131">The maximum number of characters for each entry is:</span></span>
  - <span data-ttu-id="83545-132">Hashes de arquivo = 64</span><span class="sxs-lookup"><span data-stu-id="83545-132">File hashes = 64</span></span>
  - <span data-ttu-id="83545-133">URL = 250</span><span class="sxs-lookup"><span data-stu-id="83545-133">URL = 250</span></span>

- <span data-ttu-id="83545-134">Uma entrada deve estar ativa dentro de 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="83545-134">An entry should be active within 30 minutes.</span></span>

- <span data-ttu-id="83545-135">Por padrão, as entradas na Lista de Locatários Permitir/Bloquear expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="83545-135">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="83545-136">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="83545-136">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="83545-137">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="83545-137">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="83545-138">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="83545-138">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="83545-139">Você precisa de permissões em Exchange Online  antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="83545-139">You need to be assigned permissions in Exchange Online before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="83545-140">**URLs e arquivos**:</span><span class="sxs-lookup"><span data-stu-id="83545-140">**URLs and files**:</span></span>
    - <span data-ttu-id="83545-141">Para adicionar e remover valores da Lista de Permitir/Bloquear Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança. </span><span class="sxs-lookup"><span data-stu-id="83545-141">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
    - <span data-ttu-id="83545-142">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="83545-142">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>
  - <span data-ttu-id="83545-143">**Spoofing**: uma das seguintes combinações:</span><span class="sxs-lookup"><span data-stu-id="83545-143">**Spoofing**: One of the following combinations:</span></span>
    - <span data-ttu-id="83545-144">**Organization Management**</span><span class="sxs-lookup"><span data-stu-id="83545-144">**Organization Management**</span></span>
    - <span data-ttu-id="83545-145">**Administrador de Segurança** <u>e</u> **Configuração somente exibição** ou **Gerenciamento de organização somente exibição.**</span><span class="sxs-lookup"><span data-stu-id="83545-145">**Security Administrator** <u>and</u> **View-Only Configuration** or **View-Only Organization Management**.</span></span>

  <span data-ttu-id="83545-146">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="83545-146">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="83545-147">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83545-147">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="83545-148">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="83545-148">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="83545-149">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="83545-149">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-150">Use o portal Microsoft 365 Defender para criar entradas de URL de bloqueio na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-150">Use the Microsoft 365 Defender portal to create block URL entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="83545-151">No portal Microsoft 365 Defender, vá para Políticas & **Regras** de Políticas de Ameaças seção \>  \>  Locatário \> Listas de locatários. </span><span class="sxs-lookup"><span data-stu-id="83545-151">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="83545-152">Na página **Lista de Locatários Permitir/Bloquear,** verifique se a **guia URLs** está selecionada e clique em ![ Bloquear ícone ](../../media/m365-cc-sc-create-icon.png) **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="83545-152">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="83545-153">No **sobrevoo Bloquear URLs** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="83545-153">In the **Block URLs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="83545-154">**Adicionar URLs com caracteres curinga**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="83545-154">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span> <span data-ttu-id="83545-155">Para obter detalhes sobre a sintaxe para entradas de [URL,](#url-syntax-for-the-tenant-allowblock-list) consulte a sintaxe de URL para a seção Lista de Locatários/Bloqueios posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="83545-155">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="83545-156">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="83545-156">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="83545-157">Verifique se a configuração está desligada ( Alternar ) e use a caixa Remover on para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="83545-157">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

       <span data-ttu-id="83545-158">ou</span><span class="sxs-lookup"><span data-stu-id="83545-158">or</span></span>

     - <span data-ttu-id="83545-159">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="83545-159">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="83545-161">.</span><span class="sxs-lookup"><span data-stu-id="83545-161">.</span></span>
   - <span data-ttu-id="83545-162">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="83545-162">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="83545-163">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="83545-163">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-164">Use o Microsoft 365 do Defender para criar entradas de arquivo de bloqueio na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-164">Use the Microsoft 365 Defender portal to create block file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="83545-165">No portal Microsoft 365 Defender, vá para Políticas & **Regras** de Políticas de Ameaças seção \>  \>  Locatário \> Listas de locatários. </span><span class="sxs-lookup"><span data-stu-id="83545-165">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="83545-166">Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Arquivos** e clique em Bloquear ![ ícone ](../../media/m365-cc-sc-create-icon.png) **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="83545-166">On the **Tenant Allow/Block List** page, select the **Files** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Block**.</span></span>

3. <span data-ttu-id="83545-167">No **sobrevoo Bloquear arquivos** que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="83545-167">In the **Block files** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="83545-168">**Adicionar hashes de arquivo**: insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="83545-168">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>
   - <span data-ttu-id="83545-169">**Nunca expire**: Faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="83545-169">**Never expire**: Do one of the following steps:</span></span>
     - <span data-ttu-id="83545-170">Verifique se a configuração está desligada ( Alternar ) e use a caixa Remover on para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="83545-170">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Remove on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="83545-171">ou</span><span class="sxs-lookup"><span data-stu-id="83545-171">or</span></span>

     - <span data-ttu-id="83545-172">Mova a alternância para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="83545-172">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="83545-174">.</span><span class="sxs-lookup"><span data-stu-id="83545-174">.</span></span>
   - <span data-ttu-id="83545-175">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="83545-175">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="83545-176">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="83545-176">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-177">Use o Microsoft 365 do Defender para criar entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-177">Use the Microsoft 365 Defender portal to create allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-178">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="83545-178">**Notes**:</span></span>

- <span data-ttu-id="83545-179">Somente a _combinação_ do usuário  com a infraestrutura de envio, conforme definido no par de domínios, é especificamente permitida ou bloqueada da spoofing.</span><span class="sxs-lookup"><span data-stu-id="83545-179">Only the _combination_ of the spoofed user _and_ the sending infrastructure as defined in the domain pair is specifically allowed or blocked from spoofing.</span></span>
- <span data-ttu-id="83545-180">Quando você configura uma entrada de permitir ou bloquear para um par de domínios, as mensagens desse par de domínios não aparecem mais no insight de inteligência falsa.</span><span class="sxs-lookup"><span data-stu-id="83545-180">When you configure an allow or block entry for a domain pair, messages from that domain pair no longer appear in the spoof intelligence insight.</span></span>
- <span data-ttu-id="83545-181">As entradas para os envios com spoofed nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="83545-181">Entries for spoofed senders never expire.</span></span>

1. <span data-ttu-id="83545-182">No portal Microsoft 365 Defender, vá para Políticas & **Regras** de Políticas de Ameaças seção \>  \>  Locatário \> Listas de locatários. </span><span class="sxs-lookup"><span data-stu-id="83545-182">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="83545-183">Na página **Lista de Locatários Permitir/Bloquear,** selecione a guia **Spoofing** e clique em ![ Bloquear ícone ](../../media/m365-cc-sc-create-icon.png) **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="83545-183">On the **Tenant Allow/Block List** page, select the **Spoofing** tab, and then click ![Block icon](../../media/m365-cc-sc-create-icon.png) **Add**.</span></span>

3. <span data-ttu-id="83545-184">No **flyout Adicionar novos pares de** domínio que aparece, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="83545-184">In the **Add new domain pairs** flyout that appears, configure the following settings:</span></span>
   - <span data-ttu-id="83545-185">**Adicionar novos pares de domínio com caracteres curinga**: Insira um par de domínios por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="83545-185">**Add new domain pairs with wildcards**: Enter one domain pair per line, up to a maximum of 20.</span></span> <span data-ttu-id="83545-186">Para obter detalhes sobre a sintaxe para entradas de remetentes com spoofed, consulte a sintaxe de par de domínios para entradas de remetentes com [spoofed](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) na seção Lista de Locatários Permitir/Bloquear mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="83545-186">For details about the syntax for spoofed sender entries, see the [Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) section later in this article.</span></span>
   - <span data-ttu-id="83545-187">**Tipo de spoof**: selecione um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="83545-187">**Spoof type**: Select one of the following values:</span></span>
     - <span data-ttu-id="83545-188">**Interno**: o remetente spoofed está em um domínio que pertence à sua organização [(um domínio aceito](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span><span class="sxs-lookup"><span data-stu-id="83545-188">**Internal**: The spoofed sender is in a domain that belongs to your organization (an [accepted domain](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).</span></span>
     - <span data-ttu-id="83545-189">**Externo**: o remetente spoofed está em um domínio externo.</span><span class="sxs-lookup"><span data-stu-id="83545-189">**External**: The spoofed sender is in an external domain.</span></span>
   - <span data-ttu-id="83545-190">**Ação**: Selecione **Permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="83545-190">**Action**: Select **Allow** or **Block**.</span></span>

4. <span data-ttu-id="83545-191">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="83545-191">When you're finished, click **Add**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-192">Use o Microsoft 365 do Defender para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-192">Use the Microsoft 365 Defender portal to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="83545-193">No portal Microsoft 365 Defender, vá para Políticas & **Regras** de Políticas de Ameaças seção \>  \>  Locatário \> Listas de locatários. </span><span class="sxs-lookup"><span data-stu-id="83545-193">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="83545-194">Selecione a guia que você deseja.</span><span class="sxs-lookup"><span data-stu-id="83545-194">Select the tab you want.</span></span> <span data-ttu-id="83545-195">As colunas disponíveis dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="83545-195">The columns that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="83545-196">**URLs**:</span><span class="sxs-lookup"><span data-stu-id="83545-196">**URLs**:</span></span>
     - <span data-ttu-id="83545-197">**Valor**: A URL.</span><span class="sxs-lookup"><span data-stu-id="83545-197">**Value**: The URL.</span></span>
     - <span data-ttu-id="83545-198">**Ação**: o valor **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="83545-198">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="83545-199">**Última atualização**</span><span class="sxs-lookup"><span data-stu-id="83545-199">**Last updated**</span></span>
     - <span data-ttu-id="83545-200">**Remover em**</span><span class="sxs-lookup"><span data-stu-id="83545-200">**Remove on**</span></span>
     - <span data-ttu-id="83545-201">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="83545-201">**Notes**</span></span>
   - <span data-ttu-id="83545-202">**Files**</span><span class="sxs-lookup"><span data-stu-id="83545-202">**Files**</span></span>
     - <span data-ttu-id="83545-203">**Valor**: o hash do arquivo.</span><span class="sxs-lookup"><span data-stu-id="83545-203">**Value**: The file hash.</span></span>
     - <span data-ttu-id="83545-204">**Ação**: o valor **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="83545-204">**Action**: The value **Block**.</span></span>
     - <span data-ttu-id="83545-205">**Última atualização**</span><span class="sxs-lookup"><span data-stu-id="83545-205">**Last updated**</span></span>
     - <span data-ttu-id="83545-206">**Remover em**</span><span class="sxs-lookup"><span data-stu-id="83545-206">**Remove on**</span></span>
     - <span data-ttu-id="83545-207">**Anotações**</span><span class="sxs-lookup"><span data-stu-id="83545-207">**Notes**</span></span>
   - <span data-ttu-id="83545-208">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="83545-208">**Spoofing**</span></span>
     - <span data-ttu-id="83545-209">**Usuário com spoofed**</span><span class="sxs-lookup"><span data-stu-id="83545-209">**Spoofed user**</span></span>
     - <span data-ttu-id="83545-210">**Enviando infraestrutura**</span><span class="sxs-lookup"><span data-stu-id="83545-210">**Sending infrastructure**</span></span>
     - <span data-ttu-id="83545-211">**Tipo de spoof**: o valor **Interno** ou **Externo**.</span><span class="sxs-lookup"><span data-stu-id="83545-211">**Spoof type**: The value **Internal** or **External**.</span></span>
     - <span data-ttu-id="83545-212">**Ação**: o valor **Bloquear** ou **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="83545-212">**Action**: The value **Block** or **Allow**.</span></span>

   <span data-ttu-id="83545-213">Você pode clicar em um título de coluna para classificar em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="83545-213">You can click on a column heading to sort in ascending or descending order.</span></span>

   <span data-ttu-id="83545-214">Você pode clicar **em Grupo** para agrupar os resultados.</span><span class="sxs-lookup"><span data-stu-id="83545-214">You can click **Group** to group the results.</span></span> <span data-ttu-id="83545-215">Os valores disponíveis dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="83545-215">The values that are available depend on the tab you selected:</span></span>

   - <span data-ttu-id="83545-216">**URLs**: Você pode agrupar os resultados por **Ação**.</span><span class="sxs-lookup"><span data-stu-id="83545-216">**URLs**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="83545-217">**Arquivos**: Você pode agrupar os resultados por **Ação**.</span><span class="sxs-lookup"><span data-stu-id="83545-217">**Files**: You can group the results by **Action**.</span></span>
   - <span data-ttu-id="83545-218">**Spoofing**: Você pode agrupar os resultados por **ação** ou tipo **Spoof**.</span><span class="sxs-lookup"><span data-stu-id="83545-218">**Spoofing**: You can group the results by **Action** or **Spoof type**.</span></span>

   <span data-ttu-id="83545-219">Clique **em Pesquisar**, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="83545-219">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="83545-220">Quando terminar, clique em Limpar ícone ![ de pesquisa Limpar ](../../media/m365-cc-sc-close-icon.png) **pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="83545-220">When you're finished, click ![Clear search icon](../../media/m365-cc-sc-close-icon.png) **Clear search**.</span></span>

   <span data-ttu-id="83545-221">Clique **em Filtrar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="83545-221">Click **Filter** to filter the results.</span></span> <span data-ttu-id="83545-222">Os valores disponíveis no flyout **Filter** que aparece dependem da guia selecionada:</span><span class="sxs-lookup"><span data-stu-id="83545-222">The values that are available in **Filter** flyout that appears depend on the tab you selected:</span></span>

   - <span data-ttu-id="83545-223">**URLs**</span><span class="sxs-lookup"><span data-stu-id="83545-223">**URLs**</span></span>
     - <span data-ttu-id="83545-224">**Action**</span><span class="sxs-lookup"><span data-stu-id="83545-224">**Action**</span></span>
     - <span data-ttu-id="83545-225">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="83545-225">**Never expire**</span></span>
     - <span data-ttu-id="83545-226">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="83545-226">**Last updated date**</span></span>
     - <span data-ttu-id="83545-227">**Remover em**</span><span class="sxs-lookup"><span data-stu-id="83545-227">**Remove on**</span></span>
   - <span data-ttu-id="83545-228">**Files**</span><span class="sxs-lookup"><span data-stu-id="83545-228">**Files**</span></span>
     - <span data-ttu-id="83545-229">**Action**</span><span class="sxs-lookup"><span data-stu-id="83545-229">**Action**</span></span>
     - <span data-ttu-id="83545-230">**Nunca expirar**</span><span class="sxs-lookup"><span data-stu-id="83545-230">**Never expire**</span></span>
     - <span data-ttu-id="83545-231">**Última atualização**</span><span class="sxs-lookup"><span data-stu-id="83545-231">**Last updated**</span></span>
     - <span data-ttu-id="83545-232">**Remover em**</span><span class="sxs-lookup"><span data-stu-id="83545-232">**Remove on**</span></span>
   - <span data-ttu-id="83545-233">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="83545-233">**Spoofing**</span></span>
     - <span data-ttu-id="83545-234">**Action**</span><span class="sxs-lookup"><span data-stu-id="83545-234">**Action**</span></span>
     - <span data-ttu-id="83545-235">**Tipo de spoof**</span><span class="sxs-lookup"><span data-stu-id="83545-235">**Spoof type**</span></span>

   <span data-ttu-id="83545-236">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="83545-236">When you're finished, click **Apply**.</span></span> <span data-ttu-id="83545-237">Para limpar os filtros existentes,  clique em **Filtrar** e, no sobrevoo Filtro que aparece, clique em **Limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="83545-237">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-238">Use o Microsoft 365 do Defender para modificar entradas na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-238">Use the Microsoft 365 Defender portal to modify entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="83545-239">No portal Microsoft 365 Defender, vá para Políticas & **Regras** de Políticas de Ameaças seção \>  \>  Locatário \> Listas de locatários. </span><span class="sxs-lookup"><span data-stu-id="83545-239">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="83545-240">Selecione a guia que contém o tipo de entrada que você deseja modificar:</span><span class="sxs-lookup"><span data-stu-id="83545-240">Select the tab that contains the type of entry that you want to modify:</span></span>
   - <span data-ttu-id="83545-241">**URLs**</span><span class="sxs-lookup"><span data-stu-id="83545-241">**URLs**</span></span>
   - <span data-ttu-id="83545-242">**Files**</span><span class="sxs-lookup"><span data-stu-id="83545-242">**Files**</span></span>
   - <span data-ttu-id="83545-243">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="83545-243">**Spoofing**</span></span>

3. <span data-ttu-id="83545-244">Selecione a entrada que você deseja modificar e clique em ![ Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar**.</span><span class="sxs-lookup"><span data-stu-id="83545-244">Select the entry that you want to modify, and then click ![Edit icon](../../media/m365-cc-sc-edit-icon.png) **Edit**.</span></span> <span data-ttu-id="83545-245">Os valores que você pode modificar no sobrevoo que aparece dependem da guia selecionada na etapa anterior:</span><span class="sxs-lookup"><span data-stu-id="83545-245">The values that you are able to modify in the flyout that appears depend on the tab you selected in the previous step:</span></span>
   - <span data-ttu-id="83545-246">**URLs**</span><span class="sxs-lookup"><span data-stu-id="83545-246">**URLs**</span></span>
     - <span data-ttu-id="83545-247">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="83545-247">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="83545-248">**Observação opcional**</span><span class="sxs-lookup"><span data-stu-id="83545-248">**Optional note**</span></span>
   - <span data-ttu-id="83545-249">**Files**</span><span class="sxs-lookup"><span data-stu-id="83545-249">**Files**</span></span>
     - <span data-ttu-id="83545-250">**Nunca expira** e/ou data de expiração.</span><span class="sxs-lookup"><span data-stu-id="83545-250">**Never expire** and/or expiration date.</span></span>
     - <span data-ttu-id="83545-251">**Observação opcional**</span><span class="sxs-lookup"><span data-stu-id="83545-251">**Optional note**</span></span>
   - <span data-ttu-id="83545-252">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="83545-252">**Spoofing**</span></span>
     - <span data-ttu-id="83545-253">**Ação**: você pode alterar o valor para **Permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="83545-253">**Action**: You can change the value to **Allow** or **Block**.</span></span>
4. <span data-ttu-id="83545-254">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="83545-254">When you're finished, click **Save**.</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="83545-255">Usar o portal Microsoft 365 Defender para remover entradas da lista De locatários de permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-255">Use the Microsoft 365 Defender portal to remove entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="83545-256">No portal Microsoft 365 Defender, vá para Políticas & **Regras** de Políticas de Ameaças seção \>  \>  Locatário \> Listas de locatários. </span><span class="sxs-lookup"><span data-stu-id="83545-256">In the Microsoft 365 Defender portal, go to **Policies & rules** \> **Threat Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="83545-257">Selecione a guia que contém o tipo de entrada que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="83545-257">Select the tab that contains the type of entry that you want to remove:</span></span>
   - <span data-ttu-id="83545-258">**URLs**</span><span class="sxs-lookup"><span data-stu-id="83545-258">**URLs**</span></span>
   - <span data-ttu-id="83545-259">**Files**</span><span class="sxs-lookup"><span data-stu-id="83545-259">**Files**</span></span>
   - <span data-ttu-id="83545-260">**Spoofing**</span><span class="sxs-lookup"><span data-stu-id="83545-260">**Spoofing**</span></span>

3. <span data-ttu-id="83545-261">Selecione a entrada que você deseja remover e clique em ![ Excluir ícone ](../../media/m365-cc-sc-delete-icon.png) **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="83545-261">Select the entry that you want to remove, and then click ![Delete icon](../../media/m365-cc-sc-delete-icon.png) **Delete**.</span></span>

4. <span data-ttu-id="83545-262">Na caixa de diálogo de aviso exibida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="83545-262">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="83545-263">Use Exchange Online PowerShell ou EOP PowerShell autônomo para configurar a lista de locatários de permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-263">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="83545-264">Use o PowerShell para adicionar entradas de arquivo de bloqueio ou URL à Lista de Locatários De Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-264">Use PowerShell to add block file or URL entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-265">Para adicionar entradas de arquivo de bloqueio ou URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-265">To add block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

<span data-ttu-id="83545-266">Este exemplo adiciona uma entrada de arquivo de bloqueio para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="83545-266">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="83545-267">Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os subdomas (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="83545-267">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="83545-268">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="83545-268">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="83545-269">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="83545-269">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="83545-270">Use o PowerShell para adicionar entradas de remetentes com spoofed ou de autorização ou bloqueio à Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-270">Use PowerShell to add allow or block spoofed sender entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-271">Para adicionar entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-271">To add spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

<span data-ttu-id="83545-272">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="83545-272">For detailed syntax and parameter information, see [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-273">Usar o PowerShell para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-273">Use PowerShell to view block file or URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-274">Para exibir entradas de arquivo de bloqueio ou URL na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-274">To view block file or URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

<span data-ttu-id="83545-275">Este exemplo retorna informações para o valor de hash de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="83545-275">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="83545-276">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="83545-276">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="83545-277">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="83545-277">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-278">Use o PowerShell para exibir as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-278">Use PowerShell to view allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-279">Para exibir entradas de remetentes com spoofed na Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-279">To view spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

<span data-ttu-id="83545-280">Este exemplo retorna todas as entradas de remetentes com spoofed na Lista de Locatários de Permitir/Bloquear.</span><span class="sxs-lookup"><span data-stu-id="83545-280">This example returns all spoofed sender entries in the Tenant Allow/Block List.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems
```

<span data-ttu-id="83545-281">Este exemplo retorna todas as entradas de remetentes com spoofed que são internas.</span><span class="sxs-lookup"><span data-stu-id="83545-281">This example returns all allow spoofed sender entries that are internal.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

<span data-ttu-id="83545-282">Este exemplo retorna todas as entradas de remetentes com spoofed bloqueados que são externas.</span><span class="sxs-lookup"><span data-stu-id="83545-282">This example returns all blocked spoofed sender entries that are external.</span></span>

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

<span data-ttu-id="83545-283">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="83545-283">For detailed syntax and parameter information, see [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-284">Usar o PowerShell para modificar as entradas de arquivo de bloqueio e URL na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-284">Use PowerShell to modify block file and URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-285">Para modificar entradas de arquivo de bloqueio e URL na Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-285">To modify block file and URL entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

<span data-ttu-id="83545-286">Este exemplo altera a data de expiração da entrada da URL de bloco especificada.</span><span class="sxs-lookup"><span data-stu-id="83545-286">This example changes the expiration date of the specified block URL entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

<span data-ttu-id="83545-287">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="83545-287">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-288">Use o PowerShell para modificar as entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-288">Use PowerShell to modify allow or block spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-289">Para modificar entradas de remetentes com spoofed ou de permitir ou bloquear na Lista de Locatários De permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-289">To modify allow or block spoofed sender entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

<span data-ttu-id="83545-290">Este exemplo altera a entrada de remetentes com spoofed de permitir o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="83545-290">This example changes spoofed sender entry from allow to block.</span></span>

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

<span data-ttu-id="83545-291">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="83545-291">For detailed syntax and parameter information, see [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).</span></span>

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="83545-292">Use o PowerShell para remover entradas de URL ou arquivo da Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-292">Use PowerShell to remove URL or file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-293">Para remover entradas de arquivo e URL da Lista de Locatários Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-293">To remove file and URL entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="83545-294">Este exemplo remove a entrada de URL de bloco especificada da Lista de Locatários de Bloqueio/Autorização.</span><span class="sxs-lookup"><span data-stu-id="83545-294">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="83545-295">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="83545-295">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="83545-296">Use o PowerShell para remover entradas de remetentes com spoofed ou de permitir ou bloquear da Lista de Locatários De permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-296">Use PowerShell to remove allow or block spoofed sender entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-297">Para remover as entradas de remetente de spoof ou de permitir ou bloquear da Lista de Locatários de Permitir/Bloquear, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="83545-297">To remove allow or block spoof sender entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="83545-298">Para obter informações detalhadas sobre sintaxes e parâmetros, [consulte Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span><span class="sxs-lookup"><span data-stu-id="83545-298">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="83545-299">Sintaxe de URL para a Lista de Locatários de Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-299">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="83545-300">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="83545-300">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="83545-301">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="83545-301">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="83545-302">Unicode não tem suporte, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="83545-302">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="83545-303">Os nomes de host são permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="83545-303">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="83545-304">O nomedo host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="83545-304">The hostname contains a period.</span></span>
  - <span data-ttu-id="83545-305">Há pelo menos um caractere à esquerda do período.</span><span class="sxs-lookup"><span data-stu-id="83545-305">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="83545-306">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="83545-306">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="83545-307">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="83545-307">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="83545-308">Subpaths não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="83545-308">Subpaths are not implied.</span></span>

  <span data-ttu-id="83545-309">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="83545-309">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="83545-310">Os caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="83545-310">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="83545-311">Um curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="83545-311">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="83545-312">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="83545-312">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="83545-313">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="83545-313">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="83545-314">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="83545-314">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="83545-315">Todos os subcamadas não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="83545-315">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="83545-316">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="83545-316">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="83545-317">`*.com*` é inválido (não é um domínio resolvêvel e o caractere curinga direito não segue uma barra de encaminhamento).</span><span class="sxs-lookup"><span data-stu-id="83545-317">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="83545-318">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="83545-318">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="83545-319">O caractere tilde (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="83545-319">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="83545-320">Um bloco esquerdo implica um domínio e todos os subdomas.</span><span class="sxs-lookup"><span data-stu-id="83545-320">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="83545-321">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="83545-321">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="83545-322">As entradas de URL que contêm protocolos (por exemplo, , , ou ) falharão, pois as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="83545-322">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="83545-323">Um nome de usuário ou senha não é suportado ou necessário.</span><span class="sxs-lookup"><span data-stu-id="83545-323">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="83545-324">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="83545-324">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="83545-325">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="83545-325">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="83545-326">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="83545-326">URL entry scenarios</span></span>

<span data-ttu-id="83545-327">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="83545-327">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="83545-328">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="83545-328">Scenario: No wildcards</span></span>

<span data-ttu-id="83545-329">**Entrada**: `contoso.com`</span><span class="sxs-lookup"><span data-stu-id="83545-329">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="83545-330">**Permitir match**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-330">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="83545-331">**Permitir não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="83545-331">**Allow not matched**:</span></span>

  - <span data-ttu-id="83545-332">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-332">abc-contoso.com</span></span>
  - <span data-ttu-id="83545-333">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="83545-333">contoso.com/a</span></span>
  - <span data-ttu-id="83545-334">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-334">payroll.contoso.com</span></span>
  - <span data-ttu-id="83545-335">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-335">test.com/contoso.com</span></span>
  - <span data-ttu-id="83545-336">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-336">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="83545-337">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-337">www.contoso.com</span></span>
  - <span data-ttu-id="83545-338">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-338">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="83545-339">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-339">**Block match**:</span></span>

  - <span data-ttu-id="83545-340">contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-340">contoso.com</span></span>
  - <span data-ttu-id="83545-341">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="83545-341">contoso.com/a</span></span>
  - <span data-ttu-id="83545-342">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-342">payroll.contoso.com</span></span>
  - <span data-ttu-id="83545-343">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-343">test.com/contoso.com</span></span>
  - <span data-ttu-id="83545-344">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-344">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="83545-345">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-345">www.contoso.com</span></span>
  - <span data-ttu-id="83545-346">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-346">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="83545-347">**Bloquear não corresponder :** abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-347">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="83545-348">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="83545-348">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="83545-349">**Entrada**: `*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="83545-349">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="83545-350">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-350">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="83545-351">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-351">www.contoso.com</span></span>
  - <span data-ttu-id="83545-352">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-352">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="83545-353">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="83545-353">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="83545-354">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-354">123contoso.com</span></span>
  - <span data-ttu-id="83545-355">contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-355">contoso.com</span></span>
  - <span data-ttu-id="83545-356">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-356">test.com/contoso.com</span></span>
  - <span data-ttu-id="83545-357">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="83545-357">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="83545-358">Cenário: curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="83545-358">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="83545-359">**Entrada**: `contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="83545-359">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="83545-360">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-360">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="83545-361">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="83545-361">contoso.com/a/b</span></span>
  - <span data-ttu-id="83545-362">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="83545-362">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="83545-363">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="83545-363">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="83545-364">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="83545-364">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="83545-365">contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-365">contoso.com</span></span>
  - <span data-ttu-id="83545-366">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="83545-366">contoso.com/a</span></span>
  - <span data-ttu-id="83545-367">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-367">www.contoso.com</span></span>
  - <span data-ttu-id="83545-368">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-368">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="83545-369">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="83545-369">Scenario: Left tilde</span></span>

<span data-ttu-id="83545-370">**Entrada**: `~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="83545-370">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="83545-371">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-371">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="83545-372">contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-372">contoso.com</span></span>
  - <span data-ttu-id="83545-373">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-373">www.contoso.com</span></span>
  - <span data-ttu-id="83545-374">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-374">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="83545-375">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="83545-375">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="83545-376">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-376">123contoso.com</span></span>
  - <span data-ttu-id="83545-377">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="83545-377">contoso.com/abc</span></span>
  - <span data-ttu-id="83545-378">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="83545-378">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="83545-379">Cenário: sufixo curinga correto</span><span class="sxs-lookup"><span data-stu-id="83545-379">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="83545-380">**Entrada**: `contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="83545-380">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="83545-381">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-381">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="83545-382">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="83545-382">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="83545-383">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="83545-383">contoso.com/a</span></span>
  - <span data-ttu-id="83545-384">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="83545-384">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="83545-385">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="83545-385">contoso.com/ab</span></span>
  - <span data-ttu-id="83545-386">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="83545-386">contoso.com/b</span></span>
  - <span data-ttu-id="83545-387">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="83545-387">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="83545-388">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="83545-388">contoso.com/ba</span></span>

- <span data-ttu-id="83545-389">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-389">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="83545-390">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="83545-390">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="83545-391">**Entrada**: `*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="83545-391">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="83545-392">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-392">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="83545-393">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="83545-393">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="83545-394">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="83545-394">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="83545-395">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="83545-395">www.contoso.com/a</span></span>
  - <span data-ttu-id="83545-396">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="83545-396">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="83545-397">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="83545-397">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="83545-398">**Permitir não corresponder e** **Bloquear não corresponder**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="83545-398">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="83545-399">Cenário: bloco esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="83545-399">Scenario: Left and right tilde</span></span>

<span data-ttu-id="83545-400">**Entrada**: `~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="83545-400">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="83545-401">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-401">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="83545-402">contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-402">contoso.com</span></span>
  - <span data-ttu-id="83545-403">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="83545-403">contoso.com/a</span></span>
  - <span data-ttu-id="83545-404">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-404">www.contoso.com</span></span>
  - <span data-ttu-id="83545-405">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="83545-405">www.contoso.com/b</span></span>
  - <span data-ttu-id="83545-406">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-406">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="83545-407">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="83545-407">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="83545-408">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-408">123contoso.com</span></span>
  - <span data-ttu-id="83545-409">contoso.org</span><span class="sxs-lookup"><span data-stu-id="83545-409">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="83545-410">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="83545-410">Scenario: IP address</span></span>

<span data-ttu-id="83545-411">**Entrada**: `1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="83545-411">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="83545-412">**Permitir match** e **Block match**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="83545-412">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="83545-413">**Permitir não corresponder e** **Bloquear não corresponder**:</span><span class="sxs-lookup"><span data-stu-id="83545-413">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="83545-414">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="83545-414">1.2.3.4/a</span></span>
  - <span data-ttu-id="83545-415">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="83545-415">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="83545-416">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="83545-416">IP address with right wildcard</span></span>

<span data-ttu-id="83545-417">**Entrada**: `1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="83545-417">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="83545-418">**Permitir match** e **Block match**:</span><span class="sxs-lookup"><span data-stu-id="83545-418">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="83545-419">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="83545-419">1.2.3.4/b</span></span>
  - <span data-ttu-id="83545-420">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="83545-420">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="83545-421">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="83545-421">Examples of invalid entries</span></span>

<span data-ttu-id="83545-422">As seguintes entradas são inválidas:</span><span class="sxs-lookup"><span data-stu-id="83545-422">The following entries are invalid:</span></span>

- <span data-ttu-id="83545-423">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="83545-423">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="83545-424">contoso</span><span class="sxs-lookup"><span data-stu-id="83545-424">contoso</span></span>
  - <span data-ttu-id="83545-425">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="83545-425">\*.contoso.\*</span></span>
  - <span data-ttu-id="83545-426">\*.com</span><span class="sxs-lookup"><span data-stu-id="83545-426">\*.com</span></span>
  - <span data-ttu-id="83545-427">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="83545-427">\*.pdf</span></span>

- <span data-ttu-id="83545-428">**Caractere curinga em texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="83545-428">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="83545-429">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="83545-429">\*contoso.com</span></span>
  - <span data-ttu-id="83545-430">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="83545-430">contoso.com\*</span></span>
  - <span data-ttu-id="83545-431">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="83545-431">\*1.2.3.4</span></span>
  - <span data-ttu-id="83545-432">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="83545-432">1.2.3.4\*</span></span>
  - <span data-ttu-id="83545-433">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="83545-433">contoso.com/a\*</span></span>
  - <span data-ttu-id="83545-434">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="83545-434">contoso.com/ab\*</span></span>

- <span data-ttu-id="83545-435">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="83545-435">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="83545-436">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="83545-436">contoso.com:443</span></span>
  - <span data-ttu-id="83545-437">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="83545-437">abc.contoso.com:25</span></span>

- <span data-ttu-id="83545-438">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="83545-438">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="83545-439">\*.\*</span><span class="sxs-lookup"><span data-stu-id="83545-439">\*.\*</span></span>

- <span data-ttu-id="83545-440">**Caracteres curinga intermediários**:</span><span class="sxs-lookup"><span data-stu-id="83545-440">**Middle wildcards**:</span></span>

  - <span data-ttu-id="83545-441">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="83545-441">conto\*so.com</span></span>
  - <span data-ttu-id="83545-442">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="83545-442">conto~so.com</span></span>

- <span data-ttu-id="83545-443">**Caracteres curinga duplos**</span><span class="sxs-lookup"><span data-stu-id="83545-443">**Double wildcards**</span></span>

  - <span data-ttu-id="83545-444">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="83545-444">contoso.com/\*\*</span></span>
  - <span data-ttu-id="83545-445">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="83545-445">contoso.com/\*/\*</span></span>

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="83545-446">Sintaxe de par de domínios para entradas de remetentes com spoofed na Lista de Locatários De permitir/bloquear</span><span class="sxs-lookup"><span data-stu-id="83545-446">Domain pair syntax for spoofed sender entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="83545-447">Um par de domínios para um remetente com spoofed na Lista de Locatários de Permitir/Bloquear usa a seguinte sintaxe: `<Spoofed user>, <Sending infrastructure>` .</span><span class="sxs-lookup"><span data-stu-id="83545-447">A domain pair for a spoofed sender in the Tenant Allow/Block List uses the following syntax: `<Spoofed user>, <Sending infrastructure>`.</span></span>

- <span data-ttu-id="83545-448">**Usuário com spoofed**: esse valor envolve o endereço de email do usuário que é exibido na caixa **De** em clientes de email.</span><span class="sxs-lookup"><span data-stu-id="83545-448">**Spoofed user**: This value involves the email address of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="83545-449">Esse endereço também é conhecido como `5322.From` endereço.</span><span class="sxs-lookup"><span data-stu-id="83545-449">This address is also known as the `5322.From` address.</span></span> <span data-ttu-id="83545-450">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="83545-450">Valid values include:</span></span>
  - <span data-ttu-id="83545-451">Um endereço de email individual (por exemplo, chris@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="83545-451">An individual email address (for example, chris@contoso.com).</span></span>
  - <span data-ttu-id="83545-452">Um domínio de email (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="83545-452">An email domain (for example, contoso.com).</span></span>
  - <span data-ttu-id="83545-453">O caractere curinga (por exemplo, \* ).</span><span class="sxs-lookup"><span data-stu-id="83545-453">The wildcard character (for example, \*).</span></span>

- <span data-ttu-id="83545-454">**Infraestrutura de** envio : esse valor indica a origem das mensagens do usuário espouado.</span><span class="sxs-lookup"><span data-stu-id="83545-454">**Sending infrastructure**: This value indicates the source of messages from the spoofed user.</span></span> <span data-ttu-id="83545-455">Os valores válidos incluem:</span><span class="sxs-lookup"><span data-stu-id="83545-455">Valid values include:</span></span>
  - <span data-ttu-id="83545-456">O domínio encontrado em um registro DNS reverso (registro PTR) do endereço IP do servidor de email de origem (por exemplo, fabrikam.com).</span><span class="sxs-lookup"><span data-stu-id="83545-456">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address (for example, fabrikam.com).</span></span>
  - <span data-ttu-id="83545-457">Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="83545-457">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

<span data-ttu-id="83545-458">Aqui estão alguns exemplos de pares de domínio válidos para identificar os envios com spoofed:</span><span class="sxs-lookup"><span data-stu-id="83545-458">Here are some examples of valid domain pairs to identify spoofed senders:</span></span>

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

<span data-ttu-id="83545-459">O número máximo de entradas de remetentes com spoofed é 1000.</span><span class="sxs-lookup"><span data-stu-id="83545-459">The maximum number of spoofed sender entries is 1000.</span></span>

<span data-ttu-id="83545-460">Adicionar um par de domínios  só permite ou bloqueia a combinação do usuário e da *infraestrutura* de envio.</span><span class="sxs-lookup"><span data-stu-id="83545-460">Adding a domain pair only allows or blocks the *combination* of the spoofed user *and* the sending infrastructure.</span></span> <span data-ttu-id="83545-461">Ele não permite emails do usuário com spoofed de qualquer origem, nem permite emails da fonte de infraestrutura de envio para qualquer usuário com spoofed.</span><span class="sxs-lookup"><span data-stu-id="83545-461">It does not allow email from the spoofed user from any source, nor does it allow email from the sending infrastructure source for any spoofed user.</span></span> 

<span data-ttu-id="83545-462">Por exemplo, você adiciona uma entrada de autorização para o seguinte par de domínio:</span><span class="sxs-lookup"><span data-stu-id="83545-462">For example, you add an allow entry for the following domain pair:</span></span>

- <span data-ttu-id="83545-463">**Domínio**: gmail.com</span><span class="sxs-lookup"><span data-stu-id="83545-463">**Domain**: gmail.com</span></span>
- <span data-ttu-id="83545-464">**Infraestrutura**: tms.mx.com</span><span class="sxs-lookup"><span data-stu-id="83545-464">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="83545-465">Somente as mensagens desse domínio *e o* par de infraestrutura de envio podem ser falsas.</span><span class="sxs-lookup"><span data-stu-id="83545-465">Only messages from that domain *and* sending infrastructure pair are allowed to spoof.</span></span> <span data-ttu-id="83545-466">Outros senders que tentam gmail.com não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="83545-466">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="83545-467">As mensagens de senders em outros domínios provenientes tms.mx.com são verificadas por inteligência falsa.</span><span class="sxs-lookup"><span data-stu-id="83545-467">Messages from senders in other domains originating from tms.mx.com are checked by spoof intelligence.</span></span>
