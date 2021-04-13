---
title: Implantar atualizações do Microsoft Defender ATP para Mac
description: Controlar atualizações do Microsoft Defender ATP para Mac em ambientes corporativos.
keywords: microsoft, defender, atp, mac, atualizações, implantar
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
ms.openlocfilehash: 3321c1bd181b89c53e2618fc20fa7f733a20cfc1
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689048"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="c3569-104">Implantar atualizações do Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="c3569-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c3569-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c3569-105">**Applies to:**</span></span>

- [<span data-ttu-id="c3569-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="c3569-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="c3569-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c3569-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c3569-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c3569-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c3569-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c3569-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c3569-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c3569-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="c3569-111">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="c3569-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="c3569-112">Para atualizar o Microsoft Defender para Ponto de Extremidade no macOS, um programa chamado Microsoft AutoUpdate (MAU) é usado.</span><span class="sxs-lookup"><span data-stu-id="c3569-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="c3569-113">Por padrão, o MAU verifica automaticamente as atualizações diariamente, mas você pode alterá-la para semanal, mensal ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="c3569-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Captura de tela MAU](images/MDATP-34-MAU.png)

<span data-ttu-id="c3569-115">Se você decidir implantar atualizações usando suas ferramentas de distribuição de software, configure o MAU para verificar manualmente as atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="c3569-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="c3569-116">Você pode implantar preferências para configurar como e quando o MAU verifica se há atualizações para os Macs em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3569-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="c3569-117">Usar o msupdate</span><span class="sxs-lookup"><span data-stu-id="c3569-117">Use msupdate</span></span>

<span data-ttu-id="c3569-118">O MAU inclui uma ferramenta de linha de comando, chamada *msupdate*, projetada para administradores de IT para que eles tenham um controle mais preciso sobre quando as atualizações são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="c3569-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="c3569-119">As instruções sobre como usar essa ferramenta podem ser encontradas em [Atualizar o Office para Mac usando msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="c3569-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="c3569-120">No MAU, o identificador de aplicativo do Microsoft Defender para Ponto de Extremidade no macOS é *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="c3569-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="c3569-121">Para baixar e instalar as atualizações mais recentes do Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando de uma janela de Terminal:</span><span class="sxs-lookup"><span data-stu-id="c3569-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="c3569-122">Definir preferências para o Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="c3569-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="c3569-123">Esta seção descreve as preferências mais comuns que podem ser usadas para configurar o MAU.</span><span class="sxs-lookup"><span data-stu-id="c3569-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="c3569-124">Essas configurações podem ser implantadas como um perfil de configuração por meio do console de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="c3569-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="c3569-125">Um exemplo de perfil de configuração é mostrado nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c3569-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="c3569-126">Definir o nome do canal</span><span class="sxs-lookup"><span data-stu-id="c3569-126">Set the channel name</span></span>

<span data-ttu-id="c3569-127">O canal determina o tipo e a frequência de atualizações oferecidas por meio do MAU.</span><span class="sxs-lookup"><span data-stu-id="c3569-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="c3569-128">Os `Beta` dispositivos em podem experimentar novos recursos antes dos dispositivos `Preview` e `Current` .</span><span class="sxs-lookup"><span data-stu-id="c3569-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="c3569-129">O `Current` canal contém a versão mais estável do produto.</span><span class="sxs-lookup"><span data-stu-id="c3569-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="c3569-130">Antes do Microsoft AutoUpdate versão 4.29, os canais tinham nomes diferentes:</span><span class="sxs-lookup"><span data-stu-id="c3569-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="c3569-131">`Beta` foi nomeado `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="c3569-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="c3569-132">`Preview` foi nomeado `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="c3569-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="c3569-133">`Current` foi nomeado `Production`</span><span class="sxs-lookup"><span data-stu-id="c3569-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="c3569-134">Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para `Beta` ou `Preview` .</span><span class="sxs-lookup"><span data-stu-id="c3569-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="c3569-135">Section</span><span class="sxs-lookup"><span data-stu-id="c3569-135">Section</span></span>|<span data-ttu-id="c3569-136">Valor</span><span class="sxs-lookup"><span data-stu-id="c3569-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c3569-137">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="c3569-137">**Domain**</span></span> | <span data-ttu-id="c3569-138">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="c3569-138">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="c3569-139">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c3569-139">**Key**</span></span> | <span data-ttu-id="c3569-140">ChannelName</span><span class="sxs-lookup"><span data-stu-id="c3569-140">ChannelName</span></span> |
| <span data-ttu-id="c3569-141">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3569-141">**Data type**</span></span> | <span data-ttu-id="c3569-142">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c3569-142">String</span></span> |
| <span data-ttu-id="c3569-143">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c3569-143">**Possible values**</span></span> | <span data-ttu-id="c3569-144">Beta</span><span class="sxs-lookup"><span data-stu-id="c3569-144">Beta</span></span> <br/> <span data-ttu-id="c3569-145">Visualização</span><span class="sxs-lookup"><span data-stu-id="c3569-145">Preview</span></span> <br/> <span data-ttu-id="c3569-146">Atual</span><span class="sxs-lookup"><span data-stu-id="c3569-146">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="c3569-147">Essa configuração altera o canal para todos os aplicativos que são atualizados por meio do Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="c3569-147">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="c3569-148">Para alterar o canal somente para o Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando após substituir `[channel-name]` pelo canal desejado:</span><span class="sxs-lookup"><span data-stu-id="c3569-148">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="c3569-149">Definir a frequência de verificação de atualização</span><span class="sxs-lookup"><span data-stu-id="c3569-149">Set update check frequency</span></span>

