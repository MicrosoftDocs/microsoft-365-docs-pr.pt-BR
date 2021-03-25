---
title: Habilitar o acesso controlado a pastas
keywords: Acesso controlado a pastas, windows 10, windows defender, ransomware, proteger, arquivos, pastas, habilitar, ativar, usar
description: Saiba como proteger seus arquivos importantes habilitando o acesso controlado a pastas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a35c18d805ef3645659f49b8340cbb4cabab2f8d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165064"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="e54d9-104">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="e54d9-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e54d9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e54d9-105">**Applies to:**</span></span>
- [<span data-ttu-id="e54d9-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e54d9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e54d9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e54d9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e54d9-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e54d9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e54d9-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e54d9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e54d9-110">[O acesso controlado a pastas](controlled-folders.md) ajuda você a proteger dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="e54d9-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="e54d9-111">O acesso controlado a pastas está incluído no Windows 10 e no Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e54d9-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="e54d9-112">Você pode habilitar o acesso controlado a pastas usando qualquer um desses métodos:</span><span class="sxs-lookup"><span data-stu-id="e54d9-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="e54d9-113">Aplicativo de Segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="e54d9-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="e54d9-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e54d9-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="e54d9-115">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="e54d9-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="e54d9-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e54d9-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="e54d9-117">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="e54d9-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="e54d9-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e54d9-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="e54d9-119">[O modo de](evaluate-controlled-folder-access.md) auditoria permite testar como o recurso funcionaria (e revisar eventos) sem afetar o uso normal do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e54d9-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="e54d9-120">As configurações da Política de Grupo que desabilitam a mesclação de listas de administradores locais substituirão as configurações de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="e54d9-121">Eles também substituem pastas protegidas e permitem aplicativos definidos pelo administrador local por meio de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="e54d9-122">Essas políticas incluem:</span><span class="sxs-lookup"><span data-stu-id="e54d9-122">These policies include:</span></span>

* <span data-ttu-id="e54d9-123">Microsoft Defender Antivírus **Configurar o comportamento de mesclagem do administrador local para listas**</span><span class="sxs-lookup"><span data-stu-id="e54d9-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="e54d9-124">Proteção de Ponto de Extremidade do System Center **Permitir que os usuários adicionem exclusões e substituições**</span><span class="sxs-lookup"><span data-stu-id="e54d9-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="e54d9-125">Para obter mais informações sobre como desabilitar a mesclação de listas locais, consulte Prevent or allow users [to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span><span class="sxs-lookup"><span data-stu-id="e54d9-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="e54d9-126">Aplicativo de Segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="e54d9-126">Windows Security app</span></span>

1. <span data-ttu-id="e54d9-127">Abra o aplicativo segurança do Windows selecionando o ícone de escudo na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="e54d9-128">Você também pode pesquisar o menu iniciar para **Defender**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="e54d9-129">Selecione o **&** proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e selecione **Proteção contra ransomware**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="e54d9-130">De definir a opção para **Acesso controlado à pasta** como **On**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="e54d9-131">Se o acesso controlado a pastas estiver configurado com A Política de Grupo, PowerShell ou CSPs MDM, o estado mudará no aplicativo segurança do Windows após uma reinicialização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e54d9-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="e54d9-132">Se o recurso for definido como **Modo de** Auditoria com qualquer uma dessas ferramentas, o aplicativo segurança do Windows mostrará o estado como **Off**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="e54d9-133">Se você estiver protegendo dados de perfil de usuário, recomendamos que o perfil de usuário deve estar na unidade de instalação padrão do Windows.</span><span class="sxs-lookup"><span data-stu-id="e54d9-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="e54d9-134">Intune</span><span class="sxs-lookup"><span data-stu-id="e54d9-134">Intune</span></span>

1. <span data-ttu-id="e54d9-135">Entre no [portal do Azure e](https://portal.azure.com) abra o Intune.</span><span class="sxs-lookup"><span data-stu-id="e54d9-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="e54d9-136">Vá para **Configuração do dispositivo**  >  **Perfis**  >  **Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="e54d9-137">Nomeia o perfil, escolha **Windows 10 e posterior e** Proteção de Ponto de **Extremidade**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="e54d9-138">![Criar perfil de proteção de ponto de extremidade](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="e54d9-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="e54d9-139">Vá para **Configurar Windows Defender** acesso controlado de pasta  >  do Exploit **Guard**  >    >  **Enable**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="e54d9-140">Digite o caminho para cada aplicativo que tenha acesso a pastas protegidas e o caminho para qualquer pasta adicional que precise de proteção.</span><span class="sxs-lookup"><span data-stu-id="e54d9-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="e54d9-141">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-141">Select **Add**.</span></span><br/> <span data-ttu-id="e54d9-142">![Habilitar o acesso controlado a pastas no Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="e54d9-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="e54d9-143">O Wilcard é suportado para aplicativos, mas não para pastas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="e54d9-144">As subpastas não estão protegidas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-144">Subfolders are not protected.</span></span> <span data-ttu-id="e54d9-145">Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="e54d9-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="e54d9-146">Selecione **OK** para salvar cada folha aberta e **Criar**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="e54d9-147">Selecione as **atribuições de perfil,** atribua a Todos os **Usuários & Todos os** Dispositivos e **Salve**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="e54d9-148">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="e54d9-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="e54d9-149">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="e54d9-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e54d9-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="e54d9-151">No Microsoft Endpoint Configuration Manager, acesse **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard.**</span><span class="sxs-lookup"><span data-stu-id="e54d9-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="e54d9-152">Selecione **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="e54d9-153">Insira um nome e uma descrição, selecione **Acesso controlado a** pastas e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="e54d9-154">Escolha se bloqueia ou audita alterações, permite outros aplicativos ou adiciona outras pastas e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e54d9-155">O Wilcard é suportado para aplicativos, mas não para pastas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="e54d9-156">As subpastas não estão protegidas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-156">Subfolders are not protected.</span></span> <span data-ttu-id="e54d9-157">Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="e54d9-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="e54d9-158">Revise as configurações e selecione **Próximo** para criar a política.</span><span class="sxs-lookup"><span data-stu-id="e54d9-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="e54d9-159">Depois que a política for criada, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="e54d9-160">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="e54d9-160">Group Policy</span></span>

1. <span data-ttu-id="e54d9-161">Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="e54d9-162">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="e54d9-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="e54d9-163">Expanda a árvore para **componentes do Windows > o Microsoft Defender Antivírus > Windows Defender Exploit Guard > acesso controlado a pastas.**</span><span class="sxs-lookup"><span data-stu-id="e54d9-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="e54d9-164">Clique duas vezes na **configuração Configurar acesso controlado a** pastas e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="e54d9-165">Na seção opções, você deve especificar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e54d9-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="e54d9-166">**Habilitar** - Aplicativos mal-intencionados e suspeitos não poderão fazer alterações em arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="e54d9-167">Uma notificação será fornecida no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="e54d9-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="e54d9-168">**Desabilitar (Padrão)** - O recurso de acesso controlado a pastas não funcionará.</span><span class="sxs-lookup"><span data-stu-id="e54d9-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="e54d9-169">Todos os aplicativos podem fazer alterações em arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="e54d9-170">**Modo de** Auditoria - As alterações serão permitidas se um aplicativo mal-intencionado ou suspeito tentar fazer uma alteração em um arquivo em uma pasta protegida.</span><span class="sxs-lookup"><span data-stu-id="e54d9-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="e54d9-171">No entanto, ele será gravado no log de eventos do Windows onde você pode avaliar o impacto em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e54d9-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="e54d9-172">**Bloquear somente modificação de** disco - As tentativas por aplicativos não-não-confirmados para gravar em setores de disco serão registradas no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="e54d9-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="e54d9-173">Esses logs podem ser encontrados em **Logs de** Aplicativos e Serviços > Microsoft > Windows > Windows Defender > ID operacional > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="e54d9-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="e54d9-174">**Somente modificação de** disco de auditoria - Somente as tentativas de gravação em setores de disco protegidos serão registradas no log de eventos do Windows (em Logs de Aplicativos e Serviços do  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **ID Operacional 1124**).</span><span class="sxs-lookup"><span data-stu-id="e54d9-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="e54d9-175">As tentativas de modificar ou excluir arquivos em pastas protegidas não serão gravadas.</span><span class="sxs-lookup"><span data-stu-id="e54d9-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Captura de tela da opção de política de grupo Habilitado e Modo de Auditoria selecionado no drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="e54d9-177">Para habilitar totalmente o acesso controlado a  pastas, você deve definir a opção Política de Grupo como Habilitado e selecionar **Bloquear** no menu suspenso opções.</span><span class="sxs-lookup"><span data-stu-id="e54d9-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="e54d9-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e54d9-178">PowerShell</span></span>

1. <span data-ttu-id="e54d9-179">Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="e54d9-180">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e54d9-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="e54d9-181">Você pode habilitar o recurso no modo de auditoria especificando em `AuditMode` vez de `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="e54d9-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="e54d9-182">Use `Disabled` para desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="e54d9-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="e54d9-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="e54d9-183">See also</span></span>

* [<span data-ttu-id="e54d9-184">Proteger pastas importantes com acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="e54d9-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="e54d9-185">Personalizar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="e54d9-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="e54d9-186">Avaliar o Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e54d9-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-atp.md)
