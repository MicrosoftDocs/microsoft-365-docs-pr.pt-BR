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
ms.openlocfilehash: 742a44c7ed63c8a3037e2ada295c94f89afa9c93
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726819"
---
# <a name="manage-urls-and-files-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-103">Gerenciar URLs e arquivos na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-103">Manage URLs and files in the Tenant Allow/Block List</span></span>

> [!NOTE]
> <span data-ttu-id="37a00-104">Os recursos descritos neste tópico estão em visualização, estão sujeitos a alterações e não estão disponíveis em todas as organizações.</span><span class="sxs-lookup"><span data-stu-id="37a00-104">The features described in this topic are in Preview, are subject to change, and are not available in all organizations.</span></span>

<span data-ttu-id="37a00-105">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode discordar do veredicto de filtragem EOP.</span><span class="sxs-lookup"><span data-stu-id="37a00-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you might disagree with the EOP filtering verdict.</span></span> <span data-ttu-id="37a00-106">Por exemplo, uma boa mensagem pode ser marcada como ruim (falso positivo) ou uma mensagem inválida pode ser permitida por meio de (falso negativo).</span><span class="sxs-lookup"><span data-stu-id="37a00-106">For example, a good message might be marked as bad (a false positive), or a bad message might be allowed through (a false negative).</span></span>

<span data-ttu-id="37a00-107">A lista de permissões/bloqueios de locatários no centro de conformidade do & de segurança oferece uma maneira de substituir manualmente o Microsoft 365 Filtering verdicts.</span><span class="sxs-lookup"><span data-stu-id="37a00-107">The Tenant Allow/Block List in the Security & Compliance Center gives you a way to manually override the Microsoft 365 filtering verdicts.</span></span> <span data-ttu-id="37a00-108">A lista de permissões/bloqueios de locatários é usada durante o fluxo de emails e no momento em que o usuário clica.</span><span class="sxs-lookup"><span data-stu-id="37a00-108">The Tenant Allow/Block List is used during mail flow and at the time of user clicks.</span></span> <span data-ttu-id="37a00-109">Você pode especificar URLs e arquivos para permitir ou bloquear na lista de permissões/bloqueios de locatários.</span><span class="sxs-lookup"><span data-stu-id="37a00-109">You can specify URLs and files to allow or block in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="37a00-110">Este tópico descreve como configurar entradas na lista de permissões/bloqueios de locatário no centro de conformidade & segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; autônomo do EOP PowerShell para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="37a00-110">This topic describes how to configure entries in the Tenant Allow/Block List in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="37a00-111">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="37a00-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="37a00-112">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="37a00-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="37a00-113">Para ir diretamente para a página **lista de permissões/bloqueios de locatários** , use <https://protection.office.com/tenantAllowBlockList> .</span><span class="sxs-lookup"><span data-stu-id="37a00-113">To go directly to the **Tenant Allow/Block List** page, use <https://protection.office.com/tenantAllowBlockList>.</span></span>

