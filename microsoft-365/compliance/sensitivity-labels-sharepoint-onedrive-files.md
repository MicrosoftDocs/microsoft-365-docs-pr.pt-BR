---
title: Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Os administradores podem habilitar o suporte a rótulos de confidencialidade para arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive.
ms.openlocfilehash: fea28683136ae72603b3e7a6954d7d6ecf0ffbe4
ms.sourcegitcommit: 2eb4539291f5035b7bef746df89fbcc6faa17257
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41263333"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a><span data-ttu-id="3c6e8-103">Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)</span><span class="sxs-lookup"><span data-stu-id="3c6e8-103">Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)</span></span>

<span data-ttu-id="3c6e8-104">Antes desta visualização, quando você aplicou rótulos de confidencialidade que incluíram criptografia para arquivos do Office armazenados no SharePoint e no OneDrive, o serviço não pôde processar o conteúdo desses arquivos.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-104">Before this preview, when you applied sensitivity labels that included encryption to Office files stored in SharePoint and OneDrive, the service couldn't process the content of these files.</span></span> <span data-ttu-id="3c6e8-105">A coautoria, eDiscovery, prevenção de perda de dados, pesquisa, Delve e outros recursos colaborativos não funcionaram nessas circunstâncias.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-105">Coauthoring, eDiscovery, Data Loss Prevention, search, Delve, and other collaborative features didn't work under these circumstances.</span></span> <span data-ttu-id="3c6e8-106">Essa visualização habilita esses recursos quando a criptografia foi aplicada com uma chave baseada na nuvem:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-106">This preview enables these features when the encryption has been applied with a cloud-based key:</span></span>

- <span data-ttu-id="3c6e8-107">O SharePoint reconhece rótulos de confidencialidade aplicados a arquivos do Word, Excel e PowerPoint no SharePoint e no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-107">SharePoint recognizes sensitivity labels applied to Word, Excel, and PowerPoint files in SharePoint and OneDrive.</span></span> <span data-ttu-id="3c6e8-108">O SharePoint também impõe as configurações que correspondem a cada rótulo.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-108">SharePoint also enforces the settings that correspond with each label.</span></span>

- <span data-ttu-id="3c6e8-109">Quando você baixa um arquivo do SharePoint ou do OneDrive, o rótulo de confidencialização acompanha o arquivo e as configurações permanecem impostas.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-109">When you download a file from SharePoint or OneDrive, the sensitivity label travels with the file and the settings remain enforced.</span></span>

- <span data-ttu-id="3c6e8-110">Aplicar rótulos de confidencialidade a arquivos do Office e abrir e editar arquivos com rótulos de confidencialidade aplicados (se as permissões do rótulo permitirem isso) usando as versões da Web do Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-110">Apply sensitivity labels to Office files, and open and edit files that have sensitivity labels applied (if the label's permissions allow it) by using the web versions of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="3c6e8-111">Com o Word na Web, você também pode usar o rotulamento automático ao editar documentos.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-111">With Word on the web, you can also use auto labeling when you edit documents.</span></span>

- <span data-ttu-id="3c6e8-112">O Office 365 eDiscovery oferece suporte a pesquisa de texto completo em arquivos com rótulos de confidencialidade aplicados.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-112">Office 365 eDiscovery supports full-text search in files that have sensitivity labels applied.</span></span> <span data-ttu-id="3c6e8-113">As políticas de prevenção de perda de dados (DLP) abrangem conteúdo nesses arquivos.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-113">Data Loss Prevention (DLP) policies cover content in these files.</span></span>

- <span data-ttu-id="3c6e8-114">Três novos eventos de auditoria estão disponíveis para monitoramento de rótulos de sensibilidade:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-114">Three new audit events are available for monitoring sensitivity labels:</span></span>
  - <span data-ttu-id="3c6e8-115">FileSensitivityApplied</span><span class="sxs-lookup"><span data-stu-id="3c6e8-115">FileSensitivityApplied</span></span>
  - <span data-ttu-id="3c6e8-116">FileSensitivityLabelChanged</span><span class="sxs-lookup"><span data-stu-id="3c6e8-116">FileSensitivityLabelChanged</span></span>
  - <span data-ttu-id="3c6e8-117">FileSensitivityLabelRemoved</span><span class="sxs-lookup"><span data-stu-id="3c6e8-117">FileSensitivityLabelRemoved</span></span>

