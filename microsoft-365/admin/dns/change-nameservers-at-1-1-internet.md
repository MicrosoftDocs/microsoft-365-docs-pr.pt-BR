---
title: Alterar os nameservers para configurar o Office 365 com 1&1 IONOS
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
ms.assetid: 31efc571-c8b9-46fb-b42d-203c2fb25289
description: Saiba como você pode configurar o Office 365 operado pela 21Vianet para gerenciar seus registros DNS, quando 1&1 Internet é o provedor de Hospedagem de DNS.
ms.openlocfilehash: 907e4fe097634d28ad44e4d44ba8c6ff2da9164d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237500"
---
# <a name="change-nameservers-to-set-up-office-365-with-11-ionos"></a><span data-ttu-id="6e2d5-103">Alterar os nameservers para configurar o Office 365 com 1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="6e2d5-103">Change nameservers to set up Office 365 with 1&1 IONOS</span></span>

 <span data-ttu-id="6e2d5-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6e2d5-105">Siga essas instruções se desejar que o Office 365 gerencie os registros DNS do Office 365 para você.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-105">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you.</span></span> <span data-ttu-id="6e2d5-106">Se preferir, [gerencie todos os registros DNS do Office 365 em 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span><span class="sxs-lookup"><span data-stu-id="6e2d5-106">(If you prefer, you can [manage all your Office 365 DNS records at 1&1 IONOS](create-dns-records-at-1-1-internet.md).)</span></span> 
  

    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="6e2d5-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="6e2d5-107">Add a TXT record for verification</span></span>


<span data-ttu-id="6e2d5-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e2d5-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="6e2d5-112">Siga as etapas abaixo ou [assista ao vídeo (início em 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6e2d5-112">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6e2d5-113">Para começar, vá até a página de domínios em 1&1 IONOS por meio [deste link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="6e2d5-113">To get started, go to your domains page at 1&1 IONOS via [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="6e2d5-114">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-114">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="6e2d5-115">Em **meus domínios**, selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-115">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="6e2d5-116">Na página **centro de domínio** , localize o domínio que você deseja atualizar; em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-116">On the **Domain Center** page, find the domain that you want to update; then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="6e2d5-117">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-117">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="6e2d5-118">Na seção **registros txt e SRV** , selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-118">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
    <span data-ttu-id="6e2d5-119">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="6e2d5-119">(You may have to scroll down.)</span></span> 
    
6. <span data-ttu-id="6e2d5-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-120">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="6e2d5-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-121">**Type**</span></span> <br/> |<span data-ttu-id="6e2d5-122">**Prefixo**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-122">**Prefix**</span></span> <br/> |<span data-ttu-id="6e2d5-123">**Valor do Nome**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-123">**Name Value**</span></span> <br/> |
|<span data-ttu-id="6e2d5-124">TXT</span><span class="sxs-lookup"><span data-stu-id="6e2d5-124">TXT</span></span>  <br/> |<span data-ttu-id="6e2d5-125">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="6e2d5-125">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="6e2d5-126">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6e2d5-126">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="6e2d5-127">**Observação**: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-127">**Note**: This is an example.</span></span> <span data-ttu-id="6e2d5-128">Use aqui o valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela em Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-128">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="6e2d5-129">Como faço para encontrar isso?</span><span class="sxs-lookup"><span data-stu-id="6e2d5-129">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
7. <span data-ttu-id="6e2d5-130">Selecione **salvar**e **salve** novamente.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-130">Select **Save**, and then **Save** again.</span></span> 
    
