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
description: Saiba como automatizar tarefas de pesquisa de conteúdo, como a criação de pesquisas e a execução de relatórios por meio de scripts do PowerShell no centro de conformidade de & de segurança no Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c467b8ebc5ad3171347b23cad47f563b3634ee29
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546857"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="f785e-103">Criar, gerar relatórios sobre e excluir várias Pesquisas de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="f785e-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="f785e-104">Criar e relatar rapidamente pesquisas de descoberta é geralmente uma etapa importante na descoberta eletrônica e investigações quando você está tentando saber mais sobre os dados subjacentes, e a riqueza e a qualidade das pesquisas.</span><span class="sxs-lookup"><span data-stu-id="f785e-104">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches.</span></span> <span data-ttu-id="f785e-105">Para ajudá-lo a fazer isso, o PowerShell do centro de conformidade e segurança & oferece um conjunto de cmdlets para automatizar tarefas de pesquisa de conteúdo demoradas.</span><span class="sxs-lookup"><span data-stu-id="f785e-105">To help you do this, the Security & Compliance Center PowerShell offers a set of cmdlets to automate time-consuming Content Search tasks.</span></span> <span data-ttu-id="f785e-106">Esses scripts fornecem uma maneira rápida e fácil de criar várias pesquisas e, em seguida, executar relatórios dos resultados estimados da pesquisa que podem ajudá-lo a determinar a quantidade de dados em questão.</span><span class="sxs-lookup"><span data-stu-id="f785e-106">These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question.</span></span> <span data-ttu-id="f785e-107">Você também pode usar os scripts para criar versões diferentes de pesquisas para comparar os resultados que cada um produz.</span><span class="sxs-lookup"><span data-stu-id="f785e-107">You can also use the scripts to create different versions of searches to compare the results each one produces.</span></span> <span data-ttu-id="f785e-108">Esses scripts podem ajudá-lo a identificar e analisar os dados de forma rápida e eficiente.</span><span class="sxs-lookup"><span data-stu-id="f785e-108">These scripts can help you to quickly and efficiently identify and cull your data.</span></span>

## <a name="before-you-create-a-content-search"></a><span data-ttu-id="f785e-109">Antes de criar uma pesquisa de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f785e-109">Before you create a Content Search</span></span>

- <span data-ttu-id="f785e-110">Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade do & de segurança para executar os scripts descritos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f785e-110">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the scripts that are described in this topic.</span></span>

