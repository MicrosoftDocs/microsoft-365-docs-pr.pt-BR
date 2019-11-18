---
title: Clonar uma Pesquisa de Conteúdo
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
description: Use o script do Windows PowerShell neste artigo para clonar rapidamente uma pesquisa de conteúdo existente no centro de conformidade no Office 365 ou no Microsoft 365. Quando uma pesquisa é clonada, uma nova pesquisa (com um novo nome) é criada e contém as mesmas propriedades da pesquisa original. Em seguida, você pode editar a nova pesquisa (alterando a consulta de palavra-chave ou o intervalo de datas) e, em seguida, executá-la.
ms.openlocfilehash: 25aa5d6a1ba19f697a6ccf474e055faf6a19d6bd
ms.sourcegitcommit: 1d376287f6c1bf5174873e89ed4bf7bb15bc13f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38684944"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="40dc1-105">Clonar uma Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="40dc1-105">Clone a Content Search</span></span>

<span data-ttu-id="40dc1-106">Criar uma pesquisa de conteúdo no centro de conformidade no Office 365 ou no Microsoft 365 que pesquisa muitas caixas de correio ou sites do SharePoint e do OneDrive for Business pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="40dc1-106">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches a lot of mailboxes or SharePoint and OneDrive for Business sites can take awhile.</span></span> <span data-ttu-id="40dc1-107">A especificação dos sites a serem pesquisados também pode ser propensa a erros se você digitar indigitou uma URL.</span><span class="sxs-lookup"><span data-stu-id="40dc1-107">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="40dc1-108">Para evitar esses problemas, você pode usar o script do Windows PowerShell neste artigo para clonar rapidamente uma pesquisa de conteúdo existente.</span><span class="sxs-lookup"><span data-stu-id="40dc1-108">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="40dc1-109">Quando uma pesquisa é clonada, uma nova pesquisa (com um nome diferente) é criada, contendo as mesmas propriedades (como os locais de conteúdo e a consulta de pesquisa) como a pesquisa original.</span><span class="sxs-lookup"><span data-stu-id="40dc1-109">When a you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="40dc1-110">Em seguida, você pode editar a nova pesquisa (alterando a consulta de palavra-chave ou o intervalo de datas) e executá-la.</span><span class="sxs-lookup"><span data-stu-id="40dc1-110">Then you can edit the new search (by changing the keyword query or the date range) and run it.</span></span>
  
<span data-ttu-id="40dc1-111">Por que clonar pesquisas de conteúdo?</span><span class="sxs-lookup"><span data-stu-id="40dc1-111">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="40dc1-112">Para comparar os resultados das diferentes consultas de pesquisa de palavras-chave executadas nos mesmos locais de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="40dc1-112">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="40dc1-113">Para evitar que você insira novamente um grande número de locais de conteúdo ao criar uma nova pesquisa.</span><span class="sxs-lookup"><span data-stu-id="40dc1-113">To save you from having to re-enter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="40dc1-114">Para diminuir o tamanho dos resultados da pesquisa; por exemplo, se você tiver uma pesquisa que retorne muitos resultados para exportação, você pode clonar a pesquisa e, em seguida, adicionar um critério de pesquisa com base em um intervalo de datas para reduzir o número de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="40dc1-114">To decrease the size of the search results; for example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="40dc1-115">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="40dc1-115">Before you begin</span></span>

