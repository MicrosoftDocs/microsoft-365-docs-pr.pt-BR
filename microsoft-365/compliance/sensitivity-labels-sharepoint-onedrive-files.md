---
title: Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/01/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Os administradores podem habilitar o suporte a rótulos de confidencialidade para arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive.
ms.openlocfilehash: c050aefb9feebbb3ff37a8504ba1b8385fb0ff49
ms.sourcegitcommit: 1c962bd0d51dc12419c4e6e393bb734c972b7e38
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2019
ms.locfileid: "38684902"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="7a7ad-103">Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)</span><span class="sxs-lookup"><span data-stu-id="7a7ad-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="7a7ad-104">Anteriormente, quando você aplicou rótulos de confidencialidade que incluíram criptografia para arquivos do Office armazenados no SharePoint e no OneDrive, o serviço não pôde processar o conteúdo desses arquivos.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-104">Previously, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="7a7ad-105">A coautoria, eDiscovery, prevenção de perda de dados, pesquisa, Delve e outros recursos colaborativos não funcionaram nessas circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="7a7ad-106">Essa visualização habilita estes recursos:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-106">This preview enables these features:</span></span>

- <span data-ttu-id="7a7ad-107">O SharePoint reconhece rótulos de confidencialidade aplicados a arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="7a7ad-108">O SharePoint também impõe as configurações que correspondem a cada rótulo.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="7a7ad-109">Quando você baixa um arquivo do SharePoint ou do OneDrive, o rótulo de confidencialização acompanha o arquivo e as configurações permanecem impostas.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="7a7ad-110">Aplicar rótulos de confidencialidade a arquivos do Office e abrir e editar arquivos com rótulos de confidencialidade aplicados (se as permissões do rótulo permitirem isso) usando as versões da Web do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="7a7ad-111">Com o Word na Web, você também pode usar o rotulamento automático ao editar documentos.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-111">With Word on the web, you can also use Auto labeling when you edit documents.</span></span>

- <span data-ttu-id="7a7ad-112">O Office 365 eDiscovery oferece suporte a pesquisa de texto completo em arquivos com rótulos de confidencialidade aplicados.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="7a7ad-113">As políticas de prevenção de perda de dados (DLP) abrangem conteúdo nesses arquivos.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="7a7ad-114">Três novos eventos de auditoria estão disponíveis para monitoramento de rótulos de sensibilidade:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="7a7ad-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="7a7ad-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="7a7ad-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="7a7ad-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="7a7ad-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="7a7ad-117">FileSensitivityLabelRemoved</span></span>

<span data-ttu-id="7a7ad-118">Agora, você também pode aplicar rótulos de confidencialidade ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-118">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="7a7ad-119">[Saiba mais](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="7a7ad-119">[Learn more](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="7a7ad-120">Se necessário, você pode sair da visualização a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-120">If necessary, you can opt out of the preview at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="7a7ad-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a7ad-121">Requirements</span></span>

<span data-ttu-id="7a7ad-122">Esses recursos funcionam apenas com [Rótulos de confidencialidade](sensitivity-labels.md).</span><span class="sxs-lookup"><span data-stu-id="7a7ad-122">These features work only with [sensitivity labels](sensitivity-labels.md).</span></span> <span data-ttu-id="7a7ad-123">Se você usou os rótulos de proteção de informações do Azure, é possível convertê-los em rótulos de confidencialidade para habilitar esses recursos para novos arquivos que você carregar.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-123">If you used Azure Information Protection labels, you can convert them to sensitivity labels to enable these features for new files that you upload.</span></span> [<span data-ttu-id="7a7ad-124">Saiba como</span><span class="sxs-lookup"><span data-stu-id="7a7ad-124">Learn how</span></span>](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

