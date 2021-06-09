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
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: Edite o Windows registro em seu computador local para desabilitar relatórios ao exportar os resultados de uma Pesquisa de Conteúdo do Centro de Conformidade & Segurança.
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817850"
---
# <a name="disable-reports-when-you-export-content-search-results"></a><span data-ttu-id="b9f37-103">Desabilitar relatórios ao exportar os resultados da Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="b9f37-103">Disable reports when you export Content Search results</span></span>

<span data-ttu-id="b9f37-104">Quando você usa a ferramenta Exportação de Descoberta Automática para exportar os resultados de uma Pesquisa de Conteúdo no Centro de Conformidade e Segurança, a ferramenta cria e exporta automaticamente dois relatórios que contêm informações adicionais sobre o conteúdo exportado. &</span><span class="sxs-lookup"><span data-stu-id="b9f37-104">When you use the eDiscovery Export tool to export the results of a Content Search in the Security & Compliance Center, the tool automatically creates and exports two reports that contain additional information about the exported content.</span></span> <span data-ttu-id="b9f37-105">Esses relatórios são o arquivo Results.csv e o arquivo [](#frequently-asked-questions-about-disabling-export-reports) Manifest.xml (consulte a seção Perguntas frequentes sobre como desabilitar relatórios de exportação neste tópico para descrições detalhadas desses relatórios).</span><span class="sxs-lookup"><span data-stu-id="b9f37-105">These reports are the Results.csv file and the Manifest.xml file (see the [Frequently asked questions about disabling export reports](#frequently-asked-questions-about-disabling-export-reports) section in this topic for detailed descriptions of these reports).</span></span> <span data-ttu-id="b9f37-106">Como esses arquivos podem ser muito grandes, você pode acelerar o tempo de download e economizar espaço em disco impedindo que esses arquivos sejam exportados.</span><span class="sxs-lookup"><span data-stu-id="b9f37-106">Because these files can be very large, you can speed up the download time and save disk space by preventing these files from being exported.</span></span> <span data-ttu-id="b9f37-107">Você pode fazer isso alterando a Windows registro no computador que você usa para exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b9f37-107">You can do this by changing the Windows Registry on the computer that you use to export the search results.</span></span> <span data-ttu-id="b9f37-108">Se quiser incluir os relatórios posteriormente, edite a configuração do Registro.</span><span class="sxs-lookup"><span data-stu-id="b9f37-108">If you want to include the reports at a later time, you can edit the registry setting.</span></span> 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a><span data-ttu-id="b9f37-109">Criar configurações do Registro para desabilitar os relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="b9f37-109">Create registry settings to disable the export reports</span></span>

<span data-ttu-id="b9f37-110">Execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b9f37-110">Perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="b9f37-111">Feche a ferramenta Exportação de Descoberta Digital se estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="b9f37-111">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="b9f37-112">Execute uma ou ambas as etapas a seguir, dependendo do relatório de exportação que você deseja desabilitar.</span><span class="sxs-lookup"><span data-stu-id="b9f37-112">Perform one or both of the following steps, depending on which export report you want to disable.</span></span>
    
    - <span data-ttu-id="b9f37-113">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="b9f37-113">**Results.csv**</span></span>
    
      <span data-ttu-id="b9f37-114">Salve o texto a seguir em um arquivo Windows registro usando um sufixo de nome de arquivo de .reg; por exemplo, DisableResultsCsv.reg.</span><span class="sxs-lookup"><span data-stu-id="b9f37-114">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableResultsCsv.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - <span data-ttu-id="b9f37-115">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="b9f37-115">**Manifest.xml**</span></span>
    
      <span data-ttu-id="b9f37-116">Salve o texto a seguir em um arquivo Windows registro usando um sufixo de nome de arquivo de .reg; por exemplo, DisableManifestXml.reg.</span><span class="sxs-lookup"><span data-stu-id="b9f37-116">Save the following text to a Windows registry file by using a filename suffix of .reg; for example, DisableManifestXml.reg.</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. <span data-ttu-id="b9f37-117">No Windows Explorer, clique ou clique duas vezes no arquivo .reg que você criou nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="b9f37-117">In Windows Explorer, click or double-click the .reg file that you created in the previous steps.</span></span>
    
4. <span data-ttu-id="b9f37-118">Na janela Controle de Acesso para Usuário, clique em **Sim** para permitir que o Editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="b9f37-118">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="b9f37-119">Quando solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b9f37-119">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="b9f37-120">O Editor do Registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao Registro.</span><span class="sxs-lookup"><span data-stu-id="b9f37-120">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a><span data-ttu-id="b9f37-121">Editar configurações do Registro para habilitar os relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="b9f37-121">Edit registry settings to re-enable the export reports</span></span>

<span data-ttu-id="b9f37-122">Se você desabilitou os relatórios Results.csv e Manifest.xml criando os arquivos .reg no procedimento anterior, você poderá editar esses arquivos para habilitar um relatório para que ele seja exportado com os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b9f37-122">If you disabled the Results.csv and Manifest.xml reports by creating the .reg files in the previous procedure, you can edit those files to re-enable a report so that it's exported with the search results.</span></span> <span data-ttu-id="b9f37-123">Novamente, execute o procedimento a seguir no computador que você usará para exportar os resultados de uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b9f37-123">Again, perform the following procedure on the computer that you'll use to export the results a content search.</span></span>
  
1. <span data-ttu-id="b9f37-124">Feche a ferramenta Exportação de Descoberta Digital se estiver aberta.</span><span class="sxs-lookup"><span data-stu-id="b9f37-124">Close the eDiscovery Export tool if it's open.</span></span>
    
2. <span data-ttu-id="b9f37-125">Edite um ou ambos os arquivos de edição .reg criados no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="b9f37-125">Edit one or both of the .reg edit files that you created in the previous procedure.</span></span>
    
    - <span data-ttu-id="b9f37-126">**Results.csv**</span><span class="sxs-lookup"><span data-stu-id="b9f37-126">**Results.csv**</span></span>
    
        <span data-ttu-id="b9f37-127">Abra o arquivo DisableResultsCsv.reg no Bloco de notas, altere o valor para `False` `True` e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9f37-127">Open the DisableResultsCsv.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="b9f37-128">Por exemplo, depois de editar o arquivo, ele será assim:</span><span class="sxs-lookup"><span data-stu-id="b9f37-128">For example, after you edit the file, it looks like this:</span></span>
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - <span data-ttu-id="b9f37-129">**Manifest.xml**</span><span class="sxs-lookup"><span data-stu-id="b9f37-129">**Manifest.xml**</span></span>
    
        <span data-ttu-id="b9f37-130">Abra o arquivo DisableManifestXml.reg no Bloco de notas, altere o valor `False` para e salve o `True` arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9f37-130">Open the DisableManifestXml.reg file in Notepad, change the value  `False` to  `True`, and then save the file.</span></span> <span data-ttu-id="b9f37-131">Por exemplo, depois de editar o arquivo, ele será assim:</span><span class="sxs-lookup"><span data-stu-id="b9f37-131">For example, after you edit the file, it looks like this:</span></span>
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. <span data-ttu-id="b9f37-132">No Windows Explorer, clique ou clique duas vezes em um arquivo .reg que você editou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="b9f37-132">In Windows Explorer, click or double-click a .reg file that you edited in the previous step.</span></span>
    
4. <span data-ttu-id="b9f37-133">Na janela Controle de Acesso para Usuário, clique em **Sim** para permitir que o Editor do Registro faça a alteração.</span><span class="sxs-lookup"><span data-stu-id="b9f37-133">In the User Access Control window, click **Yes** to let the Registry Editor make the change.</span></span> 
    
5. <span data-ttu-id="b9f37-134">Quando solicitado a continuar, clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b9f37-134">When prompted to continue, click **Yes**.</span></span>
    
    <span data-ttu-id="b9f37-135">O Editor do Registro exibe uma mensagem dizendo que a configuração foi adicionada com êxito ao Registro.</span><span class="sxs-lookup"><span data-stu-id="b9f37-135">The Registry Editor displays a message saying that the setting was successfully added to the registry.</span></span>
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a><span data-ttu-id="b9f37-136">Perguntas frequentes sobre desabilitar relatórios de exportação</span><span class="sxs-lookup"><span data-stu-id="b9f37-136">Frequently asked questions about disabling export reports</span></span>

 <span data-ttu-id="b9f37-137">**Quais são os Results.csv e Manifest.xml relatórios?**</span><span class="sxs-lookup"><span data-stu-id="b9f37-137">**What are the Results.csv and Manifest.xml reports?**</span></span>
  
<span data-ttu-id="b9f37-138">Os arquivos Results.csv e Manifest.xml contêm informações adicionais sobre o conteúdo que foi exportado.</span><span class="sxs-lookup"><span data-stu-id="b9f37-138">The Results.csv and Manifest.xml files contain additional information about the content that was exported.</span></span>
  
- <span data-ttu-id="b9f37-139">**Results.csv** Um Excel que contém informações sobre cada item que é baixado como resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b9f37-139">**Results.csv** An Excel document that contains information about each item that is download as a search result.</span></span> <span data-ttu-id="b9f37-140">Para emails, o log do resultado contém informações sobre cada mensagem, incluindo:</span><span class="sxs-lookup"><span data-stu-id="b9f37-140">For email, the result log contains information about each message, including:</span></span> 
    
  - <span data-ttu-id="b9f37-141">O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).</span><span class="sxs-lookup"><span data-stu-id="b9f37-141">The location of the message in the source mailbox (including whether the message is in the primary or archive mailbox).</span></span>
    
  - <span data-ttu-id="b9f37-142">A data na qual a mensagem foi enviada ou recebida.</span><span class="sxs-lookup"><span data-stu-id="b9f37-142">The date the message was sent or received.</span></span>
    
  - <span data-ttu-id="b9f37-143">A linha de assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b9f37-143">The Subject line from the message.</span></span>
    
  - <span data-ttu-id="b9f37-144">O remetente e os destinatários da mensagem.</span><span class="sxs-lookup"><span data-stu-id="b9f37-144">The sender and recipients of the message.</span></span>
    
  - <span data-ttu-id="b9f37-145">Se a mensagem é uma mensagem duplicada se você habilitar a des duplicação ao exportar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b9f37-145">Whether the message is a duplicate message if you enabled de-duplication when exporting the search results.</span></span> <span data-ttu-id="b9f37-146">As mensagens duplicadas terão um valor na coluna **ItemId pai** que identifica a mensagem como uma duplicata.</span><span class="sxs-lookup"><span data-stu-id="b9f37-146">Duplicate messages will have a value in the **Parent ItemId** column that identifies the message as a duplicate.</span></span> <span data-ttu-id="b9f37-147">O valor na **coluna ItemId pai** é o mesmo da coluna **Item DocumentId** da mensagem que foi exportada.</span><span class="sxs-lookup"><span data-stu-id="b9f37-147">The value in the **Parent ItemId** column is the same as the value in the **Item DocumentId** column of the message that was exported.</span></span> 
    
    <span data-ttu-id="b9f37-148">Para documentos de SharePoint sites OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:</span><span class="sxs-lookup"><span data-stu-id="b9f37-148">For documents from SharePoint and OneDrive for Business sites, the result log contains information about each document, including:</span></span>
    
  - <span data-ttu-id="b9f37-149">A URL para o documento.</span><span class="sxs-lookup"><span data-stu-id="b9f37-149">The URL for the document.</span></span>
    
  - <span data-ttu-id="b9f37-150">A URL para o conjunto de sites onde o documento está localizado.</span><span class="sxs-lookup"><span data-stu-id="b9f37-150">The URL for the site collection where the document is located.</span></span>
    
  - <span data-ttu-id="b9f37-151">A data em que o documento foi modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="b9f37-151">The date that the document was last modified.</span></span>
    
  - <span data-ttu-id="b9f37-152">O nome do documento (que está localizado na coluna Assunto no log de resultados).</span><span class="sxs-lookup"><span data-stu-id="b9f37-152">The name of the document (which is located in the Subject column in the result log).</span></span>
    
