---
title: Alterar os nameservers para configurar o Office 365 com a Bluehost
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Saiba como você pode configurar o Office 365 para gerenciar seus registros DNS em Bluehost. '
ms.openlocfilehash: 27d73071a08477b0adc372d8a88db2c805fecacf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236973"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a><span data-ttu-id="c6e65-103">Alterar os nameservers para configurar o Office 365 com a Bluehost</span><span class="sxs-lookup"><span data-stu-id="c6e65-103">Change nameservers to set up Office 365 with Bluehost</span></span>

 <span data-ttu-id="c6e65-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c6e65-p101">Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você. Se preferir, [gerencie todos os registros DNS do Office 365 na Bluehost](create-dns-records-at-bluehost.md).</span><span class="sxs-lookup"><span data-stu-id="c6e65-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="c6e65-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="c6e65-107">Add a TXT record for verification</span></span>

<span data-ttu-id="c6e65-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="c6e65-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6e65-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="c6e65-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="c6e65-112">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="c6e65-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="c6e65-113">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="c6e65-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c6e65-114">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="c6e65-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="c6e65-115">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="c6e65-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="c6e65-116">Na área **domain_name** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="c6e65-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c6e65-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="c6e65-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="c6e65-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c6e65-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="c6e65-119">**Host Record**</span></span> <br/> |<span data-ttu-id="c6e65-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="c6e65-120">**TTL**</span></span> <br/> |<span data-ttu-id="c6e65-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c6e65-121">**Type**</span></span> <br/> |<span data-ttu-id="c6e65-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="c6e65-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="c6e65-123">14400</span><span class="sxs-lookup"><span data-stu-id="c6e65-123">14400</span></span>  <br/> |<span data-ttu-id="c6e65-124">TXT</span><span class="sxs-lookup"><span data-stu-id="c6e65-124">TXT</span></span>  <br/> |<span data-ttu-id="c6e65-125">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c6e65-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="c6e65-126">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c6e65-126">**Note:** This is an example.</span></span> <span data-ttu-id="c6e65-127">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6e65-127">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="c6e65-128">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="c6e65-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="c6e65-129">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="c6e65-130">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="c6e65-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c6e65-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="c6e65-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c6e65-132">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="c6e65-132">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c6e65-133">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="c6e65-133">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="c6e65-134">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="c6e65-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c6e65-135">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c6e65-136">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6e65-137">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c6e65-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c6e65-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="c6e65-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c6e65-139">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c6e65-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="c6e65-140">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="c6e65-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="c6e65-p107">Para concluir a configuração do domínio com o Office 365, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do Office 365. Isso configura o Office 365 para atualizar os registros DNS do seu domínio. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="c6e65-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="c6e65-p108">Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como paulo@ *seu_domínio*  .com) vão começar a chegar no Office 365, depois que essa alteração for feita.</span><span class="sxs-lookup"><span data-stu-id="c6e65-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="c6e65-146">O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados.</span><span class="sxs-lookup"><span data-stu-id="c6e65-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="c6e65-147">> quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="c6e65-148">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="c6e65-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="c6e65-149">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="c6e65-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="c6e65-150">Na página **domínios** , na área **domain_name** , marque a caixa de seleção do seu domínio e, em seguida, selecione **servidores de nomes**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="c6e65-152">Na área **domain_name** , selecione **usar nameservers personalizados**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Aprimoramentos nas trajetórias de animação](../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="c6e65-154">Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:</span><span class="sxs-lookup"><span data-stu-id="c6e65-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="c6e65-155">Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="c6e65-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="c6e65-156">Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="c6e65-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="c6e65-157">Se NÃO houver nameservers listados</span><span class="sxs-lookup"><span data-stu-id="c6e65-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="c6e65-158">Na seção **Usar Nameservers Personalizados**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6e65-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="c6e65-159">**Primeira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-159">**First empty row**</span></span> <br/> |<span data-ttu-id="c6e65-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c6e65-161">**Segunda linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="c6e65-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegar-1-3-1](../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="c6e65-164">Selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="c6e65-166">Ainda na seção **Usar Servidores de Nomes Personalizados**, digite ou copie e cole os valores da primeira linha da tabela a seguir para a nova linha vazia.</span><span class="sxs-lookup"><span data-stu-id="c6e65-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="c6e65-167">**Terceira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="c6e65-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c6e65-169">**Quarta linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="c6e65-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="c6e65-171">Para adicionar o quarto registro de nameserver, selecione **Adicionar linha** novamente e crie um registro usando os valores da última linha da tabela acima.</span><span class="sxs-lookup"><span data-stu-id="c6e65-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="c6e65-172">Selecione **salvar configurações de nameserver**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-172">Select **save nameserver settings**.</span></span>
    
    ![Teta](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="c6e65-p111">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c6e65-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="c6e65-176">Se HOUVER nameservers listados</span><span class="sxs-lookup"><span data-stu-id="c6e65-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="c6e65-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="c6e65-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="c6e65-178">(Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="c6e65-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="c6e65-179">Se houver outros nameservers listados na área, exclua cada um deles selecionando-os e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="c6e65-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="c6e65-181">Ainda na seção **Usar Nameservers Personalizados**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c6e65-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="c6e65-182">**Primeira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-182">**First empty row**</span></span> <br/> |<span data-ttu-id="c6e65-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c6e65-184">**Segunda linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="c6e65-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegar-1-3](../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="c6e65-187">Selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="c6e65-189">Ainda na seção **Usar Servidores de Nomes Personalizados**, digite ou copie e cole os valores da primeira linha da tabela a seguir para a nova linha vazia.</span><span class="sxs-lookup"><span data-stu-id="c6e65-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="c6e65-190">**Terceira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="c6e65-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="c6e65-192">**Quarta linha vazia**</span><span class="sxs-lookup"><span data-stu-id="c6e65-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="c6e65-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="c6e65-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegar-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="c6e65-195">Para adicionar o quarto registro de nameserver, selecione **Adicionar linha** novamente e crie um registro usando os valores da última linha da tabela acima.</span><span class="sxs-lookup"><span data-stu-id="c6e65-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="c6e65-196">Selecione **salvar configurações de nameserver**.</span><span class="sxs-lookup"><span data-stu-id="c6e65-196">Select **save nameserver settings**.</span></span>
    
    ![Teta](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="c6e65-p113">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="c6e65-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
