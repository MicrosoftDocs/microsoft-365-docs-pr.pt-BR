---
title: Criar registros DNS no Register.com para Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Register.com para a Microsoft.
ms.openlocfilehash: 8badcff89b2a8d8cc9901ef4f10c0a6b31de13d7
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629270"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="6a001-103">Criar registros DNS no Register.com para Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a001-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="6a001-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="6a001-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="6a001-105">Se você usa a Register.com como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="6a001-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="6a001-106">Estes são os registros principais a adicionar.</span><span class="sxs-lookup"><span data-stu-id="6a001-106">These are the main records to add.</span></span> <span data-ttu-id="6a001-107">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a001-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="6a001-108">Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="6a001-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="6a001-109">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a001-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="6a001-110">Adicionar os registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a001-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="6a001-111">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="6a001-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="6a001-112">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a001-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="6a001-113">Depois que você adicionar esses registros no Register.com, o domínio será configurado para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a001-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="6a001-114">Para saber mais sobre o webhosting e o DNS para sites com a Microsoft, confira [usar um site público com a Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="6a001-114">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a001-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6a001-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6a001-116">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="6a001-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6a001-117">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a001-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="6a001-118">Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="6a001-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="6a001-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="6a001-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="6a001-120">Antes de usar seu domínio com a Microsoft, precisamos garantir que você o tenha.</span><span class="sxs-lookup"><span data-stu-id="6a001-120">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="6a001-121">Sua capacidade de fazer logon em sua conta no registrador de domínios e criar o registro DNS comprova para a Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="6a001-121">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a001-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="6a001-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="6a001-124">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a001-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a001-125">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="6a001-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="6a001-126">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="6a001-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="6a001-127">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="6a001-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="6a001-128">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="6a001-129">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="6a001-130">Role para baixo até a seção **configurações técnicas avançadas** e selecione **editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="6a001-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="6a001-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="6a001-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="6a001-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="6a001-132">**Host Name**</span></span> <br/> |<span data-ttu-id="6a001-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="6a001-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="6a001-134">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="6a001-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="6a001-135">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="6a001-135">**Note:** This is an example.</span></span> <span data-ttu-id="6a001-136">Use o seu **destino específico ou aponte para** o valor de endereço aqui, a partir da tabela.</span><span class="sxs-lookup"><span data-stu-id="6a001-136">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="6a001-137">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="6a001-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="6a001-138">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="6a001-139">Na próxima página, selecione **continuar** novamente para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="6a001-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="6a001-140">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="6a001-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="6a001-141">Agora que você adicionou o registro no site do seu registrador de domínio, você voltará para a Microsoft e solicitará o registro.</span><span class="sxs-lookup"><span data-stu-id="6a001-141">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="6a001-142">Quando a Microsoft encontrar o registro TXT correto, seu domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="6a001-142">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="6a001-143">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="6a001-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="6a001-144">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="6a001-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="6a001-145">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="6a001-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="6a001-146">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6a001-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6a001-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6a001-148">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="6a001-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6a001-149">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a001-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="6a001-150">Adicionar um registro MX para que o email do seu domínio seja fornecido para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a001-150">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="6a001-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="6a001-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="6a001-152">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a001-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a001-153">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="6a001-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="6a001-154">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="6a001-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="6a001-155">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="6a001-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="6a001-156">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="6a001-157">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="6a001-158">Role até a seção **configurações técnicas avançadas** e, em seguida, selecione **editar registros de servidor de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="6a001-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selecione Editar registros de servidor de mensagens](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="6a001-160">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="6a001-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="6a001-161">(Escolha o valor **prioridade** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="6a001-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6a001-162">\*\*\*\*Nome do host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="6a001-163">\*\*\*\*Prioridade\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="6a001-164">\*\*\*\*Servidor de Email\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="6a001-165">Alta</span><span class="sxs-lookup"><span data-stu-id="6a001-165">High</span></span>  <br/> <span data-ttu-id="6a001-166">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="6a001-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="6a001-167">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6a001-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="6a001-168">**Observação:** Obtenha sua \< *chave* \> de domínio de sua conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a001-168">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="6a001-169">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="6a001-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar e colar o valor da tabela](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="6a001-171">Se houver outros registros MX já listados, escolha cada um desses registros a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="6a001-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="6a001-173">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-173">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="6a001-175">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="6a001-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="6a001-177">Adicionar os registros CNAME necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a001-177">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="6a001-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="6a001-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="6a001-179">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a001-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a001-180">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="6a001-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="6a001-181">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="6a001-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="6a001-182">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="6a001-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="6a001-183">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="6a001-184">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="6a001-185">Role até a seção **configurações técnicas avançadas** e, em seguida, selecione **editar registros de alias de domínio**.</span><span class="sxs-lookup"><span data-stu-id="6a001-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Selecione Editar registros de aliases de domínio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="6a001-187">Selecione **adicionar mais aliases de domínio**.</span><span class="sxs-lookup"><span data-stu-id="6a001-187">Select **Add more domain aliases**.</span></span>
    
    ![Selecione Adicionar mais aliases de domínios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="6a001-189">Adicione os registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="6a001-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="6a001-190">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6a001-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="6a001-191">\*\*\*\*Primeiro campo (sem rótulo)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="6a001-192">\*\*\*\*Pontos de\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="6a001-193">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="6a001-193">autodiscover</span></span>  <br/> |<span data-ttu-id="6a001-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="6a001-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="6a001-195">sip</span><span class="sxs-lookup"><span data-stu-id="6a001-195">sip</span></span>  <br/> |<span data-ttu-id="6a001-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6a001-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="6a001-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6a001-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="6a001-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6a001-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="6a001-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="6a001-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="6a001-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="6a001-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="6a001-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="6a001-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="6a001-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="6a001-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiar e colar os valores DNS da tabela](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="6a001-204">Depois de adicionar todos os registros CNAME necessários, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="6a001-206">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="6a001-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="6a001-208">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="6a001-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="6a001-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="6a001-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a001-210">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="6a001-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="6a001-211">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="6a001-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="6a001-212">Se você já tiver um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6a001-212">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="6a001-213">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="6a001-213">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="6a001-214">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a001-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a001-215">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="6a001-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="6a001-216">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="6a001-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="6a001-217">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="6a001-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="6a001-218">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="6a001-219">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="6a001-220">Role até a seção **configurações técnicas avançadas** e selecione **editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="6a001-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selecionar editar registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="6a001-222">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="6a001-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="6a001-223">\*\*\*\*Nome do Host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="6a001-224">\*\*\*\*Registro TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="6a001-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="6a001-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="6a001-226">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="6a001-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiar e colar os valores da tabela](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="6a001-228">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-228">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="6a001-230">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="6a001-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="6a001-232">Adicionar os dois registros SRV necessários para o Microsoft</span><span class="sxs-lookup"><span data-stu-id="6a001-232">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="6a001-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="6a001-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="6a001-234">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="6a001-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="6a001-p112">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="6a001-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="6a001-237">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="6a001-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="6a001-238">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="6a001-239">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="6a001-240">Role até a seção **configurações técnicas avançadas** e selecione **Editar Registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="6a001-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selecione Editar Registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="6a001-242">Adicione o primeiro dos dois registros SRV:</span><span class="sxs-lookup"><span data-stu-id="6a001-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="6a001-243">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="6a001-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="6a001-244">(Escolha o valor **prioridade** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="6a001-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="6a001-245">\*\*\*\*Serviço\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="6a001-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="6a001-247">\*\*\*\*Nome\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="6a001-248">\*\*\*\*Prioridade\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="6a001-249">\*\*\*\*Peso\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="6a001-250">\*\*\*\*Porta\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="6a001-251">\*\*\*\*Destino\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6a001-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="6a001-252">_sip</span><span class="sxs-lookup"><span data-stu-id="6a001-252">_sip</span></span>  <br/> |<span data-ttu-id="6a001-253">_tls</span><span class="sxs-lookup"><span data-stu-id="6a001-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="6a001-254">Alta</span><span class="sxs-lookup"><span data-stu-id="6a001-254">High</span></span>  <br/> |<span data-ttu-id="6a001-255">1</span><span class="sxs-lookup"><span data-stu-id="6a001-255">1</span></span>  <br/> |<span data-ttu-id="6a001-256">443</span><span class="sxs-lookup"><span data-stu-id="6a001-256">443</span></span>  <br/> |<span data-ttu-id="6a001-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6a001-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="6a001-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="6a001-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="6a001-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="6a001-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="6a001-260">Alta</span><span class="sxs-lookup"><span data-stu-id="6a001-260">High</span></span>  <br/> |<span data-ttu-id="6a001-261">1</span><span class="sxs-lookup"><span data-stu-id="6a001-261">1</span></span>  <br/> |<span data-ttu-id="6a001-262">5061</span><span class="sxs-lookup"><span data-stu-id="6a001-262">5061</span></span>  <br/> |<span data-ttu-id="6a001-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="6a001-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiar e colar os valores da tabela](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="6a001-265">Selecione **adicionar mais registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="6a001-265">Select **Add more SRV records**.</span></span>
    
    ![Selecione Adicionar mais registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="6a001-267">Adicione o segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="6a001-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="6a001-268">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="6a001-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="6a001-269">Após adicionar ambos os registros SRV, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="6a001-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="6a001-271">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="6a001-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="6a001-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="6a001-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="6a001-274">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="6a001-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="6a001-275">Se você estiver tendo problemas com o fluxo de emails ou com outros problemas após adicionar registros DNS, consulte [Localizar e corrigir problemas após adicionar seu domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6a001-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
