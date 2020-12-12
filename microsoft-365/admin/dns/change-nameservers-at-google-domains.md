---
title: Alterar os nameservers para configurar a Microsoft com domínios do Google
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
ms.assetid: 68a08e94-26c2-4df2-9216-026b8ec907ca
description: Saiba como você pode configurar a Microsoft para gerenciar os registros DNS do seu domínio personalizado em domínios do Google.
ms.openlocfilehash: e475e222b6f1c9717008a49b172b0ecac5ec6fc7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658435"
---
# <a name="change-nameservers-to-set-up-microsoft-with-google-domains"></a><span data-ttu-id="82c0b-103">Alterar os nameservers para configurar a Microsoft com domínios do Google</span><span class="sxs-lookup"><span data-stu-id="82c0b-103">Change nameservers to set up Microsoft with Google Domains</span></span>

 <span data-ttu-id="82c0b-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="82c0b-105">Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="82c0b-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="82c0b-106">Se preferir, [gerencie todos os registros DNS no Google Domains](create-dns-records-at-google-domains.md).</span><span class="sxs-lookup"><span data-stu-id="82c0b-106">(If you prefer, you can [manage all your DNS records at Google Domains](create-dns-records-at-google-domains.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="82c0b-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="82c0b-107">Add a TXT record for verification</span></span>

<span data-ttu-id="82c0b-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="82c0b-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="82c0b-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="82c0b-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="82c0b-112">Para começar, vá até a sua página de domínios no Google Domains por meio [deste link](https://domains.google.com/registrar).</span><span class="sxs-lookup"><span data-stu-id="82c0b-112">To get started, go to your domains page at Google Domains via [this link](https://domains.google.com/registrar).</span></span> <span data-ttu-id="82c0b-113">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="82c0b-113">You'll be prompted to sign in.</span></span> <span data-ttu-id="82c0b-114">To do so:</span><span class="sxs-lookup"><span data-stu-id="82c0b-114">To do so:</span></span>
    
1. <span data-ttu-id="82c0b-115">Selecione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-115">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="82c0b-116">Insira suas credenciais de logon e selecione **entrar** novamente.</span><span class="sxs-lookup"><span data-stu-id="82c0b-116">Enter your login credentials and again select **Sign In**.</span></span>
    
2. <span data-ttu-id="82c0b-117">Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="82c0b-117">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="82c0b-118">Na seção **Registros de recursos personalizados**, nas caixas do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="82c0b-118">In the **Custom resource records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="82c0b-119">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="82c0b-119">(You may have to scroll down.)</span></span>
    
    <span data-ttu-id="82c0b-120">(Selecione o valor **Tipo** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="82c0b-120">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="82c0b-121">**Name**</span><span class="sxs-lookup"><span data-stu-id="82c0b-121">**Name**</span></span> <br/> |<span data-ttu-id="82c0b-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="82c0b-122">**Type**</span></span> <br/> |<span data-ttu-id="82c0b-123">**TTL**</span><span class="sxs-lookup"><span data-stu-id="82c0b-123">**TTL**</span></span> <br/> |<span data-ttu-id="82c0b-124">**Dados**</span><span class="sxs-lookup"><span data-stu-id="82c0b-124">**Data**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="82c0b-125">TXT</span><span class="sxs-lookup"><span data-stu-id="82c0b-125">TXT</span></span>  <br/> |<span data-ttu-id="82c0b-126">1H</span><span class="sxs-lookup"><span data-stu-id="82c0b-126">1H</span></span>  <br/> |<span data-ttu-id="82c0b-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="82c0b-127">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="82c0b-128">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="82c0b-128">**Note:** This is an example.</span></span> <span data-ttu-id="82c0b-129">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="82c0b-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="82c0b-130">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="82c0b-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)       <br/>  |
   
4. <span data-ttu-id="82c0b-131">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-131">Select **Add**.</span></span>
    
5. <span data-ttu-id="82c0b-132">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="82c0b-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="82c0b-133">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="82c0b-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="82c0b-134">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="82c0b-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="82c0b-135">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="82c0b-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="82c0b-136">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="82c0b-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="82c0b-137">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="82c0b-138">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="82c0b-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="82c0b-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="82c0b-140">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="82c0b-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="82c0b-141">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="82c0b-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="82c0b-142">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="82c0b-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="82c0b-143">Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="82c0b-143">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="82c0b-144">Isso configura a Microsoft para atualizar os registros DNS do domínio para você.</span><span class="sxs-lookup"><span data-stu-id="82c0b-144">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="82c0b-145">Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="82c0b-145">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="82c0b-146">Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="82c0b-146">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="82c0b-147">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="82c0b-147">For example, all email sent to your domain (like rob@ *your_domain.*</span></span>  <span data-ttu-id="82c0b-148">com) começará à Microsoft depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="82c0b-148">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="82c0b-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="82c0b-149">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <span data-ttu-id="82c0b-150">> quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro:</span><span class="sxs-lookup"><span data-stu-id="82c0b-150">> When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span> 
  
1. <span data-ttu-id="82c0b-p110">Para iniciar, vá até a página do seu domínio no Google Domains usando [este link](https://domains.google.com/registrar). Você será solicitado a entrar. Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="82c0b-p110">To get started, go to your domains page at Google Domains by using [this link](https://domains.google.com/registrar). You'll be prompted to sign in. To do so:</span></span>
    
1. <span data-ttu-id="82c0b-154">Selecione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-154">Select **Sign In**.</span></span>
    
2. <span data-ttu-id="82c0b-155">Em seguida, insira suas credenciais de login e selecione novamente **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-155">Enter your login credentials, and then again select **Sign In**.</span></span>
    
2. <span data-ttu-id="82c0b-156">Na página **Domínios**, na seção **Domínio**, escolha **Configurar DNS** para o domínio que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="82c0b-156">On the **Domains** page, in the **Domain** section, select **Configure DNS** for the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="82c0b-157">Na página **Domínios**, na seção **Servidores de nomes**, selecione **Usar servidores de nomes personalizados**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-157">On the **Domains** page, in the **Name servers** section, select **Use custom name servers**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-1](../../media/e264bc05-5a56-4962-bcaf-e2d999f62278.png)
  
4. <span data-ttu-id="82c0b-159">Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:</span><span class="sxs-lookup"><span data-stu-id="82c0b-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="82c0b-160">Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="82c0b-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="82c0b-161">Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="82c0b-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="82c0b-162">Se NÃO houver nameservers listados</span><span class="sxs-lookup"><span data-stu-id="82c0b-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="82c0b-163">Adicione o primeiro nameserver.</span><span class="sxs-lookup"><span data-stu-id="82c0b-163">Add the first nameserver.</span></span>
    
    <span data-ttu-id="82c0b-164">Na seção **Servidores de nomes**, na caixa **SERVIDOR DE NOMES**, digite ou copie e cole o primeiro valor da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="82c0b-164">In the **Name servers** section, in the **NAME SERVER** box, type or copy and paste the first value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="82c0b-165">**Primeiro servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="82c0b-165">**First name server**</span></span> <br/> |<span data-ttu-id="82c0b-166">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-166">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="82c0b-167">**Segundo servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="82c0b-167">**Second name server**</span></span> <br/> |<span data-ttu-id="82c0b-168">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-168">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="82c0b-169">**Terceiro servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="82c0b-169">**Third name server**</span></span> <br/> |<span data-ttu-id="82c0b-170">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-170">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="82c0b-171">**Quarto servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="82c0b-171">**Fourth name server**</span></span> <br/> |<span data-ttu-id="82c0b-172">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-172">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegar-1-2](../../media/6d14544d-7783-4ed4-b4dd-691624af7172.png)
  
2. <span data-ttu-id="82c0b-174">Selecione o controle **+ (Adicionar)** para criar uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="82c0b-174">Select the **+ (add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-3](../../media/ea23e5fc-07e1-4ffc-b8cf-8526867b752d.png)
  
3. <span data-ttu-id="82c0b-176">Adicione os outros três registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="82c0b-176">Add the other three Nameserver records.</span></span>
    
    <span data-ttu-id="82c0b-177">Na seção **usar servidores de nomes personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione o controle **+ (Adicionar)** para adicionar outra linha.</span><span class="sxs-lookup"><span data-stu-id="82c0b-177">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+ (add)** control to add another row.</span></span> 
    
    <span data-ttu-id="82c0b-178">Repita esse processo até ter criado todos os quatro registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="82c0b-178">Repeat this process until you have created all four Nameserver records.</span></span>
    
4. <span data-ttu-id="82c0b-179">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-179">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="82c0b-181">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="82c0b-181">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="82c0b-182">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="82c0b-182">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="82c0b-183">Se HOUVER nameservers listados</span><span class="sxs-lookup"><span data-stu-id="82c0b-183">If there ARE nameservers already listed</span></span>

1. <span data-ttu-id="82c0b-184">Se houver outros nameservers listados, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-184">If there are any other nameservers listed, select **Edit**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="82c0b-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="82c0b-185">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="82c0b-186">(Ou seja, exclua somente os nameservers atuais que  *não*  sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com** ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="82c0b-186">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
    ![Google-Domains-BP-Redelegate-1-6-1](../../media/fb45d120-55ab-42c2-bdb6-19b130c3c7db.png)
  
2. <span data-ttu-id="82c0b-188">Exclua cada um selecionando-o e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="82c0b-188">Delete each one by selecting it, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-6-2](../../media/524e64ad-56e6-4254-8a64-e4a4c3230f89.png)
  
3. <span data-ttu-id="82c0b-190">Ainda na seção **Servidores de nomes**, nas linhas **SERVIDOR DE NOMES**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="82c0b-190">Still in the **Name servers** section, in the **NAME SERVER** rows, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="82c0b-191">**Primeiro servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="82c0b-191">**First name server**</span></span> <br/> |<span data-ttu-id="82c0b-192">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-192">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="82c0b-193">**Segundo servidor de nomes**</span><span class="sxs-lookup"><span data-stu-id="82c0b-193">**Second name server**</span></span> <br/> |<span data-ttu-id="82c0b-194">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-194">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="82c0b-195">**Terceiro servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="82c0b-195">**Third name server**</span></span> <br/> |<span data-ttu-id="82c0b-196">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-196">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="82c0b-197">**Quarto servidor de nome**</span><span class="sxs-lookup"><span data-stu-id="82c0b-197">**Fourth name server**</span></span> <br/> |<span data-ttu-id="82c0b-198">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="82c0b-198">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Google-Domains-BP-redelegar-1-7](../../media/e008dccb-d789-4f52-8ecc-02831b7c6fb2.png)
  
4. <span data-ttu-id="82c0b-200">Selecione o controle **+ (Adicionar)** para criar uma linha vazia.</span><span class="sxs-lookup"><span data-stu-id="82c0b-200">Select the **+(add)** control to create an empty row.</span></span> 
    
    ![Google-Domains-BP-Redelegate-1-8](../../media/6ce40b1e-8464-443f-a64a-825dc8764590.png)
  
5. <span data-ttu-id="82c0b-202">Adicione os outros dois registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="82c0b-202">Add the other two Nameserver records.</span></span>
    
    <span data-ttu-id="82c0b-203">Na seção **usar servidores de nomes personalizados** , crie um registro usando os valores da próxima linha na tabela e, em seguida, selecione o controle **+ (Adicionar)** para adicionar outra linha.</span><span class="sxs-lookup"><span data-stu-id="82c0b-203">In the **Use custom name servers** section, create a record by using the values from the next row in the table, and then select the **+(add)** control to add another row.</span></span> 
    
    <span data-ttu-id="82c0b-204">Repita esse processo até ter criado todos os quatro registros Nameserver.</span><span class="sxs-lookup"><span data-stu-id="82c0b-204">Repeat this process until you have created all four Nameserver records.</span></span>
    
6. <span data-ttu-id="82c0b-205">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82c0b-205">Select **Save**.</span></span>
    
    ![Google-Domains-BP-Redelegate-1-5](../../media/cb954aa2-12ee-4e90-9b67-184cbe898bbb.png)
  
> [!NOTE]
> <span data-ttu-id="82c0b-207">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="82c0b-207">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="82c0b-208">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="82c0b-208">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
