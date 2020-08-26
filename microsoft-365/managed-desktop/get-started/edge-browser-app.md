---
title: O novo Microsoft Edge
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
ms.openlocfilehash: 089d9dc79da568a43c1d5701d7bc52d9bed0f4f5
ms.sourcegitcommit: c76c025fe75cd9c06eccbf9c7fc887b09da36659
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903866"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="6dbfe-103">Novo aplicativo do Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6dbfe-103">New Microsoft Edge app</span></span>

<span data-ttu-id="6dbfe-104">O novo [Microsoft Edge browser](https://www.microsoft.com/edge) oferece desempenho de classe internacional com mais privacidade, mais produtividade e mais valor ao navegar.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-104">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="6dbfe-105">A área de trabalho gerenciada da Microsoft está oferecendo uma visualização pública da implantação do novo navegador de borda em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-105">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="6dbfe-106">Implantação inicial</span><span class="sxs-lookup"><span data-stu-id="6dbfe-106">Initial deployment</span></span>

<span data-ttu-id="6dbfe-107">Para migrar seus dispositivos de área de trabalho gerenciada da Microsoft para o novo navegador da Microsoft Edge, arquivo um tíquete de suporte de ti através do portal do Microsoft Managed desktop.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-107">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="6dbfe-108">Implantaremos o canal de borda estável no grupo de teste quando você arquivar o tíquete e implantá-lo em cada grupo de implantação subsequente a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-108">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="6dbfe-109">Para pausar a implantação, arquivo outro tíquete pedindo que as operações sejam mantidas.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-109">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="6dbfe-110">O [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) também está disponível na solicitação de validação representativa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-110">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="6dbfe-111">A área de trabalho gerenciada da Microsoft implantará o aplicativo conforme necessário para o teste e os primeiros grupos para que todos os usuários tenham o canal Beta além do canal estável.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-111">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="6dbfe-112">Para qualquer usuário adicional que precise acessar o canal beta, adicione-o ao grupo de **usuários beta de borda de trabalho moderna** e faça com que eles sejam instalados do portal da empresa</span><span class="sxs-lookup"><span data-stu-id="6dbfe-112">For any additional users who need access to the Beta Channel please add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="6dbfe-113">Atualizações para o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6dbfe-113">Updates to Microsoft Edge</span></span>

<span data-ttu-id="6dbfe-114">O Microsoft Managed desktop implanta o [canal estável](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) do Microsoft Edge que é atualizado automaticamente a cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-114">Microsoft Managed Desktop deploys the [Stable channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge which is auto-updated about every six weeks.</span></span> <span data-ttu-id="6dbfe-115">As atualizações no canal estável são distribuídas [progressivamente](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) pelo grupo de produtos do Microsoft Edge para garantir a melhor experiência para os clientes.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-115">Updates on the Stable channel are rolled out [progressively](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="6dbfe-116">O [canal beta](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) é implantado para dispositivos nos primeiros grupos e teste para validação representativa dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-116">The [Beta Channel](https://docs.microsoft.com/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="6dbfe-117">Este canal é totalmente compatível e é atualizado automaticamente com novos recursos aproximadamente a cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-117">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="6dbfe-118">Para garantir que o Microsoft Edge atualize corretamente, não modifique as políticas de [atualização](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)do Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-118">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="microsoft-edge-beta-channel"></a><span data-ttu-id="6dbfe-119">Canal beta do Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6dbfe-119">Microsoft Edge Beta Channel</span></span>


## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="6dbfe-120">Configurações gerenciadas pela área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6dbfe-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="6dbfe-121">A área de trabalho gerenciada da Microsoft criou um conjunto de políticas padrão para o Microsoft Edge para proteger o navegador.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="6dbfe-122">As configurações padrão do navegador são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="6dbfe-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="6dbfe-123">Extensões do Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6dbfe-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="6dbfe-124">A linha de base de segurança do Microsoft Edge nos dispositivos de área de trabalho gerenciada da Microsoft define duas diretivas para desabilitar todas as extensões Chrome e usuários finais seguros.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure end users.</span></span> <span data-ttu-id="6dbfe-125">Para habilitar e implantar extensões no ambiente, Confira as configurações que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="6dbfe-126">Bloqueio de instalação de extensão</span><span class="sxs-lookup"><span data-stu-id="6dbfe-126">Extension installation blocklist</span></span>
<span data-ttu-id="6dbfe-127">**Valor padrão:** Todos os</span><span class="sxs-lookup"><span data-stu-id="6dbfe-127">**Default value:** All</span></span>

<span data-ttu-id="6dbfe-128">O Microsoft Managed desktop define essa política para impedir que as extensões Chrome sejam instaladas em pontos de extremidade gerenciados.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="6dbfe-129">Há riscos conhecidos associados ao modelo de extensão do Chromium, incluindo proteção contra perda de dados, privacidade e outros riscos que podem comprometer os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="6dbfe-130">Permitir hosts de mensagens nativas no nível do usuário (instalado sem permissões de administrador)</span><span class="sxs-lookup"><span data-stu-id="6dbfe-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="6dbfe-131">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="6dbfe-131">**Default value:** Disabled</span></span>

<span data-ttu-id="6dbfe-132">Ao desabilitar essa política, o Microsoft Edge usará apenas hosts de mensagens nativos instalados no nível do sistema.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="6dbfe-133">Os hosts de mensagens nativos fazem parte de extensões Chrome que permitem que o navegador interaja com outras partes do ponto de extremidade do usuário, criando uma variedade de questões de segurança.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-133">Native messaging hosts are a part of Chrome extensions which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-ssl"></a><span data-ttu-id="6dbfe-134"> Secure Sockets Layer (SSL) </span><span class="sxs-lookup"><span data-stu-id="6dbfe-134">Secure Sockets Layer (SSL)</span></span>

#### <a name="minimum-ssl-version"></a><span data-ttu-id="6dbfe-135">Versão mínima do SSL</span><span class="sxs-lookup"><span data-stu-id="6dbfe-135">Minimum SSL version</span></span>

<span data-ttu-id="6dbfe-136">**Valor padrão:** TLS mínimo 1,2 suportado</span><span class="sxs-lookup"><span data-stu-id="6dbfe-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="6dbfe-137">Se quiser usar o TLS menos seguro 1,1, você pode solicitar isso.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-137">If you want to use the less secure TLS 1.1, you can request this.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="6dbfe-138">Permite que os usuários continuem na página de aviso de SSL</span><span class="sxs-lookup"><span data-stu-id="6dbfe-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="6dbfe-139">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="6dbfe-139">**Default value:** Disabled</span></span>

<span data-ttu-id="6dbfe-140">Não é recomendável habilitar essa configuração, pois ela permite que os usuários visitem sites com erros de SSL.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-140">We don't recommend enabling this setting since it allows users to visit sites with SSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="6dbfe-141">Microsoft defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="6dbfe-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="6dbfe-142">Configurar o Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="6dbfe-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="6dbfe-143">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="6dbfe-143">**Default value:** Enabled</span></span>

<span data-ttu-id="6dbfe-144">Habilitado por padrão para ajudar a proteger os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-144">Enabled by default to help protect end users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="6dbfe-145">Prompts do Windows Defender SmartScreen para sites</span><span class="sxs-lookup"><span data-stu-id="6dbfe-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="6dbfe-146">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="6dbfe-146">**Default value:** Enabled</span></span>

<span data-ttu-id="6dbfe-147">Não recomendamos desabilitar essa configuração, pois isso permitiria que os usuários ignorem avisos e continuassem para sites potencialmente mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="6dbfe-148">Evitar o bypass de avisos do Windows Defender SmartScreen sobre downloads</span><span class="sxs-lookup"><span data-stu-id="6dbfe-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="6dbfe-149">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="6dbfe-149">**Default value:** Enabled</span></span>

<span data-ttu-id="6dbfe-150">Não recomendamos desabilitar essa configuração, pois isso permitirá que os usuários ignorem avisos e concluam os downloads não verificados.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="6dbfe-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="6dbfe-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="6dbfe-152">Configuração padrão do Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="6dbfe-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="6dbfe-153">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="6dbfe-153">**Default value:** Disabled</span></span>

<span data-ttu-id="6dbfe-154">Não é recomendável usar o flash por causa dos riscos de segurança associados.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="6dbfe-155">Se você ainda tiver processos que dependem do flash, defina a política **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar o flash para sites que precisam dele.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-155">If you still have processes which depend on Flash, set the **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites which need it.</span></span> <span data-ttu-id="6dbfe-156">Se você não puder manter uma lista de sites permitidos para usar o flash, execute uma solicitação de alteração para alterar o valor para **clique em reproduzir**, o que permite que os usuários escolham quando for apropriado executar o flash.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="6dbfe-157">Gerenciador de senhas</span><span class="sxs-lookup"><span data-stu-id="6dbfe-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="6dbfe-158">Habilitar o salvamento de senhas no Gerenciador de senhas</span><span class="sxs-lookup"><span data-stu-id="6dbfe-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="6dbfe-159">**Valor padrão:** Deficiência</span><span class="sxs-lookup"><span data-stu-id="6dbfe-159">**Default value:** Disabled</span></span>

<span data-ttu-id="6dbfe-160">Não recomendamos permitir que os usuários finais salvem senhas em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-160">We do not recommend allowing end users to save passwords on their device.</span></span>

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="6dbfe-161">Modo do Internet Explorer no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6dbfe-161">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="6dbfe-162">O modo IE no Microsoft Edge facilita o uso de todos os sites que sua organização precisa em um único navegador.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-162">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="6dbfe-163">Ele usa o mecanismo integrado do Chromium para sites que são compatíveis com o mecanismo de renderização do Chromium e usa o mecanismo Trident MSHTML do Internet Explorer 11 (IE11) para sites que não estão ou que têm dependências na funcionalidade do IE.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-163">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> <span data-ttu-id="6dbfe-164">[Saiba mais] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span><span class="sxs-lookup"><span data-stu-id="6dbfe-164">[Learn more] (https://docs.microsoft.com/DeployEdge/edge-ie-mode)</span></span> 

<span data-ttu-id="6dbfe-165">A área de trabalho gerenciada da Microsoft habilita o modo do Internet Explorer para seus dispositivos por padrão</span><span class="sxs-lookup"><span data-stu-id="6dbfe-165">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="6dbfe-166">Integração de modo do Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6dbfe-166">Internet Explorer mode integration</span></span>
<span data-ttu-id="6dbfe-167">**Valor padrão:** Modo do Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6dbfe-167">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="6dbfe-168">Por padrão, os dispositivos são definidos para usar o modo do Internet Explorer, mas você pode defini-los para abrir sites em uma janela do Internet Explorer 11 independente.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-168">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="6dbfe-169">Para alterar isso, arquivo a solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-169">To change this, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="6dbfe-170">Adicionar sites à lista de sites do modo empresarial</span><span class="sxs-lookup"><span data-stu-id="6dbfe-170">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="6dbfe-171">Para que os sites sejam abertos no modo do Internet Explorer, você deve incluí-los na [lista de sites corporativos](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span><span class="sxs-lookup"><span data-stu-id="6dbfe-171">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](https://docs.microsoft.com/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="6dbfe-172">Manter e implantar a lista de sites corporativos é sua responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-172">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="6dbfe-173">Para obter detalhes, consulte [Configurar usando a política de lista de sites do modo empresarial](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="6dbfe-173">For details, see [Configure using the Configure Enterprise Mode Site List policy](https://docs.microsoft.com/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="6dbfe-174">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="6dbfe-174">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="6dbfe-175">Habilitar o isolamento de sites para cada site</span><span class="sxs-lookup"><span data-stu-id="6dbfe-175">Enable site isolation for every site</span></span>

<span data-ttu-id="6dbfe-176">**Valor padrão:** Permiti</span><span class="sxs-lookup"><span data-stu-id="6dbfe-176">**Default value:** Enabled</span></span>

<span data-ttu-id="6dbfe-177">Quando essa política está habilitada, os usuários não podem recusar o comportamento padrão em que cada site é executado em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-177">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="6dbfe-178">Esquemas de autenticação suportados</span><span class="sxs-lookup"><span data-stu-id="6dbfe-178">Supported authentication schemes</span></span>

<span data-ttu-id="6dbfe-179">**Valor padrão:** NTLM, negociar</span><span class="sxs-lookup"><span data-stu-id="6dbfe-179">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="6dbfe-180">A área de trabalho gerenciada da Microsoft não suporta esquemas de autenticação básicos ou Digest.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-180">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="6dbfe-181">Importar automaticamente os dados e as configurações de outro navegador na primeira execução</span><span class="sxs-lookup"><span data-stu-id="6dbfe-181">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="6dbfe-182">**Valor padrão:** Importar automaticamente todos os tipos de DataTipo e configurações compatíveis do navegador padrão</span><span class="sxs-lookup"><span data-stu-id="6dbfe-182">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="6dbfe-183">Com essa política aplicada, a experiência de primeira execução ignorará a seção de importação, minimizando a interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-183">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="6dbfe-184">Os dados do navegador de versões mais antigas do Microsoft Edge serão sempre migrados silenciosamente na primeira execução, independentemente dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-184">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="6dbfe-185">Configurações que você gerencia</span><span class="sxs-lookup"><span data-stu-id="6dbfe-185">Settings you manage</span></span>

<span data-ttu-id="6dbfe-186">Você pode implantar qualquer configuração do Microsoft Edge não descrita anteriormente usando o perfil de modelos administrativos no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-186">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="6dbfe-187">Para obter detalhes, consulte [configurar as configurações de política do Microsoft Edge com o Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="6dbfe-187">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="6dbfe-188">Se você deseja avaliar uma política que não está incluída atualmente nos modelos administrativos do Microsoft Edge no Intune, é possível usar configurações personalizadas para dispositivos Windows 10 no Intune.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-188">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="6dbfe-189">Habilitar extensões Chrome específicas</span><span class="sxs-lookup"><span data-stu-id="6dbfe-189">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="6dbfe-190">O modelo administrativo oferece uma configuração para implantar extensões Chrome particulares com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-190">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="6dbfe-191">Você pode encontrá-lo na **configuração do computador > extensões de > do Microsoft Edge > permitir que extensões específicas sejam instaladas**.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-191">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="6dbfe-192">Instalar extensões silenciosamente</span><span class="sxs-lookup"><span data-stu-id="6dbfe-192">Install extensions silently</span></span>

<span data-ttu-id="6dbfe-193">Você também pode usar o modelo administrativo para definir o Microsoft Edge para instalar extensões sem alertar o usuário.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-193">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="6dbfe-194">Você pode encontrá-lo na **configuração do computador > extensões de > do Microsoft Edge > controlar quais extensões são instaladas**de modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-194">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="6dbfe-195">Políticas de atualização do Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6dbfe-195">Microsoft Edge update policies</span></span>
<span data-ttu-id="6dbfe-196">Para garantir que o Microsoft Edge atualize corretamente, não modifique as políticas de [atualização](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)do Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-196">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="6dbfe-197">Outras políticas corporativas comuns</span><span class="sxs-lookup"><span data-stu-id="6dbfe-197">Other common enterprise policies</span></span>

<span data-ttu-id="6dbfe-198">O Microsoft Edge oferece uma grande quantidade de políticas adicionais.</span><span class="sxs-lookup"><span data-stu-id="6dbfe-198">Microsoft Edge offers a great many additional policies.</span></span> <span data-ttu-id="6dbfe-199">Estes são alguns dos mais comuns:</span><span class="sxs-lookup"><span data-stu-id="6dbfe-199">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="6dbfe-200">Configurar sites na lista de sites corporativos e no modo IE</span><span class="sxs-lookup"><span data-stu-id="6dbfe-200">Configure Sites on the Enterprise Site List and IE Mode</span></span>](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="6dbfe-201">Configurar definições de inicialização, página inicial e nova página de guias</span><span class="sxs-lookup"><span data-stu-id="6dbfe-201">Configure start-up, home page, and new tab page settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="6dbfe-202">Definir a configuração de jogo de navegação</span><span class="sxs-lookup"><span data-stu-id="6dbfe-202">Configure Surf game setting</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="6dbfe-203">Definir configurações de servidor proxy</span><span class="sxs-lookup"><span data-stu-id="6dbfe-203">Configure proxy server settings</span></span>](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

