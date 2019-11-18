---
title: Trabalhar com um parceiro para arquivar dados de terceiros no Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Sua organização pode trabalhar com um parceiro da Microsoft para configurar um conector personalizado para importar dados de terceiros de fontes de dados como o Salesforce, o Yahoo Messenger ou o Yammer. Isso permite que você arquive dados de fontes de dados de terceiros no Office 365 para que possa usar os recursos de conformidade do Office 365, como retenção legal, pesquisa de conteúdo e políticas de retenção para gerenciar a governança dos dados de terceiros da sua organização.
ms.openlocfilehash: 9a1767baadb237196161032166f78c06dc7e099b
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38685023"
---
# <a name="work-with-a-partner-to-archive-third-party-data-in-office-365"></a><span data-ttu-id="81683-104">Trabalhar com um parceiro para arquivar dados de terceiros no Office 365</span><span class="sxs-lookup"><span data-stu-id="81683-104">Work with a partner to archive third-party data in Office 365</span></span>

<span data-ttu-id="81683-105">Você pode trabalhar com um parceiro da Microsoft para importar e arquivar dados de uma fonte de dados de terceiros para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-105">You can work with a Microsoft Partner to import and archive data from a third-party data source to Office 365.</span></span> <span data-ttu-id="81683-106">Um parceiro pode fornecer um conector personalizado configurado para extrair itens da fonte de dados de terceiros (regularmente) e, em seguida, importar esses itens para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-106">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items to Office 365.</span></span> <span data-ttu-id="81683-107">O conector de parceiro converte o conteúdo de um item da fonte de dados em um formato de mensagem de email e, em seguida, armazena os itens em caixas de correio no Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-107">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes in Office 365.</span></span> <span data-ttu-id="81683-108">Após a importação dos dados de terceiros, é possível aplicar recursos de conformidade do Office 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria e políticas de retenção do Office 365 a esses dados.</span><span class="sxs-lookup"><span data-stu-id="81683-108">After third-party data is imported, you can apply Office 365 compliance features such as Litigation Hold, Content Search, In-Place Archiving, Auditing, and Office 365 retention policies to this data.</span></span>
  
<span data-ttu-id="81683-109">Veja a seguir uma visão geral do processo e as etapas necessárias para trabalhar com um parceiro da Microsoft para importar dados de terceiros para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data to Office 365.</span></span>