- <span data-ttu-id="f785e-111">Para coletar uma lista das URLs para os sites do OneDrive for Business em sua organização que você pode adicionar ao arquivo CSV na etapa 1, consulte [criar uma lista de todos os locais do onedrive em sua organização](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span><span class="sxs-lookup"><span data-stu-id="f785e-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://docs.microsoft.com/onedrive/list-onedrive-urls).</span></span>

- <span data-ttu-id="f785e-112">Certifique-se de salvar todos os arquivos que você criou neste tópico para a mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="f785e-112">Be sure to save all the files that you create in this topic to the same folder.</span></span> <span data-ttu-id="f785e-113">Isso facilitará a execução dos scripts.</span><span class="sxs-lookup"><span data-stu-id="f785e-113">That will make it easier to run the scripts.</span></span>

- <span data-ttu-id="f785e-114">Os scripts incluem um tratamento de erros mínimo.</span><span class="sxs-lookup"><span data-stu-id="f785e-114">The scripts include minimal error handling.</span></span> <span data-ttu-id="f785e-115">Seu objetivo principal é criar, relatar e excluir rapidamente várias pesquisas de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f785e-115">Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>

- <span data-ttu-id="f785e-p104">Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="f785e-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="f785e-121">Etapa 1: criar um arquivo CSV que contenha informações sobre as pesquisas que você deseja executar</span><span class="sxs-lookup"><span data-stu-id="f785e-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="f785e-122">O arquivo de valor separado por vírgula (CSV) que você criou nesta etapa contém uma linha para cada usuário que deseja pesquisar.</span><span class="sxs-lookup"><span data-stu-id="f785e-122">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search.</span></span> <span data-ttu-id="f785e-123">Você pode pesquisar a caixa de correio do Exchange Online do usuário (que inclui a caixa de correio de arquivo morto, se ela estiver habilitada) e seu site do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="f785e-123">You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site.</span></span> <span data-ttu-id="f785e-124">Ou você pode pesquisar apenas a caixa de correio ou o site do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="f785e-124">Or you can search just the mailbox or the OneDrive for Business site.</span></span> <span data-ttu-id="f785e-125">Você também pode pesquisar qualquer site em sua organização do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f785e-125">You can also search any site in your SharePoint Online organization.</span></span> <span data-ttu-id="f785e-126">O script executado na etapa 3 criará uma pesquisa separada para cada linha no arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f785e-126">The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span>

1. <span data-ttu-id="f785e-127">Copie e cole o texto a seguir em um arquivo. txt usando o bloco de notas.</span><span class="sxs-lookup"><span data-stu-id="f785e-127">Copy and paste the following text into a .txt file using NotePad.</span></span> <span data-ttu-id="f785e-128">Salve esse arquivo em uma pasta no computador local.</span><span class="sxs-lookup"><span data-stu-id="f785e-128">Save this file to a folder on your local computer.</span></span> <span data-ttu-id="f785e-129">Você também salvará outros scripts nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="f785e-129">You'll save the other scripts to this folder as well.</span></span>

   ```text
   ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
   sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
   ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
   ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
   ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
   ```

   <span data-ttu-id="f785e-130">A primeira linha, ou linha de cabeçalho, do arquivo lista os parâmetros que serão usados pelo cmdlet **New-ComplianceSearch** (no script na etapa 3) para criar novas pesquisas de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f785e-130">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches.</span></span> <span data-ttu-id="f785e-131">Os nomes dos parâmetros são separados por vírgula.</span><span class="sxs-lookup"><span data-stu-id="f785e-131">Each parameter name is separated by a comma.</span></span> <span data-ttu-id="f785e-132">Certifique-se de que não haja espaços na linha de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="f785e-132">Make sure there aren't any spaces in the header row.</span></span> <span data-ttu-id="f785e-133">Cada linha sob a linha de cabeçalho representa os valores de parâmetro de cada pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f785e-133">Each row under the header row represents the parameter values for each search.</span></span> <span data-ttu-id="f785e-134">Certifique-se de substituir os dados de espaço reservado no arquivo CSV pelos dados reais.</span><span class="sxs-lookup"><span data-stu-id="f785e-134">Be sure to replace the placeholder data in the CSV file with your actual data.</span></span>

2. <span data-ttu-id="f785e-135">Abra o arquivo. txt no Excel e use as informações da tabela a seguir para editar o arquivo com as informações de cada pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f785e-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span>

   ****

   |<span data-ttu-id="f785e-136">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="f785e-136">Parameter</span></span>|<span data-ttu-id="f785e-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="f785e-137">Description</span></span>|
   |---|---|
   |`ExchangeLocation`|<span data-ttu-id="f785e-138">O endereço SMTP da caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="f785e-138">The SMTP address of the user's mailbox.</span></span>|
   |`SharePointLocation`|<span data-ttu-id="f785e-139">A URL do site do OneDrive for Business do usuário ou a URL de qualquer site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f785e-139">The URL for the user's OneDrive for Business site or the URL for any site in your organization.</span></span> <span data-ttu-id="f785e-140">Para a URL dos sites do OneDrive for Business, use este formato: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com ` .</span><span class="sxs-lookup"><span data-stu-id="f785e-140">For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `.</span></span> <span data-ttu-id="f785e-141">Por exemplo, `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span><span class="sxs-lookup"><span data-stu-id="f785e-141">For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.</span></span>|
   |`ContentMatchQuery`|<span data-ttu-id="f785e-142">A consulta de pesquisa para a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f785e-142">The search query for the search.</span></span> <span data-ttu-id="f785e-143">Para obter mais informações sobre como criar uma consulta de pesquisa, consulte [keyword queries and Search Conditions for Content Search](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="f785e-143">For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>|
   |`StartDate`|<span data-ttu-id="f785e-144">Para email, a data de ou após uma mensagem foi recebida por um destinatário ou enviada pelo remetente.</span><span class="sxs-lookup"><span data-stu-id="f785e-144">For email, the date on or after a message was received by a recipient or sent by the sender.</span></span> <span data-ttu-id="f785e-145">Para documentos em sites do SharePoint ou do OneDrive for Business, a data da última modificação de um documento.</span><span class="sxs-lookup"><span data-stu-id="f785e-145">For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>|
   |`EndDate`|<span data-ttu-id="f785e-146">Para email, a data de ou antes de uma mensagem foi enviada por um enviado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f785e-146">For email, the date on or before a message was sent by a sent by the user.</span></span> <span data-ttu-id="f785e-147">Para documentos em sites do SharePoint ou do OneDrive for Business, a data em ou antes da última modificação de um documento.</span><span class="sxs-lookup"><span data-stu-id="f785e-147">For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>|
   |

3. <span data-ttu-id="f785e-148">Salve o arquivo do Excel como um arquivo CSV em uma pasta no computador local.</span><span class="sxs-lookup"><span data-stu-id="f785e-148">Save the Excel file as a CSV file to a folder on your local computer.</span></span> <span data-ttu-id="f785e-149">O script criado na etapa 3 usará as informações neste arquivo CSV para criar as pesquisas.</span><span class="sxs-lookup"><span data-stu-id="f785e-149">The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span>

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="f785e-150">Etapa 2: Conectar-se ao Centro de Segurança e Conformidade usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="f785e-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="f785e-151">A próxima etapa é conectar-se ao Centro de Segurança e Conformidade da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f785e-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="f785e-152">Para obter instruções passo a passo, confira [Conectar-se ao Centro de Segurança e Conformidade no PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="f785e-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="f785e-153">Etapa 3: executar o script para criar e iniciar as pesquisas</span><span class="sxs-lookup"><span data-stu-id="f785e-153">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="f785e-154">O script nesta etapa criará uma pesquisa de conteúdo separada para cada linha no arquivo CSV que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f785e-154">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1.</span></span> <span data-ttu-id="f785e-155">Ao executar esse script, você será solicitado a fornecer dois valores:</span><span class="sxs-lookup"><span data-stu-id="f785e-155">When you run this script, you'll be prompted for two values:</span></span>

- <span data-ttu-id="f785e-156">**ID do grupo de pesquisa** -este nome oferece uma maneira fácil de organizar as pesquisas criadas a partir do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f785e-156">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file.</span></span> <span data-ttu-id="f785e-157">Cada pesquisa criada é nomeada com a ID do grupo de pesquisa e, em seguida, um número é acrescentado ao nome da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f785e-157">Each search that's created is named with the Search Group ID, and then a number is appended to the search name.</span></span> <span data-ttu-id="f785e-158">Por exemplo, se você inserir **ContosoCase** para a ID do grupo de pesquisa, as pesquisas serão nomeadas **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f785e-158">For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on.</span></span> <span data-ttu-id="f785e-159">Observe que o nome digitado diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f785e-159">Note that the name you type is case sensitive.</span></span> <span data-ttu-id="f785e-160">Quando você usa a ID do grupo de pesquisa na etapa 4 e a etapa 5, é necessário usar o mesmo caso que você fez ao criá-la.</span><span class="sxs-lookup"><span data-stu-id="f785e-160">When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span>

- <span data-ttu-id="f785e-161">**Arquivo CSV** -o nome do arquivo CSV que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f785e-161">**CSV file** - The name of the CSV file that you created in Step 1.</span></span> <span data-ttu-id="f785e-162">Certifique-se de incluir o uso do nome de arquivo completo, inclua a extensão de arquivo. csv; por exemplo,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="f785e-162">Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

<span data-ttu-id="f785e-163">Para executar o script:</span><span class="sxs-lookup"><span data-stu-id="f785e-163">To run the script:</span></span>

1. <span data-ttu-id="f785e-164">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `CreateSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="f785e-164">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`.</span></span> <span data-ttu-id="f785e-165">Salve o arquivo na mesma pasta onde você salvou os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="f785e-165">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="f785e-166">No Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f785e-166">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\CreateSearches.ps1
   ```

3. <span data-ttu-id="f785e-167">No prompt **ID do grupo de pesquisa** , digite um nome de grupo de pesquisa e pressione **Enter**. por exemplo,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="f785e-167">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="f785e-168">Lembre-se de que esse nome diferencia maiúsculas de minúsculas, portanto, você terá que digitá-lo da mesma maneira nas etapas subsequentes.</span><span class="sxs-lookup"><span data-stu-id="f785e-168">Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>

4. <span data-ttu-id="f785e-169">No prompt de **arquivo CSV de origem** , digite o nome do arquivo CSV, incluindo a extensão de arquivo. csv; por exemplo,  `ContosoCase.csv` .</span><span class="sxs-lookup"><span data-stu-id="f785e-169">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>

5. <span data-ttu-id="f785e-170">Pressione **Enter** para continuar executando o script.</span><span class="sxs-lookup"><span data-stu-id="f785e-170">Press **Enter** to continue running the script.</span></span>

   <span data-ttu-id="f785e-171">O script exibe o progresso da criação e execução das pesquisas.</span><span class="sxs-lookup"><span data-stu-id="f785e-171">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="f785e-172">Quando o script é concluído, ele retorna ao prompt.</span><span class="sxs-lookup"><span data-stu-id="f785e-172">When the script is complete, it returns to the prompt.</span></span>

   ![Exemplo de saída da execução do script para criar várias pesquisas de conformidade](../media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)

## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="f785e-174">Etapa 4: executar o script para relatar as estimativas de pesquisa</span><span class="sxs-lookup"><span data-stu-id="f785e-174">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="f785e-175">Após criar as pesquisas, a próxima etapa é executar um script que exibe um relatório simples do número de visitas de pesquisa para cada pesquisa criada na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="f785e-175">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3.</span></span> <span data-ttu-id="f785e-176">O relatório também inclui o tamanho dos resultados de cada pesquisa e o número total de acertos e o tamanho total de todas as pesquisas.</span><span class="sxs-lookup"><span data-stu-id="f785e-176">The report also includes the size of results for each search, and the total number of hits and total size of all searches.</span></span> <span data-ttu-id="f785e-177">Ao executar o script de relatório, você será solicitado a solicitar o ID do grupo de pesquisa e um nome de arquivo CSV se quiser salvar o relatório em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f785e-177">When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>

1. <span data-ttu-id="f785e-178">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `SearchReport.ps1` .</span><span class="sxs-lookup"><span data-stu-id="f785e-178">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`.</span></span> <span data-ttu-id="f785e-179">Salve o arquivo na mesma pasta onde você salvou os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="f785e-179">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="f785e-180">No Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f785e-180">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\SearchReport.ps1
   ```

3. <span data-ttu-id="f785e-181">No prompt **ID do grupo de pesquisa** , digite um nome de grupo de pesquisa e pressione **Enter**. por exemplo  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="f785e-181">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`.</span></span> <span data-ttu-id="f785e-182">Lembre-se de que esse nome diferencia maiúsculas de minúsculas, portanto, você terá que digitá-la da mesma maneira que fez ao executar o script na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="f785e-182">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

4. <span data-ttu-id="f785e-183">No **caminho do arquivo para salvar o relatório em um arquivo CSV (deixe em branco para exibir o relatório)** , digite um nome de arquivo completo para o caminho de arquivo (incluindo a extensão de arquivo. csv) se quiser salvar o relatório em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f785e-183">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file.</span></span> <span data-ttu-id="f785e-184">nome do arquivo CSV, incluindo a extensão de arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="f785e-184">name of the CSV file, including the .csv file extension.</span></span> <span data-ttu-id="f785e-185">Por exemplo, você poderia digitar  `ContosoCaseReport.csv` para salvá-lo no diretório atual ou poderia digitar  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` para salvá-lo em uma pasta diferente.</span><span class="sxs-lookup"><span data-stu-id="f785e-185">For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder.</span></span> <span data-ttu-id="f785e-186">Você também pode deixar o prompt em branco para exibir o relatório, mas não salvá-lo em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="f785e-186">You can also leave the prompt blank to display the report but not save it to a file.</span></span>

5. <span data-ttu-id="f785e-187">Pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="f785e-187">Press **Enter**.</span></span>

   <span data-ttu-id="f785e-188">O script exibe o progresso da criação e execução das pesquisas.</span><span class="sxs-lookup"><span data-stu-id="f785e-188">The script displays the progress of creating and running the searches.</span></span> <span data-ttu-id="f785e-189">Quando o script estiver concluído, o relatório será exibido.</span><span class="sxs-lookup"><span data-stu-id="f785e-189">When the script is complete, the report is displayed.</span></span>

   ![Executar o relatório de pesquisa para exibir as estimativas para o grupo de pesquisa](../media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)

> [!NOTE]
> <span data-ttu-id="f785e-191">Se a mesma caixa de correio ou site for especificado como um local de conteúdo em mais de uma pesquisa em um grupo de pesquisa, a estimativa de resultados total no relatório (para o número de itens e o tamanho total) poderá incluir resultados para os mesmos itens.</span><span class="sxs-lookup"><span data-stu-id="f785e-191">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items.</span></span> <span data-ttu-id="f785e-192">Isso ocorre porque o mesmo documento ou mensagem de email será contado mais de uma vez se corresponder à consulta de pesquisas diferentes no grupo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f785e-192">That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span>

## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="f785e-193">Etapa 5: executar o script para excluir as pesquisas</span><span class="sxs-lookup"><span data-stu-id="f785e-193">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="f785e-194">Como você pode estar criando muitas pesquisas, esse último script simplesmente facilita a exclusão rápida das pesquisas que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="f785e-194">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3.</span></span> <span data-ttu-id="f785e-195">Assim como os outros scripts, isso também solicita a ID do grupo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f785e-195">Like the other scripts, this one also prompts you for the Search Group ID.</span></span> <span data-ttu-id="f785e-196">Todas as pesquisas com a ID do grupo de pesquisa no nome da pesquisa serão excluídas quando você executar esse script.</span><span class="sxs-lookup"><span data-stu-id="f785e-196">All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span>

1. <span data-ttu-id="f785e-197">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `DeleteSearches.ps1` .</span><span class="sxs-lookup"><span data-stu-id="f785e-197">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`.</span></span> <span data-ttu-id="f785e-198">Salve o arquivo na mesma pasta onde você salvou os outros arquivos.</span><span class="sxs-lookup"><span data-stu-id="f785e-198">Save the file to the same folder where you saved the other files.</span></span>

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

2. <span data-ttu-id="f785e-199">No Windows PowerShell, vá para a pasta onde você salvou o script na etapa anterior e execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f785e-199">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>

   ```Powershell
   .\DeleteSearches.ps1
   ```

3. <span data-ttu-id="f785e-200">No prompt **ID do grupo de pesquisa** , digite um nome de grupo de pesquisa para as pesquisas que você deseja excluir e pressione **Enter**. por exemplo,  `ContosoCase` .</span><span class="sxs-lookup"><span data-stu-id="f785e-200">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`.</span></span> <span data-ttu-id="f785e-201">Lembre-se de que esse nome diferencia maiúsculas de minúsculas, portanto, você terá que digitá-la da mesma maneira que fez ao executar o script na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="f785e-201">Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>

   <span data-ttu-id="f785e-202">O script exibe o nome de cada pesquisa que foi excluída.</span><span class="sxs-lookup"><span data-stu-id="f785e-202">The script displays the name of each search that's deleted.</span></span>

   ![Executar o script para excluir as pesquisas no grupo de pesquisa](../media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
