---
title: Alterar os nameservers para configurar o Office 365 com o Google Domains
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Saiba como você pode configurar o Office 365 para gerenciar os registros DNS do seu domínio personalizado em domínios do Google.
ms.openlocfilehash: 771d38b9a3d08bef75c3ad1958f981539edb6c04
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237458"
---
# <a name="change-nameservers-to-set-up-office-365-with-google-domains"></a><span data-ttu-id="63861-103">Alterar os nameservers para configurar o Office 365 com o Google Domains</span><span class="sxs-lookup"><span data-stu-id="63861-103">Change nameservers to set up Office 365 with Google Domains</span></span>

 <span data-ttu-id="63861-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="63861-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="63861-p101">Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você. Se preferir, [gerencie todos os registros DNS do Office 365 em Google Domains](create-dns-records-at-google-domains.md).</span><span class="sxs-lookup"><span data-stu-id="63861-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="63861-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="63861-107">Add a TXT record for verification</span></span>

<span data-ttu-id="63861-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="63861-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="63861-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="63861-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="63861-112">Para começar, vá até a sua página de domínios no Google Domains por meio [deste link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="63861-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="63861-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="63861-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="63861-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="63861-114">To do so:</span></span>
    
1. <span data-ttu-id="63861-115">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="63861-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="63861-116">Insira suas credenciais de logon e selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="63861-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="63861-117">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="63861-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="63861-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="63861-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="63861-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="63861-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="63861-120">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="63861-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="63861-121">**Nome**</span><span class="sxs-lookup"><span data-stu-id="63861-121">**Name**</span></span> <br/> |<span data-ttu-id="63861-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="63861-122">**Type**</span></span> <br/> |<span data-ttu-id="63861-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="63861-123">**TTL**</span></span> <br/> |<span data-ttu-id="63861-124">**Dados**</span><span class="sxs-lookup"><span data-stu-id="63861-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="63861-125">TXT</span><span class="sxs-lookup"><span data-stu-id="63861-125">TXT</span></span>  <br/> |<span data-ttu-id="63861-126">1H</span><span class="sxs-lookup"><span data-stu-id="63861-126">1H</span></span>  <br/> |<span data-ttu-id="63861-127">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="63861-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="63861-128">**Observação:** Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="63861-128">**Note:** This is an example.</span></span> <span data-ttu-id="63861-129">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="63861-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="63861-130">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="63861-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="63861-131">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="63861-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="63861-132">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="63861-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="63861-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="63861-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="63861-134">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="63861-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="63861-135">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="63861-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="63861-136">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="63861-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="63861-137">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="63861-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="63861-138">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="63861-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="63861-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="63861-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="63861-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="63861-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="63861-141">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="63861-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="63861-142">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="63861-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="63861-p107">Para concluir a configuração do domínio com o Office 365, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do Office 365. Isso configura o Office 365 para atualizar os registros DNS do seu domínio. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="63861-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="63861-146">Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="63861-146">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="63861-147">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="63861-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="63861-148">com) começará a chegar ao Office 365 depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="63861-148">com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="63861-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="63861-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="63861-150">> quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro:</span><span class="sxs-lookup"><span data-stu-id="63861-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="63861-p110">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="63861-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="63861-154">Selecione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="63861-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="63861-155">Digite suas credenciais de logon e, em seguida, selecione **entrar**novamente.</span><span class="sxs-lookup"><span data-stu-id="63861-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="63861-156">Na página **domínios** , na seção **domínio** , selecione **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="63861-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="63861-157">Na página **Domínios**, na seção **Servidores de nomes**, selecione **Usar servidores de nomes personalizados**.</span><span class="sxs-lookup"><span data-stu-id="63861-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="63861-159">Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:</span><span class="sxs-lookup"><span data-stu-id="63861-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="63861-160">Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="63861-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="63861-161">Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="63861-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="63861-162">Se NÃO houver nameservers listados</span><span class="sxs-lookup"><span data-stu-id="63861-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="63861-163">Adicione o primeiro nameserver.</span><span class="sxs-lookup"><span data-stu-id="63861-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="63861-164">Na seção **Servidores de nomes**, na caixa **SERVIDOR DE NOMES**, digite ou copie e cole o primeiro valor da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="63861-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="63861-165">**Primeiro servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="63861-165">**First name server**</span></span> <br/> |<span data-ttu-id="63861-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="63861-167">**Segundo servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="63861-167">**Second name server**</span></span> <br/> |<span data-ttu-id="63861-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="63861-169">**Terceiro servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="63861-169">**Third name server**</span></span> <br/> |<span data-ttu-id="63861-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="63861-171">**Quarto servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="63861-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="63861-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegar-1-2](../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="63861-174">Selecione o controle **+ (Adicionar)** para criar uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="63861-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="63861-176">Adicione os outros três registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="63861-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="63861-177">Na seção **usar servidores de nomes personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione o controle **+ (Adicionar)** para adicionar outra linha.</span><span class="sxs-lookup"><span data-stu-id="63861-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="63861-178">Repita esse processo até ter criado todos os quatro registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="63861-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="63861-179">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="63861-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="63861-p111">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="63861-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="63861-183">Se HOUVER nameservers listados</span><span class="sxs-lookup"><span data-stu-id="63861-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="63861-184">Se houver outros nameservers listados, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="63861-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="63861-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="63861-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="63861-186">(Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="63861-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="63861-188">Exclua cada um selecionando-o e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="63861-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="63861-190">Ainda na seção **Servidores de nomes**, nas linhas **SERVIDOR DE NOMES**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="63861-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="63861-191">**Primeiro servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="63861-191">**First name server**</span></span> <br/> |<span data-ttu-id="63861-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="63861-193">**Segundo servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="63861-193">**Second name server**</span></span> <br/> |<span data-ttu-id="63861-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="63861-195">**Terceiro servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="63861-195">**Third name server**</span></span> <br/> |<span data-ttu-id="63861-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="63861-197">**Quarto servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="63861-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="63861-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="63861-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegar-1-7](../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="63861-200">Selecione o controle **+ (Adicionar)** para criar uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="63861-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="63861-202">Adicione os outros dois registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="63861-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="63861-203">Na seção **usar servidores de nomes personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione o controle **+ (Adicionar)** para adicionar outra linha.</span><span class="sxs-lookup"><span data-stu-id="63861-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="63861-204">Repita esse processo até ter criado todos os quatro registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="63861-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="63861-205">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="63861-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="63861-p113">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="63861-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
