---
title: Diretrizes de pacote de teste
description: Revisar as diretrizes em torno do pacote de teste
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: b6842f793627bddeab842bbd9570c9c3481699a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322452"
---
# <a name="test-package-guidelines"></a><span data-ttu-id="3ab25-103">Diretrizes de pacote de teste</span><span class="sxs-lookup"><span data-stu-id="3ab25-103">Test package guidelines</span></span>

## <a name="1---script-referencing"></a><span data-ttu-id="3ab25-104">1. Referência de script</span><span class="sxs-lookup"><span data-stu-id="3ab25-104">1.   Script referencing</span></span>

<span data-ttu-id="3ab25-105">Quando você carrega um arquivo .zip no portal, descompaímos todo o conteúdo desse arquivo em uma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="3ab25-105">When you upload a .zip file to the portal, we unzip all the content of that file into a root folder.</span></span> <span data-ttu-id="3ab25-106">Você não precisa escrever nenhum código para fazer essa operação inicial de descomplável.</span><span class="sxs-lookup"><span data-stu-id="3ab25-106">You do not need to write any code to do this initial unzip operation.</span></span> <span data-ttu-id="3ab25-107">Você também pode fazer referência a qualquer arquivo no .zip usando o caminho em relação ao arquivo zip carregado.</span><span class="sxs-lookup"><span data-stu-id="3ab25-107">You also can reference any file within the .zip by using the path relative to the zip file uploaded.</span></span>

<span data-ttu-id="3ab25-108">No exemplo abaixo, mostramos como você pode fazer referência aos binários/scripts do campo de entrada na guia Tarefas. O texto em azul deve ser inserido no campo **Caminho do script** sem **aspas.**</span><span class="sxs-lookup"><span data-stu-id="3ab25-108">In the example below, we show how you can reference your binaries/scripts from the input field in the Tasks tab. The text in blue should be entered into the **Script path** field **without the quotation marks.**</span></span>

<span data-ttu-id="3ab25-109">É importante que você esteja ciente do conteúdo em seu arquivo zip antes de carregar.</span><span class="sxs-lookup"><span data-stu-id="3ab25-109">It is important you are aware of the content within your zip file before uploading it.</span></span> <span data-ttu-id="3ab25-110">Muitas vezes, ao fazer o zipping de uma pasta, o computador local criará uma pasta principal sob o arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="3ab25-110">Often when zipping a folder, your local machine will create a main folder underneath the zip file.</span></span> <span data-ttu-id="3ab25-111">Nesse caso, a referência será mostrada em **negrito** abaixo:</span><span class="sxs-lookup"><span data-stu-id="3ab25-111">In this case, the referencing will be as shown in **bold** below:</span></span>

 <span data-ttu-id="3ab25-112">**Contoso_App_Folder.zip**</span><span class="sxs-lookup"><span data-stu-id="3ab25-112">**Contoso_App_Folder.zip**</span></span>
~~~ 
├── Contoso_App_Folder

│   ├── file1.exe

│   ├── ScriptX.ps1

│   ├── folder1

│        ├── file3.exe

│        ├── script.ps1
~~~

  - <span data-ttu-id="3ab25-113">ScriptX.ps1 – **"Contoso_App_Folder/ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3ab25-113">ScriptX.ps1 – **“Contoso_App_Folder/ScriptX.ps1”**</span></span>
  - <span data-ttu-id="3ab25-114">Script.ps1 – **"Contoso_App_Folder/folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3ab25-114">Script.ps1 – **“Contoso_App_Folder/folder1/script.ps1”**</span></span>

<span data-ttu-id="3ab25-115">Outras vezes, seu arquivo zip pode ter seus arquivos ou conteúdo logo abaixo dele ou seja, nenhuma pasta de nível 2nd:</span><span class="sxs-lookup"><span data-stu-id="3ab25-115">Other times, your zip file may have your files or content right underneath it i.e. no 2nd-level folder:</span></span>

 <span data-ttu-id="3ab25-116">**Zip_file_uploaded.zip**</span><span class="sxs-lookup"><span data-stu-id="3ab25-116">**Zip_file_uploaded.zip**</span></span>
~~~ 
├── file1.exe

├── ScriptX.ps1

├── folder1

│   ├── file3.exe

