---
title: Gerenciar seus arquivos e URLs permitidos e bloqueados na lista de permissões/bloqueios de locatários
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
ROBOTS: NOINDEX, NOFOLLOW
description: Os administradores podem saber como configurar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários no centro de conformidade de & de segurança.
ms.openlocfilehash: 0143ee2601a4cb9593c79f8c6c62d1f06914088f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613415"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-103">Gerenciar URLs e arquivos na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="c5f13-104">Os recursos descritos neste tópico estão em visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="c5f13-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="c5f13-105">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredicto de filtragem EOP.</span><span class="sxs-lookup"><span data-stu-id="c5f13-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="c5f13-106">Por exemplo, uma boa mensagem pode ser marcada como ruim (falso positivo) ou uma mensagem inválida pode ser permitida por meio de (falso negativo).</span><span class="sxs-lookup"><span data-stu-id="c5f13-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="c5f13-107">A lista de permissões/bloqueios de locatários no centro de conformidade do & de segurança oferece uma maneira de substituir manualmente o Microsoft 365 Filtering verdicts.</span><span class="sxs-lookup"><span data-stu-id="c5f13-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="c5f13-108">A lista de permissões/bloqueios de locatários é usada durante o fluxo de emails e no momento em que o usuário clica.</span><span class="sxs-lookup"><span data-stu-id="c5f13-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="c5f13-109">Você pode especificar URLs e arquivos para permitir ou bloquear na lista de permissões/bloqueios de locatários.</span><span class="sxs-lookup"><span data-stu-id="c5f13-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="c5f13-110">Este tópico descreve como configurar entradas na lista de permissões/bloqueios de locatário no centro de conformidade & segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; autônomo do EOP PowerShell para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c5f13-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c5f13-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c5f13-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c5f13-112">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c5f13-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c5f13-113">Para ir diretamente para a página **lista de permissões/bloqueios de locatários** , use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="c5f13-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="c5f13-114">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5f13-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="c5f13-115">Para localizar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="c5f13-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="c5f13-116">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="c5f13-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="c5f13-117">Os valores de hash perceptual (pHash) não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="c5f13-118">Os valores de URL disponíveis são descritos na [sintaxe da URL para a seção lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c5f13-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="c5f13-119">A lista de permissões/bloqueios de locatários permite um máximo de 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5f13-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="c5f13-120">Uma entrada deve estar ativa em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="c5f13-121">As entradas de bloco têm precedência sobre as entradas de permissão.</span><span class="sxs-lookup"><span data-stu-id="c5f13-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="c5f13-122">Por padrão, as entradas na lista de permissões/bloqueios de locatários expirarão após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c5f13-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="c5f13-123">Você pode especificar uma data ou defini-las para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="c5f13-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="c5f13-124">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5f13-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c5f13-125">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5f13-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c5f13-126">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-126">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c5f13-127">Para adicionar e remover valores da lista de permissões/bloqueios de locatário, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** .</span><span class="sxs-lookup"><span data-stu-id="c5f13-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="c5f13-128">Para acesso somente leitura à lista de permissões/bloqueios de locatário, você precisa ser membro do grupo de função **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="c5f13-128">For read-only access to the Tenant Allow/Block List, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="c5f13-129">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c5f13-129">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-130">Usar o centro de conformidade de & de segurança para criar entradas de URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-130">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c5f13-131">Para obter detalhes sobre a sintaxe das entradas de URL, consulte a sintaxe da URL da seção [lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c5f13-131">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="c5f13-132">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="c5f13-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c5f13-133">Na página **lista de permissões/bloqueios de locatários** , verifique se a guia **URLs** está selecionada e clique em **Adicionar**</span><span class="sxs-lookup"><span data-stu-id="c5f13-133">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="c5f13-134">No submenu **adicionar novas URLs** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c5f13-134">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c5f13-135">**Adicionar URLs com curingas**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c5f13-135">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c5f13-136">**Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** as URLs especificadas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-136">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="c5f13-137">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c5f13-137">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c5f13-138">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-138">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c5f13-139">ou</span><span class="sxs-lookup"><span data-stu-id="c5f13-139">or</span></span>

     - <span data-ttu-id="c5f13-140">Mova a opção para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="c5f13-140">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c5f13-142">.</span><span class="sxs-lookup"><span data-stu-id="c5f13-142">.</span></span>

   - <span data-ttu-id="c5f13-143">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-143">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c5f13-144">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-144">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-145">Usar o centro de conformidade de & de segurança para criar entradas de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-145">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c5f13-146">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="c5f13-146">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c5f13-147">Na página **lista de permissões/bloqueios de locatários** , selecione **arquivos** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-147">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="c5f13-148">No submenu **Adicionar novos arquivos** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c5f13-148">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c5f13-149">**Adicionar hashes de arquivo**: Insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="c5f13-149">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="c5f13-150">**Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="c5f13-150">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="c5f13-151">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c5f13-151">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c5f13-152">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-152">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="c5f13-153">ou</span><span class="sxs-lookup"><span data-stu-id="c5f13-153">or</span></span>

     - <span data-ttu-id="c5f13-154">Mova a opção para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="c5f13-154">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c5f13-156">.</span><span class="sxs-lookup"><span data-stu-id="c5f13-156">.</span></span>

   - <span data-ttu-id="c5f13-157">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-157">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="c5f13-158">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-158">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-159">Use o centro de conformidade de & de segurança para exibir entradas de URL e de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-159">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c5f13-160">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="c5f13-160">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c5f13-161">Selecione a guia **URLs** ou a guia **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="c5f13-161">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="c5f13-162">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="c5f13-162">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="c5f13-163">**Valor**: a URL ou o hash do arquivo.</span><span class="sxs-lookup"><span data-stu-id="c5f13-163">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="c5f13-164">**Ação**: **Bloquear** ou **permitir**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-164">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="c5f13-165">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="c5f13-165">**Last updated date**</span></span>
- <span data-ttu-id="c5f13-166">**Data de vencimento**</span><span class="sxs-lookup"><span data-stu-id="c5f13-166">**Expiration date**</span></span>
- <span data-ttu-id="c5f13-167">**Observação**</span><span class="sxs-lookup"><span data-stu-id="c5f13-167">**Note**</span></span>

<span data-ttu-id="c5f13-168">Clique em **Agrupar** para agrupar as entradas **por ação** (**Bloquear** ou **permitir**) ou **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-168">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="c5f13-169">Clique em **Pesquisar**, digite todo ou parte de um valor de URL ou de arquivo e pressione ENTER para localizar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="c5f13-169">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="c5f13-170">Quando tiver terminado, clique em **limpar** o ![ ícone pesquisa limpar pesquisa ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="c5f13-170">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="c5f13-171">Clique em **filtro**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-171">Click **Filter**.</span></span> <span data-ttu-id="c5f13-172">No submenu de **filtro** que aparece, configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c5f13-172">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="c5f13-173">**Ação**: selecione **permitir**, **Bloquear** ou ambos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-173">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="c5f13-174">**Nunca expirar**: selecione Desativado (desativar ![ ](../../media/scc-toggle-off.png) ) ou ativado ( ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="c5f13-174">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="c5f13-175">**Última atualização**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-175">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="c5f13-176">**Data de validade**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-176">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="c5f13-177">Quando tiver concluído, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-177">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="c5f13-178">Para limpar filtros existentes, clique em **Filtrar**e, no submenu de **filtro** que aparece, clique em **limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-178">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-179">Use o centro de conformidade de & de segurança para modificar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-179">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c5f13-180">Você não pode modificar a URL ou o valor do arquivo propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="c5f13-180">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="c5f13-181">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="c5f13-181">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="c5f13-182">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="c5f13-182">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c5f13-183">Selecione a guia **URLs** ou a guia **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="c5f13-183">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c5f13-184">Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="c5f13-184">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="c5f13-185">No submenu exibido, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c5f13-185">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="c5f13-186">**Bloquear/permitir**: selecione **permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-186">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="c5f13-187">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c5f13-187">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="c5f13-188">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento da entrada.</span><span class="sxs-lookup"><span data-stu-id="c5f13-188">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="c5f13-189">ou</span><span class="sxs-lookup"><span data-stu-id="c5f13-189">or</span></span>

     - <span data-ttu-id="c5f13-190">Mova a opção para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="c5f13-190">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="c5f13-192">.</span><span class="sxs-lookup"><span data-stu-id="c5f13-192">.</span></span>

   - <span data-ttu-id="c5f13-193">**Observação opcional**: insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="c5f13-193">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="c5f13-194">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-194">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-195">Use o centro de conformidade de & de segurança para remover entradas de URL e arquivos da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-195">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="c5f13-196">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="c5f13-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="c5f13-197">Selecione a guia **URLs** ou a guia **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="c5f13-197">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="c5f13-198">Selecione a entrada que você deseja remover e clique em **excluir** ![ excluir ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="c5f13-198">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="c5f13-199">Na caixa de diálogo de aviso que aparece, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="c5f13-199">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-200">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar a lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-200">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-201">Usar o PowerShell para adicionar entradas de URL e de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-201">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c5f13-202">Para adicionar entradas de URL e de arquivo na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c5f13-202">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c5f13-203">Este exemplo adiciona uma entrada de bloco de URL para contoso.com e todos os subdomínios (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c5f13-203">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="c5f13-204">Como não usamos os parâmetros ExpirationDate ou noexpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c5f13-204">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="c5f13-205">Este exemplo adiciona uma entrada de permissão de arquivo para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="c5f13-205">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="c5f13-206">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c5f13-206">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-207">Use o PowerShell para exibir as entradas de arquivo e URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-207">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c5f13-208">Para exibir as entradas de arquivo e URL na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c5f13-208">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="c5f13-209">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="c5f13-209">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="c5f13-210">Este exemplo retorna informações para o valor de hash do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="c5f13-210">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="c5f13-211">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c5f13-211">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-212">Usar o PowerShell para modificar as entradas de arquivo e URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-212">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="c5f13-213">Você não pode modificar a URL ou o valor do arquivo propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="c5f13-213">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="c5f13-214">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="c5f13-214">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="c5f13-215">Para modificar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c5f13-215">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="c5f13-216">Este exemplo altera a data de vencimento da entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="c5f13-216">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="c5f13-217">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c5f13-217">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-218">Use o PowerShell para remover as entradas de arquivo e URL da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="c5f13-218">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="c5f13-219">Para remover as entradas de arquivo e URL da lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c5f13-219">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="c5f13-220">Este exemplo remove a entrada de URL especificada da lista de permissões/bloqueios de locatário.</span><span class="sxs-lookup"><span data-stu-id="c5f13-220">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="c5f13-221">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="c5f13-221">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="c5f13-222">Sintaxe da URL para a lista de permissões/bloqueios de locatário</span><span class="sxs-lookup"><span data-stu-id="c5f13-222">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="c5f13-223">Os endereços IPv6 e IP4v são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="c5f13-223">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="c5f13-224">Extensões de nome de arquivo não são permitidas (por exemplo, Test. pdf).</span><span class="sxs-lookup"><span data-stu-id="c5f13-224">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="c5f13-225">Unicode não é suportado, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="c5f13-225">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="c5f13-226">Os nomes de host são permitidos se todas as instruções a seguir forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="c5f13-226">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="c5f13-227">O nome do host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="c5f13-227">The hostname contains a period.</span></span>
  - <span data-ttu-id="c5f13-228">Há pelo menos um caractere à esquerda do ponto.</span><span class="sxs-lookup"><span data-stu-id="c5f13-228">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="c5f13-229">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="c5f13-229">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="c5f13-230">Por exemplo, `t.co` é permitido; `.com` ou `contoso.` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-230">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="c5f13-231">Os subcaminhos não são inferidos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-231">Subpaths are not implied.</span></span>

  <span data-ttu-id="c5f13-232">Por exemplo, não `contoso.com` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c5f13-232">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="c5f13-233">Caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="c5f13-233">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="c5f13-234">Um caractere curinga à esquerda deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="c5f13-234">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="c5f13-235">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="c5f13-235">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="c5f13-236">Um caractere curinga à direita deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="c5f13-236">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="c5f13-237">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou `contoso.com/ab*` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-237">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="c5f13-238">Todos os subcaminhos não são inferidos por um caractere curinga correto.</span><span class="sxs-lookup"><span data-stu-id="c5f13-238">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="c5f13-239">Por exemplo, não `contoso.com/*` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="c5f13-239">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="c5f13-240">`*.com*`é inválido (não é um domínio resolvível e o caractere curinga correto não segue uma barra).</span><span class="sxs-lookup"><span data-stu-id="c5f13-240">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="c5f13-241">Curingas não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="c5f13-241">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="c5f13-242">O caractere til (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="c5f13-242">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="c5f13-243">Um til esquerdo implica um domínio e todos os subdomínios.</span><span class="sxs-lookup"><span data-stu-id="c5f13-243">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="c5f13-244">Por exemplo `~contoso.com` inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="c5f13-244">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="c5f13-245">As entradas de URL que contêm protocolos (por exemplo,, `http://` `https://` ou `ftp://` ) falharão, porque as entradas de URL se aplicam a todos os protocolos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-245">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="c5f13-246">Um nome de usuário ou senha não são suportados ou necessários.</span><span class="sxs-lookup"><span data-stu-id="c5f13-246">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="c5f13-247">Aspas ("ou") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="c5f13-247">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="c5f13-248">Uma URL deve incluir todos os redirecionamentos onde for possível.</span><span class="sxs-lookup"><span data-stu-id="c5f13-248">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="c5f13-249">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="c5f13-249">URL entry scenarios</span></span>

<span data-ttu-id="c5f13-250">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c5f13-250">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="c5f13-251">Cenário: sem curingas</span><span class="sxs-lookup"><span data-stu-id="c5f13-251">Scenario: No wildcards</span></span>

<span data-ttu-id="c5f13-252">**Entrada**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c5f13-252">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="c5f13-253">**Permitir correspondência**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-253">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="c5f13-254">**Permitir não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-254">**Allow not matched**:</span></span>

  - <span data-ttu-id="c5f13-255">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-255">abc-contoso.com</span></span>
  - <span data-ttu-id="c5f13-256">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-256">contoso.com/a</span></span>
  - <span data-ttu-id="c5f13-257">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-257">payroll.contoso.com</span></span>
  - <span data-ttu-id="c5f13-258">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-258">test.com/contoso.com</span></span>
  - <span data-ttu-id="c5f13-259">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-259">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c5f13-260">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-260">www.contoso.com</span></span>
  - <span data-ttu-id="c5f13-261">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="c5f13-261">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="c5f13-262">**Correspondência de bloco**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-262">**Block match**:</span></span>

  - <span data-ttu-id="c5f13-263">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-263">contoso.com</span></span>
  - <span data-ttu-id="c5f13-264">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-264">contoso.com/a</span></span>
  - <span data-ttu-id="c5f13-265">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-265">payroll.contoso.com</span></span>
  - <span data-ttu-id="c5f13-266">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-266">test.com/contoso.com</span></span>
  - <span data-ttu-id="c5f13-267">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-267">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="c5f13-268">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-268">www.contoso.com</span></span>
  - <span data-ttu-id="c5f13-269">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="c5f13-269">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="c5f13-270">**Bloquear não correspondente**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-270">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="c5f13-271">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="c5f13-271">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="c5f13-272">**Entrada**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c5f13-272">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="c5f13-273">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-273">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c5f13-274">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-274">www.contoso.com</span></span>
  - <span data-ttu-id="c5f13-275">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-275">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c5f13-276">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-276">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c5f13-277">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-277">123contoso.com</span></span>
  - <span data-ttu-id="c5f13-278">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-278">contoso.com</span></span>
  - <span data-ttu-id="c5f13-279">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-279">test.com/contoso.com</span></span>
  - <span data-ttu-id="c5f13-280">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c5f13-280">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="c5f13-281">Cenário: caractere curinga à direita na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="c5f13-281">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="c5f13-282">**Entrada**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="c5f13-282">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="c5f13-283">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-283">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c5f13-284">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="c5f13-284">contoso.com/a/b</span></span>
  - <span data-ttu-id="c5f13-285">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c5f13-285">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c5f13-286">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="c5f13-286">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="c5f13-287">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-287">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c5f13-288">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-288">contoso.com</span></span>
  - <span data-ttu-id="c5f13-289">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-289">contoso.com/a</span></span>
  - <span data-ttu-id="c5f13-290">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-290">www.contoso.com</span></span>
  - <span data-ttu-id="c5f13-291">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="c5f13-291">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="c5f13-292">Cenário: til esquerdo</span><span class="sxs-lookup"><span data-stu-id="c5f13-292">Scenario: Left tilde</span></span>

<span data-ttu-id="c5f13-293">**Entrada**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="c5f13-293">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="c5f13-294">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-294">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c5f13-295">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-295">contoso.com</span></span>
  - <span data-ttu-id="c5f13-296">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-296">www.contoso.com</span></span>
  - <span data-ttu-id="c5f13-297">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-297">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c5f13-298">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-298">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c5f13-299">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-299">123contoso.com</span></span>
  - <span data-ttu-id="c5f13-300">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c5f13-300">contoso.com/abc</span></span>
  - <span data-ttu-id="c5f13-301">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="c5f13-301">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="c5f13-302">Cenário: sufixo curinga à direita</span><span class="sxs-lookup"><span data-stu-id="c5f13-302">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="c5f13-303">**Entrada**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c5f13-303">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="c5f13-304">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-304">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c5f13-305">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="c5f13-305">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="c5f13-306">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-306">contoso.com/a</span></span>
  - <span data-ttu-id="c5f13-307">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c5f13-307">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c5f13-308">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c5f13-308">contoso.com/ab</span></span>
  - <span data-ttu-id="c5f13-309">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c5f13-309">contoso.com/b</span></span>
  - <span data-ttu-id="c5f13-310">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c5f13-310">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c5f13-311">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c5f13-311">contoso.com/ba</span></span>

- <span data-ttu-id="c5f13-312">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-312">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="c5f13-313">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="c5f13-313">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="c5f13-314">**Entrada**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="c5f13-314">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="c5f13-315">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-315">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c5f13-316">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="c5f13-316">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="c5f13-317">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="c5f13-317">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="c5f13-318">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-318">www.contoso.com/a</span></span>
  - <span data-ttu-id="c5f13-319">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="c5f13-319">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="c5f13-320">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="c5f13-320">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="c5f13-321">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c5f13-321">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="c5f13-322">Cenário: til esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="c5f13-322">Scenario: Left and right tilde</span></span>

<span data-ttu-id="c5f13-323">**Entrada**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="c5f13-323">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="c5f13-324">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-324">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c5f13-325">contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-325">contoso.com</span></span>
  - <span data-ttu-id="c5f13-326">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-326">contoso.com/a</span></span>
  - <span data-ttu-id="c5f13-327">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-327">www.contoso.com</span></span>
  - <span data-ttu-id="c5f13-328">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="c5f13-328">www.contoso.com/b</span></span>
  - <span data-ttu-id="c5f13-329">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-329">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="c5f13-330">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-330">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c5f13-331">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-331">123contoso.com</span></span>
  - <span data-ttu-id="c5f13-332">contoso.org</span><span class="sxs-lookup"><span data-stu-id="c5f13-332">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="c5f13-333">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="c5f13-333">Scenario: IP address</span></span>

<span data-ttu-id="c5f13-334">**Entrada**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="c5f13-334">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="c5f13-335">**Permitir** correspondência de correspondência e **bloqueio**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c5f13-335">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="c5f13-336">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-336">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="c5f13-337">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-337">1.2.3.4/a</span></span>
  - <span data-ttu-id="c5f13-338">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="c5f13-338">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="c5f13-339">Endereço IP com caractere curinga direito</span><span class="sxs-lookup"><span data-stu-id="c5f13-339">IP address with right wildcard</span></span>

<span data-ttu-id="c5f13-340">**Entrada**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="c5f13-340">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="c5f13-341">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-341">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="c5f13-342">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="c5f13-342">1.2.3.4/b</span></span>
  - <span data-ttu-id="c5f13-343">1.2.3.4/Baaaa</span><span class="sxs-lookup"><span data-stu-id="c5f13-343">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="c5f13-344">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="c5f13-344">Examples of invalid entries</span></span>

<span data-ttu-id="c5f13-345">As entradas a seguir são inválidas:</span><span class="sxs-lookup"><span data-stu-id="c5f13-345">The following entries are invalid:</span></span>

- <span data-ttu-id="c5f13-346">**Valores de domínio ausentes ou inválidos**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-346">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="c5f13-347">contoso</span><span class="sxs-lookup"><span data-stu-id="c5f13-347">contoso</span></span>
  - <span data-ttu-id="c5f13-348">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-348">\*.contoso.\*</span></span>
  - <span data-ttu-id="c5f13-349">\*. com</span><span class="sxs-lookup"><span data-stu-id="c5f13-349">\*.com</span></span>
  - <span data-ttu-id="c5f13-350">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="c5f13-350">\*.pdf</span></span>

- <span data-ttu-id="c5f13-351">**Curinga no texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-351">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="c5f13-352">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-352">\*contoso.com</span></span>
  - <span data-ttu-id="c5f13-353">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-353">contoso.com\*</span></span>
  - <span data-ttu-id="c5f13-354">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="c5f13-354">\*1.2.3.4</span></span>
  - <span data-ttu-id="c5f13-355">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-355">1.2.3.4\*</span></span>
  - <span data-ttu-id="c5f13-356">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-356">contoso.com/a\*</span></span>
  - <span data-ttu-id="c5f13-357">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-357">contoso.com/ab\*</span></span>

- <span data-ttu-id="c5f13-358">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-358">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="c5f13-359">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="c5f13-359">contoso.com:443</span></span>
  - <span data-ttu-id="c5f13-360">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="c5f13-360">abc.contoso.com:25</span></span>

- <span data-ttu-id="c5f13-361">**Curingas não descritivos**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-361">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="c5f13-362">\*.\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-362">\*.\*</span></span>

- <span data-ttu-id="c5f13-363">**Curingas médios**:</span><span class="sxs-lookup"><span data-stu-id="c5f13-363">**Middle wildcards**:</span></span>

  - <span data-ttu-id="c5f13-364">conta \* so.com</span><span class="sxs-lookup"><span data-stu-id="c5f13-364">conto\*so.com</span></span>
  - <span data-ttu-id="c5f13-365">cont ~ so. com</span><span class="sxs-lookup"><span data-stu-id="c5f13-365">conto~so.com</span></span>

- <span data-ttu-id="c5f13-366">**Curingas duplos**</span><span class="sxs-lookup"><span data-stu-id="c5f13-366">**Double wildcards**</span></span>

  - <span data-ttu-id="c5f13-367">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-367">contoso.com/\*\*</span></span>
  - <span data-ttu-id="c5f13-368">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="c5f13-368">contoso.com/\*/\*</span></span>
