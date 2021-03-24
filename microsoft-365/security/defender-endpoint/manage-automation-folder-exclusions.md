---
title: Gerenciar exclusões de pastas de automação
description: Adicione exclusões de pastas de automação para controlar os arquivos excluídos de uma investigação automatizada.
keywords: gerenciar, automação, exclusão, bloquear, limpar, mal-intencionado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: fb398f1acbea4bd8f388c072f9706f9b2ca25175
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052873"
---
# <a name="manage-automation-folder-exclusions"></a><span data-ttu-id="3dd19-104">Gerenciar exclusões de pastas de automação</span><span class="sxs-lookup"><span data-stu-id="3dd19-104">Manage automation folder exclusions</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3dd19-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3dd19-105">**Applies to:**</span></span>
- [<span data-ttu-id="3dd19-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3dd19-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="3dd19-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3dd19-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="3dd19-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="3dd19-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3dd19-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="3dd19-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

<span data-ttu-id="3dd19-110">As exclusões de pastas de automação permitem que você especifique pastas que a investigação automatizada ignorará.</span><span class="sxs-lookup"><span data-stu-id="3dd19-110">Automation folder exclusions allow you to specify folders that the Automated investigation will skip.</span></span> 

<span data-ttu-id="3dd19-111">Você pode controlar os seguintes atributos sobre a pasta que você gostaria de ser ignorada:</span><span class="sxs-lookup"><span data-stu-id="3dd19-111">You can control the following attributes about the folder that you'd like to be skipped:</span></span>
- <span data-ttu-id="3dd19-112">Folders</span><span class="sxs-lookup"><span data-stu-id="3dd19-112">Folders</span></span> 
- <span data-ttu-id="3dd19-113">Extensões dos arquivos</span><span class="sxs-lookup"><span data-stu-id="3dd19-113">Extensions of the files</span></span>
- <span data-ttu-id="3dd19-114">Nomes de arquivos</span><span class="sxs-lookup"><span data-stu-id="3dd19-114">File names</span></span>


<span data-ttu-id="3dd19-115">**Pastas**</span><span class="sxs-lookup"><span data-stu-id="3dd19-115">**Folders**</span></span><br>
<span data-ttu-id="3dd19-116">Você pode especificar uma pasta e suas subpastas a serem ignoradas.</span><span class="sxs-lookup"><span data-stu-id="3dd19-116">You can specify a folder and its subfolders to be skipped.</span></span> 


>[!NOTE]
><span data-ttu-id="3dd19-117">No momento, ainda não há suporte para o uso de cartões curinga como uma maneira de excluir arquivos em um diretório.</span><span class="sxs-lookup"><span data-stu-id="3dd19-117">At this time, use of wild cards as a way to exclude files under a directory is not yet supported.</span></span> 


<span data-ttu-id="3dd19-118">**Extensões**</span><span class="sxs-lookup"><span data-stu-id="3dd19-118">**Extensions**</span></span><br>
<span data-ttu-id="3dd19-119">Você pode especificar as extensões a excluir em um diretório específico.</span><span class="sxs-lookup"><span data-stu-id="3dd19-119">You can specify the extensions to exclude in a specific directory.</span></span> <span data-ttu-id="3dd19-120">As extensões são uma maneira de impedir que um invasor use uma pasta excluída para ocultar uma exploração.</span><span class="sxs-lookup"><span data-stu-id="3dd19-120">The extensions are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="3dd19-121">As extensões definem explicitamente quais arquivos serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="3dd19-121">The extensions explicitly define which files to ignore.</span></span> 

<span data-ttu-id="3dd19-122">**Nomes de arquivos**</span><span class="sxs-lookup"><span data-stu-id="3dd19-122">**File names**</span></span><br>
<span data-ttu-id="3dd19-123">Você pode especificar os nomes de arquivo que deseja excluir em um diretório específico.</span><span class="sxs-lookup"><span data-stu-id="3dd19-123">You can specify the file names that you want to be excluded in a specific directory.</span></span> <span data-ttu-id="3dd19-124">Os nomes são uma maneira de impedir que um invasor use uma pasta excluída para ocultar uma exploração.</span><span class="sxs-lookup"><span data-stu-id="3dd19-124">The names are a way to prevent an attacker from using an excluded folder to hide an exploit.</span></span> <span data-ttu-id="3dd19-125">Os nomes definem explicitamente quais arquivos serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="3dd19-125">The names explicitly define which files to ignore.</span></span> 



## <a name="add-an-automation-folder-exclusion"></a><span data-ttu-id="3dd19-126">Adicionar uma exclusão de pasta de automação</span><span class="sxs-lookup"><span data-stu-id="3dd19-126">Add an automation folder exclusion</span></span>
1. <span data-ttu-id="3dd19-127">No painel de navegação, selecione **Configurações**  >  **Exclusões de pasta de automação.**</span><span class="sxs-lookup"><span data-stu-id="3dd19-127">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  

2. <span data-ttu-id="3dd19-128">Clique **em Nova exclusão de pasta**.</span><span class="sxs-lookup"><span data-stu-id="3dd19-128">Click **New folder exclusion**.</span></span>  

3. <span data-ttu-id="3dd19-129">Insira os detalhes da pasta:</span><span class="sxs-lookup"><span data-stu-id="3dd19-129">Enter the folder details:</span></span>

    - <span data-ttu-id="3dd19-130">Folder</span><span class="sxs-lookup"><span data-stu-id="3dd19-130">Folder</span></span>
    - <span data-ttu-id="3dd19-131">Extensões</span><span class="sxs-lookup"><span data-stu-id="3dd19-131">Extensions</span></span>
    - <span data-ttu-id="3dd19-132">Nomes de arquivos</span><span class="sxs-lookup"><span data-stu-id="3dd19-132">File names</span></span>
    - <span data-ttu-id="3dd19-133">Descrição</span><span class="sxs-lookup"><span data-stu-id="3dd19-133">Description</span></span>
    

4. <span data-ttu-id="3dd19-134">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3dd19-134">Click **Save**.</span></span>

>[!NOTE]
> <span data-ttu-id="3dd19-135">Comandos de Resposta Ao Vivo para coletar ou examinar arquivos excluídos falharão com o erro: "O arquivo é excluído".</span><span class="sxs-lookup"><span data-stu-id="3dd19-135">Live Response commands to collect or examine excluded files will fail with error: "File is excluded".</span></span> <span data-ttu-id="3dd19-136">Além disso, as investigações automatizadas ignorarão os itens excluídos.</span><span class="sxs-lookup"><span data-stu-id="3dd19-136">In addition, automated investigations will ignore the excluded items.</span></span>

## <a name="edit-an-automation-folder-exclusion"></a><span data-ttu-id="3dd19-137">Editar uma exclusão de pasta de automação</span><span class="sxs-lookup"><span data-stu-id="3dd19-137">Edit an automation folder exclusion</span></span> 
1. <span data-ttu-id="3dd19-138">No painel de navegação, selecione **Configurações**  >  **Exclusões de pasta de automação.**</span><span class="sxs-lookup"><span data-stu-id="3dd19-138">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span> 

2. <span data-ttu-id="3dd19-139">Clique **em Editar** na exclusão de pasta.</span><span class="sxs-lookup"><span data-stu-id="3dd19-139">Click **Edit** on the folder exclusion.</span></span>  

3. <span data-ttu-id="3dd19-140">Atualize os detalhes da regra e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3dd19-140">Update the details of the rule and click **Save**.</span></span>

## <a name="remove-an-automation-folder-exclusion"></a><span data-ttu-id="3dd19-141">Remover uma exclusão de pasta de automação</span><span class="sxs-lookup"><span data-stu-id="3dd19-141">Remove an automation folder exclusion</span></span> 
1. <span data-ttu-id="3dd19-142">No painel de navegação, selecione **Configurações**  >  **Exclusões de pasta de automação.**</span><span class="sxs-lookup"><span data-stu-id="3dd19-142">In the navigation pane, select **Settings** > **Automation folder exclusions**.</span></span>  
2. <span data-ttu-id="3dd19-143">Clique **em Remover exclusão**.</span><span class="sxs-lookup"><span data-stu-id="3dd19-143">Click **Remove exclusion**.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="3dd19-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3dd19-144">Related topics</span></span>
- [<span data-ttu-id="3dd19-145">Gerenciar listas permitidas/bloqueadas de automação</span><span class="sxs-lookup"><span data-stu-id="3dd19-145">Manage automation allowed/blocked lists</span></span>](manage-indicators.md)
- [<span data-ttu-id="3dd19-146">Gerenciar carregamentos de arquivos de automação</span><span class="sxs-lookup"><span data-stu-id="3dd19-146">Manage automation file uploads</span></span>](manage-automation-file-uploads.md)
