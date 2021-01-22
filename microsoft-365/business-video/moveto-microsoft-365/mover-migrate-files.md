---
title: 'Migrar arquivos do Google para o Microsoft 365 para empresas '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como migrar arquivos do Google para o Microsoft 365 para empresas usando o Mover.
ms.openlocfilehash: 99040e4846aba084f40536e88f0aed70998f48be
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928193"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="c12f7-103">Migrar arquivos do Google para o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="c12f7-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="c12f7-104">Ao migrar para o Microsoft 365 para empresas, você vai querer migrar seus arquivos do Google Drive.</span><span class="sxs-lookup"><span data-stu-id="c12f7-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="c12f7-105">Você pode usar o aplicativo Mover para mover arquivos de Unidades pessoais e compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="c12f7-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="c12f7-106">Para obter mais informações, consulte [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span><span class="sxs-lookup"><span data-stu-id="c12f7-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="c12f7-107">O Mover fará uma cópia dos arquivos e move as cópias para o Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="c12f7-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="c12f7-108">Os arquivos originais também permanecerão no Google Drives.</span><span class="sxs-lookup"><span data-stu-id="c12f7-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="c12f7-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c12f7-109">Before you start</span></span>

<span data-ttu-id="c12f7-110">Todos os usuários devem ter feito o acesso ao Microsoft 365 para empresas e configurar o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="c12f7-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="c12f7-111">Para fazer isso, acesse [office.com,](https://office.com)entre com suas credenciais do Microsft 365 para empresas e escolha o OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c12f7-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="c12f7-112">Experimente!</span><span class="sxs-lookup"><span data-stu-id="c12f7-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="c12f7-113">Instalar o Mover</span><span class="sxs-lookup"><span data-stu-id="c12f7-113">Install Mover</span></span>

1. <span data-ttu-id="c12f7-114">Entre no console de administração do Espaço de Trabalho do Google [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="c12f7-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="c12f7-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then Add app to Domain Install **list**.</span><span class="sxs-lookup"><span data-stu-id="c12f7-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="c12f7-116">Procure o Mover e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="c12f7-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="c12f7-117">Choose **Domain Install**, then **Continue**.</span><span class="sxs-lookup"><span data-stu-id="c12f7-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="c12f7-118">Revise as permissões, marque a caixa de seleção para concordar com os termos, em seguida, selecione **Permitir**, escolher **Próximo**, em **seguida, Feito**.</span><span class="sxs-lookup"><span data-stu-id="c12f7-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="c12f7-119">Criar conectores e executar a migração</span><span class="sxs-lookup"><span data-stu-id="c12f7-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="c12f7-120">Retorne aos **aplicativos do Google Workspace Marketplace.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="c12f7-121">Atualize o navegador e selecione o **aplicativo Mover.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="c12f7-122">Role para baixo e escolha o link de navegação universal.</span><span class="sxs-lookup"><span data-stu-id="c12f7-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="c12f7-123">Selecione **Autorizar Novo Conector,** **localize G Suite (Administrador)** e escolha **Autorizar.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="c12f7-124">Altere **o Nome de Exibição,** se quiser, selecione **Autorizar.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="c12f7-125">Escolha uma conta de administrador do Google, revise as permissões e selecione **Permitir.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="c12f7-126">O Mover exibe o número de unidades de equipe e unidades de usuário descobertas por ele.</span><span class="sxs-lookup"><span data-stu-id="c12f7-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="c12f7-127">Em **Selecionar destino,** escolha **Autorizar Novo Conector,** **localize o Office 365** e selecione **Autorizar.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="c12f7-128">Para conceder permissões ao aplicativo Mover no Azure Active Directory, navegue até [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="c12f7-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="c12f7-129">Selecione **Office 365 Mover**, **Permissões,** **Conceder consentimento de administrador para sua empresa**.</span><span class="sxs-lookup"><span data-stu-id="c12f7-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="c12f7-130">Escolha sua conta, revise as permissões e selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="c12f7-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="c12f7-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span><span class="sxs-lookup"><span data-stu-id="c12f7-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="c12f7-132">Retorne ao aplicativo Mover, altere o **Nome** para Exibição, se quiser, escolha **Autorizar** e selecione uma conta de administrador da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c12f7-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="c12f7-133">O Mover informará sobre o número de sites e usuários do SharePoint Online (ou SPO) descobertos.</span><span class="sxs-lookup"><span data-stu-id="c12f7-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="c12f7-134">Choose **Continue Migration Setup**, select Add **Users**, then Automatically Discover and **Add Users**.</span><span class="sxs-lookup"><span data-stu-id="c12f7-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="c12f7-135">O aplicativo Mover tentará mapear unidades do Caminho de Origem no Google para o Caminho de Destino no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c12f7-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="c12f7-136">Se uma unidade não for mapeado automaticamente, adicione seu caminho de destino a um arquivo CSV, que será usado posteriormente para migrar a unidade compartilhada para uma biblioteca de documentos do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c12f7-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="c12f7-137">Nesse caso, adicionamos um site do SharePoint chamado Arquivos migrados e anotamos a URL da página de documentos.</span><span class="sxs-lookup"><span data-stu-id="c12f7-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="c12f7-138">Em seguida, criamos um arquivo CSV usando o formato de Caminho de Origem, Caminho de Destino e Marcas.</span><span class="sxs-lookup"><span data-stu-id="c12f7-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="c12f7-139">Para obter [detalhes, consulte aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span><span class="sxs-lookup"><span data-stu-id="c12f7-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="c12f7-140">Ao adicionar a URL do Caminho de Destino, remova tudo o que estiver depois de Documentos Compartilhados, por exemplo, essa URL completa não funcionará: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="c12f7-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="c12f7-141">Altere-o para: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="c12f7-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="c12f7-142">Quando o arquivo CSV estiver pronto, selecione **Ações** de Migração, **Adicionar** à Migração, **Escolher um arquivo para carregar.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="c12f7-143">Navegue até o arquivo CSV, selecione-o e escolha **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="c12f7-144">Selecione as unidades de usuário cujos arquivos você deseja migrar e escolha **Iniciar Migração de Usuários.**</span><span class="sxs-lookup"><span data-stu-id="c12f7-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="c12f7-145">Revise as informações de migração, escolha quando iniciar a migração, concorde com os Termos e **Condições** e selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="c12f7-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="c12f7-146">O aplicativo Mover informará quando o processo de migração for concluído.</span><span class="sxs-lookup"><span data-stu-id="c12f7-146">The Mover app will inform you when the migration process is complete.</span></span>