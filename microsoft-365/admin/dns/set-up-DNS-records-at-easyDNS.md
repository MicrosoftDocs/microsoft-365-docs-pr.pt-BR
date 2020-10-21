---
title: Criar registros DNS no easyDNS para Microsoft
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
- MET150
- MOE150
ms.assetid: 446babfe-2e08-4cc2-bbfb-c05b854933ac
description: Saiba como verificar seu domínio e configurar registros DNS para email, Skype for Business Online e outros serviços em easyDNS para a Microsoft.
ms.openlocfilehash: 4909a02ec56fc9720a2636e822da0339e89bccf8
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645546"
---
# <a name="create-dns-records-at-easydns-for-microsoft"></a><span data-ttu-id="ffb7f-103">Criar registros DNS no easyDNS para Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffb7f-103">Create DNS records at easyDNS for Microsoft</span></span>

<span data-ttu-id="ffb7f-104">[Verifique as perguntas frequentes sobre domínios ](../setup/domains-faq.md) se não encontrar o que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-104">[Check the Domains FAQ ](../setup/domains-faq.md) if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ffb7f-105">Você precisará adicionar todos os seguintes registros DNS no site do registrador para rotear emails para a Microsoft, usar seu domínio para o Teams e o Skype for Business e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-105">You'll need to add all of the following DNS records at your registrar's website to route mail to Microsoft, use your domain for Teams and Skype for Business, and so on.</span></span>
  
<span data-ttu-id="ffb7f-106">Observação: os registros SRV não estão disponíveis no momento em todos os pacotes de serviço do easyDNS.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-106">NOTE: SRV Records are currently NOT available under all easyDNS service packages.</span></span> <span data-ttu-id="ffb7f-107">Talvez seja necessário atualizar para um nível de serviço superior com o easyDNS para adicionar registros SRV necessários para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-107">You may need to upgrade to a higher service level with easyDNS to add SRV records which are required for Skype for Business.</span></span>
  
## <a name="verify-that-you-own-the-domain-with-a-txt-record"></a><span data-ttu-id="ffb7f-108">Verificar se você é o proprietário do domínio com um registro TXT</span><span class="sxs-lookup"><span data-stu-id="ffb7f-108">Verify that you own the domain with a TXT record</span></span>

1. <span data-ttu-id="ffb7f-109">Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-109">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="ffb7f-110">No cabeçalho **todos os domínios** , selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-110">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="ffb7f-111">No cabeçalho **registros txt** , selecione o botão Editar (ícone de chave inglesa).</span><span class="sxs-lookup"><span data-stu-id="ffb7f-111">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="ffb7f-112">Insira os seguintes registros nos campos de texto:</span><span class="sxs-lookup"><span data-stu-id="ffb7f-112">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="ffb7f-113">**Host**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-113">**Host**</span></span>|<span data-ttu-id="ffb7f-114">**Text**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-114">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="ffb7f-115">MS = msXXXXXXXX (use o valor fornecido na página domínios do centro de administração)</span><span class="sxs-lookup"><span data-stu-id="ffb7f-115">MS=msXXXXXXXX (Use the value provided to you on the admin center Domains page)</span></span>  <br/> |
   
5. <span data-ttu-id="ffb7f-116">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-116">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="ffb7f-117">Verifique se o registro está correto e, em seguida, selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-117">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
7. <span data-ttu-id="ffb7f-118">Aguarde alguns minutos antes de continuar, para que o registro que você acabou de criar possa se propagar pela Internet e seja detectado pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-118">Wait a few minutes before you continue, so that the record you just created can propagate across the Internet and be detected by Microsoft.</span></span>
    
8. <span data-ttu-id="ffb7f-119">Agora que você adicionou o registro no site do seu registrador de domínios, retorne à Microsoft e solicite o registro.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-119">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
    
9. <span data-ttu-id="ffb7f-120">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-120">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
10. <span data-ttu-id="ffb7f-121">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-121">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
11. <span data-ttu-id="ffb7f-122">Na página **configuração** , selecione **Iniciar configuração.**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-122">On the **Setup** page, select **Start setup.**</span></span>
    
12. <span data-ttu-id="ffb7f-123">Na página **Verificar domínio**, clique em **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-123">On the **Verify domain** page, select **Verify**.</span></span> 
    
## <a name="add-an-mx-record-to-route-email-to-microsoft"></a><span data-ttu-id="ffb7f-124">Adicionar um registro MX para rotear emails para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffb7f-124">Add an MX record to route email to Microsoft</span></span>

