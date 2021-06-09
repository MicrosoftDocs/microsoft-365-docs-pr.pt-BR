---
title: Implantar atualizações do Microsoft Defender para Ponto de Extremidade no Mac
description: Controlar atualizações do Microsoft Defender para Ponto de Extremidade no Mac em ambientes corporativos.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, atualizações, deploy
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
ms.openlocfilehash: 6447aa4182846020312e9be870c5548d9415ac71
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842825"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="4da3d-104">Implantar atualizações do Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="4da3d-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4da3d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4da3d-105">**Applies to:**</span></span>

- [<span data-ttu-id="4da3d-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="4da3d-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="4da3d-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4da3d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4da3d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4da3d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4da3d-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4da3d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4da3d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4da3d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="4da3d-111">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="4da3d-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="4da3d-112">Para atualizar o Microsoft Defender para Ponto de Extremidade no macOS, um programa chamado Microsoft AutoUpdate (MAU) é usado.</span><span class="sxs-lookup"><span data-stu-id="4da3d-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="4da3d-113">Por padrão, o MAU verifica automaticamente as atualizações diariamente, mas você pode alterá-la para semanal, mensal ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="4da3d-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Captura de tela MAU](images/MDATP-34-MAU.png)

<span data-ttu-id="4da3d-115">Se você decidir implantar atualizações usando suas ferramentas de distribuição de software, configure o MAU para verificar manualmente as atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="4da3d-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="4da3d-116">Você pode implantar preferências para configurar como e quando o MAU verifica se há atualizações para os Macs em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4da3d-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="4da3d-117">Usar o msupdate</span><span class="sxs-lookup"><span data-stu-id="4da3d-117">Use msupdate</span></span>

<span data-ttu-id="4da3d-118">O MAU inclui uma ferramenta de linha de comando, chamada *msupdate*, projetada para administradores de IT para que eles tenham um controle mais preciso sobre quando as atualizações são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="4da3d-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="4da3d-119">As instruções sobre como usar essa ferramenta podem ser encontradas em [Update Office para Mac usando msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="4da3d-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="4da3d-120">No MAU, o identificador de aplicativo do Microsoft Defender para Ponto de Extremidade no macOS é *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="4da3d-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="4da3d-121">Para baixar e instalar as atualizações mais recentes do Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando de uma janela de Terminal:</span><span class="sxs-lookup"><span data-stu-id="4da3d-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="4da3d-122">Definir preferências para o Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="4da3d-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="4da3d-123">Esta seção descreve as preferências mais comuns que podem ser usadas para configurar o MAU.</span><span class="sxs-lookup"><span data-stu-id="4da3d-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="4da3d-124">Essas configurações podem ser implantadas como um perfil de configuração por meio do console de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="4da3d-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="4da3d-125">Um exemplo de perfil de configuração é mostrado nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="4da3d-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="4da3d-126">Definir o nome do canal</span><span class="sxs-lookup"><span data-stu-id="4da3d-126">Set the channel name</span></span>

<span data-ttu-id="4da3d-127">O canal determina o tipo e a frequência de atualizações oferecidas por meio do MAU.</span><span class="sxs-lookup"><span data-stu-id="4da3d-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="4da3d-128">Os `Beta` dispositivos em podem experimentar novos recursos antes dos dispositivos `Preview` e `Current` .</span><span class="sxs-lookup"><span data-stu-id="4da3d-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="4da3d-129">O `Current` canal contém a versão mais estável do produto.</span><span class="sxs-lookup"><span data-stu-id="4da3d-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="4da3d-130">Antes do Microsoft AutoUpdate versão 4.29, os canais tinham nomes diferentes:</span><span class="sxs-lookup"><span data-stu-id="4da3d-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="4da3d-131">`Beta` foi nomeado `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="4da3d-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="4da3d-132">`Preview` foi nomeado `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="4da3d-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="4da3d-133">`Current` foi nomeado `Production`</span><span class="sxs-lookup"><span data-stu-id="4da3d-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="4da3d-134">Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para `Beta` ou `Preview` .</span><span class="sxs-lookup"><span data-stu-id="4da3d-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="4da3d-135">Section</span><span class="sxs-lookup"><span data-stu-id="4da3d-135">Section</span></span>|<span data-ttu-id="4da3d-136">Valor</span><span class="sxs-lookup"><span data-stu-id="4da3d-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="4da3d-137">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="4da3d-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="4da3d-138">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4da3d-138">**Key**</span></span> | <span data-ttu-id="4da3d-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="4da3d-139">ChannelName</span></span> |
| <span data-ttu-id="4da3d-140">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4da3d-140">**Data type**</span></span> | <span data-ttu-id="4da3d-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4da3d-141">String</span></span> |
| <span data-ttu-id="4da3d-142">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="4da3d-142">**Possible values**</span></span> | <span data-ttu-id="4da3d-143">Beta</span><span class="sxs-lookup"><span data-stu-id="4da3d-143">Beta</span></span> <br/> <span data-ttu-id="4da3d-144">Visualização</span><span class="sxs-lookup"><span data-stu-id="4da3d-144">Preview</span></span> <br/> <span data-ttu-id="4da3d-145">Atual</span><span class="sxs-lookup"><span data-stu-id="4da3d-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="4da3d-146">Essa configuração altera o canal para todos os aplicativos que são atualizados por meio do Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="4da3d-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="4da3d-147">Para alterar o canal somente para o Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando após substituir `[channel-name]` pelo canal desejado:</span><span class="sxs-lookup"><span data-stu-id="4da3d-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="4da3d-148">Definir a frequência de verificação de atualização</span><span class="sxs-lookup"><span data-stu-id="4da3d-148">Set update check frequency</span></span>