- <span data-ttu-id="37a00-114">Você especifica arquivos usando o valor de hash SHA256 do arquivo.</span><span class="sxs-lookup"><span data-stu-id="37a00-114">You specify files by using the SHA256 hash value of the file.</span></span> <span data-ttu-id="37a00-115">Para localizar o valor de hash SHA256 de um arquivo no Windows, execute o seguinte comando em um prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="37a00-115">To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt:</span></span>

  ```dos
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  <span data-ttu-id="37a00-116">Um valor de exemplo é `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` .</span><span class="sxs-lookup"><span data-stu-id="37a00-116">An example value is `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`.</span></span> <span data-ttu-id="37a00-117">Os valores de hash perceptual (pHash) não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="37a00-117">Perceptual hash (pHash) values are not allowed.</span></span>

- <span data-ttu-id="37a00-118">Os valores de URL disponíveis são descritos na [sintaxe da URL para a seção lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="37a00-118">The available URL values are described in the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

- <span data-ttu-id="37a00-119">A lista de permissões/bloqueios de locatários permite um máximo de 500 entradas para URLs e 500 entradas para hashes de arquivo.</span><span class="sxs-lookup"><span data-stu-id="37a00-119">The Tenant Allow/Block List allows a maximum of 500 entries for URLs, and 500 entries for file hashes.</span></span>

- <span data-ttu-id="37a00-120">Uma entrada deve estar ativa em 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="37a00-120">An entry should be active within 15 minutes.</span></span>

- <span data-ttu-id="37a00-121">As entradas de bloco têm precedência sobre as entradas de permissão.</span><span class="sxs-lookup"><span data-stu-id="37a00-121">Block entries take precedence over allow entries.</span></span>

- <span data-ttu-id="37a00-122">Por padrão, as entradas na lista de permissões/bloqueios de locatários expirarão após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="37a00-122">By default, entries in the Tenant Allow/Block List will expire after 30 days.</span></span> <span data-ttu-id="37a00-123">Você pode especificar uma data ou defini-las para nunca expirar.</span><span class="sxs-lookup"><span data-stu-id="37a00-123">You can specify a date or set them to never expire.</span></span>

- <span data-ttu-id="37a00-124">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="37a00-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="37a00-125">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="37a00-125">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="37a00-126">Você precisa receber permissões antes de executar os procedimentos deste tópico:</span><span class="sxs-lookup"><span data-stu-id="37a00-126">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="37a00-127">Para adicionar e remover valores da lista de permissões/bloqueios de locatário, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="37a00-127">To add and remove values from the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="37a00-128">**Gerenciamento da organização** ou **administrador de segurança** no centro de conformidade de & de [segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="37a00-128">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="37a00-129">Gerenciamento da **organização** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="37a00-129">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="37a00-130">Para acesso somente leitura à lista de permissões/bloqueios de locatário, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="37a00-130">For read-only access to the Tenant Allow/Block List, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="37a00-131">**Leitor de segurança** no [centro de conformidade & segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="37a00-131">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="37a00-132">**Gerenciamento de organização somente para exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="37a00-132">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-133">Usar o centro de conformidade de & de segurança para criar entradas de URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-133">Use the Security & Compliance Center to create URL entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37a00-134">Para obter detalhes sobre a sintaxe das entradas de URL, consulte a sintaxe da URL da seção [lista de permissões/bloqueios de locatário](#url-syntax-for-the-tenant-allowblock-list) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="37a00-134">For details about the syntax for URL entries, see the [URL syntax for the Tenant Allow/Block List](#url-syntax-for-the-tenant-allowblock-list) section later in this topic.</span></span>

1. <span data-ttu-id="37a00-135">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="37a00-135">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37a00-136">Na página **lista de permissões/bloqueios de locatários** , verifique se a guia **URLs** está selecionada e clique em **Adicionar**</span><span class="sxs-lookup"><span data-stu-id="37a00-136">On the **Tenant Allow/Block List** page, verify that the **URLs** tab is selected, and then click **Add**</span></span>

3. <span data-ttu-id="37a00-137">No submenu **adicionar novas URLs** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="37a00-137">In the **Add new URLs** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="37a00-138">**Adicionar URLs com curingas**: Insira uma URL por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="37a00-138">**Add URLs with wildcards**: Enter one URL per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="37a00-139">**Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** as URLs especificadas.</span><span class="sxs-lookup"><span data-stu-id="37a00-139">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified URLs.</span></span>

   - <span data-ttu-id="37a00-140">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="37a00-140">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="37a00-141">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.</span><span class="sxs-lookup"><span data-stu-id="37a00-141">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="37a00-142">ou</span><span class="sxs-lookup"><span data-stu-id="37a00-142">or</span></span>

     - <span data-ttu-id="37a00-143">Mova a opção para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="37a00-143">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="37a00-145">.</span><span class="sxs-lookup"><span data-stu-id="37a00-145">.</span></span>

   - <span data-ttu-id="37a00-146">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="37a00-146">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="37a00-147">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="37a00-147">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-create-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-148">Usar o centro de conformidade de & de segurança para criar entradas de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-148">Use the Security & Compliance Center to create file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37a00-149">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="37a00-149">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37a00-150">Na página **lista de permissões/bloqueios de locatários** , selecione **arquivos** e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="37a00-150">On the **Tenant Allow/Block List** page, select **Files** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="37a00-151">No submenu **Adicionar novos arquivos** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="37a00-151">In the **Add new files** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="37a00-152">**Adicionar hashes de arquivo**: Insira um valor de hash SHA256 por linha, até um máximo de 20.</span><span class="sxs-lookup"><span data-stu-id="37a00-152">**Add file hashes**: Enter one SHA256 hash value per line, up to a maximum of 20.</span></span>

   - <span data-ttu-id="37a00-153">**Bloquear/permitir**: selecione se você deseja **permitir** ou **Bloquear** os arquivos especificados.</span><span class="sxs-lookup"><span data-stu-id="37a00-153">**Block/Allow**: Select whether you want to **Allow** or **Block** the specified files.</span></span>

   - <span data-ttu-id="37a00-154">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="37a00-154">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="37a00-155">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento das entradas.</span><span class="sxs-lookup"><span data-stu-id="37a00-155">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entries.</span></span>

     <span data-ttu-id="37a00-156">ou</span><span class="sxs-lookup"><span data-stu-id="37a00-156">or</span></span>

     - <span data-ttu-id="37a00-157">Mova a opção para a direita para configurar as entradas para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="37a00-157">Move the toggle to the right to configure the entries to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="37a00-159">.</span><span class="sxs-lookup"><span data-stu-id="37a00-159">.</span></span>

   - <span data-ttu-id="37a00-160">**Observação opcional**: insira texto descritivo para as entradas.</span><span class="sxs-lookup"><span data-stu-id="37a00-160">**Optional note**: Enter descriptive text for the entries.</span></span>

4. <span data-ttu-id="37a00-161">Quando tiver concluído, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="37a00-161">When you're finished, click **Add**.</span></span>

## <a name="use-the-security--compliance-center-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-162">Use o centro de conformidade de & de segurança para exibir entradas de URL e de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-162">Use the Security & Compliance Center to view URL and file entries in the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37a00-163">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="37a00-163">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37a00-164">Selecione a guia **URLs** ou a guia **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="37a00-164">Select the **URLs** tab or the **Files** tab.</span></span>

<span data-ttu-id="37a00-165">Clique nos seguintes títulos de coluna para classificar em ordem crescente ou decrescente:</span><span class="sxs-lookup"><span data-stu-id="37a00-165">Click on the following column headings to sort in ascending or descending order:</span></span>

- <span data-ttu-id="37a00-166">**Valor**: a URL ou o hash do arquivo.</span><span class="sxs-lookup"><span data-stu-id="37a00-166">**Value**: The URL or the file hash.</span></span>
- <span data-ttu-id="37a00-167">**Ação**: **Bloquear** ou **permitir**.</span><span class="sxs-lookup"><span data-stu-id="37a00-167">**Action**: **Block** or **Allow**.</span></span>
- <span data-ttu-id="37a00-168">**Data da última atualização**</span><span class="sxs-lookup"><span data-stu-id="37a00-168">**Last updated date**</span></span>
- <span data-ttu-id="37a00-169">**Data de vencimento**</span><span class="sxs-lookup"><span data-stu-id="37a00-169">**Expiration date**</span></span>
- <span data-ttu-id="37a00-170">**Observação**</span><span class="sxs-lookup"><span data-stu-id="37a00-170">**Note**</span></span>

<span data-ttu-id="37a00-171">Clique em **Agrupar** para agrupar as entradas **por ação** (**Bloquear** ou **permitir**) ou **nenhum**.</span><span class="sxs-lookup"><span data-stu-id="37a00-171">Click **Group** to group the entries by **Action** (**Block** or **Allow**) or **None**.</span></span>

<span data-ttu-id="37a00-172">Clique em **Pesquisar**, digite todo ou parte de um valor de URL ou de arquivo e pressione ENTER para localizar um valor específico.</span><span class="sxs-lookup"><span data-stu-id="37a00-172">Click **Search**, enter all or part of a URL or file value, and then press ENTER to find a specific value.</span></span> <span data-ttu-id="37a00-173">Quando tiver terminado, clique em **limpar** o ![ ícone pesquisa limpar pesquisa ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .</span><span class="sxs-lookup"><span data-stu-id="37a00-173">When you're finished, click **Clear search** ![Clear search icon](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif).</span></span>

<span data-ttu-id="37a00-174">Clique em **filtro**.</span><span class="sxs-lookup"><span data-stu-id="37a00-174">Click **Filter**.</span></span> <span data-ttu-id="37a00-175">No submenu de **filtro** que aparece, configure qualquer uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="37a00-175">In the **Filter** flyout that appears, configure any of the following settings:</span></span>

- <span data-ttu-id="37a00-176">**Ação**: selecione **permitir**, **Bloquear** ou ambos.</span><span class="sxs-lookup"><span data-stu-id="37a00-176">**Action**: Select **Allow**, **Block** or both.</span></span>

- <span data-ttu-id="37a00-177">**Nunca expirar**: selecione Desativado (desativar ![ ](../../media/scc-toggle-off.png) ) ou ativado ( ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) ).</span><span class="sxs-lookup"><span data-stu-id="37a00-177">**Never expire**: Select off (![Toggle off](../../media/scc-toggle-off.png)) or on (![Toggle on](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)).</span></span>

- <span data-ttu-id="37a00-178">**Última atualização**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="37a00-178">**Last updated**: Select a start date (**From**), an end date (**To**) or both.</span></span>

- <span data-ttu-id="37a00-179">**Data de validade**: selecione uma data de início (**de**), uma data de término (**para**) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="37a00-179">**Expiration date**: Select a start date (**From**), an end date (**To**) or both.</span></span>

<span data-ttu-id="37a00-180">Quando tiver concluído, clique em **aplicar**.</span><span class="sxs-lookup"><span data-stu-id="37a00-180">When you're finished, click **Apply**.</span></span>

<span data-ttu-id="37a00-181">Para limpar filtros existentes, clique em **Filtrar**e, no submenu de **filtro** que aparece, clique em **limpar filtros**.</span><span class="sxs-lookup"><span data-stu-id="37a00-181">To clear existing filters, click **Filter**, and in the **Filter** flyout that appears, click **Clear filters**.</span></span>

## <a name="use-the-security--compliance-center-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-182">Use o centro de conformidade de & de segurança para modificar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-182">Use the Security & Compliance Center to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37a00-183">Você não pode modificar a URL ou o valor do arquivo propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="37a00-183">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="37a00-184">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="37a00-184">Instead, you need to delete the entry and recreate it.</span></span>

1. <span data-ttu-id="37a00-185">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="37a00-185">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37a00-186">Selecione a guia **URLs** ou a guia **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="37a00-186">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="37a00-187">Selecione a entrada que você deseja modificar e clique em **Editar** ![ ícone de edição ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .</span><span class="sxs-lookup"><span data-stu-id="37a00-187">Select the entry that you want to modify, and then click **Edit** ![Edit icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png).</span></span>

4. <span data-ttu-id="37a00-188">No submenu exibido, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="37a00-188">In the flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="37a00-189">**Bloquear/permitir**: selecione **permitir** ou **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="37a00-189">**Block/Allow**: Select **Allow** or **Block**.</span></span>

   - <span data-ttu-id="37a00-190">**Nunca expira**: execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="37a00-190">**Never expire**: Do one of the following steps:</span></span>

     - <span data-ttu-id="37a00-191">Verifique se a configuração está desativada (desative ![ ](../../media/scc-toggle-off.png) ) e use a caixa **expira em** para especificar a data de vencimento da entrada.</span><span class="sxs-lookup"><span data-stu-id="37a00-191">Verify the setting is turned off (![Toggle off](../../media/scc-toggle-off.png)) and use the **Expires on** box to specify the expiration date for the entry.</span></span>

     <span data-ttu-id="37a00-192">ou</span><span class="sxs-lookup"><span data-stu-id="37a00-192">or</span></span>

     - <span data-ttu-id="37a00-193">Mova a opção para a direita para configurar a entrada para nunca expirar:</span><span class="sxs-lookup"><span data-stu-id="37a00-193">Move the toggle to the right to configure the entry to never expire:</span></span> ![Ativar](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)<span data-ttu-id="37a00-195">.</span><span class="sxs-lookup"><span data-stu-id="37a00-195">.</span></span>

   - <span data-ttu-id="37a00-196">**Observação opcional**: insira texto descritivo para a entrada.</span><span class="sxs-lookup"><span data-stu-id="37a00-196">**Optional note**: Enter descriptive text for the entry.</span></span>

5. <span data-ttu-id="37a00-197">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="37a00-197">When you're finished, click **Save**.</span></span>

## <a name="use-the-security--compliance-center-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-198">Use o centro de conformidade de & de segurança para remover entradas de URL e arquivos da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-198">Use the Security & Compliance Center to remove URL and file entries from the Tenant Allow/Block List</span></span>

1. <span data-ttu-id="37a00-199">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **listas de permissões/bloqueios de locatários**de política de gerenciamento de ameaça.</span><span class="sxs-lookup"><span data-stu-id="37a00-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Tenant Allow/Block Lists**.</span></span>

2. <span data-ttu-id="37a00-200">Selecione a guia **URLs** ou a guia **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="37a00-200">Select the **URLs** tab or the **Files** tab.</span></span>

3. <span data-ttu-id="37a00-201">Selecione a entrada que você deseja remover e clique em **excluir** ![ excluir ícone ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .</span><span class="sxs-lookup"><span data-stu-id="37a00-201">Select the entry that you want to remove, and then click **Delete** ![Delete icon](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).</span></span>

4. <span data-ttu-id="37a00-202">Na caixa de diálogo de aviso que aparece, clique em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="37a00-202">In the warning dialog that appears, click **Delete**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-203">Usar o PowerShell do Exchange Online ou o PowerShell do EOP para configurar a lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-203">Use Exchange Online PowerShell or standalone EOP PowerShell to configure the Tenant Allow/Block List</span></span>

### <a name="use-powershell-to-add-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-204">Usar o PowerShell para adicionar entradas de URL e de arquivo na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-204">Use PowerShell to add URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37a00-205">Para adicionar entradas de URL e de arquivo na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="37a00-205">To add URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
New-TenantAllowBlockListItems -ListType <Url | FileHash> -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="37a00-206">Este exemplo adiciona uma entrada de bloco de URL para contoso.com e todos os subdomínios (por exemplo, contoso.com, www.contoso.com e xyz.abc.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="37a00-206">This example adds a URL block entry for contoso.com and all subdomains (for example, contoso.com, www.contoso.com, and xyz.abc.contoso.com).</span></span> <span data-ttu-id="37a00-207">Como não usamos os parâmetros ExpirationDate ou noexpiration, a entrada expira após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="37a00-207">Because we didn't use the ExpirationDate or NoExpiration parameters, the entry expires after 30 days.</span></span>

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Action Allow -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

<span data-ttu-id="37a00-208">Este exemplo adiciona uma entrada de permissão de arquivo para os arquivos especificados que nunca expiram.</span><span class="sxs-lookup"><span data-stu-id="37a00-208">This example adds a file allow entry for the specified files that never expires.</span></span>

<span data-ttu-id="37a00-209">Para informações detalhadas de sintaxes e de parâmetros, consulte [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="37a00-209">For detailed syntax and parameter information, see [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-view-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-210">Use o PowerShell para exibir as entradas de arquivo e URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-210">Use PowerShell to view URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37a00-211">Para exibir as entradas de arquivo e URL na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="37a00-211">To view URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType <Url | FileHash> [-Entry <URLValue | FileHashValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

<span data-ttu-id="37a00-212">Este exemplo retorna todas as URLs bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="37a00-212">This example returns all blocked URLs.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

<span data-ttu-id="37a00-213">Este exemplo retorna informações para o valor de hash do arquivo especificado.</span><span class="sxs-lookup"><span data-stu-id="37a00-213">This example returns information for the specified file hash value.</span></span>

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

<span data-ttu-id="37a00-214">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="37a00-214">For detailed syntax and parameter information, see [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-modify-url-and-file-entries-in-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-215">Usar o PowerShell para modificar as entradas de arquivo e URL na lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-215">Use PowerShell to modify URL and file entries in the Tenant Allow/Block List</span></span>

<span data-ttu-id="37a00-216">Você não pode modificar a URL ou o valor do arquivo propriamente dito.</span><span class="sxs-lookup"><span data-stu-id="37a00-216">You can't modify the URL or file value itself.</span></span> <span data-ttu-id="37a00-217">Em vez disso, você precisa excluir a entrada e recriá-la.</span><span class="sxs-lookup"><span data-stu-id="37a00-217">Instead, you need to delete the entry and recreate it.</span></span>

<span data-ttu-id="37a00-218">Para modificar as entradas de URL e de arquivo na lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="37a00-218">To modify URL and file entries in the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

<span data-ttu-id="37a00-219">Este exemplo altera a data de vencimento da entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="37a00-219">This example changes the expiration date of the specified entry.</span></span>

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

<span data-ttu-id="37a00-220">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="37a00-220">For detailed syntax and parameter information, see [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).</span></span>

### <a name="use-powershell-to-remove-url-and-file-entries-from-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-221">Use o PowerShell para remover as entradas de arquivo e URL da lista de permissões/bloqueios de locatários</span><span class="sxs-lookup"><span data-stu-id="37a00-221">Use PowerShell to remove URL and file entries from the Tenant Allow/Block List</span></span>

<span data-ttu-id="37a00-222">Para remover as entradas de arquivo e URL da lista de permissões/bloqueios de locatários, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="37a00-222">To remove URL and file entries from the Tenant Allow/Block List, use the following syntax:</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType <Url | FileHash> -Ids <"Id1","Id2",..."IdN">
```