│   ├── script.ps1
~~~
  - <span data-ttu-id="3ab25-117">ScriptX.ps1 – **"ScriptX.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3ab25-117">ScriptX.ps1 – **“ScriptX.ps1”**</span></span>
  - <span data-ttu-id="3ab25-118">Script.ps1 – **"folder1/script.ps1"**</span><span class="sxs-lookup"><span data-stu-id="3ab25-118">Script.ps1 – **“folder1/script.ps1”**</span></span>
  
## <a name="2---script-execution"></a><span data-ttu-id="3ab25-119">2. Execução de script</span><span class="sxs-lookup"><span data-stu-id="3ab25-119">2.   Script execution</span></span>

<span data-ttu-id="3ab25-120">**Testes in-locar:** O pacote de aplicativos precisa conter pelo menos três scripts do PowerShell que executarão a instalação autônoma, o lançamento e o fechamento do aplicativo e suas dependências.</span><span class="sxs-lookup"><span data-stu-id="3ab25-120">**Out-of-Box tests:** The application package needs to contain at least three PowerShell scripts that will execute unattended installing, launching, and closing of the application and its dependencies.</span></span> <span data-ttu-id="3ab25-121">Cada script deve manipular a verificação de seus próprios pré-requisitos, validando-o com êxito, bem como limpando depois de si mesmo (se necessário).</span><span class="sxs-lookup"><span data-stu-id="3ab25-121">Each script should handle checking its own prerequisites, validating it succeeded, as well as cleaning up after itself (if necessary).</span></span>

<span data-ttu-id="3ab25-122">**Testes funcionais:** O pacote do aplicativo precisa conter pelo menos um script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ab25-122">**Functional tests:** The application package needs to contain at least one PowerShell script.</span></span> <span data-ttu-id="3ab25-123">Quando mais de um script é fornecido, os scripts são executados em sequência de carregamento e uma falha em um script específico impedirá a execução de scripts subsequentes.</span><span class="sxs-lookup"><span data-stu-id="3ab25-123">Where more than one script is provided, the scripts are run in upload sequence and a failure in a particular script will stop subsequent scripts from executing.</span></span>

### <a name="script-requirements"></a><span data-ttu-id="3ab25-124">Requisitos de script</span><span class="sxs-lookup"><span data-stu-id="3ab25-124">Script requirements</span></span>

<span data-ttu-id="3ab25-125">• PowerShell Versão 5.1+</span><span class="sxs-lookup"><span data-stu-id="3ab25-125">•   PowerShell Version 5.1+</span></span>     

<span data-ttu-id="3ab25-126">• Execução autônoma</span><span class="sxs-lookup"><span data-stu-id="3ab25-126">•   Unattended execution</span></span>    

<span data-ttu-id="3ab25-127">• Código de retorno de erro</span><span class="sxs-lookup"><span data-stu-id="3ab25-127">•   Error return code</span></span>               

<span data-ttu-id="3ab25-128">• Validar o sucesso</span><span class="sxs-lookup"><span data-stu-id="3ab25-128">•   Validate success</span></span>            

<span data-ttu-id="3ab25-129">• Fazer logoff para a pasta de log específica do script</span><span class="sxs-lookup"><span data-stu-id="3ab25-129">•   Logging to script specific log folder</span></span>

<span data-ttu-id="3ab25-130">Cada script precisa ser executado completamente sem supervisão para executar com êxito no pipeline de teste.</span><span class="sxs-lookup"><span data-stu-id="3ab25-130">Each script needs to run completely unattended to successfully execute in the test pipeline.</span></span>

> [!Note]
> <span data-ttu-id="3ab25-131">Os scripts devem retornar "0" na conclusão bem-sucedida e um código de erro diferente de zero se ocorrer algum erro durante a execução.</span><span class="sxs-lookup"><span data-stu-id="3ab25-131">Scripts should return “0” on successful completion and a non-zero error code if any error occurs during execution.</span></span>

<span data-ttu-id="3ab25-132">Cada script deve validar se ele foi realizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="3ab25-132">Each script should validate that it ran successfully.</span></span> <span data-ttu-id="3ab25-133">Por exemplo</span><span class="sxs-lookup"><span data-stu-id="3ab25-133">E.g.</span></span> <span data-ttu-id="3ab25-134">o script de instalação deve verificar a existência de determinados binários e/ou chaves de registro no sistema, depois que o binário do instalador terminar de executar para garantir com um grau razoável de confiança de que a instalação foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="3ab25-134">the install script should check for the existence of certain binaries and/or registry keys on the system, after the installer binary finishes executing to ensure with a reasonable degree of confidence that the installation was successful.</span></span> 

