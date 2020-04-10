---
title: Criar registros DNS no site Register.com para o Office 365
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
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em Register.com para o Office 365.
ms.openlocfilehash: d89e1843a7c914843c7e9d5c41582878e138473a
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211093"
---
# <a name="create-dns-records-at-registercom-for-office-365"></a><span data-ttu-id="c76a2-103">Criar registros DNS no site Register.com para o Office 365</span><span class="sxs-lookup"><span data-stu-id="c76a2-103">Create DNS records at Register.com for Office 365</span></span>

 <span data-ttu-id="c76a2-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="c76a2-105">Se você usa a Register.com como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="c76a2-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="c76a2-106">Estes são os registros principais a adicionar.</span><span class="sxs-lookup"><span data-stu-id="c76a2-106">These are the main records to add.</span></span> <span data-ttu-id="c76a2-107">Siga as etapas abaixo ou [assista ao vídeo](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c76a2-107">Follow the steps below or [watch the video](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
- [<span data-ttu-id="c76a2-108">Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="c76a2-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="c76a2-109">Adicionar um registro MX para que o email do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="c76a2-109">Add an MX record so email for your domain will come to Office 365</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-office-365)
    
- [<span data-ttu-id="c76a2-110">Adicionar os registros CNAME necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="c76a2-110">Add the CNAME records that are required for Office 365</span></span>](#add-the-cname-records-that-are-required-for-office-365)
    
- [<span data-ttu-id="c76a2-111">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="c76a2-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="c76a2-112">Adicionar os dois registros SRV necessários para o Office 365</span><span class="sxs-lookup"><span data-stu-id="c76a2-112">Add the two SRV records that are required for Office 365</span></span>](#add-the-two-srv-records-that-are-required-for-office-365)
    
<span data-ttu-id="c76a2-113">Depois que você adicionar esses registros ao Register.com, o domínio será configurado para funcionar com os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c76a2-113">After you add these records at Register.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="c76a2-114">Para saber mais sobre hospedagem na Web e DNS para sites com o Office 365, confira [Usar um site público com o Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="c76a2-114">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c76a2-115">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c76a2-115">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c76a2-116">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="c76a2-116">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c76a2-117">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c76a2-117">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="c76a2-118">Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="c76a2-118">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="c76a2-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="c76a2-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="c76a2-p103">Antes de usar o seu domínio com o Office 365, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro DNS prova ao Office 365 que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="c76a2-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c76a2-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="c76a2-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="c76a2-124">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c76a2-124">Follow the steps below or [watch the video (start at 0:44)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="c76a2-125">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c76a2-125">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c76a2-126">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="c76a2-126">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c76a2-127">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-127">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c76a2-128">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-128">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c76a2-129">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-129">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c76a2-130">Role para baixo até a seção **configurações técnicas avançadas** e selecione **editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-130">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="c76a2-131">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="c76a2-131">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="c76a2-132">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="c76a2-132">**Host Name**</span></span> <br/> |<span data-ttu-id="c76a2-133">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="c76a2-133">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="c76a2-134">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="c76a2-134">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="c76a2-135">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="c76a2-135">**Note:** This is an example.</span></span> <span data-ttu-id="c76a2-136">Use seu valor específico de **Destinos ou Pontos de Endereçamento** aqui, da tabela no Office 365.</span><span class="sxs-lookup"><span data-stu-id="c76a2-136">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="c76a2-137">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="c76a2-137">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="c76a2-138">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-138">Select **Continue**.</span></span>
    
8. <span data-ttu-id="c76a2-139">Na próxima página, selecione **continuar** novamente para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="c76a2-139">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="c76a2-140">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="c76a2-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="c76a2-141">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Office 365 e solicite que o Office 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="c76a2-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="c76a2-142">Quando o Office 365 encontrar o registro TXT correto, o domínio será verificado.</span><span class="sxs-lookup"><span data-stu-id="c76a2-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="c76a2-143">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="c76a2-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="c76a2-144">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="c76a2-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="c76a2-145">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="c76a2-146">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c76a2-147">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c76a2-147">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c76a2-148">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="c76a2-148">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c76a2-149">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c76a2-149">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="c76a2-150">Adicionar um registro MX para que o e-mail do domínio vá para o Office 365</span><span class="sxs-lookup"><span data-stu-id="c76a2-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="c76a2-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="c76a2-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="c76a2-152">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c76a2-152">Follow the steps below or [watch the video (start at 3:32)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="c76a2-153">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c76a2-153">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c76a2-154">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="c76a2-154">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c76a2-155">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-155">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c76a2-156">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-156">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c76a2-157">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-157">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c76a2-158">Role até a seção **configurações técnicas avançadas** e, em seguida, selecione **editar registros de servidor de mensagens**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-158">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selecione Editar registros de servidor de mensagens](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="c76a2-160">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="c76a2-160">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="c76a2-161">(Escolha o valor **prioridade** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="c76a2-161">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c76a2-162">\*\*\*\*Nome do host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-162">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="c76a2-163">\*\*\*\*Prioridade\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-163">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="c76a2-164">\*\*\*\*Servidor de Email\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-164">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="c76a2-165">Alto</span><span class="sxs-lookup"><span data-stu-id="c76a2-165">High</span></span>  <br/> <span data-ttu-id="c76a2-166">Para saber mais sobre prioridade, confira [O que é prioridade MX?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span><span class="sxs-lookup"><span data-stu-id="c76a2-166">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="c76a2-167">*\<chave-do-domínio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c76a2-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="c76a2-168">**Observação:** Obtenha a sua \<*chave-de-domínio*\> através da conta do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c76a2-168">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> <br> [<span data-ttu-id="c76a2-169">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="c76a2-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar e colar o valor da tabela](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="c76a2-171">Se houver outros registros MX já listados, escolha cada um desses registros a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="c76a2-171">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="c76a2-173">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-173">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="c76a2-175">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c76a2-175">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="c76a2-177">Adicionar os registros CNAME necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="c76a2-177">Add the CNAME records that are required for Office 365</span></span>
<span data-ttu-id="c76a2-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="c76a2-178"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="c76a2-179">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c76a2-179">Follow the steps below or [watch the video (start at 4:23)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="c76a2-180">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c76a2-180">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c76a2-181">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="c76a2-181">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c76a2-182">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-182">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c76a2-183">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-183">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c76a2-184">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-184">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c76a2-185">Role até a seção **configurações técnicas avançadas** e, em seguida, selecione **editar registros de alias de domínio**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-185">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Selecione Editar registros de aliases de domínio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="c76a2-187">Selecione **adicionar mais aliases de domínio**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-187">Select **Add more domain aliases**.</span></span>
    
    ![Selecione Adicionar mais aliases de domínios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="c76a2-189">Adicione os registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="c76a2-189">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="c76a2-190">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c76a2-190">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="c76a2-191">\*\*\*\*Primeiro campo (sem rótulo)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-191">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="c76a2-192">\*\*\*\*Pontos de\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-192">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="c76a2-193">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="c76a2-193">autodiscover</span></span>  <br/> |<span data-ttu-id="c76a2-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="c76a2-194">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c76a2-195">sip</span><span class="sxs-lookup"><span data-stu-id="c76a2-195">sip</span></span>  <br/> |<span data-ttu-id="c76a2-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c76a2-196">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c76a2-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="c76a2-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="c76a2-198">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c76a2-198">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="c76a2-199">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="c76a2-199">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="c76a2-200">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="c76a2-200">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c76a2-201">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="c76a2-201">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="c76a2-202">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="c76a2-202">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiar e colar os valores DNS da tabela](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="c76a2-204">Depois de adicionar todos os registros CNAME necessários, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-204">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="c76a2-206">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c76a2-206">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="c76a2-208">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="c76a2-208">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="c76a2-209"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="c76a2-209"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c76a2-210">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="c76a2-210">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="c76a2-211">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="c76a2-211">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="c76a2-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="c76a2-212">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="c76a2-213">Em vez disso, adicione os valores necessários do Office 365 ao registro atual, de modo que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="c76a2-213">Instead, add the required Office 365 values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="c76a2-214">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c76a2-214">Follow the steps below or [watch the video (start at 5:12)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="c76a2-215">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/).</span><span class="sxs-lookup"><span data-stu-id="c76a2-215">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/).</span></span> <span data-ttu-id="c76a2-216">Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="c76a2-216">You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c76a2-217">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-217">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c76a2-218">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-218">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c76a2-219">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-219">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c76a2-220">Role até a seção **configurações técnicas avançadas** e selecione **editar registros txt (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-220">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selecionar editar registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="c76a2-222">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="c76a2-222">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="c76a2-223">\*\*\*\*Nome do Host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-223">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="c76a2-224">\*\*\*\*Registro TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-224">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="c76a2-225">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="c76a2-225">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="c76a2-226">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="c76a2-226">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiar e colar os valores da tabela](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="c76a2-228">Selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-228">Select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="c76a2-230">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c76a2-230">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="c76a2-232">Adicionar os dois registros SRV necessários do Office 365</span><span class="sxs-lookup"><span data-stu-id="c76a2-232">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="c76a2-233"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="c76a2-233"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="c76a2-234">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="c76a2-234">Follow the steps below or [watch the video (start at 5:55)](https://support.office.com/article/Video-Create-DNS-records-at-Register-com-for-Office-365-7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="c76a2-p112">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="c76a2-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="c76a2-237">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-237">Select **Domains**.</span></span>
    
3. <span data-ttu-id="c76a2-238">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-238">Select **Manage**.</span></span>
    
4. <span data-ttu-id="c76a2-239">Localize a linha que contém o nome do domínio que você deseja modificar; e, em seguida, nessa linha, selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-239">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="c76a2-240">Role até a seção **configurações técnicas avançadas** e selecione **Editar Registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-240">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selecione Editar Registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="c76a2-242">Adicione o primeiro dos dois registros SRV:</span><span class="sxs-lookup"><span data-stu-id="c76a2-242">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="c76a2-243">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c76a2-243">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="c76a2-244">(Escolha o valor **prioridade** na lista suspensa.)</span><span class="sxs-lookup"><span data-stu-id="c76a2-244">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="c76a2-245">\*\*\*\*Serviço\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-245">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="c76a2-246">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-246">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="c76a2-247">\*\*\*\*Nome\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-247">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="c76a2-248">\*\*\*\*Prioridade\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-248">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="c76a2-249">\*\*\*\*Peso\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-249">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="c76a2-250">\*\*\*\*Porta\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-250">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="c76a2-251">\*\*\*\*Destino\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c76a2-251">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="c76a2-252">_sip</span><span class="sxs-lookup"><span data-stu-id="c76a2-252">_sip</span></span>  <br/> |<span data-ttu-id="c76a2-253">_tls</span><span class="sxs-lookup"><span data-stu-id="c76a2-253">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="c76a2-254">Alta</span><span class="sxs-lookup"><span data-stu-id="c76a2-254">High</span></span>  <br/> |<span data-ttu-id="c76a2-255">1</span><span class="sxs-lookup"><span data-stu-id="c76a2-255">1</span></span>  <br/> |<span data-ttu-id="c76a2-256">443</span><span class="sxs-lookup"><span data-stu-id="c76a2-256">443</span></span>  <br/> |<span data-ttu-id="c76a2-257">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c76a2-257">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="c76a2-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="c76a2-258">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="c76a2-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="c76a2-259">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="c76a2-260">Alta</span><span class="sxs-lookup"><span data-stu-id="c76a2-260">High</span></span>  <br/> |<span data-ttu-id="c76a2-261">1</span><span class="sxs-lookup"><span data-stu-id="c76a2-261">1</span></span>  <br/> |<span data-ttu-id="c76a2-262">5061</span><span class="sxs-lookup"><span data-stu-id="c76a2-262">5061</span></span>  <br/> |<span data-ttu-id="c76a2-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="c76a2-263">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiar e colar os valores da tabela](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="c76a2-265">Selecione **adicionar mais registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-265">Select **Add more SRV records**.</span></span>
    
    ![Selecione Adicionar mais registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="c76a2-267">Adicione o segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="c76a2-267">Add the second SRV record:</span></span>
    
    <span data-ttu-id="c76a2-268">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="c76a2-268">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="c76a2-269">Após adicionar ambos os registros SRV, selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="c76a2-269">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Selecione continuar](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="c76a2-271">Na próxima página, selecione **continuar** novamente para confirmar e salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c76a2-271">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione continuar](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="c76a2-273">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="c76a2-273">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="c76a2-274">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="c76a2-274">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="c76a2-275">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas após alterar o nome de domínio ou registros DNS no Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c76a2-275">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
