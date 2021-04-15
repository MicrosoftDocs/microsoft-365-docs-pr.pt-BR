---
title: Microsoft Defender Antivírus no aplicativo segurança do Windows
description: Com o Microsoft Defender Antivírus agora incluído no aplicativo segurança do Windows, você pode revisar, comparar e executar tarefas comuns.
keywords: wdav, antivírus, firewall, segurança, windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7635209c03dfc0367df16bfb650a4e52d2b2b3f8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765318"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="4f31f-104">Microsoft Defender Antivírus no aplicativo segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="4f31f-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4f31f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4f31f-105">**Applies to:**</span></span>

- [<span data-ttu-id="4f31f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4f31f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="4f31f-107">No Windows 10, versão 1703 e posterior, o aplicativo Windows Defender faz parte da Segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="4f31f-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="4f31f-108">As configurações que antes eram parte do cliente Windows Defender e das configurações principais do Windows foram combinadas e movidas para o novo aplicativo, que é instalado por padrão como parte do Windows 10, versão 1703.</span><span class="sxs-lookup"><span data-stu-id="4f31f-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f31f-109">Desabilitar o serviço da Central de Segurança do Windows não desabilita o Microsoft Defender Antivírus [ou Windows Defender Firewall.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="4f31f-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="4f31f-110">Eles são desabilitados automaticamente quando um produto antivírus ou firewall de terceiros é instalado e mantido atualizado.</span><span class="sxs-lookup"><span data-stu-id="4f31f-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="4f31f-111">Se você desabilitar o serviço da Central de Segurança do Windows ou configurar suas configurações de Política de Grupo associadas para impedir que ele seja acionada ou em execução, o aplicativo de Segurança do Windows poderá exibir informações desproportivas ou imprecisas sobre qualquer antivírus ou produtos de firewall que você instalou no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f31f-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="4f31f-112">Ele também pode impedir que o Microsoft Defender Antivírus se habilita se você tiver um antivírus de terceiros antigo ou desatualizado ou se você desinstalar qualquer produto antivírus de terceiros que você possa ter instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4f31f-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="4f31f-113">Isso diminuirá significativamente a proteção do dispositivo e poderá levar a infecção por malware.</span><span class="sxs-lookup"><span data-stu-id="4f31f-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="4f31f-114">Consulte o [artigo segurança do Windows](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) para obter mais informações sobre outros recursos de segurança do Windows que podem ser monitorados no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4f31f-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="4f31f-115">O aplicativo segurança do Windows é uma interface do cliente no Windows 10, versão 1703 e posterior.</span><span class="sxs-lookup"><span data-stu-id="4f31f-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="4f31f-116">Não é o portal da Central de Segurança do Microsoft Defender que é usado para revisar e gerenciar [o Microsoft Defender para o Ponto de Extremidade.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="4f31f-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="4f31f-117">Revisar configurações de proteção contra vírus e ameaças no aplicativo segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="4f31f-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Captura de tela do rótulo de configurações de proteção contra & vírus no aplicativo segurança do Windows](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="4f31f-119">Abra o aplicativo segurança do Windows clicando no ícone de escudo na barra de tarefas ou pesquisando o menu inicial do **Defender**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="4f31f-120">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="4f31f-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="4f31f-121">As seções a seguir descrevem como executar algumas das tarefas mais comuns ao revisar ou interagir com a proteção contra ameaças fornecida pelo Microsoft Defender Antivírus no aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="4f31f-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="4f31f-122">Se essas configurações são configuradas e implantadas usando a Política de Grupo, as configurações descritas nesta seção serão acinzenadas e indisponíveis para uso em pontos de extremidade individuais.</span><span class="sxs-lookup"><span data-stu-id="4f31f-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="4f31f-123">As alterações feitas por meio de um Objeto de Política de Grupo devem primeiro ser implantadas em pontos de extremidade individuais antes que a configuração seja atualizada nas Configurações do Windows.</span><span class="sxs-lookup"><span data-stu-id="4f31f-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="4f31f-124">O [tópico Configurar interação do usuário final com o Microsoft Defender Antivírus](configure-end-user-interaction-microsoft-defender-antivirus.md) descreve como as configurações de substituição de política local podem ser configuradas.</span><span class="sxs-lookup"><span data-stu-id="4f31f-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="4f31f-125">Executar uma verificação com o aplicativo segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="4f31f-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="4f31f-126">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para **Segurança** e, em seguida, selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="4f31f-127">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="4f31f-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="4f31f-128">Selecione **Verificação rápida**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-128">Select **Quick scan**.</span></span> <span data-ttu-id="4f31f-129">Ou, para executar uma verificação completa, selecione **Opções de** verificação e selecione uma opção, como **Verificação completa**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="4f31f-130">Revise a versão de atualização de inteligência de segurança e baixe as atualizações mais recentes no aplicativo segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="4f31f-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![Informações sobre o número da versão de inteligência de segurança](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="4f31f-132">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="4f31f-133">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="4f31f-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="4f31f-134">Selecione **Atualizações & proteção contra ameaças de vírus.**</span><span class="sxs-lookup"><span data-stu-id="4f31f-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="4f31f-135">A versão instalada no momento é exibida juntamente com algumas informações sobre quando ela foi baixada.</span><span class="sxs-lookup"><span data-stu-id="4f31f-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="4f31f-136">Você pode verificar o seu atual em relação à versão mais recente disponível para download manual ou revisar o log de alterações para essa versão.</span><span class="sxs-lookup"><span data-stu-id="4f31f-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="4f31f-137">Consulte [Atualizações de inteligência de segurança para o Microsoft Defender Antivírus e outros antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4f31f-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="4f31f-138">Selecione **Verificar se há atualizações para** baixar novas atualizações de proteção (se houver alguma).</span><span class="sxs-lookup"><span data-stu-id="4f31f-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="4f31f-139">Verifique se o Microsoft Defender Antivírus está habilitado no aplicativo segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="4f31f-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="4f31f-140">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="4f31f-141">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="4f31f-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="4f31f-142">Selecione **Configurações & proteção contra ameaças.**</span><span class="sxs-lookup"><span data-stu-id="4f31f-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="4f31f-143">Alterne a **opção de proteção em** tempo real para **On**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4f31f-144">Se você desativar **a proteção em tempo real,** ela retornará automaticamente após um curto atraso.</span><span class="sxs-lookup"><span data-stu-id="4f31f-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="4f31f-145">Isso é para garantir que você está protegido contra malware e ameaças.</span><span class="sxs-lookup"><span data-stu-id="4f31f-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="4f31f-146">Se você instalar outro produto antivírus, o Microsoft Defender Antivírus se desabilitará automaticamente e será indicado como tal no aplicativo segurança do Windows.</span><span class="sxs-lookup"><span data-stu-id="4f31f-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="4f31f-147">Aparecerá uma configuração que permitirá que você habilita a [verificação periódica limitada.](limited-periodic-scanning-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4f31f-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="4f31f-148">Adicionar exclusões para o Microsoft Defender Antivírus no aplicativo segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="4f31f-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="4f31f-149">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="4f31f-150">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="4f31f-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="4f31f-151">Em Gerenciar **configurações,** selecione **Configurações & proteção** contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="4f31f-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="4f31f-152">Na **configuração Exclusões,** selecione **Adicionar ou remover exclusões**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="4f31f-153">Selecione o ícone de a mais ( **+** ) para escolher o tipo e definir as opções para cada exclusão.</span><span class="sxs-lookup"><span data-stu-id="4f31f-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="4f31f-154">A tabela a seguir resume os tipos de exclusão e o que acontece:</span><span class="sxs-lookup"><span data-stu-id="4f31f-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="4f31f-155">Tipo de exclusão</span><span class="sxs-lookup"><span data-stu-id="4f31f-155">Exclusion type</span></span>  |<span data-ttu-id="4f31f-156">Definido por</span><span class="sxs-lookup"><span data-stu-id="4f31f-156">Defined by</span></span>  |<span data-ttu-id="4f31f-157">O que acontece</span><span class="sxs-lookup"><span data-stu-id="4f31f-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="4f31f-158">**Arquivo**</span><span class="sxs-lookup"><span data-stu-id="4f31f-158">**File**</span></span> |<span data-ttu-id="4f31f-159">Local</span><span class="sxs-lookup"><span data-stu-id="4f31f-159">Location</span></span> <br/><span data-ttu-id="4f31f-160">Exemplo: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="4f31f-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="4f31f-161">O arquivo específico é ignorado pelo Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="4f31f-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="4f31f-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="4f31f-162">**Folder**</span></span>    |<span data-ttu-id="4f31f-163">Local</span><span class="sxs-lookup"><span data-stu-id="4f31f-163">Location</span></span> <br/><span data-ttu-id="4f31f-164">Exemplo: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="4f31f-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="4f31f-165">Todos os itens na pasta especificada são ignorados pelo Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="4f31f-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="4f31f-166">**Tipo de arquivo**</span><span class="sxs-lookup"><span data-stu-id="4f31f-166">**File type**</span></span>   |<span data-ttu-id="4f31f-167">Extensão de arquivo</span><span class="sxs-lookup"><span data-stu-id="4f31f-167">File extension</span></span> <br/><span data-ttu-id="4f31f-168">Exemplo: `.test`</span><span class="sxs-lookup"><span data-stu-id="4f31f-168">Example: `.test`</span></span> |<span data-ttu-id="4f31f-169">Todos os arquivos com `.test` a extensão em qualquer lugar do dispositivo são ignorados pelo Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="4f31f-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="4f31f-170">**Processo**</span><span class="sxs-lookup"><span data-stu-id="4f31f-170">**Process**</span></span>     |<span data-ttu-id="4f31f-171">Caminho do arquivo executável</span><span class="sxs-lookup"><span data-stu-id="4f31f-171">Executable file path</span></span> <br><span data-ttu-id="4f31f-172">Exemplo: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="4f31f-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="4f31f-173">O processo específico e todos os arquivos abertos por esse processo são ignorados pelo Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="4f31f-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="4f31f-174">Para saber mais, confira os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="4f31f-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="4f31f-175">Configurar e validar exclusões com base na extensão de arquivo e no local da pasta</span><span class="sxs-lookup"><span data-stu-id="4f31f-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="4f31f-176">Configurar exclusões para arquivos abertos por processos</span><span class="sxs-lookup"><span data-stu-id="4f31f-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="4f31f-177">Revisar o histórico de detecção de ameaças no aplicativo Windows Defender Centro de Segurança</span><span class="sxs-lookup"><span data-stu-id="4f31f-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="4f31f-178">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="4f31f-179">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="4f31f-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="4f31f-180">Selecione **Histórico de proteção**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-180">Select **Protection history**.</span></span> <span data-ttu-id="4f31f-181">Todos os itens recentes estão listados.</span><span class="sxs-lookup"><span data-stu-id="4f31f-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="4f31f-182">Definir opções de proteção e recuperação de ransomware</span><span class="sxs-lookup"><span data-stu-id="4f31f-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="4f31f-183">Abra o aplicativo segurança do Windows pesquisando o menu iniciar para *Segurança* e, em seguida, selecionando **Segurança do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="4f31f-184">Selecione o & de **proteção** contra ameaças (ou o ícone de escudo na barra de menus esquerda).</span><span class="sxs-lookup"><span data-stu-id="4f31f-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="4f31f-185">Em **Proteção contra ransomware,** selecione **Gerenciar proteção de ransomware**.</span><span class="sxs-lookup"><span data-stu-id="4f31f-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="4f31f-186">Para alterar **as configurações de** acesso controlado a pastas, consulte [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span><span class="sxs-lookup"><span data-stu-id="4f31f-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="4f31f-187">Para configurar opções de recuperação de ransomware, selecione Configurar em Recuperação de dados do Ransomware e siga as instruções para vincular ou configurar sua conta do OneDrive para que você possa se recuperar facilmente de um ataque de **ransomware.** </span><span class="sxs-lookup"><span data-stu-id="4f31f-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f31f-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="4f31f-188">See also</span></span>
- [<span data-ttu-id="4f31f-189">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="4f31f-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)