<span data-ttu-id="3ab25-135">Isso é necessário para diagnosticar corretamente onde ocorrem erros durante uma executar um teste, por exemplo, não é possível instalar o aplicativo com êxito em vez de não poder iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3ab25-135">This is necessary to properly diagnose where errors occur during a test run, e.g. unable to install the application successfully versus being unable to launch it.</span></span>

> [!Important]
> <span data-ttu-id="3ab25-136">**Evite o seguinte:** Os scripts não devem reiniciar o computador, se uma reinicialização for necessária, especifique isso durante o carregamento de seus scripts.</span><span class="sxs-lookup"><span data-stu-id="3ab25-136">**Avoid the following:** Scripts should not reboot the machine, if a reboot is necessary please specify this during the upload of your scripts.</span></span>

## <a name="3---log-collection"></a><span data-ttu-id="3ab25-137">3. Coleção Log</span><span class="sxs-lookup"><span data-stu-id="3ab25-137">3.   Log collection</span></span>

<span data-ttu-id="3ab25-138">Cada script deve gerar todos os logs gerados em uma pasta chamada ```logs``` .</span><span class="sxs-lookup"><span data-stu-id="3ab25-138">Each script should output any logs it generates into a folder named ```logs```.</span></span> <span data-ttu-id="3ab25-139">Todas as pastas no diretório nomeado serão copiadas e ```logs``` apresentadas para download na ```Test Results``` página.</span><span class="sxs-lookup"><span data-stu-id="3ab25-139">All folders in the directory named ```logs``` will be copied and presented for download on the ```Test Results``` page.</span></span>

<span data-ttu-id="3ab25-140">Por exemplo, o script de instalação (que pode estar localizado no diretório **App/scripts/install)** pode fazer seus logs para: **logs/install.log**, de forma que o log final estará em: **Apps/scripts/install/logs/install.log**</span><span class="sxs-lookup"><span data-stu-id="3ab25-140">For example, the installation script (which may be located in the **App/scripts/install** directory) can output its logs to: **logs/install.log**, such that the final log will be at: **Apps/scripts/install/logs/install.log**</span></span>

<span data-ttu-id="3ab25-141">O sistema irá buscar o arquivo juntamente com outros arquivos em outras pastas e ```install.log``` ```logs``` colá-lo para download.</span><span class="sxs-lookup"><span data-stu-id="3ab25-141">The system will pick up the ```install.log``` file along with other files within other ```logs``` folders and collate it for download.</span></span>


## <a name="4---application-binaries"></a><span data-ttu-id="3ab25-142">4. Binários de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3ab25-142">4.   Application binaries</span></span>

<span data-ttu-id="3ab25-143">Quaisquer binários e dependências devem ser incluídos no arquivo zip único.</span><span class="sxs-lookup"><span data-stu-id="3ab25-143">Any binaries and dependencies should be included in the single zip file.</span></span> 

<span data-ttu-id="3ab25-144">Eles devem incluir tudo o que é necessário para a instalação do aplicativo (por exemplo, o instalador de aplicativos); se o aplicativo tiver uma dependência de quaisquer estruturas, como .NET Core/Standard ou .NET Framework, elas devem ser incluídas no arquivo e referenciadas corretamente nos scripts fornecidos.</span><span class="sxs-lookup"><span data-stu-id="3ab25-144">These should include everything necessary for installation of the application (e.g. the application installer); if the application has a dependency on any frameworks, such as .NET Core/Standard or .NET Framework, these should be included in the file and referenced correctly in the provided scripts.</span></span>


> [!Note]
> <span data-ttu-id="3ab25-145">O arquivo zip carregado não pode ter espaços ou caracteres especiais em seu nome</span><span class="sxs-lookup"><span data-stu-id="3ab25-145">The uploaded zip file cannot have any spaces or special characters in its name</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ab25-146">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3ab25-146">Next steps</span></span>

<span data-ttu-id="3ab25-147">Avance para o próximo artigo para exibir algumas **perguntas frequentes (perguntas frequentes)**</span><span class="sxs-lookup"><span data-stu-id="3ab25-147">Advance to the next article to view some **Frequently Asked Questions (FAQ)**</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3ab25-148">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="3ab25-148">Next step</span></span>](faq.md)
