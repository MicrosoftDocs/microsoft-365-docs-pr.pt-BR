---
title: Alterar os nameservers para configurar a Microsoft com serviços Web da Amazon (AWS)
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Saiba como você pode configurar a Microsoft para gerenciar seus registros DNS no Amazon Web Services (AWS). '
ms.openlocfilehash: 6efe06400652783ffbc6732b5c6327067c5c484c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400672"
---
# <a name="change-nameservers-to-set-up-microsoft-with-amazon-web-services-aws"></a><span data-ttu-id="790d7-103">Alterar os nameservers para configurar a Microsoft com serviços Web da Amazon (AWS)</span><span class="sxs-lookup"><span data-stu-id="790d7-103">Change nameservers to set up Microsoft with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="790d7-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="790d7-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="790d7-105">Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="790d7-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="790d7-106">Se preferir, [gerencie todos os registros DNS da Microsoft em AWS](create-dns-records-at-aws.md).</span><span class="sxs-lookup"><span data-stu-id="790d7-106">(If you prefer, you can [manage all your Microsoft DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="790d7-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="790d7-107">Add a TXT record for verification</span></span>

<span data-ttu-id="790d7-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="790d7-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="790d7-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="790d7-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="790d7-p104">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="790d7-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="790d7-114">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="790d7-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="790d7-115">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="790d7-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="790d7-116">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="790d7-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="790d7-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="790d7-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="790d7-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="790d7-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="790d7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="790d7-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="790d7-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="790d7-121">**Name**</span></span> <br/> |<span data-ttu-id="790d7-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="790d7-122">**Type**</span></span> <br/> |<span data-ttu-id="790d7-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="790d7-123">**Alias**</span></span> <br/> |<span data-ttu-id="790d7-124">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="790d7-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="790d7-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="790d7-125">**Value**</span></span> <br/> |<span data-ttu-id="790d7-126">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="790d7-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="790d7-127">(Deixe este campo vazio)</span><span class="sxs-lookup"><span data-stu-id="790d7-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="790d7-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="790d7-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="790d7-129">Não</span><span class="sxs-lookup"><span data-stu-id="790d7-129">No</span></span>  <br/> |<span data-ttu-id="790d7-130">300</span><span class="sxs-lookup"><span data-stu-id="790d7-130">300</span></span>  <br/> |<span data-ttu-id="790d7-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="790d7-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="790d7-132">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="790d7-132">**Note:** This is an example.</span></span> <span data-ttu-id="790d7-133">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="790d7-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="790d7-134">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="790d7-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="790d7-135">Simples</span><span class="sxs-lookup"><span data-stu-id="790d7-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="790d7-136">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="790d7-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="790d7-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="790d7-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="790d7-138">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="790d7-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="790d7-139">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="790d7-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="790d7-140">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="790d7-140">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="790d7-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="790d7-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="790d7-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="790d7-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="790d7-143">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="790d7-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="790d7-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="790d7-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="790d7-145">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="790d7-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="790d7-146">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="790d7-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="790d7-147">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="790d7-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="790d7-148">Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="790d7-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="790d7-149">Isso configura a Microsoft para atualizar os registros DNS do domínio para você.</span><span class="sxs-lookup"><span data-stu-id="790d7-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="790d7-150">Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="790d7-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="790d7-151">Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="790d7-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="790d7-152">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain* . com) começarão a ser iniciados pela Microsoft depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="790d7-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="790d7-153">O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados.</span><span class="sxs-lookup"><span data-stu-id="790d7-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="790d7-154">> quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="790d7-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="790d7-155">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="790d7-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="790d7-156">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="790d7-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="790d7-157">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="790d7-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="790d7-158">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="790d7-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="790d7-159">Selecione o conjunto de registros **Nameserver**.</span><span class="sxs-lookup"><span data-stu-id="790d7-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="790d7-161">No conjunto de registros **NS - Name server** na caixa **Valor**, exclua todos os nameservers selecionando todos eles e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="790d7-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="790d7-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="790d7-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="790d7-163">(Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="790d7-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="790d7-165">Na área **TTL (segundos):** , selecione **1h** (1 hora).</span><span class="sxs-lookup"><span data-stu-id="790d7-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Selecionar 1H por uma hora](../../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="790d7-167">Ainda no conjunto de registros **NS - Nameserver**, na caixa **Valor**, digite ou copie e cole o valor **Primeira linha** da tabela a seguir, pressione a tecla **Enter** no teclado e digite ou copie e cole o valor da próxima **linha**.</span><span class="sxs-lookup"><span data-stu-id="790d7-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="790d7-168">Cada valor de nameserver  *tem que*  estar em sua própria linha separada dentro da caixa **Valor**, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="790d7-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="790d7-169">**Primeira linha**</span><span class="sxs-lookup"><span data-stu-id="790d7-169">**First line**</span></span> <br/> |<span data-ttu-id="790d7-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="790d7-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="790d7-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="790d7-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="790d7-172">**Segunda linha**</span><span class="sxs-lookup"><span data-stu-id="790d7-172">**Second line**</span></span> <br/> |<span data-ttu-id="790d7-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="790d7-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="790d7-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="790d7-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="790d7-175">**Terceira linha**</span><span class="sxs-lookup"><span data-stu-id="790d7-175">**Third line**</span></span> <br/> |<span data-ttu-id="790d7-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="790d7-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="790d7-177">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="790d7-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="790d7-178">**Quarta linha**</span><span class="sxs-lookup"><span data-stu-id="790d7-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="790d7-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="790d7-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="790d7-180">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="790d7-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Digite ou cole o valor da primeira linha na caixa de valor](../../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="790d7-182">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="790d7-182">Select **Save Record Set**.</span></span>
    
    ![Selecionar Salvar conjunto de registros](../../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="790d7-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="790d7-184">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="790d7-185">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="790d7-185">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
