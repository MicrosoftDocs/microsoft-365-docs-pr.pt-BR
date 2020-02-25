---
title: Alterar os nameservers para configurar o Office 365 com a MyDomain
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Saiba como você pode configurar o Office 365 para gerenciar os registros DNS do seu domínio personalizado em mydomain.
ms.openlocfilehash: 05681fb48cc4c06aa44421029739a71ef6e59871
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237438"
---
# <a name="change-nameservers-to-set-up-office-365-with-mydomain"></a><span data-ttu-id="01bf3-103">Alterar os nameservers para configurar o Office 365 com a MyDomain</span><span class="sxs-lookup"><span data-stu-id="01bf3-103">Change nameservers to set up Office 365 with MyDomain</span></span>

 <span data-ttu-id="01bf3-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="01bf3-p101">Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você. Se preferir, [gerencie todos os registros DNS do Office 365 na MyDomain](create-dns-records-at-mydomain.md).</span><span class="sxs-lookup"><span data-stu-id="01bf3-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="01bf3-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="01bf3-107">Add a TXT record for verification</span></span>

<span data-ttu-id="01bf3-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="01bf3-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="01bf3-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="01bf3-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="01bf3-p104">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="01bf3-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="01bf3-114">Na seção **meus favoritos** , selecione **domínio central**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="01bf3-115">Em **domínio**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="01bf3-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="01bf3-116">Na linha **visão geral** , selecione **DNS**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="01bf3-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="01bf3-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span><span class="sxs-lookup"><span data-stu-id="01bf3-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="01bf3-119">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="01bf3-119">**Content**</span></span> <br/> |
|<span data-ttu-id="01bf3-120">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="01bf3-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="01bf3-121">**Observação**: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="01bf3-121">**Note**: This is an example.</span></span> <span data-ttu-id="01bf3-122">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="01bf3-122">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="01bf3-123">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="01bf3-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="01bf3-124">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="01bf3-125">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="01bf3-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="01bf3-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="01bf3-126">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="01bf3-127">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="01bf3-127">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="01bf3-128">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="01bf3-128">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="01bf3-129">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="01bf3-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="01bf3-130">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="01bf3-131">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="01bf3-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="01bf3-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="01bf3-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="01bf3-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="01bf3-134">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="01bf3-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="01bf3-135">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="01bf3-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="01bf3-p107">Para concluir a configuração do domínio com o Office 365, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do Office 365. Isso configura o Office 365 para atualizar os registros DNS do seu domínio. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="01bf3-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="01bf3-139">Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="01bf3-139">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="01bf3-140">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="01bf3-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="01bf3-141">com) começará a chegar ao Office 365 depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="01bf3-141">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="01bf3-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="01bf3-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="01bf3-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="01bf3-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="01bf3-144">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel).</span><span class="sxs-lookup"><span data-stu-id="01bf3-144">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel).</span></span> <span data-ttu-id="01bf3-145">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="01bf3-145">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="01bf3-146">Na seção **meus favoritos** , selecione **domínio central**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="01bf3-147">Em **domínio**, selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="01bf3-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="01bf3-148">Na linha **visão geral** , selecione **nameservers**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Mydomain-BP-redelegar-1-1](../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="01bf3-150">Na seção **Update Name Servers**, selecione **Use different name servers**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Mydomain-BP-redelegar-1-2-1](../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="01bf3-152">Dependendo se já existem ou não nameservers listados na página exibida agora, continue com um dos dois procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="01bf3-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="01bf3-153">Se os nameservers corretos já ESTIVEREM listados</span><span class="sxs-lookup"><span data-stu-id="01bf3-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="01bf3-154">Se os nameservers corretos já estiverem listados, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="01bf3-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Mydomain-BP-redelegar-1-2-2](../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="01bf3-156">Se os nameservers corretos NÃO ESTIVEREM listados</span><span class="sxs-lookup"><span data-stu-id="01bf3-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="01bf3-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="01bf3-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="01bf3-158">(Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="01bf3-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="01bf3-159">Exclua os nameservers existentes selecionado cada entrada no campo **Nameserver:** e, em seguida, pressione a tecla **Delete** no seu teclado.</span><span class="sxs-lookup"><span data-stu-id="01bf3-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Mydomain-BP-redelegar-1-3-1](../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="01bf3-161">Selecione **adicionar mais** duas vezes para adicionar duas novas linhas de nameserver.</span><span class="sxs-lookup"><span data-stu-id="01bf3-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Mydomain-BP-redelegar-1-3-2](../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="01bf3-163">Nas caixas dos registros, digite ou copie e cole os valores de nameserver da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="01bf3-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="01bf3-164">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="01bf3-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="01bf3-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="01bf3-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="01bf3-166">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="01bf3-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="01bf3-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="01bf3-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="01bf3-168">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="01bf3-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="01bf3-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="01bf3-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="01bf3-170">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="01bf3-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="01bf3-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="01bf3-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Mydomain-BP-redelegar-1-4](../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="01bf3-173">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="01bf3-173">Select **Save**.</span></span>
    
    ![Mydomain-BP-redelegar-1-5](../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="01bf3-p112">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="01bf3-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