<span data-ttu-id="4da3d-149">Altere a frequência com que o MAU pesquisa atualizações.</span><span class="sxs-lookup"><span data-stu-id="4da3d-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="4da3d-150">Section</span><span class="sxs-lookup"><span data-stu-id="4da3d-150">Section</span></span>|<span data-ttu-id="4da3d-151">Valor</span><span class="sxs-lookup"><span data-stu-id="4da3d-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="4da3d-152">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="4da3d-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="4da3d-153">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4da3d-153">**Key**</span></span> | <span data-ttu-id="4da3d-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="4da3d-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="4da3d-155">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4da3d-155">**Data type**</span></span> | <span data-ttu-id="4da3d-156">Inteiro</span><span class="sxs-lookup"><span data-stu-id="4da3d-156">Integer</span></span> |
| <span data-ttu-id="4da3d-157">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="4da3d-157">**Default value**</span></span> | <span data-ttu-id="4da3d-158">720 (minutos)</span><span class="sxs-lookup"><span data-stu-id="4da3d-158">720 (minutes)</span></span> |
| <span data-ttu-id="4da3d-159">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="4da3d-159">**Comment**</span></span> | <span data-ttu-id="4da3d-160">Esse valor é definido em minutos.</span><span class="sxs-lookup"><span data-stu-id="4da3d-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="4da3d-161">Alterar como o MAU interage com atualizações</span><span class="sxs-lookup"><span data-stu-id="4da3d-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="4da3d-162">Altere como o MAU pesquisa atualizações.</span><span class="sxs-lookup"><span data-stu-id="4da3d-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="4da3d-163">Section</span><span class="sxs-lookup"><span data-stu-id="4da3d-163">Section</span></span>|<span data-ttu-id="4da3d-164">Valor</span><span class="sxs-lookup"><span data-stu-id="4da3d-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="4da3d-165">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="4da3d-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="4da3d-166">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4da3d-166">**Key**</span></span> | <span data-ttu-id="4da3d-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="4da3d-167">HowToCheck</span></span> |
| <span data-ttu-id="4da3d-168">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4da3d-168">**Data type**</span></span> | <span data-ttu-id="4da3d-169">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="4da3d-169">String</span></span> |
| <span data-ttu-id="4da3d-170">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="4da3d-170">**Possible values**</span></span> | <span data-ttu-id="4da3d-171">Manual</span><span class="sxs-lookup"><span data-stu-id="4da3d-171">Manual</span></span> <br/> <span data-ttu-id="4da3d-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="4da3d-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="4da3d-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="4da3d-173">AutomaticDownload</span></span> |
| <span data-ttu-id="4da3d-174">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="4da3d-174">**Comment**</span></span> |  <span data-ttu-id="4da3d-175">Observe que AutomaticDownload fará um download e instalará silenciosamente, se possível.</span><span class="sxs-lookup"><span data-stu-id="4da3d-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="4da3d-176">Alterar se o botão "Verificar atualizações" está habilitado</span><span class="sxs-lookup"><span data-stu-id="4da3d-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="4da3d-177">Altere se os usuários locais poderão clicar na opção "Verificar atualizações" na interface do usuário Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="4da3d-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="4da3d-178">Section</span><span class="sxs-lookup"><span data-stu-id="4da3d-178">Section</span></span>|<span data-ttu-id="4da3d-179">Valor</span><span class="sxs-lookup"><span data-stu-id="4da3d-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="4da3d-180">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="4da3d-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="4da3d-181">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4da3d-181">**Key**</span></span> | <span data-ttu-id="4da3d-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="4da3d-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="4da3d-183">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4da3d-183">**Data type**</span></span> | <span data-ttu-id="4da3d-184">Booliano</span><span class="sxs-lookup"><span data-stu-id="4da3d-184">Boolean</span></span> |
| <span data-ttu-id="4da3d-185">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="4da3d-185">**Possible values**</span></span> | <span data-ttu-id="4da3d-186">True (padrão)</span><span class="sxs-lookup"><span data-stu-id="4da3d-186">True (default)</span></span> <br/> <span data-ttu-id="4da3d-187">Falso</span><span class="sxs-lookup"><span data-stu-id="4da3d-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="4da3d-188">Desabilitar a caixa de seleção Insider</span><span class="sxs-lookup"><span data-stu-id="4da3d-188">Disable Insider checkbox</span></span>

