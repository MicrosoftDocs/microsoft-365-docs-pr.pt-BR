---
title: Alterar os nameservers para configurar o Microsoft com o Hostgator
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f3bd3c62-0477-48e4-b2b5-21e329d67985
description: Saiba como você pode configurar a Microsoft para gerenciar os registros DNS do seu domínio personalizado em Hostgator.
ms.openlocfilehash: 09f0409ed2a5f81b450c9aae7bb3699373ce6f22
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629882"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-hostgator"></a><span data-ttu-id="76ed9-103">Alterar os nameservers para configurar o Microsoft 365 com o Hostgator</span><span class="sxs-lookup"><span data-stu-id="76ed9-103">Change nameservers to set up Microsoft 365 with Hostgator</span></span>

 <span data-ttu-id="76ed9-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="76ed9-105">Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="76ed9-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="76ed9-106">Se preferir, [gerencie todos os registros DNS da Microsoft em Hostgator](create-dns-records-at-hostgator.md).</span><span class="sxs-lookup"><span data-stu-id="76ed9-106">(If you prefer, you can [manage all your Microsoft DNS records at Hostgator](create-dns-records-at-hostgator.md).)</span></span>
  
    
## <a name="point-your-domain-to-your-hosting-account"></a><span data-ttu-id="76ed9-107">Aponte o seu domínio para sua conta de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="76ed9-107">Point your domain to your hosting account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76ed9-108">Você deve executar esse procedimento antes do procedimento na seção a seguir, **Adicionar um registro TXT para verificação**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-108">You must perform this procedure before you perform the procedure in the following section, **Add a TXT record for verification**.</span></span>
  
<span data-ttu-id="76ed9-109">Siga estas etapas para associar seu domínio e as contas de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="76ed9-109">Follow these steps to associate your domain and hosting accounts.</span></span>
  
