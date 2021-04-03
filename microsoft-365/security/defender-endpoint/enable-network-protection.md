---
title: Ativar a proteção de rede
description: Habilita a proteção de rede com a Política de Grupo, o PowerShell ou o Gerenciador de Configuração e Gerenciamento de Dispositivo Móvel.
keywords: Proteção do ANetwork, explorações, site mal-intencionado, ip, domínio, domínios, habilitar, ativar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a513013c4b5f41cf95b876648882cb56ba818b32
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570991"
---
# <a name="turn-on-network-protection"></a><span data-ttu-id="e1ff6-104">Ativar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="e1ff6-104">Turn on network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e1ff6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1ff6-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e1ff6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e1ff6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1ff6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e1ff6-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e1ff6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e1ff6-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e1ff6-110">[A proteção de](network-protection.md) rede ajuda a impedir que os funcionários usem qualquer aplicativo para acessar domínios perigosos que podem hospedar esquemas de phishing, explorações e outros conteúdos mal-intencionados na Internet.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-110">[Network protection](network-protection.md) helps to prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the internet.</span></span> <span data-ttu-id="e1ff6-111">Você pode [auditar](evaluate-network-protection.md) a proteção de rede em um ambiente de teste para exibir quais aplicativos seriam bloqueados antes de habilita-la.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-111">You can [audit network protection](evaluate-network-protection.md) in a test environment to view which apps would be blocked before you enable it.</span></span>

