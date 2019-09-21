---
title: Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo
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
ms.openlocfilehash: f6abcf8afe70bc6ce04f0f9343e28879f7fed885
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071928"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="a30a2-104">Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="a30a2-104">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="a30a2-105">Ao usar a ferramenta de exportação de descoberta eletrônica do Office 365 para exportar os resultados de uma pesquisa de conteúdo no centro de conformidade de & de segurança, a ferramenta cria e exporta automaticamente dois relatórios que contêm informações adicionais sobre o conteúdo exportado.</span><span class="sxs-lookup"><span data-stu-id="a30a2-105">When you use the Office 365 eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="a30a2-106">Esses relatórios são o arquivo Results. csv e o arquivo manifest. XML (consulte a seção [perguntas frequentes sobre a desabilitação de relatórios de exportação](#frequently-asked-questions-about-disabling-export-reports) neste tópico para obter descrições detalhadas desses relatórios).</span><span class="sxs-lookup"><span data-stu-id="a30a2-106">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="a30a2-107">Como esses arquivos podem ser muito grandes, você pode acelerar o tempo de download e poupar espaço em disco, impedindo que esses arquivos sejam exportados.</span><span class="sxs-lookup"><span data-stu-id="a30a2-107">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="a30a2-108">Você pode fazer isso alterando o registro do Windows no computador que você usa para exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a30a2-108">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="a30a2-109">Se você quiser incluir os relatórios mais tarde, poderá editar a configuração do registro.</span><span class="sxs-lookup"><span data-stu-id="a30a2-109">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="a30a2-110">Criar configurações do registro para desabilitar os relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="a30a2-110">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="a30a2-111">Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a30a2-111">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="a30a2-112">Feche a ferramenta de exportação de descoberta eletrônica do Office 365 se ela estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="a30a2-112">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="a30a2-113">Execute uma ou ambas as etapas a seguir, dependendo do relatório de exportação que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="a30a2-113">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="a30a2-114">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="a30a2-114">**Results.csv**</span></span>
    
      <span data-ttu-id="a30a2-115">Salve o seguinte texto em um arquivo de registro do Windows usando um sufixo de nome de arquivo. reg; por exemplo, DisableResultsCsv. reg.</span><span class="sxs-lookup"><span data-stu-id="a30a2-115">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="a30a2-116">**Manifest. xml**</span><span class="sxs-lookup"><span data-stu-id="a30a2-116">**Manifest.xml**</span></span>
    
      <span data-ttu-id="a30a2-117">Salve o seguinte texto em um arquivo de registro do Windows usando um sufixo de nome de arquivo. reg; por exemplo, DisableManifestXml. reg.</span><span class="sxs-lookup"><span data-stu-id="a30a2-117">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="a30a2-118">No Windows Explorer, clique ou clique duas vezes no arquivo. reg que você criou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="a30a2-118">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="a30a2-119">Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="a30a2-119">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="a30a2-120">Quando for solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a30a2-120">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="a30a2-121">O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.</span><span class="sxs-lookup"><span data-stu-id="a30a2-121">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="a30a2-122">Editar configurações do registro para habilitar novamente os relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="a30a2-122">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="a30a2-123">Se você desabilitou os relatórios Results. csv e manifest. XML criando os arquivos. reg no procedimento anterior, poderá editar esses arquivos para reabilitar um relatório para que ele seja exportado com os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a30a2-123">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="a30a2-124">Novamente, execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a30a2-124">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="a30a2-125">Feche a ferramenta de exportação de descoberta eletrônica do Office 365 se ela estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="a30a2-125">Close the Office 365 eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="a30a2-126">Edite um ou ambos os arquivos. reg Edit que você criou no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="a30a2-126">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="a30a2-127">**Results. csv**</span><span class="sxs-lookup"><span data-stu-id="a30a2-127">**Results.csv**</span></span>
    
        <span data-ttu-id="a30a2-128">Abra o arquivo DisableResultsCsv. reg no bloco de notas, altere `False` o `True`valor para e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="a30a2-128">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="a30a2-129">Por exemplo, após editar o arquivo, ele terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="a30a2-129">For example, after you edit the file, it looks like this:</span></span>
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="a30a2-130">**Manifest. xml**</span><span class="sxs-lookup"><span data-stu-id="a30a2-130">**Manifest.xml**</span></span>
    
        <span data-ttu-id="a30a2-131">Abra o arquivo DisableManifestXml. reg no bloco de notas, altere `False` o `True`valor para e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="a30a2-131">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="a30a2-132">Por exemplo, após editar o arquivo, ele terá a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="a30a2-132">For example, after you edit the file, it looks like this:</span></span>
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="a30a2-133">No Windows Explorer, clique ou clique duas vezes em um arquivo. reg que você editou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="a30a2-133">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="a30a2-134">Na janela controle de acesso do usuário, clique em **Sim** para permitir que o editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="a30a2-134">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="a30a2-135">Quando for solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="a30a2-135">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="a30a2-136">O editor do registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao registro.</span><span class="sxs-lookup"><span data-stu-id="a30a2-136">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="a30a2-137">Perguntas frequentes sobre a desabilitação de relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="a30a2-137">Frequently asked questions about disabling export reports</span></span>
<span data-ttu-id="a30a2-138"><a name="faqs"> </a></span><span class="sxs-lookup"><span data-stu-id="a30a2-138"></span></span>

 <span data-ttu-id="a30a2-139">**Quais são os relatórios Results. csv e manifest. xml?**</span><span class="sxs-lookup"><span data-stu-id="a30a2-139">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="a30a2-140">Os arquivos Results. csv e manifest. xml contêm informações adicionais sobre o conteúdo que foi exportado.</span><span class="sxs-lookup"><span data-stu-id="a30a2-140">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="a30a2-141">**Results. csv** um documento do Excel que contém informações sobre cada item que é baixado como resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a30a2-141">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="a30a2-142">Para emails, o log do resultado contém informações sobre cada mensagem, incluindo:</span><span class="sxs-lookup"><span data-stu-id="a30a2-142">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="a30a2-143">O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).</span><span class="sxs-lookup"><span data-stu-id="a30a2-143">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="a30a2-144">A data na qual a mensagem foi enviada ou recebida.</span><span class="sxs-lookup"><span data-stu-id="a30a2-144">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="a30a2-145">A linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a30a2-145">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="a30a2-146">O remetente e os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a30a2-146">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="a30a2-147">Se a mensagem é uma mensagem duplicada se você habilitou a eliminação de duplicação ao exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a30a2-147">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="a30a2-148">As mensagens duplicadas terão um valor na coluna **ItemId pai** que identifica a mensagem como uma duplicata.</span><span class="sxs-lookup"><span data-stu-id="a30a2-148">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="a30a2-149">O valor na coluna **ItemId pai** é o mesmo que o valor da coluna **DocumentID de item** da mensagem que foi exportada.</span><span class="sxs-lookup"><span data-stu-id="a30a2-149">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="a30a2-150">Para documentos de sites do SharePoint e do OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:</span><span class="sxs-lookup"><span data-stu-id="a30a2-150">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="a30a2-151">A URL para o documento.</span><span class="sxs-lookup"><span data-stu-id="a30a2-151">The URL for the document.</span></span>
    
  - <span data-ttu-id="a30a2-152">A URL para o conjunto de sites onde o documento está localizado.</span><span class="sxs-lookup"><span data-stu-id="a30a2-152">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="a30a2-153">A data em que o documento foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="a30a2-153">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="a30a2-154">O nome do documento (que está localizado na coluna Assunto no log de resultados).</span><span class="sxs-lookup"><span data-stu-id="a30a2-154">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="a30a2-155">**Manifest. xml** um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a30a2-155">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="a30a2-156">As informações neste relatório são as mesmas do relatório Results. csv, mas estão no formato especificado pelo modelo de referência de descoberta eletrônica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="a30a2-156">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="a30a2-157">Para obter mais informações sobre o EDRM, [https://www.edrm.net](https://www.edrm.net)acesse.</span><span class="sxs-lookup"><span data-stu-id="a30a2-157">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="a30a2-158">**Quando devo desabilitar a exportação desses relatórios?**</span><span class="sxs-lookup"><span data-stu-id="a30a2-158">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="a30a2-159">Depende de suas necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="a30a2-159">It depends on your specific needs.</span></span> <span data-ttu-id="a30a2-160">Muitas organizações não exigem informações adicionais sobre os resultados da pesquisa e não precisam desses relatórios.</span><span class="sxs-lookup"><span data-stu-id="a30a2-160">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="a30a2-161">**Em qual computador tenho que fazer isso?**</span><span class="sxs-lookup"><span data-stu-id="a30a2-161">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="a30a2-162">Você precisa alterar a configuração do registro em qualquer computador local em que executa a ferramenta de exportação de descoberta eletrônica do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a30a2-162">You have to change the registry setting on any local computer that you run the Office 365 eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="a30a2-163">**Após alterar essa configuração, preciso reiniciar o computador?**</span><span class="sxs-lookup"><span data-stu-id="a30a2-163">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="a30a2-164">Não, não é necessário reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="a30a2-164">No, you don't have to restart the computer.</span></span> <span data-ttu-id="a30a2-165">Mas, se a ferramenta de exportação de descoberta eletrônica do Office 365 estiver em execução, você terá que fechá-la e reiniciá-la depois de alterar a configuração do registro.</span><span class="sxs-lookup"><span data-stu-id="a30a2-165">But if the Office 365 eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="a30a2-166">**Uma chave de registro existente é editada ou faz uma nova chave ser criada?**</span><span class="sxs-lookup"><span data-stu-id="a30a2-166">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="a30a2-167">Uma nova chave de registro é criada na primeira vez que você executa o arquivo. reg que você criou no procedimento deste tópico.</span><span class="sxs-lookup"><span data-stu-id="a30a2-167">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="a30a2-168">Em seguida, a configuração será editada sempre que você alterar e executar novamente o arquivo. reg Edit.</span><span class="sxs-lookup"><span data-stu-id="a30a2-168">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
