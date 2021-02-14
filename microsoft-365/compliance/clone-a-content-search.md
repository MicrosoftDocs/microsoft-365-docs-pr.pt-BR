---
title: Clonar uma Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/26/2017
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 7b40eeaa-544c-4534-b89b-9f79998e374c
ms.custom:
- seo-marvel-apr2020
description: Use o script do PowerShell neste artigo para clonar rapidamente uma Pesquisa de Conteúdo existente no centro de conformidade no Office 365 ou no Microsoft 365.
ms.openlocfilehash: 9bc9329d31ae27736bdcd399c555f5d70bb9c761
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357899"
---
# <a name="clone-a-content-search"></a><span data-ttu-id="6b811-103">Clonar uma Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="6b811-103">Clone a Content Search</span></span>

<span data-ttu-id="6b811-104">Criar uma Pesquisa de Conteúdo no centro de conformidade do Office 365 ou do Microsoft 365 que pesquisa muitas caixas de correio ou sites do SharePoint e do OneDrive for Business pode demorar um pouco.</span><span class="sxs-lookup"><span data-stu-id="6b811-104">Creating a Content Search in the compliance center in Office 365 or Microsoft 365 that searches many mailboxes or SharePoint and OneDrive for Business sites can take a while.</span></span> <span data-ttu-id="6b811-105">Especificar os sites a serem pesquisados também pode ser suscetível a erros se você usar uma URL de forma insu mesmo.</span><span class="sxs-lookup"><span data-stu-id="6b811-105">Specifying the sites to search can also be prone to errors if you mistype a URL.</span></span> <span data-ttu-id="6b811-106">Para evitar esses problemas, você pode usar o script do Windows PowerShell neste artigo para clonar rapidamente uma Pesquisa de Conteúdo existente.</span><span class="sxs-lookup"><span data-stu-id="6b811-106">To avoid these issues, you can use the Windows PowerShell script in this article to quickly clone an existing Content Search.</span></span> <span data-ttu-id="6b811-107">Quando você clona uma pesquisa, é criada uma nova pesquisa (com um nome diferente) que contém as mesmas propriedades (como os locais de conteúdo e a consulta de pesquisa) da pesquisa original.</span><span class="sxs-lookup"><span data-stu-id="6b811-107">When you clone a search, a new search (with a different name) is created that contains the same properties (such as the content locations and the search query) as the original search.</span></span> <span data-ttu-id="6b811-108">Em seguida, você pode editar a nova pesquisa alterando a consulta de palavra-chave ou o intervalo de datas e execute-a.</span><span class="sxs-lookup"><span data-stu-id="6b811-108">Then you can edit the new search by changing the keyword query or the date range, and run it.</span></span>
  
<span data-ttu-id="6b811-109">Por que clonar Pesquisas de Conteúdo?</span><span class="sxs-lookup"><span data-stu-id="6b811-109">Why clone Content Searches?</span></span>
  
- <span data-ttu-id="6b811-110">Para comparar os resultados de diferentes consultas de pesquisa de palavra-chave, execute nos mesmos locais de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6b811-110">To compare the results of different keyword search queries run on the same content locations.</span></span>
    
- <span data-ttu-id="6b811-111">Para salvá-lo de ter que reinserer um grande número de locais de conteúdo ao criar uma nova pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6b811-111">To save you from having to reenter a large number of content locations when you create a new search.</span></span>
    
- <span data-ttu-id="6b811-112">Para diminuir o tamanho dos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6b811-112">To decrease the size of the search results.</span></span> <span data-ttu-id="6b811-113">Por exemplo, se você tiver uma pesquisa que retorna muitos resultados para exportar, poderá clonar a pesquisa e adicionar uma condição de pesquisa com base em um intervalo de datas para reduzir o número de resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6b811-113">For example, if you have a search that returns too many results to export, you can clone the search and then add a search condition based on a date range to reduce the number of search results.</span></span>
  
## <a name="script-information"></a><span data-ttu-id="6b811-114">Informações de script</span><span class="sxs-lookup"><span data-stu-id="6b811-114">Script information</span></span>

- <span data-ttu-id="6b811-115">Você precisa ser um membro do grupo de funções Gerente de Descobertas eDiscovery no Centro de Conformidade e Segurança & para executar o script descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6b811-115">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the script described in this topic.</span></span>
    