- <span data-ttu-id="40dc1-116">Você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de conformidade do & de segurança para executar o script descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="40dc1-116">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="40dc1-117">O script inclui o tratamento de erros mínimo.</span><span class="sxs-lookup"><span data-stu-id="40dc1-117">The script includes minimal error handling.</span></span> <span data-ttu-id="40dc1-118">O objetivo principal do script é clonar rapidamente uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="40dc1-118">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="40dc1-119">O script cria uma nova pesquisa de conteúdo, mas não a inicia.</span><span class="sxs-lookup"><span data-stu-id="40dc1-119">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="40dc1-120">Esse script leva em consideração se a pesquisa de conteúdo que você está clonando está associada a um caso de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="40dc1-120">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="40dc1-121">Se a pesquisa estiver associada a uma ocorrência, a nova pesquisa também será associada ao mesmo caso.</span><span class="sxs-lookup"><span data-stu-id="40dc1-121">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="40dc1-122">Se a pesquisa existente não estiver associada a uma ocorrência, a nova pesquisa será listada na página de **pesquisa de conteúdo** no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="40dc1-122">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="40dc1-123">Não há suporte para o script de exemplo fornecido neste tópico em qualquer serviço ou programa de suporte padrão da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="40dc1-123">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="40dc1-124">O script de exemplo é fornecido como está sem garantia de qualquer tipo.</span><span class="sxs-lookup"><span data-stu-id="40dc1-124">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="40dc1-125">A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica.</span><span class="sxs-lookup"><span data-stu-id="40dc1-125">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="40dc1-126">Todo o risco resultante do uso ou do desempenho do script de exemplo e da documentação permanece com você.</span><span class="sxs-lookup"><span data-stu-id="40dc1-126">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="40dc1-127">De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="40dc1-127">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="40dc1-128">Etapa 1: executar o script para clonar uma pesquisa</span><span class="sxs-lookup"><span data-stu-id="40dc1-128">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="40dc1-129">O script nesta etapa criará uma nova pesquisa de conteúdo clonando uma existente.</span><span class="sxs-lookup"><span data-stu-id="40dc1-129">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="40dc1-130">Ao executar esse script, você será solicitado a fornecer as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="40dc1-130">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="40dc1-131">**Suas credenciais de usuário** -o script usará suas credenciais para se conectar ao centro de conformidade de & de segurança para sua organização do Office 365 com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40dc1-131">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your Office 365 organization with Windows PowerShell.</span></span> <span data-ttu-id="40dc1-132">Conforme mencionado anteriormente, você precisa ser membro do grupo de função Gerenciador de descoberta eletrônica no centro de segurança & compCompliance para executar o script.</span><span class="sxs-lookup"><span data-stu-id="40dc1-132">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="40dc1-133">**O nome da pesquisa existente** -esta é a pesquisa de conteúdo que você deseja clonar.</span><span class="sxs-lookup"><span data-stu-id="40dc1-133">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="40dc1-134">**O nome da nova pesquisa que será criada** -se você deixar esse valor em branco, o script criará um nome para a nova pesquisa, com base no nome da pesquisa que você está clonando.</span><span class="sxs-lookup"><span data-stu-id="40dc1-134">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="40dc1-135">Para clonar uma pesquisa:</span><span class="sxs-lookup"><span data-stu-id="40dc1-135">To clone a search:</span></span>
  
