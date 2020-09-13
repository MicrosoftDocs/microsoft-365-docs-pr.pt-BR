---
title: Solucionar problemas de AzCopy na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Solucionar erros para o Azure AzCopy ao carregar dados não-Office 365 para correção de erros na descoberta eletrônica avançada.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4a4499bb9790ffeaec6a2be36b5eaff030afc010
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546451"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="a1800-103">Solucionar problemas de AzCopy na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="a1800-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="a1800-104">Ao carregar dados ou documentos que não são da Microsoft 365 para correção de erros na descoberta eletrônica avançada, a interface do usuário fornece um comando do AzCopy do Microsoft Azure que contém parâmetros com o local onde os arquivos que você deseja carregar estão armazenados e o local de armazenamento do Azure para o qual os arquivos serão carregados.</span><span class="sxs-lookup"><span data-stu-id="a1800-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="a1800-105">Para carregar seus documentos, copie esse comando e execute-o em um prompt de comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="a1800-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="a1800-106">A captura de tela a seguir mostra um exemplo de um comando do AzCopy:</span><span class="sxs-lookup"><span data-stu-id="a1800-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![Carregar arquivos que não são da Microsoft 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="a1800-108">Normalmente, o comando fornecido funciona quando você o executa.</span><span class="sxs-lookup"><span data-stu-id="a1800-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="a1800-109">No entanto, pode haver casos em que o comando exibido não seja executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="a1800-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="a1800-110">Veja alguns motivos possíveis.</span><span class="sxs-lookup"><span data-stu-id="a1800-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="a1800-111">A versão suportada do AzCopy não está instalada no computador local</span><span class="sxs-lookup"><span data-stu-id="a1800-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="a1800-112">Neste momento, você deve usar o AzCopy v 8.1 para carregar dados que não sejam da Microsoft 365 na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="a1800-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="a1800-113">O comando AzCopy exibido na página **carregar arquivos** mostrados na captura de tela anterior retornará um erro se você não estiver usando o AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="a1800-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="a1800-114">Para instalar essa versão, consulte [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="a1800-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="a1800-115">O AzCopy não está instalado no computador local ou não está instalado no local padrão</span><span class="sxs-lookup"><span data-stu-id="a1800-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="a1800-116">Se o AzCopy não estiver instalado ou estiver instalado em um local diferente do local de instalação padrão (ou seja `%ProgramFiles(x86)%` ), você pode receber o seguinte erro ao executar o comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="a1800-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="a1800-117">O sistema não pode localizar o caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="a1800-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="a1800-118">Se o AzCopy não estiver instalado no computador local, você poderá encontrar informações de instalação em [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="a1800-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="a1800-119">Certifique-se de instalá-lo no local padrão.</span><span class="sxs-lookup"><span data-stu-id="a1800-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="a1800-120">Se o AzCopy estiver instalado, mas estiver instalado em um local diferente do local padrão, você poderá copiar o comando, colá-lo em um arquivo de texto e alterar o caminho para o local onde o AzCopy está instalado.</span><span class="sxs-lookup"><span data-stu-id="a1800-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="a1800-121">Por exemplo, se Azcopy estiver localizado em `%ProgramFiles%` , então você poderá alterar a primeira parte do comando de `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` para `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` .</span><span class="sxs-lookup"><span data-stu-id="a1800-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="a1800-122">Após fazer essa alteração, copie-a do arquivo de texto e, em seguida, execute um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="a1800-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="a1800-123">Se o AzCopy estiver instalado em um local diferente do local de instalação padrão, considere desinstalá-lo e, em seguida, instale-o novamente no local padrão.</span><span class="sxs-lookup"><span data-stu-id="a1800-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="a1800-124">Isso ajudará a evitar esse problema no futuro.</span><span class="sxs-lookup"><span data-stu-id="a1800-124">This will help prevent this issue in the future.</span></span>
