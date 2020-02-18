---
title: Solucionar problemas de AzCopy na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 3153fc92cfae6e2feba122cc895e787c9b573ef7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42080889"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="41e70-102">Solucionar problemas de AzCopy na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="41e70-102">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="41e70-103">Ao carregar dados não-Office 365 ou documentos para correção de erros na descoberta eletrônica avançada, a interface do usuário fornece um comando do AzCopy do Azure que contém parâmetros com o local onde os arquivos que você deseja carregar estão armazenados e o armazenamento do Azure local para o qual os arquivos serão carregados.</span><span class="sxs-lookup"><span data-stu-id="41e70-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="41e70-104">Para carregar seus documentos, copie esse comando e execute-o em um prompt de comando no computador local.</span><span class="sxs-lookup"><span data-stu-id="41e70-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="41e70-105">A captura de tela a seguir mostra um exemplo de um comando do AzCopy:</span><span class="sxs-lookup"><span data-stu-id="41e70-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![Carregar arquivos que não são do Office 365](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="41e70-107">Normalmente, o comando fornecido funciona quando você o executa.</span><span class="sxs-lookup"><span data-stu-id="41e70-107">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="41e70-108">No entanto, pode haver casos em que o comando exibido não seja executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="41e70-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="41e70-109">Veja alguns motivos possíveis.</span><span class="sxs-lookup"><span data-stu-id="41e70-109">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="41e70-110">A versão suportada do AzCopy não está instalada no computador local</span><span class="sxs-lookup"><span data-stu-id="41e70-110">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="41e70-111">Neste momento, você deve usar o AzCopy v 8.1 para carregar dados que não sejam do Office 365 na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="41e70-111">At this time, you must use AzCopy v8.1 to load non-Office 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="41e70-112">O comando AzCopy exibido na página **carregar arquivos** mostrados na captura de tela anterior retornará um erro se você não estiver usando o AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="41e70-112">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="41e70-113">Para instalar essa versão, consulte [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="41e70-113">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="41e70-114">O AzCopy não está instalado no computador local ou não está instalado no local padrão</span><span class="sxs-lookup"><span data-stu-id="41e70-114">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="41e70-115">Se o AzCopy não estiver instalado ou estiver instalado em um local diferente do local de instalação padrão (ou `%ProgramFiles(x86)%`seja), você pode receber o seguinte erro ao executar o comando AzCopy:</span><span class="sxs-lookup"><span data-stu-id="41e70-115">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="41e70-116">Se o AzCopy não estiver instalado no computador local, você poderá instalar [daqui.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="41e70-116">If AzCopy isn't installed on the local computer, you can install from [here](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="41e70-117">Certifique-se de instalá-lo no local padrão.</span><span class="sxs-lookup"><span data-stu-id="41e70-117">Be sure to install it in the default location.</span></span>

<span data-ttu-id="41e70-118">Se o AzCopy estiver instalado, mas estiver instalado em um local diferente do local padrão, você poderá copiar o comando, colá-lo em um arquivo de texto e alterar o caminho para o local onde o AzCopy está instalado.</span><span class="sxs-lookup"><span data-stu-id="41e70-118">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="41e70-119">Por exemplo, se Azcopy estiver localizado em `%ProgramFiles%`, então você poderá alterar a primeira parte do comando de `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` para. `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`</span><span class="sxs-lookup"><span data-stu-id="41e70-119">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="41e70-120">Após fazer essa alteração, copie-a do arquivo de texto e, em seguida, execute um prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="41e70-120">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="41e70-121">Se o AzCopy estiver instalado em um local diferente do local de instalação padrão, considere desinstalá-lo e, em seguida, instale-o novamente no local padrão.</span><span class="sxs-lookup"><span data-stu-id="41e70-121">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="41e70-122">Isso ajudará a evitar esse problema no futuro.</span><span class="sxs-lookup"><span data-stu-id="41e70-122">This will help prevent this issue in the future.</span></span>
