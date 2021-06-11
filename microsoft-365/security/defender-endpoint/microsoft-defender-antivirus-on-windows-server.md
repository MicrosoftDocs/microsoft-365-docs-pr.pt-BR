---
title: Microsoft Defender Antivírus no Windows Server
description: Saiba como habilitar e configurar Microsoft Defender Antivírus no Windows Server 2016 e Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, branch atual, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 05/13/2021
ms.openlocfilehash: 1a1083d15698eb5bbdf2f6080b152b6f326c689a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539270"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="eeda0-104">Microsoft Defender Antivírus no Windows Server</span><span class="sxs-lookup"><span data-stu-id="eeda0-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eeda0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="eeda0-105">**Applies to:**</span></span>

- [<span data-ttu-id="eeda0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="eeda0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="eeda0-107">Microsoft Defender Antivírus está disponível nas seguintes edições/versões do Windows Server:</span><span class="sxs-lookup"><span data-stu-id="eeda0-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="eeda0-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="eeda0-108">Windows Server 2019</span></span>
- <span data-ttu-id="eeda0-109">Windows Servidor, versão 1803 ou posterior</span><span class="sxs-lookup"><span data-stu-id="eeda0-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="eeda0-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="eeda0-110">Windows Server 2016.</span></span> 

<span data-ttu-id="eeda0-111">Em alguns casos, Microsoft Defender Antivírus é chamado de *Endpoint Protection;* no entanto, o mecanismo de proteção é o mesmo.</span><span class="sxs-lookup"><span data-stu-id="eeda0-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="eeda0-112">Embora a funcionalidade, a configuração e o gerenciamento sejam amplamente os mesmos para Microsoft Defender Antivírus no Windows 10 [,](microsoft-defender-antivirus-in-windows-10.md)há algumas diferenças importantes no Windows Server:</span><span class="sxs-lookup"><span data-stu-id="eeda0-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="eeda0-113">No Windows Server, [as exclusões automáticas](configure-server-exclusions-microsoft-defender-antivirus.md) são aplicadas com base na função de servidor definida.</span><span class="sxs-lookup"><span data-stu-id="eeda0-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="eeda0-114">No Windows Server, se você estiver executando uma solução de antivírus/antimalware que não seja da Microsoft, o Microsoft Defender Antivírus não entra no modo passivo ou desabilitado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eeda0-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="eeda0-115">No entanto, você pode definir Microsoft Defender Antivírus modo passivo ou desabilitado manualmente.</span><span class="sxs-lookup"><span data-stu-id="eeda0-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="eeda0-116">Configurando o Microsoft Defender Antivírus no Windows Server</span><span class="sxs-lookup"><span data-stu-id="eeda0-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="eeda0-117">O processo de configuração e execução de Microsoft Defender Antivírus em uma plataforma de servidor inclui várias etapas:</span><span class="sxs-lookup"><span data-stu-id="eeda0-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="eeda0-118">[Habilitar a interface](#enable-the-user-interface-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="eeda0-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="eeda0-119">[Instale Microsoft Defender Antivírus](#install-microsoft-defender-antivirus-on-windows-server).</span><span class="sxs-lookup"><span data-stu-id="eeda0-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="eeda0-120">[Verifique Microsoft Defender Antivírus está sendo executado](#verify-microsoft-defender-antivirus-is-running).</span><span class="sxs-lookup"><span data-stu-id="eeda0-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="eeda0-121">[Atualize sua inteligência de segurança antimalware.](#update-antimalware-security-intelligence)</span><span class="sxs-lookup"><span data-stu-id="eeda0-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="eeda0-122">(Conforme necessário) [Enviar amostras](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="eeda0-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="eeda0-123">(Conforme necessário) [Configurar exclusões automáticas](#configure-automatic-exclusions).</span><span class="sxs-lookup"><span data-stu-id="eeda0-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="eeda0-124">(Somente se necessário) [Definir Microsoft Defender Antivírus modo passivo](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span><span class="sxs-lookup"><span data-stu-id="eeda0-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="eeda0-125">Habilitar a interface do usuário no Windows Server</span><span class="sxs-lookup"><span data-stu-id="eeda0-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="eeda0-126">Por padrão, Microsoft Defender Antivírus é instalado e funcional no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="eeda0-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="eeda0-127">Às vezes, a interface do usuário (GUI) é instalada por padrão, mas a GUI não é necessária.</span><span class="sxs-lookup"><span data-stu-id="eeda0-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="eeda0-128">Você pode usar o PowerShell, a Política de Grupo ou outros métodos para gerenciar Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="eeda0-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="eeda0-129">Se a GUI não estiver instalada no servidor e você quiser instalá-la, o assistente **Adicionar Funções** e Recursos ou cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeda0-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="eeda0-130">Ativar a GUI usando o Assistente de Adicionar Funções e Recursos</span><span class="sxs-lookup"><span data-stu-id="eeda0-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="eeda0-131">Consulte [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the Add Roles and Features **Wizard**.</span><span class="sxs-lookup"><span data-stu-id="eeda0-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="eeda0-132">Quando você chegar à etapa **Recursos** do assistente, em Windows Defender **Recursos,** selecione a **opção GUI para** Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="eeda0-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="eeda0-133">No Windows Server 2016, o **Assistente de** Adicionar Funções e Recursos tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="eeda0-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Adicionar funções e assistente de recurso mostrando a gui para Windows Defender opção](images/server-add-gui.png)

   <span data-ttu-id="eeda0-135">No Windows Server 2019, **o Assistente para Adicionar Funções** e Recursos é semelhante.</span><span class="sxs-lookup"><span data-stu-id="eeda0-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="eeda0-136">Ativar a GUI usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="eeda0-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="eeda0-137">O seguinte cmdlet do PowerShell habilita a interface:</span><span class="sxs-lookup"><span data-stu-id="eeda0-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="eeda0-138">Instalar Microsoft Defender Antivírus no Windows Server</span><span class="sxs-lookup"><span data-stu-id="eeda0-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="eeda0-139">Se você precisar instalar ou reinstalar Microsoft Defender Antivírus no Windows Server, poderá fazer isso usando o Assistente para Adicionar Funções e Recursos **ou** o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eeda0-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="eeda0-140">Use o Assistente para Adicionar Funções e Recursos para instalar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="eeda0-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="eeda0-141">Consulte este [artigo](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)e use o **Assistente para Adicionar Funções e Recursos.**</span><span class="sxs-lookup"><span data-stu-id="eeda0-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="eeda0-142">Quando você chegar à etapa **Recursos** do assistente, selecione a opção Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="eeda0-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="eeda0-143">Selecione também a **opção GUI para Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="eeda0-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="eeda0-144">Use o PowerShell para instalar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="eeda0-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="eeda0-145">Para usar o PowerShell para instalar Microsoft Defender Antivírus, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="eeda0-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="eeda0-146">As mensagens de evento para o mecanismo de antimalware incluídas Microsoft Defender Antivírus podem ser encontradas em [Eventos av do Microsoft Defender.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="eeda0-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="eeda0-147">Verificar Microsoft Defender Antivírus está sendo executado</span><span class="sxs-lookup"><span data-stu-id="eeda0-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="eeda0-148">Depois Microsoft Defender Antivírus estiver instalado, a próxima etapa é verificar se ele está em execução.</span><span class="sxs-lookup"><span data-stu-id="eeda0-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="eeda0-149">No ponto de extremidade Windows Servidor do Windows, execute o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eeda0-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="eeda0-150">Para verificar se a proteção de firewall está ativado, execute o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eeda0-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="eeda0-151">Como alternativa ao PowerShell, você pode usar o Prompt de Comando para verificar se Microsoft Defender Antivírus está em execução.</span><span class="sxs-lookup"><span data-stu-id="eeda0-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="eeda0-152">Para fazer isso, execute o seguinte comando de um prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="eeda0-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="eeda0-153">O `sc query` comando retorna informações sobre o Microsoft Defender Antivírus serviço.</span><span class="sxs-lookup"><span data-stu-id="eeda0-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="eeda0-154">Quando Microsoft Defender Antivírus estiver em execução, `STATE` o valor será exibido `RUNNING` .</span><span class="sxs-lookup"><span data-stu-id="eeda0-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="eeda0-155">Atualizar inteligência de segurança antimalware</span><span class="sxs-lookup"><span data-stu-id="eeda0-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="eeda0-156">Para obter a inteligência de segurança antimalware atualizada, você deve ter o serviço Windows Update em execução.</span><span class="sxs-lookup"><span data-stu-id="eeda0-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="eeda0-157">Se você usar um serviço de gerenciamento de atualizações, como o Windows Server Update Services (WSUS), certifique-se de que as atualizações para o Microsoft Defender Antivírus de segurança sejam aprovadas para os computadores que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="eeda0-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="eeda0-158">Por padrão, Windows Update não baixa e instala atualizações automaticamente no Windows Server 2019 ou Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="eeda0-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="eeda0-159">Você pode alterar essa configuração usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="eeda0-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="eeda0-160">Método</span><span class="sxs-lookup"><span data-stu-id="eeda0-160">Method</span></span>  |<span data-ttu-id="eeda0-161">Descrição</span><span class="sxs-lookup"><span data-stu-id="eeda0-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="eeda0-162">**Windows Atualização** no Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="eeda0-162">**Windows Update** in Control Panel</span></span>     | <span data-ttu-id="eeda0-163">**Instalar atualizações resulta automaticamente** em todas as atualizações que estão sendo instaladas automaticamente, incluindo Windows Defender atualizações de inteligência de segurança.</span><span class="sxs-lookup"><span data-stu-id="eeda0-163">**Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <p><span data-ttu-id="eeda0-164">**Baixe atualizações,** mas deixe-me escolher se instalá-las permite Windows Defender baixar e instalar atualizações de inteligência de segurança automaticamente, mas outras atualizações não são instaladas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eeda0-164">**Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="eeda0-165">**Política de grupo**</span><span class="sxs-lookup"><span data-stu-id="eeda0-165">**Group Policy**</span></span>     | <span data-ttu-id="eeda0-166">Você pode configurar e gerenciar o Windows Update usando as configurações disponíveis na Política de Grupo, no seguinte caminho: Modelos **Administrativos\Windows Componentes\Windows Atualização\Configurar** Atualizações Automáticas</span><span class="sxs-lookup"><span data-stu-id="eeda0-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="eeda0-167">A **chave do Registro AUOptions**</span><span class="sxs-lookup"><span data-stu-id="eeda0-167">The **AUOptions** registry key</span></span>     | <span data-ttu-id="eeda0-168">Os dois valores a seguir permitem que Windows Atualização baixe e instale automaticamente atualizações de inteligência de segurança:</span><span class="sxs-lookup"><span data-stu-id="eeda0-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <p><span data-ttu-id="eeda0-169">**4**  -  **Instalar atualizações automaticamente**.</span><span class="sxs-lookup"><span data-stu-id="eeda0-169">**4** - **Install updates automatically**.</span></span> <span data-ttu-id="eeda0-170">Esse valor resulta em todas as atualizações sendo instaladas automaticamente, incluindo Windows Defender de inteligência de segurança.</span><span class="sxs-lookup"><span data-stu-id="eeda0-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <p><span data-ttu-id="eeda0-171">**3**  -  **Baixe atualizações, mas deixe-me escolher se deve instalá-las.**</span><span class="sxs-lookup"><span data-stu-id="eeda0-171">**3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="eeda0-172">Esse valor permite Windows Defender baixar e instalar atualizações de inteligência de segurança automaticamente, mas outras atualizações não são instaladas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="eeda0-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="eeda0-173">Para garantir que a proteção contra malware seja mantida, recomendamos que você habilita os seguintes serviços:</span><span class="sxs-lookup"><span data-stu-id="eeda0-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="eeda0-174">Relatório de Erros do Windows serviço</span><span class="sxs-lookup"><span data-stu-id="eeda0-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="eeda0-175">Windows Atualizar serviço</span><span class="sxs-lookup"><span data-stu-id="eeda0-175">Windows Update service</span></span>

<span data-ttu-id="eeda0-176">A tabela a seguir lista os serviços para Microsoft Defender Antivírus e os serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="eeda0-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="eeda0-177">Nome do Serviço</span><span class="sxs-lookup"><span data-stu-id="eeda0-177">Service Name</span></span>|<span data-ttu-id="eeda0-178">Local do arquivo</span><span class="sxs-lookup"><span data-stu-id="eeda0-178">File Location</span></span>|<span data-ttu-id="eeda0-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="eeda0-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="eeda0-180">Windows Defender Serviço (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="eeda0-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="eeda0-181">Esse é o serviço Microsoft Defender Antivírus principal que precisa estar em execução o tempo todo.</span><span class="sxs-lookup"><span data-stu-id="eeda0-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="eeda0-182">Relatório de Erros do Windows Serviço (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="eeda0-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="eeda0-183">Este serviço envia relatórios de erro de volta para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eeda0-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="eeda0-184">Windows Defender Firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="eeda0-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="eeda0-185">Recomendamos deixar o serviço Windows Defender Firewall habilitado.</span><span class="sxs-lookup"><span data-stu-id="eeda0-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="eeda0-186">Windows Atualização (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="eeda0-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="eeda0-187">Windows A atualização é necessária para obter atualizações de inteligência de segurança e atualizações do mecanismo antimalware</span><span class="sxs-lookup"><span data-stu-id="eeda0-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="eeda0-188">Enviar amostras</span><span class="sxs-lookup"><span data-stu-id="eeda0-188">Submit samples</span></span>

<span data-ttu-id="eeda0-189">O envio de exemplo permite que a Microsoft colete amostras de software potencialmente mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="eeda0-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="eeda0-190">Para ajudar a fornecer proteção contínua e atualizada, os pesquisadores da Microsoft usam esses exemplos para analisar atividades suspeitas e produzir inteligência de segurança antimalware atualizada.</span><span class="sxs-lookup"><span data-stu-id="eeda0-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="eeda0-191">Coletamos arquivos executáveis do programa, como arquivos .exe arquivos .dll arquivos.</span><span class="sxs-lookup"><span data-stu-id="eeda0-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="eeda0-192">Não coletamos arquivos que contêm dados pessoais, como Microsoft Word documentos e arquivos PDF.</span><span class="sxs-lookup"><span data-stu-id="eeda0-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="eeda0-193">Enviar um arquivo</span><span class="sxs-lookup"><span data-stu-id="eeda0-193">Submit a file</span></span>

1. <span data-ttu-id="eeda0-194">Revise o [guia de envio](/windows/security/threat-protection/intelligence/submission-guide).</span><span class="sxs-lookup"><span data-stu-id="eeda0-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="eeda0-195">Visite o [portal de envio de exemplo](https://www.microsoft.com/wdsi/filesubmission)e envie seu arquivo.</span><span class="sxs-lookup"><span data-stu-id="eeda0-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="eeda0-196">Habilitar envio automático de exemplo</span><span class="sxs-lookup"><span data-stu-id="eeda0-196">Enable automatic sample submission</span></span>

<span data-ttu-id="eeda0-197">Para habilitar o envio automático de exemplo, inicie um console Windows PowerShell como administrador e desmarcar os dados de valor **SubmitSamplesConsent** de acordo com uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="eeda0-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="eeda0-198">Configuração</span><span class="sxs-lookup"><span data-stu-id="eeda0-198">Setting</span></span>  |<span data-ttu-id="eeda0-199">Descrição</span><span class="sxs-lookup"><span data-stu-id="eeda0-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="eeda0-200">**0**  -  **Sempre prompt**</span><span class="sxs-lookup"><span data-stu-id="eeda0-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="eeda0-201">O Microsoft Defender Antivírus solicita que você confirme o envio de todos os arquivos necessários.</span><span class="sxs-lookup"><span data-stu-id="eeda0-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="eeda0-202">Essa é a configuração padrão para Microsoft Defender Antivírus, mas não é recomendada para instalações em Windows Server 2016 ou 2019 sem uma GUI.</span><span class="sxs-lookup"><span data-stu-id="eeda0-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="eeda0-203">**1**   -  **Enviar amostras seguras automaticamente**</span><span class="sxs-lookup"><span data-stu-id="eeda0-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="eeda0-204">O Microsoft Defender Antivírus envia todos os arquivos marcados como "seguros" e solicita o restante dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="eeda0-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="eeda0-205">**2**  -  **Nunca enviar**</span><span class="sxs-lookup"><span data-stu-id="eeda0-205">**2** - **Never send**</span></span>      |<span data-ttu-id="eeda0-206">O Microsoft Defender Antivírus serviço não solicita e não envia arquivos.</span><span class="sxs-lookup"><span data-stu-id="eeda0-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="eeda0-207">**3**  -  **Enviar todos os exemplos automaticamente**</span><span class="sxs-lookup"><span data-stu-id="eeda0-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="eeda0-208">O Microsoft Defender Antivírus envia todos os arquivos sem um prompt para confirmação.</span><span class="sxs-lookup"><span data-stu-id="eeda0-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="eeda0-209">Configurar exclusões automáticas</span><span class="sxs-lookup"><span data-stu-id="eeda0-209">Configure automatic exclusions</span></span>

<span data-ttu-id="eeda0-210">Para ajudar a garantir a segurança e o desempenho, determinadas exclusões são adicionadas automaticamente com base nas funções e recursos que você instala ao usar o Microsoft Defender Antivírus no Windows Server 2016 ou 2019.</span><span class="sxs-lookup"><span data-stu-id="eeda0-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="eeda0-211">Consulte [Configure exclusions in Microsoft Defender Antivírus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="eeda0-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="eeda0-212">Precisa definir Microsoft Defender Antivírus modo passivo?</span><span class="sxs-lookup"><span data-stu-id="eeda0-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="eeda0-213">Se você estiver usando um produto antivírus que não seja da Microsoft como sua solução antivírus principal no Windows Server, você deve definir Microsoft Defender Antivírus modo passivo ou desabilitado.</span><span class="sxs-lookup"><span data-stu-id="eeda0-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="eeda0-214">No Windows Server, versão 1803 ou mais recente ou Windows Server 2019, você pode definir Microsoft Defender Antivírus modo passivo.</span><span class="sxs-lookup"><span data-stu-id="eeda0-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="eeda0-215">No Windows Server 2016, Microsoft Defender Antivírus não é suportado juntamente com um produto antivírus/antimalware que não seja da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eeda0-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="eeda0-216">Nesses casos, você deve definir Microsoft Defender Antivírus modo desabilitado.</span><span class="sxs-lookup"><span data-stu-id="eeda0-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="eeda0-217">Definir Microsoft Defender Antivírus modo passivo usando uma chave do Registro</span><span class="sxs-lookup"><span data-stu-id="eeda0-217">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="eeda0-218">Se você estiver usando o Windows Server, versão 1803 ou Windows Server 2019, poderá definir o Microsoft Defender Antivírus para o modo passivo definindo a seguinte chave do Registro:</span><span class="sxs-lookup"><span data-stu-id="eeda0-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="eeda0-219">Caminho: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="eeda0-219">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="eeda0-220">Nome: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="eeda0-220">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="eeda0-221">Digite: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="eeda0-221">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="eeda0-222">Valor: `1`</span><span class="sxs-lookup"><span data-stu-id="eeda0-222">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="eeda0-223">Desabilitar Microsoft Defender Antivírus usando o assistente Remover Funções e Recursos</span><span class="sxs-lookup"><span data-stu-id="eeda0-223">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="eeda0-224">Consulte [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the Remove Roles and Features **Wizard**.</span><span class="sxs-lookup"><span data-stu-id="eeda0-224">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="eeda0-225">Quando você chegar à etapa **Recursos** do assistente, des limpar a opção Windows Defender **Recursos.**</span><span class="sxs-lookup"><span data-stu-id="eeda0-225">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="eeda0-226">Se você limpar **Windows Defender** por conta própria na seção recursos Windows Defender, será solicitado a remover **a** **GUI** de opção de interface para Windows Defender .</span><span class="sxs-lookup"><span data-stu-id="eeda0-226">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="eeda0-227">Microsoft Defender Antivírus funcionará normalmente sem a interface do usuário, mas a interface do usuário não poderá ser habilitada se você desabilitar o recurso **Windows Defender** principal.</span><span class="sxs-lookup"><span data-stu-id="eeda0-227">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="eeda0-228">Desativar a interface do Microsoft Defender Antivírus usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="eeda0-228">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="eeda0-229">Para desativar a GUI Microsoft Defender Antivírus, use o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eeda0-229">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="eeda0-230">Você está usando Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="eeda0-230">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="eeda0-231">Se você estiver usando Windows Server 2016 e um produto antimalware/antivírus de terceiros que não seja oferecido ou desenvolvido pela Microsoft, você precisará desabilitar/desinstalar Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="eeda0-231">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="eeda0-232">Você não pode desinstalar o aplicativo Segurança do Windows, mas pode desabilitar a interface com essas instruções.</span><span class="sxs-lookup"><span data-stu-id="eeda0-232">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="eeda0-233">O seguinte cmdlet do PowerShell desinstala Microsoft Defender Antivírus no Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="eeda0-233">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="eeda0-234">Para desabilitar Microsoft Defender Antivírus no Windows Server 2016, use o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="eeda0-234">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="eeda0-235">Confira também</span><span class="sxs-lookup"><span data-stu-id="eeda0-235">See also</span></span>

- [<span data-ttu-id="eeda0-236">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="eeda0-236">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="eeda0-237">Microsoft Defender Antivírus compatibilidade</span><span class="sxs-lookup"><span data-stu-id="eeda0-237">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