<span data-ttu-id="37a00-223">Este exemplo remove a entrada de URL especificada da lista de permissões/bloqueios de locatário.</span><span class="sxs-lookup"><span data-stu-id="37a00-223">This example removes the specified URL entry from the Tenant Allow/Block List.</span></span>

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

<span data-ttu-id="37a00-224">Para informações detalhadas de sintaxes e de parâmetros, consulte [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span><span class="sxs-lookup"><span data-stu-id="37a00-224">For detailed syntax and parameter information, see [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).</span></span>

## <a name="url-syntax-for-the-tenant-allowblock-list"></a><span data-ttu-id="37a00-225">Sintaxe da URL para a lista de permissões/bloqueios de locatário</span><span class="sxs-lookup"><span data-stu-id="37a00-225">URL syntax for the Tenant Allow/Block List</span></span>

- <span data-ttu-id="37a00-226">Os endereços IPv6 e IP4v são permitidos, mas as portas TCP/UDP não são.</span><span class="sxs-lookup"><span data-stu-id="37a00-226">IP4v and IPv6 addresses are allowed, but TCP/UDP ports are not.</span></span>

- <span data-ttu-id="37a00-227">Extensões de nome de arquivo não são permitidas (por exemplo, test.pdf).</span><span class="sxs-lookup"><span data-stu-id="37a00-227">Filename extensions are not allowed (for example, test.pdf).</span></span>

- <span data-ttu-id="37a00-228">Unicode não é suportado, mas Punycode é.</span><span class="sxs-lookup"><span data-stu-id="37a00-228">Unicode is not supported, but Punycode is.</span></span>

- <span data-ttu-id="37a00-229">Os nomes de host são permitidos se todas as instruções a seguir forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="37a00-229">Hostnames are allowed if all of the following statements are true:</span></span>

  - <span data-ttu-id="37a00-230">O nome do host contém um ponto.</span><span class="sxs-lookup"><span data-stu-id="37a00-230">The hostname contains a period.</span></span>
  - <span data-ttu-id="37a00-231">Há pelo menos um caractere à esquerda do ponto.</span><span class="sxs-lookup"><span data-stu-id="37a00-231">There is at least one character to the left of the period.</span></span>
  - <span data-ttu-id="37a00-232">Há pelo menos dois caracteres à direita do ponto.</span><span class="sxs-lookup"><span data-stu-id="37a00-232">There are at least two characters to the right of the period.</span></span>

  <span data-ttu-id="37a00-233">Por exemplo, `t.co` é permitido; `.com` ou `contoso.` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="37a00-233">For example, `t.co` is allowed; `.com` or `contoso.` are not allowed.</span></span>

- <span data-ttu-id="37a00-234">Os subcaminhos não são inferidos.</span><span class="sxs-lookup"><span data-stu-id="37a00-234">Subpaths are not implied.</span></span>

  <span data-ttu-id="37a00-235">Por exemplo, não `contoso.com` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="37a00-235">For example, `contoso.com` does not include `contoso.com/a`.</span></span>

- <span data-ttu-id="37a00-236">Caracteres curinga (\*) são permitidos nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="37a00-236">Wildcards (\*) are allowed in the following scenarios:</span></span>

  - <span data-ttu-id="37a00-237">Um caractere curinga à esquerda deve ser seguido por um ponto para especificar um subdomínio.</span><span class="sxs-lookup"><span data-stu-id="37a00-237">A left wildcard must be followed by a period to specify a subdomain.</span></span>

    <span data-ttu-id="37a00-238">Por exemplo, `*.contoso.com` é permitido; `*contoso.com` não é permitido.</span><span class="sxs-lookup"><span data-stu-id="37a00-238">For example, `*.contoso.com` is allowed; `*contoso.com` is not allowed.</span></span>

  - <span data-ttu-id="37a00-239">Um caractere curinga à direita deve seguir uma barra (/) para especificar um caminho.</span><span class="sxs-lookup"><span data-stu-id="37a00-239">A right wildcard must follow a forward slash (/) to specify a path.</span></span>

    <span data-ttu-id="37a00-240">Por exemplo, `contoso.com/*` é permitido; `contoso.com*` ou `contoso.com/ab*` não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="37a00-240">For example, `contoso.com/*` is allowed; `contoso.com*` or `contoso.com/ab*` are not allowed.</span></span>

  - <span data-ttu-id="37a00-241">Todos os subcaminhos não são inferidos por um caractere curinga correto.</span><span class="sxs-lookup"><span data-stu-id="37a00-241">All subpaths are not implied by a right wildcard.</span></span>

    <span data-ttu-id="37a00-242">Por exemplo, não `contoso.com/*` inclui `contoso.com/a` .</span><span class="sxs-lookup"><span data-stu-id="37a00-242">For example, `contoso.com/*` does not include `contoso.com/a`.</span></span>

  - <span data-ttu-id="37a00-243">`*.com*`é inválido (não é um domínio resolvível e o caractere curinga correto não segue uma barra).</span><span class="sxs-lookup"><span data-stu-id="37a00-243">`*.com*` is invalid (not a resolvable domain and the right wildcard does not follow a forward slash).</span></span>

  - <span data-ttu-id="37a00-244">Curingas não são permitidos em endereços IP.</span><span class="sxs-lookup"><span data-stu-id="37a00-244">Wildcards are not allowed in IP addresses.</span></span>

- <span data-ttu-id="37a00-245">O caractere til (~) está disponível nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="37a00-245">The tilde (~) character is available in the following scenarios:</span></span>

  - <span data-ttu-id="37a00-246">Um til esquerdo implica um domínio e todos os subdomínios.</span><span class="sxs-lookup"><span data-stu-id="37a00-246">A left tilde implies a domain and all subdomains.</span></span>

    <span data-ttu-id="37a00-247">Por exemplo `~contoso.com` inclui `contoso.com` e `*.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="37a00-247">For example `~contoso.com` includes `contoso.com` and `*.contoso.com`.</span></span>

- <span data-ttu-id="37a00-248">As entradas de URL que contêm protocolos (por exemplo,, `http://` `https://` ou `ftp://` ) falharão, porque as entradas de URL se aplicam a todos os protocolos.</span><span class="sxs-lookup"><span data-stu-id="37a00-248">URL entries that contain protocols (for example, `http://`, `https://`, or `ftp://`) will fail, because URL entries apply to all protocols.</span></span>

- <span data-ttu-id="37a00-249">Um nome de usuário ou senha não são suportados ou necessários.</span><span class="sxs-lookup"><span data-stu-id="37a00-249">A username or password aren't supported or required.</span></span>

- <span data-ttu-id="37a00-250">Aspas ("ou") são caracteres inválidos.</span><span class="sxs-lookup"><span data-stu-id="37a00-250">Quotes (' or ") are invalid characters.</span></span>

- <span data-ttu-id="37a00-251">Uma URL deve incluir todos os redirecionamentos onde for possível.</span><span class="sxs-lookup"><span data-stu-id="37a00-251">A URL should include all redirects where possible.</span></span>

### <a name="url-entry-scenarios"></a><span data-ttu-id="37a00-252">Cenários de entrada de URL</span><span class="sxs-lookup"><span data-stu-id="37a00-252">URL entry scenarios</span></span>

<span data-ttu-id="37a00-253">Entradas de URL válidas e seus resultados são descritos nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="37a00-253">Valid URL entries and their results are described in the following sections.</span></span>

#### <a name="scenario-no-wildcards"></a><span data-ttu-id="37a00-254">Cenário: sem curingas</span><span class="sxs-lookup"><span data-stu-id="37a00-254">Scenario: No wildcards</span></span>

<span data-ttu-id="37a00-255">**Entrada**:`contoso.com`</span><span class="sxs-lookup"><span data-stu-id="37a00-255">**Entry**: `contoso.com`</span></span>

- <span data-ttu-id="37a00-256">**Permitir correspondência**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-256">**Allow match**: contoso.com</span></span>

- <span data-ttu-id="37a00-257">**Permitir não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="37a00-257">**Allow not matched**:</span></span>

  - <span data-ttu-id="37a00-258">abc-contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-258">abc-contoso.com</span></span>
  - <span data-ttu-id="37a00-259">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37a00-259">contoso.com/a</span></span>
  - <span data-ttu-id="37a00-260">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-260">payroll.contoso.com</span></span>
  - <span data-ttu-id="37a00-261">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-261">test.com/contoso.com</span></span>
  - <span data-ttu-id="37a00-262">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-262">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="37a00-263">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-263">www.contoso.com</span></span>
  - <span data-ttu-id="37a00-264">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="37a00-264">www.contoso.com/q=a@contoso.com</span></span>
  
- <span data-ttu-id="37a00-265">**Correspondência de bloco**:</span><span class="sxs-lookup"><span data-stu-id="37a00-265">**Block match**:</span></span>

  - <span data-ttu-id="37a00-266">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-266">contoso.com</span></span>
  - <span data-ttu-id="37a00-267">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37a00-267">contoso.com/a</span></span>
  - <span data-ttu-id="37a00-268">payroll.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-268">payroll.contoso.com</span></span>
  - <span data-ttu-id="37a00-269">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-269">test.com/contoso.com</span></span>
  - <span data-ttu-id="37a00-270">test.com/q=contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-270">test.com/q=contoso.com</span></span>
  - <span data-ttu-id="37a00-271">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-271">www.contoso.com</span></span>
  - <span data-ttu-id="37a00-272">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="37a00-272">www.contoso.com/q=a@contoso.com</span></span>

- <span data-ttu-id="37a00-273">**Bloquear não correspondente**: ABC-contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-273">**Block not matched**: abc-contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain"></a><span data-ttu-id="37a00-274">Cenário: curinga esquerdo (subdomínio)</span><span class="sxs-lookup"><span data-stu-id="37a00-274">Scenario: Left wildcard (subdomain)</span></span>

<span data-ttu-id="37a00-275">**Entrada**:`*.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="37a00-275">**Entry**: `*.contoso.com`</span></span>

- <span data-ttu-id="37a00-276">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="37a00-276">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37a00-277">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-277">www.contoso.com</span></span>
  - <span data-ttu-id="37a00-278">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-278">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="37a00-279">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="37a00-279">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37a00-280">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-280">123contoso.com</span></span>
  - <span data-ttu-id="37a00-281">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-281">contoso.com</span></span>
  - <span data-ttu-id="37a00-282">test.com/contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-282">test.com/contoso.com</span></span>
  - <span data-ttu-id="37a00-283">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="37a00-283">www.contoso.com/abc</span></span>
  
#### <a name="scenario-right-wildcard-at-top-of-path"></a><span data-ttu-id="37a00-284">Cenário: caractere curinga à direita na parte superior do caminho</span><span class="sxs-lookup"><span data-stu-id="37a00-284">Scenario: Right wildcard at top of path</span></span>

<span data-ttu-id="37a00-285">**Entrada**:`contoso.com/a/*`</span><span class="sxs-lookup"><span data-stu-id="37a00-285">**Entry**: `contoso.com/a/*`</span></span>

- <span data-ttu-id="37a00-286">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="37a00-286">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37a00-287">contoso.com/a/b</span><span class="sxs-lookup"><span data-stu-id="37a00-287">contoso.com/a/b</span></span>
  - <span data-ttu-id="37a00-288">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="37a00-288">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="37a00-289">contoso. com/a/? q = joe@t. com</span><span class="sxs-lookup"><span data-stu-id="37a00-289">contoso.com/a/?q=joe@t.com</span></span>

- <span data-ttu-id="37a00-290">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="37a00-290">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37a00-291">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-291">contoso.com</span></span>
  - <span data-ttu-id="37a00-292">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37a00-292">contoso.com/a</span></span>
  - <span data-ttu-id="37a00-293">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-293">www.contoso.com</span></span>
  - <span data-ttu-id="37a00-294">www. contoso. com/q = a@contoso. com</span><span class="sxs-lookup"><span data-stu-id="37a00-294">www.contoso.com/q=a@contoso.com</span></span>
  
#### <a name="scenario-left-tilde"></a><span data-ttu-id="37a00-295">Cenário: til esquerdo</span><span class="sxs-lookup"><span data-stu-id="37a00-295">Scenario: Left tilde</span></span>

<span data-ttu-id="37a00-296">**Entrada**:`~contoso.com`</span><span class="sxs-lookup"><span data-stu-id="37a00-296">**Entry**: `~contoso.com`</span></span>

- <span data-ttu-id="37a00-297">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="37a00-297">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37a00-298">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-298">contoso.com</span></span>
  - <span data-ttu-id="37a00-299">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-299">www.contoso.com</span></span>
  - <span data-ttu-id="37a00-300">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-300">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="37a00-301">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="37a00-301">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37a00-302">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-302">123contoso.com</span></span>
  - <span data-ttu-id="37a00-303">contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="37a00-303">contoso.com/abc</span></span>
  - <span data-ttu-id="37a00-304">www.contoso.com/abc</span><span class="sxs-lookup"><span data-stu-id="37a00-304">www.contoso.com/abc</span></span>

#### <a name="scenario-right-wildcard-suffix"></a><span data-ttu-id="37a00-305">Cenário: sufixo curinga à direita</span><span class="sxs-lookup"><span data-stu-id="37a00-305">Scenario: Right wildcard suffix</span></span>

<span data-ttu-id="37a00-306">**Entrada**:`contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="37a00-306">**Entry**: `contoso.com/*`</span></span>

- <span data-ttu-id="37a00-307">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="37a00-307">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37a00-308">contoso. com/? q = whatever@fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="37a00-308">contoso.com/?q=whatever@fabrikam.com</span></span>
  - <span data-ttu-id="37a00-309">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37a00-309">contoso.com/a</span></span>
  - <span data-ttu-id="37a00-310">contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="37a00-310">contoso.com/a/b/c</span></span>
  - <span data-ttu-id="37a00-311">contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="37a00-311">contoso.com/ab</span></span>
  - <span data-ttu-id="37a00-312">contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="37a00-312">contoso.com/b</span></span>
  - <span data-ttu-id="37a00-313">contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="37a00-313">contoso.com/b/a/c</span></span>
  - <span data-ttu-id="37a00-314">contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="37a00-314">contoso.com/ba</span></span>

- <span data-ttu-id="37a00-315">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-315">**Allow not matched** and **Block not matched**: contoso.com</span></span>

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a><span data-ttu-id="37a00-316">Cenário: subdomínio curinga esquerdo e sufixo curinga direito</span><span class="sxs-lookup"><span data-stu-id="37a00-316">Scenario: Left wildcard subdomain and right wildcard suffix</span></span>

<span data-ttu-id="37a00-317">**Entrada**:`*.contoso.com/*`</span><span class="sxs-lookup"><span data-stu-id="37a00-317">**Entry**: `*.contoso.com/*`</span></span>

- <span data-ttu-id="37a00-318">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="37a00-318">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37a00-319">abc.contoso.com/ab</span><span class="sxs-lookup"><span data-stu-id="37a00-319">abc.contoso.com/ab</span></span>
  - <span data-ttu-id="37a00-320">abc.xyz.contoso.com/a/b/c</span><span class="sxs-lookup"><span data-stu-id="37a00-320">abc.xyz.contoso.com/a/b/c</span></span>
  - <span data-ttu-id="37a00-321">www.contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37a00-321">www.contoso.com/a</span></span>
  - <span data-ttu-id="37a00-322">www.contoso.com/b/a/c</span><span class="sxs-lookup"><span data-stu-id="37a00-322">www.contoso.com/b/a/c</span></span>
  - <span data-ttu-id="37a00-323">xyz.contoso.com/ba</span><span class="sxs-lookup"><span data-stu-id="37a00-323">xyz.contoso.com/ba</span></span>

- <span data-ttu-id="37a00-324">**Permitir não correspondente** e **Bloquear não correspondente**: contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="37a00-324">**Allow not matched** and **Block not matched**: contoso.com/b</span></span>

#### <a name="scenario-left-and-right-tilde"></a><span data-ttu-id="37a00-325">Cenário: til esquerdo e direito</span><span class="sxs-lookup"><span data-stu-id="37a00-325">Scenario: Left and right tilde</span></span>

<span data-ttu-id="37a00-326">**Entrada**:`~contoso.com~`</span><span class="sxs-lookup"><span data-stu-id="37a00-326">**Entry**: `~contoso.com~`</span></span>

- <span data-ttu-id="37a00-327">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="37a00-327">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37a00-328">contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-328">contoso.com</span></span>
  - <span data-ttu-id="37a00-329">contoso.com/a</span><span class="sxs-lookup"><span data-stu-id="37a00-329">contoso.com/a</span></span>
  - <span data-ttu-id="37a00-330">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-330">www.contoso.com</span></span>
  - <span data-ttu-id="37a00-331">www.contoso.com/b</span><span class="sxs-lookup"><span data-stu-id="37a00-331">www.contoso.com/b</span></span>
  - <span data-ttu-id="37a00-332">xyz.abc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-332">xyz.abc.contoso.com</span></span>

- <span data-ttu-id="37a00-333">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="37a00-333">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37a00-334">123contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-334">123contoso.com</span></span>
  - <span data-ttu-id="37a00-335">contoso.org</span><span class="sxs-lookup"><span data-stu-id="37a00-335">contoso.org</span></span>

#### <a name="scenario-ip-address"></a><span data-ttu-id="37a00-336">Cenário: endereço IP</span><span class="sxs-lookup"><span data-stu-id="37a00-336">Scenario: IP address</span></span>

<span data-ttu-id="37a00-337">**Entrada**:`1.2.3.4`</span><span class="sxs-lookup"><span data-stu-id="37a00-337">**Entry**: `1.2.3.4`</span></span>

- <span data-ttu-id="37a00-338">**Permitir** correspondência de correspondência e **bloqueio**: 1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="37a00-338">**Allow match** and **Block match**: 1.2.3.4</span></span>

- <span data-ttu-id="37a00-339">**Permitir não correspondente** e **Bloquear não correspondente**:</span><span class="sxs-lookup"><span data-stu-id="37a00-339">**Allow not matched** and **Block not matched**:</span></span>

  - <span data-ttu-id="37a00-340">1.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="37a00-340">1.2.3.4/a</span></span>
  - <span data-ttu-id="37a00-341">11.2.3.4/a</span><span class="sxs-lookup"><span data-stu-id="37a00-341">11.2.3.4/a</span></span>

#### <a name="ip-address-with-right-wildcard"></a><span data-ttu-id="37a00-342">Endereço IP com caractere curinga direito</span><span class="sxs-lookup"><span data-stu-id="37a00-342">IP address with right wildcard</span></span>

<span data-ttu-id="37a00-343">**Entrada**:`1.2.3.4/*`</span><span class="sxs-lookup"><span data-stu-id="37a00-343">**Entry**: `1.2.3.4/*`</span></span>

- <span data-ttu-id="37a00-344">**Permitir** correspondência de correspondência e **bloqueio**:</span><span class="sxs-lookup"><span data-stu-id="37a00-344">**Allow match** and **Block match**:</span></span>

  - <span data-ttu-id="37a00-345">1.2.3.4/b</span><span class="sxs-lookup"><span data-stu-id="37a00-345">1.2.3.4/b</span></span>
  - <span data-ttu-id="37a00-346">1.2.3.4/Baaaa</span><span class="sxs-lookup"><span data-stu-id="37a00-346">1.2.3.4/baaaa</span></span>

### <a name="examples-of-invalid-entries"></a><span data-ttu-id="37a00-347">Exemplos de entradas inválidas</span><span class="sxs-lookup"><span data-stu-id="37a00-347">Examples of invalid entries</span></span>

<span data-ttu-id="37a00-348">As entradas a seguir são inválidas:</span><span class="sxs-lookup"><span data-stu-id="37a00-348">The following entries are invalid:</span></span>

- <span data-ttu-id="37a00-349">**Valores de domínio ausentes ou inválidos**:</span><span class="sxs-lookup"><span data-stu-id="37a00-349">**Missing or invalid domain values**:</span></span>

  - <span data-ttu-id="37a00-350">contoso</span><span class="sxs-lookup"><span data-stu-id="37a00-350">contoso</span></span>
  - <span data-ttu-id="37a00-351">\*contoso.\*</span><span class="sxs-lookup"><span data-stu-id="37a00-351">\*.contoso.\*</span></span>
  - <span data-ttu-id="37a00-352">\*. com</span><span class="sxs-lookup"><span data-stu-id="37a00-352">\*.com</span></span>
  - <span data-ttu-id="37a00-353">\*.pdf</span><span class="sxs-lookup"><span data-stu-id="37a00-353">\*.pdf</span></span>

- <span data-ttu-id="37a00-354">**Curinga no texto ou sem caracteres de espaçamento**:</span><span class="sxs-lookup"><span data-stu-id="37a00-354">**Wildcard on text or without spacing characters**:</span></span>

  - <span data-ttu-id="37a00-355">\*contoso.com</span><span class="sxs-lookup"><span data-stu-id="37a00-355">\*contoso.com</span></span>
  - <span data-ttu-id="37a00-356">contoso.com\*</span><span class="sxs-lookup"><span data-stu-id="37a00-356">contoso.com\*</span></span>
  - <span data-ttu-id="37a00-357">\*1.2.3.4</span><span class="sxs-lookup"><span data-stu-id="37a00-357">\*1.2.3.4</span></span>
  - <span data-ttu-id="37a00-358">1.2.3.4\*</span><span class="sxs-lookup"><span data-stu-id="37a00-358">1.2.3.4\*</span></span>
  - <span data-ttu-id="37a00-359">contoso.com/a\*</span><span class="sxs-lookup"><span data-stu-id="37a00-359">contoso.com/a\*</span></span>
  - <span data-ttu-id="37a00-360">contoso.com/ab\*</span><span class="sxs-lookup"><span data-stu-id="37a00-360">contoso.com/ab\*</span></span>

- <span data-ttu-id="37a00-361">**Endereços IP com portas**:</span><span class="sxs-lookup"><span data-stu-id="37a00-361">**IP addresses with ports**:</span></span>

  - <span data-ttu-id="37a00-362">contoso.com:443</span><span class="sxs-lookup"><span data-stu-id="37a00-362">contoso.com:443</span></span>
  - <span data-ttu-id="37a00-363">abc.contoso.com:25</span><span class="sxs-lookup"><span data-stu-id="37a00-363">abc.contoso.com:25</span></span>

- <span data-ttu-id="37a00-364">**Curingas não descritivos**:</span><span class="sxs-lookup"><span data-stu-id="37a00-364">**Non-descriptive wildcards**:</span></span>

  - \*
  - <span data-ttu-id="37a00-365">\*.\*</span><span class="sxs-lookup"><span data-stu-id="37a00-365">\*.\*</span></span>

- <span data-ttu-id="37a00-366">**Curingas médios**:</span><span class="sxs-lookup"><span data-stu-id="37a00-366">**Middle wildcards**:</span></span>

  - <span data-ttu-id="37a00-367">conta \* so.com</span><span class="sxs-lookup"><span data-stu-id="37a00-367">conto\*so.com</span></span>
  - <span data-ttu-id="37a00-368">cont ~ so. com</span><span class="sxs-lookup"><span data-stu-id="37a00-368">conto~so.com</span></span>

- <span data-ttu-id="37a00-369">**Curingas duplos**</span><span class="sxs-lookup"><span data-stu-id="37a00-369">**Double wildcards**</span></span>

  - <span data-ttu-id="37a00-370">contoso.com/\*\*</span><span class="sxs-lookup"><span data-stu-id="37a00-370">contoso.com/\*\*</span></span>
  - <span data-ttu-id="37a00-371">contoso.com/\*/\*</span><span class="sxs-lookup"><span data-stu-id="37a00-371">contoso.com/\*/\*</span></span>
