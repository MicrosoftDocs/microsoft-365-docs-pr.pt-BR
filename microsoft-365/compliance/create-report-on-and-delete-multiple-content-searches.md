---
title: Criar, gerar relatórios sobre e excluir várias Pesquisas de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Saiba como automatizar tarefas de Pesquisa de Conteúdo, como criar pesquisas e executar relatórios por meio de scripts do PowerShell no Centro de Conformidade & segurança no Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6155a0bf411cc83fd58291efe7797e7f68370708
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994958"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="99858-103">Criar, gerar relatórios sobre e excluir várias Pesquisas de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="99858-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="99858-104">A criação e o relatório rápido de pesquisas de descoberta geralmente é uma etapa importante na Descoberta EDiscovery e nas investigações quando você está tentando aprender sobre os dados subjacentes e a riqueza e a qualidade de suas pesquisas.</span><span class="sxs-lookup"><span data-stu-id="99858-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="99858-105">Para ajudá-lo a fazer isso, o Centro de Conformidade e Segurança & PowerShell oferece um conjunto de cmdlets para automatizar tarefas de Pesquisa de Conteúdo demoradas.</span><span class="sxs-lookup"><span data-stu-id="99858-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="99858-106">Esses scripts fornecem uma maneira rápida e fácil de criar uma série de pesquisas e, em seguida, executar relatórios dos resultados de pesquisa estimados que podem ajudá-lo a determinar a quantidade de dados em questão.</span><span class="sxs-lookup"><span data-stu-id="99858-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="99858-107">Você também pode usar os scripts para criar diferentes versões de pesquisas para comparar os resultados que cada um produz.</span><span class="sxs-lookup"><span data-stu-id="99858-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="99858-108">Esses scripts podem ajudá-lo a identificar e separar seus dados de forma rápida e eficiente.</span><span class="sxs-lookup"><span data-stu-id="99858-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="99858-109">Antes de criar uma Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="99858-109">Before you create a Content Search</span></span>

