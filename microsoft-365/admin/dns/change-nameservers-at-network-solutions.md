---
title: Alterar os nameservers para configurar a Microsoft com soluções de rede
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
ms.assetid: d4ba60f3-4e1c-4180-99bd-250b8955be2a
description: 'Saiba como configurar seu domínio personalizado da Microsoft com soluções de rede se quiser que a Microsoft gerencie seus registros DNS. '
ms.openlocfilehash: 04817ca24b13b4c138986df3875b6d397100fffd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658423"
---
# <a name="change-nameservers-to-set-up-microsoft-with-network-solutions"></a><span data-ttu-id="8c7da-103">Alterar os nameservers para configurar a Microsoft com soluções de rede</span><span class="sxs-lookup"><span data-stu-id="8c7da-103">Change nameservers to set up Microsoft with Network Solutions</span></span>

 <span data-ttu-id="8c7da-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span>
  
<span data-ttu-id="8c7da-105">Siga estas instruções se quiser que a Microsoft gerencie seus registros DNS para você.</span><span class="sxs-lookup"><span data-stu-id="8c7da-105">Follow these instructions if you want Microsoft to manage your DNS records for you.</span></span> <span data-ttu-id="8c7da-106">Se preferir, gerencie todos os registros DNS da Microsoft na [Network Solutions.](create-dns-records-at-network-solutions.md)</span><span class="sxs-lookup"><span data-stu-id="8c7da-106">(If you prefer, you can [manage all your Microsoft DNS records at Network Solutions](create-dns-records-at-network-solutions.md).)</span></span>
  
    
## <a name="add-a-txt-record-at-network-solutions-to-verify-that-you-own-the-domain"></a><span data-ttu-id="8c7da-107">Adicionar um registro TXT na Network Solutions para verificar o proprietário do domínio</span><span class="sxs-lookup"><span data-stu-id="8c7da-107">Add a TXT record at Network Solutions to verify that you own the domain</span></span>

<span data-ttu-id="8c7da-p102">Antes de usar o seu domínio com a Microsoft, precisamos verificar se você é o proprietário dele. A capacidade de entrar na conta do seu registrador de domínios e criar o registro de DNS prova à Microsoft que você é o proprietário do domínio.</span><span class="sxs-lookup"><span data-stu-id="8c7da-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c7da-p103">Esse registro é usado exclusivamente para confirmar se você é o proprietário do domínio; ele não afeta mais nada. É possível excluí-lo mais tarde, se desejar.</span><span class="sxs-lookup"><span data-stu-id="8c7da-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="8c7da-112">Siga as etapas abaixo ou [assista ao vídeo (inicia em 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span><span class="sxs-lookup"><span data-stu-id="8c7da-112">Follow the steps below or [watch the video (start at 0:47)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
1. <span data-ttu-id="8c7da-p104">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it). Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="8c7da-p104">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it). You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8c7da-115">Antes de selecionar o **botão Logon,** primeiro escolha Gerenciar Meus Nomes de **Domínio** na lista de logon **em:** lista drop-down.</span><span class="sxs-lookup"><span data-stu-id="8c7da-115">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span>
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8c7da-117">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="8c7da-117">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8c7da-119">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-119">Select **Edit DNS**.</span></span>
    
    ![Selecionar Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8c7da-121">Selecione **Gerenciar Registros DNS Avançados.**</span><span class="sxs-lookup"><span data-stu-id="8c7da-121">Select **Manage Advanced DNS Records**.</span></span>
    
    <span data-ttu-id="8c7da-122">(Pode ser necessário rolar para baixo.)</span><span class="sxs-lookup"><span data-stu-id="8c7da-122">(You may have to scroll down.)</span></span>
    
    ![Selecionar Gerenciar Registros DNS Avançados](../../media/fd2956d6-eec3-47ea-b60a-266bab14f51f.png)
  
5. <span data-ttu-id="8c7da-124">Role para baixo até **a seção Texto (Registros TXT)** e selecione **Editar Registros TXT.**</span><span class="sxs-lookup"><span data-stu-id="8c7da-124">Scroll down to the **Text (TXT Records)** section, and then select **Edit TXT Records**.</span></span>
    
    ![Selecionar Editar Registros TXT](../../media/240a01d6-750a-4da6-8554-641b571e4b71.png)
  
6. <span data-ttu-id="8c7da-126">Nas caixas do novo registro, digite ou copie e cole os valores na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="8c7da-126">In the boxes for the new record, type or copy and paste the values in the following table.</span></span>
    
|<span data-ttu-id="8c7da-127">**Host**</span><span class="sxs-lookup"><span data-stu-id="8c7da-127">**Host**</span></span>|<span data-ttu-id="8c7da-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8c7da-128">**TTL**</span></span>|<span data-ttu-id="8c7da-129">**Texto**</span><span class="sxs-lookup"><span data-stu-id="8c7da-129">**Text**</span></span>|
|:-----|:-----|:-----|
|@  <br/> <span data-ttu-id="8c7da-130">(The system will change this value to **@ (None)** when you save the record.)</span><span class="sxs-lookup"><span data-stu-id="8c7da-130">(The system will change this value to **@ (None)** when you save the record.)</span></span>  <br/> |<span data-ttu-id="8c7da-131">3600</span><span class="sxs-lookup"><span data-stu-id="8c7da-131">3600</span></span>  <br/> |<span data-ttu-id="8c7da-132">MS = ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8c7da-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8c7da-133">**Observação:** este é um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8c7da-133">**Note**: This is an example.</span></span> <span data-ttu-id="8c7da-134">Use seu valor específico de **Destino ou Pontos de Endereçamento** aqui, retirado da tabela no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8c7da-134">Use your specific **Destination or Points to Address** value here, from the table in Microsoft 365.</span></span>           [<span data-ttu-id="8c7da-135">Como localizo isto?</span><span class="sxs-lookup"><span data-stu-id="8c7da-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)
   
    
   ![Digite ou colar valores nas caixas do novo registro](../../media/8a76daab-b6ff-4c82-ba68-192b24fbb934.png)
  
