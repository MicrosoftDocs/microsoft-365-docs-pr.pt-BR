---
title: Logs de diagnóstico
description: Logs que podem ser coletados de dispositivos durante a solução de problemas e como eles são armazenados
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272883"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="a8fee-104">Logs de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a8fee-104">Diagnostic logs</span></span>

<span data-ttu-id="a8fee-105">Quando solucionarmos um problema em um dispositivo gerenciado pela Área de Trabalho Gerenciada da Microsoft, se um relatado ou identificado pelo nosso serviço, talvez seja preciso coletar certos logs de diagnóstico do dispositivo sem intervenção do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8fee-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="a8fee-106">Não coletamos conteúdo ou informações gerados pelo usuário de diretórios de usuários.</span><span class="sxs-lookup"><span data-stu-id="a8fee-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="a8fee-107">Coletamos apenas dados de diagnóstico e log que dizem respeito à saúde e ao status do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a8fee-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="a8fee-108">Armazenamos todos os logs coletados por 28 dias e os excluímos.</span><span class="sxs-lookup"><span data-stu-id="a8fee-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="a8fee-109">Processemos todos os logs coletados de um dispositivo seguindo nossos padrões [de tratamento de dados.](privacy-personal-data.md)</span><span class="sxs-lookup"><span data-stu-id="a8fee-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="a8fee-110">Dados coletados</span><span class="sxs-lookup"><span data-stu-id="a8fee-110">Data collected</span></span>

<span data-ttu-id="a8fee-111">Essa lista inclui todas as pastas, logs de eventos, executáveis ou locais do registro dos Área de Trabalho Gerenciada da Microsoft que podem coletar logs de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="a8fee-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="a8fee-112">Os dados reais coletados serão um subconjunto dessa lista e dependerão do problema identificado.</span><span class="sxs-lookup"><span data-stu-id="a8fee-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="a8fee-113">Chaves de registro</span><span class="sxs-lookup"><span data-stu-id="a8fee-113">Registry keys</span></span>

- <span data-ttu-id="a8fee-114">Serviços HKLM \\ SYSTEM \\ CurrentControlSet \\</span><span class="sxs-lookup"><span data-stu-id="a8fee-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="a8fee-115">HKLM \\ SOFTWARE \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="a8fee-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="a8fee-116">Políticas de SOFTWARE HKLM \\ \\ Microsoft Windows \\ \\ \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="a8fee-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="a8fee-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="a8fee-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="a8fee-118">Políticas de software HKLM \\ \\ Microsoft \\ \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="a8fee-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="a8fee-119">Software HKLM \\ \\ Microsoft Windows \\ \\ \\ WindowsStore WindowsUpdate do CurrentVersion \\</span><span class="sxs-lookup"><span data-stu-id="a8fee-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="a8fee-120">Software HKLM \\ \\ Microsoft Windows NT \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="a8fee-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="a8fee-121">Software HKLM \\ \\ Microsoft Windows NT \\ \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="a8fee-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="a8fee-122">SOFTWARE HKLM \\ \\ Microsoft Windows \\ \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="a8fee-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="a8fee-123">Firmware do controle HKLM \\ SYSTEM \\ CurrentControlSetResources \\ \\</span><span class="sxs-lookup"><span data-stu-id="a8fee-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="a8fee-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="a8fee-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="a8fee-125">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="a8fee-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="a8fee-126">Software HKLM \\ \\ Microsoft Windows \\ \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="a8fee-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="a8fee-127">Software HKLM \\ \\ Microsoft Windows NT \\ \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="a8fee-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="a8fee-128">Instalação do SISTEMA HKLM \\ \\</span><span class="sxs-lookup"><span data-stu-id="a8fee-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="a8fee-129">HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="a8fee-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="a8fee-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="a8fee-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="a8fee-131">Software HKLM \\ Microsoft Windows Proteção Avançada contra \\ \\ Ameaças</span><span class="sxs-lookup"><span data-stu-id="a8fee-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="a8fee-132">Software HKLM \\ Microsoft \\ Windows \\ \\ LogonUI de \\ \\ autenticação CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="a8fee-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="a8fee-133">SOFTWARE HKLM \\ \\ Microsoft Windows Internet \\ \\ CurrentVersion \\ Configurações</span><span class="sxs-lookup"><span data-stu-id="a8fee-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="a8fee-134">Software HKLM \\ \\ Microsoft Windows \\ \\ \\ Desinstalação do CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="a8fee-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="a8fee-135">Políticas de software HKLM \\ \\</span><span class="sxs-lookup"><span data-stu-id="a8fee-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="a8fee-136">Políticas de SOFTWARE HKLM \\ \\ Microsoft \\ \\ Cryptography Configuration \\ \\ SSL</span><span class="sxs-lookup"><span data-stu-id="a8fee-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="a8fee-137">Políticas de SOFTWARE HKLM \\ Microsoft Windows Proteção Avançada contra \\ \\ \\ Ameaças</span><span class="sxs-lookup"><span data-stu-id="a8fee-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="a8fee-138">SOFTWARE HKLM \\ \\ WOW6432Node \\ Microsoft \\ Windows \\ \\ Desinstalação do CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="a8fee-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="a8fee-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="a8fee-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="a8fee-140">Comandos</span><span class="sxs-lookup"><span data-stu-id="a8fee-140">Commands</span></span>