8. <span data-ttu-id="6e2d5-131">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-131">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
9. <span data-ttu-id="6e2d5-132">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6e2d5-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="6e2d5-134">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6e2d5-135">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="6e2d5-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6e2d5-136">Na página **domínios** , selecione o domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6e2d5-137">Na página **configuração** , selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6e2d5-138">Na página **verificar domínio** , selecione **verificar**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6e2d5-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6e2d5-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6e2d5-141">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6e2d5-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="6e2d5-142">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="6e2d5-142">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="6e2d5-p107">Para concluir a configuração do domínio com o Office 365, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários do Office 365. Isso configura o Office 365 para atualizar os registros DNS do seu domínio. Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="6e2d5-p108">Ao alterar os registros NS do domínio para direcionar para os servidores de nome do Office 365, todos os serviços associados atualmente a esse domínio serão afetados. Por exemplo, todos os emails enviados para seu domínio (como paulo@ *seu_domínio*  .com) vão começar a chegar no Office 365, depois que essa alteração for feita.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
<span data-ttu-id="6e2d5-p109">Pronto para alterar os registros NS de modo que o Office 365 possa configurar seu domínio? Siga as etapas abaixo ou [assista ao vídeo (inicia em 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p109">Ready to change your NS records so Office 365 can set up your domain? Follow the steps below or [watch the video (start at 2:47)](https://support.office.com/article/Video-Change-nameservers-to-set-up-Office-365-with-1-1-Internet-0ef1b3b5-d27a-4004-8ca1-fbe0453a0ea3?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="6e2d5-150">O procedimento a seguir mostrará como excluir outros nameservers indesejados da lista e também como adicionar os nameservers corretos se eles ainda não estiverem listados.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-150">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="6e2d5-151">> quando você tiver concluído as etapas nesta seção, os únicos nameservers que devem ser listados são estes quatro: > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-151">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="6e2d5-152">Para começar, vá até a página de domínios em 1&1 IONOS usando [este link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span><span class="sxs-lookup"><span data-stu-id="6e2d5-152">To get started, go to your domains page at 1&1 IONOS by using [this link](https://account.1and1.com/?redirect_url=https%3A%2F%2Fmy.1and1.com%2F).</span></span> <span data-ttu-id="6e2d5-153">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-153">You'll be prompted to log in.</span></span> 
    
2. <span data-ttu-id="6e2d5-154">Em **meus domínios**, selecione **gerenciar domínios**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-154">Under **MY DOMAINS**, select **Manage domains**.</span></span>
    
3. <span data-ttu-id="6e2d5-155">Na página **centro de domínio** , localize o domínio que você deseja atualizar e, em seguida, selecione o controle de **painel** ( **v**) para esse domínio.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-155">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="6e2d5-156">Na área **configurações de domínio** , selecione **Editar configurações de DNS**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-156">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="6e2d5-157">Na seção **Configurações de Servidor de nomes**, selecione **Outros servidores de nomes**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-157">In the **Name Server Settings** section, select **Other name servers**.</span></span>
    
    <span data-ttu-id="6e2d5-158">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="6e2d5-158">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="6e2d5-159">Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:</span><span class="sxs-lookup"><span data-stu-id="6e2d5-159">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="6e2d5-160">Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="6e2d5-160">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="6e2d5-161">Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="6e2d5-161">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="6e2d5-162">Se NÃO houver nameservers listados</span><span class="sxs-lookup"><span data-stu-id="6e2d5-162">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="6e2d5-163">Na segunda caixa **Servidor de nomes 1**, digite ou copie e cole o valor da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-163">In the **Name server 1** box, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6e2d5-164">**Servidor de nomes 1**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-164">**Name server 1**</span></span> <br/> |<span data-ttu-id="6e2d5-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Inserindo um valor na caixa servidor de nomes 1](../media/34509935-461f-427f-9796-c3cf840bd9be.png)
  
2. <span data-ttu-id="6e2d5-167">Na lista suspensa **Servidores de nomes adicionais**, escolha **Meus servidores de nomes secundários**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-167">In the **Additional name servers** drop-down list, choose **My secondary name servers**.</span></span>
    
    ![Choosing My secondary name servers in the list](../media/7eb14856-86da-45c2-910c-c72312250a18.png)
  
3. <span data-ttu-id="6e2d5-169">Nas caixas **Servidor de nomes 2, 3 e 4**, digite ou copie e cole o valor da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-169">In the **Name server 2, 3, and 4** boxes, type or copy and paste the value from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6e2d5-170">**Servidor de nomes 2**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-170">**Name server 2**</span></span> <br/> |<span data-ttu-id="6e2d5-171">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-171">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e2d5-172">**Servidor de nomes 3**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-172">**Name server 3**</span></span> <br/> |<span data-ttu-id="6e2d5-173">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-173">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e2d5-174">**Servidor de nomes 4**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-174">**Name server 4**</span></span> <br/> |<span data-ttu-id="6e2d5-175">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-175">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Entering name server values](../media/0f15880c-88b6-4133-8f31-62f0d98ee63f.png)
  
4. <span data-ttu-id="6e2d5-176">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-176">Select **Save**.</span></span>
    
    ![Selecionar salvar na página Configurações do servidor de nomes](../media/864f7927-7127-4784-b8d2-dadfea2f9dc8.png)
  
5. <span data-ttu-id="6e2d5-178">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-178">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Selecionar salvar na caixa de diálogo Editar configurações de DNS](../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="6e2d5-p112">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p112">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="6e2d5-182">Se HOUVER nameservers listados</span><span class="sxs-lookup"><span data-stu-id="6e2d5-182">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="6e2d5-p113">Siga estas etapas  *somente*  se você tiver outros nameservers existentes, além dos quatro nameservers  *corretos*  . Ou seja, exclua  *somente*  nameservers atuais que  *não*  sejam denominados como **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** ou **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="6e2d5-185">Se houver outros nameservers listados nas caixas **Servidor de nomes**, exclua cada um deles selecionando e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-185">If there are already nameservers listed in the **Name server** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Deleting name servers](../media/af0a68cc-b058-4925-b3b1-52dfded003c1.png)
  
2. <span data-ttu-id="6e2d5-187">Nas caixas **Servidor de nomes 1, 2, 3 e 4**, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-187">In the **Name server 1, 2, 3, and 4** boxes, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="6e2d5-188">**Servidor de nomes 1**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-188">**Name server 1**</span></span> <br/> |<span data-ttu-id="6e2d5-189">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-189">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e2d5-190">**Servidor de nomes 2**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-190">**Name server 2**</span></span> <br/> |<span data-ttu-id="6e2d5-191">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-191">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e2d5-192">**Servidor de nomes 3**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-192">**Name server 3**</span></span> <br/> |<span data-ttu-id="6e2d5-193">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-193">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="6e2d5-194">**Servidor de nomes 4**</span><span class="sxs-lookup"><span data-stu-id="6e2d5-194">**Name server 4**</span></span> <br/> |<span data-ttu-id="6e2d5-195">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="6e2d5-195">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Inserir valores de servidor de nomes](../media/52826bd1-0596-4103-a728-d5d28b9610d2.png)
  
3. <span data-ttu-id="6e2d5-197">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-197">Select **Save**.</span></span>
    
    ![Selecionar salvar na página Configurações do servidor de nomes](../media/cd10e4fb-b7fa-480f-855b-a443f2705cf2.png)
  
4. <span data-ttu-id="6e2d5-199">Na caixa de diálogo **Editar configurações de DNS** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-199">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
    ![Selecionar salvar na caixa de diálogo Editar configurações de DNS](../media/0558e24c-17cd-428c-9ec1-5ed46481af7c.png)
  
> [!NOTE]
> <span data-ttu-id="6e2d5-p114">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet. Em seguida, os seus emails e outros serviços do Office 365 serão todos configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="6e2d5-p114">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  