1. <span data-ttu-id="40dc1-136">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `CloneSearch.ps1`.</span><span class="sxs-lookup"><span data-stu-id="40dc1-136">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing Content Search in the Office 365 security and compliance center.
  # Get login credentials from the user
  if(!$UserCredential)
  {
      $UserCredential = Get-Credential
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
      if (!$Session)
      {
          Write-Error "Couldn't create a remote PowerShell session."
          return
      }
      Import-PSSession $Session -AllowClobber -DisableNameChecking
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)"
  }
  # Ask for the name of the search you want to clone
  $searchName = Read-Host 'Enter the name of the search that you want to clone'
  # Ask for the name of the new search
  $newSearchName = Read-Host 'Enter a name for the new search [leave blank to automatically generate a name]'
  $originalSearch = Get-ComplianceSearch $searchName -EA SilentlyContinue
  # Make sure we have a valid search before continuing
  if(!$originalSearch)
  {
      Write-Error "Couldn't find search: $searchName"
      return
  }
  $searchNameCounter = 1
  # Find a suitable name for the new search
  while(!$newSearchName)
  {
      $newSearchName = $originalSearch.Name + "_" + $searchNameCounter
      $tempSearch = Get-ComplianceSearch $newSearchName -EA SilentlyContinue
      if ($tempSearch)
      {
          $newSearchName = $null
          $searchNameCounter++
      }
  }
  $caseName
  # Determine if the search is part of a case; if so get the case name
  if ($originalSearch.CaseId)
  {
      $searchCase = Get-ComplianceCase $originalSearch.CaseId
      $caseName = $searchCase.Name
  }
  # Need to cast this value as a Boolean the old fashion way
  $allowNotFoundExchangeLocationsEnabled = $false
  if ($originalSearch.AllowNotFoundExchangeLocationsEnabled)
  {
      $allowNotFoundExchangeLocationsEnabled = $true
  }
  $newSearch = New-ComplianceSearch -Name $newSearchName -AllowNotFoundExchangeLocationsEnabled $allowNotFoundExchangeLocationsEnabled -Case $caseName -ContentMatchQuery $originalSearch.ContentMatchQuery -Description $originalSearch.Description -ExchangeLocation $originalSearch.ExchangeLocation -ExchangeLocationExclusion $originalSearch.ExchangeLocationExclusion -Language $originalSearch.Language -SharePointLocation $originalSearch.SharePointLocation -SharePointLocationExclusion $originalSearch.SharePointLocationExclusion -PublicFolderLocation $originalSearch.PublicFolderLocation
  if ($newSearch)
  {
      Write-Host $newSearch.Name "was successfully created" -ForegroundColor Yellow
  }
  ```

2. <span data-ttu-id="40dc1-137">Abra o Windows PowerShell e vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="40dc1-137">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="40dc1-138">Executar o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="40dc1-138">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="40dc1-139">Quando solicitar suas credenciais, insira seu endereço de email e senha e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="40dc1-139">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="40dc1-140">Insira as informações a seguir quando solicitado pelo script.</span><span class="sxs-lookup"><span data-stu-id="40dc1-140">Enter following information when prompted by the script.</span></span> <span data-ttu-id="40dc1-141">Digite cada informação e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="40dc1-141">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="40dc1-142">O nome da pesquisa existente.</span><span class="sxs-lookup"><span data-stu-id="40dc1-142">The name of the existing search.</span></span>
    
    - <span data-ttu-id="40dc1-143">O nome da nova pesquisa.</span><span class="sxs-lookup"><span data-stu-id="40dc1-143">The name of the new search.</span></span>
    
    <span data-ttu-id="40dc1-144">O script cria a nova pesquisa de conteúdo, mas não a inicia.</span><span class="sxs-lookup"><span data-stu-id="40dc1-144">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="40dc1-145">Isso lhe dá a oportunidade de editar e executar a pesquisa na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="40dc1-145">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="40dc1-146">Você pode exibir as propriedades da nova pesquisa executando o cmdlet **Get-ComplianceSearch** ou indo para a página de **pesquisa de conteúdo** ou **descoberta eletrônica** no centro de conformidade, dependendo se a nova pesquisa está ou não associada a um caso.</span><span class="sxs-lookup"><span data-stu-id="40dc1-146">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether or not the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="40dc1-147">Etapa 2: editar e executar a pesquisa clonada no centro de conformidade</span><span class="sxs-lookup"><span data-stu-id="40dc1-147">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="40dc1-148">Depois de executar o script para clonar uma pesquisa de conteúdo existente, a próxima etapa é usar o centro de conformidade para editar e executar a nova pesquisa.</span><span class="sxs-lookup"><span data-stu-id="40dc1-148">After the you've run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="40dc1-149">Conforme mencionado anteriormente, você pode editar uma pesquisa, alterando a consulta de pesquisa de palavra-chave e adicionando ou removendo condições de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="40dc1-149">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="40dc1-150">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="40dc1-150">For more information, see:</span></span>
  
- [<span data-ttu-id="40dc1-151">Pesquisa de Conteúdo no Office 365</span><span class="sxs-lookup"><span data-stu-id="40dc1-151">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="40dc1-152">Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="40dc1-152">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="40dc1-153">ocorrências de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="40dc1-153">eDiscovery cases</span></span>](ediscovery-cases.md)
