---
title: Novo Microsoft Edge
description: ''
keywords: navegador, área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 916ddaea2bc91c56944d4561771c1e807447d604
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170666"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="27f28-103">Novo aplicativo do Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="27f28-103">New Microsoft Edge app</span></span>

<span data-ttu-id="27f28-104">O novo [Microsoft Edge browser](https://www.microsoft.com/edge) oferece desempenho de classe internacional com mais privacidade, mais produtividade e mais valor ao navegar.</span><span class="sxs-lookup"><span data-stu-id="27f28-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="27f28-105">A área de trabalho gerenciada da Microsoft está oferecendo uma visualização pública da implantação do novo navegador de borda em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="27f28-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="27f28-106">Implantação inicial</span><span class="sxs-lookup"><span data-stu-id="27f28-106">Initial deployment</span></span>

<span data-ttu-id="27f28-107">Para migrar seus dispositivos de área de trabalho gerenciada da Microsoft para o novo navegador da Microsoft Edge, arquivo um tíquete de suporte de ti através do portal do Microsoft Managed desktop.</span><span class="sxs-lookup"><span data-stu-id="27f28-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="27f28-108">Implantaremos o canal de borda estável no grupo de teste quando você arquivar o tíquete e implantá-lo em cada grupo de implantação subsequente a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="27f28-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="27f28-109">Para pausar a implantação, arquivo outro tíquete pedindo que as operações sejam mantidas.</span><span class="sxs-lookup"><span data-stu-id="27f28-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="27f28-110">Atualizações para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="27f28-110">Updates to Microsoft Edge</span></span>

<span data-ttu-id="27f28-111">O Microsoft Managed desktop implanta o [canal estável](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) do Microsoft Edge que é atualizado automaticamente a cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="27f28-111">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="27f28-112">As atualizações no canal estável são distribuídas [progressivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) pelo grupo de produtos do Microsoft Edge para garantir a melhor experiência para os clientes.</span><span class="sxs-lookup"><span data-stu-id="27f28-112">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> <span data-ttu-id="27f28-113">O canal beta do Microsoft Edge não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="27f28-113">The Microsoft Edge Beta channel is not currently available.</span></span>

<span data-ttu-id="27f28-114">Para garantir que o Microsoft Edge atualize corretamente, não modifique as políticas de [atualização](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)do Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="27f28-114">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="27f28-115">Configurações gerenciadas pela área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="27f28-115">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="27f28-116">A área de trabalho gerenciada da Microsoft criou um conjunto de políticas padrão para o Microsoft Edge para proteger o navegador.</span><span class="sxs-lookup"><span data-stu-id="27f28-116">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="27f28-117">As configurações padrão do navegador são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="27f28-117">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="27f28-118">Extensões do Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="27f28-118">Microsoft Edge extensions</span></span>

<span data-ttu-id="27f28-119">A linha de base de segurança do Microsoft Edge nos dispositivos de área de trabalho gerenciada da Microsoft define duas diretivas para desabilitar todas as extensões Chrome e usuários finais seguros.</span><span class="sxs-lookup"><span data-stu-id="27f28-119">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="27f28-120">Para habilitar e implantar extensões no ambiente, Confira as configurações que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="27f28-120">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="27f28-121">Bloqueio de instalação de extensão</span><span class="sxs-lookup"><span data-stu-id="27f28-121">Extension installation blocklist</span></span>
<span data-ttu-id="27f28-122">**Valor padrão:** Todos os</span><span class="sxs-lookup"><span data-stu-id="27f28-122">**Default value:** All</span></span>

<span data-ttu-id="27f28-123">O Microsoft Managed desktop define essa política para impedir que as extensões Chrome sejam instaladas em pontos de extremidade gerenciados.</span><span class="sxs-lookup"><span data-stu-id="27f28-123">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="27f28-124">Há sassociated de risco conhecidos com o modelo de extensão Chromium, incluindo proteção contra perda de dados, privacidade e outros riscos que podem comprometer os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="27f28-124">There are known risk sassociated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="27f28-125">Permitir hosts de mensagens nativas no nível do usuário (instalado sem permissões de administrador)</span><span class="sxs-lookup"><span data-stu-id="27f28-125">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="27f28-126">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="27f28-126">**Default value:** Disabled</span></span>

<span data-ttu-id="27f28-127">Ao desabilitar essa política, o Microsoft Edge usará apenas hosts de mensagens nativos instalados no nível do sistema.</span><span class="sxs-lookup"><span data-stu-id="27f28-127">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="27f28-128">Os hosts de mensagens nativos fazem parte de extensões Chrome que permitem que o navegador interaja com outras partes do ponto de extremidade do usuário, criando uma variedade de questões de segurança.</span><span class="sxs-lookup"><span data-stu-id="27f28-128">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="27f28-129"> Secure Sockets Layer (SSL) </span><span class="sxs-lookup"><span data-stu-id="27f28-129">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="27f28-130">Versão mínima do SSL</span><span class="sxs-lookup"><span data-stu-id="27f28-130">Minimum SSL version</span></span>

<span data-ttu-id="27f28-131">**Valor padrão:** TLS mínimo 1,2 suportado</span><span class="sxs-lookup"><span data-stu-id="27f28-131">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="27f28-132">Se quiser usar o TLS menos seguro 1,1, você pode solicitar isso.</span><span class="sxs-lookup"><span data-stu-id="27f28-132">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="27f28-133">Permite que os usuários continuem na página de aviso de SSL</span><span class="sxs-lookup"><span data-stu-id="27f28-133">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="27f28-134">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="27f28-134">**Default value:** Disabled</span></span>

<span data-ttu-id="27f28-135">Não é recomendável habilitar essa configuração, pois ela permite que os usuários visitem sites com erros de SSL.</span><span class="sxs-lookup"><span data-stu-id="27f28-135">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smart-screen"></a><span data-ttu-id="27f28-136">Tela inteligente do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="27f28-136">Microsoft Defender Smart Screen</span></span>

#### <a name="configure-microsoft-defender-smartscreen"></a><span data-ttu-id="27f28-137">Configurar o Microsoft defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="27f28-137">Configure Microsoft Defender SmartScreen</span></span>

<span data-ttu-id="27f28-138">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="27f28-138">**Default value:** Enabled</span></span>

<span data-ttu-id="27f28-139">Habilitado por padrão para ajudar a proteger os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="27f28-139">Enabled by default to help protect end users.</span></span>

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="27f28-140">Prompts do Microsoft defender SmartScreen para sites</span><span class="sxs-lookup"><span data-stu-id="27f28-140">Microsoft Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="27f28-141">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="27f28-141">**Default value:** Enabled</span></span>

<span data-ttu-id="27f28-142">Não recomendamos desabilitar essa configuração, pois isso permitiria que os usuários ignorem avisos e continuassem para sites potencialmente mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="27f28-142">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="27f28-143">Evitar o bypass de avisos do Microsoft defender SmartScreen sobre downloads</span><span class="sxs-lookup"><span data-stu-id="27f28-143">Prevent bypassing of Microsoft Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="27f28-144">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="27f28-144">**Default value:** Enabled</span></span>

<span data-ttu-id="27f28-145">Não recomendamos desabilitar essa configuração, pois isso permitirá que os usuários ignorem avisos e concluam os downloads não verificados.</span><span class="sxs-lookup"><span data-stu-id="27f28-145">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="27f28-146">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="27f28-146">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="27f28-147">Configuração padrão do Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="27f28-147">Default Adobe Flash setting</span></span>

<span data-ttu-id="27f28-148">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="27f28-148">**Default value:** Disabled</span></span>

<span data-ttu-id="27f28-149">Não é recomendável usar o flash por causa dos riscos de segurança associados.</span><span class="sxs-lookup"><span data-stu-id="27f28-149">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="27f28-150">Se você ainda tiver processos que dependem do flash, defina a política **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar o flash para sites que precisam dele.</span><span class="sxs-lookup"><span data-stu-id="27f28-150">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="27f28-151">Se você não puder manter uma lista de sites permitidos para usar o flash, execute uma solicitação de alteração para alterar o valor para **clique em reproduzir**, o que permite que os usuários escolham quando for apropriado executar o flash.</span><span class="sxs-lookup"><span data-stu-id="27f28-151">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="27f28-152">Gerenciador de senhas</span><span class="sxs-lookup"><span data-stu-id="27f28-152">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="27f28-153">Habilitar o salvamento de senhas no Gerenciador de senhas</span><span class="sxs-lookup"><span data-stu-id="27f28-153">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="27f28-154">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="27f28-154">**Default value:** Disabled</span></span>

<span data-ttu-id="27f28-155">Não recomendamos permitir que os usuários finais salvem senhas em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="27f28-155">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="other-settings"></a><span data-ttu-id="27f28-156">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="27f28-156">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="27f28-157">Habilitar o isolamento de sites para cada site</span><span class="sxs-lookup"><span data-stu-id="27f28-157">Enable site isolation for every site</span></span>

<span data-ttu-id="27f28-158">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="27f28-158">**Default value:** Enabled</span></span>

<span data-ttu-id="27f28-159">Quando essa política está habilitada, os usuários não podem recusar o comportamento padrão em que cada site é executado em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="27f28-159">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="27f28-160">Esquemas de autenticação suportados</span><span class="sxs-lookup"><span data-stu-id="27f28-160">Supported authentication schemes</span></span>

<span data-ttu-id="27f28-161">**Valor padrão:** NTLM, negociar</span><span class="sxs-lookup"><span data-stu-id="27f28-161">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="27f28-162">A área de trabalho gerenciada da Microsoft não suporta esquemas de autenticação básicos ou Digest.</span><span class="sxs-lookup"><span data-stu-id="27f28-162">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="27f28-163">Importar automaticamente os dados e as configurações de outro navegador na primeira execução</span><span class="sxs-lookup"><span data-stu-id="27f28-163">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="27f28-164">**Valor padrão:** Importar automaticamente todos os tipos de DataTipo e configurações compatíveis do navegador padrão</span><span class="sxs-lookup"><span data-stu-id="27f28-164">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="27f28-165">Com essa política aplicada, a experiência de primeira execução ignorará a seção de importação, minimizando a interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="27f28-165">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="27f28-166">Os dados do navegador de versões mais antigas do Microsoft Edge serão sempre migrados silenciosamente na primeira execução, independentemente dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="27f28-166">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="27f28-167">Configurações que você gerencia</span><span class="sxs-lookup"><span data-stu-id="27f28-167">Settings you manage</span></span>

<span data-ttu-id="27f28-168">Você pode implantar qualquer configuração do Microsoft Edge não descrita anteriormente usando o perfil de modelos administrativos no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="27f28-168">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="27f28-169">Para obter detalhes, consulte [configurar as configurações de política do Microsoft Edge com o Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="27f28-169">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="27f28-170">Se você deseja avaliar uma política que não está incluída atualmente nos modelos administrativos do Microsoft Edge no Intune, é possível usar configurações personalizadas para dispositivos Windows 10 no Intune.</span><span class="sxs-lookup"><span data-stu-id="27f28-170">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="27f28-171">Habilitar extensões Chrome específicas</span><span class="sxs-lookup"><span data-stu-id="27f28-171">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="27f28-172">O modelo administrativo oferece uma configuração para implantar extensões Chrome particulares com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="27f28-172">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="27f28-173">Você pode encontrá-lo na **configuração do computador > extensões de > do Microsoft Edge > permitir que extensões específicas sejam instaladas**.</span><span class="sxs-lookup"><span data-stu-id="27f28-173">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="27f28-174">Instalar extensões silenciosamente</span><span class="sxs-lookup"><span data-stu-id="27f28-174">Install extensions silently</span></span>

<span data-ttu-id="27f28-175">Você também pode usar o modelo administrativo para definir o Microsoft Edge para instalar extensões sem alertar o usuário.</span><span class="sxs-lookup"><span data-stu-id="27f28-175">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="27f28-176">Você pode encontrá-lo na **configuração do computador > extensões de > do Microsoft Edge > controlar quais extensões são instaladas**de modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="27f28-176">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="27f28-177">Outras políticas corporativas comuns</span><span class="sxs-lookup"><span data-stu-id="27f28-177">Other common enterprise policies</span></span>

<span data-ttu-id="27f28-178">O Microsoft Edge oferece uma grande quantidade de políticas adicionais.</span><span class="sxs-lookup"><span data-stu-id="27f28-178">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="27f28-179">Estes são alguns dos mais comuns:</span><span class="sxs-lookup"><span data-stu-id="27f28-179">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="27f28-180">Configurar sites na lista de sites corporativos e no modo IE</span><span class="sxs-lookup"><span data-stu-id="27f28-180">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="27f28-181">Configurar definições de inicialização, página inicial e nova página de guias</span><span class="sxs-lookup"><span data-stu-id="27f28-181">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="27f28-182">Definir a configuração de jogo de navegação</span><span class="sxs-lookup"><span data-stu-id="27f28-182">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="27f28-183">Definir configurações de servidor proxy</span><span class="sxs-lookup"><span data-stu-id="27f28-183">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

