---
title: Microsoft Defender Antivírus no aplicativo Segurança do Windows aplicativo
description: Com Microsoft Defender Antivírus agora incluído no aplicativo Segurança do Windows, você pode revisar, comparar e executar tarefas comuns.
keywords: wdav, antivírus, firewall, segurança, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ccb0d4cf168bbb4d3c1575c1e6611829909d0817
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275403"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="7ddd7-104">Microsoft Defender Antivírus no aplicativo Segurança do Windows aplicativo</span><span class="sxs-lookup"><span data-stu-id="7ddd7-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7ddd7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7ddd7-105">**Applies to:**</span></span>

- [<span data-ttu-id="7ddd7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7ddd7-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7ddd7-107">No Windows 10, versão 1703 e posterior, o aplicativo Windows Defender faz parte do Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="7ddd7-108">Configurações que antes eram parte do cliente Windows Defender e do Windows Configurações principal foram combinados e movidos para o novo aplicativo, que é instalado por padrão como parte do Windows 10, versão 1703.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ddd7-109">Desabilitar o serviço Segurança do Windows Central não desabilita Microsoft Defender Antivírus ou [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="7ddd7-110">Eles são desabilitados automaticamente quando um produto antivírus ou firewall de terceiros é instalado e mantido atualizado.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="7ddd7-111">Se você desabilitar o serviço central do Segurança do Windows ou configurar suas configurações de Política de Grupo associadas para impedir que ele seja acionada ou em execução, o aplicativo Segurança do Windows poderá exibir informações desproportivas ou imprecisas sobre quaisquer produtos antivírus ou firewall que você instalou no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="7ddd7-112">Também pode impedir Microsoft Defender Antivírus se você tiver um antivírus de terceiros antigo ou desatualizado ou se você desinstalar qualquer produto antivírus de terceiros que você possa ter instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="7ddd7-113">Isso diminuirá significativamente a proteção do dispositivo e poderá levar a infecção por malware.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="7ddd7-114">Consulte o [Segurança do Windows para](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) obter mais informações sobre outros Windows de segurança que podem ser monitorados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="7ddd7-115">O Segurança do Windows app é uma interface do cliente Windows 10, versão 1703 e posterior.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="7ddd7-116">Não é o portal Central de Segurança do Microsoft Defender web usado para analisar e gerenciar o [Microsoft Defender para o Ponto de Extremidade.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="7ddd7-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="7ddd7-117">Revisar configurações de proteção contra vírus e ameaças no Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="7ddd7-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Captura de tela do rótulo de configurações de proteção contra & vírus no Segurança do Windows app](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="7ddd7-119">Abra o Segurança do Windows aplicativo clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="7ddd7-120">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="7ddd7-121">As seções a seguir descrevem como executar algumas das tarefas mais comuns ao revisar ou interagir com a proteção contra ameaças fornecida pelo Microsoft Defender Antivírus no aplicativo Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="7ddd7-122">Se essas configurações são configuradas e implantadas usando a Política de Grupo, as configurações descritas nesta seção serão acinzenadas e indisponíveis para uso em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="7ddd7-123">As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada Windows Configurações.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="7ddd7-124">O [tópico Configurar interação do usuário](configure-end-user-interaction-microsoft-defender-antivirus.md) final com Microsoft Defender Antivírus descreve como as configurações de substituição de política local podem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="7ddd7-125">Executar uma verificação com o Segurança do Windows aplicativo</span><span class="sxs-lookup"><span data-stu-id="7ddd7-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="7ddd7-126">Abra o Segurança do Windows aplicativo pesquisando o menu iniciar para **Segurança** e selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7ddd7-127">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7ddd7-128">Selecione **Verificação rápida**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-128">Select **Quick scan**.</span></span> <span data-ttu-id="7ddd7-129">Ou, para executar uma verificação completa, selecione **Opções de** verificação e selecione uma opção, como **Verificação completa**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="7ddd7-130">Revise a versão de atualização de inteligência de segurança e baixe as atualizações mais recentes no Segurança do Windows app</span><span class="sxs-lookup"><span data-stu-id="7ddd7-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Informações sobre o número da versão de inteligência de segurança](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="7ddd7-132">Abra o Segurança do Windows aplicativo pesquisando o menu iniciar para *Segurança* e selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7ddd7-133">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7ddd7-134">Selecione **Atualizações & proteção contra ameaças de vírus.**</span><span class="sxs-lookup"><span data-stu-id="7ddd7-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="7ddd7-135">A versão instalada no momento é exibida juntamente com algumas informações sobre quando ela foi baixada.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="7ddd7-136">Você pode verificar o seu atual em relação à versão mais recente disponível para download manual ou revisar o log de alterações para essa versão.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="7ddd7-137">Consulte [Atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="7ddd7-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="7ddd7-138">Selecione **Verificar se há atualizações para** baixar novas atualizações de proteção (se houver alguma).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="7ddd7-139">Verifique se Microsoft Defender Antivírus está habilitado no aplicativo Segurança do Windows aplicativo</span><span class="sxs-lookup"><span data-stu-id="7ddd7-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="7ddd7-140">Abra o Segurança do Windows aplicativo pesquisando o menu iniciar para *Segurança* e selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7ddd7-141">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7ddd7-142">Selecione **Configurações & proteção contra ameaças.**</span><span class="sxs-lookup"><span data-stu-id="7ddd7-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="7ddd7-143">Alterne a **opção de proteção em** tempo real para **On**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7ddd7-144">Se você desativar **a proteção em tempo real,** ela retornará automaticamente após um curto atraso.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="7ddd7-145">Isso é para garantir que você está protegido contra malware e ameaças.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="7ddd7-146">Se você instalar outro produto antivírus, Microsoft Defender Antivírus se desabilitará automaticamente e será indicado como tal no Segurança do Windows app.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="7ddd7-147">Aparecerá uma configuração que permitirá que você habilita a [verificação periódica limitada.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="7ddd7-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="7ddd7-148">Adicionar exclusões para Microsoft Defender Antivírus no aplicativo Segurança do Windows aplicativo</span><span class="sxs-lookup"><span data-stu-id="7ddd7-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="7ddd7-149">Abra o Segurança do Windows aplicativo pesquisando o menu iniciar para *Segurança* e selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7ddd7-150">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7ddd7-151">Em Gerenciar **configurações,** selecione **Configurações & proteção** contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="7ddd7-152">Na **configuração Exclusões,** selecione **Adicionar ou remover exclusões**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="7ddd7-153">Selecione o ícone de a mais ( **+** ) para escolher o tipo e definir as opções para cada exclusão.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="7ddd7-154">A tabela a seguir resume os tipos de exclusão e o que acontece:</span><span class="sxs-lookup"><span data-stu-id="7ddd7-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="7ddd7-155">Tipo de exclusão</span><span class="sxs-lookup"><span data-stu-id="7ddd7-155">Exclusion type</span></span>  |<span data-ttu-id="7ddd7-156">Definido por</span><span class="sxs-lookup"><span data-stu-id="7ddd7-156">Defined by</span></span>  |<span data-ttu-id="7ddd7-157">O que acontece</span><span class="sxs-lookup"><span data-stu-id="7ddd7-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7ddd7-158">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="7ddd7-158">**File**</span></span> |<span data-ttu-id="7ddd7-159">Location</span><span class="sxs-lookup"><span data-stu-id="7ddd7-159">Location</span></span> <br/><span data-ttu-id="7ddd7-160">Exemplo: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="7ddd7-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="7ddd7-161">O arquivo específico é ignorado por Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="7ddd7-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="7ddd7-162">**Folder**</span></span>    |<span data-ttu-id="7ddd7-163">Location</span><span class="sxs-lookup"><span data-stu-id="7ddd7-163">Location</span></span> <br/><span data-ttu-id="7ddd7-164">Exemplo: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="7ddd7-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="7ddd7-165">Todos os itens na pasta especificada são ignorados por Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="7ddd7-166">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="7ddd7-166">**File type**</span></span>   |<span data-ttu-id="7ddd7-167">Extensão de arquivo</span><span class="sxs-lookup"><span data-stu-id="7ddd7-167">File extension</span></span> <br/><span data-ttu-id="7ddd7-168">Exemplo: `.test`</span><span class="sxs-lookup"><span data-stu-id="7ddd7-168">Example: `.test`</span></span> |<span data-ttu-id="7ddd7-169">Todos os arquivos com a extensão em qualquer lugar do `.test` dispositivo são ignorados por Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="7ddd7-170">**Processo**</span><span class="sxs-lookup"><span data-stu-id="7ddd7-170">**Process**</span></span>     |<span data-ttu-id="7ddd7-171">Caminho do arquivo executável</span><span class="sxs-lookup"><span data-stu-id="7ddd7-171">Executable file path</span></span> <br><span data-ttu-id="7ddd7-172">Exemplo: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="7ddd7-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="7ddd7-173">O processo específico e todos os arquivos abertos por esse processo são ignorados por Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="7ddd7-174">Para saber mais, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="7ddd7-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="7ddd7-175">Configurar e validar exclusões com base na extensão de arquivo e no local da pasta</span><span class="sxs-lookup"><span data-stu-id="7ddd7-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="7ddd7-176">Configurar exclusões para arquivos abertos por processos</span><span class="sxs-lookup"><span data-stu-id="7ddd7-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="7ddd7-177">Revisar o histórico de detecção de ameaças no aplicativo Windows Defender Centro de Segurança</span><span class="sxs-lookup"><span data-stu-id="7ddd7-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="7ddd7-178">Abra o Segurança do Windows aplicativo pesquisando o menu iniciar para *Segurança* e selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7ddd7-179">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7ddd7-180">Selecione **Histórico de proteção**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-180">Select **Protection history**.</span></span> <span data-ttu-id="7ddd7-181">Todos os itens recentes estão listados.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="7ddd7-182">Definir opções de proteção e recuperação de ransomware</span><span class="sxs-lookup"><span data-stu-id="7ddd7-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="7ddd7-183">Abra o Segurança do Windows aplicativo pesquisando o menu iniciar para *Segurança* e selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="7ddd7-184">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="7ddd7-185">Em **Proteção contra ransomware,** selecione **Gerenciar proteção de ransomware**.</span><span class="sxs-lookup"><span data-stu-id="7ddd7-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="7ddd7-186">Para alterar **as configurações de** acesso controlado a pastas, consulte [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span><span class="sxs-lookup"><span data-stu-id="7ddd7-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="7ddd7-187">Para configurar opções de recuperação de ransomware, selecione Configurar em Recuperação de dados do Ransomware e siga as instruções para vincular ou configurar sua conta OneDrive para que você possa se recuperar facilmente de um ataque de **ransomware.** </span><span class="sxs-lookup"><span data-stu-id="7ddd7-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ddd7-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ddd7-188">See also</span></span>
- [<span data-ttu-id="7ddd7-189">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="7ddd7-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)