- <span data-ttu-id="b9f37-153">**Manifest.xml** Um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b9f37-153">**Manifest.xml** A manifest file (in XML format) that contains information about each item included in the search results.</span></span> <span data-ttu-id="b9f37-154">As informações neste relatório são as mesmas do relatório de Results.csv, mas estão no formato especificado pelo Modelo de Referência de Descoberta Eletrônica (EDRM).</span><span class="sxs-lookup"><span data-stu-id="b9f37-154">The information in this report is the same as the Results.csv report, but it's in the format specified by the Electronic Discovery Reference Model (EDRM).</span></span> <span data-ttu-id="b9f37-155">Para obter mais informações sobre o EDRM, vá para [https://www.edrm.net](https://www.edrm.net) .</span><span class="sxs-lookup"><span data-stu-id="b9f37-155">For more information about EDRM, go to [https://www.edrm.net](https://www.edrm.net).</span></span>
    
 <span data-ttu-id="b9f37-156">**Quando devo desabilitar a exportação desses relatórios?**</span><span class="sxs-lookup"><span data-stu-id="b9f37-156">**When should I disable exporting these reports?**</span></span>
  
<span data-ttu-id="b9f37-157">Depende de suas necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="b9f37-157">It depends on your specific needs.</span></span> <span data-ttu-id="b9f37-158">Muitas organizações não exigem informações adicionais sobre os resultados da pesquisa e não precisam desses relatórios.</span><span class="sxs-lookup"><span data-stu-id="b9f37-158">Many organizations don't require additional information about search results, and don't need these reports.</span></span>
  
 <span data-ttu-id="b9f37-159">**Em qual computador devo fazer isso?**</span><span class="sxs-lookup"><span data-stu-id="b9f37-159">**What computer do I have to do this on?**</span></span>
  
 <span data-ttu-id="b9f37-160">Você precisa alterar a configuração do Registro em qualquer computador local em que você execute a ferramenta Exportar Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="b9f37-160">You have to change the registry setting on any local computer that you run the eDiscovery Export tool on.</span></span> 
  
 <span data-ttu-id="b9f37-161">**Depois de alterar essa configuração, preciso reiniciar o computador?**</span><span class="sxs-lookup"><span data-stu-id="b9f37-161">**After I change this setting, do I have to restart the computer?**</span></span>
  