- <span data-ttu-id="a8fee-141">%programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles</span><span class="sxs-lookup"><span data-stu-id="a8fee-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="a8fee-142">%windir% \\ system32 \\certutil.exe -store</span><span class="sxs-lookup"><span data-stu-id="a8fee-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="a8fee-143">%windir% \\ system32 \\certutil.exe -store -user my</span><span class="sxs-lookup"><span data-stu-id="a8fee-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="a8fee-144">%windir% \\ system32 \\Dsregcmd.exe /status</span><span class="sxs-lookup"><span data-stu-id="a8fee-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="a8fee-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="a8fee-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="a8fee-146">%windir% \\ system32 \\ipconfig.exe /displaydns</span><span class="sxs-lookup"><span data-stu-id="a8fee-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="a8fee-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="a8fee-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="a8fee-148">%windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="a8fee-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="a8fee-149">%windir% \\ system32 \\netsh.exe advfirewall mostram allprofiles</span><span class="sxs-lookup"><span data-stu-id="a8fee-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="a8fee-150">%windir% \\ system32 \\netsh.exe advfirewall mostrar global</span><span class="sxs-lookup"><span data-stu-id="a8fee-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="a8fee-151">%windir% \\ system32 \\netsh.exe lan mostrar perfis</span><span class="sxs-lookup"><span data-stu-id="a8fee-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="a8fee-152">%windir% \\ system32 \\netsh.exe winhttp show proxy</span><span class="sxs-lookup"><span data-stu-id="a8fee-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="a8fee-153">%windir% \\ system32 \\netsh.exe wlan mostrar perfis</span><span class="sxs-lookup"><span data-stu-id="a8fee-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="a8fee-154">%windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="a8fee-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="a8fee-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="a8fee-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="a8fee-156">%windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html</span><span class="sxs-lookup"><span data-stu-id="a8fee-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="a8fee-157">%windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html</span><span class="sxs-lookup"><span data-stu-id="a8fee-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="a8fee-158">bitsadmin /list /allusers /verbose</span><span class="sxs-lookup"><span data-stu-id="a8fee-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="a8fee-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="a8fee-159">fltMC.exe</span></span>
- <span data-ttu-id="a8fee-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="a8fee-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="a8fee-161">manage-bde -protectors -get</span><span class="sxs-lookup"><span data-stu-id="a8fee-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="a8fee-162">Windows PowerShell comandos:</span><span class="sxs-lookup"><span data-stu-id="a8fee-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="a8fee-163">Get-appxpackage -allusers</span><span class="sxs-lookup"><span data-stu-id="a8fee-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="a8fee-164">Get-appxpackage -packagetype bundle</span><span class="sxs-lookup"><span data-stu-id="a8fee-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="a8fee-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="a8fee-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="a8fee-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="a8fee-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="a8fee-167">Get-WmiObject -Class win32 \_ product</span><span class="sxs-lookup"><span data-stu-id="a8fee-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="a8fee-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="a8fee-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="a8fee-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="a8fee-169">Get-Service</span></span>
    - <span data-ttu-id="a8fee-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="a8fee-170">Get-Process</span></span>
    - <span data-ttu-id="a8fee-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="a8fee-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="a8fee-172">Logs de eventos</span><span class="sxs-lookup"><span data-stu-id="a8fee-172">Event logs</span></span>