- <span data-ttu-id="99858-110">Você precisa ser membro do grupo de funções do Gerenciador de Descobertas e No Centro de Conformidade & Segurança para executar os scripts descritos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="99858-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="99858-111">Para coletar uma lista das URLs para os sites OneDrive for Business em sua organização que você pode adicionar ao arquivo CSV na Etapa 1, consulte Create a list of all [OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span><span class="sxs-lookup"><span data-stu-id="99858-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="99858-112">Salve todos os arquivos que você criar neste tópico na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="99858-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="99858-113">Isso facilitará a executar os scripts.</span><span class="sxs-lookup"><span data-stu-id="99858-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="99858-114">Os scripts incluem tratamento mínimo de erros.</span><span class="sxs-lookup"><span data-stu-id="99858-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="99858-115">Seu principal objetivo é criar, relatar e excluir rapidamente várias Pesquisas de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="99858-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="99858-p104">Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="99858-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="99858-121">Etapa 1: Criar um arquivo CSV que contenha informações sobre as pesquisas que você deseja executar</span><span class="sxs-lookup"><span data-stu-id="99858-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="99858-122">O arquivo CSV (valor separado por vírgula) que você cria nesta etapa contém uma linha para cada usuário que deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="99858-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="99858-123">Você pode pesquisar a caixa de correio Exchange Online do usuário (que inclui a caixa de correio de arquivo morto, se ela estiver habilitada) e seu site de OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="99858-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="99858-124">Ou você pode pesquisar apenas a caixa de correio ou o OneDrive for Business site.</span><span class="sxs-lookup"><span data-stu-id="99858-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="99858-125">Você também pode pesquisar em qualquer site em sua organização SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="99858-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="99858-126">O script executado na Etapa 3 criará uma pesquisa separada para cada linha no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="99858-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="99858-127">Copie e colar o texto a seguir em um arquivo .txt usando o NotePad.</span><span class="sxs-lookup"><span data-stu-id="99858-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="99858-128">Salve esse arquivo em uma pasta no computador local.</span><span class="sxs-lookup"><span data-stu-id="99858-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="99858-129">Você também salvará os outros scripts nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="99858-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="99858-130">A primeira linha, ou linha de header, do arquivo lista os parâmetros que serão usados pelo cmdlet **New-ComplianceSearch** (no script na Etapa 3) para criar uma nova Pesquisa de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="99858-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="99858-131">Os nomes dos parâmetros são separados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="99858-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="99858-132">Certifique-se de que não haja espaços na linha do header.</span><span class="sxs-lookup"><span data-stu-id="99858-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="99858-133">Cada linha sob a linha de header representa os valores de parâmetro para cada pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99858-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="99858-134">Certifique-se de substituir os dados de espaço reservado no arquivo CSV por seus dados reais.</span><span class="sxs-lookup"><span data-stu-id="99858-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="99858-135">Abra o .txt no Excel e, em seguida, use as informações na tabela a seguir para editar o arquivo com informações para cada pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99858-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="99858-136">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="99858-136">Parameter</span></span>|<span data-ttu-id="99858-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="99858-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="99858-138">O endereço SMTP da caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="99858-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="99858-139">A URL do site de OneDrive for Business do usuário ou a URL de qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="99858-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="99858-140">Para a URL para OneDrive for Business sites, use este formato: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` .</span><span class="sxs-lookup"><span data-stu-id="99858-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="99858-141">Por exemplo, `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="99858-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="99858-142">A consulta de pesquisa para a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99858-142">The search query for the search.</span></span> <span data-ttu-id="99858-143">Para obter mais informações sobre como criar uma consulta de pesquisa, consulte [Consultas de palavra-chave e condições](keyword-queries-and-search-conditions.md)de pesquisa para Pesquisa de Conteúdo .</span><span class="sxs-lookup"><span data-stu-id="99858-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="99858-144">Para email, a data em ou após uma mensagem ter sido recebida por um destinatário ou enviada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="99858-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="99858-145">Para documentos em SharePoint ou OneDrive for Business sites, a data em ou após a última modificação de um documento.</span><span class="sxs-lookup"><span data-stu-id="99858-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="99858-146">Para email, a data em ou antes de uma mensagem ter sido enviada por um usuário.</span><span class="sxs-lookup"><span data-stu-id="99858-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="99858-147">Para documentos em SharePoint ou OneDrive for Business sites, a data em ou antes de um documento ter sido modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="99858-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="99858-148">Salve o Excel como um arquivo CSV em uma pasta em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="99858-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="99858-149">O script criado na Etapa 3 usará as informações neste arquivo CSV para criar as pesquisas.</span><span class="sxs-lookup"><span data-stu-id="99858-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="99858-150">Etapa 2: Conectar-se ao Centro de Segurança e Conformidade usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="99858-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="99858-151">A próxima etapa é conectar-se ao Centro de Segurança e Conformidade da sua organização.</span><span class="sxs-lookup"><span data-stu-id="99858-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="99858-152">Para obter instruções passo a passo, confira [Conectar-se ao Centro de Segurança e Conformidade no PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="99858-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="99858-153">Etapa 3: Executar o script para criar e iniciar as pesquisas</span><span class="sxs-lookup"><span data-stu-id="99858-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="99858-154">O script nesta etapa criará uma Pesquisa de Conteúdo separada para cada linha no arquivo CSV que você criou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="99858-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="99858-155">Ao executar esse script, você será solicitado a dois valores:</span><span class="sxs-lookup"><span data-stu-id="99858-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="99858-156">**ID do Grupo de** Pesquisa - Esse nome fornece uma maneira fácil de organizar as pesquisas criadas a partir do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="99858-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="99858-157">Cada pesquisa criada é nomeada com a ID do Grupo de Pesquisa e, em seguida, um número é anexado ao nome da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99858-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="99858-158">Por exemplo, se você inserir **ContosoCase** para a ID do Grupo de Pesquisa, as pesquisas serão denominadas **ContosoCase_1,** **ContosoCase_2,** **ContosoCase_3** e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="99858-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="99858-159">Observe que o nome que você digita é sensível a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="99858-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="99858-160">Quando você usa a ID do Grupo de Pesquisa na Etapa 4 e na Etapa 5, você precisa usar o mesmo caso que usou ao criar.</span><span class="sxs-lookup"><span data-stu-id="99858-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="99858-161">**Arquivo CSV** - O nome do arquivo CSV que você criou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="99858-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="99858-162">Certifique-se de incluir o nome de arquivo completo, inclua a extensão .csv arquivo; por exemplo,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="99858-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="99858-163">Para executar o script:</span><span class="sxs-lookup"><span data-stu-id="99858-163">To run the script:</span></span>