- <span data-ttu-id="6b811-116">O script inclui tratamento mínimo de erros.</span><span class="sxs-lookup"><span data-stu-id="6b811-116">The script includes minimal error handling.</span></span> <span data-ttu-id="6b811-117">O principal objetivo do script é clonar rapidamente uma pesquisa de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="6b811-117">The primary purpose of the script is to quickly clone a content search.</span></span>
    
- <span data-ttu-id="6b811-118">O script cria uma nova Pesquisa de Conteúdo, mas não a inicia.</span><span class="sxs-lookup"><span data-stu-id="6b811-118">The script creates a new Content Search, but doesn't start it.</span></span>
    
- <span data-ttu-id="6b811-119">Esse script leva em conta se a Pesquisa de Conteúdo que você está clonando está associada a um caso de Descoberta eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="6b811-119">This script takes into account whether the Content Search that you're cloning is associated with an eDiscovery case.</span></span> <span data-ttu-id="6b811-120">Se a pesquisa estiver associada a uma ocorrência, a nova pesquisa também será associada ao mesmo caso.</span><span class="sxs-lookup"><span data-stu-id="6b811-120">If the search is associated with a case, the new search will also be associated with the same case.</span></span> <span data-ttu-id="6b811-121">Se a pesquisa existente não estiver associada a uma ocorrência, a  nova pesquisa será listada na página Pesquisa de conteúdo no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6b811-121">If the existing search isn't associated with a case, the new search will be listed on the **Content search** page in the compliance center.</span></span> 
    
- <span data-ttu-id="6b811-122">O script de exemplo fornecido neste tópico não tem suporte em nenhum serviço ou programa de suporte padrão da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6b811-122">The sample script provided in this topic isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="6b811-123">O script de amostra é fornecido COMO ESTÁ, sem garantia de nenhum tipo.</span><span class="sxs-lookup"><span data-stu-id="6b811-123">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="6b811-124">A Microsoft também se isenta de todas as garantias implícitas, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou adequação a uma finalidade específica.</span><span class="sxs-lookup"><span data-stu-id="6b811-124">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="6b811-125">Todo o risco decorrente do uso ou desempenho do script de amostra e da documentação permanece com você.</span><span class="sxs-lookup"><span data-stu-id="6b811-125">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="6b811-126">De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="6b811-126">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-clone-a-search"></a><span data-ttu-id="6b811-127">Etapa 1: Executar o script para clonar uma pesquisa</span><span class="sxs-lookup"><span data-stu-id="6b811-127">Step 1: Run the script to clone a search</span></span>

<span data-ttu-id="6b811-128">O script nesta etapa criará uma nova Pesquisa de Conteúdo clonando uma existente.</span><span class="sxs-lookup"><span data-stu-id="6b811-128">The script in this step will create a new Content Search by cloning an existing one.</span></span> <span data-ttu-id="6b811-129">Ao executar esse script, você será solicitado a obter as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6b811-129">When you run this script, you'll be prompted for the following information:</span></span>
  
- <span data-ttu-id="6b811-130">**Suas credenciais de usuário** – o script usará suas credenciais para se conectar ao Centro de Conformidade e Segurança da & da sua organização com o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b811-130">**Your user credentials** - The script will use your credentials to connect to the Security & Compliance Center for your organization with Windows PowerShell.</span></span> <span data-ttu-id="6b811-131">Conforme mencionado anteriormente, você precisa ser um membro do grupo de função gerente de descoberta de ediscovery no Centro de & de segurança para executar o script.</span><span class="sxs-lookup"><span data-stu-id="6b811-131">As previously stated, you have to be a member of the eDiscovery Manager role group in the Security & compCompliance Center to run the script.</span></span> 
    
- <span data-ttu-id="6b811-132">**O nome da pesquisa existente** - Esta é a Pesquisa de Conteúdo que você deseja clonar.</span><span class="sxs-lookup"><span data-stu-id="6b811-132">**The name of the existing search** - This is the Content Search that you want to clone.</span></span> 
    
- <span data-ttu-id="6b811-133">O nome da nova pesquisa que será **criada-** Se você deixar esse valor em branco, o script criará um nome para a nova pesquisa com base no nome da pesquisa que você está clonando.</span><span class="sxs-lookup"><span data-stu-id="6b811-133">**The name of the new search that will be created** - If you leave this value blank, the script will create a name for the new search that is based on the name of the search that you're cloning.</span></span> 
    