[<span data-ttu-id="e1ff6-112">Saiba mais sobre as opções de configuração de filtragem de rede</span><span class="sxs-lookup"><span data-stu-id="e1ff6-112">Learn more about network filtering configuration options</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a><span data-ttu-id="e1ff6-113">Verificar se a proteção de rede está habilitada</span><span class="sxs-lookup"><span data-stu-id="e1ff6-113">Check if network protection is enabled</span></span>

<span data-ttu-id="e1ff6-114">Verifique se a proteção de rede foi habilitada em um dispositivo local usando o editor do Registro.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-114">Check if network protection has been enabled on a local device by using Registry editor.</span></span>

1. <span data-ttu-id="e1ff6-115">Selecione o **botão Iniciar** na barra de tarefas e digite **regedit** para abrir o editor do Registro</span><span class="sxs-lookup"><span data-stu-id="e1ff6-115">Select the **Start** button in the task bar and type **regedit** to open Registry editor</span></span>
1. <span data-ttu-id="e1ff6-116">Escolha **HKEY_LOCAL_MACHINE** no menu lateral</span><span class="sxs-lookup"><span data-stu-id="e1ff6-116">Choose **HKEY_LOCAL_MACHINE** from the side menu</span></span>
1. <span data-ttu-id="e1ff6-117">Navegue pelos menus aninhados para **Políticas de SOFTWARE**  >    >  **Microsoft**  >  **Windows Defender** Windows Defender Proteção de  >    >  **Rede** do Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="e1ff6-117">Navigate through the nested menus to **SOFTWARE** > **Policies** > **Microsoft** > **Windows Defender** > **Windows Defender Exploit Guard** > **Network Protection**</span></span>
1. <span data-ttu-id="e1ff6-118">Selecione **EnableNetworkProtection** para ver o estado atual da proteção de rede no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e1ff6-118">Select **EnableNetworkProtection** to see the current state of network protection on the device</span></span>

    * <span data-ttu-id="e1ff6-119">0 ou **Off**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-119">0, or **Off**</span></span>
    * <span data-ttu-id="e1ff6-120">1 ou **On**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-120">1, or **On**</span></span>
    * <span data-ttu-id="e1ff6-121">2, ou **Modo de** auditoria</span><span class="sxs-lookup"><span data-stu-id="e1ff6-121">2, or **Audit** mode</span></span>
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a><span data-ttu-id="e1ff6-123">Habilitar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="e1ff6-123">Enable network protection</span></span>

<span data-ttu-id="e1ff6-124">Habilita a proteção de rede usando qualquer um desses métodos:</span><span class="sxs-lookup"><span data-stu-id="e1ff6-124">Enable network protection by using any of these methods:</span></span>

* [<span data-ttu-id="e1ff6-125">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ff6-125">PowerShell</span></span>](#powershell)
* [<span data-ttu-id="e1ff6-126">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="e1ff6-126">Mobile Device Management (MDM)</span></span>](#mobile-device-management-mdm)
* [<span data-ttu-id="e1ff6-127">Microsoft Endpoint Manager /Intune</span><span class="sxs-lookup"><span data-stu-id="e1ff6-127">Microsoft Endpoint Manager / Intune</span></span>](#microsoft-endpoint-manager-formerly-intune)
* [<span data-ttu-id="e1ff6-128">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="e1ff6-128">Group Policy</span></span>](#group-policy)

### <a name="powershell"></a><span data-ttu-id="e1ff6-129">PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1ff6-129">PowerShell</span></span>

1. <span data-ttu-id="e1ff6-130">Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-130">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="e1ff6-131">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e1ff6-131">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. <span data-ttu-id="e1ff6-132">Opcional: Habilita o recurso no modo de auditoria usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e1ff6-132">Optional: Enable the feature in audit mode using the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    <span data-ttu-id="e1ff6-133">Use `Disabled` em vez de ou para desativar o `AuditMode` `Enabled` recurso.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-133">Use `Disabled` instead of `AuditMode` or `Enabled` to turn off the feature.</span></span>

### <a name="mobile-device-management-mdm"></a><span data-ttu-id="e1ff6-134">Gerenciamento de dispositivo móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="e1ff6-134">Mobile device management (MDM)</span></span>

<span data-ttu-id="e1ff6-135">Use o provedor de serviço de configuração [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) (CSP) para habilitar ou desabilitar a proteção de rede ou habilitar o modo de auditoria.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-135">Use the [./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) configuration service provider (CSP) to enable or disable network protection or enable audit mode.</span></span>

### <a name="microsoft-endpoint-manager-formerly-intune"></a><span data-ttu-id="e1ff6-136">Microsoft Endpoint Manager (anteriormente Intune)</span><span class="sxs-lookup"><span data-stu-id="e1ff6-136">Microsoft Endpoint Manager (formerly Intune)</span></span>

1. <span data-ttu-id="e1ff6-137">Entre no Centro de administração do Microsoft Endpoint Manager (https://endpoint.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e1ff6-137">Sign into the Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com)</span></span>

2. <span data-ttu-id="e1ff6-138">Criar ou editar um perfil [de configuração de proteção de ponto de extremidade](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span><span class="sxs-lookup"><span data-stu-id="e1ff6-138">Create or edit an [endpoint protection configuration profile](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-configure)</span></span>

3. <span data-ttu-id="e1ff6-139">Em "Configurações configurações" no fluxo de perfil, acesse **Microsoft Defender Exploit Guard** Network  >  **filtering** Network protection  >    >  **Enable** or Audit **only**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-139">Under "Configuration Settings" in the profile flow, go to **Microsoft Defender Exploit Guard** > **Network filtering** > **Network protection** > **Enable** or **Audit only**</span></span>

### <a name="group-policy"></a><span data-ttu-id="e1ff6-140">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="e1ff6-140">Group Policy</span></span>

<span data-ttu-id="e1ff6-141">Use o procedimento a seguir para habilitar a proteção de rede em computadores ingressados no domínio ou em um computador autônomo.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-141">Use the following procedure to enable network protection on domain-joined computers or on a standalone computer.</span></span>

1. <span data-ttu-id="e1ff6-142">Em um computador autônomo, vá para **Iniciar** e digite e selecione **Editar política de grupo**.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-142">On a standalone computer, go to **Start** and then type and select **Edit group policy**.</span></span>

    <span data-ttu-id="e1ff6-143">*-Ou-*</span><span class="sxs-lookup"><span data-stu-id="e1ff6-143">*-Or-*</span></span>

    <span data-ttu-id="e1ff6-144">Em um computador de gerenciamento de Política de Grupo ingressado no domínio, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-144">On a domain-joined Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="e1ff6-145">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-145">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="e1ff6-146">Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Windows Defender Proteção de** Rede do Exploit  >  Guard.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Network protection**.</span></span>

> [!NOTE]
> <span data-ttu-id="e1ff6-147">Em versões mais antigas do Windows, o caminho da política de grupo pode dizer "Windows Defender Antivírus" em vez de "Microsoft Defender Antivírus".</span><span class="sxs-lookup"><span data-stu-id="e1ff6-147">On older versions of Windows, the group policy path may say "Windows Defender Antivirus" instead of "Microsoft Defender Antivirus."</span></span>

4. <span data-ttu-id="e1ff6-148">Clique duas vezes na **configuração Impedir que usuários e aplicativos** acessem sites perigosos e de definir a opção **como Habilitado.**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-148">Double-click the **Prevent users and apps from accessing dangerous websites** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="e1ff6-149">Na seção opções, você deve especificar uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e1ff6-149">In the options section, you must specify one of the following options:</span></span>
    * <span data-ttu-id="e1ff6-150">**Bloquear** - Os usuários não podem acessar endereços IP mal-intencionados e domínios</span><span class="sxs-lookup"><span data-stu-id="e1ff6-150">**Block** - Users can't access malicious IP addresses and domains</span></span>
    * <span data-ttu-id="e1ff6-151">**Desabilitar (Padrão)** - O recurso de proteção de rede não funcionará.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-151">**Disable (Default)** - The Network protection feature won't work.</span></span> <span data-ttu-id="e1ff6-152">Os usuários não serão impedidos de acessar domínios mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="e1ff6-152">Users won't be blocked from accessing malicious domains</span></span>
    * <span data-ttu-id="e1ff6-153">**Modo de** Auditoria - Se um usuário visitar um endereço IP ou domínio mal-intencionado, um evento será gravado no log de eventos do Windows.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-153">**Audit Mode** - If a user visits a malicious IP address or domain, an event will be recorded in the Windows event log.</span></span> <span data-ttu-id="e1ff6-154">No entanto, o usuário não será impedido de visitar o endereço.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-154">However, the user won't be blocked from visiting the address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e1ff6-155">Para habilitar totalmente a proteção de  rede, você deve definir a opção Política de Grupo como Habilitada e também selecionar **Bloquear** no menu suspenso opções.</span><span class="sxs-lookup"><span data-stu-id="e1ff6-155">To fully enable network protection, you must set the Group Policy option to **Enabled** and also select **Block** in the options drop-down menu.</span></span>

<span data-ttu-id="e1ff6-156">Confirme se a proteção de rede está habilitada em um computador local usando o editor do Registro:</span><span class="sxs-lookup"><span data-stu-id="e1ff6-156">Confirm network protection is enabled on a local computer by using Registry editor:</span></span>

1. <span data-ttu-id="e1ff6-157">Selecione **Iniciar** e digite **regedit** para abrir **o Editor do Registro.**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-157">Select **Start** and type **regedit** to open **Registry Editor**.</span></span>

2. <span data-ttu-id="e1ff6-158">Navegue até **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span><span class="sxs-lookup"><span data-stu-id="e1ff6-158">Navigate to **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection**</span></span>

3. <span data-ttu-id="e1ff6-159">Selecione **EnableNetworkProtection** e confirme o valor:</span><span class="sxs-lookup"><span data-stu-id="e1ff6-159">Select **EnableNetworkProtection** and confirm the value:</span></span>
   * <span data-ttu-id="e1ff6-160">0=Off</span><span class="sxs-lookup"><span data-stu-id="e1ff6-160">0=Off</span></span>
   * <span data-ttu-id="e1ff6-161">1=On</span><span class="sxs-lookup"><span data-stu-id="e1ff6-161">1=On</span></span>
   * <span data-ttu-id="e1ff6-162">2=Auditoria</span><span class="sxs-lookup"><span data-stu-id="e1ff6-162">2=Audit</span></span>

## <a name="see-also"></a><span data-ttu-id="e1ff6-163">Confira também</span><span class="sxs-lookup"><span data-stu-id="e1ff6-163">See also</span></span>

* [<span data-ttu-id="e1ff6-164">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="e1ff6-164">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="e1ff6-165">Avaliar a proteção de rede</span><span class="sxs-lookup"><span data-stu-id="e1ff6-165">Evaluate network protection</span></span>](evaluate-network-protection.md)
* [<span data-ttu-id="e1ff6-166">Solucionar problemas de proteção de rede</span><span class="sxs-lookup"><span data-stu-id="e1ff6-166">Troubleshoot network protection</span></span>](troubleshoot-np.md)