1. <span data-ttu-id="76ed9-p102">Para começar, vá até a sua página de gerenciamento de clientes na Hostgator usando [este link](https://portal.hostgator.com/domain/manage). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="76ed9-p102">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Conectando a lista de tarefas ao Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="76ed9-113">Selecione a guia **domínios** .</span><span class="sxs-lookup"><span data-stu-id="76ed9-113">Select the **Domains** tab.</span></span>
    
    ![Faixa de Opções do Office 14](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="76ed9-115">Na página **gerenciar domínios** , na área **meus domínios** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="76ed9-115">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span>
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="76ed9-117">Na página **visão geral de domínios** , na área **servidores de nomes** , selecione **alterar**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-117">On the **Domains Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Imagem do botão Definir cor transparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="76ed9-119">Na página **servidores de nomes** do seu domínio, na lista suspensa **selecionar conta de hospedagem** , escolha a conta de **hospedagem** associada ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="76ed9-119">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span>
    
    ![Painéis do Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="76ed9-121">Selecione **salvar servidores de nomes**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-121">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-9](../../media/b52a825a-6d54-49ba-87c8-52f770fdfa0c.png)
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="76ed9-123">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="76ed9-123">Add a TXT record for verification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76ed9-124">Antes de executar este procedimento, você deve primeiro executar o procedimento na primeira seção deste artigo, [aponte seu domínio para sua conta de hospedagem.](#point-your-domain-to-your-hosting-account).</span><span class="sxs-lookup"><span data-stu-id="76ed9-124">Before you perform this procedure, you must first perform the procedure in the first section of this article, [Point your domain to your hosting account.](#point-your-domain-to-your-hosting-account).</span></span>
  
<span data-ttu-id="76ed9-125">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="76ed9-125">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="76ed9-126">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="76ed9-126">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76ed9-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="76ed9-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span>
  
1. <span data-ttu-id="76ed9-p105">Para começar, vá para a página do cPanel no Hostgator. Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="76ed9-p105">To get started, go to your cPanel page at Hostgator. You'll be prompted to log in first.</span></span>
    
    <span data-ttu-id="76ed9-p106">(É atribuído um endereço cPanel exclusivo a cada conta hospedada no Hostgator. Seu endereço cPanel deve ter esta aparência: https://YourSiteAddress:secure-port-numberçoDoSeuSite:número-de-porta-segura. O email de inscrição recebido do Hostgator especificará esse endereço.)</span><span class="sxs-lookup"><span data-stu-id="76ed9-p106">(Each hosted account at Hostgator is assigned a unique cPanel address. Your cPanel address should look like this: https://YourSiteAddress:secure-port-number. The sign-up email you received from Hostgator will specify that address.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="76ed9-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span><span class="sxs-lookup"><span data-stu-id="76ed9-134">To have a cPanel associated with your domain, you need a hosting account with Hostgator.</span></span> <span data-ttu-id="76ed9-135">Para começar, você pode comprar uma conta de hospedagem do Hostgator ou [alterar os registros de nameserver (ns) do seu domínio](#change-your-domains-nameserver-ns-records) para apontar para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76ed9-135">To get started, you can either purchase a hosting account from Hostgator or [change your domain's nameserver (NS) records](#change-your-domains-nameserver-ns-records) to point to Microsoft.</span></span> 
  
2. <span data-ttu-id="76ed9-136">Na página **painel de controle** , na área **domínios** , selecione **Editor de zona de DNS avançado**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-136">On the **Control Panel** page, in the **Domains** area, select **Advanced DNS Zone Editor**.</span></span>
    
    <span data-ttu-id="76ed9-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="76ed9-137">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="76ed9-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="76ed9-138">On the **Advanced DNS Zone Editor** page, in the **Add a Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="76ed9-139">(Escolha o valor de **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="76ed9-139">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76ed9-140">**Nome**</span><span class="sxs-lookup"><span data-stu-id="76ed9-140">**Name**</span></span> <br/> |<span data-ttu-id="76ed9-141">**TTL**</span><span class="sxs-lookup"><span data-stu-id="76ed9-141">**TTL**</span></span> <br/> |<span data-ttu-id="76ed9-142">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="76ed9-142">**Type**</span></span> <br/> |<span data-ttu-id="76ed9-143">**Dados TXT**</span><span class="sxs-lookup"><span data-stu-id="76ed9-143">**TXT Data**</span></span> <br/> |
|<span data-ttu-id="76ed9-p108">Use seu  *domain_name*  . (por exemplo, fourthcoffee.com.)  </span><span class="sxs-lookup"><span data-stu-id="76ed9-p108">Use your  *domain_name*  . (for example, fourthcoffee.com.)  </span></span><br/> <span data-ttu-id="76ed9-146">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="76ed9-146">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="76ed9-147">1</span><span class="sxs-lookup"><span data-stu-id="76ed9-147">1</span></span>  <br/> |<span data-ttu-id="76ed9-148">TXT</span><span class="sxs-lookup"><span data-stu-id="76ed9-148">TXT</span></span>  <br/> |<span data-ttu-id="76ed9-149">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="76ed9-149">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="76ed9-150">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="76ed9-150">**Note:** This is an example.</span></span> <span data-ttu-id="76ed9-151">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="76ed9-151">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="76ed9-152">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="76ed9-152">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)     <br/>  |
   
4. <span data-ttu-id="76ed9-153">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-153">Select **Add Record**.</span></span>
    
5. <span data-ttu-id="76ed9-154">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="76ed9-154">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="76ed9-155">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="76ed9-155">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="76ed9-156">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="76ed9-156">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="76ed9-157">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="76ed9-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="76ed9-158">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="76ed9-158">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="76ed9-159">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-159">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="76ed9-160">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-160">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="76ed9-161">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="76ed9-161">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="76ed9-162">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="76ed9-162">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="76ed9-163">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="76ed9-163">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="76ed9-164">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="76ed9-164">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="76ed9-165">Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="76ed9-165">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="76ed9-166">Isso configura a Microsoft para atualizar os registros DNS do domínio para você.</span><span class="sxs-lookup"><span data-stu-id="76ed9-166">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="76ed9-167">Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="76ed9-167">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="76ed9-168">Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="76ed9-168">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="76ed9-169">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain* . com) começarão a ser iniciados pela Microsoft depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="76ed9-169">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="76ed9-170">O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados.</span><span class="sxs-lookup"><span data-stu-id="76ed9-170">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="76ed9-171">Quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**e **NS4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-171">When you have completed the steps in this section, the only nameservers that should be listed are these four:  **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span>
  
1. <span data-ttu-id="76ed9-p114">Para começar, vá até a sua página de gerenciamento de clientes na Hostgator usando [este link](https://portal.hostgator.com/domain/manage). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="76ed9-p114">To get started, go to your customer portal page at Hostgator by using [this link](https://portal.hostgator.com/domain/manage). You'll be prompted to log in.</span></span>
    
    ![Conectando a lista de tarefas ao Outlook](../../media/6749ac23-4832-4daf-8f3b-bc3b9b1b979c.png)
  
2. <span data-ttu-id="76ed9-175">Selecione a guia **domínios** .</span><span class="sxs-lookup"><span data-stu-id="76ed9-175">Select the **Domains** tab.</span></span> 
    
    ![Faixa de Opções do Office 14](../../media/56d12bfd-3549-4033-90dc-077c76ca798c.png)
  
3. <span data-ttu-id="76ed9-177">Na página **gerenciar domínios** , na área **meus domínios** , selecione o domínio que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="76ed9-177">On the **Manage Domains** page, in the **My Domains** area, select the domain you want to update.</span></span> 
    
    ![Hostgator-BP-Redelegate-1-2](../../media/2c2f8530-26a1-4e62-bb04-b3874bc1cf36.png)
  
4. <span data-ttu-id="76ed9-179">Na página **visão geral do domínio** , na área **servidores de nomes** , selecione **alterar**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-179">On the **Domain Overview** page, in the **Name Servers** area, select **Change**.</span></span>
    
    ![Imagem do botão Definir cor transparente](../../media/c8979d8a-ee96-4064-a8df-c5b01054cb16.png)
  
5. <span data-ttu-id="76ed9-181">Na página **servidores de nomes** do seu domínio, na lista suspensa **selecionar conta de hospedagem** , escolha a conta de **hospedagem** associada ao seu domínio.</span><span class="sxs-lookup"><span data-stu-id="76ed9-181">On the **Name Servers** page for your domain, in the **Select Hosting Account** drop-down list, choose the **hosting account** that is associated with your domain.</span></span> 
    
    ![Painéis do Power BI](../../media/4cf61060-1e8a-4758-9892-32059ffc90c2.png)
  
6. <span data-ttu-id="76ed9-183">Selecione **definir manualmente os meus servidores de nomes**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-183">Select **Manually set my name servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-5](../../media/5b73ae32-f26e-48aa-b5ad-6da20f1c491a.png)
  
7.   <span data-ttu-id="76ed9-185">**Cuidado**: Siga estas etapas somente se você tiver nameservers existentes além dos quatro nameservers corretos.</span><span class="sxs-lookup"><span data-stu-id="76ed9-185">**CAUTION**: Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="76ed9-186">(Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="76ed9-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
        <span data-ttu-id="76ed9-187">Ainda na página **Servidores de Nomes** do domínio, na lista de servidores de nomes, exclua cada nameserver na lista selecionando-o e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="76ed9-187">Still on the **Name Servers** page for your domain, in the list of nameservers, delete each nameserver in the list by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
   ![O365_Adddomain_wizard_1_7a](../../media/fa9820e7-28bb-4792-b16c-51e54d83feb1.png)
  
8. <span data-ttu-id="76ed9-189">Ainda na lista de servidores de nomes, digite ou copie e cole os dois primeiros valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="76ed9-189">Still in the list of nameservers, type or copy and paste the first two values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="76ed9-190">**Servidor de nomes 1:**</span><span class="sxs-lookup"><span data-stu-id="76ed9-190">**Name Server 1:**</span></span> <br/> |<span data-ttu-id="76ed9-191">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76ed9-191">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="76ed9-192">**Servidor de nomes 2:**</span><span class="sxs-lookup"><span data-stu-id="76ed9-192">**Name Server 2:**</span></span> <br/> |<span data-ttu-id="76ed9-193">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76ed9-193">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="76ed9-194">**Servidor de Nomes 3:**</span><span class="sxs-lookup"><span data-stu-id="76ed9-194">**Name Server 3:**</span></span> <br/> |<span data-ttu-id="76ed9-195">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76ed9-195">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="76ed9-196">**Servidor de Nomes 4:**</span><span class="sxs-lookup"><span data-stu-id="76ed9-196">**Name Server 4:**</span></span> <br/> |<span data-ttu-id="76ed9-197">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="76ed9-197">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Hostgator-BP-redelegar-1-7-1](../../media/a8c10aa7-30b0-4bc8-9596-20256d396274.png)
  
9. <span data-ttu-id="76ed9-199">Adicione outros valores de nameserver.</span><span class="sxs-lookup"><span data-stu-id="76ed9-199">Add the other nameserver values.</span></span>
    
    <span data-ttu-id="76ed9-200">Selecione **(+)** adicionar e, em seguida, digite ou copie e cole o valor da próxima linha da tabela na caixa do registro.</span><span class="sxs-lookup"><span data-stu-id="76ed9-200">Select **(+)** add, and then type or copy and paste the value from the next row of the table into the box for the record.</span></span> 
    
    <span data-ttu-id="76ed9-201">Repita esse processo até ter criado todos os quatro registros nameserver.</span><span class="sxs-lookup"><span data-stu-id="76ed9-201">Repeat this process until you have created all four nameserver records.</span></span>
    
    ![Hostgator-BP-Redelegate-1-7-2](../../media/92159a39-e498-4220-9b0d-ae2e718c7fb9.png)
  
10. <span data-ttu-id="76ed9-203">Selecione **salvar servidores de nomes**.</span><span class="sxs-lookup"><span data-stu-id="76ed9-203">Select **Save Name Servers**.</span></span>
    
    ![Hostgator-BP-Redelegate-1-8](../../media/bd6b0dfa-5d39-4805-970d-7ab153cff117.png)
  
> [!NOTE]
> <span data-ttu-id="76ed9-205">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="76ed9-205">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="76ed9-206">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="76ed9-206">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