<span data-ttu-id="6b811-134">Para clonar uma pesquisa:</span><span class="sxs-lookup"><span data-stu-id="6b811-134">To clone a search:</span></span>
  
1. <span data-ttu-id="6b811-135">Salve o texto a seguir em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo .ps1; por exemplo, `CloneSearch.ps1` .</span><span class="sxs-lookup"><span data-stu-id="6b811-135">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CloneSearch.ps1`.</span></span>
    
  ```powershell
  # This PowerShell script clones an existing content search in the Security &amp; Compliance Center.
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

2. <span data-ttu-id="6b811-136">Abra o Windows PowerShell e vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="6b811-136">Open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="6b811-137">Execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6b811-137">Run the script; for example:</span></span>
    
    ```powershell
    .\CloneSearch.ps1
    ```

4. <span data-ttu-id="6b811-138">Quando solicitado a inserir suas credenciais, insira seu endereço de email e senha e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="6b811-138">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span>
    
5. <span data-ttu-id="6b811-139">Insira as informações a seguir quando solicitado pelo script.</span><span class="sxs-lookup"><span data-stu-id="6b811-139">Enter following information when prompted by the script.</span></span> <span data-ttu-id="6b811-140">Digite cada informação e pressione **Enter.**</span><span class="sxs-lookup"><span data-stu-id="6b811-140">Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="6b811-141">O nome da pesquisa existente.</span><span class="sxs-lookup"><span data-stu-id="6b811-141">The name of the existing search.</span></span>
    
    - <span data-ttu-id="6b811-142">O nome da nova pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6b811-142">The name of the new search.</span></span>
    
    <span data-ttu-id="6b811-143">O script cria a nova Pesquisa de Conteúdo, mas não a inicia.</span><span class="sxs-lookup"><span data-stu-id="6b811-143">The script creates the new Content Search, but doesn't start it.</span></span> <span data-ttu-id="6b811-144">Isso dá a você a oportunidade de editar e executar a pesquisa na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="6b811-144">This gives you a chance to edit and run the search in the next step.</span></span> <span data-ttu-id="6b811-145">Você pode exibir as propriedades da nova pesquisa executando o cmdlet **Get-ComplianceSearch** ou indo para a página Pesquisa de Conteúdo ou Descoberta Eletrônica no centro de conformidade, dependendo se a nova pesquisa está associada a uma ocorrência.  </span><span class="sxs-lookup"><span data-stu-id="6b811-145">You can view the properties of the new search by running the **Get-ComplianceSearch** cmdlet or by going to the **Content search** or **eDiscovery** page in the compliance center, depending on whether the new search is associated with a case.</span></span> 
  
## <a name="step-2-edit-and-run-the-cloned-search-in-the-compliance-center"></a><span data-ttu-id="6b811-146">Etapa 2: Editar e executar a pesquisa clonada no centro de conformidade</span><span class="sxs-lookup"><span data-stu-id="6b811-146">Step 2: Edit and run the cloned search in the compliance center</span></span>

<span data-ttu-id="6b811-147">Depois de executar o script para clonar uma Pesquisa de Conteúdo existente, a próxima etapa é ir para o centro de conformidade para editar e executar a nova pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6b811-147">After you run the script to clone an existing Content Search, the next step is to go to the compliance center to edit and run the new search.</span></span> <span data-ttu-id="6b811-148">Conforme mencionado anteriormente, você pode editar uma pesquisa alterando a consulta de pesquisa de palavra-chave e adicionando ou removendo condições de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6b811-148">As previously stated, you can edit a search by changing the keyword search query and adding or removing search conditions.</span></span> <span data-ttu-id="6b811-149">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="6b811-149">For more information, see:</span></span>
  
- [<span data-ttu-id="6b811-150">Pesquisa de Conteúdo no Office 365</span><span class="sxs-lookup"><span data-stu-id="6b811-150">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="6b811-151">Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="6b811-151">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="6b811-152">Casos de Descoberta eDiscovery</span><span class="sxs-lookup"><span data-stu-id="6b811-152">eDiscovery cases</span></span>](ediscovery-cases.md)