<span data-ttu-id="c3569-150">Altere a frequência com que o MAU pesquisa atualizações.</span><span class="sxs-lookup"><span data-stu-id="c3569-150">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="c3569-151">Section</span><span class="sxs-lookup"><span data-stu-id="c3569-151">Section</span></span>|<span data-ttu-id="c3569-152">Valor</span><span class="sxs-lookup"><span data-stu-id="c3569-152">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c3569-153">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="c3569-153">**Domain**</span></span> | <span data-ttu-id="c3569-154">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="c3569-154">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="c3569-155">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c3569-155">**Key**</span></span> | <span data-ttu-id="c3569-156">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="c3569-156">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="c3569-157">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3569-157">**Data type**</span></span> | <span data-ttu-id="c3569-158">Inteiro</span><span class="sxs-lookup"><span data-stu-id="c3569-158">Integer</span></span> |
| <span data-ttu-id="c3569-159">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="c3569-159">**Default value**</span></span> | <span data-ttu-id="c3569-160">720 (minutos)</span><span class="sxs-lookup"><span data-stu-id="c3569-160">720 (minutes)</span></span> |
| <span data-ttu-id="c3569-161">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c3569-161">**Comment**</span></span> | <span data-ttu-id="c3569-162">Esse valor é definido em minutos.</span><span class="sxs-lookup"><span data-stu-id="c3569-162">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="c3569-163">Alterar como o MAU interage com atualizações</span><span class="sxs-lookup"><span data-stu-id="c3569-163">Change how MAU interacts with updates</span></span>

<span data-ttu-id="c3569-164">Altere como o MAU pesquisa atualizações.</span><span class="sxs-lookup"><span data-stu-id="c3569-164">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="c3569-165">Section</span><span class="sxs-lookup"><span data-stu-id="c3569-165">Section</span></span>|<span data-ttu-id="c3569-166">Valor</span><span class="sxs-lookup"><span data-stu-id="c3569-166">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c3569-167">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="c3569-167">**Domain**</span></span> | <span data-ttu-id="c3569-168">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="c3569-168">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="c3569-169">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c3569-169">**Key**</span></span> | <span data-ttu-id="c3569-170">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="c3569-170">HowToCheck</span></span> |
| <span data-ttu-id="c3569-171">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3569-171">**Data type**</span></span> | <span data-ttu-id="c3569-172">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c3569-172">String</span></span> |
| <span data-ttu-id="c3569-173">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c3569-173">**Possible values**</span></span> | <span data-ttu-id="c3569-174">Manual</span><span class="sxs-lookup"><span data-stu-id="c3569-174">Manual</span></span> <br/> <span data-ttu-id="c3569-175">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="c3569-175">AutomaticCheck</span></span> <br/> <span data-ttu-id="c3569-176">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="c3569-176">AutomaticDownload</span></span> |
| <span data-ttu-id="c3569-177">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c3569-177">**Comment**</span></span> |  <span data-ttu-id="c3569-178">Observe que AutomaticDownload fará um download e instalará silenciosamente, se possível.</span><span class="sxs-lookup"><span data-stu-id="c3569-178">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="c3569-179">Alterar se o botão "Verificar atualizações" está habilitado</span><span class="sxs-lookup"><span data-stu-id="c3569-179">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="c3569-180">Altere se os usuários locais poderão clicar na opção "Verificar atualizações" na interface do usuário Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="c3569-180">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="c3569-181">Section</span><span class="sxs-lookup"><span data-stu-id="c3569-181">Section</span></span>|<span data-ttu-id="c3569-182">Valor</span><span class="sxs-lookup"><span data-stu-id="c3569-182">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c3569-183">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="c3569-183">**Domain**</span></span> | <span data-ttu-id="c3569-184">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="c3569-184">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="c3569-185">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c3569-185">**Key**</span></span> | <span data-ttu-id="c3569-186">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="c3569-186">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="c3569-187">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3569-187">**Data type**</span></span> | <span data-ttu-id="c3569-188">Booliano</span><span class="sxs-lookup"><span data-stu-id="c3569-188">Boolean</span></span> |
| <span data-ttu-id="c3569-189">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c3569-189">**Possible values**</span></span> | <span data-ttu-id="c3569-190">True (padrão)</span><span class="sxs-lookup"><span data-stu-id="c3569-190">True (default)</span></span> <br/> <span data-ttu-id="c3569-191">Falso</span><span class="sxs-lookup"><span data-stu-id="c3569-191">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="c3569-192">Desabilitar a caixa de seleção Insider</span><span class="sxs-lookup"><span data-stu-id="c3569-192">Disable Insider checkbox</span></span>