- <span data-ttu-id="a8fee-173">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="a8fee-173">Application</span></span>
- <span data-ttu-id="a8fee-174">Microsoft-Windows-AppLocker/EXE e DLL</span><span class="sxs-lookup"><span data-stu-id="a8fee-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="a8fee-175">Microsoft-Windows-AppLocker/MSI e Script</span><span class="sxs-lookup"><span data-stu-id="a8fee-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="a8fee-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span><span class="sxs-lookup"><span data-stu-id="a8fee-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="a8fee-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span><span class="sxs-lookup"><span data-stu-id="a8fee-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="a8fee-178">Gerenciamento do Microsoft-Windows-Bitlocker/Bitlocker</span><span class="sxs-lookup"><span data-stu-id="a8fee-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="a8fee-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="a8fee-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="a8fee-180">Microsoft-Windows-SenseIR/Operacional</span><span class="sxs-lookup"><span data-stu-id="a8fee-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="a8fee-181">Configurar</span><span class="sxs-lookup"><span data-stu-id="a8fee-181">Setup</span></span>
- <span data-ttu-id="a8fee-182">Sistema</span><span class="sxs-lookup"><span data-stu-id="a8fee-182">System</span></span>

### <a name="files"></a><span data-ttu-id="a8fee-183">Arquivos</span><span class="sxs-lookup"><span data-stu-id="a8fee-183">Files</span></span>

- <span data-ttu-id="a8fee-184">%ProgramData% \\ \\ Coletores de DiagnosticLogCSP da Microsoft \\ \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="a8fee-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="a8fee-185">%ProgramData% \\ Logs do Microsoft \\ IntuneManagementExtension \\ \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="a8fee-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="a8fee-186">%ProgramData% \\ Microsoft Windows Defender Suporte \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="a8fee-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="a8fee-187">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="a8fee-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="a8fee-188">%ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="a8fee-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="a8fee-189">%windir% \\ ccm \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="a8fee-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="a8fee-190">%windir% \\ ccmsetup \\ logs \* .log</span><span class="sxs-lookup"><span data-stu-id="a8fee-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="a8fee-191">%windir% \\ registra \\ CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="a8fee-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="a8fee-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="a8fee-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="a8fee-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="a8fee-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="a8fee-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="a8fee-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="a8fee-195">Sessões de manutenção %windir% \\ \\ActionList.xml \\</span><span class="sxs-lookup"><span data-stu-id="a8fee-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="a8fee-196">Sessões de manutenção %windir% \\ \\Sessions.xml \\</span><span class="sxs-lookup"><span data-stu-id="a8fee-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="a8fee-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="a8fee-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="a8fee-198">%windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="a8fee-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="a8fee-199">%windir% \\ logs \\ dism \\ dism.log</span><span class="sxs-lookup"><span data-stu-id="a8fee-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="a8fee-200">%SystemRoot% \\ Logs \\ winevt do System32 </span><span class="sxs-lookup"><span data-stu-id="a8fee-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\\\
- <span data-ttu-id="a8fee-201">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="a8fee-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="a8fee-202">%appdata% \\ Microsoft \\ Teams \\ \\ \* skylib .blog</span><span class="sxs-lookup"><span data-stu-id="a8fee-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="a8fee-203">%appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="a8fee-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="a8fee-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="a8fee-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="a8fee-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="a8fee-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>