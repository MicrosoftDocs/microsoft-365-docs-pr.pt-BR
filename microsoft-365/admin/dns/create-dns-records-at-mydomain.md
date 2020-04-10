---
title: Criar registros DNS no site MyDomain para o Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9982191d-ed79-46a9-b2e7-317d1a3a9867
description: Aprenda a verificar seu domínio e a configurar registros DNS para e-mails, Skype for Business Online e outros serviços em Meu Domínio do Office 365.
ms.openlocfilehash: 1a75c2ab0077cac07781e5102c43e53ed965b1df
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211686"
---
# <a name="create-dns-records-at-mydomain-for-office-365"></a><span data-ttu-id="21523-103">Criar registros DNS no site Meu Domínio do Office 365</span><span class="sxs-lookup"><span data-stu-id="21523-103">Create DNS records at MyDomain for Office 365</span></span>


  
 <span data-ttu-id="21523-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="21523-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="21523-p101">O site MyDomain não dá suporte a registros SRV, ou seja, vários recursos do Skype for Business Online e do Outlook Web App não funcionarão. Não importa qual plano do Office 365 você utiliza, se você gerenciar seus registros DNS no site MyDomain, haverá [limitações de serviço significativas](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) e talvez você queira mudar para um provedor de hospedagem de DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="21523-p101">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
<span data-ttu-id="21523-107">Se você quiser gerenciar seus próprios registros DNS do Office 365 na MyDomain apesar das limitações do serviço, siga as etapas deste artigo para configurar os registros DNS para email, Skype for Business Online e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="21523-107">If you choose to manage your own Office 365 DNS records at MyDomain despite the service limitations, follow the steps in this article to set up your DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="21523-108">Depois que você adicionar esses registros na MyDomain, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="21523-108">After you add these records at MyDomain, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="21523-109">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="21523-109">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="21523-110">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="21523-110">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="21523-111">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="21523-111">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="21523-112">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="21523-112">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="21523-113">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="21523-113">Add a TXT record for verification</span></span>
<span data-ttu-id="21523-114"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="21523-114"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="21523-p103">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="21523-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21523-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="21523-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="21523-p105">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="21523-p105">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21523-121">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="21523-121">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="21523-122">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="21523-122">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="21523-123">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="21523-123">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="21523-124">Na lista suspensa **Modificar**, clique em **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="21523-124">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
6. <span data-ttu-id="21523-125">Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="21523-125">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    ||
    |:-----|
    |<span data-ttu-id="21523-126">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="21523-126">**Content**</span></span> <br/> |
    |<span data-ttu-id="21523-127">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="21523-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="21523-128">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="21523-128">**Note:** This is an example.</span></span> <span data-ttu-id="21523-129">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="21523-129">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="21523-130">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="21523-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="21523-131">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21523-131">Select **Add**.</span></span>
    
8. <span data-ttu-id="21523-132">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="21523-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="21523-133">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="21523-133">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="21523-134">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="21523-134">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="21523-135">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="21523-135">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="21523-136">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="21523-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="21523-137">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="21523-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="21523-138">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="21523-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="21523-139">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="21523-139">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="21523-140">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="21523-140">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="21523-141">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="21523-141">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="21523-142">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="21523-142">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="21523-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="21523-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="21523-p108">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="21523-p108">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21523-146">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="21523-146">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="21523-147">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="21523-147">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="21523-148">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="21523-148">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="21523-149">Na lista suspensa **Modificar**, escolha **Registro MX**.</span><span class="sxs-lookup"><span data-stu-id="21523-149">From the **Modify** drop-down list, choose **MX Record**.</span></span>
    
    ![MyDomain-BP-Configure-2-1](../../media/bbfba978-8c53-471b-8c9e-8ae62e559d15.png)
  