<span data-ttu-id="c3569-193">Definir como true para tornar o "Ingressar no Programa Office Insider..." caixa de seleção indisponível/esvazada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="c3569-193">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="c3569-194">Section</span><span class="sxs-lookup"><span data-stu-id="c3569-194">Section</span></span>|<span data-ttu-id="c3569-195">Valor</span><span class="sxs-lookup"><span data-stu-id="c3569-195">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c3569-196">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="c3569-196">**Domain**</span></span> | <span data-ttu-id="c3569-197">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="c3569-197">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="c3569-198">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c3569-198">**Key**</span></span> | <span data-ttu-id="c3569-199">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="c3569-199">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="c3569-200">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3569-200">**Data type**</span></span> | <span data-ttu-id="c3569-201">Booliano</span><span class="sxs-lookup"><span data-stu-id="c3569-201">Boolean</span></span> |
| <span data-ttu-id="c3569-202">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c3569-202">**Possible values**</span></span> | <span data-ttu-id="c3569-203">False (padrão)</span><span class="sxs-lookup"><span data-stu-id="c3569-203">False (default)</span></span> <br/> <span data-ttu-id="c3569-204">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="c3569-204">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="c3569-205">Limitar a telemetria enviada do MAU</span><span class="sxs-lookup"><span data-stu-id="c3569-205">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="c3569-206">De definida como false para enviar dados mínimos de pulsação, sem uso de aplicativo e sem detalhes do ambiente.</span><span class="sxs-lookup"><span data-stu-id="c3569-206">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="c3569-207">Section</span><span class="sxs-lookup"><span data-stu-id="c3569-207">Section</span></span>|<span data-ttu-id="c3569-208">Valor</span><span class="sxs-lookup"><span data-stu-id="c3569-208">Value</span></span>|
|:--|:--|
| <span data-ttu-id="c3569-209">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="c3569-209">**Domain**</span></span> | <span data-ttu-id="c3569-210">com.microsoft.autoupdate2</span><span class="sxs-lookup"><span data-stu-id="c3569-210">com.microsoft.autoupdate2</span></span> |
| <span data-ttu-id="c3569-211">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="c3569-211">**Key**</span></span> | <span data-ttu-id="c3569-212">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="c3569-212">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="c3569-213">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c3569-213">**Data type**</span></span> | <span data-ttu-id="c3569-214">Booliano</span><span class="sxs-lookup"><span data-stu-id="c3569-214">Boolean</span></span> |
| <span data-ttu-id="c3569-215">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="c3569-215">**Possible values**</span></span> | <span data-ttu-id="c3569-216">True (padrão)</span><span class="sxs-lookup"><span data-stu-id="c3569-216">True (default)</span></span> <br/> <span data-ttu-id="c3569-217">Falso</span><span class="sxs-lookup"><span data-stu-id="c3569-217">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="c3569-218">Exemplo de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="c3569-218">Example configuration profile</span></span>

<span data-ttu-id="c3569-219">O seguinte perfil de configuração é usado para:</span><span class="sxs-lookup"><span data-stu-id="c3569-219">The following configuration profile is used to:</span></span>
- <span data-ttu-id="c3569-220">Colocar o dispositivo no canal Beta</span><span class="sxs-lookup"><span data-stu-id="c3569-220">Place the device in the Beta channel</span></span>
- <span data-ttu-id="c3569-221">Baixar e instalar atualizações automaticamente</span><span class="sxs-lookup"><span data-stu-id="c3569-221">Automatically download and install updates</span></span>
- <span data-ttu-id="c3569-222">Habilitar o botão "Verificar atualizações" na interface do usuário</span><span class="sxs-lookup"><span data-stu-id="c3569-222">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="c3569-223">Permitir que os usuários no dispositivo se inscrevam nos canais Insider</span><span class="sxs-lookup"><span data-stu-id="c3569-223">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="c3569-224">JAMF</span><span class="sxs-lookup"><span data-stu-id="c3569-224">JAMF</span></span>

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Beta</string>
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

### <a name="intune"></a><span data-ttu-id="c3569-225">Intune</span><span class="sxs-lookup"><span data-stu-id="c3569-225">Intune</span></span>

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
            <string>Beta</string>
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

<span data-ttu-id="c3569-226">Para configurar o MAU, você pode implantar esse perfil de configuração a partir da ferramenta de gerenciamento que sua empresa está usando:</span><span class="sxs-lookup"><span data-stu-id="c3569-226">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="c3569-227">No JAMF, carregue esse perfil de configuração e de definir o Domínio de Preferência *como com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="c3569-227">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="c3569-228">No Intune, carregue esse perfil de configuração e defina o nome do perfil de configuração personalizado *como com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="c3569-228">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="c3569-229">Recursos</span><span class="sxs-lookup"><span data-stu-id="c3569-229">Resources</span></span>

- [<span data-ttu-id="c3569-230">referência msupdate</span><span class="sxs-lookup"><span data-stu-id="c3569-230">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
