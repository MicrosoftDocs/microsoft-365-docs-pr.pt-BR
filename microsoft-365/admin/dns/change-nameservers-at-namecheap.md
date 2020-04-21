---
title: Alterar os nameservers para configurar o Microsoft com o Namecheap
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
ms.assetid: 84f467f6-28cf-40f0-94d0-a2a27ddfc2e7
description: 'Saiba como configurar seu domínio personalizado da Microsoft com o Namecheap se quiser que a Microsoft gerencie seus registros DNS. '
ms.openlocfilehash: 6fdec37e837c74666ada82af81d43faaa0a6d589
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629774"
---
# <a name="change-nameservers-to-set-up-microsoft-with-namecheap"></a><span data-ttu-id="a47d3-103">Alterar os nameservers para configurar o Microsoft com o Namecheap</span><span class="sxs-lookup"><span data-stu-id="a47d3-103">Change nameservers to set up Microsoft with Namecheap</span></span>

 <span data-ttu-id="a47d3-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="a47d3-105">Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="a47d3-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="a47d3-106">Se preferir, [gerencie todos os registros DNS da Microsoft em Namecheap](create-dns-records-at-namecheap.md).</span><span class="sxs-lookup"><span data-stu-id="a47d3-106">(If you prefer, you can [manage all your Microsoft DNS records at Namecheap](create-dns-records-at-namecheap.md).)</span></span>
  
    
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a47d3-107">Adicionar um registro TXT para verificação</span><span class="sxs-lookup"><span data-stu-id="a47d3-107">Add a TXT record for verification</span></span>

1. <span data-ttu-id="a47d3-108">Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="a47d3-108">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="a47d3-109">Você será solicitado a entrar e continuar.</span><span class="sxs-lookup"><span data-stu-id="a47d3-109">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a47d3-111">Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a47d3-111">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a47d3-113">Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-113">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a47d3-115">Selecione **DNS avançado**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-115">Select **Advanced DNS**.</span></span>
    
    ![Namecheap-BP-configure-1-4](../../media/05a4f0b9-1d27-448e-9954-2b23304c5f65.png)
  
5. <span data-ttu-id="a47d3-117">Na seção **registros de host** , selecione **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-117">In the **HOST RECORDS** section, select **ADD NEW RECORD**.</span></span>
    
    ![Namecheap-BP-configure-1-5](../../media/8849abfe-deb6-4f6a-b56d-e69be9a28b0f.png)
  
6. <span data-ttu-id="a47d3-119">Na lista suspensa **tipo** , selecione **registro txt**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-119">In the **Type** drop-down, select **TXT Record**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a47d3-120">O menu suspenso **tipo** aparece automaticamente quando você seleciona **Adicionar novo registro**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-120">The **Type** drop-down automatically appears when you select **ADD NEW RECORD**.</span></span>
  
    ![Namecheap-BP-Verify-1-1](../../media/a5b40973-19b5-4c32-8e1b-1521aa971836.png)
  