6. <span data-ttu-id="21523-151">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="21523-151">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="21523-152">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="21523-152">**Priority**</span></span>|<span data-ttu-id="21523-153">**Host**</span><span class="sxs-lookup"><span data-stu-id="21523-153">**Host**</span></span>|<span data-ttu-id="21523-154">**Aponta para:**</span><span class="sxs-lookup"><span data-stu-id="21523-154">**Points To:**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="21523-155">0</span><span class="sxs-lookup"><span data-stu-id="21523-155">0</span></span>  <br/> <span data-ttu-id="21523-156">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="21523-156">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |@  <br/> | <span data-ttu-id="21523-157">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="21523-157">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="21523-158">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="21523-158">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span><span data-ttu-id="21523-159"> > [Como localizo isso?](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="21523-159"> > [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![MyDomain-BP-Configure-2-2](../../media/3e19cec3-7f3b-493d-81f7-cda30ba007d5.png)
  
7. <span data-ttu-id="21523-161">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21523-161">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-2-3](../../media/1a1951a8-11d7-405d-bef5-285bbb053ce8.png)
  
8. <span data-ttu-id="21523-163">Se houver outros registros MX, selecione **Remover** na coluna **Ação** em cada um para excluí-los.</span><span class="sxs-lookup"><span data-stu-id="21523-163">If there are any other existing MX records, select **Remove** in the **Action** column for each one to delete it.</span></span> 
    
    ![MyDomain-BP-Configure-2-4](../../media/42576149-e056-4a81-a5fd-2c5dfac44e2e.png)
  
9. <span data-ttu-id="21523-165">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="21523-165">Select **OK**.</span></span>
    
    ![MyDomain-BP-Configure-2-5](../../media/d6b70eb7-b79c-499e-82ff-ecef2e300368.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="21523-167">Adicionar os registros CNAME necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="21523-167">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="21523-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="21523-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="21523-p110">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="21523-p110">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21523-171">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="21523-171">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="21523-172">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="21523-172">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="21523-173">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="21523-173">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="21523-174">Na lista suspensa **Modificar**, escolha **Alias CNAME**.</span><span class="sxs-lookup"><span data-stu-id="21523-174">From the **Modify** drop-down list, choose **CNAME Alias**.</span></span>
    
    ![MyDomain-BP-Configure-3-1](../../media/628267fc-d37b-42ef-bb92-265284e339ac.png)
  
6. <span data-ttu-id="21523-176">Adicionar o primeiro registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="21523-176">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="21523-177">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="21523-177">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="21523-178">**Host**</span><span class="sxs-lookup"><span data-stu-id="21523-178">**Host**</span></span>|<span data-ttu-id="21523-179">**Aponta para:**</span><span class="sxs-lookup"><span data-stu-id="21523-179">**Points To:**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="21523-180">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="21523-180">autodiscover</span></span>  <br/> |<span data-ttu-id="21523-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="21523-181">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="21523-182">sip</span><span class="sxs-lookup"><span data-stu-id="21523-182">sip</span></span>  <br/> |<span data-ttu-id="21523-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="21523-183">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="21523-184">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="21523-184">lyncdiscover</span></span>  <br/> |<span data-ttu-id="21523-185">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="21523-185">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="21523-186">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="21523-186">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="21523-187">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="21523-187">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="21523-188">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="21523-188">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="21523-189">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="21523-189">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![MyDomain-BP-Configure-3-2](../../media/3c8660b3-40bb-453d-8b99-4d22032bc4b3.png)
  
7. <span data-ttu-id="21523-191">Clique em **Adicionar** para adicionar o primeiro registro.</span><span class="sxs-lookup"><span data-stu-id="21523-191">Select **Add** to add the first record.</span></span> 
    
    ![MyDomain-BP-Configure-3-3](../../media/103a1d99-70da-4fdf-9291-7dd058ec6c4a.png)
  
8. <span data-ttu-id="21523-193">Adicione o segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="21523-193">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="21523-194">Use os valores da segunda linha da tabela acima e clique em **Adicionar** para adicionar o segundo registro.</span><span class="sxs-lookup"><span data-stu-id="21523-194">Use the values from the second row of the table above, and then select **Add** to add the second record.</span></span> 
    
    <span data-ttu-id="21523-195">Adicione os registros restantes da mesma maneira, usando os valores da terceira, quarta, quinta e sexta linhas da tabela.</span><span class="sxs-lookup"><span data-stu-id="21523-195">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="21523-196">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="21523-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="21523-197"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="21523-197"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="21523-198">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="21523-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="21523-199">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="21523-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="21523-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="21523-200">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="21523-201">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="21523-201">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span> <span data-ttu-id="21523-202">Precisa de exemplos?</span><span class="sxs-lookup"><span data-stu-id="21523-202">Need examples?</span></span> <span data-ttu-id="21523-203">Confira os [Registros do sistema de nomes de domínios externos do Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords). </span><span class="sxs-lookup"><span data-stu-id="21523-203">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0#bkmk_spfrecords).</span></span> <span data-ttu-id="21523-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="21523-204">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="21523-p112">Para começar, vá até a sua página de domínios em MeuDomínio usando [este link](https://www.mydomain.com/controlpanel). Você será solicitado a fazer logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="21523-p112">To get started, go to your domains page at MyDomain by using [this link](https://www.mydomain.com/controlpanel). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="21523-207">Na seção **Meus Favoritos**, clique em **Central de domínio**.</span><span class="sxs-lookup"><span data-stu-id="21523-207">In the **My Favorites** section, select **Domain Central**.</span></span>
    
3. <span data-ttu-id="21523-208">Na opção **Domínio**, clique no nome do domínio que quer editar.</span><span class="sxs-lookup"><span data-stu-id="21523-208">Under **Domain**, select the name of the domain that you want to edit.</span></span>
    
4. <span data-ttu-id="21523-209">Na linha **Visão geral**, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="21523-209">In the **Overview** row, select **DNS**.</span></span>
    
5. <span data-ttu-id="21523-210">Na lista suspensa **Modificar**, escolha **Registro TXT/SPF**.</span><span class="sxs-lookup"><span data-stu-id="21523-210">From the **Modify** drop-down list, choose **TXT/SPF Record**.</span></span>
    
    ![MyDomain-BP-Configure-4-1](../../media/c461c762-52e6-4fde-b5bc-4dd5e5d62ed3.png)
  
6. <span data-ttu-id="21523-212">Em **Content**, na caixa do novo registro, digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="21523-212">Under **Content**, in the box for the new record, type or copy and paste the value from the following table.</span></span>
    
    |<span data-ttu-id="21523-213">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="21523-213">**Content**</span></span>|
    |:-----|
    |<span data-ttu-id="21523-214">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="21523-214">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="21523-215">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="21523-215">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![MyDomain-BP-Configure-4-2](../../media/17d43106-88e6-47e5-aeba-0f18484acf3e.png)
  
7. <span data-ttu-id="21523-217">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21523-217">Select **Add**.</span></span>
    
    ![MyDomain-BP-Configure-4-3](../../media/b3670563-b620-470c-a42b-2c77888981f8.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="21523-219">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="21523-219">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="21523-220"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="21523-220"><a name="BKMK_add_SRV"> </a></span></span>

> [!CAUTION]
> <span data-ttu-id="21523-p113">O site MyDomain não dá suporte a registros SRV, ou seja, vários recursos do Skype for Business Online e do Outlook Web App não funcionarão. Não importa qual plano do Office 365 você utiliza, se você gerenciar seus registros DNS no site MyDomain, haverá [limitações de serviço significativas](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) e talvez você queira mudar para um provedor de hospedagem de DNS diferente.</span><span class="sxs-lookup"><span data-stu-id="21523-p113">The MyDomain website doesn't support SRV records, which means several Skype for Business Online and Outlook Web App features won't work. No matter which Office 365 plan you use, if you manage your DNS records at MyDomain, there are [significant service limitations](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx), and you might want to switch to a different DNS hosting provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="21523-223">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="21523-223">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="21523-224">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="21523-224">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="21523-225">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="21523-225">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
