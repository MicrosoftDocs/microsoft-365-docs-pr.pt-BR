---
title: Guia de implantação Virtual Desktop Infrastructure microsoft defender antivírus
description: Saiba como implantar o Microsoft Defender Antivírus em um ambiente de área de trabalho virtual para o melhor equilíbrio entre proteção e desempenho.
keywords: vdi, hyper-v, vm, máquina virtual, windows defender, antivírus, av, área de trabalho virtual, rds, área de trabalho remota
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b81addbcaabb1c5ea0d344dbaab9d76a8b100c2b
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690000"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="a8a55-104">Guia de implantação do Microsoft Defender Antivírus em um ambiente de infraestrutura de área de trabalho virtual (VDI)</span><span class="sxs-lookup"><span data-stu-id="a8a55-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a8a55-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a8a55-105">**Applies to:**</span></span>

- [<span data-ttu-id="a8a55-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a8a55-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a8a55-107">Além das configurações locais ou de hardware padrão, você também pode usar o Microsoft Defender Antivírus em um ambiente de área de trabalho remota (RDS) ou VDI (infraestrutura de área de trabalho virtual).</span><span class="sxs-lookup"><span data-stu-id="a8a55-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="a8a55-108">Consulte [a Documentação da Área de](/azure/virtual-desktop) Trabalho Virtual do Windows para obter mais detalhes sobre os Serviços de Área de Trabalho Remota da Microsoft e suporte à VDI.</span><span class="sxs-lookup"><span data-stu-id="a8a55-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="a8a55-109">Para máquinas virtuais baseadas no Azure, consulte [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span><span class="sxs-lookup"><span data-stu-id="a8a55-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="a8a55-110">Com a capacidade de implantar atualizações facilmente em VMs em execução em VDIs, reduzimos este guia para se concentrar em como você pode obter atualizações em seus máquinas de forma rápida e fácil.</span><span class="sxs-lookup"><span data-stu-id="a8a55-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="a8a55-111">Você não precisa mais criar e selar imagens douradas periodicamente, pois as atualizações são expandidas para seus bits de componente no servidor host e baixadas diretamente para a VM quando ela estiver ligada.</span><span class="sxs-lookup"><span data-stu-id="a8a55-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="a8a55-112">Este guia descreve como configurar suas VMs para proteção e desempenho ideais, incluindo como:</span><span class="sxs-lookup"><span data-stu-id="a8a55-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="a8a55-113">Configurar um compartilhamento de arquivos VDI dedicado para atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="a8a55-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="a8a55-114">Randomizar verificações agendadas</span><span class="sxs-lookup"><span data-stu-id="a8a55-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="a8a55-115">Usar verificações rápidas</span><span class="sxs-lookup"><span data-stu-id="a8a55-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="a8a55-116">Impedir notificações</span><span class="sxs-lookup"><span data-stu-id="a8a55-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="a8a55-117">Desabilitar verificações de ocorrência após cada atualização</span><span class="sxs-lookup"><span data-stu-id="a8a55-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="a8a55-118">Examinar máquinas ou máquinas desatentas que estão offline há algum tempo</span><span class="sxs-lookup"><span data-stu-id="a8a55-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="a8a55-119">Aplicar exclusões</span><span class="sxs-lookup"><span data-stu-id="a8a55-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="a8a55-120">Você também pode baixar o whitepaper [Microsoft Defender Antivírus](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)no Virtual Desktop Infrastructure , que analisa o novo recurso de atualização de inteligência de segurança compartilhada, além de testes de desempenho e orientações sobre como testar o desempenho do antivírus em sua própria VDI.</span><span class="sxs-lookup"><span data-stu-id="a8a55-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8a55-121">Embora a VDI possa ser hospedada no Windows Server 2012 ou no Windows Server 2016, as máquinas virtuais (VMs) devem estar executando o Windows 10, 1607 no mínimo, devido ao aumento das tecnologias e recursos de proteção que não estão disponíveis em versões anteriores do Windows.</span><span class="sxs-lookup"><span data-stu-id="a8a55-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="a8a55-122">Há melhorias de desempenho e recursos na forma como o Microsoft Defender AV opera em máquinas virtuais no Windows 10 Insider Preview, build 18323 (e posterior).</span><span class="sxs-lookup"><span data-stu-id="a8a55-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="a8a55-123">Identificaremos neste guia se você precisar usar uma com build do Insider Preview; se não for especificado, a versão mínima necessária para a melhor proteção e desempenho é o Windows 10 1607.</span><span class="sxs-lookup"><span data-stu-id="a8a55-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="a8a55-124">Configurar um compartilhamento de arquivos VDI dedicado</span><span class="sxs-lookup"><span data-stu-id="a8a55-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="a8a55-125">No Windows 10, versão 1903, introduzimos o recurso de inteligência de segurança compartilhada, que descarrega a descompactação de atualizações de inteligência de segurança baixadas em uma máquina host, salvando recursos de CPU, disco e memória anteriores em computadores individuais.</span><span class="sxs-lookup"><span data-stu-id="a8a55-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="a8a55-126">Esse recurso foi reportada e agora funciona no Windows 10 versão 1703 ou superior.</span><span class="sxs-lookup"><span data-stu-id="a8a55-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="a8a55-127">Você pode definir esse recurso com uma Política de Grupo ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a8a55-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="a8a55-128">Use a Política de Grupo para habilitar o recurso de inteligência de segurança compartilhada:</span><span class="sxs-lookup"><span data-stu-id="a8a55-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="a8a55-129">No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de Grupo, clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="a8a55-130">No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**</span><span class="sxs-lookup"><span data-stu-id="a8a55-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="a8a55-131">Clique **em Modelos Administrativos**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="a8a55-132">Expanda a árvore para **componentes do Windows** Atualizações de Inteligência de Segurança do Microsoft Defender  >    >  **Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="a8a55-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="a8a55-133">Clique duas vezes em Definir local de inteligência de segurança para **clientes VDI** e defina a opção **como Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="a8a55-134">Um campo é exibido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a8a55-134">A field automatically appears.</span></span>

6. <span data-ttu-id="a8a55-135">Insira `\\<sharedlocation\>\wdav-update` (para ajudar com esse valor, consulte [Baixar e descompactar](#download-and-unpackage-the-latest-updates)).</span><span class="sxs-lookup"><span data-stu-id="a8a55-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="a8a55-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-136">Click **OK**.</span></span>

8. <span data-ttu-id="a8a55-137">Implante o GPO nas VMs que você deseja testar.</span><span class="sxs-lookup"><span data-stu-id="a8a55-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="a8a55-138">Usar o PowerShell para habilitar o recurso de inteligência de segurança compartilhada</span><span class="sxs-lookup"><span data-stu-id="a8a55-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="a8a55-139">Use o cmdlet a seguir para habilitar o recurso.</span><span class="sxs-lookup"><span data-stu-id="a8a55-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="a8a55-140">Em seguida, você precisará pressionar isso, pois normalmente empurraria as políticas de configuração baseadas no PowerShell para as VMs:</span><span class="sxs-lookup"><span data-stu-id="a8a55-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="a8a55-141">Consulte a [seção Baixar e descompactar](#download-and-unpackage-the-latest-updates) o \<shared location\> que será.</span><span class="sxs-lookup"><span data-stu-id="a8a55-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="a8a55-142">Baixar e descompactar as atualizações mais recentes</span><span class="sxs-lookup"><span data-stu-id="a8a55-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="a8a55-143">Agora você pode começar a baixar e instalar novas atualizações.</span><span class="sxs-lookup"><span data-stu-id="a8a55-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="a8a55-144">Criamos um exemplo de script do PowerShell para você abaixo.</span><span class="sxs-lookup"><span data-stu-id="a8a55-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="a8a55-145">Esse script é a maneira mais fácil de baixar novas atualizações e preparar as VMs.</span><span class="sxs-lookup"><span data-stu-id="a8a55-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="a8a55-146">Em seguida, você deve definir o script para ser executado em um determinado momento na máquina de gerenciamento usando uma tarefa agendada (ou, se você estiver familiarizado com o uso de scripts do PowerShell no Azure, Intune ou SCCM, também poderá usar esses scripts).</span><span class="sxs-lookup"><span data-stu-id="a8a55-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="a8a55-147">Você pode definir uma tarefa agendada para ser executado uma vez por dia para que sempre que o pacote for baixado e descompactado, as VMs receberão a nova atualização.</span><span class="sxs-lookup"><span data-stu-id="a8a55-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="a8a55-148">Sugerimos começar uma vez por dia, mas você deve experimentar aumentar ou diminuir a frequência para entender o impacto.</span><span class="sxs-lookup"><span data-stu-id="a8a55-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="a8a55-149">Normalmente, os pacotes de inteligência de segurança são publicados uma vez a cada três a quatro horas.</span><span class="sxs-lookup"><span data-stu-id="a8a55-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="a8a55-150">A configuração de uma frequência menor que quatro horas não é aconselhada porque aumentará a sobrecarga de rede em sua máquina de gerenciamento sem benefícios.</span><span class="sxs-lookup"><span data-stu-id="a8a55-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="a8a55-151">Definir uma tarefa agendada para executar o script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8a55-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="a8a55-152">Na máquina de gerenciamento, abra o menu Iniciar e digite **Agendador de Tarefas.**</span><span class="sxs-lookup"><span data-stu-id="a8a55-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="a8a55-153">Abra-o e selecione **Criar tarefa...**</span><span class="sxs-lookup"><span data-stu-id="a8a55-153">Open it and select **Create task…**</span></span> <span data-ttu-id="a8a55-154">no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="a8a55-154">on the side panel.</span></span>

2. <span data-ttu-id="a8a55-155">Insira o nome como **desempacotar inteligência de segurança.**</span><span class="sxs-lookup"><span data-stu-id="a8a55-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="a8a55-156">Vá para a **guia Gatilho.** Selecione **Novo...**</span><span class="sxs-lookup"><span data-stu-id="a8a55-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="a8a55-157"> > **Diariamente** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="a8a55-158">Vá para a **guia Ações.** Selecione **Novo...**</span><span class="sxs-lookup"><span data-stu-id="a8a55-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="a8a55-159">Insira **o PowerShell** no **campo Programa/Script.**</span><span class="sxs-lookup"><span data-stu-id="a8a55-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="a8a55-160">Insira `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` no campo Adicionar **argumentos.**</span><span class="sxs-lookup"><span data-stu-id="a8a55-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="a8a55-161">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-161">Select **OK**.</span></span>

4. <span data-ttu-id="a8a55-162">Você pode optar por configurar configurações adicionais, se desejar.</span><span class="sxs-lookup"><span data-stu-id="a8a55-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="a8a55-163">Selecione **OK** para salvar a tarefa agendada.</span><span class="sxs-lookup"><span data-stu-id="a8a55-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="a8a55-164">Você pode iniciar a atualização manualmente clicando com o botão direito do mouse na tarefa e clicando em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="a8a55-165">Baixar e descompactar manualmente</span><span class="sxs-lookup"><span data-stu-id="a8a55-165">Download and unpackage manually</span></span>

<span data-ttu-id="a8a55-166">Se você preferir fazer tudo manualmente, veja o que fazer para replicar o comportamento do script:</span><span class="sxs-lookup"><span data-stu-id="a8a55-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="a8a55-167">Crie uma nova pasta na raiz do sistema chamada para armazenar atualizações de `wdav_update` inteligência, por exemplo, crie a pasta `c:\wdav_update` .</span><span class="sxs-lookup"><span data-stu-id="a8a55-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="a8a55-168">Criar uma subpasta em *wdav_update* com um nome GUID, como `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="a8a55-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="a8a55-169">Veja um exemplo: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="a8a55-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8a55-170">No script, definimos-o para que os últimos 12 dígitos do GUID sejam o ano, mês, dia e hora em que o arquivo foi baixado para que uma nova pasta seja criada sempre.</span><span class="sxs-lookup"><span data-stu-id="a8a55-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="a8a55-171">Você pode alterar isso para que o arquivo seja baixado para a mesma pasta sempre.</span><span class="sxs-lookup"><span data-stu-id="a8a55-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="a8a55-172">Baixe um pacote de inteligência de segurança [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  na pasta GUID.</span><span class="sxs-lookup"><span data-stu-id="a8a55-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="a8a55-173">O arquivo deve ser nomeado `mpam-fe.exe` .</span><span class="sxs-lookup"><span data-stu-id="a8a55-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="a8a55-174">Abra uma janela de prompt de cmd e navegue até a pasta GUID criada.</span><span class="sxs-lookup"><span data-stu-id="a8a55-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="a8a55-175">Use o **comando de extração /X** para extrair os arquivos, por exemplo `mpam-fe.exe /X` .</span><span class="sxs-lookup"><span data-stu-id="a8a55-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8a55-176">As VMs receberão o pacote atualizado sempre que uma nova pasta GUID for criada com um pacote de atualização extraído ou sempre que uma pasta existente for atualizada com um novo pacote extraído.</span><span class="sxs-lookup"><span data-stu-id="a8a55-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="a8a55-177">Randomizar verificações agendadas</span><span class="sxs-lookup"><span data-stu-id="a8a55-177">Randomize scheduled scans</span></span>

<span data-ttu-id="a8a55-178">Verificações agendadas são executados além da proteção e verificação em tempo [real.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a8a55-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="a8a55-179">A hora de início da verificação em si ainda é baseada na política de verificação agendada (**ScheduleDay**, **ScheduleTime** e **ScheduleQuickScanTime**).</span><span class="sxs-lookup"><span data-stu-id="a8a55-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="a8a55-180">A randomização fará com que o Microsoft Defender Antivírus inicie uma verificação em cada máquina dentro de uma janela de 4 horas a partir do tempo definido para a verificação agendada.</span><span class="sxs-lookup"><span data-stu-id="a8a55-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="a8a55-181">Consulte [Agendar verificações](scheduled-catch-up-scans-microsoft-defender-antivirus.md) para outras opções de configuração disponíveis para verificações agendadas.</span><span class="sxs-lookup"><span data-stu-id="a8a55-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="a8a55-182">Usar verificações rápidas</span><span class="sxs-lookup"><span data-stu-id="a8a55-182">Use quick scans</span></span>

<span data-ttu-id="a8a55-183">Você pode especificar o tipo de verificação que deve ser executada durante uma verificação agendada.</span><span class="sxs-lookup"><span data-stu-id="a8a55-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="a8a55-184">As verificações rápidas são a abordagem preferencial, pois foram projetadas para procurar em todos os locais onde o malware precisa residir para estar ativo.</span><span class="sxs-lookup"><span data-stu-id="a8a55-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="a8a55-185">O procedimento a seguir descreve como configurar verificações rápidas usando a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="a8a55-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="a8a55-186">No Editor de Política de Grupo, vá para **Modelos Administrativos Componentes**  >  **do Windows** Microsoft Defender  >    >  **Antivírus Scan**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="a8a55-187">Selecione **Especificar o tipo de verificação a ser usado para uma verificação agendada** e edite a configuração de política.</span><span class="sxs-lookup"><span data-stu-id="a8a55-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="a8a55-188">De definir a política **como Habilitado** e, em Seguida, em **Opções,** selecione  **Verificação rápida**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="a8a55-189">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-189">Select **OK**.</span></span> 

5. <span data-ttu-id="a8a55-190">Implante seu objeto de Política de Grupo como você costuma fazer.</span><span class="sxs-lookup"><span data-stu-id="a8a55-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="a8a55-191">Impedir notificações</span><span class="sxs-lookup"><span data-stu-id="a8a55-191">Prevent notifications</span></span>

<span data-ttu-id="a8a55-192">Às vezes, as notificações do Microsoft Defender Antivírus podem ser enviadas ou persistir em várias sessões.</span><span class="sxs-lookup"><span data-stu-id="a8a55-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="a8a55-193">Para minimizar esse problema, você pode bloquear a interface de usuário do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="a8a55-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="a8a55-194">O procedimento a seguir descreve como suprimir notificações com a Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="a8a55-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="a8a55-195">No Editor de Política de Grupo, acesse **Componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Interface do Cliente**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="a8a55-196">Selecione **Suprimir todas as notificações** e edite as configurações de política.</span><span class="sxs-lookup"><span data-stu-id="a8a55-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="a8a55-197">De definir a política **como Habilitado** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="a8a55-198">Implante seu objeto de Política de Grupo como você costuma fazer.</span><span class="sxs-lookup"><span data-stu-id="a8a55-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="a8a55-199">A supressão de notificações impede que as notificações do Microsoft Defender Antivírus sejam aparecendo no Centro de Ações no Windows 10 quando as verificações são feitas ou ações de correção são tomadas.</span><span class="sxs-lookup"><span data-stu-id="a8a55-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="a8a55-200">No entanto, sua equipe de operações de segurança verá os resultados da verificação no Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="a8a55-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="a8a55-201">Para abrir o Centro de Ações no Windows 10, dê uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="a8a55-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="a8a55-202">Na extremidade direita da barra de tarefas, selecione o ícone centro de ações.</span><span class="sxs-lookup"><span data-stu-id="a8a55-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="a8a55-203">Pressione o botão tecla de logotipo do Windows + A.</span><span class="sxs-lookup"><span data-stu-id="a8a55-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="a8a55-204">Em um dispositivo touchscreen, passe o dedo da borda direita da tela.</span><span class="sxs-lookup"><span data-stu-id="a8a55-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="a8a55-205">Desabilitar verificações após uma atualização</span><span class="sxs-lookup"><span data-stu-id="a8a55-205">Disable scans after an update</span></span>

<span data-ttu-id="a8a55-206">Desabilitar uma verificação após uma atualização impedirá que uma verificação ocorra depois de receber uma atualização.</span><span class="sxs-lookup"><span data-stu-id="a8a55-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="a8a55-207">Você pode aplicar essa configuração ao criar a imagem base se também tiver executado uma verificação rápida.</span><span class="sxs-lookup"><span data-stu-id="a8a55-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="a8a55-208">Dessa forma, você pode impedir que a VM recém-atualizada faça uma verificação novamente (como você já a examinou ao criar a imagem base).</span><span class="sxs-lookup"><span data-stu-id="a8a55-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8a55-209">Executar verificações após uma atualização ajudará a garantir que suas VMs sejam protegidas com as atualizações mais recentes de Inteligência de Segurança.</span><span class="sxs-lookup"><span data-stu-id="a8a55-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="a8a55-210">Desabilitar essa opção reduzirá o nível de proteção de suas VMs e só deve ser usado ao criar ou implantar a imagem base pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="a8a55-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="a8a55-211">No Editor de Política de Grupo, acesse **Componentes do Windows** Atualizações de Inteligência de Segurança do  >  **Microsoft Defender**  >  **Antivírus.**</span><span class="sxs-lookup"><span data-stu-id="a8a55-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="a8a55-212">Selecione **Ativar a verificação após a atualização de inteligência de** segurança e edite a configuração de política.</span><span class="sxs-lookup"><span data-stu-id="a8a55-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="a8a55-213">De definir a política como **Desabilitada**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="a8a55-214">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-214">Select **OK**.</span></span>

5. <span data-ttu-id="a8a55-215">Implante seu objeto de Política de Grupo como você costuma fazer.</span><span class="sxs-lookup"><span data-stu-id="a8a55-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="a8a55-216">Essa política impede que uma verificação seja executado imediatamente após uma atualização.</span><span class="sxs-lookup"><span data-stu-id="a8a55-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="a8a55-217">Examinar VMs que tenham sido offline</span><span class="sxs-lookup"><span data-stu-id="a8a55-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="a8a55-218">No Editor de Política de Grupo, acesse **Componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Scan**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="a8a55-219">Selecione **Ativar a verificação rápida de catch-up** e edite a configuração de política.</span><span class="sxs-lookup"><span data-stu-id="a8a55-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="a8a55-220">De definir a política como **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="a8a55-221">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-221">Select **OK**.</span></span>

5. <span data-ttu-id="a8a55-222">Implante seu Objeto de Política de Grupo como normalmente faz.</span><span class="sxs-lookup"><span data-stu-id="a8a55-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="a8a55-223">Essa política força uma verificação se a VM tiver perdido duas ou mais verificações agendadas consecutivas.</span><span class="sxs-lookup"><span data-stu-id="a8a55-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="a8a55-224">Habilitar o modo de interface do usuário sem cabeça</span><span class="sxs-lookup"><span data-stu-id="a8a55-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="a8a55-225">No Editor de Política de Grupo, acesse **Componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Interface do Cliente**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="a8a55-226">Selecione **Habilitar o modo de interface do usuário sem** cabeça e edite a política.</span><span class="sxs-lookup"><span data-stu-id="a8a55-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="a8a55-227">De definir a política como **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="a8a55-228">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a8a55-228">Click **OK**.</span></span>

5. <span data-ttu-id="a8a55-229">Implante seu Objeto de Política de Grupo como normalmente faz.</span><span class="sxs-lookup"><span data-stu-id="a8a55-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="a8a55-230">Essa política oculta toda a interface do usuário do Microsoft Defender Antivírus dos usuários finais em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8a55-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="a8a55-231">Exclusões</span><span class="sxs-lookup"><span data-stu-id="a8a55-231">Exclusions</span></span>

<span data-ttu-id="a8a55-232">As exclusões podem ser adicionadas, removidas ou personalizadas para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="a8a55-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="a8a55-233">Para obter mais informações, [consulte Configure Microsoft Defender Antivírus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="a8a55-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8a55-234">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a8a55-234">Additional resources</span></span>

- [<span data-ttu-id="a8a55-235">Blog da Comunidade Técnica: Configurando o Microsoft Defender Antivírus para máquinas VDI não persistentes</span><span class="sxs-lookup"><span data-stu-id="a8a55-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="a8a55-236">Fóruns do TechNet em Serviços de Área de Trabalho Remota e VDI</span><span class="sxs-lookup"><span data-stu-id="a8a55-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="a8a55-237">Script signatureDownloadCustomTask PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8a55-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)