> [!NOTE]
> <span data-ttu-id="3c6e8-118">Se a criptografia não tiver sido aplicada com uma chave baseada na nuvem, mas uma chave local, uma topologia de gerenciamento de chave freqüentemente chamada de "conter sua própria chave" (HYOK), o comportamento do SharePoint não mudará com esta visualização.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-118">If encryption hasn't been applied with a cloud-based key but an on-premises key, a key management topology often referred to as "hold your own key" (HYOK), the SharePoint behavior doesn't change with this preview.</span></span> 

<span data-ttu-id="3c6e8-119">Agora, você também pode aplicar rótulos de confidencialidade ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-119">You can also now apply sensitivity labels to Microsoft Teams, Office 365 groups, and SharePoint sites.</span></span> <span data-ttu-id="3c6e8-120">Para obter mais informações sobre essa visualização separada, confira [usar rótulos de sensibilidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)](sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="3c6e8-120">For more information about this separate preview, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites (public preview)](sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="3c6e8-121">Você sempre tem a opção de cancelar essa visualização a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-121">You always have the choice to opt out of this preview at any time.</span></span>

<span data-ttu-id="3c6e8-122">Assista ao vídeo a seguir (sem áudio) para ver os novos recursos em ação:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-122">Watch the following video (no audio) to see these new capabilities in action:</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

## <a name="requirements"></a><span data-ttu-id="3c6e8-123">Requirements</span><span class="sxs-lookup"><span data-stu-id="3c6e8-123">Requirements</span></span>

<span data-ttu-id="3c6e8-124">Esses recursos funcionam somente com [Rótulos de confidencialidade](sensitivity-labels.md) .</span><span class="sxs-lookup"><span data-stu-id="3c6e8-124">These features work with [sensitivity labels](sensitivity-labels.md) only.</span></span> <span data-ttu-id="3c6e8-125">Se, no momento, você tiver rótulos de proteção de informações do Azure, primeiro migre-os para os rótulos de confidencialização para que você possa habilitar esses recursos para novos arquivos que você carregar.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-125">If you currently have Azure Information Protection labels, first migrate them to sensitivity labels so that you can enable these features for new files that you upload.</span></span> <span data-ttu-id="3c6e8-126">Para obter instruções, consulte [como migrar rótulos de proteção de informações do Azure para rótulos de sensibilidade unificada](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span><span class="sxs-lookup"><span data-stu-id="3c6e8-126">For instructions, see [How to migrate Azure Information Protection labels to unified sensitivity labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)</span></span>

