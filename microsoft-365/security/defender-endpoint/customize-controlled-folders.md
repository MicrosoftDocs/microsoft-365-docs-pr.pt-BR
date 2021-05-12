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
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326518"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="c3624-104">Personalizar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c3624-104">Customize controlled folder access</span></span>

<span data-ttu-id="c3624-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c3624-105">**Applies to:**</span></span>
- [<span data-ttu-id="c3624-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c3624-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3624-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3624-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="c3624-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c3624-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c3624-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c3624-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="c3624-110">O acesso controlado a pastas ajuda você a proteger dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="c3624-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="c3624-111">O acesso controlado a pastas é suportado nos clientes do Windows Server 2019 e do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c3624-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="c3624-112">Este artigo descreve como personalizar recursos de acesso controlado a pastas e inclui as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="c3624-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="c3624-113">Proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="c3624-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="c3624-114">Adicionar aplicativos que devem ter permissão para acessar pastas protegidas</span><span class="sxs-lookup"><span data-stu-id="c3624-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="c3624-115">Permitir que arquivos executáveis assinados acessem pastas protegidas</span><span class="sxs-lookup"><span data-stu-id="c3624-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="c3624-116">Personalizar a notificação</span><span class="sxs-lookup"><span data-stu-id="c3624-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="c3624-117">O acesso controlado a pastas monitora aplicativos para atividades detectadas como mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="c3624-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="c3624-118">Às vezes, aplicativos legítimos são impedidos de fazer alterações em seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="c3624-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="c3624-119">Se o acesso controlado a pastas afetar a produtividade da [](audit-windows-defender.md) sua organização, considere executar esse recurso no modo de auditoria para avaliar totalmente o impacto.</span><span class="sxs-lookup"><span data-stu-id="c3624-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="c3624-120">Proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="c3624-120">Protect additional folders</span></span>

<span data-ttu-id="c3624-121">O acesso controlado a pastas se aplica a várias pastas do sistema e locais padrão, incluindo pastas como **Documentos,** **Imagens** e **Filmes.**</span><span class="sxs-lookup"><span data-stu-id="c3624-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="c3624-122">Você pode adicionar outras pastas a serem protegidas, mas não pode remover as pastas padrão na lista padrão.</span><span class="sxs-lookup"><span data-stu-id="c3624-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="c3624-123">Adicionar outras pastas ao acesso controlado a pastas pode ser útil para casos em que você não armazena arquivos nas bibliotecas padrão do Windows ou alterou o local padrão de suas bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="c3624-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="c3624-124">Você também pode especificar compartilhamentos de rede e unidades mapeadas.</span><span class="sxs-lookup"><span data-stu-id="c3624-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="c3624-125">Há suporte para variáveis de ambiente e curingas.</span><span class="sxs-lookup"><span data-stu-id="c3624-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="c3624-126">Para obter informações sobre como usar caracteres curinga, consulte Use curingas no nome do arquivo e no caminho da pasta ou listas de [exclusão de extensão.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c3624-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="c3624-127">Você pode usar o aplicativo segurança do Windows, Política de Grupo, cmdlets do PowerShell ou provedores de serviço de configuração de gerenciamento de dispositivo móvel para adicionar e remover pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3624-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="c3624-128">Usar o aplicativo segurança do Windows para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="c3624-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="c3624-129">Abra o aplicativo segurança do Windows selecionando o ícone de escudo na barra de tarefas ou procurando *segurança* no menu Iniciar.</span><span class="sxs-lookup"><span data-stu-id="c3624-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="c3624-130">Selecione **Proteção contra & contra vírus** e, em seguida, role para baixo até a seção proteção **ransomware.**</span><span class="sxs-lookup"><span data-stu-id="c3624-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="c3624-131">Selecione **Gerenciar proteção de ransomware** para abrir o painel de proteção do **Ransomware.**</span><span class="sxs-lookup"><span data-stu-id="c3624-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="c3624-132">Na seção **Acesso controlado a pastas,** selecione **Pastas protegidas**.</span><span class="sxs-lookup"><span data-stu-id="c3624-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="c3624-133">Escolha **Sim** no prompt **controle de acesso do** usuário.</span><span class="sxs-lookup"><span data-stu-id="c3624-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="c3624-134">O **painel Pastas Protegidas** é exibido.</span><span class="sxs-lookup"><span data-stu-id="c3624-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="c3624-135">Selecione **Adicionar uma pasta protegida** e siga os prompts para adicionar pastas.</span><span class="sxs-lookup"><span data-stu-id="c3624-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="c3624-136">Usar a Política de Grupo para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="c3624-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="c3624-137">No computador de gerenciamento de Política de Grupo, abra o [Console de Gerenciamento de Política de Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span><span class="sxs-lookup"><span data-stu-id="c3624-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="c3624-138">Clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3624-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="c3624-139">No Editor **de Gerenciamento de Política de Grupo,** acesse Políticas de **configuração** do computador  >    >  **Modelos administrativos.**</span><span class="sxs-lookup"><span data-stu-id="c3624-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="c3624-140">Expanda a árvore para **componentes do Windows**  >  **O Microsoft Defender**  >  **Antivírus Windows Defender acesso controlado** à  >  **pasta do** Exploit Guard .</span><span class="sxs-lookup"><span data-stu-id="c3624-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="c3624-141">**OBSERVAÇÃO**: Em versões mais antigas do Windows, você pode ver Windows Defender **Antivírus** em vez **do Microsoft Defender Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="c3624-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="c3624-142">Clique duas vezes **em Configurações de pastas protegidas** e, em seguida, de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="c3624-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="c3624-143">Selecione **Mostrar** e especifique cada pasta que você deseja proteger.</span><span class="sxs-lookup"><span data-stu-id="c3624-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="c3624-144">Implante seu Objeto de Política de Grupo como normalmente faz.</span><span class="sxs-lookup"><span data-stu-id="c3624-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="c3624-145">Usar o PowerShell para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="c3624-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="c3624-146">Digite **o PowerShell** no menu Iniciar, clique com o botão direito **do mouse Windows PowerShell** e selecione Executar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="c3624-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="c3624-147">Digite o seguinte cmdlet do PowerShell, substituindo pelo caminho da `<the folder to be protected>` pasta (como `"c:\apps\"` ):</span><span class="sxs-lookup"><span data-stu-id="c3624-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="c3624-148">Repita a etapa 2 para cada pasta que você deseja proteger.</span><span class="sxs-lookup"><span data-stu-id="c3624-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="c3624-149">As pastas protegidas ficam visíveis no aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="c3624-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="Janela do PowerShell com cmdlet mostrado":::

> [!IMPORTANT]
> <span data-ttu-id="c3624-151">Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista e não `Set-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="c3624-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="c3624-152">O uso `Set-MpPreference` do cmdlet substituirá a lista existente.</span><span class="sxs-lookup"><span data-stu-id="c3624-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="c3624-153">Usar CSPs MDM para proteger pastas adicionais</span><span class="sxs-lookup"><span data-stu-id="c3624-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="c3624-154">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3624-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="c3624-155">Permitir que aplicativos específicos façam alterações em pastas controladas</span><span class="sxs-lookup"><span data-stu-id="c3624-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="c3624-156">Você pode especificar se determinados aplicativos são sempre considerados seguros e dar acesso de gravação a arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3624-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="c3624-157">Permitir aplicativos pode ser útil se um aplicativo específico que você conhece e confiança estiver sendo bloqueado pelo recurso de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="c3624-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3624-158">Por padrão, o Windows adiciona aplicativos considerados amigáveis à lista permitida.</span><span class="sxs-lookup"><span data-stu-id="c3624-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="c3624-159">Esses aplicativos adicionados automaticamente não são registrados na lista mostrada no aplicativo segurança do Windows ou usando os cmdlets associados do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c3624-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="c3624-160">Não é necessário adicionar a maioria dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c3624-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="c3624-161">Adicione apenas aplicativos se eles estão sendo bloqueados e você pode verificar sua confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="c3624-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="c3624-162">Ao adicionar um aplicativo, você precisa especificar o local do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c3624-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="c3624-163">Somente o aplicativo nesse local terá acesso permitido às pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3624-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="c3624-164">Se o aplicativo (com o mesmo nome) estiver em um local diferente, ele não será adicionado à lista de autorizações e poderá ser bloqueado pelo acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="c3624-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="c3624-165">Um aplicativo ou serviço permitido só tem acesso de gravação a uma pasta controlada depois que ele é iniciado.</span><span class="sxs-lookup"><span data-stu-id="c3624-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="c3624-166">Por exemplo, um serviço de atualização continuará disparando eventos depois que ele for permitido até ser interrompido e reiniciado.</span><span class="sxs-lookup"><span data-stu-id="c3624-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="c3624-167">Use o aplicativo Windows Defender Segurança para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="c3624-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="c3624-168">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="c3624-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="c3624-169">Selecione o **&** de proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e selecione Gerenciar proteção **de ransomware**.</span><span class="sxs-lookup"><span data-stu-id="c3624-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="c3624-170">Na seção **Acesso controlado a pastas,** selecione **Permitir um aplicativo por meio do acesso controlado a pastas**</span><span class="sxs-lookup"><span data-stu-id="c3624-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="c3624-171">Selecione **Adicionar um aplicativo permitido** e siga as solicitações para adicionar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c3624-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Adicionar um botão de aplicativo permitido":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="c3624-173">Usar a Política de Grupo para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="c3624-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="c3624-174">Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c3624-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="c3624-175">No **Editor de Gerenciamento de Política de Grupo**, acesse **Configuração do Computador** e selecione **Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="c3624-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="c3624-176">Expanda a árvore para **componentes do Windows**  >  **O Microsoft Defender**  >  **Antivírus Windows Defender acesso controlado** à  >  **pasta do** Exploit Guard .</span><span class="sxs-lookup"><span data-stu-id="c3624-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="c3624-177">Clique duas vezes na **configuração Configurar aplicativos permitidos** e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="c3624-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="c3624-178">Selecione **Mostrar** e insira cada aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c3624-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="c3624-179">Usar o PowerShell para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="c3624-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="c3624-180">Digite **o PowerShell** no menu Iniciar, clique com o botão direito **do mouse Windows PowerShell** e selecione Executar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="c3624-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="c3624-181">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c3624-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="c3624-182">Por exemplo, para adicionar  otest.exeexecutável localizado na pasta *C:\apps,* o cmdlet seria o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c3624-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="c3624-183">Continue a usar `Add-MpPreference -ControlledFolderAccessAllowedApplications` para adicionar mais aplicativos à lista.</span><span class="sxs-lookup"><span data-stu-id="c3624-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="c3624-184">Os aplicativos adicionados usando esse cmdlet aparecerão no aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="c3624-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet do PowerShell para permitir um aplicativo":::

> [!IMPORTANT]
> <span data-ttu-id="c3624-186">Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista.</span><span class="sxs-lookup"><span data-stu-id="c3624-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="c3624-187">O uso `Set-MpPreference` do cmdlet substituirá a lista existente.</span><span class="sxs-lookup"><span data-stu-id="c3624-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="c3624-188">Usar CSPs MDM para permitir aplicativos específicos</span><span class="sxs-lookup"><span data-stu-id="c3624-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="c3624-189">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3624-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="c3624-190">Permitir que arquivos executáveis assinados acessem pastas protegidas</span><span class="sxs-lookup"><span data-stu-id="c3624-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="c3624-191">Os indicadores de certificado e arquivo do Microsoft Defender for Endpoint podem permitir que arquivos executáveis assinados acessem pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="c3624-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="c3624-192">Para obter detalhes da implementação, [consulte Create indicators based on certificates](indicator-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="c3624-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="c3624-193">Isso não se aplica a mecanismos de script, incluindo o Powershell</span><span class="sxs-lookup"><span data-stu-id="c3624-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="c3624-194">Personalizar a notificação</span><span class="sxs-lookup"><span data-stu-id="c3624-194">Customize the notification</span></span>

<span data-ttu-id="c3624-195">Para obter mais informações sobre como personalizar a notificação quando uma regra é disparada e bloqueia um aplicativo ou arquivo, consulte [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="c3624-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c3624-196">Confira também</span><span class="sxs-lookup"><span data-stu-id="c3624-196">See also</span></span>

- [<span data-ttu-id="c3624-197">Proteger pastas importantes com acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c3624-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="c3624-198">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="c3624-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="c3624-199">Avaliar as regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="c3624-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
