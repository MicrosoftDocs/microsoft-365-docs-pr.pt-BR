---
title: Personalizar o acesso controlado a pastas
description: Adicione outras pastas que devem ser protegidas pelo acesso controlado a pastas ou permita que aplicativos que bloqueem incorretamente as alterações em arquivos importantes.
keywords: Acesso controlado a pastas, windows 10, windows defender, ransomware, proteger, arquivos, pastas, personalizar, adicionar pasta, adicionar aplicativo, permitir, adicionar executável
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 01/06/2021
ms.technology: mde
ms.openlocfilehash: 64f96544361a672881c590716adea80f40777c6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163334"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="6e122-104">Personalizar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="6e122-104">Customize controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6e122-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6e122-105">**Applies to:**</span></span>
- [<span data-ttu-id="6e122-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6e122-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6e122-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6e122-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6e122-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6e122-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6e122-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6e122-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="6e122-110">O acesso controlado a pastas ajuda você a proteger dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="6e122-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="6e122-111">O acesso controlado a pastas é suportado nos clientes do Windows Server 2019 e do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6e122-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="6e122-112">Este artigo descreve como personalizar recursos de acesso controlado a pastas e inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="6e122-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="6e122-113">Proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="6e122-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="6e122-114">Adicionar aplicativos que devem ter permissão para acessar pastas protegidas</span><span class="sxs-lookup"><span data-stu-id="6e122-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="6e122-115">Permitir que arquivos executáveis assinados acessem pastas protegidas</span><span class="sxs-lookup"><span data-stu-id="6e122-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="6e122-116">Personalizar a notificação</span><span class="sxs-lookup"><span data-stu-id="6e122-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="6e122-117">O acesso controlado a pastas monitora aplicativos para atividades detectadas como mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="6e122-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="6e122-118">Às vezes, aplicativos legítimos são impedidos de fazer alterações em seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="6e122-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="6e122-119">Se o acesso controlado a pastas afetar a produtividade da [](audit-windows-defender.md) sua organização, considere executar esse recurso no modo de auditoria para avaliar totalmente o impacto.</span><span class="sxs-lookup"><span data-stu-id="6e122-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="6e122-120">Proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="6e122-120">Protect additional folders</span></span>

<span data-ttu-id="6e122-121">O acesso controlado a pastas se aplica a várias pastas do sistema e locais padrão, incluindo pastas como **Documentos,** **Imagens** e **Filmes.**</span><span class="sxs-lookup"><span data-stu-id="6e122-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="6e122-122">Você pode adicionar pastas adicionais a serem protegidas, mas não pode remover as pastas padrão na lista padrão.</span><span class="sxs-lookup"><span data-stu-id="6e122-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="6e122-123">Adicionar outras pastas ao acesso controlado a pastas pode ser útil para casos em que você não armazena arquivos nas bibliotecas padrão do Windows ou alterou o local padrão de suas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="6e122-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="6e122-124">Você também pode especificar compartilhamentos de rede e unidades mapeadas.</span><span class="sxs-lookup"><span data-stu-id="6e122-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="6e122-125">Há suporte para variáveis de ambiente e curingas.</span><span class="sxs-lookup"><span data-stu-id="6e122-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="6e122-126">Para obter informações sobre como usar caracteres curinga, consulte Use curingas no nome do arquivo e no caminho da pasta ou listas de [exclusão de extensão.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="6e122-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="6e122-127">Você pode usar o aplicativo segurança do Windows, Política de Grupo, cmdlets do PowerShell ou provedores de serviço de configuração de gerenciamento de dispositivo móvel para adicionar e remover pastas protegidas adicionais.</span><span class="sxs-lookup"><span data-stu-id="6e122-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="6e122-128">Usar o aplicativo segurança do Windows para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="6e122-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="6e122-129">Abra o aplicativo segurança do Windows selecionando o ícone de escudo na barra de tarefas ou pesquisando o menu iniciar para **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="6e122-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="6e122-130">Selecione **Proteção contra & contra vírus** e, em seguida, role para baixo até a seção proteção **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="6e122-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="6e122-131">Selecione **Gerenciar proteção de ransomware** para abrir o painel de proteção do **Ransomware.**</span><span class="sxs-lookup"><span data-stu-id="6e122-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="6e122-132">Na seção **Acesso controlado a pastas,** selecione **Pastas protegidas**.</span><span class="sxs-lookup"><span data-stu-id="6e122-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="6e122-133">Escolha **Sim** no prompt **controle de acesso do** usuário.</span><span class="sxs-lookup"><span data-stu-id="6e122-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="6e122-134">O **painel Pastas Protegidas** é exibido.</span><span class="sxs-lookup"><span data-stu-id="6e122-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="6e122-135">Selecione **Adicionar uma pasta protegida** e siga os prompts para adicionar pastas.</span><span class="sxs-lookup"><span data-stu-id="6e122-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="6e122-136">Usar a Política de Grupo para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="6e122-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="6e122-137">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6e122-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="6e122-138">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="6e122-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="6e122-139">Expanda a árvore para **componentes do Windows**  >  **O Microsoft Defender**  >  **Antivírus Windows Defender acesso controlado** à  >  **pasta do** Exploit Guard .</span><span class="sxs-lookup"><span data-stu-id="6e122-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="6e122-140">Clique duas vezes **em Configurações de pastas protegidas** e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6e122-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="6e122-141">Selecione **Mostrar** e insira cada pasta.</span><span class="sxs-lookup"><span data-stu-id="6e122-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="6e122-142">Usar o PowerShell para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="6e122-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="6e122-143">Digite **o PowerShell** no menu Iniciar, clique com o botão direito **do mouse Windows PowerShell** e selecione Executar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="6e122-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="6e122-144">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6e122-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="6e122-145">Repita a etapa 2 até que você tenha adicionado todas as pastas que deseja proteger.</span><span class="sxs-lookup"><span data-stu-id="6e122-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="6e122-146">As pastas adicionadas ficam visíveis no aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="6e122-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Captura de tela de uma janela do PowerShell com o cmdlet acima inserido](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="6e122-148">Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista.</span><span class="sxs-lookup"><span data-stu-id="6e122-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="6e122-149">O uso `Set-MpPreference` do cmdlet substituirá a lista existente.</span><span class="sxs-lookup"><span data-stu-id="6e122-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="6e122-150">Usar CSPs MDM para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="6e122-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="6e122-151">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="6e122-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="6e122-152">Permitir que aplicativos específicos façam alterações em pastas controladas</span><span class="sxs-lookup"><span data-stu-id="6e122-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="6e122-153">Você pode especificar se determinados aplicativos são sempre considerados seguros e dar acesso de gravação a arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="6e122-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="6e122-154">Permitir aplicativos pode ser útil se um aplicativo específico que você conhece e confiança estiver sendo bloqueado pelo recurso de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="6e122-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e122-155">Por padrão, o Windows adiciona aplicativos considerados amigáveis à lista permitida.</span><span class="sxs-lookup"><span data-stu-id="6e122-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="6e122-156">Esses aplicativos adicionados automaticamente não são registrados na lista mostrada no aplicativo segurança do Windows ou usando os cmdlets associados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e122-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="6e122-157">Não é necessário adicionar a maioria dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6e122-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="6e122-158">Adicione apenas aplicativos se eles estão sendo bloqueados e você pode verificar sua confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="6e122-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="6e122-159">Ao adicionar um aplicativo, você precisa especificar o local do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6e122-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="6e122-160">Somente o aplicativo nesse local terá acesso permitido às pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="6e122-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="6e122-161">Se o aplicativo (com o mesmo nome) estiver em um local diferente, ele não será adicionado à lista de autorizações e poderá ser bloqueado pelo acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="6e122-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="6e122-162">Um aplicativo ou serviço permitido só tem acesso de gravação a uma pasta controlada depois que ele é iniciado.</span><span class="sxs-lookup"><span data-stu-id="6e122-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="6e122-163">Por exemplo, um serviço de atualização continuará disparando eventos depois que ele for permitido até ser interrompido e reiniciado.</span><span class="sxs-lookup"><span data-stu-id="6e122-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="6e122-164">Use o aplicativo Windows Defender Segurança para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="6e122-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="6e122-165">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="6e122-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="6e122-166">Selecione o **&** de proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e selecione Gerenciar proteção **de ransomware**.</span><span class="sxs-lookup"><span data-stu-id="6e122-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="6e122-167">Na seção **Acesso controlado a pastas,** selecione **Permitir um aplicativo por meio do acesso controlado a pastas**</span><span class="sxs-lookup"><span data-stu-id="6e122-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="6e122-168">Selecione **Adicionar um aplicativo permitido** e siga as solicitações para adicionar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6e122-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

    ![Captura de tela de como adicionar um botão de aplicativo permitido](/microsoft-365/security/defender-endpoint/images/cfa-allow-app)

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="6e122-170">Usar a Política de Grupo para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="6e122-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="6e122-171">Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6e122-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="6e122-172">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="6e122-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="6e122-173">Expanda a árvore para **componentes do Windows**  >  **O Microsoft Defender**  >  **Antivírus Windows Defender acesso controlado** à  >  **pasta do** Exploit Guard .</span><span class="sxs-lookup"><span data-stu-id="6e122-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="6e122-174">Clique duas vezes na **configuração Configurar aplicativos permitidos** e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6e122-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="6e122-175">Selecione **Mostrar** e insira cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6e122-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="6e122-176">Usar o PowerShell para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="6e122-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="6e122-177">Digite **o PowerShell** no menu Iniciar, clique com o botão direito **do mouse Windows PowerShell** e selecione Executar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="6e122-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="6e122-178">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="6e122-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="6e122-179">Por exemplo, para adicionar  otest.exeexecutável localizado na pasta *C:\apps,* o cmdlet seria o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6e122-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="6e122-180">Continue a usar `Add-MpPreference -ControlledFolderAccessAllowedApplications` para adicionar mais aplicativos à lista.</span><span class="sxs-lookup"><span data-stu-id="6e122-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="6e122-181">Os aplicativos adicionados usando esse cmdlet aparecerão no aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="6e122-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

![Captura de tela de uma janela do PowerShell com o cmdlet acima inserido](/microsoft-365/security/defender-endpoint/images/cfa-allow-app-ps)

> [!IMPORTANT]
> <span data-ttu-id="6e122-183">Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista.</span><span class="sxs-lookup"><span data-stu-id="6e122-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="6e122-184">O uso `Set-MpPreference` do cmdlet substituirá a lista existente.</span><span class="sxs-lookup"><span data-stu-id="6e122-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="6e122-185">Usar CSPs MDM para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="6e122-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="6e122-186">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="6e122-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="6e122-187">Permitir que arquivos executáveis assinados acessem pastas protegidas</span><span class="sxs-lookup"><span data-stu-id="6e122-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="6e122-188">Os indicadores de certificado e arquivo do Microsoft Defender for Endpoint podem permitir que arquivos executáveis assinados acessem pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="6e122-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="6e122-189">Para obter detalhes da implementação, [consulte Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span><span class="sxs-lookup"><span data-stu-id="6e122-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="6e122-190">Isso não se aplica a mecanismos de script, incluindo o Powershell</span><span class="sxs-lookup"><span data-stu-id="6e122-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="6e122-191">Personalizar a notificação</span><span class="sxs-lookup"><span data-stu-id="6e122-191">Customize the notification</span></span>

<span data-ttu-id="6e122-192">Para obter mais informações sobre como personalizar a notificação quando uma regra é disparada e bloqueia um aplicativo ou arquivo, consulte [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span><span class="sxs-lookup"><span data-stu-id="6e122-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="6e122-193">Confira também</span><span class="sxs-lookup"><span data-stu-id="6e122-193">See also</span></span>

- [<span data-ttu-id="6e122-194">Proteger pastas importantes com acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="6e122-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="6e122-195">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="6e122-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="6e122-196">Avaliar regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="6e122-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
