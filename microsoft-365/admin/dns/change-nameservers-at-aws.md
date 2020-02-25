---
title: Alterar os nameservers para configurar o Office 365 com a AWS (Amazon Web Services)
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
ms.assetid: 0ddbe33c-81ea-4c02-8db9-e71d3810c0ec
description: 'Saiba como você pode configurar o Office 365 para gerenciar seus registros DNS no Amazon Web Services (AWS). '
ms.openlocfilehash: 08deba83738ba0e530e719cd6fd57bee423df5e0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237485"
---
# <a name="change-nameservers-to-set-up-office-365-with-amazon-web-services-aws"></a><span data-ttu-id="276cb-103">Alterar os nameservers para configurar o Office 365 com a AWS (Amazon Web Services)</span><span class="sxs-lookup"><span data-stu-id="276cb-103">Change nameservers to set up Office 365 with Amazon Web Services (AWS)</span></span>

 <span data-ttu-id="276cb-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="276cb-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="276cb-p101">Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você. Se preferir, [gerencie todos os registros DNS do Office 365 no AWS](create-dns-records-at-aws.md).</span><span class="sxs-lookup"><span data-stu-id="276cb-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at AWS](create-dns-records-at-aws.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="276cb-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="276cb-107">Add a TXT record for verification</span></span>

<span data-ttu-id="276cb-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="276cb-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="276cb-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="276cb-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="276cb-p104">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="276cb-p104">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="276cb-114">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="276cb-114">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="276cb-115">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="276cb-115">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="276cb-116">Selecione **criar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="276cb-116">Select **Create Record Set**.</span></span>
    
5. <span data-ttu-id="276cb-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="276cb-117">In the **Create Record Set** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="276cb-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span><span class="sxs-lookup"><span data-stu-id="276cb-118">(Choose the **Type** and **Routing Policy** values from the drop-down lists.)</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="276cb-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span><span class="sxs-lookup"><span data-stu-id="276cb-p105">The quotation marks required by the onscreen instructions are supplied automatically. You don't need to type them manually.</span></span> 
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="276cb-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="276cb-121">**Name**</span></span> <br/> |<span data-ttu-id="276cb-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="276cb-122">**Type**</span></span> <br/> |<span data-ttu-id="276cb-123">**Alias**</span><span class="sxs-lookup"><span data-stu-id="276cb-123">**Alias**</span></span> <br/> |<span data-ttu-id="276cb-124">**TTL (Segundos)**</span><span class="sxs-lookup"><span data-stu-id="276cb-124">**TTL (Seconds)**</span></span> <br/> |<span data-ttu-id="276cb-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="276cb-125">**Value**</span></span> <br/> |<span data-ttu-id="276cb-126">**Política de Roteamento**</span><span class="sxs-lookup"><span data-stu-id="276cb-126">**Routing Policy**</span></span> <br/> |
|<span data-ttu-id="276cb-127">(Deixe este campo vazio)</span><span class="sxs-lookup"><span data-stu-id="276cb-127">(Leave this field empty)</span></span>  <br/> |<span data-ttu-id="276cb-128">TXT - Text</span><span class="sxs-lookup"><span data-stu-id="276cb-128">TXT - Text</span></span>  <br/> |<span data-ttu-id="276cb-129">Não</span><span class="sxs-lookup"><span data-stu-id="276cb-129">No</span></span>  <br/> |<span data-ttu-id="276cb-130">300</span><span class="sxs-lookup"><span data-stu-id="276cb-130">300</span></span>  <br/> |<span data-ttu-id="276cb-131">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="276cb-131">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="276cb-132">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="276cb-132">**Note:** This is an example.</span></span> <span data-ttu-id="276cb-133">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="276cb-133">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="276cb-134">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="276cb-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)  <br/>  |<span data-ttu-id="276cb-135">Simples</span><span class="sxs-lookup"><span data-stu-id="276cb-135">Simple</span></span> <br/> |
   
6. <span data-ttu-id="276cb-136">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="276cb-136">Select **Create**.</span></span>
    
7. <span data-ttu-id="276cb-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="276cb-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="276cb-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="276cb-138">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="276cb-139">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="276cb-139">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="276cb-140">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="276cb-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="276cb-141">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="276cb-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="276cb-142">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="276cb-142">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="276cb-143">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="276cb-143">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="276cb-144">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="276cb-144">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="276cb-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="276cb-145">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="276cb-146">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="276cb-146">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="276cb-147">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="276cb-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="276cb-p108">Para concluir a configuração do domínio com o Office 365, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do Office 365. Isso configura o Office 365 para atualizar os registros DNS do seu domínio. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="276cb-p108">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="276cb-p109">Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como paulo@ *seu_domínio*  .com) vão começar a chegar no Office 365, depois que essa alteração for feita.</span><span class="sxs-lookup"><span data-stu-id="276cb-p109">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="276cb-153">O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados.</span><span class="sxs-lookup"><span data-stu-id="276cb-153">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="276cb-154">> quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="276cb-154">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="276cb-155">Para começar, vá para sua página de domínios no AWS usando [este link](https://console.aws.amazon.com/route53/home).</span><span class="sxs-lookup"><span data-stu-id="276cb-155">To get started, go to your domains page at AWS by using [this link](https://console.aws.amazon.com/route53/home).</span></span> <span data-ttu-id="276cb-156">Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="276cb-156">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="276cb-157">Na página **recursos** , selecione **zonas hospedadas**.</span><span class="sxs-lookup"><span data-stu-id="276cb-157">On the **Resources** page, select **Hosted Zones**.</span></span>
    