<span data-ttu-id="b9f37-162">Não, você não precisa reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="b9f37-162">No, you don't have to restart the computer.</span></span> <span data-ttu-id="b9f37-163">Porém, se a ferramenta Exportação de Descoberta Digital estiver em execução, você terá que fechar e reinicie-a depois de alterar a configuração do Registro.</span><span class="sxs-lookup"><span data-stu-id="b9f37-163">But if the eDiscovery Export tool is running, you have to close it and then restart it after you change the registry setting.</span></span>
  
 <span data-ttu-id="b9f37-164">**Uma chave existente do Registro é editada ou uma nova chave é criada?**</span><span class="sxs-lookup"><span data-stu-id="b9f37-164">**Does an existing registry key get edited or does a new key get created?**</span></span>
  
<span data-ttu-id="b9f37-165">Uma nova chave do Registro é criada na primeira vez que você executar o arquivo .reg que você criou no procedimento neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b9f37-165">A new registry key is created the first time you run the .reg file that you created in the procedure in this topic.</span></span> <span data-ttu-id="b9f37-166">Em seguida, a configuração é editada sempre que você alterar e executar o arquivo de edição .reg.</span><span class="sxs-lookup"><span data-stu-id="b9f37-166">Then the setting is edited each time you change and re-run the .reg edit file.</span></span>
