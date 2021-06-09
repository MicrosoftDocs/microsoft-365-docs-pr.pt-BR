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
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1d09eaf04999478a0cd0b4907667a522a23fb39f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841973"
---
# <a name="enable-controlled-folder-access"></a><span data-ttu-id="56020-104">Habilitar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="56020-104">Enable controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="56020-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="56020-105">**Applies to:**</span></span>
- [<span data-ttu-id="56020-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="56020-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="56020-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="56020-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="56020-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="56020-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="56020-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="56020-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="56020-110">[O acesso controlado a pastas](controlled-folders.md) ajuda você a proteger dados valiosos contra aplicativos mal-intencionados e ameaças, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="56020-110">[Controlled folder access](controlled-folders.md) helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="56020-111">O acesso controlado a pastas está incluído no Windows 10 e Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="56020-111">Controlled folder access is included with Windows 10 and Windows Server 2019.</span></span>

<span data-ttu-id="56020-112">Você pode habilitar o acesso controlado a pastas usando qualquer um desses métodos:</span><span class="sxs-lookup"><span data-stu-id="56020-112">You can enable controlled folder access by using any of these methods:</span></span>

* [<span data-ttu-id="56020-113">Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="56020-113">Windows Security app</span></span>](#windows-security-app)
* [<span data-ttu-id="56020-114">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="56020-114">Microsoft Intune</span></span>](#intune)
* [<span data-ttu-id="56020-115">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="56020-115">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="56020-116">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="56020-116">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
* [<span data-ttu-id="56020-117">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="56020-117">Group Policy</span></span>](#group-policy)
* [<span data-ttu-id="56020-118">PowerShell</span><span class="sxs-lookup"><span data-stu-id="56020-118">PowerShell</span></span>](#powershell)

<span data-ttu-id="56020-119">[O modo de](evaluate-controlled-folder-access.md) auditoria permite testar como o recurso funcionaria (e revisar eventos) sem afetar o uso normal do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="56020-119">[Audit mode](evaluate-controlled-folder-access.md) allows you to test how the feature would work (and review events) without impacting the normal use of the device.</span></span>

<span data-ttu-id="56020-120">As configurações da Política de Grupo que desabilitam a mesclação de listas de administradores locais substituirão as configurações de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="56020-120">Group Policy settings that disable local administrator list merging will override controlled folder access settings.</span></span> <span data-ttu-id="56020-121">Eles também substituem pastas protegidas e permitem aplicativos definidos pelo administrador local por meio de acesso controlado a pastas.</span><span class="sxs-lookup"><span data-stu-id="56020-121">They also override protected folders and allowed apps set by the local administrator through controlled folder access.</span></span> <span data-ttu-id="56020-122">Essas políticas incluem:</span><span class="sxs-lookup"><span data-stu-id="56020-122">These policies include:</span></span>

* <span data-ttu-id="56020-123">Microsoft Defender Antivírus configurar **o comportamento de mesclagem de administrador local para listas**</span><span class="sxs-lookup"><span data-stu-id="56020-123">Microsoft Defender Antivirus **Configure local administrator merge behavior for lists**</span></span>
* <span data-ttu-id="56020-124">System Center Endpoint Protection permitir **que os usuários adicionem exclusões e substituições**</span><span class="sxs-lookup"><span data-stu-id="56020-124">System Center Endpoint Protection **Allow users to add exclusions and overrides**</span></span>

<span data-ttu-id="56020-125">Para obter mais informações sobre como desabilitar a mesclação de listas locais, consulte Prevent or allow users [to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span><span class="sxs-lookup"><span data-stu-id="56020-125">For more information about disabling local list merging, see [Prevent or allow users to locally modify Microsoft Defender AV policy settings](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).</span></span>

## <a name="windows-security-app"></a><span data-ttu-id="56020-126">Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="56020-126">Windows Security app</span></span>

1. <span data-ttu-id="56020-127">Abra o Segurança do Windows aplicativo selecionando o ícone de escudo na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="56020-127">Open the Windows Security app by selecting the shield icon in the task bar.</span></span> <span data-ttu-id="56020-128">Você também pode pesquisar o menu iniciar para **Defender**.</span><span class="sxs-lookup"><span data-stu-id="56020-128">You can also search the start menu for **Defender**.</span></span>

2. <span data-ttu-id="56020-129">Selecione o **&** proteção contra ameaças (ou o ícone de escudo na barra de menus esquerda) e selecione **Proteção contra ransomware**.</span><span class="sxs-lookup"><span data-stu-id="56020-129">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Ransomware protection**.</span></span>

3. <span data-ttu-id="56020-130">De definir a opção para **Acesso controlado à pasta** como **On**.</span><span class="sxs-lookup"><span data-stu-id="56020-130">Set the switch for **Controlled folder access** to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="56020-131">Se o acesso controlado a pastas estiver configurado com A Política de Grupo, PowerShell ou CSPs MDM, o estado mudará no aplicativo Segurança do Windows após uma reinicialização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="56020-131">If controlled folder access is configured with Group Policy, PowerShell, or MDM CSPs, the state will change in the Windows Security app after a restart of the device.</span></span>
> <span data-ttu-id="56020-132">Se o recurso for definido como **Modo de** Auditoria com qualquer uma dessas ferramentas, o aplicativo Segurança do Windows mostrará o estado como **Off**.</span><span class="sxs-lookup"><span data-stu-id="56020-132">If the feature is set to **Audit mode** with any of those tools, the Windows Security app will show the state as **Off**.</span></span>
> <span data-ttu-id="56020-133">Se você estiver protegendo dados de perfil de usuário, recomendamos que o perfil de usuário deve estar na unidade de instalação Windows padrão.</span><span class="sxs-lookup"><span data-stu-id="56020-133">If you are protecting user profile data, we recommend that the user profile should be on the default Windows installation drive.</span></span>

## <a name="intune"></a><span data-ttu-id="56020-134">Intune</span><span class="sxs-lookup"><span data-stu-id="56020-134">Intune</span></span>

1. <span data-ttu-id="56020-135">Entre no [portal do Azure e](https://portal.azure.com) abra o Intune.</span><span class="sxs-lookup"><span data-stu-id="56020-135">Sign in to the [Azure portal](https://portal.azure.com) and open Intune.</span></span>

2. <span data-ttu-id="56020-136">Vá para **Configuração do dispositivo**  >  **Perfis**  >  **Criar perfil**.</span><span class="sxs-lookup"><span data-stu-id="56020-136">Go to **Device configuration** > **Profiles** > **Create profile**.</span></span>

3. <span data-ttu-id="56020-137">Nomee o perfil, escolha **Windows 10 e posterior e** Proteção de Ponto de **Extremidade.**</span><span class="sxs-lookup"><span data-stu-id="56020-137">Name the profile, choose **Windows 10 and later** and **Endpoint protection**.</span></span> <br/> <span data-ttu-id="56020-138">![Criar perfil de proteção de ponto de extremidade](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span><span class="sxs-lookup"><span data-stu-id="56020-138">![Create endpoint protection profile](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile)</span></span> <br/>

4. <span data-ttu-id="56020-139">Vá para **Configurar Windows Defender** acesso controlado de pasta  >  do Exploit **Guard**  >    >  **Enable**.</span><span class="sxs-lookup"><span data-stu-id="56020-139">Go to **Configure** > **Windows Defender Exploit Guard** > **Controlled folder access** > **Enable**.</span></span>

5. <span data-ttu-id="56020-140">Digite o caminho para cada aplicativo que tenha acesso a pastas protegidas e o caminho para qualquer pasta adicional que precise de proteção.</span><span class="sxs-lookup"><span data-stu-id="56020-140">Type the path to each application that has access to protected folders and the path to any additional folder that needs protection.</span></span> <span data-ttu-id="56020-141">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="56020-141">Select **Add**.</span></span><br/> <span data-ttu-id="56020-142">![Habilitar o acesso controlado a pastas no Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span><span class="sxs-lookup"><span data-stu-id="56020-142">![Enable controlled folder access in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)</span></span><br/>

   > [!NOTE]
   > <span data-ttu-id="56020-143">O Wilcard é suportado para aplicativos, mas não para pastas.</span><span class="sxs-lookup"><span data-stu-id="56020-143">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="56020-144">As subpastas não estão protegidas.</span><span class="sxs-lookup"><span data-stu-id="56020-144">Subfolders are not protected.</span></span> <span data-ttu-id="56020-145">Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="56020-145">Allowed apps will continue to trigger events until they are restarted.</span></span>

6. <span data-ttu-id="56020-146">Selecione **OK** para salvar cada folha aberta e **Criar**.</span><span class="sxs-lookup"><span data-stu-id="56020-146">Select **OK** to save each open blade and **Create**.</span></span>

7. <span data-ttu-id="56020-147">Selecione as **atribuições de perfil,** atribua a Todos os **Usuários & Todos os** Dispositivos e **Salve**.</span><span class="sxs-lookup"><span data-stu-id="56020-147">Select the profile **Assignments**, assign to **All Users & All Devices**, and **Save**.</span></span>

## <a name="mobile-device-management-mdm"></a><span data-ttu-id="56020-148">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="56020-148">Mobile Device Management (MDM)</span></span>

<span data-ttu-id="56020-149">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP) para permitir que os aplicativos façam alterações em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="56020-149">Use the [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="56020-150">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="56020-150">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="56020-151">Em Microsoft Endpoint Configuration Manager, acesse **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard.**</span><span class="sxs-lookup"><span data-stu-id="56020-151">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="56020-152">Selecione **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="56020-152">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="56020-153">Insira um nome e uma descrição, selecione **Acesso controlado a** pastas e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="56020-153">Enter a name and a description, select **Controlled folder access**, and select **Next**.</span></span>

4. <span data-ttu-id="56020-154">Escolha se bloqueia ou audita alterações, permite outros aplicativos ou adiciona outras pastas e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="56020-154">Choose whether block or audit changes, allow other apps, or add other folders, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="56020-155">O Wilcard é suportado para aplicativos, mas não para pastas.</span><span class="sxs-lookup"><span data-stu-id="56020-155">Wilcard is supported for applications, but not for folders.</span></span> <span data-ttu-id="56020-156">As subpastas não estão protegidas.</span><span class="sxs-lookup"><span data-stu-id="56020-156">Subfolders are not protected.</span></span> <span data-ttu-id="56020-157">Os aplicativos permitidos continuarão a disparar eventos até que sejam reiniciados.</span><span class="sxs-lookup"><span data-stu-id="56020-157">Allowed apps will continue to trigger events until they are restarted.</span></span>

5. <span data-ttu-id="56020-158">Revise as configurações e selecione **Próximo** para criar a política.</span><span class="sxs-lookup"><span data-stu-id="56020-158">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="56020-159">Depois que a política for criada, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="56020-159">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="56020-160">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="56020-160">Group Policy</span></span>

1. <span data-ttu-id="56020-161">Em seu dispositivo de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="56020-161">On your Group Policy management device, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="56020-162">No **Editor de Gerenciamento de Política de Grupo**, acesse **Configuração do Computador** e selecione **Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="56020-162">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="56020-163">Expanda a árvore para **Windows componentes > Microsoft Defender Antivírus > Windows Defender Exploit Guard > acesso controlado à pasta**.</span><span class="sxs-lookup"><span data-stu-id="56020-163">Expand the tree to **Windows components > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Controlled folder access**.</span></span>

4. <span data-ttu-id="56020-164">Clique duas vezes na **configuração Configurar acesso controlado a** pastas e de definir a opção como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="56020-164">Double-click the **Configure Controlled folder access** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="56020-165">Na seção opções, você deve especificar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="56020-165">In the options section you must specify one of the following options:</span></span>
    * <span data-ttu-id="56020-166">**Habilitar** - Aplicativos mal-intencionados e suspeitos não poderão fazer alterações em arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="56020-166">**Enable** - Malicious and suspicious apps won't be allowed to make changes to files in protected folders.</span></span> <span data-ttu-id="56020-167">Uma notificação será fornecida no log Windows evento.</span><span class="sxs-lookup"><span data-stu-id="56020-167">A notification will be provided in the Windows event log.</span></span>
    * <span data-ttu-id="56020-168">**Desabilitar (Padrão)** - O recurso de acesso controlado a pastas não funcionará.</span><span class="sxs-lookup"><span data-stu-id="56020-168">**Disable (Default)** - The Controlled folder access feature won't work.</span></span> <span data-ttu-id="56020-169">Todos os aplicativos podem fazer alterações em arquivos em pastas protegidas.</span><span class="sxs-lookup"><span data-stu-id="56020-169">All apps can make changes to files in protected folders.</span></span>
    * <span data-ttu-id="56020-170">**Modo de** Auditoria - As alterações serão permitidas se um aplicativo mal-intencionado ou suspeito tentar fazer uma alteração em um arquivo em uma pasta protegida.</span><span class="sxs-lookup"><span data-stu-id="56020-170">**Audit Mode** - Changes will be allowed if a malicious or suspicious app attempts to make a change to a file in a protected folder.</span></span> <span data-ttu-id="56020-171">No entanto, ele será registrado no log de eventos Windows onde você pode avaliar o impacto em sua organização.</span><span class="sxs-lookup"><span data-stu-id="56020-171">However, it will be recorded in the Windows event log where you can assess the impact on your organization.</span></span>
    * <span data-ttu-id="56020-172">**Bloquear somente modificação de** disco - As tentativas por aplicativos não confirmados para gravar em setores de disco serão registradas Windows log de eventos.</span><span class="sxs-lookup"><span data-stu-id="56020-172">**Block disk modification only** - Attempts by untrusted apps to write to disk sectors will be logged in Windows Event log.</span></span> <span data-ttu-id="56020-173">Esses logs podem ser encontrados em **Logs de** Aplicativos e Serviços > Microsoft > Windows > Windows Defender > ID > ID 1123.</span><span class="sxs-lookup"><span data-stu-id="56020-173">These logs can be found in **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.</span></span>
    * <span data-ttu-id="56020-174">**Somente** modificação de disco de auditoria - Somente as tentativas de gravação em setores de disco protegidos serão registradas no log de eventos Windows (em Logs de Aplicativos e Serviços da  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **ID Operacional 1124**).</span><span class="sxs-lookup"><span data-stu-id="56020-174">**Audit disk modification only** - Only attempts to write to protected disk sectors will be recorded in the Windows event log (under **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender** > **Operational** > **ID 1124**).</span></span> <span data-ttu-id="56020-175">As tentativas de modificar ou excluir arquivos em pastas protegidas não serão gravadas.</span><span class="sxs-lookup"><span data-stu-id="56020-175">Attempts to modify or delete files in protected folders won't be recorded.</span></span>

      ![Captura de tela da opção de política de grupo Habilitado e Modo de Auditoria selecionado no drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> <span data-ttu-id="56020-177">Para habilitar totalmente o acesso controlado a  pastas, você deve definir a opção Política de Grupo como Habilitado e selecionar **Bloquear** no menu suspenso opções.</span><span class="sxs-lookup"><span data-stu-id="56020-177">To fully enable controlled folder access, you must set the Group Policy option to **Enabled** and select **Block** in the options drop-down menu.</span></span>

## <a name="powershell"></a><span data-ttu-id="56020-178">PowerShell</span><span class="sxs-lookup"><span data-stu-id="56020-178">PowerShell</span></span>

1. <span data-ttu-id="56020-179">Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="56020-179">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="56020-180">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="56020-180">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

<span data-ttu-id="56020-181">Você pode habilitar o recurso no modo de auditoria especificando em `AuditMode` vez de `Enabled` .</span><span class="sxs-lookup"><span data-stu-id="56020-181">You can enable the feature in audit mode by specifying `AuditMode` instead of `Enabled`.</span></span>

<span data-ttu-id="56020-182">Use `Disabled` para desativar o recurso.</span><span class="sxs-lookup"><span data-stu-id="56020-182">Use `Disabled` to turn off the feature.</span></span>

## <a name="see-also"></a><span data-ttu-id="56020-183">Confira também</span><span class="sxs-lookup"><span data-stu-id="56020-183">See also</span></span>

* [<span data-ttu-id="56020-184">Proteger pastas importantes com acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="56020-184">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
* [<span data-ttu-id="56020-185">Personalizar o acesso controlado a pastas</span><span class="sxs-lookup"><span data-stu-id="56020-185">Customize controlled folder access</span></span>](customize-controlled-folders.md)
* [<span data-ttu-id="56020-186">Avaliar o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="56020-186">Evaluate Microsoft Defender for Endpoint</span></span>](evaluate-mde.md)
