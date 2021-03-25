---
title: Novidades no Microsoft Defender para Ponto de Extremidade para Mac
description: Saiba mais sobre as principais alterações para versões anteriores do Microsoft Defender para Ponto de Extremidade para Mac.
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: be906baca3a54183e22fa3b4ee424a9d8fc6957a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198688"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="344ec-104">Novidades no Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="344ec-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="344ec-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="344ec-105">**Applies to:**</span></span>
- [<span data-ttu-id="344ec-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="344ec-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="344ec-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="344ec-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="344ec-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="344ec-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="344ec-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="344ec-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="344ec-110">No macOS 11 (Big Sur), o Microsoft Defender para Endpoint requer perfis de configuração adicionais.</span><span class="sxs-lookup"><span data-stu-id="344ec-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="344ec-111">Se você for um cliente existente atualizando de versões anteriores do macOS, certifique-se de implantar os perfis de configuração adicionais listados [nesta página](mac-sysext-policies.md).</span><span class="sxs-lookup"><span data-stu-id="344ec-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="344ec-112">O suporte para macOS 10.13 (High Sierra) será descontinuado em 15 de fevereiro de 2021.</span><span class="sxs-lookup"><span data-stu-id="344ec-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="344ec-113">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="344ec-113">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="344ec-114">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-114">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="344ec-115">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="344ec-115">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="344ec-116">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-116">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="344ec-117">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="344ec-117">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="344ec-118">A sintaxe da ferramenta de linha de comando antiga foi preterida com essa versão.</span><span class="sxs-lookup"><span data-stu-id="344ec-118">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="344ec-119">Para obter informações sobre a nova sintaxe, consulte [Resources](mac-resources.md#configuring-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="344ec-119">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="344ec-120">Adicionada uma nova opção de linha de comando para desabilitar a extensão de rede: `mdatp system-extension network-filter disable` .</span><span class="sxs-lookup"><span data-stu-id="344ec-120">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="344ec-121">Esse comando pode ser útil para solucionar problemas de rede que podem estar relacionados ao Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="344ec-121">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="344ec-122">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-122">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="344ec-123">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="344ec-123">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="344ec-124">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-124">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="344ec-125">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="344ec-125">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="344ec-126">Melhorou a confiabilidade do agente ao executar no macOS 11 Big Sur</span><span class="sxs-lookup"><span data-stu-id="344ec-126">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="344ec-127">Adicionada uma nova opção de linha de comando ( `--ignore-exclusions` ) para ignorar exclusões av durante verificações personalizadas ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="344ec-127">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="344ec-128">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-128">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="344ec-129">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="344ec-129">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="344ec-130">Condições removidas quando o Microsoft Defender for Endpoint estava disparando um bug do macOS 11 (Big Sur) que se manifestou em um pânico do kernel</span><span class="sxs-lookup"><span data-stu-id="344ec-130">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="344ec-131">Correção de um vazamento de memória na extensão do sistema de Segurança do Ponto de Extremidade ao ser executado no mac 11 (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="344ec-131">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="344ec-132">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-132">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="344ec-133">101.10.72</span><span class="sxs-lookup"><span data-stu-id="344ec-133">101.10.72</span></span>

- <span data-ttu-id="344ec-134">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-134">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="344ec-135">101.09.61</span><span class="sxs-lookup"><span data-stu-id="344ec-135">101.09.61</span></span>

- <span data-ttu-id="344ec-136">Adicionada uma nova preferência gerenciada [para desabilitar a opção de enviar comentários](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="344ec-136">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="344ec-137">O ícone do menu Status agora mostra um estado ável quando as configurações do produto são gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="344ec-137">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="344ec-138">Anteriormente, o ícone do menu de status exibia um estado de aviso ou erro, mesmo que as configurações do produto fossem gerenciadas pelo administrador</span><span class="sxs-lookup"><span data-stu-id="344ec-138">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="344ec-139">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-139">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="344ec-140">101.09.50</span><span class="sxs-lookup"><span data-stu-id="344ec-140">101.09.50</span></span>

- <span data-ttu-id="344ec-141">Esta versão do produto foi validada no macOS Big Sur 11 beta 9</span><span class="sxs-lookup"><span data-stu-id="344ec-141">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="344ec-142">A nova sintaxe da ferramenta `mdatp` de linha de comando agora é a padrão.</span><span class="sxs-lookup"><span data-stu-id="344ec-142">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="344ec-143">Para obter mais informações sobre a nova sintaxe, consulte [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="344ec-143">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="344ec-144">A sintaxe da ferramenta de linha de comando antiga será removida do produto em 1º de janeiro de **2021**.</span><span class="sxs-lookup"><span data-stu-id="344ec-144">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="344ec-145">Estendido com um novo parâmetro ( ) que permite que os logs de `mdatp diagnostic create` diagnóstico sejam salvos em um diretório `--path [directory]` diferente</span><span class="sxs-lookup"><span data-stu-id="344ec-145">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="344ec-146">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-146">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="344ec-147">101.09.49</span><span class="sxs-lookup"><span data-stu-id="344ec-147">101.09.49</span></span>

- <span data-ttu-id="344ec-148">Melhorias na interface do usuário para diferenciar exclusões gerenciadas pelo administrador de IT versus exclusões definidas pelo usuário local</span><span class="sxs-lookup"><span data-stu-id="344ec-148">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="344ec-149">Utilização aprimorada da CPU durante verificações sob demanda</span><span class="sxs-lookup"><span data-stu-id="344ec-149">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="344ec-150">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-150">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="344ec-151">101.07.23</span><span class="sxs-lookup"><span data-stu-id="344ec-151">101.07.23</span></span>

- <span data-ttu-id="344ec-152">Adicionados novos campos à saída de para verificar o status do modo passivo e a `mdatp --health` ID do grupo EDR</span><span class="sxs-lookup"><span data-stu-id="344ec-152">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="344ec-153">`mdatp --health` será substituído por em `mdatp health` uma atualização futura do produto.</span><span class="sxs-lookup"><span data-stu-id="344ec-153">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="344ec-154">Correção de um bug em que o envio automático de amostra não foi marcado como gerenciado na interface do usuário</span><span class="sxs-lookup"><span data-stu-id="344ec-154">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="344ec-155">Adicionadas novas configurações para controlar a retenção de itens no histórico de verificação de antivírus.</span><span class="sxs-lookup"><span data-stu-id="344ec-155">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="344ec-156">Agora você pode [especificar o número de dias para reter](mac-preferences.md#antivirus-scan-history-retention-in-days) itens no histórico de verificação e especificar o número máximo de itens no histórico de [verificação](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="344ec-156">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="344ec-157">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-157">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="344ec-158">101.06.63</span><span class="sxs-lookup"><span data-stu-id="344ec-158">101.06.63</span></span>

- <span data-ttu-id="344ec-159">Abordamos uma regressão de desempenho introduzida na versão `101.05.17` .</span><span class="sxs-lookup"><span data-stu-id="344ec-159">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="344ec-160">A regressão foi introduzida com a correção para eliminar os problemas de kernel que alguns clientes observaram ao acessar compartilhamentos SMB.</span><span class="sxs-lookup"><span data-stu-id="344ec-160">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="344ec-161">Revertemos essa alteração de código e estamos investigando maneiras alternativas de eliminar os pânicos do kernel.</span><span class="sxs-lookup"><span data-stu-id="344ec-161">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="344ec-162">101.05.17</span><span class="sxs-lookup"><span data-stu-id="344ec-162">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="344ec-163">Estamos trabalhando em uma sintaxe nova e aprimorada para a `mdatp` ferramenta de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="344ec-163">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="344ec-164">A nova sintaxe é atualmente o padrão nos canais de atualização Insider Fast e Insider Slow.</span><span class="sxs-lookup"><span data-stu-id="344ec-164">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="344ec-165">Recomendamos que você famliliarize a si mesmo com essa nova sintaxe.</span><span class="sxs-lookup"><span data-stu-id="344ec-165">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="344ec-166">Continuaremos dando suporte à sintaxe antiga em paralelo com a nova sintaxe e forneceremos mais comunicação em torno do plano de prevaleção para a sintaxe antiga nos próximos meses.</span><span class="sxs-lookup"><span data-stu-id="344ec-166">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="344ec-167">Resolvido um pânico do kernel que ocorreu às vezes ao acessar compartilhamentos de arquivos SMB</span><span class="sxs-lookup"><span data-stu-id="344ec-167">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="344ec-168">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-168">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="344ec-169">101.05.16</span><span class="sxs-lookup"><span data-stu-id="344ec-169">101.05.16</span></span>

- <span data-ttu-id="344ec-170">Melhorias na lógica de verificação rápida para reduzir significativamente o número de arquivos verificados</span><span class="sxs-lookup"><span data-stu-id="344ec-170">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="344ec-171">Adicionado [suporte de autocompleção](mac-resources.md#how-to-enable-autocompletion) para a ferramenta de linha de comando</span><span class="sxs-lookup"><span data-stu-id="344ec-171">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="344ec-172">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-172">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="344ec-173">101.03.12</span><span class="sxs-lookup"><span data-stu-id="344ec-173">101.03.12</span></span>

- <span data-ttu-id="344ec-174">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-174">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="344ec-175">101.01.54</span><span class="sxs-lookup"><span data-stu-id="344ec-175">101.01.54</span></span>

- <span data-ttu-id="344ec-176">Melhorias em relação à compatibilidade com o Time Machine</span><span class="sxs-lookup"><span data-stu-id="344ec-176">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="344ec-177">Melhorias de acessibilidade</span><span class="sxs-lookup"><span data-stu-id="344ec-177">Accessibility improvements</span></span>
- <span data-ttu-id="344ec-178">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-178">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="344ec-179">101.00.31</span><span class="sxs-lookup"><span data-stu-id="344ec-179">101.00.31</span></span>

- <span data-ttu-id="344ec-180">Experiência [aprimorada de integração de produtos para usuários do Intune](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="344ec-180">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="344ec-181">As [exclusões de antivírus agora suportam curingas](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="344ec-181">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="344ec-182">Adicionada a capacidade de disparar verificações antivírus do menu contextual do macOS.</span><span class="sxs-lookup"><span data-stu-id="344ec-182">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="344ec-183">Agora você pode clicar com o botão direito do mouse em um arquivo ou uma pasta no Finder e selecionar **Verificar com o Microsoft Defender para Ponto de Extremidade**</span><span class="sxs-lookup"><span data-stu-id="344ec-183">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="344ec-184">As rebaixamentos in-locar do produto agora são explicitamente não permitidos pelo instalador.</span><span class="sxs-lookup"><span data-stu-id="344ec-184">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="344ec-185">Se você precisar fazer downgrade, primeiro desinstale a versão existente e reconfigure seu dispositivo</span><span class="sxs-lookup"><span data-stu-id="344ec-185">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="344ec-186">Outras melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-186">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="344ec-187">100.90.27</span><span class="sxs-lookup"><span data-stu-id="344ec-187">100.90.27</span></span>

- <span data-ttu-id="344ec-188">Agora você pode [definir um canal de](mac-updates.md#set-the-channel-name) atualização para o Microsoft Defender para Ponto de Extremidade para Mac diferente do canal de atualização em todo o sistema</span><span class="sxs-lookup"><span data-stu-id="344ec-188">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="344ec-189">Novo ícone do produto</span><span class="sxs-lookup"><span data-stu-id="344ec-189">New product icon</span></span>
- <span data-ttu-id="344ec-190">Outras melhorias na experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="344ec-190">Other user experience improvements</span></span>
- <span data-ttu-id="344ec-191">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-191">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="344ec-192">100.86.92</span><span class="sxs-lookup"><span data-stu-id="344ec-192">100.86.92</span></span>

- <span data-ttu-id="344ec-193">Melhorias em relação à compatibilidade com o Time Machine</span><span class="sxs-lookup"><span data-stu-id="344ec-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="344ec-194">Resolvido um problema em que o produto às vezes não limpava todos os arquivos `/Library/Application Support/Microsoft/Defender` durante a desinstalação</span><span class="sxs-lookup"><span data-stu-id="344ec-194">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="344ec-195">Redução da utilização da CPU do produto quando os produtos Microsoft são atualizados por meio do Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="344ec-195">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="344ec-196">Outras melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-196">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="344ec-197">100.86.91</span><span class="sxs-lookup"><span data-stu-id="344ec-197">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="344ec-198">Para garantir a proteção mais completa para seus dispositivos macOS e em alinhamento com a Apple interrompendo a entrega de atualizações de segurança nativas do macOS para versões do sistema operacional anteriores [atual – 2], a implantação e as atualizações do MDATP para Mac não terão mais suporte no macOS Sierra [10.12].</span><span class="sxs-lookup"><span data-stu-id="344ec-198">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="344ec-199">As atualizações e aprimoramentos do MDATP para Mac serão entregues aos dispositivos que executam as versões Catalina [10.15], Mojave [10.14], e High Sierra [10.13].</span><span class="sxs-lookup"><span data-stu-id="344ec-199">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="344ec-200">Se você já tiver o MDATP para Mac implantado em seus dispositivos Sierra [10.12], atualize para a versão mais recente do macOS para eliminar os riscos de perda de proteção.</span><span class="sxs-lookup"><span data-stu-id="344ec-200">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="344ec-201">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-201">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="344ec-202">100.83.73</span><span class="sxs-lookup"><span data-stu-id="344ec-202">100.83.73</span></span>

- <span data-ttu-id="344ec-203">Adicionado mais controles para [](mac-preferences.md#exclusion-merge-policy)administradores de IT em torno do gerenciamento de exclusões, [gerenciamento](mac-preferences.md#threat-type-settings-merge-policy)de configurações de tipo de ameaça e ações de ameaças [não permitidos](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="344ec-203">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="344ec-204">Quando o Acesso a Disco Completo não está habilitado no dispositivo, um aviso agora é exibido no menu de status</span><span class="sxs-lookup"><span data-stu-id="344ec-204">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="344ec-205">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-205">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="344ec-206">100.82.60</span><span class="sxs-lookup"><span data-stu-id="344ec-206">100.82.60</span></span>

- <span data-ttu-id="344ec-207">Resolvido um problema em que o produto não consegue começar a seguir uma atualização de definição.</span><span class="sxs-lookup"><span data-stu-id="344ec-207">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="344ec-208">100.80.42</span><span class="sxs-lookup"><span data-stu-id="344ec-208">100.80.42</span></span>

- <span data-ttu-id="344ec-209">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-209">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="344ec-210">100.79.42</span><span class="sxs-lookup"><span data-stu-id="344ec-210">100.79.42</span></span>

- <span data-ttu-id="344ec-211">Corrigido um problema em que o Microsoft Defender para Ponto de Extremidade para Mac estava, às vezes, interferendo com o Time Machine</span><span class="sxs-lookup"><span data-stu-id="344ec-211">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="344ec-212">Adicionada uma nova opção ao utilitário de linha de comando para testar a conectividade com o serviço back-end</span><span class="sxs-lookup"><span data-stu-id="344ec-212">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="344ec-213">Adicionada a capacidade de exibir o histórico completo de ameaças na interface do usuário (pode ser acessada a partir do visualização **histórico de** proteção)</span><span class="sxs-lookup"><span data-stu-id="344ec-213">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="344ec-214">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-214">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="344ec-215">100.72.15</span><span class="sxs-lookup"><span data-stu-id="344ec-215">100.72.15</span></span>

- <span data-ttu-id="344ec-216">Correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-216">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="344ec-217">100.70.99</span><span class="sxs-lookup"><span data-stu-id="344ec-217">100.70.99</span></span>

- <span data-ttu-id="344ec-218">Resolvido um problema que afeta a capacidade de alguns usuários atualizarem para o macOS Catalina quando a proteção em tempo real está habilitada.</span><span class="sxs-lookup"><span data-stu-id="344ec-218">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="344ec-219">Esse problema esporádico foi causado pelo Microsoft Defender para arquivos de bloqueio de ponto de extremidade no pacote de atualização de Catalina enquanto os examinou em busca de ameaças, o que resultou em falhas na sequência de atualização.</span><span class="sxs-lookup"><span data-stu-id="344ec-219">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="344ec-220">100.68.99</span><span class="sxs-lookup"><span data-stu-id="344ec-220">100.68.99</span></span>

- <span data-ttu-id="344ec-221">Adicionada a capacidade de configurar a funcionalidade antivírus para ser executado no [modo passivo](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="344ec-221">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="344ec-222">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-222">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="344ec-223">100.65.28</span><span class="sxs-lookup"><span data-stu-id="344ec-223">100.65.28</span></span>

- <span data-ttu-id="344ec-224">Adicionado suporte para macOS Catalina</span><span class="sxs-lookup"><span data-stu-id="344ec-224">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="344ec-225">O macOS 10.15 (Catalina) contém novos aprimoramentos de segurança e privacidade.</span><span class="sxs-lookup"><span data-stu-id="344ec-225">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="344ec-226">A partir dessa versão, por padrão, os aplicativos não são capazes de acessar determinados locais no disco (como Documentos, Downloads, Área de Trabalho, etc.) sem consentimento explícito.</span><span class="sxs-lookup"><span data-stu-id="344ec-226">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="344ec-227">Na ausência desse consentimento, o Microsoft Defender para Ponto de Extremidade não é capaz de proteger totalmente seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="344ec-227">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="344ec-228">O mecanismo para conceder esse consentimento depende de como você implantou o Microsoft Defender para o Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="344ec-228">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="344ec-229">Para implantações manuais, consulte as instruções atualizadas no [tópico implantação manual.](mac-install-manually.md#how-to-allow-full-disk-access)</span><span class="sxs-lookup"><span data-stu-id="344ec-229">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="344ec-230">Para implantações gerenciadas, consulte as instruções atualizadas nos tópicos de implantação baseada em [JAMF](mac-install-with-jamf.md) e implantação baseada no [Microsoft Intune.](mac-install-with-intune.md#create-system-configuration-profiles)</span><span class="sxs-lookup"><span data-stu-id="344ec-230">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="344ec-231">Melhorias de desempenho & correções de bugs</span><span class="sxs-lookup"><span data-stu-id="344ec-231">Performance improvements & bug fixes</span></span>