1. <span data-ttu-id="99858-164">Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="99858-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="99858-165">Salve o arquivo na mesma pasta em que você salvou os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="99858-165">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   # Get the Search Group ID and the location of the CSV input file
   $searchGroup = Read-Host 'Search Group ID'
   $csvFile = Read-Host 'Source CSV file'

   # Do a quick check to make sure our group name will not collide with other searches
   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
       Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
       return
    }
    $searchCounter++
   }

   $searchCounter = 1
   import-csv $csvFile |
     ForEach-Object{

    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }

     # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
     $exchangeLocation = $null
     if ( $_.ExchangeLocation)
     {
           $exchangeLocation = $_.ExchangeLocation
     }

    # Create and run the search
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query

    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
       Write-Host " ." -NoNewline
       Start-Sleep -s 3
    }
    Write-Host ""

    $searchCounter++
   }
   ```

2. <span data-ttu-id="99858-166">Em Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="99858-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="99858-167">No prompt **de ID do Grupo** de Pesquisa, digite um nome de grupo de pesquisa e pressione **Enter**; por exemplo,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="99858-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="99858-168">Lembre-se de que esse nome é sensível a casos, portanto, você terá que digitá-lo da mesma maneira nas etapas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="99858-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="99858-169">No prompt **de arquivo CSV** de origem, digite o nome do arquivo CSV, incluindo a extensão .csv arquivo; por exemplo,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="99858-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="99858-170">Pressione **Enter** para continuar executando o script.</span><span class="sxs-lookup"><span data-stu-id="99858-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="99858-171">O script exibe o progresso da criação e execução das pesquisas.</span><span class="sxs-lookup"><span data-stu-id="99858-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="99858-172">Quando o script é concluído, ele retorna para o prompt.</span><span class="sxs-lookup"><span data-stu-id="99858-172">When the script is complete, it returns to the prompt.</span></span>

   ![Exemplo de saída da execução do script para criar várias pesquisas de conformidade](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="99858-174">Etapa 4: Executar o script para relatar as estimativas de pesquisa</span><span class="sxs-lookup"><span data-stu-id="99858-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="99858-175">Depois de criar as pesquisas, a próxima etapa é executar um script que exibe um relatório simples do número de visitas de pesquisa para cada pesquisa criada na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="99858-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="99858-176">O relatório também inclui o tamanho dos resultados de cada pesquisa e o número total de visitas e o tamanho total de todas as pesquisas.</span><span class="sxs-lookup"><span data-stu-id="99858-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="99858-177">Ao executar o script de relatório, você será solicitado a procurar a ID do Grupo de Pesquisa e um nome de arquivo CSV se quiser salvar o relatório em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="99858-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="99858-178">Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="99858-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="99858-179">Salve o arquivo na mesma pasta em que você salvou os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="99858-179">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   $searchGroup = Read-Host 'Search Group ID'
   $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
   $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
   $allSearchStats = @()
   foreach ($partialObj in $searches)
   {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
   }
   # Calculate the totals
   $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
   # Convert the total size to MB and round to the nearst 100th
   $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
   $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
   # Get the total successful searches and total of all searches
   $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
   $allCount = $allSearchStats.Count
   $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
   # Totals Row
   $totalSearchStats = New-Object PSObject
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
   Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
   $allSearchStats += $totalSearchStats
   # Just get the columns we're interested in showing
   $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
   # Print the results to the screen
   $allSearchStatsPrime |ft -AutoSize -Wrap
   # Save the results to a CSV file
   if ($outputFile)
   {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
   }
   ```

