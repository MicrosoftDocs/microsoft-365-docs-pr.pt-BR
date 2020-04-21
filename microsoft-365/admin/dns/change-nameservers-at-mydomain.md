---
title: Alterar os nameservers para configurar o Microsoft com mydomain
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
ms.assetid: c5f6140a-4a12-401b-9bbd-7dfb0d6b0ba3
description: Saiba como você pode configurar a Microsoft para gerenciar os registros DNS do seu domínio personalizado em mydomain.
ms.openlocfilehash: 8f4a72aa0ece24ed09c4d036239a2a13c196be6c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629786"
---
# <a name="change-nameservers-to-set-up-microsoft-with-mydomain"></a><span data-ttu-id="b5a03-103">Alterar os nameservers para configurar o Microsoft com mydomain</span><span class="sxs-lookup"><span data-stu-id="b5a03-103">Change nameservers to set up Microsoft with MyDomain</span></span>

 <span data-ttu-id="b5a03-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="b5a03-105">Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="b5a03-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="b5a03-106">Se preferir, [gerencie todos os registros DNS da Microsoft em mydomain](create-dns-records-at-mydomain.md).</span><span class="sxs-lookup"><span data-stu-id="b5a03-106">(If you prefer, you can [manage all your Microsoft DNS records at MyDomain](create-dns-records-at-mydomain.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="b5a03-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="b5a03-107">Add a TXT record for verification</span></span>

<span data-ttu-id="b5a03-108">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="b5a03-108">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="b5a03-109">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="b5a03-109">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5a03-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="b5a03-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="b5a03-p104">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="b5a03-p104">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b5a03-114">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-114">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="b5a03-115">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="b5a03-115">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="b5a03-116">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-116">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="b5a03-117">Na lista suspensa **Modificar**, clique em **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-117">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="b5a03-118">Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5a03-118">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
||
|:-----|
|<span data-ttu-id="b5a03-119">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="b5a03-119">**Content**</span></span> <br/> |
|<span data-ttu-id="b5a03-120">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="b5a03-120">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="b5a03-121">**Observação**: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="b5a03-121">**Note**: This is an example.</span></span> <span data-ttu-id="b5a03-122">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="b5a03-122">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="b5a03-123">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="b5a03-123">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="b5a03-124">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-124">Select **Add**.</span></span>
    
8. <span data-ttu-id="b5a03-125">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="b5a03-125">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="b5a03-126">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para o Microsoft 365 e solicitará que a Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="b5a03-126">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="b5a03-127">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="b5a03-127">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="b5a03-128">No centro de administração da Microsoft, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="b5a03-128">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="b5a03-129">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="b5a03-129">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="b5a03-130">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-130">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="b5a03-131">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-131">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5a03-132">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="b5a03-132">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="b5a03-133">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="b5a03-133">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="b5a03-134">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="b5a03-134">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="b5a03-135">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="b5a03-135">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="b5a03-136">Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b5a03-136">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="b5a03-137">Isso configura a Microsoft para atualizar os registros DNS do domínio para você.</span><span class="sxs-lookup"><span data-stu-id="b5a03-137">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="b5a03-138">Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="b5a03-138">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b5a03-139">Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="b5a03-139">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="b5a03-140">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain.*</span><span class="sxs-lookup"><span data-stu-id="b5a03-140">For example, all email sent to your domain (like rob@ *your_domain.*</span></span> <span data-ttu-id="b5a03-141">com) começará à Microsoft depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="b5a03-141">com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b5a03-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span><span class="sxs-lookup"><span data-stu-id="b5a03-142">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already in the list.</span></span> <br/> <span data-ttu-id="b5a03-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span><span class="sxs-lookup"><span data-stu-id="b5a03-143">When you have completed the steps in this section, the only nameservers that should be listed are these four:</span></span>
  
1. <span data-ttu-id="b5a03-p110">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="b5a03-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="b5a03-146">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="b5a03-147">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="b5a03-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="b5a03-148">Na linha **visão geral** , selecione **nameservers**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-148">In the **Overview** row, select **Nameservers**.</span></span>
    
    ![Mydomain-BP-redelegar-1-1](../../media/49e91235-44b5-46d6-a82e-8f11329db3d6.png)
  
5. <span data-ttu-id="b5a03-150">Na seção **Update Name Servers**, selecione **Use different name servers**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-150">In the **Update Name Servers** section, select **Use different name servers**.</span></span>
    
    ![Mydomain-BP-redelegar-1-2-1](../../media/f869fb26-54dc-4b66-8378-a78a79b582bd.png)
  
6. <span data-ttu-id="b5a03-152">Dependendo se já existem ou não nameservers listados na página exibida agora, continue com um dos dois procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5a03-152">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-the-correct-nameservers-are-already-listed"></a><span data-ttu-id="b5a03-153">Se os nameservers corretos já ESTIVEREM listados</span><span class="sxs-lookup"><span data-stu-id="b5a03-153">If the correct nameservers ARE already listed</span></span>

- <span data-ttu-id="b5a03-154">Se os nameservers corretos já estiverem listados, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="b5a03-154">If the correct nameservers are already listed, you can skip this step.</span></span>
    
    ![Mydomain-BP-redelegar-1-2-2](../../media/601f6a46-15bd-4a92-b792-ac628ff86628.png)
  
### <a name="if-the-correct-nameservers-are-not-already-listed"></a><span data-ttu-id="b5a03-156">Se os nameservers corretos NÃO ESTIVEREM listados</span><span class="sxs-lookup"><span data-stu-id="b5a03-156">If the correct nameservers are NOT already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="b5a03-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="b5a03-157">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="b5a03-158">(Ou seja, exclua somente os nameservers atuais que *não* sejam denominados **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **NS3.bdm.microsoftonline.com**ou **NS4.bdm.microsoftonline.com**.)</span><span class="sxs-lookup"><span data-stu-id="b5a03-158">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="b5a03-159">Exclua os nameservers existentes selecionado cada entrada no campo **Nameserver:** e, em seguida, pressione a tecla **Delete** no seu teclado.</span><span class="sxs-lookup"><span data-stu-id="b5a03-159">Delete the existing nameservers by selecting each entry in the **Nameserver:** field, and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Mydomain-BP-redelegar-1-3-1](../../media/5024cd27-a2b1-42a2-99e4-5ceb5e6eddb9.png)
  
2. <span data-ttu-id="b5a03-161">Selecione **adicionar mais** duas vezes para adicionar duas novas linhas de nameserver.</span><span class="sxs-lookup"><span data-stu-id="b5a03-161">Select **Add More** twice to add two new Nameserver rows.</span></span> 
    
    ![Mydomain-BP-redelegar-1-3-2](../../media/19307893-2f73-4e4d-9221-a5870e09ab48.png)
  
3. <span data-ttu-id="b5a03-163">Nas caixas dos registros, digite ou copie e cole os valores de nameserver da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b5a03-163">In the boxes for the records, type or copy and paste the nameserver values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="b5a03-164">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="b5a03-164">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="b5a03-165">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b5a03-165">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b5a03-166">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="b5a03-166">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="b5a03-167">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b5a03-167">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b5a03-168">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="b5a03-168">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="b5a03-169">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b5a03-169">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="b5a03-170">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="b5a03-170">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="b5a03-171">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="b5a03-171">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Mydomain-BP-redelegar-1-4](../../media/7427e99c-49c7-4a2e-a5bf-66fc46900cd1.png)
  
4. <span data-ttu-id="b5a03-173">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b5a03-173">Select **Save**.</span></span>
    
    ![Mydomain-BP-redelegar-1-5](../../media/48473816-b881-47f0-9344-74622efa3bf8.png)
  
> [!NOTE]
> <span data-ttu-id="b5a03-175">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="b5a03-175">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="b5a03-176">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="b5a03-176">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
