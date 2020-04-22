---
title: Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: Edite o registro do Windows no computador local para desabilitar relatórios ao exportar os resultados de uma pesquisa de conteúdo do centro de conformidade de & de segurança no Office 365. A desabilitação desses relatórios pode acelerar o tempo de download e poupar espaço em disco.
ms.openlocfilehash: 3bd5fadda750c709c463fbc4d84668b43e0d3a10
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633446"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="fc45d-104">Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="fc45d-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="fc45d-105">Ao usar a ferramenta de exportação de descoberta eletrônica para exportar os resultados de uma pesquisa de conteúdo no centro de conformidade de & de segurança, a ferramenta cria e exporta automaticamente dois relatórios que contêm informações adicionais sobre o conteúdo exportado.</span><span class="sxs-lookup"><span data-stu-id="fc45d-105">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="fc45d-106">Esses relatórios são o arquivo Results. csv e o arquivo manifest. XML (consulte a seção [perguntas frequentes sobre a desabilitação de relatórios de exportação](#frequently-asked-questions-about-disabling-export-reports) neste tópico para obter descrições detalhadas desses relatórios).</span><span class="sxs-lookup"><span data-stu-id="fc45d-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="fc45d-107">Como esses arquivos podem ser muito grandes, você pode acelerar o tempo de download e poupar espaço em disco, impedindo que esses arquivos sejam exportados.</span><span class="sxs-lookup"><span data-stu-id="fc45d-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="fc45d-108">Você pode fazer isso alterando o registro do Windows no computador que você usa para exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fc45d-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="fc45d-109">Se você quiser incluir os relatórios mais tarde, poderá editar a configuração do registro.</span><span class="sxs-lookup"><span data-stu-id="fc45d-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="fc45d-110">Criar configurações do registro para desabilitar os relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="fc45d-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="fc45d-111">Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fc45d-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="fc45d-112">Feche a ferramenta de exportação de descoberta eletrônica, se ela estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="fc45d-112">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="fc45d-113">Execute uma ou ambas as etapas a seguir, dependendo do relatório de exportação que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="fc45d-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="fc45d-114">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="fc45d-114">**Results.csv**</span></span>
    
      <span data-ttu-id="fc45d-115">Salve o seguinte texto em um arquivo de registro do Windows usando um sufixo de nome de arquivo. reg; por exemplo, DisableResultsCsv. reg.</span><span class="sxs-lookup"><span data-stu-id="fc45d-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="fc45d-116">**Manifest. xml**</span><span class="sxs-lookup"><span data-stu-id="fc45d-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="fc45d-117">Salve o seguinte texto em um arquivo de registro do Windows usando um sufixo de nome de arquivo. reg; por exemplo, DisableManifestXml. reg.</span><span class="sxs-lookup"><span data-stu-id="fc45d-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="fc45d-118">No Windows Explorer, clique ou clique duas vezes no arquivo. reg que você criou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="fc45d-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="fc45d-119">Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="fc45d-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="fc45d-120">Quando for solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fc45d-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="fc45d-121">O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.</span><span class="sxs-lookup"><span data-stu-id="fc45d-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="fc45d-122">Editar configurações do registro para habilitar novamente os relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="fc45d-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="fc45d-123">Se você desabilitou os relatórios Results. csv e manifest. XML criando os arquivos. reg no procedimento anterior, poderá editar esses arquivos para reabilitar um relatório para que ele seja exportado com os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fc45d-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="fc45d-124">Novamente, execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="fc45d-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="fc45d-125">Feche a ferramenta de exportação de descoberta eletrônica, se ela estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="fc45d-125">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="fc45d-126">Edite um ou ambos os arquivos. reg Edit que você criou no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="fc45d-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="fc45d-127">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="fc45d-127">**Results.csv**</span></span>
    
        <span data-ttu-id="fc45d-128">Abra o arquivo DisableResultsCsv. reg no bloco de notas, altere `False` o `True`valor para e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fc45d-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="fc45d-129">Por exemplo, após editar o arquivo, ele terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="fc45d-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="fc45d-130">**Manifest. xml**</span><span class="sxs-lookup"><span data-stu-id="fc45d-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="fc45d-131">Abra o arquivo DisableManifestXml. reg no bloco de notas, altere `False` o `True`valor para e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="fc45d-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="fc45d-132">Por exemplo, após editar o arquivo, ele terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="fc45d-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="fc45d-133">No Windows Explorer, clique ou clique duas vezes em um arquivo. reg que você editou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="fc45d-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="fc45d-134">Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="fc45d-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="fc45d-135">Quando for solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fc45d-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="fc45d-136">O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.</span><span class="sxs-lookup"><span data-stu-id="fc45d-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="fc45d-137">Perguntas frequentes sobre a desabilitação de relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="fc45d-137">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="fc45d-138">**Quais são os relatórios Results. csv e manifest. xml?**</span><span class="sxs-lookup"><span data-stu-id="fc45d-138">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="fc45d-139">Os arquivos Results. csv e manifest. xml contêm informações adicionais sobre o conteúdo que foi exportado.</span><span class="sxs-lookup"><span data-stu-id="fc45d-139">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="fc45d-140">**Results. csv** um documento do Excel que contém informações sobre cada item que é baixado como resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fc45d-140">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="fc45d-141">Para emails, o log do resultado contém informações sobre cada mensagem, incluindo:</span><span class="sxs-lookup"><span data-stu-id="fc45d-141">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="fc45d-142">O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).</span><span class="sxs-lookup"><span data-stu-id="fc45d-142">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="fc45d-143">A data na qual a mensagem foi enviada ou recebida.</span><span class="sxs-lookup"><span data-stu-id="fc45d-143">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="fc45d-144">A linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="fc45d-144">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="fc45d-145">O remetente e os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="fc45d-145">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="fc45d-146">Se a mensagem é uma mensagem duplicada se você habilitou a eliminação de duplicação ao exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fc45d-146">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="fc45d-147">As mensagens duplicadas terão um valor na coluna **ItemId pai** que identifica a mensagem como uma duplicata.</span><span class="sxs-lookup"><span data-stu-id="fc45d-147">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="fc45d-148">O valor na coluna **ItemId pai** é o mesmo que o valor da coluna **DocumentID de item** da mensagem que foi exportada.</span><span class="sxs-lookup"><span data-stu-id="fc45d-148">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="fc45d-149">Para documentos de sites do SharePoint e do OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:</span><span class="sxs-lookup"><span data-stu-id="fc45d-149">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="fc45d-150">A URL para o documento.</span><span class="sxs-lookup"><span data-stu-id="fc45d-150">The URL for the document.</span></span>
    
  - <span data-ttu-id="fc45d-151">A URL para o conjunto de sites onde o documento está localizado.</span><span class="sxs-lookup"><span data-stu-id="fc45d-151">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="fc45d-152">A data em que o documento foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="fc45d-152">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="fc45d-153">O nome do documento (que está localizado na coluna Assunto no log de resultados).</span><span class="sxs-lookup"><span data-stu-id="fc45d-153">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="fc45d-154">**Manifest. xml** um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fc45d-154">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="fc45d-155">As informações neste relatório são as mesmas do relatório Results. csv, mas estão no formato especificado pelo modelo de referência de descoberta eletrônica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="fc45d-155">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="fc45d-156">Para obter mais informações sobre o EDRM, [https://www.edrm.net](https://www.edrm.net)acesse.</span><span class="sxs-lookup"><span data-stu-id="fc45d-156">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="fc45d-157">**Quando devo desabilitar a exportação desses relatórios?**</span><span class="sxs-lookup"><span data-stu-id="fc45d-157">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="fc45d-158">Depende de suas necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="fc45d-158">It depends on your specific needs.</span></span> <span data-ttu-id="fc45d-159">Muitas organizações não exigem informações adicionais sobre os resultados da pesquisa e não precisam desses relatórios.</span><span class="sxs-lookup"><span data-stu-id="fc45d-159">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="fc45d-160">**Em qual computador tenho que fazer isso?**</span><span class="sxs-lookup"><span data-stu-id="fc45d-160">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="fc45d-161">É necessário alterar a configuração do registro em qualquer computador local em que você executa a ferramenta de exportação de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="fc45d-161">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="fc45d-162">**Após alterar essa configuração, preciso reiniciar o computador?**</span><span class="sxs-lookup"><span data-stu-id="fc45d-162">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="fc45d-163">Não, não é necessário reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="fc45d-163">No, you don't have to restart the computer.</span></span> <span data-ttu-id="fc45d-164">Mas, se a ferramenta de exportação de descoberta eletrônica estiver em execução, você terá de fechá-la e reiniciá-la depois de alterar a configuração do registro.</span><span class="sxs-lookup"><span data-stu-id="fc45d-164">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="fc45d-165">**Uma chave de registro existente é editada ou faz uma nova chave ser criada?**</span><span class="sxs-lookup"><span data-stu-id="fc45d-165">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="fc45d-166">Uma nova chave de registro é criada na primeira vez que você executa o arquivo. reg que você criou no procedimento deste tópico.</span><span class="sxs-lookup"><span data-stu-id="fc45d-166">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="fc45d-167">Em seguida, a configuração será editada sempre que você alterar e executar novamente o arquivo. reg Edit.</span><span class="sxs-lookup"><span data-stu-id="fc45d-167">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