2. <span data-ttu-id="99858-180">Em Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="99858-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="99858-181">No prompt **de ID do Grupo** de Pesquisa, digite um nome de grupo de pesquisa e pressione **Enter**; por exemplo  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="99858-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="99858-182">Lembre-se de que esse nome é sensível a minúsculas, portanto, você terá que digitá-lo da mesma maneira que você fez quando você correu o script na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="99858-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="99858-183">No caminho arquivo para salvar o relatório em um arquivo **CSV (deixe** em branco para apenas exibir o relatório), digite um nome de arquivo do caminho completo do nome do arquivo (incluindo .csv extensão de arquivo) se quiser salvar o relatório em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="99858-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="99858-184">nome do arquivo CSV, incluindo a extensão .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="99858-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="99858-185">Por exemplo, você pode digitar para salvá-lo no diretório atual ou digitar para  `ContosoCaseReport.csv`  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` salvá-lo em uma pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="99858-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="99858-186">Você também pode deixar o prompt em branco para exibir o relatório, mas não salvá-lo em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="99858-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="99858-187">Pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="99858-187">Press **Enter**.</span></span>

   <span data-ttu-id="99858-188">O script exibe o progresso da criação e execução das pesquisas.</span><span class="sxs-lookup"><span data-stu-id="99858-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="99858-189">Quando o script é concluído, o relatório é exibido.</span><span class="sxs-lookup"><span data-stu-id="99858-189">When the script is complete, the report is displayed.</span></span>

   ![Executar o relatório de pesquisa para exibir as estimativas para o grupo de pesquisa](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="99858-191">Se a mesma caixa de correio ou site for especificada como um local de conteúdo em mais de uma pesquisa em um grupo de pesquisa, a estimativa total de resultados no relatório (para o número de itens e o tamanho total) pode incluir resultados para os mesmos itens.</span><span class="sxs-lookup"><span data-stu-id="99858-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="99858-192">Isso porque a mesma mensagem de email ou documento será contada mais de uma vez se ela corresponde à consulta para pesquisas diferentes no grupo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99858-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="99858-193">Etapa 5: Executar o script para excluir as pesquisas</span><span class="sxs-lookup"><span data-stu-id="99858-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="99858-194">Como você pode estar criando muitas pesquisas, esse último script facilita a exclusão rápida das pesquisas criadas na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="99858-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="99858-195">Assim como os outros scripts, este também solicita a ID do Grupo de Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="99858-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="99858-196">Todas as pesquisas com a ID do Grupo de Pesquisa no nome da pesquisa serão excluídas quando você executar esse script.</span><span class="sxs-lookup"><span data-stu-id="99858-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="99858-197">Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="99858-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="99858-198">Salve o arquivo na mesma pasta em que você salvou os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="99858-198">Save the file to the same folder where you saved the other files.</span></span>

   ```Powershell
   # Delete all searches in a search group
   $searchGroup = Read-Host 'Search Group ID'
   Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
   }
   ```

2. <span data-ttu-id="99858-199">Em Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="99858-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="99858-200">No prompt **de ID do** Grupo de Pesquisa, digite um nome de grupo de pesquisa para as pesquisas que você deseja excluir e pressione **Enter**; por exemplo,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="99858-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="99858-201">Lembre-se de que esse nome é sensível a minúsculas, portanto, você terá que digitá-lo da mesma maneira que você fez quando você correu o script na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="99858-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="99858-202">O script exibe o nome de cada pesquisa excluída.</span><span class="sxs-lookup"><span data-stu-id="99858-202">The script displays the name of each search that's deleted.</span></span>

   ![Executar o script para excluir as pesquisas no grupo de pesquisa](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