<span data-ttu-id="3c6e8-127">Para esta visualização, use o aplicativo de sincronização do OneDrive versão 19.002.0121.0008 ou posterior no Windows e versão 19.002.0107.0008 ou posterior no Mac.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-127">For this preview, use the OneDrive sync app version 19.002.0121.0008 or later on Windows, and version 19.002.0107.0008 or later on Mac.</span></span> <span data-ttu-id="3c6e8-128">Essas duas versões foram lançadas em 28 de janeiro de 2019 e foram lançadas atualmente para todos os toques.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-128">Both these versions were released January 28, 2019, and are currently released to all rings.</span></span> <span data-ttu-id="3c6e8-129">Para obter mais informações, consulte as [notas de versão do onedrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span><span class="sxs-lookup"><span data-stu-id="3c6e8-129">For more information, see the [OneDrive release notes](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0).</span></span> <span data-ttu-id="3c6e8-130">Após habilitar essa visualização, os usuários que executam uma versão mais antiga do aplicativo de sincronização são solicitados a atualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-130">After you enable this preview, users who run an older version of the sync app are prompted to update it.</span></span>

## <a name="limitations"></a><span data-ttu-id="3c6e8-131">Limitações</span><span class="sxs-lookup"><span data-stu-id="3c6e8-131">Limitations</span></span>

- <span data-ttu-id="3c6e8-132">Quando você habilita essa visualização, os usuários que alteram um rótulo para um arquivo em uma pasta de sincronização do OneDrive podem não conseguir salvar outras alterações que eles fazem no arquivo.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-132">When you enable this preview, users who change a label to a file in a OneDrive Sync folder might be unable to save other changes they make to the file.</span></span>  <span data-ttu-id="3c6e8-133">Os usuários vêem um [círculo vermelho com um erro de ícone de cruz branco](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)e são solicitados a salvar novas alterações como uma cópia separada.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-133">Users see a [red circle with a white cross icon error](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), and they are asked to save new changes as a separate copy.</span></span>  <span data-ttu-id="3c6e8-134">Além das alterações de rótulo que são iniciadas pelos usuários, o mesmo comportamento pode ocorrer se um administrador alterar as configurações de um rótulo publicado já aplicado aos arquivos baixados para o cliente de sincronização dos usuários.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-134">In addition to label changes that are initiated by users, the same behavior can occur if an admin changes settings for a published label that's already applied to files downloaded to users' sync client.</span></span>
    
    <span data-ttu-id="3c6e8-135">Para evitar a perda de trabalho nesses cenários, execute uma destas ações:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-135">To avoid losing work for these scenarios, do one of these actions:</span></span>
    - <span data-ttu-id="3c6e8-136">Para aplicar rótulos, use as versões Web dos aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-136">To apply labels, use the web versions of the Office apps.</span></span>
    - <span data-ttu-id="3c6e8-137">Feche um arquivo depois de aplicar um rótulo e reabra o arquivo para fazer outras alterações.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-137">Close a file after you apply a label, and then reopen the file to make other changes.</span></span>

- <span data-ttu-id="3c6e8-138">O SharePoint não aplica automaticamente os novos rótulos aos arquivos existentes que você já criptografou usando os rótulos de proteção de informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-138">SharePoint doesn't automatically apply the new labels to existing files that you've already encrypted using Azure Information Protection labels.</span></span> <span data-ttu-id="3c6e8-139">Em vez disso, para fazer com que os recursos funcionem depois de habilitar esta visualização, conclua estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-139">Instead, to get the features to work after you enable this preview, complete these tasks:</span></span>
    
    1. <span data-ttu-id="3c6e8-140">Certifique-se de ter migrado os rótulos de proteção de informações do Azure para os rótulos de confidencialidade e publicá-los no centro de conformidade do Microsoft 365 ou no centro de administração de rótulo equivalente.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-140">Make sure you have migrated the Azure Information Protection labels to sensitivity labels and published them from the Microsoft 365 compliance center, or equivalent labeling admin center.</span></span>
    
    2. <span data-ttu-id="3c6e8-141">Baixe os arquivos e carregue-os no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-141">Download the files and upload them to SharePoint.</span></span>

- <span data-ttu-id="3c6e8-142">O SharePoint não pode processar arquivos criptografados quando o rótulo que aplicou a criptografia tem uma das seguintes configurações de criptografia:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-142">SharePoint can't process encrypted files when the label that applied the encryption has either of the following configurations for encryption:</span></span>
    - <span data-ttu-id="3c6e8-143">**Permitir que os usuários atribuam permissões quando aplicarem o rótulo** e **no Word, PowerPoint e Excel, solicitar que os usuários especifiquem permissões**</span><span class="sxs-lookup"><span data-stu-id="3c6e8-143">**Let users assign permissions when they apply the label** and **In Word, PowerPoint, and Excel, prompt users to specify permissions**</span></span>
    - <span data-ttu-id="3c6e8-144">O **acesso do usuário ao conteúdo expira** é definido como um valor diferente de **nunca**.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-144">**User access to content expires** is set to a value other than **Never**.</span></span>

- <span data-ttu-id="3c6e8-145">Para um documento criptografado que concede permissões de edição para um usuário, a cópia não pode ser bloqueada nas versões Web dos aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-145">For an encrypted document that grants edit permissions to a user, copying can't be blocked in the web versions of the Office apps.</span></span>

- <span data-ttu-id="3c6e8-146">O site de acompanhamento de documentos da proteção de informações do Azure não é suportado.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-146">The Azure Information Protection document tracking site is not supported.</span></span>

- <span data-ttu-id="3c6e8-147">Aplicativos de área de trabalho do Office e aplicativos móveis não oferecem suporte à coautoria.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-147">Office desktop apps and mobile apps don't support coauthoring.</span></span> <span data-ttu-id="3c6e8-148">Em vez disso, esses aplicativos continuam a abrir arquivos no modo de edição exclusivo.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-148">Instead, these apps continue to open files in exclusive editing mode.</span></span>

- <span data-ttu-id="3c6e8-149">Se um rótulo incluir criptografia, o Microsoft Cloud app Security não poderá ler as informações de rótulo dos arquivos no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-149">If a label includes encryption, Microsoft Cloud App Security isn't able to read the label information for the files in SharePoint.</span></span>

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a><span data-ttu-id="3c6e8-150">Preparar o Shell de gerenciamento do SharePoint Online para a visualização</span><span class="sxs-lookup"><span data-stu-id="3c6e8-150">Prepare the SharePoint Online Management Shell for the preview</span></span>

<span data-ttu-id="3c6e8-151">Antes de habilitar a visualização, verifique se você está executando o Shell de gerenciamento do SharePoint Online versão 16.0.19418.12000 ou superior.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-151">Before you enable the preview, ensure that you're running SharePoint Online Management Shell version 16.0.19418.12000 or above.</span></span> <span data-ttu-id="3c6e8-152">Se você já tiver a versão mais recente, poderá prosseguir e habilitar a visualização.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-152">If you already have the latest version, you can go ahead and enable the preview.</span></span>

1. <span data-ttu-id="3c6e8-153">Se você tiver instalado uma versão anterior do Shell de gerenciamento do SharePoint Online a partir da galeria do PowerShell, você pode atualizar o módulo executando o seguinte cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-153">If you have installed a previous version of the SharePoint Online Management Shell from PowerShell gallery, you can update the module by running the following cmdlet.</span></span>

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. <span data-ttu-id="3c6e8-154">Como alternativa, se você tiver instalado uma versão anterior do Shell de gerenciamento do SharePoint Online no centro de download da Microsoft, também poderá ir para **Adicionar ou remover programas** e desinstalar o Shell de gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-154">Alternatively, if you have installed a previous version of the SharePoint Online Management Shell from the Microsoft Download Center, you can also go to **Add or remove programs** and uninstall the SharePoint Online Management Shell.</span></span>

3. <span data-ttu-id="3c6e8-155">Em um navegador da Web, acesse a página do centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="3c6e8-155">In a web browser, go to the Download Center page and [Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

4. <span data-ttu-id="3c6e8-156">Escolha o idioma e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-156">Select your language and then click **Download**.</span></span>

5. <span data-ttu-id="3c6e8-157">Escolha entre o arquivo .msi x64 e x86.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-157">Choose between the x64 and x86 .msi file.</span></span> <span data-ttu-id="3c6e8-158">Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86, se você executar a versão de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-158">Download the x64 file if you run the 64-bit version of Windows or the x86 file if you run the 32-bit version.</span></span> <span data-ttu-id="3c6e8-159">Se não souber, confira [qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="3c6e8-159">If you don’t know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system)</span></span>


6. <span data-ttu-id="3c6e8-160">Depois de baixar o arquivo, execute o arquivo e siga as etapas no assistente de instalação.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-160">After you have downloaded the file, run the file and follow the steps in the Setup Wizard.</span></span>

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a><span data-ttu-id="3c6e8-161">Habilitar a visualização usando o Microsoft PowerShell (aceitar)</span><span class="sxs-lookup"><span data-stu-id="3c6e8-161">Enable the preview by using Microsoft PowerShell (opt-in)</span></span>

<span data-ttu-id="3c6e8-162">Para habilitar a visualização, use o cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-162">To enable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="3c6e8-163">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-163">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="3c6e8-164">Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="3c6e8-164">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="3c6e8-165">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-165">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a><span data-ttu-id="3c6e8-166">Agendar a distribuição após criar ou alterar um rótulo de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="3c6e8-166">Schedule roll-out after you create or change a sensitivity label</span></span>

<span data-ttu-id="3c6e8-167">Após criar ou alterar um rótulo de confidencialidade no centro de conformidade do Microsoft 365, publique-o em estágios.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-167">After you create or change a sensitivity label in the Microsoft 365 compliance center, publish it in stages.</span></span> <span data-ttu-id="3c6e8-168">Se você publicar rótulos que não estão totalmente sincronizados, quando os usuários aplicam os rótulos aos arquivos e os carregam no SharePoint, os arquivos não podem ser abertos nas versões Web dos aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-168">If you publish labels that haven't fully synchronized, when users apply the labels to files and upload them to SharePoint, the files can’t be opened in the web versions of the Office apps.</span></span> <span data-ttu-id="3c6e8-169">A pesquisa e a descoberta eletrônica também não funcionam para os arquivos.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-169">Search and eDiscovery also don't work for the files.</span></span>

<span data-ttu-id="3c6e8-170">Recomendamos que você siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-170">We recommend that you follow these steps:</span></span>

1. <span data-ttu-id="3c6e8-171">Publicar o rótulo de confidencialidade novo ou modificado somente para uma ou duas pessoas.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-171">Publish the new or modified sensitivity label only to one or two people.</span></span>

2. <span data-ttu-id="3c6e8-172">Aguarde pelo menos 24 horas após a publicação inicial.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-172">Wait for at least 24 hours after initial publication.</span></span> <span data-ttu-id="3c6e8-173">Verifique se o rótulo foi totalmente sincronizado.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-173">Verify that the label has fully synchronized.</span></span>

3. <span data-ttu-id="3c6e8-174">Publique o rótulo de forma mais ampla.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-174">Publish the label more broadly.</span></span>

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a><span data-ttu-id="3c6e8-175">Desabilitar a visualização usando o Microsoft PowerShell (recusar)</span><span class="sxs-lookup"><span data-stu-id="3c6e8-175">Disable the preview by using Microsoft PowerShell (opt-out)</span></span>

<span data-ttu-id="3c6e8-176">Se você desabilitar essa visualização, os arquivos que você carregou durante a visualização continuam a ser protegidos pelo rótulo.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-176">If you disable this preview, files that you uploaded during the preview continue to be protected by the label.</span></span> <span data-ttu-id="3c6e8-177">As configurações correspondentes continuam a ser impostas.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-177">The corresponding settings continue to be enforced.</span></span> <span data-ttu-id="3c6e8-178">Quando você aplica rótulos a novos arquivos depois de desabilitar a visualização, a pesquisa de texto completo, a descoberta eletrônica e a coautoria não funcionarão mais.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-178">When you apply labels to new files after you disable the preview, full-text search, eDiscovery, and coauthoring will no longer work.</span></span>

<span data-ttu-id="3c6e8-179">Para desabilitar a visualização, use o cmdlet Set-SPOTenant:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-179">To disable the preview, use the Set-SPOTenant cmdlet:</span></span>

1. <span data-ttu-id="3c6e8-180">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao SharePoint.</span><span class="sxs-lookup"><span data-stu-id="3c6e8-180">Using a work or school account that has global administrator or SharePoint admin privileges in Office 365, connect to SharePoint.</span></span> <span data-ttu-id="3c6e8-181">Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="3c6e8-181">To learn how, see [Getting started with SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

2. <span data-ttu-id="3c6e8-182">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3c6e8-182">Run the following command:</span></span>

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```
