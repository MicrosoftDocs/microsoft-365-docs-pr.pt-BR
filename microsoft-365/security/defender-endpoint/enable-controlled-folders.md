---
title: Habilitar o acesso controlado a pastas
keywords: Acesso controlado a pastas, windows 10, windows defender, ransomware, proteger, arquivos, pastas, habilitar, ativar, usar
description: Saiba como proteger seus arquivos importantes habilitando o acesso controlado a pastas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ed0859e6018d171b48aac83d394eacbd2163c37b
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924678"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="855dd-104">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="855dd-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="855dd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="855dd-105">**Applies to:**</span></span>
- [<span data-ttu-id="855dd-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="855dd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="855dd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="855dd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="855dd-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="855dd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="855dd-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="855dd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="855dd-110">[O acesso controlado a pastas](controlled-folders.md) ajuda você a proteger dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="855dd-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="855dd-111">O acesso controlado a pastas está incluído no Windows 10 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="855dd-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="855dd-112">Você pode habilitar o acesso controlado a pastas usando qualquer um desses métodos:</span><span class="sxs-lookup"><span data-stu-id="855dd-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="855dd-113">Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="855dd-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="855dd-114">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="855dd-114">Microsoft Endpoint Manager</span></span>](#endpoint-manager)
* [<span data-ttu-id="855dd-115">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="855dd-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="855dd-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="855dd-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="855dd-117">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="855dd-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="855dd-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="855dd-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="855dd-119">[O modo de](evaluate-controlled-folder-access.md) auditoria permite testar como o recurso funcionaria (e revisar eventos) sem afetar o uso normal do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="855dd-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="855dd-120">As configurações da Política de Grupo que desabilitam a mesclação de listas de administradores locais substituirão as configurações de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="855dd-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="855dd-121">Eles também substituem pastas protegidas e permitem aplicativos definidos pelo administrador local por meio de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="855dd-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="855dd-122">Essas políticas incluem:</span><span class="sxs-lookup"><span data-stu-id="855dd-122">These policies include:</span></span>

* <span data-ttu-id="855dd-123">Microsoft Defender Antivírus configurar **o comportamento de mesclagem de administrador local para listas**</span><span class="sxs-lookup"><span data-stu-id="855dd-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="855dd-124">System Center Endpoint Protection permitir **que os usuários adicionem exclusões e substituições**</span><span class="sxs-lookup"><span data-stu-id="855dd-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="855dd-125">Para obter mais informações sobre como desabilitar a mesclação de listas locais, consulte Prevent or allow users [to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="855dd-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="855dd-126">Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="855dd-126">Windows Security app</span></span>

1. <span data-ttu-id="855dd-127">Abra o Segurança do Windows aplicativo selecionando o ícone de escudo na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="855dd-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="855dd-128">Você também pode pesquisar o menu iniciar para **Defender**.</span><span class="sxs-lookup"><span data-stu-id="855dd-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="855dd-129">Selecione o **&** proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e selecione **Proteção contra ransomware**.</span><span class="sxs-lookup"><span data-stu-id="855dd-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="855dd-130">De definir a opção para **Acesso controlado à pasta** como **On**.</span><span class="sxs-lookup"><span data-stu-id="855dd-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="855dd-131">Se o acesso controlado a pastas estiver configurado com A Política de Grupo, PowerShell ou CSPs MDM, o estado mudará no aplicativo Segurança do Windows após uma reinicialização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="855dd-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="855dd-132">Se o recurso for definido como **Modo de** Auditoria com qualquer uma dessas ferramentas, o aplicativo Segurança do Windows mostrará o estado como **Off**.</span><span class="sxs-lookup"><span data-stu-id="855dd-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="855dd-133">Se você estiver protegendo dados de perfil de usuário, recomendamos que o perfil de usuário deve estar na unidade de instalação Windows padrão.</span><span class="sxs-lookup"><span data-stu-id="855dd-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="endpoint-manager"></a><span data-ttu-id="855dd-134">Gerenciador de Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="855dd-134">Endpoint Manager</span></span>

1. <span data-ttu-id="855dd-135">Entre no Endpoint Manager [e](https://endpoint.microsoft.com) abra a Segurança do Ponto de **Extremidade.**</span><span class="sxs-lookup"><span data-stu-id="855dd-135">Sign in to the [Endpoint Manager](https://endpoint.microsoft.com) and open **Endpoint Security**.</span></span>

2. <span data-ttu-id="855dd-136">Vá para **Política de Redução de Superfície de**  >  **Ataque**.</span><span class="sxs-lookup"><span data-stu-id="855dd-136">Go to **Attack Surface Reduction** > **Policy**.</span></span>

3. <span data-ttu-id="855dd-137">Selecione **Plataforma,** escolha **Windows 10 e posterior** e selecione o perfil Regras de Redução de Superfície de **Ataque**  >  **Criar**.</span><span class="sxs-lookup"><span data-stu-id="855dd-137">Select **Platform**, choose **Windows 10 and later**, and select the profile **Attack Surface Reduction rules** > **Create**.</span></span>

4.  <span data-ttu-id="855dd-138">Nomeia a política e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="855dd-138">Name the policy and add a description.</span></span> <span data-ttu-id="855dd-139">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="855dd-139">Select **Next**.</span></span>

5.  <span data-ttu-id="855dd-140">Role para baixo até a parte inferior, selecione o menu drop-down **Habilitar Proteção** de Pasta e escolha **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="855dd-140">Scroll down to the bottom, select the **Enable Folder Protection** drop-down, and choose **Enable**.</span></span>

6.  <span data-ttu-id="855dd-141">Selecione **Lista de pastas adicionais que precisam ser protegidas** e adicione as pastas que precisam ser protegidas.</span><span class="sxs-lookup"><span data-stu-id="855dd-141">Select **List of additional folders that need to be protected** and add the folders that need to be protected.</span></span>

7.  <span data-ttu-id="855dd-142">Selecione **Lista de aplicativos que têm acesso** a pastas protegidas e adicione os aplicativos que têm acesso a pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="855dd-142">Select **List of apps that have access to protected folders** and add the apps that have access to protected folders.</span></span>

8.  <span data-ttu-id="855dd-143">Selecione **Excluir arquivos e caminhos das regras** de redução de superfície de ataque e adicione os arquivos e caminhos que precisam ser excluídos das regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="855dd-143">Select **Exclude files and paths from attack surface reduction rules** and add the files and paths that need to be excluded from attack surface reduction rules.</span></span>

9.  <span data-ttu-id="855dd-144">Selecione as **atribuições de perfil,** atribua a Todos os **Usuários & Todos os** Dispositivos e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="855dd-144">Select the profile **Assignments**, assign to **All Users & All Devices**, and select **Save**.</span></span>

10.  <span data-ttu-id="855dd-145">Selecione **Próximo para** salvar cada folha aberta **e,** em seguida, Criar .</span><span class="sxs-lookup"><span data-stu-id="855dd-145">Select **Next** to save each open blade and then **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="855dd-146">Os curingas são suportados para aplicativos, mas não para pastas.</span><span class="sxs-lookup"><span data-stu-id="855dd-146">Wildcards are supported for applications, but not for folders.</span></span> <span data-ttu-id="855dd-147">As subpastas não estão protegidas.</span><span class="sxs-lookup"><span data-stu-id="855dd-147">Subfolders are not protected.</span></span> <span data-ttu-id="855dd-148">Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="855dd-148">Allowed apps will continue to trigger events until they are restarted.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="855dd-149">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="855dd-149">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="855dd-150">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="855dd-150">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="855dd-151">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="855dd-151">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="855dd-152">Em Microsoft Endpoint Configuration Manager, acesse **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard.**</span><span class="sxs-lookup"><span data-stu-id="855dd-152">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="855dd-153">Selecione **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="855dd-153">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="855dd-154">Insira um nome e uma descrição, selecione **Acesso controlado a** pastas e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="855dd-154">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="855dd-155">Escolha se bloqueia ou audita alterações, permite outros aplicativos ou adiciona outras pastas e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="855dd-155">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="855dd-156">O Wilcard é suportado para aplicativos, mas não para pastas.</span><span class="sxs-lookup"><span data-stu-id="855dd-156">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="855dd-157">As subpastas não estão protegidas.</span><span class="sxs-lookup"><span data-stu-id="855dd-157">Subfolders are not protected.</span></span> <span data-ttu-id="855dd-158">Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="855dd-158">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="855dd-159">Revise as configurações e selecione **Próximo** para criar a política.</span><span class="sxs-lookup"><span data-stu-id="855dd-159">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="855dd-160">Depois que a política for criada, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="855dd-160">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="855dd-161">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="855dd-161">Group Policy</span></span>

1. <span data-ttu-id="855dd-162">Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="855dd-162">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="855dd-163">No **Editor de Gerenciamento de Política de Grupo**, acesse **Configuração do Computador** e selecione **Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="855dd-163">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="855dd-164">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Windows Defender Exploit Guard > acesso controlado à pasta**.</span><span class="sxs-lookup"><span data-stu-id="855dd-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="855dd-165">Clique duas vezes na **configuração Configurar acesso controlado a** pastas e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="855dd-165">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="855dd-166">Na seção opções, você deve especificar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="855dd-166">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="855dd-167">**Habilitar** - Aplicativos mal-intencionados e suspeitos não poderão fazer alterações em arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="855dd-167">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="855dd-168">Uma notificação será fornecida no log Windows evento.</span><span class="sxs-lookup"><span data-stu-id="855dd-168">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="855dd-169">**Desabilitar (Padrão)** - O recurso de acesso controlado a pastas não funcionará.</span><span class="sxs-lookup"><span data-stu-id="855dd-169">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="855dd-170">Todos os aplicativos podem fazer alterações em arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="855dd-170">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="855dd-171">**Modo de** Auditoria - As alterações serão permitidas se um aplicativo mal-intencionado ou suspeito tentar fazer uma alteração em um arquivo em uma pasta protegida.</span><span class="sxs-lookup"><span data-stu-id="855dd-171">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="855dd-172">No entanto, ele será registrado no log de eventos Windows onde você pode avaliar o impacto em sua organização.</span><span class="sxs-lookup"><span data-stu-id="855dd-172">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="855dd-173">**Bloquear somente modificação de** disco - As tentativas por aplicativos não confirmados para gravar em setores de disco serão registradas Windows log de eventos.</span><span class="sxs-lookup"><span data-stu-id="855dd-173">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="855dd-174">Esses logs podem ser encontrados em **Logs de** Aplicativos e Serviços > Microsoft > Windows > Windows Defender > ID > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="855dd-174">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="855dd-175">**Somente** modificação de disco de auditoria - Somente as tentativas de gravação em setores de disco protegidos serão registradas no log de eventos Windows (em Logs de Aplicativos e Serviços da  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **ID Operacional 1124**).</span><span class="sxs-lookup"><span data-stu-id="855dd-175">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="855dd-176">As tentativas de modificar ou excluir arquivos em pastas protegidas não serão gravadas.</span><span class="sxs-lookup"><span data-stu-id="855dd-176">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Captura de tela da opção de política de grupo Habilitado e Modo de Auditoria selecionado no drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="855dd-178">Para habilitar totalmente o acesso controlado a  pastas, você deve definir a opção Política de Grupo como Habilitado e selecionar **Bloquear** no menu suspenso opções.</span><span class="sxs-lookup"><span data-stu-id="855dd-178">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="855dd-179">PowerShell</span><span class="sxs-lookup"><span data-stu-id="855dd-179">PowerShell</span></span>

1. <span data-ttu-id="855dd-180">Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="855dd-180">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="855dd-181">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="855dd-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="855dd-182">Você pode habilitar o recurso no modo de auditoria especificando em `AuditMode` vez de `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="855dd-182">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="855dd-183">Use `Disabled` para desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="855dd-183">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="855dd-184">Confira também</span><span class="sxs-lookup"><span data-stu-id="855dd-184">See also</span></span>

* [<span data-ttu-id="855dd-185">Proteger pastas importantes com acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="855dd-185">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="855dd-186">Personalizar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="855dd-186">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="855dd-187">Avaliar o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="855dd-187">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
