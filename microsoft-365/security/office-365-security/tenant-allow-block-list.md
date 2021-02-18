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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar os bloqueios e as autorizações na Lista de Bloqueios/Permitir Locatários no portal de Segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 250b6223ffe663e0cd950069a3c3c7827b4aa57b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290160"
---
# <a name="manage-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-103">Gerenciar a lista de Permissões/Bloqueios do Locatário</span><span class="sxs-lookup"><span data-stu-id="39cc3-103">Manage the Tenant Allow/Block List</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="39cc3-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="39cc3-104">**Applies to**</span></span>
- [<span data-ttu-id="39cc3-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="39cc3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="39cc3-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="39cc3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="39cc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39cc3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

> [!NOTE]
>
> <span data-ttu-id="39cc3-108">Os recursos descritos neste artigo estão na visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="39cc3-108">The features described in this article are in Preview, are subject to change, and are not available in all organizations.</span></span>
>
> <span data-ttu-id="39cc3-109">Você não pode configurar **itens** permitidos na Lista de Permissão/Bloqueio de Locatários no momento.</span><span class="sxs-lookup"><span data-stu-id="39cc3-109">You can't **configure** allowed items in the Tenant Allow/Block List at this time.</span></span>

<span data-ttu-id="39cc3-110">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode não concordar com o veredito de filtragem do EOP.</span><span class="sxs-lookup"><span data-stu-id="39cc3-110">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="39cc3-111">Por exemplo, uma boa mensagem pode ser marcada como ruim (um falso positivo) ou uma mensagem ruim pode ser permitida (um falso negativo).</span><span class="sxs-lookup"><span data-stu-id="39cc3-111">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="39cc3-112">A Lista de Bloqueio & s/Bloqueios de Locatários no Centro de Conformidade e Segurança oferece uma maneira de substituir manualmente os vereditos de filtragem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39cc3-112">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="39cc3-113">A Lista de Bloqueios/Permitir Locatários é usada durante o fluxo de emails e no momento dos cliques do usuário.</span><span class="sxs-lookup"><span data-stu-id="39cc3-113">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="39cc3-114">Você pode especificar URLs ou arquivos para sempre bloquear.</span><span class="sxs-lookup"><span data-stu-id="39cc3-114">You can specify URLs or files to always block.</span></span>

<span data-ttu-id="39cc3-115">Este artigo descreve como configurar entradas na Lista de Bloqueios/Permitir Locatários no Centro de Conformidade do & de Segurança ou no PowerShell (organizações do PowerShell do Exchange Online para Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="39cc3-115">This article describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39cc3-116">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="39cc3-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="39cc3-117">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="39cc3-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="39cc3-118">Para ir diretamente para a página **Permitir/Bloquear Lista** de Locatários, use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="39cc3-118">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="39cc3-119">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="39cc3-119">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="39cc3-120">Para encontrar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um Prompt de Comando:</span><span class="sxs-lookup"><span data-stu-id="39cc3-120">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="39cc3-121">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="39cc3-121">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="39cc3-122">Não há suporte para valores de hash perceptual (pHash).</span><span class="sxs-lookup"><span data-stu-id="39cc3-122">Perceptual hash (pHash) values are not supported.</span></span>

- <span data-ttu-id="39cc3-123">Os valores de URL disponíveis são descritos na sintaxe da URL para a seção [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="39cc3-123">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

- <span data-ttu-id="39cc3-124">A Lista de Bloqueios/Permitir Locatários permite um máximo de 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="39cc3-124">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="39cc3-125">Uma entrada deve estar ativa dentro de 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-125">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="39cc3-126">Por padrão, as entradas na Lista de Bloqueios/Bloqueios de Locatários expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="39cc3-126">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="39cc3-127">Você pode especificar uma data ou defini-la para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="39cc3-127">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="39cc3-128">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="39cc3-128">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="39cc3-129">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="39cc3-129">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="39cc3-130">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="39cc3-130">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="39cc3-131">Para adicionar e remover valores da Lista de Bloqueios/Permitir  Locatários, você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="39cc3-131">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="39cc3-132">Para acesso somente leitura à Lista de Locatários Permitir/Bloquear, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="39cc3-132">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="39cc3-133">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="39cc3-133">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="39cc3-134">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-134">**Notes**:</span></span>

  - <span data-ttu-id="39cc3-135">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="39cc3-135">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="39cc3-136">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="39cc3-136">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="39cc3-137">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="39cc3-137">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-138">Usar o Centro de Conformidade & segurança para criar entradas de URL na Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-138">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39cc3-139">Para obter detalhes sobre a sintaxe para entradas de URL, consulte a sintaxe da URL para a seção [Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="39cc3-139">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this article.</span></span>

1. <span data-ttu-id="39cc3-140">No Centro de Conformidade & Segurança, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="39cc3-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39cc3-141">Na página **Permitir/Bloquear Lista** de Locatários, verifique se a **guia URLs** está selecionada e clique em **Bloquear**</span><span class="sxs-lookup"><span data-stu-id="39cc3-141">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Block**</span></span>

3. <span data-ttu-id="39cc3-142">No flyout **Bloquear URLs** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="39cc3-142">In the **Block URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="39cc3-143">**Adicione URLs para bloquear:** insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="39cc3-143">**Add URLs to block**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="39cc3-144">**Nunca expirar:** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="39cc3-144">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="39cc3-145">Verifique se a configuração está desligada ( Alternar) e use a caixa Expira na caixa Para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="39cc3-145">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="39cc3-146">ou</span><span class="sxs-lookup"><span data-stu-id="39cc3-146">or</span></span>

     - <span data-ttu-id="39cc3-147">Mova o alternância para a direita para configurar as entradas para nunca expirarem:</span><span class="sxs-lookup"><span data-stu-id="39cc3-147">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="39cc3-149">.</span><span class="sxs-lookup"><span data-stu-id="39cc3-149">.</span></span>

   - <span data-ttu-id="39cc3-150">**Observação opcional:** insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="39cc3-150">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="39cc3-151">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="39cc3-151">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-152">Usar o Centro de Conformidade & segurança para criar entradas de arquivo na Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-152">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="39cc3-153">No Centro de Conformidade & Segurança, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="39cc3-153">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39cc3-154">Na página **Permitir/Bloquear Lista** de Locatários, selecione a guia **Arquivos** e clique em **Bloquear.**</span><span class="sxs-lookup"><span data-stu-id="39cc3-154">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Block**.</span></span>

3. <span data-ttu-id="39cc3-155">No menu **Adicionar arquivos para bloquear o** menu desdogurado que aparece, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="39cc3-155">In the **Add files to block** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="39cc3-156">**Adicionar hashes de** arquivo: insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="39cc3-156">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="39cc3-157">**Nunca expirar:** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="39cc3-157">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="39cc3-158">Verifique se a configuração está desligada ( Alternar) e use a caixa Expira na caixa Para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração para as entradas. </span><span class="sxs-lookup"><span data-stu-id="39cc3-158">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="39cc3-159">ou</span><span class="sxs-lookup"><span data-stu-id="39cc3-159">or</span></span>

     - <span data-ttu-id="39cc3-160">Mova o alternância para a direita para configurar as entradas para nunca expirarem:</span><span class="sxs-lookup"><span data-stu-id="39cc3-160">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="39cc3-162">.</span><span class="sxs-lookup"><span data-stu-id="39cc3-162">.</span></span>

   - <span data-ttu-id="39cc3-163">**Observação opcional:** insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="39cc3-163">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="39cc3-164">Quando terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="39cc3-164">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-165">Usar o Centro de Conformidade & segurança para exibir entradas na Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-165">Use the Security & Compliance Center to view entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="39cc3-166">No Centro de Conformidade & Segurança, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="39cc3-166">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39cc3-167">Selecione a **guia URLs** ou a **guia** Arquivos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-167">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="39cc3-168">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="39cc3-168">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="39cc3-169">**Valor:** a URL ou o hash do arquivo.</span><span class="sxs-lookup"><span data-stu-id="39cc3-169">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="39cc3-170">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="39cc3-170">**Last updated date**</span></span>
- <span data-ttu-id="39cc3-171">**Data de expiração**</span><span class="sxs-lookup"><span data-stu-id="39cc3-171">**Expiration date**</span></span>
- <span data-ttu-id="39cc3-172">**Observação**</span><span class="sxs-lookup"><span data-stu-id="39cc3-172">**Note**</span></span>

<span data-ttu-id="39cc3-173">Clique **em** Pesquisar, insira todo ou parte de um valor e pressione ENTER para encontrar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="39cc3-173">Click **Search**, enter all or part of a value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="39cc3-174">Quando terminar, clique em Limpar ícone **Limpar** ![ ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) pesquisa.</span><span class="sxs-lookup"><span data-stu-id="39cc3-174">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="39cc3-175">Clique **em Filtro**.</span><span class="sxs-lookup"><span data-stu-id="39cc3-175">Click **Filter**.</span></span> <span data-ttu-id="39cc3-176">No  menu desdopante Filtro exibido, de configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="39cc3-176">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="39cc3-177">**Nunca expirar**: Selecione desligado: ![ Alternar ](../../media/scc-toggle-off.png) ou desligar: ![ ](../../media/scc-toggle-on.png) Alternar.</span><span class="sxs-lookup"><span data-stu-id="39cc3-177">**Never expire**: Select off: ![Toggle off](../../media/scc-toggle-off.png) or on: ![Toggle on](../../media/scc-toggle-on.png).</span></span>

- <span data-ttu-id="39cc3-178">**Last updated:** Select a start date (**From**), an end date (**To**) or both.</span><span class="sxs-lookup"><span data-stu-id="39cc3-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="39cc3-179">**Data de expiração:** selecione uma data de início (**De**), uma data de término (**Para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="39cc3-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="39cc3-180">Quando terminar, clique em **Aplicar.**</span><span class="sxs-lookup"><span data-stu-id="39cc3-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="39cc3-181">Para limpar os filtros existentes, clique em **Filtro** e, no flyout **Filtro** exibido, clique em **Limpar filtros.**</span><span class="sxs-lookup"><span data-stu-id="39cc3-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-182">Usar o Centro de Conformidade & segurança para modificar entradas de bloco na Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-182">Use the Security & Compliance Center to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39cc3-183">Não é possível modificar os valores de arquivo ou URL bloqueados existentes em uma entrada.</span><span class="sxs-lookup"><span data-stu-id="39cc3-183">You can't modify the existing blocked URL or file values within an entry.</span></span> <span data-ttu-id="39cc3-184">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="39cc3-184">To modify these values, you need to delete and recreate the entry.</span></span>

1. <span data-ttu-id="39cc3-185">No Centro de Conformidade & Segurança, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="39cc3-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39cc3-186">Selecione a **guia URLs** ou a **guia** Arquivos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="39cc3-187">Selecione a entrada de bloco que você deseja modificar e clique em **Editar** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) ícone.</span><span class="sxs-lookup"><span data-stu-id="39cc3-187">Select the block entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="39cc3-188">No menu desdopo que aparece, de configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="39cc3-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="39cc3-189">**Nunca expirar:** faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="39cc3-189">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="39cc3-190">Verifique se a configuração está desligada ( Alternar) e use a caixa Expira na caixa para especificar a data de ![ ](../../media/scc-toggle-off.png) expiração da entrada. </span><span class="sxs-lookup"><span data-stu-id="39cc3-190">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="39cc3-191">ou</span><span class="sxs-lookup"><span data-stu-id="39cc3-191">or</span></span>

     - <span data-ttu-id="39cc3-192">Mova o alternância para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="39cc3-192">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/scc-toggle-on.png)<span data-ttu-id="39cc3-194">.</span><span class="sxs-lookup"><span data-stu-id="39cc3-194">.</span></span>

   - <span data-ttu-id="39cc3-195">**Observação opcional:** insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="39cc3-195">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="39cc3-196">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="39cc3-196">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-197">Usar o Centro de Conformidade & segurança para remover entradas de bloqueio da Lista de Bloqueios/Bloqueios de Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-197">Use the Security & Compliance Center to remove block entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="39cc3-198">No Centro de Conformidade & Segurança, vá para **Listas** de \>  \> **Bloqueios/Permitir** Locatários da Política de Gerenciamento de Ameaças.</span><span class="sxs-lookup"><span data-stu-id="39cc3-198">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="39cc3-199">Selecione a **guia URLs** ou a **guia** Arquivos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-199">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="39cc3-200">Selecione a entrada de bloco que você deseja remover e clique no ícone **Excluir** ![ ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) Exclusão.</span><span class="sxs-lookup"><span data-stu-id="39cc3-200">Select the block entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="39cc3-201">Na caixa de diálogo de aviso exibida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="39cc3-201">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-202">Usar o PowerShell do Exchange Online ou o PowerShell do EOP autônomo para configurar a Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-202">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-block-entries-to-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-203">Usar o PowerShell para adicionar entradas de bloco à Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-203">Use PowerShell to add block entries to the Tenant Allow/Block List</span></span>

<span data-ttu-id="39cc3-204">Para adicionar entradas de bloco na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="39cc3-204">To add block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Block -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="39cc3-205">Este exemplo adiciona uma entrada de URL de bloco para contoso.com e todos os sub-contoso.com (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="39cc3-205">This example adds a block URL entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="39cc3-206">Como não usamos os parâmetros ExpirationDate ou NoExpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="39cc3-206">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Block -Entries ~contoso.com
```

<span data-ttu-id="39cc3-207">Este exemplo adiciona uma entrada de arquivo de bloco para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="39cc3-207">This example adds a block file entry for the specified files that never expires.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="39cc3-208">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="39cc3-208">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-209">Usar o PowerShell para exibir entradas na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="39cc3-209">Use PowerShell to view entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39cc3-210">Para exibir entradas na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="39cc3-210">To view entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Block] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="39cc3-211">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="39cc3-211">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

<span data-ttu-id="39cc3-212">Este exemplo retorna informações para o valor de hash de arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="39cc3-212">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="39cc3-213">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="39cc3-213">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-block-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-214">Usar o PowerShell para modificar entradas de bloco na Lista de Locatários Permitir/Bloquear</span><span class="sxs-lookup"><span data-stu-id="39cc3-214">Use PowerShell to modify block entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="39cc3-215">Não é possível modificar a URL ou os valores de arquivo existentes dentro de uma entrada de bloco.</span><span class="sxs-lookup"><span data-stu-id="39cc3-215">You can't modify the existing URL or file values within a block entry.</span></span> <span data-ttu-id="39cc3-216">Para modificar esses valores, você precisa excluir e recriar a entrada.</span><span class="sxs-lookup"><span data-stu-id="39cc3-216">To modify these values, you need to delete and recreate the entry.</span></span>

<span data-ttu-id="39cc3-217">Para modificar entradas de bloco na Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="39cc3-217">To modify block entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Block] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="39cc3-218">Este exemplo altera a data de expiração da entrada de bloco especificada.</span><span class="sxs-lookup"><span data-stu-id="39cc3-218">This example changes the expiration date of the specified block entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="39cc3-219">Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="39cc3-219">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-block-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-220">Usar o PowerShell para remover entradas de bloco da Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-220">Use PowerShell to remove block entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="39cc3-221">Para remover entradas de bloco da Lista de Bloqueios/Permitir Locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="39cc3-221">To remove block entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="39cc3-222">Este exemplo remove a entrada de URL de bloco especificada da Lista de Bloqueios/Permitir Locatários.</span><span class="sxs-lookup"><span data-stu-id="39cc3-222">This example removes the specified block URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="39cc3-223">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="39cc3-223">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="39cc3-224">Sintaxe de URL para a Lista de Bloqueios/Permitir Locatários</span><span class="sxs-lookup"><span data-stu-id="39cc3-224">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="39cc3-225">Os endereços IP4v e IPv6 são permitidos, mas as portas TCP/UDP não.</span><span class="sxs-lookup"><span data-stu-id="39cc3-225">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="39cc3-226">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="39cc3-226">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="39cc3-227">Unicode não é suportado, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="39cc3-227">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="39cc3-228">Os nomes de host serão permitidos se todas as instruções a seguir são verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="39cc3-228">Hostnames are allowed if all of the following statements are true:</span></span>
  - <span data-ttu-id="39cc3-229">O nome do host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="39cc3-229">The hostname contains a period.</span></span>
  - <span data-ttu-id="39cc3-230">Há pelo menos um caractere à esquerda do ponto.</span><span class="sxs-lookup"><span data-stu-id="39cc3-230">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="39cc3-231">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="39cc3-231">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="39cc3-232">Por exemplo, `t.co` é permitido; `.com` ou não são `contoso.` permitidos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-232">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="39cc3-233">Os subcaminhos não estão implícitos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-233">Subpaths are not implied.</span></span>

  <span data-ttu-id="39cc3-234">Por exemplo, `contoso.com` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="39cc3-234">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="39cc3-235">Caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="39cc3-235">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="39cc3-236">Um caractere curinga esquerdo deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="39cc3-236">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="39cc3-237">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="39cc3-237">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="39cc3-238">Um curinga direito deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="39cc3-238">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="39cc3-239">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou não são `contoso.com/ab*` permitidos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-239">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="39cc3-240">Todos os subcaminhos não estão implícitos por um caractere curinga direito.</span><span class="sxs-lookup"><span data-stu-id="39cc3-240">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="39cc3-241">Por exemplo, `contoso.com/*` não inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="39cc3-241">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="39cc3-242">`*.com*` é inválido (não é um domínio que pode ser resolvido e o curinga direito não segue uma barra).</span><span class="sxs-lookup"><span data-stu-id="39cc3-242">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="39cc3-243">Caracteres curinga não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="39cc3-243">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="39cc3-244">O caractere til (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="39cc3-244">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="39cc3-245">Um til esquerdo implica em um domínio e em todos os sub-domínios.</span><span class="sxs-lookup"><span data-stu-id="39cc3-245">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="39cc3-246">Por `~contoso.com` exemplo, inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="39cc3-246">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="39cc3-247">Entradas de URL que contêm protocolos (por exemplo, , ou ) falharão, porque as entradas de URL se `http://` aplicam a todos os `https://` `ftp://` protocolos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-247">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="39cc3-248">Um nome de usuário ou senha não tem suporte ou é necessário.</span><span class="sxs-lookup"><span data-stu-id="39cc3-248">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="39cc3-249">Aspas (' ou ") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="39cc3-249">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="39cc3-250">Uma URL deve incluir todos os redirecionamentos sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="39cc3-250">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="39cc3-251">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="39cc3-251">URL entry scenarios</span></span>

<span data-ttu-id="39cc3-252">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="39cc3-252">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="39cc3-253">Cenário: sem caracteres curinga</span><span class="sxs-lookup"><span data-stu-id="39cc3-253">Scenario: No wildcards</span></span>

<span data-ttu-id="39cc3-254">**Entrada:**`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="39cc3-254">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="39cc3-255">**Permitir a combinação**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-255">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="39cc3-256">**Allow not matched**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-256">**Allow not matched**:</span></span>

  - <span data-ttu-id="39cc3-257">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-257">abc-contoso.com</span></span>
  - <span data-ttu-id="39cc3-258">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-258">contoso.com/a</span></span>
  - <span data-ttu-id="39cc3-259">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-259">payroll.contoso.com</span></span>
  - <span data-ttu-id="39cc3-260">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-260">test.com/contoso.com</span></span>
  - <span data-ttu-id="39cc3-261">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-261">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="39cc3-262">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-262">www.contoso.com</span></span>
  - <span data-ttu-id="39cc3-263">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-263">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="39cc3-264">**Block match**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-264">**Block match**:</span></span>

  - <span data-ttu-id="39cc3-265">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-265">contoso.com</span></span>
  - <span data-ttu-id="39cc3-266">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-266">contoso.com/a</span></span>
  - <span data-ttu-id="39cc3-267">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-267">payroll.contoso.com</span></span>
  - <span data-ttu-id="39cc3-268">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-268">test.com/contoso.com</span></span>
  - <span data-ttu-id="39cc3-269">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-269">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="39cc3-270">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-270">www.contoso.com</span></span>
  - <span data-ttu-id="39cc3-271">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-271">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="39cc3-272">**Bloqueio não corresponder**: abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-272">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="39cc3-273">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="39cc3-273">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="39cc3-274">**Entrada:**`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="39cc3-274">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="39cc3-275">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-275">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39cc3-276">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-276">www.contoso.com</span></span>
  - <span data-ttu-id="39cc3-277">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-277">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="39cc3-278">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-278">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39cc3-279">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-279">123contoso.com</span></span>
  - <span data-ttu-id="39cc3-280">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-280">contoso.com</span></span>
  - <span data-ttu-id="39cc3-281">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-281">test.com/contoso.com</span></span>
  - <span data-ttu-id="39cc3-282">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="39cc3-282">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="39cc3-283">Cenário: curinga direito na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="39cc3-283">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="39cc3-284">**Entrada:**`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="39cc3-284">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="39cc3-285">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-285">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39cc3-286">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="39cc3-286">contoso.com/a/b</span></span>
  - <span data-ttu-id="39cc3-287">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="39cc3-287">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="39cc3-288">contoso.com/a/?q=joe@t.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-288">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="39cc3-289">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-289">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39cc3-290">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-290">contoso.com</span></span>
  - <span data-ttu-id="39cc3-291">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-291">contoso.com/a</span></span>
  - <span data-ttu-id="39cc3-292">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-292">www.contoso.com</span></span>
  - <span data-ttu-id="39cc3-293">www.contoso.com/q=a@contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-293">www.contoso.com/q=a@contoso.com</span></span>

#### <a name="scenario-left-tilde"></a><span data-ttu-id="39cc3-294">Cenário: bloco esquerdo</span><span class="sxs-lookup"><span data-stu-id="39cc3-294">Scenario: Left tilde</span></span>

<span data-ttu-id="39cc3-295">**Entrada:**`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="39cc3-295">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="39cc3-296">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-296">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39cc3-297">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-297">contoso.com</span></span>
  - <span data-ttu-id="39cc3-298">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-298">www.contoso.com</span></span>
  - <span data-ttu-id="39cc3-299">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-299">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="39cc3-300">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-300">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39cc3-301">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-301">123contoso.com</span></span>
  - <span data-ttu-id="39cc3-302">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="39cc3-302">contoso.com/abc</span></span>
  - <span data-ttu-id="39cc3-303">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="39cc3-303">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="39cc3-304">Cenário: sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="39cc3-304">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="39cc3-305">**Entrada:**`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="39cc3-305">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="39cc3-306">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-306">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39cc3-307">contoso.com/?q=whatever@fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-307">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="39cc3-308">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-308">contoso.com/a</span></span>
  - <span data-ttu-id="39cc3-309">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="39cc3-309">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="39cc3-310">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="39cc3-310">contoso.com/ab</span></span>
  - <span data-ttu-id="39cc3-311">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="39cc3-311">contoso.com/b</span></span>
  - <span data-ttu-id="39cc3-312">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="39cc3-312">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="39cc3-313">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="39cc3-313">contoso.com/ba</span></span>

- <span data-ttu-id="39cc3-314">**Allow not matched** and **Block not matched**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-314">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="39cc3-315">Cenário: subdomínio de curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="39cc3-315">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="39cc3-316">**Entrada:**`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="39cc3-316">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="39cc3-317">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-317">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39cc3-318">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="39cc3-318">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="39cc3-319">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="39cc3-319">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="39cc3-320">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-320">www.contoso.com/a</span></span>
  - <span data-ttu-id="39cc3-321">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="39cc3-321">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="39cc3-322">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="39cc3-322">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="39cc3-323">**Allow not matched** and **Block not matched**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="39cc3-323">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="39cc3-324">Cenário: til esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="39cc3-324">Scenario: Left and right tilde</span></span>

<span data-ttu-id="39cc3-325">**Entrada:**`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="39cc3-325">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="39cc3-326">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-326">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39cc3-327">contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-327">contoso.com</span></span>
  - <span data-ttu-id="39cc3-328">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-328">contoso.com/a</span></span>
  - <span data-ttu-id="39cc3-329">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-329">www.contoso.com</span></span>
  - <span data-ttu-id="39cc3-330">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="39cc3-330">www.contoso.com/b</span></span>
  - <span data-ttu-id="39cc3-331">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-331">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="39cc3-332">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-332">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39cc3-333">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-333">123contoso.com</span></span>
  - <span data-ttu-id="39cc3-334">contoso.org</span><span class="sxs-lookup"><span data-stu-id="39cc3-334">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="39cc3-335">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="39cc3-335">Scenario: IP address</span></span>

<span data-ttu-id="39cc3-336">**Entrada:**`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="39cc3-336">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="39cc3-337">**Permitir match** e **Block match:** 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="39cc3-337">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="39cc3-338">**Allow not matched** and **Block not matched**:</span><span class="sxs-lookup"><span data-stu-id="39cc3-338">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="39cc3-339">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-339">1.2.3.4/a</span></span>
  - <span data-ttu-id="39cc3-340">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="39cc3-340">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="39cc3-341">Endereço IP com curinga direito</span><span class="sxs-lookup"><span data-stu-id="39cc3-341">IP address with right wildcard</span></span>

<span data-ttu-id="39cc3-342">**Entrada:**`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="39cc3-342">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="39cc3-343">**Permitir a match** e **a block match:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-343">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="39cc3-344">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="39cc3-344">1.2.3.4/b</span></span>
  - <span data-ttu-id="39cc3-345">1.2.3.4/baaaa</span><span class="sxs-lookup"><span data-stu-id="39cc3-345">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="39cc3-346">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="39cc3-346">Examples of invalid entries</span></span>

<span data-ttu-id="39cc3-347">As entradas a seguir são inválidas:</span><span class="sxs-lookup"><span data-stu-id="39cc3-347">The following entries are invalid:</span></span>

- <span data-ttu-id="39cc3-348">**Valores de domínio ausentes ou inválidos:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-348">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="39cc3-349">contoso</span><span class="sxs-lookup"><span data-stu-id="39cc3-349">contoso</span></span>
  - <span data-ttu-id="39cc3-350">\*.contoso.\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-350">\*.contoso.\*</span></span>
  - <span data-ttu-id="39cc3-351">\*.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-351">\*.com</span></span>
  - <span data-ttu-id="39cc3-352">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="39cc3-352">\*.pdf</span></span>

- <span data-ttu-id="39cc3-353">**Caractere curinga no texto ou sem caracteres de espaçamento:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-353">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="39cc3-354">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-354">\*contoso.com</span></span>
  - <span data-ttu-id="39cc3-355">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-355">contoso.com\*</span></span>
  - <span data-ttu-id="39cc3-356">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="39cc3-356">\*1.2.3.4</span></span>
  - <span data-ttu-id="39cc3-357">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-357">1.2.3.4\*</span></span>
  - <span data-ttu-id="39cc3-358">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-358">contoso.com/a\*</span></span>
  - <span data-ttu-id="39cc3-359">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-359">contoso.com/ab\*</span></span>

- <span data-ttu-id="39cc3-360">**Endereços IP com portas:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-360">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="39cc3-361">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="39cc3-361">contoso.com:443</span></span>
  - <span data-ttu-id="39cc3-362">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="39cc3-362">abc.contoso.com:25</span></span>

- <span data-ttu-id="39cc3-363">**Caracteres curinga não descritivos:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-363">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="39cc3-364">\*.\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-364">\*.\*</span></span>

- <span data-ttu-id="39cc3-365">**Curingas intermediários:**</span><span class="sxs-lookup"><span data-stu-id="39cc3-365">**Middle wildcards**:</span></span>

  - <span data-ttu-id="39cc3-366">conto \* so.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-366">conto\*so.com</span></span>
  - <span data-ttu-id="39cc3-367">conto~so.com</span><span class="sxs-lookup"><span data-stu-id="39cc3-367">conto~so.com</span></span>

- <span data-ttu-id="39cc3-368">**Curingas duplos**</span><span class="sxs-lookup"><span data-stu-id="39cc3-368">**Double wildcards**</span></span>

  - <span data-ttu-id="39cc3-369">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-369">contoso.com/\*\*</span></span>
  - <span data-ttu-id="39cc3-370">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="39cc3-370">contoso.com/\*/\*</span></span>
