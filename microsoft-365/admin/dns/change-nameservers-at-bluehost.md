---
title: Alterar os nameservers para configurar o Microsoft com o Bluehost
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Saiba como você pode configurar a Microsoft para gerenciar seus registros DNS em Bluehost. '
ms.openlocfilehash: c15ba11e0df57deaef61309f5bc6d1b2a60645b8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646458"
---
# <a name="change-nameservers-to-set-up-microsoft-with-bluehost"></a><span data-ttu-id="7c6b7-103">Alterar os nameservers para configurar o Microsoft com o Bluehost</span><span class="sxs-lookup"><span data-stu-id="7c6b7-103">Change nameservers to set up Microsoft with Bluehost</span></span>

 <span data-ttu-id="7c6b7-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="7c6b7-105">Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="7c6b7-106">Se preferir, [gerencie todos os registros DNS em Bluehost](create-dns-records-at-bluehost.md).</span><span class="sxs-lookup"><span data-stu-id="7c6b7-106">(If you prefer, you can [manage all your DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="7c6b7-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="7c6b7-107">Add a TXT record for verification</span></span>

<span data-ttu-id="7c6b7-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c6b7-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="7c6b7-112">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="7c6b7-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7c6b7-113">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7c6b7-114">Na página **Domínios**, na área **domínio**, localize a linha do domínio que está sendo alterado e marque a caixa de seleção desse domínio.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="7c6b7-115">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="7c6b7-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="7c6b7-116">Na área **domain_name** , na linha **Editor de zona DNS** , selecione **gerenciar registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="7c6b7-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="7c6b7-118">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="7c6b7-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7c6b7-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-119">**Host Record**</span></span> <br/> |<span data-ttu-id="7c6b7-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-120">**TTL**</span></span> <br/> |<span data-ttu-id="7c6b7-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-121">**Type**</span></span> <br/> |<span data-ttu-id="7c6b7-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="7c6b7-123">14400</span><span class="sxs-lookup"><span data-stu-id="7c6b7-123">14400</span></span>  <br/> |<span data-ttu-id="7c6b7-124">TXT</span><span class="sxs-lookup"><span data-stu-id="7c6b7-124">TXT</span></span>  <br/> |<span data-ttu-id="7c6b7-125">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="7c6b7-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="7c6b7-126">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-126">**Note:** This is an example.</span></span> <span data-ttu-id="7c6b7-127">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-127">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="7c6b7-128">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="7c6b7-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="7c6b7-129">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="7c6b7-130">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="7c6b7-131">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-131">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="7c6b7-132">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-132">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="7c6b7-133">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-133">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="7c6b7-134">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="7c6b7-135">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="7c6b7-136">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7c6b7-137">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-137">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="7c6b7-138">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-138">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="7c6b7-139">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="7c6b7-139">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="7c6b7-140">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="7c6b7-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="7c6b7-141">Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primário e secundário.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-141">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the  primary and secondary name servers.</span></span> <span data-ttu-id="7c6b7-142">Isso configura a Microsoft para atualizar os registros DNS do domínio para você.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-142">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="7c6b7-143">Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-143">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7c6b7-144">Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-144">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="7c6b7-145">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain*  . com) começarão a ser iniciados pela Microsoft depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-145">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="7c6b7-146">O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="7c6b7-147">> quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="7c6b7-148">Para começar, vá para sua página de domínios no Bluehost usando [este link](https://my.bluehost.com/cgi/dm).</span><span class="sxs-lookup"><span data-stu-id="7c6b7-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="7c6b7-149">Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="7c6b7-150">Na página **domínios** , na área **domain_name** , marque a caixa de seleção do seu domínio e, em seguida, selecione **servidores de nomes**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="7c6b7-152">Na área **domain_name** , selecione **usar nameservers personalizados**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Aprimoramentos nas trajetórias de animação](../../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="7c6b7-154">Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7c6b7-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="7c6b7-155">Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="7c6b7-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="7c6b7-156">Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="7c6b7-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="7c6b7-157">Se NÃO houver nameservers listados</span><span class="sxs-lookup"><span data-stu-id="7c6b7-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="7c6b7-158">Na seção **Usar Nameservers Personalizados**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7c6b7-159">**Primeira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-159">**First empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7c6b7-161">**Segunda linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegar-1-3-1](../../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="7c6b7-164">Selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="7c6b7-166">Ainda na seção **Usar Servidores de Nomes Personalizados**, digite ou copie e cole os valores da primeira linha da tabela a seguir para a nova linha vazia.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7c6b7-167">**Terceira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7c6b7-169">**Quarta linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
  
4. <span data-ttu-id="7c6b7-171">Para adicionar o quarto registro de nameserver, selecione **Adicionar linha** novamente e crie um registro usando os valores da última linha da tabela acima.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="7c6b7-172">Selecione **salvar configurações de nameserver**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-172">Select **save nameserver settings**.</span></span>
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="7c6b7-174">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-174">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="7c6b7-175">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-175">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="7c6b7-176">Se HOUVER nameservers listados</span><span class="sxs-lookup"><span data-stu-id="7c6b7-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="7c6b7-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="7c6b7-178">(Ou seja, exclua somente os nameservers atuais que  *não*  sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="7c6b7-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="7c6b7-179">Se houver outros nameservers listados na área, exclua cada um deles selecionando-os e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="7c6b7-181">Ainda na seção **Usar Nameservers Personalizados**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7c6b7-182">**Primeira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-182">**First empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7c6b7-184">**Segunda linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegar-1-3](../../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="7c6b7-187">Selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="7c6b7-189">Ainda na seção **Usar Servidores de Nomes Personalizados**, digite ou copie e cole os valores da primeira linha da tabela a seguir para a nova linha vazia.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="7c6b7-190">**Terceira linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="7c6b7-192">**Quarta linha vazia**</span><span class="sxs-lookup"><span data-stu-id="7c6b7-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="7c6b7-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="7c6b7-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-redelegar-1-3-3](../../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="7c6b7-195">Para adicionar o quarto registro de nameserver, selecione **Adicionar linha** novamente e crie um registro usando os valores da última linha da tabela acima.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="7c6b7-196">Selecione **salvar configurações de nameserver**.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-196">Select **save nameserver settings**.</span></span>
    
    ![Teta](../../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="7c6b7-198">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-198">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="7c6b7-199">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="7c6b7-199">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
