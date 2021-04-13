---
title: Solucionar problemas do Microsoft Defender Antivírus durante a migração de uma solução de terceiros
description: Solucionar erros comuns ao migrar para o Microsoft Defender Antivírus
keywords: event, error code, logging, troubleshooting, microsoft defender antivírus, windows defender antivírus, migration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2ca486b86c24e18ae08753b5e88f2eb42986dddf
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689880"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="b6b36-104">Solucionar problemas do Microsoft Defender Antivírus durante a migração de uma solução de terceiros</span><span class="sxs-lookup"><span data-stu-id="b6b36-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b6b36-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b6b36-105">**Applies to:**</span></span>

- [<span data-ttu-id="b6b36-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b6b36-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="b6b36-107">Você pode encontrar ajuda aqui se encontrar problemas ao migrar de uma solução de segurança de terceiros para o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="b6b36-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="b6b36-108">Revisar logs de eventos</span><span class="sxs-lookup"><span data-stu-id="b6b36-108">Review event logs</span></span>

<span data-ttu-id="b6b36-109">Abra o aplicativo visualizador de eventos selecionando o **ícone pesquisar** na barra de tarefas e procurando o *visualizador de eventos*.</span><span class="sxs-lookup"><span data-stu-id="b6b36-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="b6b36-110">Informações sobre o Microsoft Defender Antivírus podem ser encontradas em **Logs de Aplicativos e Serviços** do  >  **Microsoft**  >  **Windows**  >  **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="b6b36-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="b6b36-111">A partir daí, selecione **Abrir** em **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="b6b36-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="b6b36-112">Selecionar um evento no painel de detalhes mostrará mais informações sobre um evento no painel inferior, nas guias **Geral** e **Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="b6b36-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="b6b36-113">O Microsoft Defender Antivírus não iniciará</span><span class="sxs-lookup"><span data-stu-id="b6b36-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="b6b36-114">Esse problema pode se manifesto na forma de várias IDs de evento diferentes, todas com a mesma causa subjacente.</span><span class="sxs-lookup"><span data-stu-id="b6b36-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="b6b36-115">IDs de eventos associados</span><span class="sxs-lookup"><span data-stu-id="b6b36-115">Associated event IDs</span></span>

 <span data-ttu-id="b6b36-116">ID de evento</span><span class="sxs-lookup"><span data-stu-id="b6b36-116">Event ID</span></span> | <span data-ttu-id="b6b36-117">Nome do log</span><span class="sxs-lookup"><span data-stu-id="b6b36-117">Log name</span></span> | <span data-ttu-id="b6b36-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6b36-118">Description</span></span> | <span data-ttu-id="b6b36-119">Origem</span><span class="sxs-lookup"><span data-stu-id="b6b36-119">Source</span></span>
-|-|-|-
<span data-ttu-id="b6b36-120">15 </span><span class="sxs-lookup"><span data-stu-id="b6b36-120">15</span></span> | <span data-ttu-id="b6b36-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="b6b36-121">Application</span></span> | <span data-ttu-id="b6b36-122">Atualizou Windows Defender status com êxito para SECURITY_PRODUCT_STATE_OFF.</span><span class="sxs-lookup"><span data-stu-id="b6b36-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="b6b36-123">Central de Segurança</span><span class="sxs-lookup"><span data-stu-id="b6b36-123">Security Center</span></span>
<span data-ttu-id="b6b36-124">5007</span><span class="sxs-lookup"><span data-stu-id="b6b36-124">5007</span></span> | <span data-ttu-id="b6b36-125">Microsoft-Windows-Windows Defender/Operacional</span><span class="sxs-lookup"><span data-stu-id="b6b36-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="b6b36-126">Windows Defender Configuração antivírus foi alterada.</span><span class="sxs-lookup"><span data-stu-id="b6b36-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="b6b36-127">Se esse for um evento inesperado, você deverá revisar as configurações, pois isso pode ser o resultado de malware.</span><span class="sxs-lookup"><span data-stu-id="b6b36-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="b6b36-128">**Valor antigo:** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="b6b36-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="b6b36-129">**Novo valor:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="b6b36-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="b6b36-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b6b36-130">Windows Defender</span></span>
<span data-ttu-id="b6b36-131">5010</span><span class="sxs-lookup"><span data-stu-id="b6b36-131">5010</span></span> | <span data-ttu-id="b6b36-132">Microsoft-Windows-Windows Defender/Operacional</span><span class="sxs-lookup"><span data-stu-id="b6b36-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="b6b36-133">Windows Defender verificação de antivírus para spyware e outros softwares potencialmente indesejados está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b6b36-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="b6b36-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b6b36-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="b6b36-135">Como saber se o Microsoft Defender Antivírus não iniciará porque um antivírus de terceiros está instalado</span><span class="sxs-lookup"><span data-stu-id="b6b36-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="b6b36-136">Em um dispositivo Windows 10, se você não estiver usando o Microsoft Defender para Ponto de Extremidade e tiver um antivírus de terceiros instalado, o Microsoft Defender Antivírus será automaticamente desligado.</span><span class="sxs-lookup"><span data-stu-id="b6b36-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="b6b36-137">Se você estiver usando o Microsoft Defender para Ponto de Extremidade com um antivírus de terceiros instalado, o Microsoft Defender Antivírus começará no modo passivo, com funcionalidade reduzida.</span><span class="sxs-lookup"><span data-stu-id="b6b36-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="b6b36-138">O cenário descrito se aplica somente ao Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b6b36-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="b6b36-139">Outras versões do Windows têm [respostas diferentes](microsoft-defender-antivirus-compatibility.md) ao Microsoft Defender Antivírus que está sendo executado junto com software de segurança de terceiros.</span><span class="sxs-lookup"><span data-stu-id="b6b36-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="b6b36-140">Usar o aplicativo Serviços para verificar se o Microsoft Defender Antivírus está desligado</span><span class="sxs-lookup"><span data-stu-id="b6b36-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="b6b36-141">Para abrir o aplicativo Serviços, selecione o **ícone Pesquisar** na barra de tarefas e procure *por serviços.*</span><span class="sxs-lookup"><span data-stu-id="b6b36-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="b6b36-142">Você também pode abrir o aplicativo na linha de comando digitando *services.msc*.</span><span class="sxs-lookup"><span data-stu-id="b6b36-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="b6b36-143">As informações sobre o Microsoft Defender Antivírus serão listadas no aplicativo Serviços em **Windows Defender**  >  **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="b6b36-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="b6b36-144">O nome do serviço antivírus é *Windows Defender Antivírus.*</span><span class="sxs-lookup"><span data-stu-id="b6b36-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="b6b36-145">Ao verificar o aplicativo, você pode ver que o serviço antivírus do *Windows Defender* está definido como manual , mas quando você tenta iniciar esse serviço manualmente, você tem um aviso informando que o serviço de Serviço antivírus do Windows Defender no Computador Local foi iniciado e *interrompido. Alguns serviços param automaticamente se não estão em uso por outros serviços ou programas.*</span><span class="sxs-lookup"><span data-stu-id="b6b36-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="b6b36-146">Isso indica que o Microsoft Defender Antivírus foi automaticamente desligado para preservar a compatibilidade com um antivírus de terceiros.</span><span class="sxs-lookup"><span data-stu-id="b6b36-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="b6b36-147">Gerar um relatório detalhado</span><span class="sxs-lookup"><span data-stu-id="b6b36-147">Generate a detailed report</span></span>

<span data-ttu-id="b6b36-148">Você pode gerar um relatório detalhado sobre as políticas de  grupo ativas no momento abrindo um prompt de comando no modo de administração e inserindo o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b6b36-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="b6b36-149">Isso gerará um relatório localizado em *./gpresult.html*.</span><span class="sxs-lookup"><span data-stu-id="b6b36-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="b6b36-150">Abra este arquivo e você poderá ver os resultados a seguir, dependendo de como o Microsoft Defender Antivírus foi desligado.</span><span class="sxs-lookup"><span data-stu-id="b6b36-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="b6b36-151">Resultados da política de grupo</span><span class="sxs-lookup"><span data-stu-id="b6b36-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="b6b36-152">Se as configurações de segurança são implementadas por meio de política de grupo (GPO) no domínio ou no nível local, ou embora o System center configuration manager (SCCM)</span><span class="sxs-lookup"><span data-stu-id="b6b36-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="b6b36-153">No relatório GPResults, sob o título, Componentes do *Windows/Windows Defender Antivírus*, você pode ver algo como a entrada a seguir, indicando que o Microsoft Defender Antivírus está desligado.</span><span class="sxs-lookup"><span data-stu-id="b6b36-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="b6b36-154">Política</span><span class="sxs-lookup"><span data-stu-id="b6b36-154">Policy</span></span> | <span data-ttu-id="b6b36-155">Setting</span><span class="sxs-lookup"><span data-stu-id="b6b36-155">Setting</span></span> | <span data-ttu-id="b6b36-156">GpO vencedor</span><span class="sxs-lookup"><span data-stu-id="b6b36-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="b6b36-157">Desativar o Windows Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="b6b36-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="b6b36-158">Habilitado</span><span class="sxs-lookup"><span data-stu-id="b6b36-158">Enabled</span></span> | <span data-ttu-id="b6b36-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="b6b36-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="b6b36-160">Se as configurações de segurança são implementadas por meio da preferência de política de grupo (GPP)</span><span class="sxs-lookup"><span data-stu-id="b6b36-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="b6b36-161">Sob o título, item do Registro (Caminho da chave: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Nome do *valor: DisableAntiSpyware)*, você pode ver algo como a entrada a seguir, indicando que o Microsoft Defender Antivírus está desligado.</span><span class="sxs-lookup"><span data-stu-id="b6b36-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="b6b36-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="b6b36-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="b6b36-163">GpO vencedor</span><span class="sxs-lookup"><span data-stu-id="b6b36-163">Winning GPO</span></span> | <span data-ttu-id="b6b36-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="b6b36-164">Win10-Workstations</span></span>
<span data-ttu-id="b6b36-165">Resultado: Sucesso</span><span class="sxs-lookup"><span data-stu-id="b6b36-165">Result: Success</span></span> | 
<span data-ttu-id="b6b36-166">**Geral**</span><span class="sxs-lookup"><span data-stu-id="b6b36-166">**General**</span></span> | 
<span data-ttu-id="b6b36-167">Action</span><span class="sxs-lookup"><span data-stu-id="b6b36-167">Action</span></span> | <span data-ttu-id="b6b36-168">Atualizar</span><span class="sxs-lookup"><span data-stu-id="b6b36-168">Update</span></span>
<span data-ttu-id="b6b36-169">**Properties**</span><span class="sxs-lookup"><span data-stu-id="b6b36-169">**Properties**</span></span> | 
<span data-ttu-id="b6b36-170">Hive</span><span class="sxs-lookup"><span data-stu-id="b6b36-170">Hive</span></span> | <span data-ttu-id="b6b36-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="b6b36-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="b6b36-172">Caminho da chave</span><span class="sxs-lookup"><span data-stu-id="b6b36-172">Key path</span></span> | <span data-ttu-id="b6b36-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="b6b36-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="b6b36-174">Nome do valor </span><span class="sxs-lookup"><span data-stu-id="b6b36-174">Value name</span></span> | <span data-ttu-id="b6b36-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="b6b36-175">DisableAntiSpyware</span></span>
<span data-ttu-id="b6b36-176">Tipo do valor</span><span class="sxs-lookup"><span data-stu-id="b6b36-176">Value type</span></span> | <span data-ttu-id="b6b36-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="b6b36-177">REG_DWORD</span></span>
<span data-ttu-id="b6b36-178">Dados de valor</span><span class="sxs-lookup"><span data-stu-id="b6b36-178">Value data</span></span> | <span data-ttu-id="b6b36-179">0x1 (1)</span><span class="sxs-lookup"><span data-stu-id="b6b36-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="b6b36-180">Se as configurações de segurança são implementadas por meio da chave do Registro</span><span class="sxs-lookup"><span data-stu-id="b6b36-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="b6b36-181">O relatório pode conter o seguinte texto, indicando que o Microsoft Defender Antivírus está desligado:</span><span class="sxs-lookup"><span data-stu-id="b6b36-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="b6b36-182">Registro (regedit.exe)</span><span class="sxs-lookup"><span data-stu-id="b6b36-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="b6b36-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span><span class="sxs-lookup"><span data-stu-id="b6b36-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="b6b36-184">Se as configurações de segurança são definidas no Windows ou na imagem do Windows Server</span><span class="sxs-lookup"><span data-stu-id="b6b36-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="b6b36-185">Seu administrador imaginário pode ter definido a política de segurança, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, localmente por *GPEdit.exe*, *LGPO.exe*, ou modificando o Registro em sua sequência de tarefas.</span><span class="sxs-lookup"><span data-stu-id="b6b36-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="b6b36-186">Você pode [configurar um Identificador de Imagem Confiável](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) para o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="b6b36-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="b6b36-187">Ativar novamente o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="b6b36-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="b6b36-188">O Microsoft Defender Antivírus será ativado automaticamente se nenhum outro antivírus estiver ativo no momento.</span><span class="sxs-lookup"><span data-stu-id="b6b36-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="b6b36-189">Você precisará desativar completamente o antivírus de terceiros para garantir que o Microsoft Defender Antivírus possa ser executado com funcionalidade completa.</span><span class="sxs-lookup"><span data-stu-id="b6b36-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="b6b36-190">As soluções sugerindo  que você edite os valores de início do Windows Defender para *wdboot,* *wdfilter,* *wdnisdrv,* *wdnissvc* e *windefend* no HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services não são compatíveis e podem forçar você a fazer uma nova imagem do sistema.</span><span class="sxs-lookup"><span data-stu-id="b6b36-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="b6b36-191">O modo passivo estará disponível se você começar a usar o Microsoft Defender para Ponto de Extremidade e um antivírus de terceiros juntamente com o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="b6b36-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b6b36-192">O modo passivo permite que o Microsoft Defender digitalize arquivos e se atualize, mas não correção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="b6b36-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="b6b36-193">Além disso, o monitoramento de comportamento por meio da Proteção em Tempo [Real](configure-real-time-protection-microsoft-defender-antivirus.md) não está disponível no modo passivo, a menos que a prevenção contra perda de dados do Ponto de Extremidade [(DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) seja implantada.</span><span class="sxs-lookup"><span data-stu-id="b6b36-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="b6b36-194">Outro recurso, conhecido como [verificação periódica limitada,](limited-periodic-scanning-microsoft-defender-antivirus.md)está disponível para os usuários finais quando o Microsoft Defender Antivírus é definido para desativar automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b6b36-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="b6b36-195">Esse recurso permite que o Microsoft Defender Antivírus digitalizar arquivos periodicamente juntamente com um antivírus de terceiros, usando um número limitado de detecções.</span><span class="sxs-lookup"><span data-stu-id="b6b36-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6b36-196">A verificação periódica limitada não é recomendada em ambientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="b6b36-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="b6b36-197">Os recursos de detecção, gerenciamento e relatório disponíveis ao executar o Microsoft Defender Antivírus neste modo são reduzidos em comparação ao modo ativo.</span><span class="sxs-lookup"><span data-stu-id="b6b36-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="b6b36-198">Confira também</span><span class="sxs-lookup"><span data-stu-id="b6b36-198">See also</span></span>

* [<span data-ttu-id="b6b36-199">Compatibilidade com o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="b6b36-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="b6b36-200">Microsoft Defender Antivírus no aplicativo segurança do Windows</span><span class="sxs-lookup"><span data-stu-id="b6b36-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)