1. <span data-ttu-id="ffb7f-125">Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-125">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="ffb7f-126">No cabeçalho **todos os domínios** , selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-126">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="ffb7f-127">No cabeçalho **registros MX** , selecione o botão Editar (ícone de chave inglesa).</span><span class="sxs-lookup"><span data-stu-id="ffb7f-127">Under the **MX records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="ffb7f-128">Insira os seguintes registros nos campos de texto:</span><span class="sxs-lookup"><span data-stu-id="ffb7f-128">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="ffb7f-129">**EMAIL PARA A ZONA**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-129">**MAIL FOR ZONE**</span></span>|<span data-ttu-id="ffb7f-130">**SERVIDOR DE EMAIL**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-130">**MAIL SERVER**</span></span>|<span data-ttu-id="ffb7f-131">**PREF**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-131">**PREF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="ffb7f-132">\<domain-key\>. mail.protection.outlook.com (obter seu \<domain-key\> valor na página domínios do centro de administração)</span><span class="sxs-lookup"><span data-stu-id="ffb7f-132">\<domain-key\>.mail.protection.outlook.com (Get your \<domain-key\> value from the admin center Domains page)</span></span>  <br/> |<span data-ttu-id="ffb7f-133">,0</span><span class="sxs-lookup"><span data-stu-id="ffb7f-133">0</span></span>  <br/> |
   
2. <span data-ttu-id="ffb7f-134">Se você quiser salvar seus outros registros MX para fins de backup, copie-os para baixo em algum lugar.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-134">If you want to save your other MX records for backup purposes, copy them down somewhere.</span></span> <span data-ttu-id="ffb7f-135">Antes de prosseguir, remova todos os outros registros MX aqui.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-135">Before moving on, remove all other MX records here.</span></span>
    
5. <span data-ttu-id="ffb7f-136">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-136">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="ffb7f-137">Verifique se o registro está correto e, em seguida, selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-137">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-required-cname-records"></a><span data-ttu-id="ffb7f-138">Adicionar os registros CNAME necessários</span><span class="sxs-lookup"><span data-stu-id="ffb7f-138">Add the required CNAME records</span></span>

1. <span data-ttu-id="ffb7f-139">Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-139">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="ffb7f-140">No cabeçalho **todos os domínios** , selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-140">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="ffb7f-141">No título **registros CNAME/alias** , selecione o botão Editar (ícone de uma chave inglesa).</span><span class="sxs-lookup"><span data-stu-id="ffb7f-141">Under the **CNAME/Alias records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="ffb7f-142">Insira os seguintes registros nos campos de texto:</span><span class="sxs-lookup"><span data-stu-id="ffb7f-142">Enter the following records in the text fields:</span></span>


    |<span data-ttu-id="ffb7f-143">**HOST**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-143">**HOST**</span></span>|<span data-ttu-id="ffb7f-144">**Endereço (deve terminar com um ".")**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-144">**Address (Must end with a ".")**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ffb7f-145">autodiscover</span><span class="sxs-lookup"><span data-stu-id="ffb7f-145">autodiscover</span></span>  <br/> |<span data-ttu-id="ffb7f-146">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-146">autodiscover.outlook.com.</span></span>  <br/> |
    |<span data-ttu-id="ffb7f-147">sip</span><span class="sxs-lookup"><span data-stu-id="ffb7f-147">sip</span></span>  <br/> |<span data-ttu-id="ffb7f-148">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-148">sipdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="ffb7f-149">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ffb7f-149">lyncdiscover</span></span>  <br/> |<span data-ttu-id="ffb7f-150">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-150">webdir.online.lync.com.</span></span>  <br/> |
    |<span data-ttu-id="ffb7f-151">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="ffb7f-151">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="ffb7f-152">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-152">enterpriseregistration.windows.net.</span></span>  <br/> |
    |<span data-ttu-id="ffb7f-153">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="ffb7f-153">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="ffb7f-154">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-154">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> |
   
5. <span data-ttu-id="ffb7f-155">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-155">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="ffb7f-156">Verifique se o registro está correto e, em seguida, selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-156">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="ffb7f-157">Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail</span><span class="sxs-lookup"><span data-stu-id="ffb7f-157">Add a TXT record for SPF to help prevent email spam</span></span>

1. <span data-ttu-id="ffb7f-158">Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-158">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="ffb7f-159">No cabeçalho **todos os domínios** , selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-159">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="ffb7f-160">No cabeçalho **registros txt** , selecione o botão Editar (ícone de chave inglesa).</span><span class="sxs-lookup"><span data-stu-id="ffb7f-160">Under the **TXT records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="ffb7f-161">Insira os seguintes registros nos campos de texto:</span><span class="sxs-lookup"><span data-stu-id="ffb7f-161">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="ffb7f-162">**Host**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-162">**Host**</span></span>|<span data-ttu-id="ffb7f-163">**Text**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-163">**Text**</span></span>|
    |:-----|:-----|
    |@  <br/> |<span data-ttu-id="ffb7f-164">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="ffb7f-164">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> |
   
5. <span data-ttu-id="ffb7f-165">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-165">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="ffb7f-166">Verifique se o registro está correto e, em seguida, selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-166">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="ffb7f-167">Adicionar os dois registros SRV necessários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffb7f-167">Add the two SRV records that are required for Microsoft</span></span>

