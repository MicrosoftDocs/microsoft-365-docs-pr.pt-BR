---
title: Criar registros DNS no site Crazy Domains para o Office 365
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em domínios malucos para o Office 365.
ms.openlocfilehash: 74c9a940f8d6f52c31712357557ea8cfda76e6bb
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211818"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="5c5e8-103">Criar registros DNS no site Crazy Domains para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5c5e8-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="5c5e8-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5c5e8-105">Se você usa a Crazy Domains como provedor de hospedagem DNS, realize os procedimentos deste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5c5e8-106">Depois que você adicionar esses registros na Crazy Domains, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5c5e8-107">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5c5e8-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c5e8-p101">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5c5e8-111">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="5c5e8-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5c5e8-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5c5e8-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5c5e8-p102">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c5e8-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5c5e8-p104">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5c5e8-120">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5c5e8-122">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5c5e8-124">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5c5e8-126">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5c5e8-128">Escolha **Registro TXT** na lista suspensa **Adicionar Registro**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-Verify-1-1](../../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="5c5e8-130">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-130">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-2](../../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="5c5e8-132">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5c5e8-133">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-133">**Sub Domain**</span></span>|<span data-ttu-id="5c5e8-134">**Registro de Texto**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5c5e8-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5c5e8-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5c5e8-136">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5c5e8-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5c5e8-137">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-137">**Note:** This is an example.</span></span> <span data-ttu-id="5c5e8-138">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-138">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span>           [<span data-ttu-id="5c5e8-139">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="5c5e8-139">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![CrazyDomains-BP-Verify-1-3](../../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="5c5e8-141">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-141">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-Verify-1-4](../../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="5c5e8-143">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5c5e8-144">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5c5e8-145">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5c5e8-146">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5c5e8-147">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5c5e8-148">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5c5e8-149">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5c5e8-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5c5e8-153">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5c5e8-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5c5e8-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5c5e8-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5c5e8-p107">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5c5e8-158">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5c5e8-160">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5c5e8-162">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5c5e8-164">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5c5e8-166">Escolha **Registro MX** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-2-1](../../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="5c5e8-168">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-168">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-2-2](../../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="5c5e8-170">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5c5e8-171">(Escolha o valor **prioridade** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="5c5e8-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5c5e8-172">**Email para a zona**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-172">**Mail For Zone**</span></span>|<span data-ttu-id="5c5e8-173">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-173">**Priority**</span></span>|<span data-ttu-id="5c5e8-174">**Atribuído a um servidor**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5c5e8-175">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="5c5e8-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5c5e8-176">1</span><span class="sxs-lookup"><span data-stu-id="5c5e8-176">1</span></span>  <br/> <span data-ttu-id="5c5e8-177">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="5c5e8-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5c5e8-178">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5c5e8-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5c5e8-179">**Observação:** Obtenha sua \* \<chave\> de domínio\* de sua conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="5c5e8-180">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="5c5e8-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-BP-configure-2-3](../../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="5c5e8-182">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-182">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-2-4](../../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="5c5e8-184">Se houver outros registros MX listados na seção **registro MX** , selecione **Modificar** para um desses registros.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-BP-configure-2-5](../../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="5c5e8-186">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-BP-configure-2-6](../../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="5c5e8-188">Selecione **Atualizar** para confirmar a exclusão.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-BP-configure-2-7](../../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="5c5e8-190">Use o mesmo processo para remover outros registros MX na lista, até que somente o domínio que você adicionou anteriormente neste procedimento permaneça.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5c5e8-191">Adicionar os seis registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="5c5e8-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5c5e8-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5c5e8-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5c5e8-p109">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5c5e8-196">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5c5e8-198">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5c5e8-200">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5c5e8-202">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5c5e8-204">Escolha **Registro CNAME** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-3-1](../../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="5c5e8-206">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-206">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-3-2](../../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="5c5e8-208">Adicione o primeiro dos seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="5c5e8-209">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="5c5e8-210">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-210">**Sub Domain**</span></span>|<span data-ttu-id="5c5e8-211">**Alias para**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5c5e8-212">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="5c5e8-212">autodiscover</span></span>  <br/> |<span data-ttu-id="5c5e8-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5c5e8-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5c5e8-214">sip</span><span class="sxs-lookup"><span data-stu-id="5c5e8-214">sip</span></span>  <br/> |<span data-ttu-id="5c5e8-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c5e8-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5c5e8-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5c5e8-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5c5e8-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c5e8-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5c5e8-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5c5e8-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5c5e8-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5c5e8-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5c5e8-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5c5e8-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5c5e8-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5c5e8-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-3-3](../../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="5c5e8-223">Selecione **adicionar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-BP-configure-3-4](../../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="5c5e8-225">Adicione o segundo registro CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="5c5e8-226">Nas caixas do novo registro, use os valores da próxima linha na tabela e selecione novamente **adicionar registro CNAME**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="5c5e8-227">Repita esse processo até ter criado todos os seis registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="5c5e8-228">Selecione **Atualizar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-3-5](../../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5c5e8-230">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="5c5e8-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5c5e8-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5c5e8-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c5e8-232">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5c5e8-233">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5c5e8-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5c5e8-235">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um  *único*  registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5c5e8-p111">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5c5e8-239">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5c5e8-241">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5c5e8-243">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5c5e8-245">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5c5e8-247">Escolha **Registro TXT** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-4-1](../../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="5c5e8-249">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-249">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-4-2](../../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="5c5e8-251">Nas caixas do novo registro, digite ou cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5c5e8-252">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-252">**Sub Domain**</span></span>|<span data-ttu-id="5c5e8-253">**Registro de Texto**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5c5e8-254">(Deixe este campo vazio.)</span><span class="sxs-lookup"><span data-stu-id="5c5e8-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5c5e8-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5c5e8-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5c5e8-256">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-BP-configure-4-3](../../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="5c5e8-258">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-258">Select **Update**.</span></span>
    
    ![CrazyDomains-BP-configure-4-4](../../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5c5e8-260">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="5c5e8-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5c5e8-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5c5e8-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5c5e8-p112">Para iniciar, acesse a sua página de domínios no usando [link](https://manage.crazydomains.com/members/domains/). Será solicitado que você faça logon primeiro.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-BP-configure-1-1](../../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5c5e8-265">Na seção **minha conta** , selecione **domínios**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-BP-configure-1-2](../../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5c5e8-267">Na página **nomes de domínio** , na seção **domínio** , selecione o nome do domínio que você está atualizando.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-BP-configure-1-3](../../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5c5e8-269">Na seção **configurações de DNS** , selecione o ícone de lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-BP-configure-1-4-1](../../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5c5e8-271">Selecione **adicionar registro**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-BP-configure-1-4-2](../../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5c5e8-273">Escolha **Registro SRV** na lista suspensa **Adicionar Registro:**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-BP-configure-5-1](../../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="5c5e8-275">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-275">Select **Add**.</span></span>
    
    ![CrazyDomains-BP-configure-5-2](../../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="5c5e8-277">Adicione o primeiro dos dois registros SRV.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5c5e8-278">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="5c5e8-279">**Tipo de Registro**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-279">**Record Type**</span></span>|<span data-ttu-id="5c5e8-280">**Subdomínio**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-280">**Sub Domain**</span></span>|<span data-ttu-id="5c5e8-281">**Prioridade**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-281">**Priority**</span></span>|<span data-ttu-id="5c5e8-282">**Espessura**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-282">**Weight**</span></span>|<span data-ttu-id="5c5e8-283">**Porta**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-283">**Port**</span></span>|<span data-ttu-id="5c5e8-284">**Destino**</span><span class="sxs-lookup"><span data-stu-id="5c5e8-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5c5e8-285">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="5c5e8-285">SRV Record</span></span>  <br/> |<span data-ttu-id="5c5e8-286">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="5c5e8-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="5c5e8-287">100</span><span class="sxs-lookup"><span data-stu-id="5c5e8-287">100</span></span>  <br/> |<span data-ttu-id="5c5e8-288">1</span><span class="sxs-lookup"><span data-stu-id="5c5e8-288">1</span></span>  <br/> |<span data-ttu-id="5c5e8-289">443</span><span class="sxs-lookup"><span data-stu-id="5c5e8-289">443</span></span>  <br/> |<span data-ttu-id="5c5e8-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c5e8-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5c5e8-291">Registro SRV</span><span class="sxs-lookup"><span data-stu-id="5c5e8-291">SRV Record</span></span>  <br/> |<span data-ttu-id="5c5e8-292">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="5c5e8-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5c5e8-293">100</span><span class="sxs-lookup"><span data-stu-id="5c5e8-293">100</span></span>  <br/> |<span data-ttu-id="5c5e8-294">1</span><span class="sxs-lookup"><span data-stu-id="5c5e8-294">1</span></span>  <br/> |<span data-ttu-id="5c5e8-295">5061</span><span class="sxs-lookup"><span data-stu-id="5c5e8-295">5061</span></span>  <br/> |<span data-ttu-id="5c5e8-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5c5e8-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-BP-configure-5-3](../../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="5c5e8-298">Selecione **adicionar registro SRV**.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-BP-configure-5-4](../../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="5c5e8-300">Adicione o outro registro SRV.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5c5e8-301">Nas caixas para o novo registro, use os valores da segunda linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="5c5e8-302">Selecione **Atualizar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="5c5e8-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-BP-configure-5-5](../../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="5c5e8-p113">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c5e8-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
