---
title: Habilitar regras da redução da superfície de ataque
description: Habilita as regras de redução de superfície de ataque (ASR) para proteger seus dispositivos contra ataques que usam macros, scripts e técnicas de injeção comuns.
keywords: Redução de superfície de ataque, quadris, sistema de prevenção contra intrusões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, habilitar, ativar
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
ms.openlocfilehash: 84947057abbd456dee5cbf5d0c6fea37f679d9ad
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570943"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="90113-104">Habilitar regras da redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="90113-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="90113-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="90113-105">**Applies to:**</span></span>
- [<span data-ttu-id="90113-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="90113-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="90113-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90113-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="90113-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="90113-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="90113-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="90113-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="90113-110">[As regras de redução de](attack-surface-reduction.md) superfície de ataque (regras ASR) ajudam a evitar ações que o malware geralmente abusa para comprometer dispositivos e redes.</span><span class="sxs-lookup"><span data-stu-id="90113-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="90113-111">Você pode definir regras ASR para dispositivos que executam qualquer uma das seguintes edições e versões do Windows:</span><span class="sxs-lookup"><span data-stu-id="90113-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="90113-112">Windows 10 Pro, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior</span><span class="sxs-lookup"><span data-stu-id="90113-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="90113-113">Windows 10 Enterprise, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior</span><span class="sxs-lookup"><span data-stu-id="90113-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="90113-114">Windows Server, [versão 1803 (Canal Semesanuais)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior</span><span class="sxs-lookup"><span data-stu-id="90113-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="90113-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="90113-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="90113-116">Cada regra ASR contém uma das três configurações:</span><span class="sxs-lookup"><span data-stu-id="90113-116">Each ASR rule contains one of three settings:</span></span>

- <span data-ttu-id="90113-117">Não configurado: desabilitar a regra ASR</span><span class="sxs-lookup"><span data-stu-id="90113-117">Not configured: Disable the ASR rule</span></span>
- <span data-ttu-id="90113-118">Bloquear: Habilitar a regra ASR</span><span class="sxs-lookup"><span data-stu-id="90113-118">Block: Enable the ASR rule</span></span>
- <span data-ttu-id="90113-119">Auditoria: Avalie como a regra ASR afetaria sua organização se habilitada</span><span class="sxs-lookup"><span data-stu-id="90113-119">Audit: Evaluate how the ASR rule would impact your organization if enabled</span></span>

<span data-ttu-id="90113-120">É altamente recomendável que você use regras ASR com uma licença do Windows E5 (ou SKU de licenciamento semelhante) para aproveitar os recursos avançados de monitoramento e relatório disponíveis no [Microsoft Defender para Ponto](https://docs.microsoft.com/windows/security/threat-protection) de Extremidade (Defender para Ponto de Extremidade).</span><span class="sxs-lookup"><span data-stu-id="90113-120">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="90113-121">No entanto, para outras licenças, como o Windows Professional ou o E3 que não têm acesso aos recursos avançados de monitoramento e relatórios, você pode desenvolver suas próprias ferramentas de monitoramento e relatório em cima dos eventos gerados em cada ponto de extremidade quando as regras ASR são acionadas (por exemplo, Encaminhamento de Eventos).</span><span class="sxs-lookup"><span data-stu-id="90113-121">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="90113-122">Para saber mais sobre o licenciamento do Windows, consulte [Licenciamento do Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e obter o guia de Licenciamento por [Volume do Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span><span class="sxs-lookup"><span data-stu-id="90113-122">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="90113-123">Você pode habilitar regras de redução de superfície de ataque usando qualquer um desses métodos:</span><span class="sxs-lookup"><span data-stu-id="90113-123">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="90113-124">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="90113-124">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="90113-125">Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="90113-125">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="90113-126">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="90113-126">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="90113-127">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="90113-127">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="90113-128">PowerShell</span><span class="sxs-lookup"><span data-stu-id="90113-128">PowerShell</span></span>](#powershell)

<span data-ttu-id="90113-129">É recomendável o gerenciamento no nível empresarial, como o Intune ou o Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="90113-129">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="90113-130">O gerenciamento no nível empresarial substituirá qualquer política de grupo conflitante ou configurações do PowerShell na inicialização.</span><span class="sxs-lookup"><span data-stu-id="90113-130">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="90113-131">Excluir arquivos e pastas de regras ASR</span><span class="sxs-lookup"><span data-stu-id="90113-131">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="90113-132">Você pode excluir arquivos e pastas de serem avaliados pela maioria das regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="90113-132">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="90113-133">Isso significa que, mesmo que uma regra ASR determine que o arquivo ou pasta contém comportamento mal-intencionado, ele não impedirá a execução do arquivo.</span><span class="sxs-lookup"><span data-stu-id="90113-133">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="90113-134">Isso pode permitir que arquivos não seguros executem e infectem seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="90113-134">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="90113-135">Você também pode excluir as regras ASR de disparar com base em hashes de certificado e arquivo, permitindo indicadores de certificado e de arquivo do Defender para Ponto de Extremidade especificados.</span><span class="sxs-lookup"><span data-stu-id="90113-135">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="90113-136">(Consulte [Gerenciar indicadores](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span><span class="sxs-lookup"><span data-stu-id="90113-136">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90113-137">A exclusão de arquivos ou pastas pode reduzir gravemente a proteção fornecida pelas regras ASR.</span><span class="sxs-lookup"><span data-stu-id="90113-137">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="90113-138">Arquivos excluídos terão permissão para serem executados e nenhum relatório ou evento será gravado.</span><span class="sxs-lookup"><span data-stu-id="90113-138">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="90113-139">Se as regras ASR estão detectando arquivos que você acredita que não devem ser detectados, você deve usar o modo de auditoria [primeiro para testar a regra](evaluate-attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="90113-139">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="90113-140">Você pode especificar arquivos ou pastas individuais (usando caminhos de pasta ou nomes de recursos totalmente qualificados), mas não pode especificar a quais regras as exclusões se aplicam.</span><span class="sxs-lookup"><span data-stu-id="90113-140">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="90113-141">Uma exclusão é aplicada somente quando o aplicativo ou serviço excluído é iniciado.</span><span class="sxs-lookup"><span data-stu-id="90113-141">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="90113-142">Por exemplo, se você adicionar uma exclusão para um serviço de atualização que já está em execução, o serviço de atualização continuará disparando eventos até que o serviço seja interrompido e reiniciado.</span><span class="sxs-lookup"><span data-stu-id="90113-142">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="90113-143">As regras ASR suportam variáveis de ambiente e caracteres curinga.</span><span class="sxs-lookup"><span data-stu-id="90113-143">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="90113-144">Para obter informações sobre como usar caracteres curinga, consulte Use curingas no nome do arquivo e no caminho da pasta ou listas de [exclusão de extensão.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="90113-144">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="90113-145">Os procedimentos a seguir para habilenciar regras ASR incluem instruções sobre como excluir arquivos e pastas.</span><span class="sxs-lookup"><span data-stu-id="90113-145">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="90113-146">Intune</span><span class="sxs-lookup"><span data-stu-id="90113-146">Intune</span></span>

1. <span data-ttu-id="90113-147">Selecione **Perfis de**  >  **configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="90113-147">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="90113-148">Escolha um perfil de proteção de ponto de extremidade existente ou crie um novo.</span><span class="sxs-lookup"><span data-stu-id="90113-148">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="90113-149">Para criar um novo, selecione **Criar perfil e** insira informações para esse perfil.</span><span class="sxs-lookup"><span data-stu-id="90113-149">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="90113-150">Para **o tipo de** perfil, selecione Proteção de ponto de **extremidade**.</span><span class="sxs-lookup"><span data-stu-id="90113-150">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="90113-151">Se você tiver escolhido um perfil existente, selecione **Propriedades** e, em seguida, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="90113-151">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="90113-152">No painel **proteção de ponto de** extremidade, selecione Windows Defender Exploit **Guard,** em seguida, **selecione Redução de Superfície de Ataque**.</span><span class="sxs-lookup"><span data-stu-id="90113-152">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="90113-153">Selecione a configuração desejada para cada regra ASR.</span><span class="sxs-lookup"><span data-stu-id="90113-153">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="90113-154">Em **Exceções de Redução de Superfície de Ataque,** insira arquivos e pastas individuais.</span><span class="sxs-lookup"><span data-stu-id="90113-154">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="90113-155">Você também pode selecionar **Importar para** importar um arquivo CSV que contém arquivos e pastas a ser excluído das regras ASR.</span><span class="sxs-lookup"><span data-stu-id="90113-155">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="90113-156">Cada linha no arquivo CSV deve ser formatada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="90113-156">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="90113-157">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="90113-157">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="90113-158">Selecione **OK** nos três painéis de configuração.</span><span class="sxs-lookup"><span data-stu-id="90113-158">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="90113-159">Em **seguida, selecione** Criar se você estiver criando um novo arquivo de proteção de ponto de extremidade ou **Salvar** se estiver editando um existente.</span><span class="sxs-lookup"><span data-stu-id="90113-159">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="90113-160">MDM</span><span class="sxs-lookup"><span data-stu-id="90113-160">MDM</span></span>

<span data-ttu-id="90113-161">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) para habilitar e definir individualmente o modo para cada regra.</span><span class="sxs-lookup"><span data-stu-id="90113-161">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="90113-162">A seguir, um exemplo de referência, usando [valores GUID para regras ASR](attack-surface-reduction.md#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="90113-162">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="90113-163">Os valores para habilitar, desabilitar ou habilitar no modo de auditoria são:</span><span class="sxs-lookup"><span data-stu-id="90113-163">The values to enable, disable, or enable in audit mode are:</span></span>

- <span data-ttu-id="90113-164">Desabilitar = 0</span><span class="sxs-lookup"><span data-stu-id="90113-164">Disable = 0</span></span>
- <span data-ttu-id="90113-165">Bloquear (habilitar regra ASR) = 1</span><span class="sxs-lookup"><span data-stu-id="90113-165">Block (enable ASR rule) = 1</span></span>
- <span data-ttu-id="90113-166">Auditoria = 2</span><span class="sxs-lookup"><span data-stu-id="90113-166">Audit = 2</span></span>

<span data-ttu-id="90113-167">Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) para adicionar exclusões.</span><span class="sxs-lookup"><span data-stu-id="90113-167">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="90113-168">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="90113-168">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="90113-169">Insira valores OMA-URI sem espaços.</span><span class="sxs-lookup"><span data-stu-id="90113-169">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="90113-170">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="90113-170">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="90113-171">No Microsoft Endpoint Configuration Manager, acesse **Assets and Compliance**  >  **Endpoint Protection** Windows Defender Exploit  >  **Guard.**</span><span class="sxs-lookup"><span data-stu-id="90113-171">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="90113-172">Selecione **Home**  >  **Create Exploit Guard Policy**.</span><span class="sxs-lookup"><span data-stu-id="90113-172">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="90113-173">Insira um nome e uma descrição, selecione **Redução de Superfície de Ataque** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="90113-173">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="90113-174">Escolha quais regras bloquearão ou auditarão ações e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="90113-174">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="90113-175">Revise as configurações e selecione **Próximo** para criar a política.</span><span class="sxs-lookup"><span data-stu-id="90113-175">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="90113-176">Depois que a política for criada, **Feche**.</span><span class="sxs-lookup"><span data-stu-id="90113-176">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="90113-177">Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="90113-177">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="90113-178">Se você gerenciar seus computadores e dispositivos com o Intune, o Configuration Manager ou outra plataforma de gerenciamento de nível empresarial, o software de gerenciamento substituirá quaisquer configurações conflitantes da Política de Grupo na inicialização.</span><span class="sxs-lookup"><span data-stu-id="90113-178">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="90113-179">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="90113-179">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="90113-180">No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e selecione Modelos **administrativos.**</span><span class="sxs-lookup"><span data-stu-id="90113-180">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="90113-181">Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender Antivírus**  >  **Redução** de superfície  >  **de ataque do** Microsoft Defender Exploit Guard .</span><span class="sxs-lookup"><span data-stu-id="90113-181">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="90113-182">Selecione **Configurar regras de redução de superfície de ataque** e selecione **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="90113-182">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="90113-183">Em seguida, você pode definir o estado individual para cada regra na seção opções.</span><span class="sxs-lookup"><span data-stu-id="90113-183">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="90113-184">Selecione **Mostrar...** e insira a ID da regra na coluna **Nome do** valor e seu estado escolhido na coluna **Valor** da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="90113-184">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="90113-185">Desabilitar = 0</span><span class="sxs-lookup"><span data-stu-id="90113-185">Disable = 0</span></span>
   - <span data-ttu-id="90113-186">Bloquear (habilitar regra ASR) = 1</span><span class="sxs-lookup"><span data-stu-id="90113-186">Block (enable ASR rule) = 1</span></span>
   - <span data-ttu-id="90113-187">Auditoria = 2</span><span class="sxs-lookup"><span data-stu-id="90113-187">Audit = 2</span></span>

   ![Configuração da política de grupo mostrando uma ID da regra de redução de superfície de ataque em branco e o valor de 1](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. <span data-ttu-id="90113-189">Para excluir arquivos e pastas de regras  ASR, selecione a configuração Excluir arquivos e caminhos de regras de redução de superfície de ataque e de definir a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="90113-189">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="90113-190">Selecione **Mostrar** e insira cada arquivo ou pasta na coluna **Nome do** valor.</span><span class="sxs-lookup"><span data-stu-id="90113-190">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="90113-191">Insira **0** na coluna **Valor** para cada item.</span><span class="sxs-lookup"><span data-stu-id="90113-191">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="90113-192">Não use aspas, pois elas não são suportadas para a coluna **Nome do** valor ou para a **coluna Valor.**</span><span class="sxs-lookup"><span data-stu-id="90113-192">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="90113-193">PowerShell</span><span class="sxs-lookup"><span data-stu-id="90113-193">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="90113-194">Se você gerenciar seus computadores e dispositivos com o Intune, o Configuration Manager ou outra plataforma de gerenciamento de nível empresarial, o software de gerenciamento substituirá as configurações conflitantes do PowerShell na inicialização.</span><span class="sxs-lookup"><span data-stu-id="90113-194">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="90113-195">Para permitir que os usuários definam o valor usando o PowerShell, use a opção "Definido pelo Usuário" para a regra na plataforma de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="90113-195">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="90113-196">Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**.</span><span class="sxs-lookup"><span data-stu-id="90113-196">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="90113-197">Insira o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90113-197">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="90113-198">Para habilitar regras ASR no modo de auditoria, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90113-198">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="90113-199">Para desativar as regras ASR, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90113-199">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="90113-200">Você deve especificar o estado individualmente para cada regra, mas pode combinar regras e estados em uma lista separada por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="90113-200">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="90113-201">No exemplo a seguir, as duas primeiras regras serão habilitadas, a terceira regra será desabilitada e a quarta regra será habilitada no modo de auditoria:</span><span class="sxs-lookup"><span data-stu-id="90113-201">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="90113-202">Você também pode usar o `Add-MpPreference` verbo PowerShell para adicionar novas regras à lista existente.</span><span class="sxs-lookup"><span data-stu-id="90113-202">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="90113-203">`Set-MpPreference` sempre substituirá o conjunto de regras existente.</span><span class="sxs-lookup"><span data-stu-id="90113-203">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="90113-204">Se você quiser adicionar ao conjunto existente, você deve usar `Add-MpPreference` em vez disso.</span><span class="sxs-lookup"><span data-stu-id="90113-204">If you want to add to the existing set, you should use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="90113-205">Você pode obter uma lista de regras e seu estado atual usando `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="90113-205">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="90113-206">Para excluir arquivos e pastas de regras ASR, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="90113-206">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="90113-207">Continue a usar `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` para adicionar mais arquivos e pastas à lista.</span><span class="sxs-lookup"><span data-stu-id="90113-207">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="90113-208">Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista.</span><span class="sxs-lookup"><span data-stu-id="90113-208">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="90113-209">O uso `Set-MpPreference` do cmdlet substituirá a lista existente.</span><span class="sxs-lookup"><span data-stu-id="90113-209">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="90113-210">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="90113-210">Related articles</span></span>

- [<span data-ttu-id="90113-211">Reduzir superfícies de ataque com regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="90113-211">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="90113-212">Avaliar a redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="90113-212">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="90113-213">Perguntas frequentes sobre a redução da superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="90113-213">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