[<span data-ttu-id="81683-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="81683-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="81683-111">Step 2: Create and configure a third-party data mailbox in Office 365</span><span class="sxs-lookup"><span data-stu-id="81683-111">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[<span data-ttu-id="81683-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="81683-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="81683-113">Etapa 4: fornecer informações ao seu parceiro</span><span class="sxs-lookup"><span data-stu-id="81683-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="81683-114">Etapa 5: registrar o conector de dados de terceiros no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="81683-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="81683-115">Como funciona o processo de importação de dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="81683-115">How the third-party data import process works</span></span>

<span data-ttu-id="81683-116">A ilustração e a descrição a seguir explicam como funciona o processo de importação de dados de terceiros ao trabalhar com um parceiro.</span><span class="sxs-lookup"><span data-stu-id="81683-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![Como funciona o processo de importação de dados de terceiros](media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="81683-118">O cliente trabalha com o parceiro escolhido para configurar um conector que extrairá itens da fonte de dados de terceiros e, em seguida, importará esses itens para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Office 365.</span></span>
    
2. <span data-ttu-id="81683-119">O conector de parceiro se conecta a fontes de dados de terceiros por meio de uma API de terceiros (em uma base agendada ou definida) e extrai itens da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="81683-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="81683-120">O conector do parceiro converte o conteúdo de um item em um formato de mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="81683-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="81683-121">Consulte a seção [mais informações](#more-information) para obter uma descrição do esquema de formato de mensagem.</span><span class="sxs-lookup"><span data-stu-id="81683-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="81683-122">O conector de parceiro se conecta ao serviço do Azure no Office 365 usando o serviço Web do Exchange (EWS) por meio de um ponto de extremidade conhecido.</span><span class="sxs-lookup"><span data-stu-id="81683-122">Partner connector connects to the Azure service in Office 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="81683-p104">Os itens são importados para a caixa de correio de um usuário específico ou para uma caixa de correio de dados de terceiros "pega-tudo". Os critérios a seguir definem se um item será importado para a caixa de correio de um usuário específico ou para a caixa de correio de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-p104">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
    <span data-ttu-id="81683-125">a.</span><span class="sxs-lookup"><span data-stu-id="81683-125">a.</span></span> <span data-ttu-id="81683-126">**Itens que têm uma ID de usuário que corresponde a uma conta de usuário do Office 365:** Se o conector de parceiro puder mapear a ID de usuário do item da fonte de dados de terceiros para uma ID de usuário específica no Office 365, o item será copiado para a pasta **limpezas** na pasta itens recuperáveis do usuário.</span><span class="sxs-lookup"><span data-stu-id="81683-126">**Items that have a user ID that corresponds to an Office 365 user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Office 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="81683-127">Os usuários não podem acessar os itens na pasta Remoções.</span><span class="sxs-lookup"><span data-stu-id="81683-127">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="81683-128">No entanto, você pode usar as ferramentas de descoberta eletrônica do Office 365 para pesquisar itens na pasta expurgações.</span><span class="sxs-lookup"><span data-stu-id="81683-128">However, you can use Office 365 eDiscovery tools to search for items in the Purges folder.</span></span>
    
    <span data-ttu-id="81683-129">b.</span><span class="sxs-lookup"><span data-stu-id="81683-129">b.</span></span> <span data-ttu-id="81683-130">**Itens que não têm uma ID de usuário que corresponda a uma conta de usuário do Office 365:** Se o conector de parceiro não puder mapear a ID de usuário de um item para uma ID de usuário específica no Office 365, o item será copiado para a pasta **caixa de entrada** da caixa de correio de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-130">**Items that don't have a user ID that corresponds to an Office 365 user account:** If the partner connector can't map the user ID of an item to a specific user ID in Office 365, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="81683-131">Importar itens para a caixa de entrada permite que você ou alguém em sua organização entre na caixa de correio de terceiros para exibir e gerenciar esses itens e ver se os ajustes precisam ser feitos na configuração do conector do parceiro.</span><span class="sxs-lookup"><span data-stu-id="81683-131">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="81683-132">Etapa 1: encontrar um parceiro de dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="81683-132">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="81683-133">Um componente fundamental para o arquivamento de dados de terceiros no Office 365 está encontrando e trabalhando com um parceiro da Microsoft especializado na captura de dados de uma fonte de dados de terceiros e importando-os para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-133">A key component for archiving third-party data in Office 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Office 365.</span></span> <span data-ttu-id="81683-134">Depois que os dados são importados, eles podem ser arquivados e preservados junto com outros dados da sua organização, como email do Exchange e documentos do SharePoint e do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="81683-134">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="81683-135">Um parceiro cria um conector que extrai dados das fontes de dados de terceiros de sua organização (como BlackBerry, Facebook, Google +, Thomson Reuters, Twitter e YouTube) e transmite esses dados para uma API do Office 365 que importa itens para caixas de correio do Exchange como mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="81683-135">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to an Office 365 API that imports items to Exchange mailboxes as email messages.</span></span> 
  
<span data-ttu-id="81683-136">As seções a seguir listam os parceiros da Microsoft (e as fontes de dados de terceiros que eles dão suporte) que estão participando do programa para arquivar dados de terceiros no Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-136">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Office 365.</span></span>

[<span data-ttu-id="81683-137">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="81683-137">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="81683-138">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="81683-138">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="81683-139">Globanet</span><span class="sxs-lookup"><span data-stu-id="81683-139">Globanet</span></span>](#globanet)
  
[<span data-ttu-id="81683-140">OpenText</span><span class="sxs-lookup"><span data-stu-id="81683-140">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="81683-141">Smarsh</span><span class="sxs-lookup"><span data-stu-id="81683-141">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="81683-142">Verba</span><span class="sxs-lookup"><span data-stu-id="81683-142">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="81683-143">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="81683-143">17a-4 LLC</span></span>

<span data-ttu-id="81683-144">o [17a-4 LLC](https://www.17a-4.com) suporta as seguintes fontes de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-144">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="81683-145">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="81683-145">BlackBerry</span></span>
    
- <span data-ttu-id="81683-146">Fluxos de dados do Bloomberg</span><span class="sxs-lookup"><span data-stu-id="81683-146">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="81683-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="81683-147">Cisco Jabber</span></span>
    
- <span data-ttu-id="81683-148">FactSet</span><span class="sxs-lookup"><span data-stu-id="81683-148">FactSet</span></span>
    
- <span data-ttu-id="81683-149">HipChat</span><span class="sxs-lookup"><span data-stu-id="81683-149">HipChat</span></span>
    
- <span data-ttu-id="81683-150">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="81683-150">InvestEdge</span></span>
    
- <span data-ttu-id="81683-151">LivePerson</span><span class="sxs-lookup"><span data-stu-id="81683-151">LivePerson</span></span>
    
- <span data-ttu-id="81683-152">MessageLabs Data Streams</span><span class="sxs-lookup"><span data-stu-id="81683-152">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="81683-153">OpenText</span><span class="sxs-lookup"><span data-stu-id="81683-153">OpenText</span></span>
    
- <span data-ttu-id="81683-154">Oracle/ATG 'click-to-call' Live Help</span><span class="sxs-lookup"><span data-stu-id="81683-154">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="81683-155">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="81683-155">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="81683-156">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="81683-156">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="81683-157">MindAlign</span><span class="sxs-lookup"><span data-stu-id="81683-157">MindAlign</span></span>
    
- <span data-ttu-id="81683-158">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="81683-158">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="81683-159">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="81683-159">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="81683-160">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="81683-160">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="81683-161">Bancos de dados SQL</span><span class="sxs-lookup"><span data-stu-id="81683-161">SQL Databases</span></span>
    
- <span data-ttu-id="81683-162">Squawker</span><span class="sxs-lookup"><span data-stu-id="81683-162">Squawker</span></span>
    
- <span data-ttu-id="81683-163">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="81683-163">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="81683-164">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="81683-164">ArchiveSocial</span></span>

<span data-ttu-id="81683-165">O [ArchiveSocial](https://www.archivesocial.com) suporta as seguintes fontes de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-165">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="81683-166">Facebook</span><span class="sxs-lookup"><span data-stu-id="81683-166">Facebook</span></span>
    
- <span data-ttu-id="81683-167">Flickr</span><span class="sxs-lookup"><span data-stu-id="81683-167">Flickr</span></span>
    
- <span data-ttu-id="81683-168">Instagram</span><span class="sxs-lookup"><span data-stu-id="81683-168">Instagram</span></span>
    
- <span data-ttu-id="81683-169">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="81683-169">LinkedIn</span></span>
    
- <span data-ttu-id="81683-170">Pinterest</span><span class="sxs-lookup"><span data-stu-id="81683-170">Pinterest</span></span>
    
- <span data-ttu-id="81683-171">Twitter</span><span class="sxs-lookup"><span data-stu-id="81683-171">Twitter</span></span>
    
- <span data-ttu-id="81683-172">YouTube</span><span class="sxs-lookup"><span data-stu-id="81683-172">YouTube</span></span>
    
- <span data-ttu-id="81683-173">Vimeo</span><span class="sxs-lookup"><span data-stu-id="81683-173">Vimeo</span></span>
  
### <a name="globanet"></a><span data-ttu-id="81683-174">Globanet</span><span class="sxs-lookup"><span data-stu-id="81683-174">Globanet</span></span>

<span data-ttu-id="81683-175">O [Globanet](https://www.globanet.com) suporta as seguintes fontes de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-175">[Globanet](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="81683-176">AOL with Pivot Client</span><span class="sxs-lookup"><span data-stu-id="81683-176">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="81683-177">BlackBerry Call Logs (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-177">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-178">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-178">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-179">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-179">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-180">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-180">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-181">Bloomberg Chat</span><span class="sxs-lookup"><span data-stu-id="81683-181">Bloomberg Chat</span></span>
    
- <span data-ttu-id="81683-182">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="81683-182">Bloomberg Mail</span></span>
    
- <span data-ttu-id="81683-183">Caixa</span><span class="sxs-lookup"><span data-stu-id="81683-183">Box</span></span>
    
- <span data-ttu-id="81683-184">CipherCloud for Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="81683-184">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="81683-185">Servidor de &amp; presença de im da Cisco (v10, v 10.5.1 SU1, v 11.0, v 11.5 SU2)</span><span class="sxs-lookup"><span data-stu-id="81683-185">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="81683-186">Equipes do Cisco WebEx</span><span class="sxs-lookup"><span data-stu-id="81683-186">Cisco Webex Teams</span></span>

- <span data-ttu-id="81683-187">Compartilhamento do &amp; Citrix Workspace</span><span class="sxs-lookup"><span data-stu-id="81683-187">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="81683-188">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="81683-188">CrowdCompass</span></span>

- <span data-ttu-id="81683-189">Arquivos de texto delimitados por personalização</span><span class="sxs-lookup"><span data-stu-id="81683-189">Custom-delimited text files</span></span>
    
- <span data-ttu-id="81683-190">Arquivos XML personalizados</span><span class="sxs-lookup"><span data-stu-id="81683-190">Custom XML files</span></span>
    
- <span data-ttu-id="81683-191">Facebook (páginas)</span><span class="sxs-lookup"><span data-stu-id="81683-191">Facebook (Pages)</span></span>
    
- <span data-ttu-id="81683-192">FactSet</span><span class="sxs-lookup"><span data-stu-id="81683-192">Factset</span></span>
    
- <span data-ttu-id="81683-193">FXConnect</span><span class="sxs-lookup"><span data-stu-id="81683-193">FXConnect</span></span>
    
- <span data-ttu-id="81683-194">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="81683-194">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="81683-195">Jive</span><span class="sxs-lookup"><span data-stu-id="81683-195">Jive</span></span>
    
- <span data-ttu-id="81683-196">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="81683-196">Macgregor XIP</span></span>

- <span data-ttu-id="81683-197">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="81683-197">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="81683-198">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="81683-198">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="81683-199">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="81683-199">Microsoft Teams</span></span>
       
- <span data-ttu-id="81683-200">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="81683-200">Microsoft Yammer</span></span>
    
- <span data-ttu-id="81683-201">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="81683-201">Mobile Guard</span></span>
    
- <span data-ttu-id="81683-202">Navegação dinâmica</span><span class="sxs-lookup"><span data-stu-id="81683-202">Pivot</span></span>
    
- <span data-ttu-id="81683-203">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="81683-203">Salesforce Chatter</span></span>

- <span data-ttu-id="81683-204">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="81683-204">Skype for Business Online</span></span>
    
- <span data-ttu-id="81683-205">Skype for Business, versões 2007 R2 - 2016 (local)</span><span class="sxs-lookup"><span data-stu-id="81683-205">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="81683-206">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="81683-206">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="81683-207">Symphony</span><span class="sxs-lookup"><span data-stu-id="81683-207">Symphony</span></span>
    
- <span data-ttu-id="81683-208">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="81683-208">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="81683-209">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="81683-209">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="81683-210">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="81683-210">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="81683-211">Twitter</span><span class="sxs-lookup"><span data-stu-id="81683-211">Twitter</span></span>
    
- <span data-ttu-id="81683-212">UBS Chat</span><span class="sxs-lookup"><span data-stu-id="81683-212">UBS Chat</span></span>
    
- <span data-ttu-id="81683-213">YouTube</span><span class="sxs-lookup"><span data-stu-id="81683-213">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="81683-214">OpenText</span><span class="sxs-lookup"><span data-stu-id="81683-214">OpenText</span></span>

<span data-ttu-id="81683-215">A [OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) suporta as seguintes fontes de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-215">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="81683-216">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="81683-216">Axs Encrypted</span></span>
    
- <span data-ttu-id="81683-217">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="81683-217">Axs Exchange</span></span>
    
- <span data-ttu-id="81683-218">Axs Local Archive</span><span class="sxs-lookup"><span data-stu-id="81683-218">Axs Local Archive</span></span>
    
- <span data-ttu-id="81683-219">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="81683-219">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="81683-220">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="81683-220">Axs Signed</span></span>
    
- <span data-ttu-id="81683-221">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="81683-221">Bloomberg</span></span>
    
- <span data-ttu-id="81683-222">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="81683-222">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="81683-223">Smarsh</span><span class="sxs-lookup"><span data-stu-id="81683-223">Smarsh</span></span>

<span data-ttu-id="81683-224">O [Smarsh](https://www.smarsh.com) suporta as seguintes fontes de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-224">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="81683-225">META</span><span class="sxs-lookup"><span data-stu-id="81683-225">AIM</span></span>
    
- <span data-ttu-id="81683-226">American Idol</span><span class="sxs-lookup"><span data-stu-id="81683-226">American Idol</span></span>
    
- <span data-ttu-id="81683-227">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="81683-227">Apple Juice</span></span>
    
- <span data-ttu-id="81683-228">AOL with Pivot Client</span><span class="sxs-lookup"><span data-stu-id="81683-228">AOL with Pivot client</span></span>
    
- <span data-ttu-id="81683-229">Ares</span><span class="sxs-lookup"><span data-stu-id="81683-229">Ares</span></span>
    
- <span data-ttu-id="81683-230">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="81683-230">Bazaar Voice</span></span>
    
- <span data-ttu-id="81683-231">Bear Share</span><span class="sxs-lookup"><span data-stu-id="81683-231">Bear Share</span></span>
    
- <span data-ttu-id="81683-232">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="81683-232">Bit Torrent</span></span>
    
- <span data-ttu-id="81683-233">BlackBerry Call Logs (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-233">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-234">BlackBerry Messenger (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-234">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-235">BlackBerry PIN (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-235">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-236">BlackBerry SMS (v5, v10, v12)</span><span class="sxs-lookup"><span data-stu-id="81683-236">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="81683-237">Bloomberg Mail</span><span class="sxs-lookup"><span data-stu-id="81683-237">Bloomberg Mail</span></span>
    
- <span data-ttu-id="81683-238">CellTrust</span><span class="sxs-lookup"><span data-stu-id="81683-238">CellTrust</span></span>
    
- <span data-ttu-id="81683-239">Importação de bate-papo</span><span class="sxs-lookup"><span data-stu-id="81683-239">Chat Import</span></span>
    
- <span data-ttu-id="81683-240">Política e registros de bate-papo em tempo real</span><span class="sxs-lookup"><span data-stu-id="81683-240">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="81683-241">Instabilidade</span><span class="sxs-lookup"><span data-stu-id="81683-241">Chatter</span></span>
    
- <span data-ttu-id="81683-242">Servidor de &amp; presença de im da Cisco (v 9.0.1, v 9.1, v 9.1.1 SU1, v10, v 10.5.1 SU1)</span><span class="sxs-lookup"><span data-stu-id="81683-242">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="81683-243">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span><span class="sxs-lookup"><span data-stu-id="81683-243">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="81683-244">Importação de colaboração</span><span class="sxs-lookup"><span data-stu-id="81683-244">Collaboration Import</span></span>
    
- <span data-ttu-id="81683-245">Registro de colaboração em tempo real</span><span class="sxs-lookup"><span data-stu-id="81683-245">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="81683-246">Conexão Direta</span><span class="sxs-lookup"><span data-stu-id="81683-246">Direct Connect</span></span>
    
- <span data-ttu-id="81683-247">Facebook</span><span class="sxs-lookup"><span data-stu-id="81683-247">Facebook</span></span>
    
- <span data-ttu-id="81683-248">FactSet</span><span class="sxs-lookup"><span data-stu-id="81683-248">FactSet</span></span>
    
- <span data-ttu-id="81683-249">FastTrack</span><span class="sxs-lookup"><span data-stu-id="81683-249">FastTrack</span></span>
    
- <span data-ttu-id="81683-250">Gnutella</span><span class="sxs-lookup"><span data-stu-id="81683-250">Gnutella</span></span>
    
- <span data-ttu-id="81683-251">Google +</span><span class="sxs-lookup"><span data-stu-id="81683-251">Google+</span></span>
    
- <span data-ttu-id="81683-252">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="81683-252">GoToMyPC</span></span>
    
- <span data-ttu-id="81683-253">Hopster</span><span class="sxs-lookup"><span data-stu-id="81683-253">Hopster</span></span>
    
- <span data-ttu-id="81683-254">HubConnex</span><span class="sxs-lookup"><span data-stu-id="81683-254">HubConnex</span></span>
    
- <span data-ttu-id="81683-255">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span><span class="sxs-lookup"><span data-stu-id="81683-255">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="81683-256">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="81683-256">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="81683-257">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="81683-257">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="81683-258">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="81683-258">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="81683-259">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="81683-259">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="81683-260">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span><span class="sxs-lookup"><span data-stu-id="81683-260">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="81683-261">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="81683-261">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="81683-262">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="81683-262">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="81683-263">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="81683-263">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="81683-264">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="81683-264">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="81683-265">Importação de mensagem Instantânea</span><span class="sxs-lookup"><span data-stu-id="81683-265">IM Import</span></span>
    
- <span data-ttu-id="81683-266">Política e registro de mensagem instantânea em tempo real</span><span class="sxs-lookup"><span data-stu-id="81683-266">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="81683-267">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="81683-267">Indii Messenger</span></span>
    
- <span data-ttu-id="81683-268">Instant Bloomberg</span><span class="sxs-lookup"><span data-stu-id="81683-268">Instant Bloomberg</span></span>
    
- <span data-ttu-id="81683-269">IRC</span><span class="sxs-lookup"><span data-stu-id="81683-269">IRC</span></span>
    
- <span data-ttu-id="81683-270">Jive</span><span class="sxs-lookup"><span data-stu-id="81683-270">Jive</span></span>
    
- <span data-ttu-id="81683-271">Jive 6 Real Time Logging (v6, v7)</span><span class="sxs-lookup"><span data-stu-id="81683-271">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="81683-272">Jive Import</span><span class="sxs-lookup"><span data-stu-id="81683-272">Jive Import</span></span>
    
- <span data-ttu-id="81683-273">JXTA</span><span class="sxs-lookup"><span data-stu-id="81683-273">JXTA</span></span>
    
- <span data-ttu-id="81683-274">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="81683-274">LinkedIn</span></span>
    
- <span data-ttu-id="81683-275">Microsoft Lync (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="81683-275">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="81683-276">MFTP</span><span class="sxs-lookup"><span data-stu-id="81683-276">MFTP</span></span>
    
- <span data-ttu-id="81683-277">Microsoft Lync 2013 Voice</span><span class="sxs-lookup"><span data-stu-id="81683-277">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="81683-278">Microsoft SharePoint (2010, 2013)</span><span class="sxs-lookup"><span data-stu-id="81683-278">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="81683-279">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="81683-279">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="81683-280">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="81683-280">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="81683-281">MindAlign</span><span class="sxs-lookup"><span data-stu-id="81683-281">MindAlign</span></span>
    
- <span data-ttu-id="81683-282">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="81683-282">Mobile Guard</span></span>
    
- <span data-ttu-id="81683-283">MSN</span><span class="sxs-lookup"><span data-stu-id="81683-283">MSN</span></span>
    
- <span data-ttu-id="81683-284">My Space</span><span class="sxs-lookup"><span data-stu-id="81683-284">My Space</span></span>
    
- <span data-ttu-id="81683-285">NEONetwork</span><span class="sxs-lookup"><span data-stu-id="81683-285">NEONetwork</span></span>
    
- <span data-ttu-id="81683-286">Office 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="81683-286">Office 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="81683-287">Office 365 Shared IM</span><span class="sxs-lookup"><span data-stu-id="81683-287">Office 365 Shared IM</span></span>
    
- <span data-ttu-id="81683-288">Pinterest</span><span class="sxs-lookup"><span data-stu-id="81683-288">Pinterest</span></span>
    
- <span data-ttu-id="81683-289">Navegação dinâmica</span><span class="sxs-lookup"><span data-stu-id="81683-289">Pivot</span></span>
    
- <span data-ttu-id="81683-290">QQ</span><span class="sxs-lookup"><span data-stu-id="81683-290">QQ</span></span>
    
- <span data-ttu-id="81683-291">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="81683-291">Skype for Business 2015</span></span>
    
- <span data-ttu-id="81683-292">SoftEther</span><span class="sxs-lookup"><span data-stu-id="81683-292">SoftEther</span></span>
    
- <span data-ttu-id="81683-293">Symphony</span><span class="sxs-lookup"><span data-stu-id="81683-293">Symphony</span></span>
    
- <span data-ttu-id="81683-294">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="81683-294">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="81683-295">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="81683-295">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="81683-296">Tor</span><span class="sxs-lookup"><span data-stu-id="81683-296">Tor</span></span>
    
- <span data-ttu-id="81683-297">TTT</span><span class="sxs-lookup"><span data-stu-id="81683-297">TTT</span></span>
    
- <span data-ttu-id="81683-298">Twitter</span><span class="sxs-lookup"><span data-stu-id="81683-298">Twitter</span></span>
    
- <span data-ttu-id="81683-299">WinMX</span><span class="sxs-lookup"><span data-stu-id="81683-299">WinMX</span></span>
    
- <span data-ttu-id="81683-300">Winny</span><span class="sxs-lookup"><span data-stu-id="81683-300">Winny</span></span>
    
- <span data-ttu-id="81683-301">Instant</span><span class="sxs-lookup"><span data-stu-id="81683-301">Yahoo</span></span>
    
- <span data-ttu-id="81683-302">Yammer</span><span class="sxs-lookup"><span data-stu-id="81683-302">Yammer</span></span>
    
- <span data-ttu-id="81683-303">YouTube</span><span class="sxs-lookup"><span data-stu-id="81683-303">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="81683-304">Verba</span><span class="sxs-lookup"><span data-stu-id="81683-304">Verba</span></span>

<span data-ttu-id="81683-305">O [verba](https://www.verba.com) suporta as seguintes fontes de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-305">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="81683-306">Avaya Aura Video</span><span class="sxs-lookup"><span data-stu-id="81683-306">Avaya Aura Video</span></span>
    
- <span data-ttu-id="81683-307">Avaya Aura Voice</span><span class="sxs-lookup"><span data-stu-id="81683-307">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="81683-308">Avtec Radio</span><span class="sxs-lookup"><span data-stu-id="81683-308">Avtec Radio</span></span>
    
- <span data-ttu-id="81683-309">Bosch/Telex Radio</span><span class="sxs-lookup"><span data-stu-id="81683-309">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="81683-310">BroadSoft Vídeo</span><span class="sxs-lookup"><span data-stu-id="81683-310">BroadSoft Video</span></span>
    
- <span data-ttu-id="81683-311">BroadSoft Voice</span><span class="sxs-lookup"><span data-stu-id="81683-311">BroadSoft Voice</span></span>
    
- <span data-ttu-id="81683-312">Centile Voice</span><span class="sxs-lookup"><span data-stu-id="81683-312">Centile Voice</span></span>
    
- <span data-ttu-id="81683-313">Cisco Jabber IM</span><span class="sxs-lookup"><span data-stu-id="81683-313">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="81683-314">Cisco UC Video</span><span class="sxs-lookup"><span data-stu-id="81683-314">Cisco UC Video</span></span>
    
- <span data-ttu-id="81683-315">Cisco UC Voice</span><span class="sxs-lookup"><span data-stu-id="81683-315">Cisco UC Voice</span></span>
    
- <span data-ttu-id="81683-316">Vídeo do Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="81683-316">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="81683-317">Voz do Cisco UCCX/UCCE</span><span class="sxs-lookup"><span data-stu-id="81683-317">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="81683-318">ESChat Radio</span><span class="sxs-lookup"><span data-stu-id="81683-318">ESChat Radio</span></span>
    
- <span data-ttu-id="81683-319">Geoman Contact Expert</span><span class="sxs-lookup"><span data-stu-id="81683-319">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="81683-320">IP Trade Voice</span><span class="sxs-lookup"><span data-stu-id="81683-320">IP Trade Voice</span></span>
    
- <span data-ttu-id="81683-321">Luware LUCS Contact Center</span><span class="sxs-lookup"><span data-stu-id="81683-321">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="81683-322">Microsoft UC (Unified Communications)</span><span class="sxs-lookup"><span data-stu-id="81683-322">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="81683-323">Mitel MiContact Center for Lync (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="81683-323">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="81683-324">Oracle / Acme Packet Session Border Controller Video</span><span class="sxs-lookup"><span data-stu-id="81683-324">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="81683-325">Oracle / Acme Packet Session Border Controller Voice</span><span class="sxs-lookup"><span data-stu-id="81683-325">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="81683-326">Singtel Mobile Voice</span><span class="sxs-lookup"><span data-stu-id="81683-326">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="81683-327">SIPREC Video</span><span class="sxs-lookup"><span data-stu-id="81683-327">SIPREC Video</span></span>
    
-  <span data-ttu-id="81683-328">SIPREC Voice</span><span class="sxs-lookup"><span data-stu-id="81683-328">SIPREC Voice</span></span> 
    
- <span data-ttu-id="81683-329">Skype for Business / Lync IM</span><span class="sxs-lookup"><span data-stu-id="81683-329">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="81683-330">Skype for Business / Lync Video</span><span class="sxs-lookup"><span data-stu-id="81683-330">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="81683-331">Skype for Business / Lync Voice</span><span class="sxs-lookup"><span data-stu-id="81683-331">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="81683-332">Speakerbus Voice</span><span class="sxs-lookup"><span data-stu-id="81683-332">Speakerbus Voice</span></span>
    
- <span data-ttu-id="81683-333">Standard SIP/H.323 Video</span><span class="sxs-lookup"><span data-stu-id="81683-333">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="81683-334">Standard SIP/H.323 Voice</span><span class="sxs-lookup"><span data-stu-id="81683-334">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="81683-335">Truphone Voice</span><span class="sxs-lookup"><span data-stu-id="81683-335">Truphone Voice</span></span>
    
- <span data-ttu-id="81683-336">TwistedPair Radio</span><span class="sxs-lookup"><span data-stu-id="81683-336">TwistedPair Radio</span></span>
    
- <span data-ttu-id="81683-337">Windows Desktop Computer Screen</span><span class="sxs-lookup"><span data-stu-id="81683-337">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a><span data-ttu-id="81683-338">Etapa 2: criar e configurar uma caixa de correio de dados de terceiros no Office 365</span><span class="sxs-lookup"><span data-stu-id="81683-338">Step 2: Create and configure a third-party data mailbox in Office 365</span></span>

<span data-ttu-id="81683-339">Aqui estão as etapas para criar e configurar uma caixa de correio de dados de terceiros para importar dados para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-339">Here are the steps for creating and configuring a third-party data mailbox for importing data to Office 365.</span></span> <span data-ttu-id="81683-340">Como explicado anteriormente, os itens são importados para esta caixa de correio se o conector de parceiro não puder mapear a ID de usuário do item para uma conta de usuário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-340">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to an Office 365 user account.</span></span>
  
 <span data-ttu-id="81683-341">**Concluir estas tarefas no centro de administração do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="81683-341">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="81683-342">Criar uma conta de usuário no Office 365 e atribuí-la a uma licença do Exchange Online Plan 2; consulte [Adicionar usuários ao Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span><span class="sxs-lookup"><span data-stu-id="81683-342">Create a user account in Office 365 and assign it an Exchange Online Plan 2 license; see [Add users to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098).</span></span> <span data-ttu-id="81683-343">Uma licença do plano 2 é necessária para colocar a caixa de correio em retenção de litígio ou habilitar uma caixa de correio de arquivo morto com uma cota de armazenamento ilimitada.</span><span class="sxs-lookup"><span data-stu-id="81683-343">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="81683-344">Adicione a conta de usuário para a caixa de correio de dados de terceiros à função de administrador de **Administradores do Exchange** no Office 365; Confira [atribuir funções de administrador no Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span><span class="sxs-lookup"><span data-stu-id="81683-344">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Office 365; see [Assign admin roles in Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="81683-345">Anote as credenciais da conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="81683-345">Write down the credentials for this user account.</span></span> <span data-ttu-id="81683-346">Você precisa enviá-las para o seu parceiro, conforme descrito na Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="81683-346">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="81683-347">**Concluir estas tarefas no centro de administração do Exchange**</span><span class="sxs-lookup"><span data-stu-id="81683-347">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="81683-348">Ocultar a caixa de correio de dados de terceiros no catálogo de endereços e em outras listas de endereços em sua organização; consulte [manage user Mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span><span class="sxs-lookup"><span data-stu-id="81683-348">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058).</span></span> <span data-ttu-id="81683-349">Como alternativa, você pode executar o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="81683-349">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="81683-350">Atribua a permissão **FullAccess** à caixa de correio de dados de terceiros para que administradores ou gerentes de conformidade possam abrir a caixa de correio de dados de terceiros no cliente da área de trabalho do Outlook; consulte [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span><span class="sxs-lookup"><span data-stu-id="81683-350">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="81683-351">Habilite os seguintes recursos do Office 365 relacionados à conformidade para a caixa de correio de dados de terceiros:</span><span class="sxs-lookup"><span data-stu-id="81683-351">Enable the following compliance-related Office 365 features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="81683-352">Habilitar a caixa de correio de arquivo morto; consulte [habilitar caixas de correio de arquivo morto](enable-archive-mailboxes.md) e [habilitar o arquivamento ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="81683-352">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="81683-353">Isso permite que você libere espaço de armazenamento na caixa de correio principal Configurando uma política de arquivamento que move itens de dados de terceiros para a caixa de correio de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="81683-353">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="81683-354">Isso fornece armazenamento ilimitado para dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-354">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="81683-355">Colocar a caixa de correio de dados de terceiros em Retenção de Litígio.</span><span class="sxs-lookup"><span data-stu-id="81683-355">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="81683-356">Você também pode aplicar uma política de retenção do Office 365 no centro de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="81683-356">You can also apply an Office 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="81683-357">Colocar esta caixa de correio em retenção mantém itens de dados de terceiros (indefinidamente ou por um período especificado) e impede que eles sejam excluídos da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="81683-357">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="81683-358">Consulte um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="81683-358">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="81683-359">Colocar uma caixa de correio em Retenção de Litígio</span><span class="sxs-lookup"><span data-stu-id="81683-359">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [<span data-ttu-id="81683-360">Visão geral das políticas de retenção no Office 365</span><span class="sxs-lookup"><span data-stu-id="81683-360">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    - <span data-ttu-id="81683-361">Para habilitar o log de auditoria da caixa de correio para acesso de proprietário, representante e administrador à caixa de correio de dados de terceiros, consulte [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="81683-361">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing in Office 365](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="81683-362">Isso permite que você faça a auditoria de todas as atividades realizadas por qualquer usuário que tenha acesso à caixa de correio de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-362">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="81683-363">Etapa 3: configurar caixas de correio de usuário para dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="81683-363">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="81683-364">A próxima etapa é configurar as caixas de correio do usuário para oferecer suporte a dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-364">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="81683-365">Conclua essas tarefas usando o centro de administração do Exchange ou usando os cmdlets do Windows PowerShell correspondentes.</span><span class="sxs-lookup"><span data-stu-id="81683-365">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="81683-366">Habilitar a caixa de correio de arquivo morto para cada usuário; consulte [habilitar caixas de correio de arquivo morto](enable-archive-mailboxes.md) e [habilitar o arquivamento ilimitado](enable-unlimited-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="81683-366">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="81683-367">Coloque as caixas de correio do usuário em retenção de litígio ou aplique uma política de retenção do Office 365; consulte um dos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="81683-367">Place user mailboxes on Litigation Hold or apply an Office 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="81683-368">Colocar uma caixa de correio em Retenção de Litígio</span><span class="sxs-lookup"><span data-stu-id="81683-368">Place a mailbox on Litigation Hold</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [<span data-ttu-id="81683-369">Visão geral das políticas de retenção no Office 365</span><span class="sxs-lookup"><span data-stu-id="81683-369">Overview of retention policies in Office 365</span></span>](retention-policies.md)
    
    <span data-ttu-id="81683-370">Conforme mencionado anteriormente, quando você coloca as caixas de correio em retenção, é possível definir uma duração para a retenção dos itens da fonte de dados de terceiros, ou você pode optar por reter itens indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="81683-370">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="81683-371">Etapa 4: fornecer informações ao seu parceiro</span><span class="sxs-lookup"><span data-stu-id="81683-371">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="81683-372">A etapa final é fornecer a seu parceiro as informações a seguir, para que ele possa configurar o conector a fim de se conectar à sua organização do Office 365 e importar dados para as caixas de correio do usuário e para a caixa de correio de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-372">The final step is to provide your partner with the following information so they can configure the connector to connect to your Office 365 organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="81683-373">O ponto de extremidade usado para se conectar ao serviço do Azure no Office 365:</span><span class="sxs-lookup"><span data-stu-id="81683-373">The endpoint used to connect to the Azure service in Office 365:</span></span>

    ```text
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="81683-374">As credenciais de entrada (ID de usuário e senha do Office 365) da caixa de correio de dados de terceiros que você criou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="81683-374">The sign in credentials (Office 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="81683-375">Essas credenciais são necessárias para que o conector do parceiro possa acessar e importar itens para a caixa de correio do usuário e a caixa de correio de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-375">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="81683-376">Etapa 5: registrar o conector de dados de terceiros no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="81683-376">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="81683-377">Desde 30 de setembro de 2018, o serviço do Azure no Office 365 começará a usar a autenticação moderna no Exchange Online para autenticar conectores de dados de terceiros que tentam se conectar à sua organização do Office 365 para importar dados.</span><span class="sxs-lookup"><span data-stu-id="81683-377">Starting September 30, 2018, the Azure service in Office 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your Office 365 organization to import data.</span></span> <span data-ttu-id="81683-378">O motivo dessa alteração é que a autenticação moderna fornece mais segurança do que o método atual, que se baseia em conectores de terceiros em lista branca que usam o ponto de extremidade descrito anteriormente para se conectar ao serviço do Azure.</span><span class="sxs-lookup"><span data-stu-id="81683-378">The reason for this change is that modern authentication provides more security than the current method, which was based on whitelisting third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="81683-379">Para permitir que um conector de dados de terceiros se conecte ao Office 365 usando o novo método de autenticação moderna, um administrador na sua organização do Office 365 deve se concordar em registrar o conector como um aplicativo de serviço confiável no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81683-379">To enable a third-party data connector to connect to Office 365 using the new modern authentication method, an administrator in your Office 365 organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="81683-380">Isso é feito aceitando uma solicitação de permissão para permitir que o conector acesse os dados da sua organização no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81683-380">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="81683-381">Depois que você aceita essa solicitação, o conector de dados de terceiros é adicionado como um aplicativo corporativo ao Azure Active Directory e representado como uma entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="81683-381">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="81683-382">Para obter mais informações sobre o processo de consentimento, consulte [consentimento do administrador do locatário](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span><span class="sxs-lookup"><span data-stu-id="81683-382">For more information the consent process, see  [Tenant Admin Consent](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="81683-383">Aqui estão as etapas para acessar e aceitar a solicitação de registro do conector:</span><span class="sxs-lookup"><span data-stu-id="81683-383">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="81683-384">Vá até [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entre usando as credenciais de um administrador global do Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-384">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of an Office 365 global administrator.</span></span><br/><br/><span data-ttu-id="81683-385">A caixa de diálogo a seguir é exibida.</span><span class="sxs-lookup"><span data-stu-id="81683-385">The following dialog box is displayed.</span></span> <span data-ttu-id="81683-386">Você pode expandir os acentos para revisar as permissões que serão atribuídas ao conector.</span><span class="sxs-lookup"><span data-stu-id="81683-386">You can expand the carets to review the permissions that will be assigned to the connector.</span></span><br/><br/><span data-ttu-id="81683-387">![A caixa de diálogo de solicitação de permissões é exibida](media/O365-ThirdPartyDataConnector-OptIn1.png)</span><span class="sxs-lookup"><span data-stu-id="81683-387">![The permissions request dialog is displayed](media/O365-ThirdPartyDataConnector-OptIn1.png)</span></span>
2. <span data-ttu-id="81683-388">Clique em **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="81683-388">Click **Accept**.</span></span>

<span data-ttu-id="81683-389">Após aceitar a solicitação, o [portal do Azure](https://portal.azure.com) é exibido.</span><span class="sxs-lookup"><span data-stu-id="81683-389">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="81683-390">Para exibir a lista de aplicativos da sua organização, clique em**aplicativos corporativos** **do Azure Active Directory** > .</span><span class="sxs-lookup"><span data-stu-id="81683-390">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="81683-391">O conector de dados de terceiros do Office 365 está listado na folha **aplicativos empresariais** .</span><span class="sxs-lookup"><span data-stu-id="81683-391">The Office 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81683-392">Após 30 de setembro de 2018, os dados de terceiros não serão mais importados para caixas de correio em sua organização se você não registrar um conector de dados de terceiros no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81683-392">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="81683-393">Observação os conectores de dados de terceiros existentes (aqueles criados antes de 30 de setembro de 2018) também devem ser registrados no Azure Active Directory seguindo o procedimento na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="81683-393">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="81683-394">Revogar o consentimento de um conector de dados de terceiros</span><span class="sxs-lookup"><span data-stu-id="81683-394">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="81683-395">Depois que sua organização concorda com a solicitação de permissões para registrar um conector de dados de terceiros no Azure Active Directory, sua organização pode revogar esse consentimento a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="81683-395">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="81683-396">No entanto, revogar o consentimento de um conector significa que os dados da fonte de dados de terceiros não serão mais importados para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-396">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Office 365.</span></span>

<span data-ttu-id="81683-397">Para revogar o consentimento de um conector de dados de terceiros, você pode excluir o aplicativo (excluindo a entidade de serviço correspondente) do Azure Active Directory usando a lâmina **aplicativos corporativos** no portal do Azure ou usando o [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) no Office 365 PowerShell.</span><span class="sxs-lookup"><span data-stu-id="81683-397">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) in Office 365 PowerShell.</span></span> <span data-ttu-id="81683-398">Você também pode usar o cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) no PowerShell do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="81683-398">You can also use the [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="81683-399">Mais informações</span><span class="sxs-lookup"><span data-stu-id="81683-399">More information</span></span>

- <span data-ttu-id="81683-400">Conforme explicado anteriormente, os itens de fontes de dados de terceiros são importados para caixas de correio do Exchange como mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="81683-400">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="81683-401">O conector de parceiro importa o item usando um esquema exigido pela API do Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-401">The partner connector imports the item using a schema required by the Office 365 API.</span></span> <span data-ttu-id="81683-402">A tabela a seguir descreve as propriedades de mensagem de um item de uma fonte de dados de terceiros após importá-lo para uma caixa de correio do Exchange como uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="81683-402">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="81683-403">A tabela também indica se a propriedade da mensagem é obrigatória.</span><span class="sxs-lookup"><span data-stu-id="81683-403">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="81683-404">As propriedades obrigatórias devem ser preenchidas.</span><span class="sxs-lookup"><span data-stu-id="81683-404">Mandatory properties must be populated.</span></span> <span data-ttu-id="81683-405">Se um item não tiver uma propriedade obrigatória, ele não será importado para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-405">If an item is missing a mandatory property, it won't be imported to Office 365.</span></span> <span data-ttu-id="81683-406">O processo de importação retorna uma mensagem de erro explicando por que um item não foi importado e qual propriedade está ausente.</span><span class="sxs-lookup"><span data-stu-id="81683-406">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span>
    
    |<span data-ttu-id="81683-407">**Propriedade da mensagem**</span><span class="sxs-lookup"><span data-stu-id="81683-407">**Message property**</span></span>|<span data-ttu-id="81683-408">**Obrigatório?**</span><span class="sxs-lookup"><span data-stu-id="81683-408">**Mandatory?**</span></span>|<span data-ttu-id="81683-409">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="81683-409">**Description**</span></span>|<span data-ttu-id="81683-410">**Valor de Exemplo**</span><span class="sxs-lookup"><span data-stu-id="81683-410">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="81683-411">**FROM**</span><span class="sxs-lookup"><span data-stu-id="81683-411">**FROM**</span></span> <br/> |<span data-ttu-id="81683-412">Sim</span><span class="sxs-lookup"><span data-stu-id="81683-412">Yes</span></span>  <br/> |<span data-ttu-id="81683-413">O usuário que criou ou enviou originalmente o item na fonte de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-413">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="81683-414">O conector de parceiro tenta mapear a ID de usuário do item de origem (por exemplo, um manipulador do Twitter) para uma conta de usuário do Office 365 para todos os participantes (usuários nos campos de e para).</span><span class="sxs-lookup"><span data-stu-id="81683-414">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to an Office 365 user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="81683-415">Uma cópia da mensagem será importada para a caixa de correio de cada participante.</span><span class="sxs-lookup"><span data-stu-id="81683-415">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="81683-416">Se nenhum dos participantes do item puder ser mapeado para uma conta de usuário do Office 365, o item será importado para a caixa de correio de arquivamento de terceiros no Office 365.</span><span class="sxs-lookup"><span data-stu-id="81683-416">If none of the participants from the item can be mapped to an Office 365 user account, the item will be imported to the third-party archiving mailbox in Office 365.</span></span>  <br/> <br/> <span data-ttu-id="81683-417">O participante identificado como o remetente do item deve ter uma caixa de correio ativa na organização do Office 365 à qual o item está sendo importado.</span><span class="sxs-lookup"><span data-stu-id="81683-417">The participant who's identified as the sender of the item must have an active mailbox in the Office 365 organization that the item is being imported to.</span></span> <span data-ttu-id="81683-418">Se o remetente não tem uma caixa de correio ativa, o seguinte erro é retornado:</span><span class="sxs-lookup"><span data-stu-id="81683-418">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="81683-419">**TO**</span><span class="sxs-lookup"><span data-stu-id="81683-419">**TO**</span></span> <br/> |<span data-ttu-id="81683-420">Sim</span><span class="sxs-lookup"><span data-stu-id="81683-420">Yes</span></span>  <br/> |<span data-ttu-id="81683-421">O usuário que recebeu um item, caso seja aplicável a um item na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="81683-421">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="81683-422">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="81683-422">**SUBJECT**</span></span> <br/> |<span data-ttu-id="81683-423">Não</span><span class="sxs-lookup"><span data-stu-id="81683-423">No</span></span>  <br/> |<span data-ttu-id="81683-424">O assunto do item de origem.</span><span class="sxs-lookup"><span data-stu-id="81683-424">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="81683-425">**PÓS-DATADOS**</span><span class="sxs-lookup"><span data-stu-id="81683-425">**DATE**</span></span> <br/> |<span data-ttu-id="81683-426">Sim</span><span class="sxs-lookup"><span data-stu-id="81683-426">Yes</span></span>  <br/> |<span data-ttu-id="81683-427">A data em que o item foi originalmente criado ou Postado na fonte de dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="81683-427">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="81683-428">Por exemplo, essa data quando uma mensagem do Twitter foi tweeted.</span><span class="sxs-lookup"><span data-stu-id="81683-428">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="81683-429">**ÓRGÃO**</span><span class="sxs-lookup"><span data-stu-id="81683-429">**BODY**</span></span> <br/> |<span data-ttu-id="81683-430">Não</span><span class="sxs-lookup"><span data-stu-id="81683-430">No</span></span>  <br/> |<span data-ttu-id="81683-431">O conteúdo da mensagem ou publicação.</span><span class="sxs-lookup"><span data-stu-id="81683-431">The contents of the message or post.</span></span> <span data-ttu-id="81683-432">Para algumas fontes de dados, o conteúdo dessa propriedade pode ser o mesmo que o conteúdo da propriedade **ASSUNTO**.</span><span class="sxs-lookup"><span data-stu-id="81683-432">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="81683-433">Durante o processo de importação, o conector parceiro tenta manter a fidelidade total da fonte de conteúdo possível.</span><span class="sxs-lookup"><span data-stu-id="81683-433">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="81683-434">Se for possível, arquivos, gráficos ou outros tipos de conteúdo do corpo do item de origem estarão incluídos nesta propriedade.</span><span class="sxs-lookup"><span data-stu-id="81683-434">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="81683-435">Caso contrário, o conteúdo do item de origem estará incluído na propriedade **ANEXO**.</span><span class="sxs-lookup"><span data-stu-id="81683-435">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="81683-436">O conteúdo dessa propriedade depende do conector de parceiro e da capacidade da plataforma de origem.</span><span class="sxs-lookup"><span data-stu-id="81683-436">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="81683-437">**ANEXAR**</span><span class="sxs-lookup"><span data-stu-id="81683-437">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="81683-438">Não</span><span class="sxs-lookup"><span data-stu-id="81683-438">No</span></span>  <br/> |<span data-ttu-id="81683-439">Se um item na fonte de dados (como um tweet no Twitter ou uma conversa de mensagem instantânea) tiver um arquivo anexado ou incluir imagens, a conexão de parceiro tentará primeiro incluir anexos na propriedade **Body** .</span><span class="sxs-lookup"><span data-stu-id="81683-439">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="81683-440">Se isso não for possível, então será adicionado à propriedade \* \* ATTACHMENT \* \*.</span><span class="sxs-lookup"><span data-stu-id="81683-440">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="81683-441">Outros exemplos de anexos incluem Curtidas no Facebook, metadados da fonte de conteúdo e respostas a uma mensagem ou publicação.</span><span class="sxs-lookup"><span data-stu-id="81683-441">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="81683-442">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="81683-442">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="81683-443">Sim</span><span class="sxs-lookup"><span data-stu-id="81683-443">Yes</span></span>  <br/> | <span data-ttu-id="81683-444">Esta é uma propriedade com múltiplos valores, que é criada e preenchida pelo conector parceiro.</span><span class="sxs-lookup"><span data-stu-id="81683-444">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="81683-445">O formato dessa propriedade é `IPM.NOTE.Source.Event`.</span><span class="sxs-lookup"><span data-stu-id="81683-445">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="81683-446">(Essa propriedade deve começar com `IPM.NOTE`.</span><span class="sxs-lookup"><span data-stu-id="81683-446">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="81683-447">Este formato é semelhante ao da classe de `IPM.NOTE.X` mensagens.) Esta propriedade inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="81683-447">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="81683-448">`Source`: Indica a fonte de dados de terceiros; por exemplo, Twitter, Facebook ou BlackBerry.</span><span class="sxs-lookup"><span data-stu-id="81683-448">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="81683-449">`Event`: Indica o tipo de atividade que foi executado na fonte de dados de terceiros que produziu os itens; por exemplo, um tweet no Twitter ou uma postagem no Facebook.</span><span class="sxs-lookup"><span data-stu-id="81683-449">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="81683-450">Eventos são específicos à fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="81683-450">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="81683-451">Uma finalidade dessa propriedade é filtrar itens específicos com base na fonte de dados na qual um item teve origem ou com base no tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="81683-451">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="81683-452">Por exemplo, em uma pesquisa de Descoberta Eletrônica você poderia criar uma consulta de pesquisa para encontrar todos os tweets publicados por um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="81683-452">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="81683-453">Quando os itens são importados com êxito para caixas de correio no Office 365, um identificador exclusivo é retornado de volta para o chamador como parte da resposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="81683-453">When items are successfully imported to mailboxes in Office 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="81683-454">Esse identificador, chamado `x-IngestionCorrelationID`, pode ser usado para fins de solução de problemas subsequentes por parceiros para o controle de ponta a ponta dos itens.</span><span class="sxs-lookup"><span data-stu-id="81683-454">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="81683-455">É recomendável que os parceiros capturem essas informações e as registrem de acordo no lado deles.</span><span class="sxs-lookup"><span data-stu-id="81683-455">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="81683-456">Veja aqui um exemplo de uma resposta HTTP que mostra esse identificador:</span><span class="sxs-lookup"><span data-stu-id="81683-456">Here's an example of an HTTP response showing this identifier:</span></span>

    ```text
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="81683-457">Você pode usar a ferramenta de pesquisa de conteúdo no centro de conformidade e segurança para pesquisar itens que foram importados para caixas de correio no Office 365 de uma fonte de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-457">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes in Office 365 from a third-party data source.</span></span> <span data-ttu-id="81683-458">Para pesquisar especificamente esses itens importados, você pode usar os seguintes pares de propriedade de mensagem-valor na caixa palavra-chave de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="81683-458">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="81683-459">**`kind:externaldata`**: Use este par de propriedade-valor para pesquisar todos os tipos de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-459">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="81683-460">Por exemplo, para pesquisar itens que foram importados de uma fonte de dados de terceiros e continham a palavra "contoso" na propriedade Subject do item importado, você usaria a `kind:externaldata AND subject:contoso`consulta de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="81683-460">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="81683-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Use este par de propriedade-valor para pesquisar apenas um tipo de dados de terceiros.</span><span class="sxs-lookup"><span data-stu-id="81683-461">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="81683-462">Por exemplo, para pesquisar apenas dados do Facebook que contenham a palavra "contoso" na propriedade Subject, você usaria a consulta `itemclass:ipm.externaldata.Facebook* AND subject:contoso`de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="81683-462">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="81683-463">Para obter uma lista completa de valores a serem usados para tipos de dados de terceiros `itemclass` para a propriedade, consulte [usar a pesquisa de conteúdo para pesquisar dados de terceiros que foram importados para o Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span><span class="sxs-lookup"><span data-stu-id="81683-463">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Office 365](use-content-search-to-search-third-party-data-that-was-imported.md)</span></span>
    
   <span data-ttu-id="81683-464">Veja mais informações sobre como usar a Pesquisa de Conteúdo e criar consultas de pesquisa de palavra-chave em:</span><span class="sxs-lookup"><span data-stu-id="81683-464">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="81683-465">Pesquisa de Conteúdo no Office 365</span><span class="sxs-lookup"><span data-stu-id="81683-465">Content Search in Office 365</span></span>](content-search.md)
    
  - [<span data-ttu-id="81683-466">Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="81683-466">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
 