<span data-ttu-id="4da3d-189">De definir como true para tornar o "Ingressar no programa Office Insider..." caixa de seleção indisponível/esvazada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="4da3d-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="4da3d-190">Section</span><span class="sxs-lookup"><span data-stu-id="4da3d-190">Section</span></span>|<span data-ttu-id="4da3d-191">Valor</span><span class="sxs-lookup"><span data-stu-id="4da3d-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="4da3d-192">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="4da3d-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="4da3d-193">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4da3d-193">**Key**</span></span> | <span data-ttu-id="4da3d-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="4da3d-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="4da3d-195">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4da3d-195">**Data type**</span></span> | <span data-ttu-id="4da3d-196">Booliano</span><span class="sxs-lookup"><span data-stu-id="4da3d-196">Boolean</span></span> |
| <span data-ttu-id="4da3d-197">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="4da3d-197">**Possible values**</span></span> | <span data-ttu-id="4da3d-198">False (padrão)</span><span class="sxs-lookup"><span data-stu-id="4da3d-198">False (default)</span></span> <br/> <span data-ttu-id="4da3d-199">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="4da3d-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="4da3d-200">Limitar a telemetria enviada do MAU</span><span class="sxs-lookup"><span data-stu-id="4da3d-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="4da3d-201">De definida como false para enviar dados mínimos de pulsação, sem uso de aplicativo e sem detalhes do ambiente.</span><span class="sxs-lookup"><span data-stu-id="4da3d-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="4da3d-202">Section</span><span class="sxs-lookup"><span data-stu-id="4da3d-202">Section</span></span>|<span data-ttu-id="4da3d-203">Valor</span><span class="sxs-lookup"><span data-stu-id="4da3d-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="4da3d-204">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="4da3d-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="4da3d-205">**Chave**</span><span class="sxs-lookup"><span data-stu-id="4da3d-205">**Key**</span></span> | <span data-ttu-id="4da3d-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="4da3d-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="4da3d-207">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4da3d-207">**Data type**</span></span> | <span data-ttu-id="4da3d-208">Booliano</span><span class="sxs-lookup"><span data-stu-id="4da3d-208">Boolean</span></span> |
| <span data-ttu-id="4da3d-209">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="4da3d-209">**Possible values**</span></span> | <span data-ttu-id="4da3d-210">True (padrão)</span><span class="sxs-lookup"><span data-stu-id="4da3d-210">True (default)</span></span> <br/> <span data-ttu-id="4da3d-211">Falso</span><span class="sxs-lookup"><span data-stu-id="4da3d-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="4da3d-212">Exemplo de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="4da3d-212">Example configuration profile</span></span>

<span data-ttu-id="4da3d-213">O seguinte perfil de configuração é usado para:</span><span class="sxs-lookup"><span data-stu-id="4da3d-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="4da3d-214">Colocar o dispositivo no canal de produção</span><span class="sxs-lookup"><span data-stu-id="4da3d-214">Place the device in the Production channel</span></span>
- <span data-ttu-id="4da3d-215">Baixar e instalar atualizações automaticamente</span><span class="sxs-lookup"><span data-stu-id="4da3d-215">Automatically download and install updates</span></span>
- <span data-ttu-id="4da3d-216">Habilitar o botão "Verificar atualizações" na interface do usuário</span><span class="sxs-lookup"><span data-stu-id="4da3d-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="4da3d-217">Permitir que os usuários no dispositivo se inscrevam nos canais Insider</span><span class="sxs-lookup"><span data-stu-id="4da3d-217">Allow users on the device to enroll into the Insider channels</span></span>


>[!WARNING]
><span data-ttu-id="4da3d-218">A configuração abaixo é um exemplo de configuração e não deve ser usada na produção sem a revisão adequada das configurações e do ajuste das configurações.</span><span class="sxs-lookup"><span data-stu-id="4da3d-218">The below configuration is an example configuration and should not be used in production without proper review of settings and tailor of configurations.</span></span>

>[!TIP]
><span data-ttu-id="4da3d-219">Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para `Beta` ou `Preview` .</span><span class="sxs-lookup"><span data-stu-id="4da3d-219">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

### <a name="jamf"></a><span data-ttu-id="4da3d-220">JAMF</span><span class="sxs-lookup"><span data-stu-id="4da3d-220">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a><span data-ttu-id="4da3d-221">Intune</span><span class="sxs-lookup"><span data-stu-id="4da3d-221">Intune</span></span>

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

<span data-ttu-id="4da3d-222">Para configurar o MAU, você pode implantar esse perfil de configuração a partir da ferramenta de gerenciamento que sua empresa está usando:</span><span class="sxs-lookup"><span data-stu-id="4da3d-222">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="4da3d-223">No JAMF, carregue esse perfil de configuração e de definir o Domínio de Preferência *como com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="4da3d-223">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="4da3d-224">No Intune, carregue esse perfil de configuração e defina o nome do perfil de configuração personalizado *como com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="4da3d-224">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="4da3d-225">Recursos</span><span class="sxs-lookup"><span data-stu-id="4da3d-225">Resources</span></span>

- [<span data-ttu-id="4da3d-226">referência msupdate</span><span class="sxs-lookup"><span data-stu-id="4da3d-226">msupdate reference</span></span>](/deployoffice/mac/update-office-for-mac-using-msupdate)
