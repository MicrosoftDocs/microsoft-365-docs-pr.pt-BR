---
title: Upload Binários de aplicativo
description: Como começar a usar a Base de Teste para M365
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
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322472"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="4055e-103">Etapa 3: Upload binários, dependências e scripts</span><span class="sxs-lookup"><span data-stu-id="4055e-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="4055e-104">Nesta guia, você carregará um único pacote zip contendo seus binários, dependências e scripts usados para executar seu pacote de teste.</span><span class="sxs-lookup"><span data-stu-id="4055e-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="4055e-105">Upload arquivo zip do pacote</span><span class="sxs-lookup"><span data-stu-id="4055e-105">Upload package zip file</span></span>

![Upload binários](Media/AddBinaries.png)

  - <span data-ttu-id="4055e-107">As dependências carregadas podem incluir estruturas de teste, mecanismos de script ou dados que serão acessados para executar seu aplicativo ou casos de teste.</span><span class="sxs-lookup"><span data-stu-id="4055e-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="4055e-108">Por exemplo, você pode carregar Selenium e um instalador webdriver para ajudar a executar testes baseados no navegador.</span><span class="sxs-lookup"><span data-stu-id="4055e-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="4055e-109">É prática prática garantir que suas atividades de script sejam mantidas modulares ou seja.</span><span class="sxs-lookup"><span data-stu-id="4055e-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="4055e-110">O ```Install``` script executa apenas operações de instalação.</span><span class="sxs-lookup"><span data-stu-id="4055e-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="4055e-111">O ```Launch``` script só inicia o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4055e-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="4055e-112">O ```Close``` script apenas fecha o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4055e-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="4055e-113">O ```Uninstall``` script opcional apenas desinstala o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4055e-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="4055e-114">**Atualmente, o portal só dá suporte a scripts do PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="4055e-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="4055e-115">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4055e-115">Next steps</span></span> 

<span data-ttu-id="4055e-116">Avance para o próximo artigo para ir para a Etapa 4: **Definir suas Tarefas de Teste**.</span><span class="sxs-lookup"><span data-stu-id="4055e-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="4055e-117">Voltar</span><span class="sxs-lookup"><span data-stu-id="4055e-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="4055e-118">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="4055e-118">Next step</span></span>](testtask.md)