7. <span data-ttu-id="a47d3-122">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="a47d3-122">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="a47d3-123">(Escolha o valor **TTL** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="a47d3-123">(Choose the **TTL** value from the drop-down list.)</span></span> 
    
|<span data-ttu-id="a47d3-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a47d3-124">**Type**</span></span>|<span data-ttu-id="a47d3-125">**Host**</span><span class="sxs-lookup"><span data-stu-id="a47d3-125">**Host**</span></span>|<span data-ttu-id="a47d3-126">**Valor**</span><span class="sxs-lookup"><span data-stu-id="a47d3-126">**Value**</span></span>|<span data-ttu-id="a47d3-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a47d3-127">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a47d3-128">TXT</span><span class="sxs-lookup"><span data-stu-id="a47d3-128">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="a47d3-129">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a47d3-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a47d3-130">**Observação**: Este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="a47d3-130">**Note**: This is an example.</span></span> <span data-ttu-id="a47d3-131">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="a47d3-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a47d3-132">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="a47d3-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="a47d3-133">30 min</span><span class="sxs-lookup"><span data-stu-id="a47d3-133">30 min</span></span>  <br/> |
   
   ![Namecheap-BP-Verify-1-2](../../media/fe75c0fd-f85c-4bef-8068-edaf9779b7f1.png)
  
8. <span data-ttu-id="a47d3-135">Selecione o controle **salvar alterações** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a47d3-135">Select the **Save Changes** (check mark) control.</span></span> 
    
    ![Namecheap-BP-Verify-1-3](../../media/b48d2c67-66b5-4aa4-8e59-0c764f236fac.png)
  
9. <span data-ttu-id="a47d3-137">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="a47d3-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a47d3-138">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará uma pesquisa para o registro.</span><span class="sxs-lookup"><span data-stu-id="a47d3-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="a47d3-139">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="a47d3-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a47d3-140">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="a47d3-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a47d3-141">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="a47d3-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a47d3-142">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-142">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a47d3-143">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a47d3-p104">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a47d3-p104">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a47d3-147">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="a47d3-147">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="a47d3-148">Para concluir a configuração do seu domínio com a Microsoft, altere os registros NS do seu domínio no seu registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a47d3-148">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="a47d3-149">Isso configura a Microsoft para atualizar os registros DNS do domínio para você.</span><span class="sxs-lookup"><span data-stu-id="a47d3-149">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="a47d3-150">Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="a47d3-150">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="a47d3-151">Quando você alterar os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços associados atualmente ao seu domínio serão afetados.</span><span class="sxs-lookup"><span data-stu-id="a47d3-151">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="a47d3-152">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain* . com) começarão a ser iniciados pela Microsoft depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="a47d3-152">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="a47d3-153">Quando você concluir as etapas desta seção, os  *únicos*  nameservers que deverão estar listados são estes quatro: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  O procedimento a seguir mostra como excluir outros nameservers indesejados da lista, além de adicionar os nameservers  *corretos*  se ainda não estiverem na lista.</span><span class="sxs-lookup"><span data-stu-id="a47d3-153">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com >  The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="a47d3-154">Para começar, vá até a sua página de domínios no Namecheap usando [este link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span><span class="sxs-lookup"><span data-stu-id="a47d3-154">To get started, go to your domains page at Namecheap by using [this link](https://www.namecheap.com/myaccount/login.aspx?ReturnUrl=%2f).</span></span> <span data-ttu-id="a47d3-155">Você será solicitado a entrar e continuar.</span><span class="sxs-lookup"><span data-stu-id="a47d3-155">You'll be prompted to Sign in and Continue.</span></span>
    
    ![Namecheap-BP-configure-1-1](../../media/1827f9fc-4dc9-4f9d-a392-7817c47b00b3.png)
  
2. <span data-ttu-id="a47d3-157">Na página de **aterrissagem** , em **conta**, escolha **lista de domínios** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a47d3-157">On the **Landing** page, under **Account**, choose **Domain List** from the drop-down list.</span></span> 
    
    ![Namecheap-BP-configure-1-2](../../media/3f457d64-4589-422c-ae34-fc24b0e819eb.png)
  
3. <span data-ttu-id="a47d3-159">Na página **lista de domínios** , localize o nome do domínio que você deseja editar e, em seguida, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-159">On the **Domain List** page, find the name of the domain that you want to edit, and then select **Manage**.</span></span>
    
    ![Namecheap-BP-configure-1-3](../../media/fb2020d8-707c-4148-835e-304ac6244d66.png)
  
4. <span data-ttu-id="a47d3-161">Selecione **domínio**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-161">Select **Domain**.</span></span>
    
    ![Namecheap-BP-redelegar-1-1](../../media/59588406-794e-4ae4-8526-35e3111b5791.png)
  
5. <span data-ttu-id="a47d3-163">Encontre a seção **nameservers** e, em seguida, selecione **personalizado** na lista suspensa **Namecheap padrão** .</span><span class="sxs-lookup"><span data-stu-id="a47d3-163">Find the **NAMESERVERS** section, and then select **Custom** from the **Namecheap Default** drop-down list.</span></span> 
    
    ![Namecheap-BP-redelegar-1-2](../../media/7df56295-fdb3-472f-9442-13f780c2c93e.png)
  
6. <span data-ttu-id="a47d3-165">Dependendo se já existem ou não nameservers listados na página exibida agora, continue com um dos dois procedimentos a seguir.</span><span class="sxs-lookup"><span data-stu-id="a47d3-165">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures.</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="a47d3-166">Se NÃO houver nameservers listados</span><span class="sxs-lookup"><span data-stu-id="a47d3-166">If there are NO nameservers already listed</span></span>
<span data-ttu-id="a47d3-167"><a name="BKMK_ProcedureWithOUT"> </a></span><span class="sxs-lookup"><span data-stu-id="a47d3-167"><a name="BKMK_ProcedureWithOUT"> </a></span></span>

1. <span data-ttu-id="a47d3-168">Selecione **Adicionar nameserver** duas vezes para adicionar duas novas linhas.</span><span class="sxs-lookup"><span data-stu-id="a47d3-168">Select **ADD NAMESERVER** twice to add two new rows.</span></span>
    
    ![Namecheap-BP-redelegar-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
2. <span data-ttu-id="a47d3-170">Nas caixas **nameserver** , digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a47d3-170">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="a47d3-171">**Nameserver 1**</span><span class="sxs-lookup"><span data-stu-id="a47d3-171">**Nameserver 1**</span></span> <br/> |<span data-ttu-id="a47d3-172">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-172">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a47d3-173">**Nameserver 2**</span><span class="sxs-lookup"><span data-stu-id="a47d3-173">**Nameserver 2**</span></span> <br/> |<span data-ttu-id="a47d3-174">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-174">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a47d3-175">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="a47d3-175">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="a47d3-176">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-176">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a47d3-177">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="a47d3-177">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="a47d3-178">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-178">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-redelegar-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
3. <span data-ttu-id="a47d3-180">Selecione o controle **salvar** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a47d3-180">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-redelegar-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="a47d3-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a47d3-182">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a47d3-183">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="a47d3-183">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="a47d3-184">Se HOUVER nameservers listados</span><span class="sxs-lookup"><span data-stu-id="a47d3-184">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="a47d3-p109">Siga estas etapas  *somente*  se você tiver outros nameservers existentes, além dos quatro nameservers  *corretos*  . Ou seja, exclua  *somente*  nameservers atuais que  *não*  sejam denominados como **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** ou **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="a47d3-p109">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="a47d3-187">Se houver outros nameservers listados nas caixas **nameserver** , exclua cada um selecionando-o e pressionando a tecla **delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="a47d3-187">If there are any other nameservers listed in the **Nameserver** boxes, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Namecheap-BP-redelegar-1-4](../../media/3270603a-c4f4-40b7-acad-733d56e2f53c.png)
  
2. <span data-ttu-id="a47d3-189">Selecione **Adicionar nameserver** duas vezes para adicionar duas novas linhas.</span><span class="sxs-lookup"><span data-stu-id="a47d3-189">Select **ADD NAMESERVER** twice to add two new rows.</span></span> 
    
    ![Namecheap-BP-redelegar-1-3-1](../../media/e8816bf5-bb59-49d5-bfca-43e502242dc3.png)
  
3. <span data-ttu-id="a47d3-191">Nas caixas **nameserver** , digite ou copie e cole os valores da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a47d3-191">In the **Nameserver** boxes, type or copy and paste the values from the following table.</span></span>
 
    
|||
|:-----|:-----|
|<span data-ttu-id="a47d3-192">**Servidor de nomes 1**</span><span class="sxs-lookup"><span data-stu-id="a47d3-192">**Name Server 1**</span></span> <br/> |<span data-ttu-id="a47d3-193">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-193">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a47d3-194">**Servidor de nomes 2**</span><span class="sxs-lookup"><span data-stu-id="a47d3-194">**Name Server 2**</span></span> <br/> |<span data-ttu-id="a47d3-195">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-195">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a47d3-196">**Nameserver 3**</span><span class="sxs-lookup"><span data-stu-id="a47d3-196">**Nameserver 3**</span></span> <br/> |<span data-ttu-id="a47d3-197">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-197">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="a47d3-198">**Nameserver 4**</span><span class="sxs-lookup"><span data-stu-id="a47d3-198">**Nameserver 4**</span></span> <br/> |<span data-ttu-id="a47d3-199">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="a47d3-199">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Namecheap-BP-redelegar-1-3-2](../../media/21d681b7-4f96-4e96-ac27-9534c388537c.png)
  
4. <span data-ttu-id="a47d3-201">Selecione o controle **salvar** (marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="a47d3-201">Select the **Save** (check mark) control.</span></span> 
    
    ![Namecheap-BP-redelegar-1-5](../../media/07aaf1e5-c24f-4c51-bfe0-f99868b3bf35.png)
  
> [!NOTE]
> <span data-ttu-id="a47d3-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="a47d3-203">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a47d3-204">Em seguida, seu email da Microsoft e outros serviços serão configurados para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="a47d3-204">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
