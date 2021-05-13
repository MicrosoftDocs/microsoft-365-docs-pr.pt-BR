---
title: Recursos para o Microsoft Defender para Ponto de Extremidade no Mac
description: Recursos para o Microsoft Defender para Ponto de Extremidade no Mac, incluindo como desinstalar, como coletar logs de diagnóstico, comandos CLI e problemas conhecidos com o produto.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 29e9eefdf85c80b6d3c44eba01d0df57be0193a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346385"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="b7107-104">Recursos para o Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="b7107-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b7107-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b7107-105">**Applies to:**</span></span>

- [<span data-ttu-id="b7107-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b7107-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b7107-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b7107-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b7107-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b7107-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b7107-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b7107-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="b7107-110">Coletando informações de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b7107-110">Collecting diagnostic information</span></span>

<span data-ttu-id="b7107-111">Se você puder reproduzir um problema, aumente o nível de registro em log, execute o sistema por algum tempo e restaure o nível de log para o padrão.</span><span class="sxs-lookup"><span data-stu-id="b7107-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="b7107-112">Aumentar o nível de registro em log:</span><span class="sxs-lookup"><span data-stu-id="b7107-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="b7107-113">Reproduzir o problema</span><span class="sxs-lookup"><span data-stu-id="b7107-113">Reproduce the problem</span></span>

3. <span data-ttu-id="b7107-114">Execute `sudo mdatp diagnostic create` para fazer o back up dos logs do Microsoft Defender para Pontos de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b7107-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="b7107-115">Os arquivos serão armazenados dentro de um arquivo .zip arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="b7107-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="b7107-116">Esse comando também imprimirá o caminho do arquivo para o backup depois que a operação for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b7107-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="b7107-117">Por padrão, os logs de diagnóstico são salvos em `/Library/Application Support/Microsoft/Defender/wdavdiag/` .</span><span class="sxs-lookup"><span data-stu-id="b7107-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="b7107-118">Para alterar o diretório onde os logs de diagnóstico são salvos, passe para o `--path [directory]` comando abaixo, substituindo `[directory]` pelo diretório desejado.</span><span class="sxs-lookup"><span data-stu-id="b7107-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="b7107-119">Restaurar o nível de registro em log:</span><span class="sxs-lookup"><span data-stu-id="b7107-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="b7107-120">Problemas de instalação de log</span><span class="sxs-lookup"><span data-stu-id="b7107-120">Logging installation issues</span></span>

<span data-ttu-id="b7107-121">Se ocorrer um erro durante a instalação, o instalador relatará apenas uma falha geral.</span><span class="sxs-lookup"><span data-stu-id="b7107-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="b7107-122">O log detalhado será salvo em `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="b7107-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="b7107-123">Se você tiver problemas durante a instalação, envie-nos esse arquivo para que possamos ajudar a diagnosticar a causa.</span><span class="sxs-lookup"><span data-stu-id="b7107-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="b7107-124">Desinstalação</span><span class="sxs-lookup"><span data-stu-id="b7107-124">Uninstalling</span></span>

<span data-ttu-id="b7107-125">Há várias maneiras de desinstalar o Microsoft Defender para o Ponto de Extremidade no macOS.</span><span class="sxs-lookup"><span data-stu-id="b7107-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="b7107-126">Observe que, embora a desinstalação gerenciada centralmente está disponível no JAMF, ela ainda não está disponível para Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="b7107-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="b7107-127">Desinstalação interativa</span><span class="sxs-lookup"><span data-stu-id="b7107-127">Interactive uninstallation</span></span>

- <span data-ttu-id="b7107-128">Abra **o Finder > Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b7107-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="b7107-129">Clique com o botão direito do **mouse no Microsoft Defender para Endpoint > Mover para Lixo**.</span><span class="sxs-lookup"><span data-stu-id="b7107-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="b7107-130">Da linha de comando</span><span class="sxs-lookup"><span data-stu-id="b7107-130">From the command line</span></span>

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="b7107-131">Configurando a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="b7107-131">Configuring from the command line</span></span>

<span data-ttu-id="b7107-132">Tarefas importantes, como controlar as configurações do produto e disparar verificações sob demanda, podem ser feitas a partir da linha de comando:</span><span class="sxs-lookup"><span data-stu-id="b7107-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="b7107-133">Grupo</span><span class="sxs-lookup"><span data-stu-id="b7107-133">Group</span></span>        |<span data-ttu-id="b7107-134">Cenário</span><span class="sxs-lookup"><span data-stu-id="b7107-134">Scenario</span></span>                                   |<span data-ttu-id="b7107-135">Comando</span><span class="sxs-lookup"><span data-stu-id="b7107-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="b7107-136">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-136">Configuration</span></span>|<span data-ttu-id="b7107-137">Ativar/desativar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="b7107-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="b7107-138">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-138">Configuration</span></span>|<span data-ttu-id="b7107-139">Ativar/desativar a proteção de nuvem</span><span class="sxs-lookup"><span data-stu-id="b7107-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="b7107-140">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-140">Configuration</span></span>|<span data-ttu-id="b7107-141">Ativar/desativar diagnósticos de produto</span><span class="sxs-lookup"><span data-stu-id="b7107-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="b7107-142">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-142">Configuration</span></span>|<span data-ttu-id="b7107-143">Ativar/desativar envio automático de exemplo</span><span class="sxs-lookup"><span data-stu-id="b7107-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="b7107-144">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-144">Configuration</span></span>|<span data-ttu-id="b7107-145">Adicionar um nome de ameaça à lista permitida</span><span class="sxs-lookup"><span data-stu-id="b7107-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="b7107-146">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-146">Configuration</span></span>|<span data-ttu-id="b7107-147">Remover um nome de ameaça da lista permitida</span><span class="sxs-lookup"><span data-stu-id="b7107-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="b7107-148">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-148">Configuration</span></span>|<span data-ttu-id="b7107-149">Listar todos os nomes de ameaça permitidos</span><span class="sxs-lookup"><span data-stu-id="b7107-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="b7107-150">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-150">Configuration</span></span>|<span data-ttu-id="b7107-151">Ativar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="b7107-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="b7107-152">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-152">Configuration</span></span>|<span data-ttu-id="b7107-153">Desativar a proteção PUA</span><span class="sxs-lookup"><span data-stu-id="b7107-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="b7107-154">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-154">Configuration</span></span>|<span data-ttu-id="b7107-155">Ativar o modo de auditoria para proteção pua</span><span class="sxs-lookup"><span data-stu-id="b7107-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="b7107-156">Configuração</span><span class="sxs-lookup"><span data-stu-id="b7107-156">Configuration</span></span>|<span data-ttu-id="b7107-157">Ativar/desativar passiveMode</span><span class="sxs-lookup"><span data-stu-id="b7107-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="b7107-158">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="b7107-158">Diagnostics</span></span>  |<span data-ttu-id="b7107-159">Alterar o nível de log</span><span class="sxs-lookup"><span data-stu-id="b7107-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="b7107-160">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="b7107-160">Diagnostics</span></span>  |<span data-ttu-id="b7107-161">Gerar logs de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="b7107-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="b7107-162">Integridade</span><span class="sxs-lookup"><span data-stu-id="b7107-162">Health</span></span>       |<span data-ttu-id="b7107-163">Verificar a saúde do produto</span><span class="sxs-lookup"><span data-stu-id="b7107-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="b7107-164">Integridade</span><span class="sxs-lookup"><span data-stu-id="b7107-164">Health</span></span>       |<span data-ttu-id="b7107-165">Verifique se há um atributo de produto esefico</span><span class="sxs-lookup"><span data-stu-id="b7107-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="b7107-166">Proteção</span><span class="sxs-lookup"><span data-stu-id="b7107-166">Protection</span></span>   |<span data-ttu-id="b7107-167">Examinar um caminho</span><span class="sxs-lookup"><span data-stu-id="b7107-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="b7107-168">Proteção</span><span class="sxs-lookup"><span data-stu-id="b7107-168">Protection</span></span>   |<span data-ttu-id="b7107-169">Fazer uma verificação rápida</span><span class="sxs-lookup"><span data-stu-id="b7107-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="b7107-170">Proteção</span><span class="sxs-lookup"><span data-stu-id="b7107-170">Protection</span></span>   |<span data-ttu-id="b7107-171">Fazer uma verificação completa</span><span class="sxs-lookup"><span data-stu-id="b7107-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="b7107-172">Proteção</span><span class="sxs-lookup"><span data-stu-id="b7107-172">Protection</span></span>   |<span data-ttu-id="b7107-173">Cancelar uma verificação contínua sob demanda</span><span class="sxs-lookup"><span data-stu-id="b7107-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="b7107-174">Proteção</span><span class="sxs-lookup"><span data-stu-id="b7107-174">Protection</span></span>   |<span data-ttu-id="b7107-175">Solicitar uma atualização de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="b7107-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="b7107-176">EDR</span><span class="sxs-lookup"><span data-stu-id="b7107-176">EDR</span></span>          |<span data-ttu-id="b7107-177">Adicione a marca de grupo ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7107-177">Add group tag to device.</span></span> <span data-ttu-id="b7107-178">EDR marcas são usadas para gerenciar grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b7107-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="b7107-179">Para obter mais informações, visite https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="b7107-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="b7107-180">EDR</span><span class="sxs-lookup"><span data-stu-id="b7107-180">EDR</span></span>          |<span data-ttu-id="b7107-181">Remover a marca de grupo do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7107-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="b7107-182">EDR</span><span class="sxs-lookup"><span data-stu-id="b7107-182">EDR</span></span>          |<span data-ttu-id="b7107-183">Adicionar ID de Grupo</span><span class="sxs-lookup"><span data-stu-id="b7107-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="b7107-184">Como habilitar a comcompleção automática</span><span class="sxs-lookup"><span data-stu-id="b7107-184">How to enable autocompletion</span></span>

<span data-ttu-id="b7107-185">Para habilitar a comcompleção automática em bash, execute o seguinte comando e reinicie a sessão terminal:</span><span class="sxs-lookup"><span data-stu-id="b7107-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="b7107-186">Para habilitar a comcompleção automática em zsh:</span><span class="sxs-lookup"><span data-stu-id="b7107-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="b7107-187">Verifique se a comcompleção automática está habilitada em seu dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b7107-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="b7107-188">Se o comando anterior não produzir nenhuma saída, você poderá habilitar a comcompleção automática usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b7107-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="b7107-189">Execute os seguintes comandos para habilitar a composição automática do Microsoft Defender para Ponto de Extremidade no macOS e reinicie a sessão terminal:</span><span class="sxs-lookup"><span data-stu-id="b7107-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="b7107-190">Diretório de quarentena do Microsoft Defender para Ponto de Extremidade cliente</span><span class="sxs-lookup"><span data-stu-id="b7107-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="b7107-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contém os arquivos em quarentena por `mdatp` .</span><span class="sxs-lookup"><span data-stu-id="b7107-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="b7107-192">Os arquivos são nomeados após o trackingId de ameaças.</span><span class="sxs-lookup"><span data-stu-id="b7107-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="b7107-193">Os trackingIds atuais são mostrados com `mdatp threat list` .</span><span class="sxs-lookup"><span data-stu-id="b7107-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="b7107-194">Informações do portal do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b7107-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="b7107-195">EDR recursos para [macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)chegaram , no blog do Microsoft Defender para Ponto de Extremidade, fornece orientações detalhadas sobre o que esperar no Centro de Segurança do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b7107-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
