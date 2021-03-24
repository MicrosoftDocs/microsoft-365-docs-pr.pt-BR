---
title: Microsoft Defender ATP para recursos Linux
ms.reviewer: ''
description: Descreve os recursos do Microsoft Defender ATP para Linux, incluindo como desinstalar, como coletar logs de diagnóstico, comandos CLI e problemas conhecidos com o produto.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 08dd8a3ff5f0b55d7fec8decd41f1120ca05077a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053776"
---
# <a name="resources"></a><span data-ttu-id="25e11-104">Recursos</span><span class="sxs-lookup"><span data-stu-id="25e11-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="25e11-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="25e11-105">**Applies to:**</span></span>
- [<span data-ttu-id="25e11-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="25e11-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="25e11-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25e11-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="25e11-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="25e11-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="25e11-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="25e11-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="25e11-110">Coletar informações de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="25e11-110">Collect diagnostic information</span></span>

<span data-ttu-id="25e11-111">Se você puder reproduzir um problema, primeiro aumente o nível de registro em log, execute o sistema por algum tempo e restaure o nível de registro em log como padrão.</span><span class="sxs-lookup"><span data-stu-id="25e11-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="25e11-112">Aumentar o nível de registro em log:</span><span class="sxs-lookup"><span data-stu-id="25e11-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="25e11-113">Reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="25e11-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="25e11-114">Execute o seguinte comando para fazer o back-up do Defender para logs do Endpoint.</span><span class="sxs-lookup"><span data-stu-id="25e11-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="25e11-115">Os arquivos serão armazenados dentro de um arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="25e11-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="25e11-116">Esse comando também imprimirá o caminho do arquivo para o backup depois que a operação for bem-sucedida:</span><span class="sxs-lookup"><span data-stu-id="25e11-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="25e11-117">Restaurar o nível de registro em log:</span><span class="sxs-lookup"><span data-stu-id="25e11-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="25e11-118">Problemas de instalação de log</span><span class="sxs-lookup"><span data-stu-id="25e11-118">Log installation issues</span></span>

<span data-ttu-id="25e11-119">Se ocorrer um erro durante a instalação, o instalador relatará apenas uma falha geral.</span><span class="sxs-lookup"><span data-stu-id="25e11-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="25e11-120">O log detalhado será salvo em `/var/log/microsoft/mdatp_install.log` .</span><span class="sxs-lookup"><span data-stu-id="25e11-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="25e11-121">Se você tiver problemas durante a instalação, envie-nos esse arquivo para que possamos ajudar a diagnosticar a causa.</span><span class="sxs-lookup"><span data-stu-id="25e11-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="25e11-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="25e11-122">Uninstall</span></span>

<span data-ttu-id="25e11-123">Há várias maneiras de desinstalar o Defender para o Ponto de Extremidade para Linux.</span><span class="sxs-lookup"><span data-stu-id="25e11-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="25e11-124">Se você estiver usando uma ferramenta de configuração como o Puppet, siga as instruções de desinstalação do pacote para a ferramenta de configuração.</span><span class="sxs-lookup"><span data-stu-id="25e11-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="25e11-125">Desinstalação manual</span><span class="sxs-lookup"><span data-stu-id="25e11-125">Manual uninstallation</span></span>

- <span data-ttu-id="25e11-126">`sudo yum remove mdatp` para o RHEL e variantes(CentOS e Oracle Linux).</span><span class="sxs-lookup"><span data-stu-id="25e11-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="25e11-127">`sudo zypper remove mdatp` para SLES e variantes.</span><span class="sxs-lookup"><span data-stu-id="25e11-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="25e11-128">`sudo apt-get purge mdatp` para sistemas Ubuntu e Debian.</span><span class="sxs-lookup"><span data-stu-id="25e11-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="25e11-129">Configurar a partir da linha de comando</span><span class="sxs-lookup"><span data-stu-id="25e11-129">Configure from the command line</span></span>

<span data-ttu-id="25e11-130">Tarefas importantes, como controlar as configurações do produto e disparar verificações sob demanda, podem ser feitas a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="25e11-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="25e11-131">Opções globais</span><span class="sxs-lookup"><span data-stu-id="25e11-131">Global options</span></span>

<span data-ttu-id="25e11-132">Por padrão, a ferramenta de linha de comando resulta no formato aceitável para humanos.</span><span class="sxs-lookup"><span data-stu-id="25e11-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="25e11-133">Além disso, a ferramenta também dá suporte à saída do resultado como JSON, que é útil para cenários de automação.</span><span class="sxs-lookup"><span data-stu-id="25e11-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="25e11-134">Para alterar a saída para JSON, passe `--output json` para qualquer um dos comandos abaixo.</span><span class="sxs-lookup"><span data-stu-id="25e11-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="25e11-135">Comandos com suporte</span><span class="sxs-lookup"><span data-stu-id="25e11-135">Supported commands</span></span>

<span data-ttu-id="25e11-136">A tabela a seguir lista comandos para alguns dos cenários mais comuns.</span><span class="sxs-lookup"><span data-stu-id="25e11-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="25e11-137">Execute `mdatp help` a partir do Terminal para exibir a lista completa de comandos com suporte.</span><span class="sxs-lookup"><span data-stu-id="25e11-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="25e11-138">Grupo</span><span class="sxs-lookup"><span data-stu-id="25e11-138">Group</span></span>                 |<span data-ttu-id="25e11-139">Cenário</span><span class="sxs-lookup"><span data-stu-id="25e11-139">Scenario</span></span>                                                |<span data-ttu-id="25e11-140">Comando</span><span class="sxs-lookup"><span data-stu-id="25e11-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="25e11-141">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-141">Configuration</span></span>         |<span data-ttu-id="25e11-142">Ativar/desativar a proteção em tempo real</span><span class="sxs-lookup"><span data-stu-id="25e11-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="25e11-143">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-143">Configuration</span></span>         |<span data-ttu-id="25e11-144">Ativar/desativar a proteção de nuvem</span><span class="sxs-lookup"><span data-stu-id="25e11-144">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="25e11-145">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-145">Configuration</span></span>         |<span data-ttu-id="25e11-146">Ativar/desativar diagnósticos de produto</span><span class="sxs-lookup"><span data-stu-id="25e11-146">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="25e11-147">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-147">Configuration</span></span>         |<span data-ttu-id="25e11-148">Ativar/desativar envio automático de exemplo</span><span class="sxs-lookup"><span data-stu-id="25e11-148">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="25e11-149">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-149">Configuration</span></span>         |<span data-ttu-id="25e11-150">Ativar/desativar o modo passivo AV</span><span class="sxs-lookup"><span data-stu-id="25e11-150">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="25e11-151">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-151">Configuration</span></span>         |<span data-ttu-id="25e11-152">Adicionar/remover uma exclusão de antivírus para uma extensão de arquivo</span><span class="sxs-lookup"><span data-stu-id="25e11-152">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="25e11-153">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-153">Configuration</span></span>         |<span data-ttu-id="25e11-154">Adicionar/remover uma exclusão de antivírus para um arquivo</span><span class="sxs-lookup"><span data-stu-id="25e11-154">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="25e11-155">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-155">Configuration</span></span>         |<span data-ttu-id="25e11-156">Adicionar/remover uma exclusão de antivírus para um diretório</span><span class="sxs-lookup"><span data-stu-id="25e11-156">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="25e11-157">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-157">Configuration</span></span>         |<span data-ttu-id="25e11-158">Adicionar/remover uma exclusão de antivírus para um processo</span><span class="sxs-lookup"><span data-stu-id="25e11-158">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="25e11-159">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-159">Configuration</span></span>         |<span data-ttu-id="25e11-160">Listar todas as exclusões de antivírus</span><span class="sxs-lookup"><span data-stu-id="25e11-160">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="25e11-161">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-161">Configuration</span></span>         |<span data-ttu-id="25e11-162">Adicionar um nome de ameaça à lista permitida</span><span class="sxs-lookup"><span data-stu-id="25e11-162">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="25e11-163">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-163">Configuration</span></span>         |<span data-ttu-id="25e11-164">Remover um nome de ameaça da lista permitida</span><span class="sxs-lookup"><span data-stu-id="25e11-164">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="25e11-165">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-165">Configuration</span></span>         |<span data-ttu-id="25e11-166">Listar todos os nomes de ameaça permitidos</span><span class="sxs-lookup"><span data-stu-id="25e11-166">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="25e11-167">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-167">Configuration</span></span>         |<span data-ttu-id="25e11-168">Ativar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="25e11-168">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="25e11-169">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-169">Configuration</span></span>         |<span data-ttu-id="25e11-170">Desativar a proteção PUA</span><span class="sxs-lookup"><span data-stu-id="25e11-170">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="25e11-171">Configuração</span><span class="sxs-lookup"><span data-stu-id="25e11-171">Configuration</span></span>         |<span data-ttu-id="25e11-172">Ativar o modo de auditoria para proteção pua</span><span class="sxs-lookup"><span data-stu-id="25e11-172">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="25e11-173">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="25e11-173">Diagnostics</span></span>           |<span data-ttu-id="25e11-174">Alterar o nível de log</span><span class="sxs-lookup"><span data-stu-id="25e11-174">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="25e11-175">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="25e11-175">Diagnostics</span></span>           |<span data-ttu-id="25e11-176">Gerar logs de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="25e11-176">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="25e11-177">Integridade</span><span class="sxs-lookup"><span data-stu-id="25e11-177">Health</span></span>                |<span data-ttu-id="25e11-178">Verificar a saúde do produto</span><span class="sxs-lookup"><span data-stu-id="25e11-178">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="25e11-179">Proteção</span><span class="sxs-lookup"><span data-stu-id="25e11-179">Protection</span></span>            |<span data-ttu-id="25e11-180">Examinar um caminho</span><span class="sxs-lookup"><span data-stu-id="25e11-180">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="25e11-181">Proteção</span><span class="sxs-lookup"><span data-stu-id="25e11-181">Protection</span></span>            |<span data-ttu-id="25e11-182">Fazer uma verificação rápida</span><span class="sxs-lookup"><span data-stu-id="25e11-182">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="25e11-183">Proteção</span><span class="sxs-lookup"><span data-stu-id="25e11-183">Protection</span></span>            |<span data-ttu-id="25e11-184">Fazer uma verificação completa</span><span class="sxs-lookup"><span data-stu-id="25e11-184">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="25e11-185">Proteção</span><span class="sxs-lookup"><span data-stu-id="25e11-185">Protection</span></span>            |<span data-ttu-id="25e11-186">Cancelar uma verificação contínua sob demanda</span><span class="sxs-lookup"><span data-stu-id="25e11-186">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="25e11-187">Proteção</span><span class="sxs-lookup"><span data-stu-id="25e11-187">Protection</span></span>            |<span data-ttu-id="25e11-188">Solicitar uma atualização de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="25e11-188">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="25e11-189">Histórico de proteção</span><span class="sxs-lookup"><span data-stu-id="25e11-189">Protection history</span></span>    |<span data-ttu-id="25e11-190">Imprimir o histórico de proteção completo</span><span class="sxs-lookup"><span data-stu-id="25e11-190">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="25e11-191">Histórico de proteção</span><span class="sxs-lookup"><span data-stu-id="25e11-191">Protection history</span></span>    |<span data-ttu-id="25e11-192">Obter detalhes da ameaça</span><span class="sxs-lookup"><span data-stu-id="25e11-192">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="25e11-193">Gerenciamento de quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-193">Quarantine management</span></span> |<span data-ttu-id="25e11-194">Listar todos os arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-194">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="25e11-195">Gerenciamento de quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-195">Quarantine management</span></span> |<span data-ttu-id="25e11-196">Remover todos os arquivos da quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-196">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="25e11-197">Gerenciamento de quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-197">Quarantine management</span></span> |<span data-ttu-id="25e11-198">Adicionar um arquivo detectado como uma ameaça à quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-198">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="25e11-199">Gerenciamento de quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-199">Quarantine management</span></span> |<span data-ttu-id="25e11-200">Remover um arquivo detectado como uma ameaça da quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-200">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="25e11-201">Gerenciamento de quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-201">Quarantine management</span></span> |<span data-ttu-id="25e11-202">Restaurar um arquivo da quarentena</span><span class="sxs-lookup"><span data-stu-id="25e11-202">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="25e11-203">Detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="25e11-203">Endpoint Detection and Response</span></span> |<span data-ttu-id="25e11-204">Definir visualização antecipada (nãousada)</span><span class="sxs-lookup"><span data-stu-id="25e11-204">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="25e11-205">Detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="25e11-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="25e11-206">Definir id de grupo</span><span class="sxs-lookup"><span data-stu-id="25e11-206">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="25e11-207">Detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="25e11-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="25e11-208">Marca Set/Remove, com `GROUP` suporte apenas</span><span class="sxs-lookup"><span data-stu-id="25e11-208">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="25e11-209">Detecção e resposta do ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="25e11-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="25e11-210">exclusões de lista (raiz)</span><span class="sxs-lookup"><span data-stu-id="25e11-210">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="25e11-211">Informações do portal do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="25e11-211">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="25e11-212">No portal Defender para Ponto de Extremidade, você verá duas categorias de informações:</span><span class="sxs-lookup"><span data-stu-id="25e11-212">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="25e11-213">Alertas antivírus, incluindo:</span><span class="sxs-lookup"><span data-stu-id="25e11-213">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="25e11-214">Severity</span><span class="sxs-lookup"><span data-stu-id="25e11-214">Severity</span></span>
  - <span data-ttu-id="25e11-215">Tipo de verificação</span><span class="sxs-lookup"><span data-stu-id="25e11-215">Scan type</span></span>
  - <span data-ttu-id="25e11-216">Informações do dispositivo (nome do host, identificador de dispositivo, identificador de locatário, versão do aplicativo e tipo de sistema operacional)</span><span class="sxs-lookup"><span data-stu-id="25e11-216">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="25e11-217">Informações do arquivo (nome, caminho, tamanho e hash)</span><span class="sxs-lookup"><span data-stu-id="25e11-217">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="25e11-218">Informações sobre ameaças (nome, tipo e estado)</span><span class="sxs-lookup"><span data-stu-id="25e11-218">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="25e11-219">Informações do dispositivo, incluindo:</span><span class="sxs-lookup"><span data-stu-id="25e11-219">Device information, including:</span></span>
  - <span data-ttu-id="25e11-220">Identificador de dispositivo</span><span class="sxs-lookup"><span data-stu-id="25e11-220">Device identifier</span></span>
  - <span data-ttu-id="25e11-221">Identificador de locatário</span><span class="sxs-lookup"><span data-stu-id="25e11-221">Tenant identifier</span></span>
  - <span data-ttu-id="25e11-222">Versão do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="25e11-222">App version</span></span>
  - <span data-ttu-id="25e11-223">Nome do host</span><span class="sxs-lookup"><span data-stu-id="25e11-223">Hostname</span></span>
  - <span data-ttu-id="25e11-224">Tipo de sistema operacional</span><span class="sxs-lookup"><span data-stu-id="25e11-224">OS type</span></span>
  - <span data-ttu-id="25e11-225">Versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="25e11-225">OS version</span></span>
  - <span data-ttu-id="25e11-226">Modelo de computador</span><span class="sxs-lookup"><span data-stu-id="25e11-226">Computer model</span></span>
  - <span data-ttu-id="25e11-227">Arquitetura do processador</span><span class="sxs-lookup"><span data-stu-id="25e11-227">Processor architecture</span></span>
  - <span data-ttu-id="25e11-228">Se o dispositivo é uma máquina virtual</span><span class="sxs-lookup"><span data-stu-id="25e11-228">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="25e11-229">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="25e11-229">Known issues</span></span>

- <span data-ttu-id="25e11-230">Você pode ver "Sem dados do sensor, comunicações prejudicadas" na página de informações do computador do portal do Centro de Segurança do Microsoft Defender, mesmo que o produto está funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="25e11-230">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="25e11-231">Estamos trabalhando para resolver esse problema.</span><span class="sxs-lookup"><span data-stu-id="25e11-231">We are working on addressing this issue.</span></span>
- <span data-ttu-id="25e11-232">Usuários conectados não aparecem no portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="25e11-232">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="25e11-233">Em distribuições SUSE, se a instalação de *liúndice1* falhar, você deve validar que seu sistema operacional está registrado:</span><span class="sxs-lookup"><span data-stu-id="25e11-233">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