<span data-ttu-id="7a7ad-125">Para esta visualização, use o OneDrive Sync app versão 19.002.0121.0008 ou posterior no Windows e versão 19.002.0107.0008 ou posterior no Mac.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-125">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="7a7ad-126">Essas duas versões foram lançadas em 28 de janeiro de 2019 e foram lançadas atualmente para todos os toques.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-126">Both of these versions were released on January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="7a7ad-127">[Confira as notas de versão do onedrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="7a7ad-127">[See the OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="7a7ad-128">Após habilitar essa visualização, os usuários que executam uma versão mais antiga do aplicativo de sincronização serão solicitados a atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-128">After you enable this preview, users who run an older version of the sync app will be prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="7a7ad-129">Limitações</span><span class="sxs-lookup"><span data-stu-id="7a7ad-129">Limitations</span></span>

- <span data-ttu-id="7a7ad-130">Quando você habilita essa visualização, os usuários que aplicam um rótulo a um arquivo usando a área de trabalho do Office ou aplicativos móveis podem não conseguir salvar outras alterações que eles fazem no arquivo.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-130">When you enable this preview, users who apply a label to a file by using the Office desktop or mobile apps might be unable to save other changes they make to the file.</span></span> <span data-ttu-id="7a7ad-131">Em vez disso, o aplicativo solicita que os usuários salvem como ou descartam alterações locais.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-131">Instead, the app prompts users to Save As or Discard local changes.</span></span> <span data-ttu-id="7a7ad-132">Para evitar a perda de trabalho, execute uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-132">To avoid losing work, do one of these actions:</span></span>

  - <span data-ttu-id="7a7ad-133">Para aplicar rótulos, use as versões Web dos aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-133">To apply labels, use the web versions of the Office apps.</span></span>

  - <span data-ttu-id="7a7ad-134">Feche um arquivo depois de aplicar um rótulo e reabra o arquivo para fazer outras alterações.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-134">Close a file after you apply a label and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="7a7ad-135">O SharePoint não aplica automaticamente os novos rótulos aos arquivos existentes que você já criptografou usando os rótulos de proteção de informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-135">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="7a7ad-136">Em vez disso, para fazer com que os recursos funcionem depois de habilitar esta visualização, conclua estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-136">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>

  - <span data-ttu-id="7a7ad-137">Converta os rótulos de proteção de informações do Azure em rótulos de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-137">Convert the Azure Information Protection labels to sensitivity labels.</span></span>

  - <span data-ttu-id="7a7ad-138">Baixe os arquivos e carregue-os no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-138">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="7a7ad-139">O SharePoint não pode processar rótulos com permissões e rótulos personalizados com datas de expiração.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-139">SharePoint can't process labels with custom permissions and labels with expiration dates.</span></span>

- <span data-ttu-id="7a7ad-140">Quando os usuários têm permissões de edição, as versões Web dos aplicativos do Office permitem a cópia, independentemente da configuração de política de cópia no rótulo.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-140">When users have edit permissions, the web versions of the Office apps allow copying regardless of the copy policy setting in the label.</span></span>

- <span data-ttu-id="7a7ad-141">A revogação, o rastreamento e o relatório do RMS não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-141">RMS revocation, tracking, and reporting are unsupported.</span></span>

- <span data-ttu-id="7a7ad-142">Aplicativos de área de trabalho do Office e aplicativos móveis não oferecem suporte à coautoria.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-142">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="7a7ad-143">Em vez disso, esses aplicativos continuam a abrir arquivos no modo de edição exclusivo.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-143">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="7a7ad-144">Se um rótulo incluir criptografia, o Microsoft Cloud app Security não poderá ler as informações de rótulo dos arquivos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-144">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="7a7ad-145">Preparar o Shell de gerenciamento do SharePoint Online para a visualização</span><span class="sxs-lookup"><span data-stu-id="7a7ad-145">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="7a7ad-146">Antes de habilitar a visualização, verifique se você está executando o Shell de gerenciamento do SharePoint Online mais recente.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-146">Before you enable the preview, ensure that you're running the latest SharePoint Online Management Shell.</span></span> <span data-ttu-id="7a7ad-147">Se você já tiver a versão mais recente, poderá prosseguir e habilitar a visualização.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-147">If you already have the latest version, you can go ahead and enable the preview.</span></span>

<span data-ttu-id="7a7ad-148">Para preparar o Shell de gerenciamento do SharePoint Online para a visualização:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-148">To prepare the SharePoint Online Management Shell for the preview:</span></span>

1. <span data-ttu-id="7a7ad-149">Se você instalou uma versão anterior do Shell de gerenciamento do SharePoint Online, vá para **Adicionar ou remover programas** e desinstalar o Shell de gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-149">If you installed a previous version of the SharePoint Online Management Shell, go to **Add or remove programs** and uninstall “SharePoint Online Management Shell.”</span></span>

2. <span data-ttu-id="7a7ad-150">Em um navegador da Web, vá até a página centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="7a7ad-150">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

3. <span data-ttu-id="7a7ad-151">Selecione seu idioma e clique em **baixar**.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-151">Select your language and then click **Download**.</span></span>

4. <span data-ttu-id="7a7ad-152">Escolha entre o arquivo x64 e x86. msi.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-152">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="7a7ad-153">Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86, se você executar a versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-153">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="7a7ad-154">Se você não souber, confira [qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="7a7ad-154">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span>

5. <span data-ttu-id="7a7ad-155">Depois de baixar o arquivo, execute o arquivo e siga as etapas no assistente de instalação.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-155">After you download the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="7a7ad-156">Habilitar a visualização usando o Microsoft PowerShell (aceitar)</span><span class="sxs-lookup"><span data-stu-id="7a7ad-156">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="7a7ad-157">Para habilitar a visualização, use o cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-157">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="7a7ad-158">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-158">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="7a7ad-159">Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="7a7ad-159">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="7a7ad-160">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-160">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="7a7ad-161">Agendar a distribuição após criar ou alterar um rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="7a7ad-161">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="7a7ad-162">Após criar ou alterar um rótulo de confidencialidade no centro de conformidade do Microsoft 365, publique-o em estágios.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-162">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="7a7ad-163">Se você publicar rótulos que não estão totalmente sincronizados, quando os usuários aplicam os rótulos aos arquivos e os carregam no SharePoint, os arquivos não podem ser abertos nas versões Web dos aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-163">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="7a7ad-164">A pesquisa e a descoberta eletrônica também não funcionam para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-164">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="7a7ad-165">Recomendamos que você siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-165">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="7a7ad-166">Publicar o rótulo de confidencialidade novo ou modificado somente para uma ou duas pessoas.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-166">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="7a7ad-167">Aguarde pelo menos 24 horas após a publicação inicial.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-167">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="7a7ad-168">Verifique se o rótulo foi totalmente sincronizado.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-168">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="7a7ad-169">Publique o rótulo de forma mais ampla.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-169">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="7a7ad-170">Desabilitar a visualização usando o Microsoft PowerShell (recusar)</span><span class="sxs-lookup"><span data-stu-id="7a7ad-170">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="7a7ad-171">Se você desabilitar essa visualização, os arquivos que você carregou durante a visualização continuam a ser protegidos pelo rótulo.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-171">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="7a7ad-172">As configurações correspondentes continuam a ser impostas.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-172">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="7a7ad-173">Quando você aplica rótulos a novos arquivos depois de desabilitar a visualização, a pesquisa de texto completo, a descoberta eletrônica e a coautoria não funcionarão mais.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-173">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="7a7ad-174">Para desabilitar a visualização, use o cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-174">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="7a7ad-175">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7a7ad-175">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="7a7ad-176">Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="7a7ad-176">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="7a7ad-177">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7a7ad-177">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
