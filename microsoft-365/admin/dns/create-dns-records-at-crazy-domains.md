---
title: Criar registros DNS em domínios malucos para a Microsoft
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em domínios malucos para a Microsoft.
ms.openlocfilehash: 05f0f281d97d497fe3a6cf9695e5c458492f95aa
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049078"
---
# <a name="create-dns-records-at-crazy-domains-for-microsoft"></a><span data-ttu-id="71140-103">Criar registros DNS em domínios malucos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71140-103">Create DNS records at Crazy Domains for Microsoft</span></span>

 <span data-ttu-id="71140-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="71140-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="71140-105">Se você usa a Crazy Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="71140-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="71140-106">Depois que você adicionar esses registros em domínios malucos, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71140-106">After you add these records at Crazy Domains, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="71140-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71140-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="71140-110">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="71140-110">Add a TXT record for verification</span></span>
<span data-ttu-id="71140-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="71140-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="71140-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="71140-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71140-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="71140-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="71140-p104">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="71140-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="71140-119">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="71140-119">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="71140-121">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="71140-121">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="71140-123">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="71140-123">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="71140-125">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="71140-125">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="71140-127">Escolha **Registro TXT** na lista suspensa **Adicionar Registro**.</span><span class="sxs-lookup"><span data-stu-id="71140-127">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="71140-129">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="71140-129">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="71140-131">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="71140-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="71140-132">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="71140-132">**Sub Domain**</span></span>|<span data-ttu-id="71140-133">**Registro de Texto**</span><span class="sxs-lookup"><span data-stu-id="71140-133">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="71140-134">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="71140-134">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="71140-135">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="71140-135">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="71140-136">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="71140-136">**Note:** This is an example.</span></span> <span data-ttu-id="71140-137">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="71140-137">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="71140-138">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="71140-138">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="71140-140">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="71140-140">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="71140-142">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="71140-142">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="71140-143">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="71140-143">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="71140-144">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="71140-144">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="71140-145">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="71140-145">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="71140-146">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="71140-146">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="71140-147">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="71140-147">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="71140-148">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="71140-148">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="71140-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71140-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="71140-152">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71140-152">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="71140-153"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="71140-153"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="71140-p107">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="71140-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="71140-157">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="71140-157">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="71140-159">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="71140-159">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="71140-161">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="71140-161">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="71140-163">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="71140-163">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="71140-165">Escolha **Registro MX** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="71140-165">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="71140-167">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="71140-167">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="71140-169">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="71140-169">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="71140-170">(Escolha o valor **prioridade** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="71140-170">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="71140-171">**Email para a zona**</span><span class="sxs-lookup"><span data-stu-id="71140-171">**Mail For Zone**</span></span>|<span data-ttu-id="71140-172">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="71140-172">**Priority**</span></span>|<span data-ttu-id="71140-173">**Atribuído a um servidor**</span><span class="sxs-lookup"><span data-stu-id="71140-173">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="71140-174">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="71140-174">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="71140-175">1</span><span class="sxs-lookup"><span data-stu-id="71140-175">1</span></span>  <br/> <span data-ttu-id="71140-176">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="71140-176">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="71140-177">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="71140-177">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="71140-178">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71140-178">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="71140-179">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="71140-179">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="71140-181">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="71140-181">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="71140-183">Se houver outros registros MX listados na seção **registro MX** , selecione **Modificar** para um desses registros.</span><span class="sxs-lookup"><span data-stu-id="71140-183">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="71140-185">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="71140-185">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="71140-187">Selecione **Atualizar** para confirmar a exclusão.</span><span class="sxs-lookup"><span data-stu-id="71140-187">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="71140-189">Use o mesmo processo para remover outros registros MX na lista, até que somente o domínio que você adicionou anteriormente neste procedimento permaneça.</span><span class="sxs-lookup"><span data-stu-id="71140-189">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="71140-190">Adicionar os seis registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="71140-190">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="71140-191"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="71140-191"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="71140-p109">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="71140-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="71140-195">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="71140-195">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="71140-197">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="71140-197">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="71140-199">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="71140-199">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="71140-201">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="71140-201">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="71140-203">Escolha **Registro CNAME** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="71140-203">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="71140-205">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="71140-205">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="71140-207">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="71140-207">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="71140-208">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="71140-208">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="71140-209">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="71140-209">**Sub Domain**</span></span>|<span data-ttu-id="71140-210">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="71140-210">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="71140-211">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="71140-211">autodiscover</span></span>  <br/> |<span data-ttu-id="71140-212">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="71140-212">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="71140-213">sip</span><span class="sxs-lookup"><span data-stu-id="71140-213">sip</span></span>  <br/> |<span data-ttu-id="71140-214">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71140-214">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="71140-215">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="71140-215">lyncdiscover</span></span>  <br/> |<span data-ttu-id="71140-216">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71140-216">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="71140-217">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="71140-217">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="71140-218">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="71140-218">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="71140-219">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="71140-219">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="71140-220">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="71140-220">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="71140-222">Selecione **adicionar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="71140-222">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="71140-224">Adicione o segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="71140-224">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="71140-225">Nas caixas do novo registro, use os valores da próxima linha na tabela e selecione novamente **adicionar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="71140-225">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="71140-226">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="71140-226">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="71140-227">Selecione **Atualizar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="71140-227">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="71140-229">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="71140-229">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="71140-230"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="71140-230"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="71140-231">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="71140-231">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="71140-232">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="71140-232">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="71140-233">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71140-233">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="71140-234">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="71140-234">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="71140-p111">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="71140-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="71140-238">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="71140-238">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="71140-240">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="71140-240">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="71140-242">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="71140-242">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="71140-244">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="71140-244">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="71140-246">Escolha **Registro TXT** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="71140-246">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="71140-248">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="71140-248">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="71140-250">Nas caixas do novo registro, digite ou cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="71140-250">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="71140-251">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="71140-251">**Sub Domain**</span></span>|<span data-ttu-id="71140-252">**Registro de Texto**</span><span class="sxs-lookup"><span data-stu-id="71140-252">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="71140-253">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="71140-253">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="71140-254">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="71140-254">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="71140-255">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="71140-255">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="71140-257">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="71140-257">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="71140-259">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="71140-259">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="71140-260"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="71140-260"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="71140-p112">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="71140-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="71140-264">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="71140-264">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="71140-266">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="71140-266">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="71140-268">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="71140-268">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="71140-270">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="71140-270">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="71140-272">Escolha **Registro SRV** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="71140-272">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="71140-274">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="71140-274">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="71140-276">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="71140-276">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="71140-277">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="71140-277">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="71140-278">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="71140-278">**Record Type**</span></span>|<span data-ttu-id="71140-279">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="71140-279">**Sub Domain**</span></span>|<span data-ttu-id="71140-280">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="71140-280">**Priority**</span></span>|<span data-ttu-id="71140-281">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="71140-281">**Weight**</span></span>|<span data-ttu-id="71140-282">**Porta**</span><span class="sxs-lookup"><span data-stu-id="71140-282">**Port**</span></span>|<span data-ttu-id="71140-283">**Destino**</span><span class="sxs-lookup"><span data-stu-id="71140-283">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="71140-284">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="71140-284">SRV Record</span></span>  <br/> |<span data-ttu-id="71140-285">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="71140-285">_sip._tls</span></span>  <br/> |<span data-ttu-id="71140-286">100</span><span class="sxs-lookup"><span data-stu-id="71140-286">100</span></span>  <br/> |<span data-ttu-id="71140-287">1</span><span class="sxs-lookup"><span data-stu-id="71140-287">1</span></span>  <br/> |<span data-ttu-id="71140-288">443</span><span class="sxs-lookup"><span data-stu-id="71140-288">443</span></span>  <br/> |<span data-ttu-id="71140-289">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71140-289">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="71140-290">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="71140-290">SRV Record</span></span>  <br/> |<span data-ttu-id="71140-291">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="71140-291">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="71140-292">100</span><span class="sxs-lookup"><span data-stu-id="71140-292">100</span></span>  <br/> |<span data-ttu-id="71140-293">1</span><span class="sxs-lookup"><span data-stu-id="71140-293">1</span></span>  <br/> |<span data-ttu-id="71140-294">5061</span><span class="sxs-lookup"><span data-stu-id="71140-294">5061</span></span>  <br/> |<span data-ttu-id="71140-295">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="71140-295">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="71140-297">Selecione **adicionar registro SRV**.</span><span class="sxs-lookup"><span data-stu-id="71140-297">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="71140-299">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="71140-299">Add the other SRV record.</span></span>
    
    <span data-ttu-id="71140-300">Nas caixas para o novo registro, use os valores da segunda linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="71140-300">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="71140-301">Selecione **Atualizar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="71140-301">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="71140-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="71140-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