7. <span data-ttu-id="8c7da-137">Selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-137">Select **Continue**.</span></span>
    
    ![Selecionar Continuar](../../media/89e7fb38-b4d9-4949-a1bb-d0dd10b361e0.png)
  
8. <span data-ttu-id="8c7da-139">Selecione **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-139">Select **Save Changes**.</span></span>
    
    ![Selecionar Salvar Alterações](../../media/bd4d7cd0-c8a3-497a-b080-cfd5a5c60dc5.png)
  
9. <span data-ttu-id="8c7da-141">Aguarde alguns minutos antes de prosseguir para que o registro que você acabou de criar possa ser atualizado na Internet.</span><span class="sxs-lookup"><span data-stu-id="8c7da-141">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8c7da-142">Agora que você adicionou o registro no site do seu registrador de domínios, retorne ao Microsoft 365 e solicite que o Microsoft 365 procure o registro.</span><span class="sxs-lookup"><span data-stu-id="8c7da-142">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="8c7da-143">Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.</span><span class="sxs-lookup"><span data-stu-id="8c7da-143">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8c7da-144">No centro do administrador da Microsoft, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="8c7da-144">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8c7da-145">Na página **Domínios**, clique no domínio que você está verificando.</span><span class="sxs-lookup"><span data-stu-id="8c7da-145">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8c7da-146">Na página **Configuração**, clique em **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-146">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8c7da-147">Na página **Verificar domínio**, marque **Verificar**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-147">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8c7da-p106">Normalmente, são necessários cerca de 15 minutos para que as alterações de DNS entrem em vigor. Mas, às vezes, pode ser necessário mais tempo para atualizar uma alteração feita no sistema DNS da Internet. Se você tiver problemas com o fluxo de emails ou de outro tipo após adicionar os registros DNS, consulte [Solucionar problemas após alterar o nome de domínio ou registros DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8c7da-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8c7da-151">Alterar os registros de nameserver (NS) de seu domínio</span><span class="sxs-lookup"><span data-stu-id="8c7da-151">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="8c7da-152">Para concluir a configuração do domínio com a Microsoft, altere os registros NS do seu domínio no registrador de domínios para apontar para os servidores de nomes primários e secundários da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8c7da-152">To complete setting up your domain with Microsoft, you change your domain's NS records at your domain registrar to point to the Microsoft primary and secondary name servers.</span></span> <span data-ttu-id="8c7da-153">Isso configura a Microsoft para atualizar os registros DNS do domínio para você.</span><span class="sxs-lookup"><span data-stu-id="8c7da-153">This sets up Microsoft to update the domain's DNS records for you.</span></span> <span data-ttu-id="8c7da-154">Todos os registros são adicionados para que os seus emails, o Skype for Business Online e os sites públicos funcionem com o seu domínio e você fique com tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="8c7da-154">We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8c7da-155">Quando você altera os registros NS do seu domínio para apontar para os servidores de nomes da Microsoft, todos os serviços atualmente associados ao seu domínio são afetados.</span><span class="sxs-lookup"><span data-stu-id="8c7da-155">When you change your domain's NS records to point to the Microsoft name servers, all the services that are currently associated with your domain are affected.</span></span> <span data-ttu-id="8c7da-156">Por exemplo, todos os emails enviados para seu domínio (como rob@ *your_domain*  .com) começarão a chegar na Microsoft depois que você fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="8c7da-156">For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Microsoft after you make this change.</span></span>
  
<span data-ttu-id="8c7da-157">Pronto para alterar seus registros NS para que a Microsoft possa configurar seu domínio?</span><span class="sxs-lookup"><span data-stu-id="8c7da-157">Ready to change your NS records so Microsoft can set up your domain?</span></span> <span data-ttu-id="8c7da-158">Siga as etapas abaixo ou [assista ao vídeo (inicia em 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span><span class="sxs-lookup"><span data-stu-id="8c7da-158">Follow the steps below or [watch the video (start at 2:23)](https://support.microsoft.com/office/69b092e3-c026-4d19-a7d0-16cdb2d8b261).</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="8c7da-159">Quando você tiver concluído as etapas  nesta seção, os únicos nameservers que devem estar listados são estes quatro: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** e **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-159">When you have completed the steps in this section, the  *only*  nameservers that should be listed are these four: **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, and **ns4.bdm.microsoftonline.com**.</span></span> <span data-ttu-id="8c7da-160">O procedimento a seguir mostra como excluir outros nameservers indesejados da lista, além de adicionar os nameservers  *corretos*  se ainda não estiverem na lista.</span><span class="sxs-lookup"><span data-stu-id="8c7da-160">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the  *correct*  nameservers if they are not already in the list.</span></span> 
  
1. <span data-ttu-id="8c7da-161">Para iniciar, vá até a página do seu domínio em Network Solutions, usando [este link](https://www.networksolutions.com/manage-it).</span><span class="sxs-lookup"><span data-stu-id="8c7da-161">To get started, go to your domains page at Network Solutions by using [this link](https://www.networksolutions.com/manage-it).</span></span> <span data-ttu-id="8c7da-162">Você será solicitado a fazer o logon.</span><span class="sxs-lookup"><span data-stu-id="8c7da-162">You'll be prompted to log in.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8c7da-163">Antes de selecionar o **botão Logon,** primeiro escolha Gerenciar Meus Nomes de **Domínio** na lista de logon **em:** lista drop-down.</span><span class="sxs-lookup"><span data-stu-id="8c7da-163">Before you select the **Login** button, first choose **Manage My Domain Names** in the **Log In to:** drop-down list.</span></span> 
  
    ![Escolha Gerenciar Meus Nomes de Domínio e entre no Network Solutions](../../media/fda7d4a1-9445-4086-be9c-87c6983ef2aa.png)
  
2. <span data-ttu-id="8c7da-165">Selecione a caixa de seleção ao lado do nome do domínio que você está modificando.</span><span class="sxs-lookup"><span data-stu-id="8c7da-165">Select the check box next to the name of the domain that you are modifying.</span></span>
    
    ![Marque a caixa de seleção do domínio](../../media/2c13d2ba-4a31-44da-812c-2cc90900a183.png)
  
3. <span data-ttu-id="8c7da-167">Selecione **Editar DNS**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-167">Select **Edit DNS**.</span></span>
    
    ![Selecionar Editar DNS](../../media/9d7c269f-48d1-442c-9d7b-63bd384a36a9.png)
  
4. <span data-ttu-id="8c7da-169">Selecione **Mover DNS**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-169">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-1](../../media/e57a30f3-63d5-4bcb-84c6-c8be21c261a2.png)
  
5. <span data-ttu-id="8c7da-171">Dependendo se há ou não nameservers já listados na página exibida agora, continue para um destes dois procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8c7da-171">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="8c7da-172">Se **NÃO HOUVER** nameservers listados, [Se NÃO houver nameservers listados](#if-there-are-no-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="8c7da-172">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="8c7da-173">Se **HOUVER** nameservers listados, [Se HOUVER nameservers listados](#if-there-are-nameservers-already-listed).</span><span class="sxs-lookup"><span data-stu-id="8c7da-173">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="8c7da-174">Se NÃO houver nameservers listados</span><span class="sxs-lookup"><span data-stu-id="8c7da-174">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="8c7da-175">Na página **Domínios,** na seção Especificar Servidores **de** Nomes de Domínio, selecione **Adicionar Mais Servidores de Nomes.**</span><span class="sxs-lookup"><span data-stu-id="8c7da-175">On the **Domains** page, in the **Specify Domain Name Servers** section, select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
2. <span data-ttu-id="8c7da-177">Na página **Nomes de Domínio**, digite ou copie e cole os valores de nameserver da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8c7da-177">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="8c7da-178">**Servidor de nomes 1**</span><span class="sxs-lookup"><span data-stu-id="8c7da-178">**Name Server 1**</span></span> <br/> |<span data-ttu-id="8c7da-179">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-179">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8c7da-180">**Servidor de nomes 2**</span><span class="sxs-lookup"><span data-stu-id="8c7da-180">**Name Server 2**</span></span> <br/> |<span data-ttu-id="8c7da-181">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-181">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8c7da-182">**Servidor de nomes 2**</span><span class="sxs-lookup"><span data-stu-id="8c7da-182">**Name Server 2**</span></span> <br/> |<span data-ttu-id="8c7da-183">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-183">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8c7da-184">**Servidor de nomes 2**</span><span class="sxs-lookup"><span data-stu-id="8c7da-184">**Name Server 2**</span></span> <br/> |<span data-ttu-id="8c7da-185">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-185">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
3. <span data-ttu-id="8c7da-187">Selecione **Mover DNS**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-187">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
4. <span data-ttu-id="8c7da-189">Selecione **Salvar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-189">Select **Save Changes**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="8c7da-191">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8c7da-191">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8c7da-192">Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="8c7da-192">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="8c7da-193">Se HOUVER nameservers listados</span><span class="sxs-lookup"><span data-stu-id="8c7da-193">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="8c7da-p113">Siga estas etapas  *somente*  se você tiver outros nameservers existentes, além dos quatro nameservers  *corretos*  . Ou seja, exclua  *somente*  nameservers atuais que  *não*  sejam denominados como **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com** ou **ns4.bdm.microsoftonline.com**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-p113">Follow these steps  *only*  if you have existing nameservers other than the four  *correct*  nameservers. (That is, delete  *only*  any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span>
  
1. <span data-ttu-id="8c7da-196">Se houver outros nameservers listados, exclua cada um deles, selecionando-os e pressionando a tecla **Delete** no teclado.</span><span class="sxs-lookup"><span data-stu-id="8c7da-196">If there are any other nameservers listed, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span>
    
    ![NetworkSolutions-BP-Redelegate-1-5](../../media/eeb8ad22-bf4a-43a8-b97a-f09c3654d89b.png)
  
2. <span data-ttu-id="8c7da-198">Selecione **Adicionar mais servidores de nomes.**</span><span class="sxs-lookup"><span data-stu-id="8c7da-198">Select **Add More Name Servers**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-1](../../media/57e22ef1-ac88-4d4a-bc8e-058023255dfd.png)
  
3. <span data-ttu-id="8c7da-200">Na página **Nomes de Domínio**, digite ou copie e cole os valores de nameserver da tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8c7da-200">On the **Domain Names** page, type or copy and paste the nameserver values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="8c7da-201">**Servidor de nomes 1**</span><span class="sxs-lookup"><span data-stu-id="8c7da-201">**Name Server 1**</span></span> <br/> |<span data-ttu-id="8c7da-202">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-202">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8c7da-203">**Servidor de nomes 2**</span><span class="sxs-lookup"><span data-stu-id="8c7da-203">**Name Server 2**</span></span> <br/> |<span data-ttu-id="8c7da-204">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-204">ns2.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8c7da-205">**Servidor de Nomes 3**</span><span class="sxs-lookup"><span data-stu-id="8c7da-205">**Name Server 3**</span></span> <br/> |<span data-ttu-id="8c7da-206">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-206">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="8c7da-207">**Servidor de Nomes 4**</span><span class="sxs-lookup"><span data-stu-id="8c7da-207">**Name Server 4**</span></span> <br/> |<span data-ttu-id="8c7da-208">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="8c7da-208">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    
![NetworkSolutionsBP-Redelegate-1-2-2](../../media/795e8c6b-4828-4de2-b624-82f067bb2eb1.png)
  
4. <span data-ttu-id="8c7da-210">Selecione **Mover DNS**.</span><span class="sxs-lookup"><span data-stu-id="8c7da-210">Select **Move DNS**.</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-3](../../media/d4a0a7c2-6868-471f-bbf4-16ce2e2348de.png)
  
5. <span data-ttu-id="8c7da-212">Selecione **Salvar Alterações.**</span><span class="sxs-lookup"><span data-stu-id="8c7da-212">Select **Save Changes.**</span></span>
    
    ![NetworkSolutionsBP-Redelegate-1-2-4](../../media/897bc864-b340-4385-abeb-f94bc7f73e5e.png)
  
> [!NOTE]
> <span data-ttu-id="8c7da-214">As atualizações de registro do servidor de nomes poderão levar várias horas para entrarem em vigor no sistema DNS da Internet.</span><span class="sxs-lookup"><span data-stu-id="8c7da-214">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8c7da-215">Em seguida, seu email da Microsoft e outros serviços serão definidos para funcionar com seu domínio.</span><span class="sxs-lookup"><span data-stu-id="8c7da-215">Then your Microsoft email and other services will be all set to work with your domain.</span></span>
