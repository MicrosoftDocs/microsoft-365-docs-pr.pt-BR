---
title: Criar registros DNS no Register.com para a Microsoft
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
ms.assetid: 55bd8c38-3316-48ae-a368-4959b2c1684e
description: Aprenda a verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços Register.com para a Microsoft.
ms.openlocfilehash: 439b96ef7ad2fd70b94c3945519d4fa270e43fd2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910049"
---
# <a name="create-dns-records-at-registercom-for-microsoft"></a><span data-ttu-id="ef17d-103">Criar registros DNS no Register.com para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef17d-103">Create DNS records at Register.com for Microsoft</span></span>

 <span data-ttu-id="ef17d-104">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ef17d-105">Se você usa a Register.com como provedor de hospedagem DNS, siga as etapas neste artigo para verificar o domínio e configurar registros DNS para o Skype for Business Online, email e outros serviços.</span><span class="sxs-lookup"><span data-stu-id="ef17d-105">If Register.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="ef17d-106">Estes são os registros principais a adicionar.</span><span class="sxs-lookup"><span data-stu-id="ef17d-106">These are the main records to add.</span></span> <span data-ttu-id="ef17d-107">Siga as etapas abaixo ou [assista ao vídeo](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ef17d-107">Follow the steps below or [watch the video](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
- [<span data-ttu-id="ef17d-108">Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="ef17d-108">Add a TXT record at Register.com to verify that you own the domain</span></span>](#add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain)
    
- [<span data-ttu-id="ef17d-109">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef17d-109">Add an MX record so email for your domain will come to Microsoft</span></span>](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)
    
- [<span data-ttu-id="ef17d-110">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef17d-110">Add the CNAME records that are required for Microsoft</span></span>](#add-the-cname-records-that-are-required-for-microsoft)
    
- [<span data-ttu-id="ef17d-111">Adicionar registro TXT à SPF para ajudar a evitar spam de email</span><span class="sxs-lookup"><span data-stu-id="ef17d-111">Add a TXT record for SPF to help prevent email spam</span></span>](#add-a-txt-record-for-spf-to-help-prevent-email-spam)

- [<span data-ttu-id="ef17d-112">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef17d-112">Add the two SRV records that are required for Microsoft</span></span>](#add-the-two-srv-records-that-are-required-for-microsoft)
    
<span data-ttu-id="ef17d-113">Depois de adicionar esses registros Register.com, seu domínio será definido para funcionar com os serviços da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef17d-113">After you add these records at Register.com, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="ef17d-114">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ef17d-114">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ef17d-115">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="ef17d-115">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ef17d-116">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef17d-116">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-at-registercom-to-verify-that-you-own-the-domain"></a><span data-ttu-id="ef17d-117">Adicionar um registro TXT ao Register.com para verificar o proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="ef17d-117">Add a TXT record at Register.com to verify that you own the domain</span></span>
<span data-ttu-id="ef17d-118"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="ef17d-118"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="ef17d-p103">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="ef17d-p103">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef17d-p104">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="ef17d-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="ef17d-123">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ef17d-123">Follow the steps below or [watch the video (start at 0:44)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ef17d-p105">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="ef17d-p105">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ef17d-126">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-126">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ef17d-127">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-127">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ef17d-128">Encontre a linha que contém o nome do domínio que você deseja modificar; e, nessa linha, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-128">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ef17d-129">Role para baixo até **a seção Configurações Técnicas Avançadas** e selecione **Editar Registros TXT (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-129">Scroll down to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
6. <span data-ttu-id="ef17d-130">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="ef17d-130">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="ef17d-131">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="ef17d-131">**Host Name**</span></span> <br/> |<span data-ttu-id="ef17d-132">**TXT Record**</span><span class="sxs-lookup"><span data-stu-id="ef17d-132">**TXT Record**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="ef17d-133">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="ef17d-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="ef17d-134">**Observação**: esse é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="ef17d-134">**Note:** This is an example.</span></span> <span data-ttu-id="ef17d-135">Use aqui seu valor específico de **Destino ou Pontos de Endereçamento**, retirado da tabela.</span><span class="sxs-lookup"><span data-stu-id="ef17d-135">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="ef17d-136">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="ef17d-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="ef17d-137">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-137">Select **Continue**.</span></span>
    
8. <span data-ttu-id="ef17d-138">Na próxima página, selecione **Continuar novamente** para confirmar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="ef17d-138">On the next page, select **Continue** again to confirm your changes.</span></span> 
    
9. <span data-ttu-id="ef17d-139">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="ef17d-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="ef17d-140">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="ef17d-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="ef17d-141">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="ef17d-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="ef17d-142">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="ef17d-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="ef17d-143">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="ef17d-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="ef17d-144">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-144">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="ef17d-145">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-145">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ef17d-146">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ef17d-146">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ef17d-147">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="ef17d-147">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ef17d-148">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef17d-148">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="ef17d-149">Adicione um registro MX para que o email do domínio vá para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef17d-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="ef17d-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="ef17d-150"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="ef17d-151">Siga as etapas abaixo ou [assista ao vídeo (inicia em 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ef17d-151">Follow the steps below or [watch the video (start at 3:32)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ef17d-p108">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="ef17d-p108">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ef17d-154">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-154">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ef17d-155">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-155">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ef17d-156">Encontre a linha que contém o nome do domínio que você deseja modificar; e, nessa linha, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-156">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ef17d-157">Role até a **seção Configurações Técnicas Avançadas** e selecione **Editar Registros do Exchanger de Email.**</span><span class="sxs-lookup"><span data-stu-id="ef17d-157">Scroll to the **Advanced Technical Settings** section, and then select **Edit Mail Exchanger Records**.</span></span>
    
    ![Selecionar Editar Registros do Exchanger de Email](../../media/366b96a1-9147-4bbb-9f8f-50856466cc61.png)
  
6. <span data-ttu-id="ef17d-159">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="ef17d-159">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="ef17d-160">(Escolha o **valor Priority** na listada.)</span><span class="sxs-lookup"><span data-stu-id="ef17d-160">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ef17d-161">\*\*\*\*Nome do host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-161">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="ef17d-162">\*\*\*\*Prioridade\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-162">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="ef17d-163">\*\*\*\*Servidor de Email\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-163">\*\*\*\*Mail Server\*\*\*\*</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ef17d-164">Alta</span><span class="sxs-lookup"><span data-stu-id="ef17d-164">High</span></span>  <br/> <span data-ttu-id="ef17d-165">Para saber mais sobre prioridade, confira [O que é prioridade MX?](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="ef17d-165">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> | <span data-ttu-id="ef17d-166">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ef17d-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <br/><span data-ttu-id="ef17d-167">**Observação:** Obtenha a sua \<*domain-key*\> através da sua conta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef17d-167">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> <br> [<span data-ttu-id="ef17d-168">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="ef17d-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiar e colar o valor da tabela](../../media/a1a15a14-c3dc-45dc-adcd-90fdb3f7455d.png)
  
7. <span data-ttu-id="ef17d-170">Se houver outros registros MX já listados, escolha cada um desses registros a serem excluídos.</span><span class="sxs-lookup"><span data-stu-id="ef17d-170">If there were any other MX records already listed, select each of those records to be deleted.</span></span>
    
    ![Select each record to delete](../../media/0708d03e-346f-4ae7-8cc4-01589efc00ce.png)
  
8. <span data-ttu-id="ef17d-172">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-172">Select **Continue**.</span></span>
    
    ![Selecione Continuar](../../media/6ef6ce01-ce21-4e3c-8209-4aa9a3dd4b76.png)
  
9. <span data-ttu-id="ef17d-174">Na próxima página, selecione **Continuar novamente** para confirmar e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="ef17d-174">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione Continuar](../../media/adba4a60-bf61-44fc-9ad9-360e66f8a2ee.png)
  
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef17d-176">Adicionar os registros CNAME necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef17d-176">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="ef17d-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ef17d-177"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="ef17d-178">Siga as etapas abaixo ou [assista ao vídeo (inicia em 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ef17d-178">Follow the steps below or [watch the video (start at 4:23)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ef17d-p109">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="ef17d-p109">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ef17d-181">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-181">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ef17d-182">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-182">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ef17d-183">Encontre a linha que contém o nome do domínio que você deseja modificar; e, nessa linha, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-183">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ef17d-184">Role até a **seção Configurações Técnicas Avançadas** e selecione **Editar Registros de Aliases de Domínio.**</span><span class="sxs-lookup"><span data-stu-id="ef17d-184">Scroll to the **Advanced Technical Settings** section, and then select **Edit Domain Aliases Records**.</span></span>
    
    ![Selecione Editar Registros de Aliases de Domínio](../../media/9fbc31ed-d67c-4828-8bd4-b51068f1e0ca.png)
  
6. <span data-ttu-id="ef17d-186">Selecione **Adicionar mais aliases de domínio.**</span><span class="sxs-lookup"><span data-stu-id="ef17d-186">Select **Add more domain aliases**.</span></span>
    
    ![Selecione Adicionar mais aliases de domínios](../../media/b787505f-5566-4879-8552-13f9e89cbf6b.png)
  
7. <span data-ttu-id="ef17d-188">Adicione os registros CNAME.</span><span class="sxs-lookup"><span data-stu-id="ef17d-188">Add the required CNAME records.</span></span>
    
    <span data-ttu-id="ef17d-189">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef17d-189">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="ef17d-190">\*\*\*\*Primeiro campo (sem rótulo)\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-190">\*\*\*\*First field (unlabeled)\*\*\*\*</span></span>|<span data-ttu-id="ef17d-191">\*\*\*\*Pontos de\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-191">\*\*\*\*Points to\*\*\*\*</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ef17d-192">descoberta automática</span><span class="sxs-lookup"><span data-stu-id="ef17d-192">autodiscover</span></span>  <br/> |<span data-ttu-id="ef17d-193">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="ef17d-193">autodiscover.outlook.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ef17d-194">sip</span><span class="sxs-lookup"><span data-stu-id="ef17d-194">sip</span></span>  <br/> |<span data-ttu-id="ef17d-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef17d-195">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ef17d-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ef17d-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ef17d-197">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef17d-197">webdir.online.lync.com</span></span> <br/>  <br/> |
    |<span data-ttu-id="ef17d-198">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ef17d-198">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ef17d-199">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="ef17d-199">enterpriseregistration.windows.net</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ef17d-200">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ef17d-200">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ef17d-201">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="ef17d-201">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/>  <br/> |
   
     ![Copiar e colar os valores DNS da tabela](../../media/0e2b36b2-8a0b-4019-addf-301763f9a626.png)
  
8. <span data-ttu-id="ef17d-203">Quando você tiver adicionado todos os registros CNAME necessários, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-203">When you have added all of the CNAME records that you need, select **Continue**.</span></span>
    
    ![Selecione Continuar](../../media/1942612b-338a-48fa-a45d-2d5434516723.png)
  
9. <span data-ttu-id="ef17d-205">Na próxima página, selecione **Continuar novamente** para confirmar e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="ef17d-205">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione Continuar](../../media/3342b570-0633-49c5-9175-5cc8e4a67b53.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ef17d-207">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="ef17d-207">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="ef17d-208"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="ef17d-208"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef17d-209">Não é possível ter mais de um registro TXT para SPF para um domínio.</span><span class="sxs-lookup"><span data-stu-id="ef17d-209">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="ef17d-210">Se o seu domínio possuir mais de um registro SPF, ocorrerão erros de email, bem como problemas na entrega e na classificação de spam.</span><span class="sxs-lookup"><span data-stu-id="ef17d-210">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="ef17d-211">Se você já possui um registro SPF para seu domínio, não crie um novo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ef17d-211">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="ef17d-212">Em vez disso, adicione os valores necessários da Microsoft ao registro atual para que você tenha um único registro SPF que inclua os dois conjuntos de valores.</span><span class="sxs-lookup"><span data-stu-id="ef17d-212">Instead, add the required Microsoft values to the current record so that you have a single SPF record that includes both sets of values.</span></span>  
  
<span data-ttu-id="ef17d-213">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ef17d-213">Follow the steps below or [watch the video (start at 5:12)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ef17d-p111">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="ef17d-p111">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ef17d-216">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-216">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ef17d-217">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-217">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ef17d-218">Encontre a linha que contém o nome do domínio que você deseja modificar; e, nessa linha, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-218">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ef17d-219">Role até a **seção Configurações Técnicas Avançadas** e selecione **Editar Registros TXT (SPF)**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-219">Scroll to the **Advanced Technical Settings** section, and then select **Edit TXT Records (SPF)**.</span></span>
    
    ![Selecione Editar Registros TXT (SPF)](../../media/c917577a-8b3a-4210-ab6e-776e84f926d0.png)
  
6. <span data-ttu-id="ef17d-221">Nas caixas do novo registro, digite ou copie e cole os valores da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="ef17d-221">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="ef17d-222">\*\*\*\*Nome do Host\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-222">\*\*\*\*Host Name\*\*\*\*</span></span>|<span data-ttu-id="ef17d-223">\*\*\*\*Registro TXT\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-223">\*\*\*\*TXT Record\*\*\*\*</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="ef17d-224">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ef17d-224">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="ef17d-225">**Observação:** é recomendável copiar e colar essa entrada para que o espaçamento permaneça correto.</span><span class="sxs-lookup"><span data-stu-id="ef17d-225">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>  |
   
     ![Copiar e colar os valores da tabela](../../media/b1dc5036-c13c-4306-b1e3-5a38a74643b7.png)
  
7. <span data-ttu-id="ef17d-227">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-227">Select **Continue**.</span></span>
    
    ![Selecione Continuar](../../media/08250c98-1a86-48a8-ad94-f96cf338126b.png)
  
8. <span data-ttu-id="ef17d-229">Na próxima página, selecione **Continuar novamente** para confirmar e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="ef17d-229">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione Continuar](../../media/56be3b0a-dc71-471c-9be3-6ab927296f67.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ef17d-231">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ef17d-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="ef17d-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="ef17d-232"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="ef17d-233">Siga as etapas abaixo ou [assista ao vídeo (inicia em 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span><span class="sxs-lookup"><span data-stu-id="ef17d-233">Follow the steps below or [watch the video (start at 5:55)](https://support.microsoft.com/office/7448dd9e-c0e7-4d5e-a7e9-f0e4715433c4).</span></span>
  
1. <span data-ttu-id="ef17d-p112">Para iniciar, vá até a sua página de domínios em Register.com usando [este link](https://www.register.com/myaccount/). Você será solicitado a entrar.</span><span class="sxs-lookup"><span data-stu-id="ef17d-p112">To get started, go to your domains page at Register.com by using [this link](https://www.register.com/myaccount/). You'll be prompted to sign in.</span></span>
    
2. <span data-ttu-id="ef17d-236">Escolha **Domínios**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-236">Select **Domains**.</span></span>
    
3. <span data-ttu-id="ef17d-237">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-237">Select **Manage**.</span></span>
    
4. <span data-ttu-id="ef17d-238">Encontre a linha que contém o nome do domínio que você deseja modificar; e, nessa linha, selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-238">Find the row that contains the name of the domain that you want to modify; and then, in that row, select **Manage**.</span></span>
    
5. <span data-ttu-id="ef17d-239">Role até a **seção Configurações Técnicas Avançadas** e selecione **Editar Registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-239">Scroll to the **Advanced Technical Settings** section, and then select **Edit SRV Records**.</span></span>
    
    ![Selecione Editar Registros SRV](../../media/73c149ae-f0d6-460e-880a-7e04a995acc3.png)
  
6. <span data-ttu-id="ef17d-241">Adicione o primeiro dos dois registros SRV:</span><span class="sxs-lookup"><span data-stu-id="ef17d-241">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="ef17d-242">Nas caixas do novo registro, digite ou copie e cole os valores da primeira linha da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ef17d-242">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="ef17d-243">(Escolha o **valor Priority** na listada.)</span><span class="sxs-lookup"><span data-stu-id="ef17d-243">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="ef17d-244">\*\*\*\*Serviço\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-244">\*\*\*\*Service\*\*\*\*</span></span>|<span data-ttu-id="ef17d-245">\*\*\*\*Proto\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-245">\*\*\*\*Proto\*\*\*\*</span></span>|<span data-ttu-id="ef17d-246">\*\*\*\*Nome\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-246">\*\*\*\*Name\*\*\*\*</span></span>|<span data-ttu-id="ef17d-247">\*\*\*\*Prioridade\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-247">\*\*\*\*Priority\*\*\*\*</span></span>|<span data-ttu-id="ef17d-248">\*\*\*\*Peso\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-248">\*\*\*\*Weight\*\*\*\*</span></span>|<span data-ttu-id="ef17d-249">\*\*\*\*Porta\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-249">\*\*\*\*Port\*\*\*\*</span></span>|<span data-ttu-id="ef17d-250">\*\*\*\*Destino\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ef17d-250">\*\*\*\*Target\*\*\*\*</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ef17d-251">_sip</span><span class="sxs-lookup"><span data-stu-id="ef17d-251">_sip</span></span>  <br/> |<span data-ttu-id="ef17d-252">_tls</span><span class="sxs-lookup"><span data-stu-id="ef17d-252">_tls</span></span>  <br/> |@  <br/> |<span data-ttu-id="ef17d-253">Alta</span><span class="sxs-lookup"><span data-stu-id="ef17d-253">High</span></span>  <br/> |<span data-ttu-id="ef17d-254">1</span><span class="sxs-lookup"><span data-stu-id="ef17d-254">1</span></span>  <br/> |<span data-ttu-id="ef17d-255">443</span><span class="sxs-lookup"><span data-stu-id="ef17d-255">443</span></span>  <br/> |<span data-ttu-id="ef17d-256">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef17d-256">sipdir.online.lync.com</span></span>  <br/>  <br/> |
    |<span data-ttu-id="ef17d-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ef17d-257">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ef17d-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="ef17d-258">_tcp</span></span>  <br/> |@  <br/> |<span data-ttu-id="ef17d-259">Alta</span><span class="sxs-lookup"><span data-stu-id="ef17d-259">High</span></span>  <br/> |<span data-ttu-id="ef17d-260">1</span><span class="sxs-lookup"><span data-stu-id="ef17d-260">1</span></span>  <br/> |<span data-ttu-id="ef17d-261">5061</span><span class="sxs-lookup"><span data-stu-id="ef17d-261">5061</span></span>  <br/> |<span data-ttu-id="ef17d-262">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ef17d-262">sipfed.online.lync.com</span></span>  <br/>  <br/> |
   
    ![Copiar e colar os valores da tabela](../../media/71304c81-5845-4a8f-b969-d9efc8721184.png)
  
7. <span data-ttu-id="ef17d-264">Selecione **Adicionar mais registros SRV**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-264">Select **Add more SRV records**.</span></span>
    
    ![Selecione Adicionar mais registros SRV](../../media/823c6bd2-4af7-4079-bf8c-8d35a5c6730f.png)
  
8. <span data-ttu-id="ef17d-266">Adicione o segundo registro SRV:</span><span class="sxs-lookup"><span data-stu-id="ef17d-266">Add the second SRV record:</span></span>
    
    <span data-ttu-id="ef17d-267">Digite ou copie e cole os valores da segunda linha da tabela acima nas caixas do segundo registro.</span><span class="sxs-lookup"><span data-stu-id="ef17d-267">Type or copy and paste the values from the second row of the table above into the boxes for the second record.</span></span>
    
9. <span data-ttu-id="ef17d-268">Quando você tiver adicionado ambos os registros SRV, selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="ef17d-268">When you have added both of the SRV records, select **Continue**.</span></span>
    
    ![Selecione Continuar](../../media/008b255a-42d3-442d-83ea-3ffcb7c8fc5d.png)
  
10. <span data-ttu-id="ef17d-270">Na próxima página, selecione **Continuar novamente** para confirmar e salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="ef17d-270">On the next page, select **Continue** again to confirm and save your changes.</span></span> 
    
    ![Selecione Continuar](../../media/b4166e3d-7e4b-41ef-b616-747e95aefc37.png)
  
> [!NOTE]
> <span data-ttu-id="ef17d-272">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="ef17d-272">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="ef17d-273">Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="ef17d-273">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="ef17d-274">Se você tiver problemas com o fluxo de e-mails ou de outro tipo após adicionar os registros DNS, consulte [Localizar e corrigir problemas ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef17d-274">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