3. <span data-ttu-id="276cb-158">Na página **zonas hospedadas** , na coluna **nome do domínio** , selecione o nome do domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="276cb-158">On the **Hosted Zones** page, in the **Domain Name** column, select the name of the domain that you want to edit.</span></span> 
    
4. <span data-ttu-id="276cb-159">Selecione o conjunto de registros **Nameserver**.</span><span class="sxs-lookup"><span data-stu-id="276cb-159">Select the **Nameserver** record set.</span></span> 
    
    ![Select the recordset](../media/24e618e4-0a16-43a2-9886-f4f5dac79374.png)
  
5. <span data-ttu-id="276cb-161">No conjunto de registros **NS - Name server** na caixa **Valor**, exclua todos os nameservers selecionando todos eles e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="276cb-161">In the **NS - Name server** record set in the **Value** box, delete all of the nameservers by selecting them all and then pressing the **Delete** key on your keyboard.</span></span> 
    
    > [!CAUTION]
    > <span data-ttu-id="276cb-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="276cb-162">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="276cb-163">(Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="276cb-163">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Select and delete all of the nameservers in the Value box](../media/ecf1e897-fa7d-4abc-b00b-bf55b8ed2139.png)
  
6. <span data-ttu-id="276cb-165">Na área **TTL (segundos):** , selecione **1h** (1 hora).</span><span class="sxs-lookup"><span data-stu-id="276cb-165">In the **TTL (Seconds):** area, select **1h** (1 Hour).</span></span> 
    
    ![Selecionar 1H por uma hora](../media/c70070e1-4bde-41a7-b271-9d22c475edf6.png)
  
7. <span data-ttu-id="276cb-167">Ainda no conjunto de registros **NS - Nameserver**, na caixa **Valor**, digite ou copie e cole o valor **Primeira linha** da tabela a seguir, pressione a tecla **Enter** no teclado e digite ou copie e cole o valor da próxima **linha**.</span><span class="sxs-lookup"><span data-stu-id="276cb-167">Still in the **NS - Name server** record set, in the **Value** box, type or copy and paste the **First line** value from the following table, then press the **Enter** key on your keyboard and type or copy and paste the next **line** value.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="276cb-168">Cada valor de nameserver  *tem que*  estar em sua própria linha separada dentro da caixa **Valor**, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="276cb-168">Each nameserver value  *must*  be on its own separate line within the **Value** box, as shown in the following illustration.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="276cb-169">**Primeira linha**</span><span class="sxs-lookup"><span data-stu-id="276cb-169">**First line**</span></span> <br/> |<span data-ttu-id="276cb-170">ns1.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="276cb-170">ns1.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="276cb-171">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="276cb-171">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="276cb-172">**Segunda linha**</span><span class="sxs-lookup"><span data-stu-id="276cb-172">**Second line**</span></span> <br/> |<span data-ttu-id="276cb-173">ns2.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="276cb-173">ns2.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="276cb-174">**This value MUST end with a period (.)**</span><span class="sxs-lookup"><span data-stu-id="276cb-174">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="276cb-175">**Terceira linha**</span><span class="sxs-lookup"><span data-stu-id="276cb-175">**Third line**</span></span> <br/> |<span data-ttu-id="276cb-176">ns3.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="276cb-176">ns3.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="276cb-177">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="276cb-177">**This value MUST end with a period (.)**</span></span> <br/> |
|<span data-ttu-id="276cb-178">**Quarta linha**</span><span class="sxs-lookup"><span data-stu-id="276cb-178">**Fourth line**</span></span> <br/> |<span data-ttu-id="276cb-179">ns4.bdm.microsoftonline.com.</span><span class="sxs-lookup"><span data-stu-id="276cb-179">ns4.bdm.microsoftonline.com.</span></span>  <br/> <span data-ttu-id="276cb-180">**Este valor deve OBRIGATORIAMENTE terminar com um ponto (.)**</span><span class="sxs-lookup"><span data-stu-id="276cb-180">**This value MUST end with a period (.)**</span></span> <br/> |
   
   ![Digite ou cole o valor da primeira linha na caixa de valor](../media/b63f41e0-51ef-4ab2-a4b8-ee7380e5ab35.png)
  
8. <span data-ttu-id="276cb-182">Selecione **Salvar conjunto de registros**.</span><span class="sxs-lookup"><span data-stu-id="276cb-182">Select **Save Record Set**.</span></span>
    
    ![Selecionar Salvar conjunto de registros](../media/ab3c0558-bb7c-41e4-871e-ea82f1553476.png)
  
> [!NOTE]
> <span data-ttu-id="276cb-p113">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="276cb-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