<span data-ttu-id="ffb7f-168">Observação: os registros SRV não estão disponíveis no momento no easyDNS ' domínio mais nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-168">NOTE: SRV Records are currently NOT available under easyDNS' Domain Plus service level.</span></span> <span data-ttu-id="ffb7f-169">Talvez seja necessário atualizar para um nível de serviço superior com o easyDNS para adicionar registros SRV</span><span class="sxs-lookup"><span data-stu-id="ffb7f-169">You may need to upgrade to a higher service level with easyDNS to add SRV records</span></span> 
  
1. <span data-ttu-id="ffb7f-170">Vá para [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) e faça logon com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-170">Go to [https://cp.easydns.com/manage/domains/](https://cp.easydns.com/manage/domains/) and log in with your credentials.</span></span> 
    
2. <span data-ttu-id="ffb7f-171">No cabeçalho **todos os domínios** , selecione **DNS.**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-171">Under the **all domains** heading, select **dns.**</span></span>
    
3. <span data-ttu-id="ffb7f-172">No cabeçalho **Registros SRV** , selecione o botão Editar (ícone de chave inglesa).</span><span class="sxs-lookup"><span data-stu-id="ffb7f-172">Under the **SRV records** heading, select the edit button (wrench icon).</span></span> 
    
4. <span data-ttu-id="ffb7f-173">Insira os seguintes registros nos campos de texto:</span><span class="sxs-lookup"><span data-stu-id="ffb7f-173">Enter the following records in the text fields:</span></span>
    
    |<span data-ttu-id="ffb7f-174">**SERVIÇO**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-174">**SERVICE**</span></span>|<span data-ttu-id="ffb7f-175">**PROTOCOLO**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-175">**PROTO**</span></span>|<span data-ttu-id="ffb7f-176">**HOST**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-176">**HOST**</span></span>|<span data-ttu-id="ffb7f-177">**PRI**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-177">**PRI**</span></span>|<span data-ttu-id="ffb7f-178">**WGT**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-178">**WGT**</span></span>|<span data-ttu-id="ffb7f-179">**PORTA**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-179">**PORT**</span></span>|<span data-ttu-id="ffb7f-180">**TARGET (deve terminar com um ".")**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-180">**TARGET(Must end with a ".")**</span></span>|<span data-ttu-id="ffb7f-181">**TTL**</span><span class="sxs-lookup"><span data-stu-id="ffb7f-181">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="ffb7f-182">_sip</span><span class="sxs-lookup"><span data-stu-id="ffb7f-182">_sip</span></span>  <br/> |<span data-ttu-id="ffb7f-183">TLS</span><span class="sxs-lookup"><span data-stu-id="ffb7f-183">TLS</span></span>  <br/> |@  <br/> |<span data-ttu-id="ffb7f-184">100</span><span class="sxs-lookup"><span data-stu-id="ffb7f-184">100</span></span>  <br/> |<span data-ttu-id="ffb7f-185">1</span><span class="sxs-lookup"><span data-stu-id="ffb7f-185">1</span></span>  <br/> |<span data-ttu-id="ffb7f-186">443</span><span class="sxs-lookup"><span data-stu-id="ffb7f-186">443</span></span>  <br/> |<span data-ttu-id="ffb7f-187">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-187">sipdir.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ffb7f-188">1800</span><span class="sxs-lookup"><span data-stu-id="ffb7f-188">1800</span></span>  <br/> |
    |<span data-ttu-id="ffb7f-189">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="ffb7f-189">_sipfederationtls</span></span>  <br/> |<span data-ttu-id="ffb7f-190">TCP</span><span class="sxs-lookup"><span data-stu-id="ffb7f-190">TCP</span></span>  <br/> |@  <br/> |<span data-ttu-id="ffb7f-191">100</span><span class="sxs-lookup"><span data-stu-id="ffb7f-191">100</span></span>  <br/> |<span data-ttu-id="ffb7f-192">1</span><span class="sxs-lookup"><span data-stu-id="ffb7f-192">1</span></span>  <br/> |<span data-ttu-id="ffb7f-193">5061</span><span class="sxs-lookup"><span data-stu-id="ffb7f-193">5061</span></span>  <br/> |<span data-ttu-id="ffb7f-194">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-194">sipfed.online.lync.com.</span></span>  <br/> |<span data-ttu-id="ffb7f-195">1800</span><span class="sxs-lookup"><span data-stu-id="ffb7f-195">1800</span></span>  <br/> |
   
5. <span data-ttu-id="ffb7f-196">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-196">Select **NEXT**.</span></span> 
    
6. <span data-ttu-id="ffb7f-197">Verifique se o registro está correto e, em seguida, selecione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ffb7f-197">Check to make sure the record is correct, and then select **CONFIRM**.</span></span> 
    

