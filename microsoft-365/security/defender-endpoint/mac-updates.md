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
ms.openlocfilehash: 886195de38856306d69932446eae34212fe4bb0d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934496"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="88c67-104">Implantar atualizações do Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="88c67-104">Deploy updates for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="88c67-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="88c67-105">**Applies to:**</span></span>

- [<span data-ttu-id="88c67-106">Microsoft Defender para Ponto de Extremidade no macOS</span><span class="sxs-lookup"><span data-stu-id="88c67-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="88c67-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="88c67-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="88c67-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="88c67-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="88c67-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="88c67-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="88c67-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="88c67-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="88c67-111">A Microsoft publica regularmente atualizações de software para melhorar o desempenho, a segurança e fornecer novos recursos.</span><span class="sxs-lookup"><span data-stu-id="88c67-111">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

<span data-ttu-id="88c67-112">Para atualizar o Microsoft Defender para Ponto de Extremidade no macOS, um programa chamado Microsoft AutoUpdate (MAU) é usado.</span><span class="sxs-lookup"><span data-stu-id="88c67-112">To update Microsoft Defender for Endpoint on macOS, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="88c67-113">Por padrão, o MAU verifica automaticamente as atualizações diariamente, mas você pode alterá-la para semanal, mensal ou manualmente.</span><span class="sxs-lookup"><span data-stu-id="88c67-113">By default, MAU automatically checks for updates daily, but you can change that to weekly, monthly, or manually.</span></span>

![Captura de tela MAU](images/MDATP-34-MAU.png)

<span data-ttu-id="88c67-115">Se você decidir implantar atualizações usando suas ferramentas de distribuição de software, configure o MAU para verificar manualmente as atualizações de software.</span><span class="sxs-lookup"><span data-stu-id="88c67-115">If you decide to deploy updates by using your software distribution tools, you should configure MAU to manually check for software updates.</span></span> <span data-ttu-id="88c67-116">Você pode implantar preferências para configurar como e quando o MAU verifica se há atualizações para os Macs em sua organização.</span><span class="sxs-lookup"><span data-stu-id="88c67-116">You can deploy preferences to configure how and when MAU checks for updates for the Macs in your organization.</span></span>

## <a name="use-msupdate"></a><span data-ttu-id="88c67-117">Usar o msupdate</span><span class="sxs-lookup"><span data-stu-id="88c67-117">Use msupdate</span></span>

<span data-ttu-id="88c67-118">O MAU inclui uma ferramenta de linha de comando, chamada *msupdate*, projetada para administradores de IT para que eles tenham um controle mais preciso sobre quando as atualizações são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="88c67-118">MAU includes a command-line tool, called *msupdate*, that is designed for IT administrators so that they have more precise control over when updates are applied.</span></span> <span data-ttu-id="88c67-119">As instruções sobre como usar essa ferramenta podem ser encontradas em [Atualizar o Office para Mac usando msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span><span class="sxs-lookup"><span data-stu-id="88c67-119">Instructions for how to use this tool can be found in [Update Office for Mac by using msupdate](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate).</span></span>

<span data-ttu-id="88c67-120">No MAU, o identificador de aplicativo do Microsoft Defender para Ponto de Extremidade no macOS é *WDAV00*.</span><span class="sxs-lookup"><span data-stu-id="88c67-120">In MAU, the application identifier for Microsoft Defender for Endpoint on macOS is *WDAV00*.</span></span> <span data-ttu-id="88c67-121">Para baixar e instalar as atualizações mais recentes do Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando de uma janela de Terminal:</span><span class="sxs-lookup"><span data-stu-id="88c67-121">To download and install the latest updates for Microsoft Defender for Endpoint on macOS, execute the following command from a Terminal window:</span></span>

```
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a><span data-ttu-id="88c67-122">Definir preferências para o Microsoft AutoUpdate</span><span class="sxs-lookup"><span data-stu-id="88c67-122">Set preferences for Microsoft AutoUpdate</span></span>

<span data-ttu-id="88c67-123">Esta seção descreve as preferências mais comuns que podem ser usadas para configurar o MAU.</span><span class="sxs-lookup"><span data-stu-id="88c67-123">This section describes the most common preferences that can be used to configure MAU.</span></span> <span data-ttu-id="88c67-124">Essas configurações podem ser implantadas como um perfil de configuração por meio do console de gerenciamento que sua empresa está usando.</span><span class="sxs-lookup"><span data-stu-id="88c67-124">These settings can be deployed as a configuration profile through the management console that your enterprise is using.</span></span> <span data-ttu-id="88c67-125">Um exemplo de perfil de configuração é mostrado nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="88c67-125">An example of a configuration profile is shown in the following sections.</span></span>

### <a name="set-the-channel-name"></a><span data-ttu-id="88c67-126">Definir o nome do canal</span><span class="sxs-lookup"><span data-stu-id="88c67-126">Set the channel name</span></span>

<span data-ttu-id="88c67-127">O canal determina o tipo e a frequência de atualizações oferecidas por meio do MAU.</span><span class="sxs-lookup"><span data-stu-id="88c67-127">The channel determines the type and frequency of updates that are offered through MAU.</span></span> <span data-ttu-id="88c67-128">Os `Beta` dispositivos em podem experimentar novos recursos antes dos dispositivos `Preview` e `Current` .</span><span class="sxs-lookup"><span data-stu-id="88c67-128">Devices in `Beta` can try out new features before devices in `Preview` and `Current`.</span></span> 

<span data-ttu-id="88c67-129">O `Current` canal contém a versão mais estável do produto.</span><span class="sxs-lookup"><span data-stu-id="88c67-129">The `Current` channel contains the most stable version of the product.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="88c67-130">Antes do Microsoft AutoUpdate versão 4.29, os canais tinham nomes diferentes:</span><span class="sxs-lookup"><span data-stu-id="88c67-130">Prior to Microsoft AutoUpdate version 4.29, channels had different names:</span></span> 
> 
> - <span data-ttu-id="88c67-131">`Beta` foi nomeado `InsiderFast` (Insider Fast)</span><span class="sxs-lookup"><span data-stu-id="88c67-131">`Beta` was named `InsiderFast` (Insider Fast)</span></span>
> - <span data-ttu-id="88c67-132">`Preview` foi nomeado `External` (Insider Slow)</span><span class="sxs-lookup"><span data-stu-id="88c67-132">`Preview` was named `External` (Insider Slow)</span></span>
> - <span data-ttu-id="88c67-133">`Current` foi nomeado `Production`</span><span class="sxs-lookup"><span data-stu-id="88c67-133">`Current` was named `Production`</span></span>

>[!TIP]
><span data-ttu-id="88c67-134">Para visualizar novos recursos e fornecer comentários antecipados, é recomendável configurar alguns dispositivos em sua empresa para `Beta` ou `Preview` .</span><span class="sxs-lookup"><span data-stu-id="88c67-134">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to `Beta` or `Preview`.</span></span>

|<span data-ttu-id="88c67-135">Section</span><span class="sxs-lookup"><span data-stu-id="88c67-135">Section</span></span>|<span data-ttu-id="88c67-136">Valor</span><span class="sxs-lookup"><span data-stu-id="88c67-136">Value</span></span>|
|:--|:--|
| <span data-ttu-id="88c67-137">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="88c67-137">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="88c67-138">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="88c67-138">**Key**</span></span> | <span data-ttu-id="88c67-139">ChannelName</span><span class="sxs-lookup"><span data-stu-id="88c67-139">ChannelName</span></span> |
| <span data-ttu-id="88c67-140">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="88c67-140">**Data type**</span></span> | <span data-ttu-id="88c67-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="88c67-141">String</span></span> |
| <span data-ttu-id="88c67-142">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="88c67-142">**Possible values**</span></span> | <span data-ttu-id="88c67-143">Beta</span><span class="sxs-lookup"><span data-stu-id="88c67-143">Beta</span></span> <br/> <span data-ttu-id="88c67-144">Visualização</span><span class="sxs-lookup"><span data-stu-id="88c67-144">Preview</span></span> <br/> <span data-ttu-id="88c67-145">Atual</span><span class="sxs-lookup"><span data-stu-id="88c67-145">Current</span></span> |
|||

>[!WARNING]
><span data-ttu-id="88c67-146">Essa configuração altera o canal para todos os aplicativos que são atualizados por meio do Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="88c67-146">This setting changes the channel for all applications that are updated through Microsoft AutoUpdate.</span></span> <span data-ttu-id="88c67-147">Para alterar o canal somente para o Microsoft Defender para Ponto de Extremidade no macOS, execute o seguinte comando após substituir `[channel-name]` pelo canal desejado:</span><span class="sxs-lookup"><span data-stu-id="88c67-147">To change the channel only for Microsoft Defender for Endpoint on macOS, execute the following command after replacing `[channel-name]` with the desired channel:</span></span>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a><span data-ttu-id="88c67-148">Definir a frequência de verificação de atualização</span><span class="sxs-lookup"><span data-stu-id="88c67-148">Set update check frequency</span></span>

<span data-ttu-id="88c67-149">Altere a frequência com que o MAU pesquisa atualizações.</span><span class="sxs-lookup"><span data-stu-id="88c67-149">Change how often MAU searches for updates.</span></span>

|<span data-ttu-id="88c67-150">Section</span><span class="sxs-lookup"><span data-stu-id="88c67-150">Section</span></span>|<span data-ttu-id="88c67-151">Valor</span><span class="sxs-lookup"><span data-stu-id="88c67-151">Value</span></span>|
|:--|:--|
| <span data-ttu-id="88c67-152">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="88c67-152">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="88c67-153">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="88c67-153">**Key**</span></span> | <span data-ttu-id="88c67-154">UpdateCheckFrequency</span><span class="sxs-lookup"><span data-stu-id="88c67-154">UpdateCheckFrequency</span></span> |
| <span data-ttu-id="88c67-155">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="88c67-155">**Data type**</span></span> | <span data-ttu-id="88c67-156">Inteiro</span><span class="sxs-lookup"><span data-stu-id="88c67-156">Integer</span></span> |
| <span data-ttu-id="88c67-157">**Valor padrão**</span><span class="sxs-lookup"><span data-stu-id="88c67-157">**Default value**</span></span> | <span data-ttu-id="88c67-158">720 (minutos)</span><span class="sxs-lookup"><span data-stu-id="88c67-158">720 (minutes)</span></span> |
| <span data-ttu-id="88c67-159">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="88c67-159">**Comment**</span></span> | <span data-ttu-id="88c67-160">Esse valor é definido em minutos.</span><span class="sxs-lookup"><span data-stu-id="88c67-160">This value is set in minutes.</span></span> |


### <a name="change-how-mau-interacts-with-updates"></a><span data-ttu-id="88c67-161">Alterar como o MAU interage com atualizações</span><span class="sxs-lookup"><span data-stu-id="88c67-161">Change how MAU interacts with updates</span></span>

<span data-ttu-id="88c67-162">Altere como o MAU pesquisa atualizações.</span><span class="sxs-lookup"><span data-stu-id="88c67-162">Change how MAU searches for updates.</span></span>

|<span data-ttu-id="88c67-163">Section</span><span class="sxs-lookup"><span data-stu-id="88c67-163">Section</span></span>|<span data-ttu-id="88c67-164">Valor</span><span class="sxs-lookup"><span data-stu-id="88c67-164">Value</span></span>|
|:--|:--|
| <span data-ttu-id="88c67-165">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="88c67-165">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="88c67-166">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="88c67-166">**Key**</span></span> | <span data-ttu-id="88c67-167">HowToCheck</span><span class="sxs-lookup"><span data-stu-id="88c67-167">HowToCheck</span></span> |
| <span data-ttu-id="88c67-168">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="88c67-168">**Data type**</span></span> | <span data-ttu-id="88c67-169">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="88c67-169">String</span></span> |
| <span data-ttu-id="88c67-170">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="88c67-170">**Possible values**</span></span> | <span data-ttu-id="88c67-171">Manual</span><span class="sxs-lookup"><span data-stu-id="88c67-171">Manual</span></span> <br/> <span data-ttu-id="88c67-172">AutomaticCheck</span><span class="sxs-lookup"><span data-stu-id="88c67-172">AutomaticCheck</span></span> <br/> <span data-ttu-id="88c67-173">AutomaticDownload</span><span class="sxs-lookup"><span data-stu-id="88c67-173">AutomaticDownload</span></span> |
| <span data-ttu-id="88c67-174">**Comentário**</span><span class="sxs-lookup"><span data-stu-id="88c67-174">**Comment**</span></span> |  <span data-ttu-id="88c67-175">Observe que AutomaticDownload fará um download e instalará silenciosamente, se possível.</span><span class="sxs-lookup"><span data-stu-id="88c67-175">Note that AutomaticDownload will do a download and install silently if possible.</span></span> |


### <a name="change-whether-the-check-for-updates-button-is-enabled"></a><span data-ttu-id="88c67-176">Alterar se o botão "Verificar atualizações" está habilitado</span><span class="sxs-lookup"><span data-stu-id="88c67-176">Change whether the "Check for Updates" button is enabled</span></span>

<span data-ttu-id="88c67-177">Altere se os usuários locais poderão clicar na opção "Verificar atualizações" na interface do usuário Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="88c67-177">Change whether local users will be able to click the "Check for Updates" option in the Microsoft AutoUpdate user interface.</span></span>

|<span data-ttu-id="88c67-178">Section</span><span class="sxs-lookup"><span data-stu-id="88c67-178">Section</span></span>|<span data-ttu-id="88c67-179">Valor</span><span class="sxs-lookup"><span data-stu-id="88c67-179">Value</span></span>|
|:--|:--|
| <span data-ttu-id="88c67-180">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="88c67-180">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="88c67-181">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="88c67-181">**Key**</span></span> | <span data-ttu-id="88c67-182">EnableCheckForUpdatesButton</span><span class="sxs-lookup"><span data-stu-id="88c67-182">EnableCheckForUpdatesButton</span></span> |
| <span data-ttu-id="88c67-183">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="88c67-183">**Data type**</span></span> | <span data-ttu-id="88c67-184">Booliano</span><span class="sxs-lookup"><span data-stu-id="88c67-184">Boolean</span></span> |
| <span data-ttu-id="88c67-185">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="88c67-185">**Possible values**</span></span> | <span data-ttu-id="88c67-186">True (padrão)</span><span class="sxs-lookup"><span data-stu-id="88c67-186">True (default)</span></span> <br/> <span data-ttu-id="88c67-187">Falso</span><span class="sxs-lookup"><span data-stu-id="88c67-187">False</span></span> |


### <a name="disable-insider-checkbox"></a><span data-ttu-id="88c67-188">Desabilitar a caixa de seleção Insider</span><span class="sxs-lookup"><span data-stu-id="88c67-188">Disable Insider checkbox</span></span>

<span data-ttu-id="88c67-189">Definir como true para tornar o "Ingressar no Programa Office Insider..." caixa de seleção indisponível/esvazada para os usuários.</span><span class="sxs-lookup"><span data-stu-id="88c67-189">Set to true to make the "Join the Office Insider Program..." checkbox unavailable / greyed out to users.</span></span>

|<span data-ttu-id="88c67-190">Section</span><span class="sxs-lookup"><span data-stu-id="88c67-190">Section</span></span>|<span data-ttu-id="88c67-191">Valor</span><span class="sxs-lookup"><span data-stu-id="88c67-191">Value</span></span>|
|:--|:--|
| <span data-ttu-id="88c67-192">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="88c67-192">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="88c67-193">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="88c67-193">**Key**</span></span> | <span data-ttu-id="88c67-194">DisableInsiderCheckbox</span><span class="sxs-lookup"><span data-stu-id="88c67-194">DisableInsiderCheckbox</span></span> |
| <span data-ttu-id="88c67-195">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="88c67-195">**Data type**</span></span> | <span data-ttu-id="88c67-196">Booliano</span><span class="sxs-lookup"><span data-stu-id="88c67-196">Boolean</span></span> |
| <span data-ttu-id="88c67-197">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="88c67-197">**Possible values**</span></span> | <span data-ttu-id="88c67-198">False (padrão)</span><span class="sxs-lookup"><span data-stu-id="88c67-198">False (default)</span></span> <br/> <span data-ttu-id="88c67-199">Verdadeiro</span><span class="sxs-lookup"><span data-stu-id="88c67-199">True</span></span> |


### <a name="limit-the-telemetry-that-is-sent-from-mau"></a><span data-ttu-id="88c67-200">Limitar a telemetria enviada do MAU</span><span class="sxs-lookup"><span data-stu-id="88c67-200">Limit the telemetry that is sent from MAU</span></span>

<span data-ttu-id="88c67-201">De definida como false para enviar dados mínimos de pulsação, sem uso de aplicativo e sem detalhes do ambiente.</span><span class="sxs-lookup"><span data-stu-id="88c67-201">Set to false to send minimal heartbeat data, no application usage, and no environment details.</span></span>

|<span data-ttu-id="88c67-202">Section</span><span class="sxs-lookup"><span data-stu-id="88c67-202">Section</span></span>|<span data-ttu-id="88c67-203">Valor</span><span class="sxs-lookup"><span data-stu-id="88c67-203">Value</span></span>|
|:--|:--|
| <span data-ttu-id="88c67-204">**Domínio**</span><span class="sxs-lookup"><span data-stu-id="88c67-204">**Domain**</span></span> | `com.microsoft.autoupdate2` |
| <span data-ttu-id="88c67-205">**Tecla**</span><span class="sxs-lookup"><span data-stu-id="88c67-205">**Key**</span></span> | <span data-ttu-id="88c67-206">SendAllTelemetryEnabled</span><span class="sxs-lookup"><span data-stu-id="88c67-206">SendAllTelemetryEnabled</span></span> |
| <span data-ttu-id="88c67-207">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="88c67-207">**Data type**</span></span> | <span data-ttu-id="88c67-208">Booliano</span><span class="sxs-lookup"><span data-stu-id="88c67-208">Boolean</span></span> |
| <span data-ttu-id="88c67-209">**Valores possíveis**</span><span class="sxs-lookup"><span data-stu-id="88c67-209">**Possible values**</span></span> | <span data-ttu-id="88c67-210">True (padrão)</span><span class="sxs-lookup"><span data-stu-id="88c67-210">True (default)</span></span> <br/> <span data-ttu-id="88c67-211">Falso</span><span class="sxs-lookup"><span data-stu-id="88c67-211">False</span></span> |


## <a name="example-configuration-profile"></a><span data-ttu-id="88c67-212">Exemplo de perfil de configuração</span><span class="sxs-lookup"><span data-stu-id="88c67-212">Example configuration profile</span></span>

<span data-ttu-id="88c67-213">O seguinte perfil de configuração é usado para:</span><span class="sxs-lookup"><span data-stu-id="88c67-213">The following configuration profile is used to:</span></span>
- <span data-ttu-id="88c67-214">Colocar o dispositivo no canal Beta</span><span class="sxs-lookup"><span data-stu-id="88c67-214">Place the device in the Beta channel</span></span>
- <span data-ttu-id="88c67-215">Baixar e instalar atualizações automaticamente</span><span class="sxs-lookup"><span data-stu-id="88c67-215">Automatically download and install updates</span></span>
- <span data-ttu-id="88c67-216">Habilitar o botão "Verificar atualizações" na interface do usuário</span><span class="sxs-lookup"><span data-stu-id="88c67-216">Enable the "Check for updates" button in the user interface</span></span>
- <span data-ttu-id="88c67-217">Permitir que os usuários no dispositivo se inscrevam nos canais Insider</span><span class="sxs-lookup"><span data-stu-id="88c67-217">Allow users on the device to enroll into the Insider channels</span></span>

### <a name="jamf"></a><span data-ttu-id="88c67-218">JAMF</span><span class="sxs-lookup"><span data-stu-id="88c67-218">JAMF</span></span>

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

### <a name="intune"></a><span data-ttu-id="88c67-219">Intune</span><span class="sxs-lookup"><span data-stu-id="88c67-219">Intune</span></span>

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

<span data-ttu-id="88c67-220">Para configurar o MAU, você pode implantar esse perfil de configuração a partir da ferramenta de gerenciamento que sua empresa está usando:</span><span class="sxs-lookup"><span data-stu-id="88c67-220">To configure MAU, you can deploy this configuration profile from the management tool that your enterprise is using:</span></span>
- <span data-ttu-id="88c67-221">No JAMF, carregue esse perfil de configuração e de definir o Domínio de Preferência *como com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="88c67-221">From JAMF, upload this configuration profile and set the Preference Domain to *com.microsoft.autoupdate2*.</span></span>
- <span data-ttu-id="88c67-222">No Intune, carregue esse perfil de configuração e defina o nome do perfil de configuração personalizado *como com.microsoft.autoupdate2*.</span><span class="sxs-lookup"><span data-stu-id="88c67-222">From Intune, upload this configuration profile and set the custom configuration profile name to *com.microsoft.autoupdate2*.</span></span>

## <a name="resources"></a><span data-ttu-id="88c67-223">Recursos</span><span class="sxs-lookup"><span data-stu-id="88c67-223">Resources</span></span>

- [<span data-ttu-id="88c67-224">referência msupdate</span><span class="sxs-lookup"><span data-stu-id="88c67-224">msupdate reference</span></span>](https://docs.microsoft.com/deployoffice/mac/update-office-for-mac-using-msupdate)
