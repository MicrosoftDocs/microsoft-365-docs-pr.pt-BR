---
title: O novo Microsoft Edge
description: Explica como o novo navegador de Borda é implantado e atualizado
keywords: browser, Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2bf1fab504ae77a1e66235f49333c3b123e38904
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822245"
---
# <a name="new-microsoft-edge-app"></a><span data-ttu-id="50d27-104">Novo Microsoft Edge app</span><span class="sxs-lookup"><span data-stu-id="50d27-104">New Microsoft Edge app</span></span>

<span data-ttu-id="50d27-105">O novo [Microsoft Edge oferece](https://www.microsoft.com/edge) um desempenho de classe mundial com mais privacidade, mais produtividade e mais valor enquanto você navega.</span><span class="sxs-lookup"><span data-stu-id="50d27-105">The new [Microsoft Edge browser](https://www.microsoft.com/edge) provides world-class performance with more privacy, more productivity, and more value while you browse.</span></span> <span data-ttu-id="50d27-106">Área de Trabalho Gerenciada da Microsoft está oferecendo uma visualização pública da implantação do novo navegador de Borda em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="50d27-106">Microsoft Managed Desktop is offering a public preview of deployment of the new Edge browser in your environment.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="50d27-107">Implantação inicial</span><span class="sxs-lookup"><span data-stu-id="50d27-107">Initial deployment</span></span>

<span data-ttu-id="50d27-108">Para migrar seus dispositivos Área de Trabalho Gerenciada da Microsoft para o novo navegador Microsoft Edge, arquiva um Tíquete de Suporte de IT por meio do portal Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="50d27-108">To migrate your Microsoft Managed Desktop devices to the new Microsoft Edge browser, file an IT Support Ticket through the Microsoft Managed Desktop Portal.</span></span> <span data-ttu-id="50d27-109">Implantaremos o canal Estável de Borda no Grupo de Teste quando você arquivar o tíquete e implantá-lo em cada grupo de implantação subsequente a cada 24 horas.</span><span class="sxs-lookup"><span data-stu-id="50d27-109">We will deploy the Edge Stable channel to the Test Group when you file the ticket, and then deploy it in each subsequent deployment group every 24 hours.</span></span> <span data-ttu-id="50d27-110">Para pausar a implantação, arquiva outro tíquete solicitando a ressarção de Operações.</span><span class="sxs-lookup"><span data-stu-id="50d27-110">To pause the deployment, file another ticket asking Operations to hold.</span></span>

<span data-ttu-id="50d27-111">O [Canal Beta](/deployedge/microsoft-edge-channels#beta-channel) também está disponível mediante solicitação de validação representativa em sua organização.</span><span class="sxs-lookup"><span data-stu-id="50d27-111">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is also available upon request for representative validation within your organization.</span></span> <span data-ttu-id="50d27-112">Área de Trabalho Gerenciada da Microsoft implantará o aplicativo conforme necessário para o Test and First Groups para que todos esses usuários tenham o Canal Beta, além do Canal Estável.</span><span class="sxs-lookup"><span data-stu-id="50d27-112">Microsoft Managed Desktop will deploy the application as required to the Test and First Groups so that all of those users have the Beta Channel in addition to the Stable Channel.</span></span> <span data-ttu-id="50d27-113">Para qualquer outro usuário que precise de acesso ao Canal Beta, adicione-os ao grupo Local de Trabalho Moderno - Usuários **Beta** de Borda e instale-o a partir do Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="50d27-113">For any other users who need access to the Beta Channel, add them to the **Modern Workplace - Edge Beta Users** group and have them install it from the Company Portal</span></span>

## <a name="updates-to-microsoft-edge"></a><span data-ttu-id="50d27-114">Atualizações para Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="50d27-114">Updates to Microsoft Edge</span></span>

<span data-ttu-id="50d27-115">Área de Trabalho Gerenciada da Microsoft implanta o [canal estável](/deployedge/microsoft-edge-channels#stable-channel) do Microsoft Edge, que é atualizado automaticamente a cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="50d27-115">Microsoft Managed Desktop deploys the [Stable channel](/deployedge/microsoft-edge-channels#stable-channel) of Microsoft Edge, which is auto-updated about every six weeks.</span></span> <span data-ttu-id="50d27-116">As atualizações no canal Estável [](/deployedge/microsoft-edge-update-progressive-rollout) são roladas progressivamente pelo grupo de produtos Microsoft Edge para garantir a melhor experiência para os clientes.</span><span class="sxs-lookup"><span data-stu-id="50d27-116">Updates on the Stable channel are rolled out [progressively](/deployedge/microsoft-edge-update-progressive-rollout) by the Microsoft Edge product group in order to ensure the best experience for customers.</span></span> 

<span data-ttu-id="50d27-117">O [Canal Beta é](/deployedge/microsoft-edge-channels#beta-channel) implantado em dispositivos nos grupos Test e First para validação representativa dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="50d27-117">The [Beta Channel](/deployedge/microsoft-edge-channels#beta-channel) is deployed to devices in both the Test and First groups for representative validation within the organization.</span></span> <span data-ttu-id="50d27-118">Esse canal tem suporte total e é atualizado automaticamente com novos recursos aproximadamente a cada seis semanas.</span><span class="sxs-lookup"><span data-stu-id="50d27-118">This channel is fully supported and is auto-updated with new features approximately every six weeks.</span></span>

<span data-ttu-id="50d27-119">Para garantir que Microsoft Edge atualizações corretamente, não modifique as políticas de Microsoft Edge [de atualização.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="50d27-119">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>



## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="50d27-120">Configurações gerenciado por Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="50d27-120">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="50d27-121">Área de Trabalho Gerenciada da Microsoft criou um conjunto padrão de políticas para Microsoft Edge proteger o navegador.</span><span class="sxs-lookup"><span data-stu-id="50d27-121">Microsoft Managed Desktop has created a default set of policies for Microsoft Edge to secure the browser.</span></span> <span data-ttu-id="50d27-122">As configurações padrão do navegador são as seguinte:</span><span class="sxs-lookup"><span data-stu-id="50d27-122">The default browser settings are as follows:</span></span>

### <a name="microsoft-edge-extensions"></a><span data-ttu-id="50d27-123">Microsoft Edge extensões</span><span class="sxs-lookup"><span data-stu-id="50d27-123">Microsoft Edge extensions</span></span>

<span data-ttu-id="50d27-124">A linha de base de segurança para Microsoft Edge em Área de Trabalho Gerenciada da Microsoft define duas políticas para desabilitar todas as extensões do Chrome e proteger usuários.</span><span class="sxs-lookup"><span data-stu-id="50d27-124">The security baseline for Microsoft Edge on Microsoft Managed Desktop devices sets two policies to disable all Chrome extensions and secure users.</span></span> <span data-ttu-id="50d27-125">Para habilitar e implantar extensões em seu ambiente, consulte Configurações gerenciar.</span><span class="sxs-lookup"><span data-stu-id="50d27-125">To enable and deploy extensions in your environment, see Settings you manage.</span></span> 

#### <a name="extension-installation-blocklist"></a><span data-ttu-id="50d27-126">Lista de bloqueios de instalação de extensão</span><span class="sxs-lookup"><span data-stu-id="50d27-126">Extension installation blocklist</span></span>
<span data-ttu-id="50d27-127">**Valor padrão:** Todos</span><span class="sxs-lookup"><span data-stu-id="50d27-127">**Default value:** All</span></span>

<span data-ttu-id="50d27-128">Área de Trabalho Gerenciada da Microsoft essa política para impedir que extensões do Chrome seja instaladas em pontos de extremidade gerenciados.</span><span class="sxs-lookup"><span data-stu-id="50d27-128">Microsoft Managed Desktop sets this policy to prevent Chrome extensions from being installed on managed endpoints.</span></span> <span data-ttu-id="50d27-129">Há riscos conhecidos associados ao modelo de extensão Chromium, incluindo proteção contra perda de dados, privacidade e outros riscos que podem comprometer dispositivos.</span><span class="sxs-lookup"><span data-stu-id="50d27-129">There are known risks associated with the Chromium extension model including data loss protection, privacy, and other risks that can compromise devices.</span></span> 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a><span data-ttu-id="50d27-130">Permitir hosts de mensagens nativos no nível do usuário (instalados sem permissões de administrador)</span><span class="sxs-lookup"><span data-stu-id="50d27-130">Allow user-level native messaging hosts (installed without admin permissions)</span></span>

<span data-ttu-id="50d27-131">**Valor padrão:** Desabilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-131">**Default value:** Disabled</span></span>

<span data-ttu-id="50d27-132">Ao desabilitar essa política, Microsoft Edge usará somente hosts de mensagens nativos instalados no nível do sistema.</span><span class="sxs-lookup"><span data-stu-id="50d27-132">By disabling this policy, Microsoft Edge will only use native messaging hosts installed on the system level.</span></span> <span data-ttu-id="50d27-133">Hosts de mensagens nativos fazem parte das extensões do Chrome, que permitem que o navegador interaja com outras partes do ponto de extremidade do usuário, criando uma variedade de preocupações de segurança.</span><span class="sxs-lookup"><span data-stu-id="50d27-133">Native messaging hosts are a part of Chrome extensions, which allow for the browser to interact with other parts of user’s endpoint, creating a variety of security concerns.</span></span>  

### <a name="secure-sockets-layer-tlsssl"></a><span data-ttu-id="50d27-134">Camada de Soquetes Seguros (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="50d27-134">Secure Sockets Layer (TLS/SSL)</span></span>

#### <a name="minimum-tls-version"></a><span data-ttu-id="50d27-135">Versão TLS mínima</span><span class="sxs-lookup"><span data-stu-id="50d27-135">Minimum TLS version</span></span>

<span data-ttu-id="50d27-136">**Valor padrão:** TLS 1.2 mínimo suportado</span><span class="sxs-lookup"><span data-stu-id="50d27-136">**Default value:** Minimum TLS 1.2 supported</span></span>

<span data-ttu-id="50d27-137">Se você quiser usar o TLS 1.1 menos seguro, poderá fazer uma solicitação para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="50d27-137">If you want to use the less secure TLS 1.1, you can file a request to do so.</span></span>

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a><span data-ttu-id="50d27-138">Permite que os usuários prossigam da página de aviso SSL</span><span class="sxs-lookup"><span data-stu-id="50d27-138">Allows users to proceed from the SSL warning page</span></span>

<span data-ttu-id="50d27-139">**Valor padrão:** Desabilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-139">**Default value:** Disabled</span></span>

<span data-ttu-id="50d27-140">Não recomendamos a habilitação dessa configuração, pois permite que os usuários visite sites com erros TSL.</span><span class="sxs-lookup"><span data-stu-id="50d27-140">We don't recommend enabling this setting since it allows users to visit sites with TSL errors.</span></span>

### <a name="microsoft-defender-smartscreen"></a><span data-ttu-id="50d27-141">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="50d27-141">Microsoft Defender SmartScreen</span></span>

#### <a name="configure-windows-defender-smartscreen"></a><span data-ttu-id="50d27-142">Configurar Windows Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="50d27-142">Configure Windows Defender SmartScreen</span></span>

<span data-ttu-id="50d27-143">**Valor padrão:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-143">**Default value:** Enabled</span></span>

<span data-ttu-id="50d27-144">Habilitado por padrão para ajudar a proteger os usuários.</span><span class="sxs-lookup"><span data-stu-id="50d27-144">Enabled by default to help protect users.</span></span>

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a><span data-ttu-id="50d27-145">Windows Defender Prompts smartScreen para sites</span><span class="sxs-lookup"><span data-stu-id="50d27-145">Windows Defender SmartScreen prompts for sites</span></span>

<span data-ttu-id="50d27-146">**Valor padrão:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-146">**Default value:** Enabled</span></span>

<span data-ttu-id="50d27-147">Não recomendamos desabilitar essa configuração, pois isso permitiria que os usuários ignorassem os avisos e continuassem a sites potencialmente mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="50d27-147">We do not recommend disabling this setting since that would allow users to ignore warnings and continue to potentially malicious sites.</span></span>

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a><span data-ttu-id="50d27-148">Impedir o desvio de Windows Defender avisos do SmartScreen sobre downloads</span><span class="sxs-lookup"><span data-stu-id="50d27-148">Prevent bypassing of Windows Defender SmartScreen warnings about downloads</span></span>

<span data-ttu-id="50d27-149">**Valor padrão:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-149">**Default value:** Enabled</span></span>

<span data-ttu-id="50d27-150">Não recomendamos desabilitar essa configuração, pois isso permitiria aos usuários ignorar avisos e concluir downloads não verificados.</span><span class="sxs-lookup"><span data-stu-id="50d27-150">We do not recommend disabling this setting since that would allow users to ignore warnings and complete unverified downloads.</span></span>

### <a name="adobe-flash"></a><span data-ttu-id="50d27-151">Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="50d27-151">Adobe Flash</span></span>

#### <a name="default-adobe-flash-setting"></a><span data-ttu-id="50d27-152">Configuração padrão do Adobe Flash</span><span class="sxs-lookup"><span data-stu-id="50d27-152">Default Adobe Flash setting</span></span>

<span data-ttu-id="50d27-153">**Valor padrão:** Desabilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-153">**Default value:** Disabled</span></span>

<span data-ttu-id="50d27-154">Não recomendamos o uso do Flash devido aos riscos de segurança associados.</span><span class="sxs-lookup"><span data-stu-id="50d27-154">We don't recommend using Flash because of associated security risks.</span></span> <span data-ttu-id="50d27-155">Se você ainda tiver processos que dependem do Flash, defina a **[política PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** para habilitar o Flash para sites que precisam dele.</span><span class="sxs-lookup"><span data-stu-id="50d27-155">If you still have processes that depend on Flash, set the **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** policy to enable Flash for sites that need it.</span></span> <span data-ttu-id="50d27-156">Se você não puder manter uma lista de sites permitidos para usar o Flash, arquiva uma solicitação de alteração para alterar o valor para **Clique** para Reproduzir , o que permite que os usuários escolham quando é apropriado executar o Flash.</span><span class="sxs-lookup"><span data-stu-id="50d27-156">If you can't maintain an allowed list of sites to use Flash, file a change request to change the value to **Click to Play**, which allows users choose when it's appropriate to run Flash.</span></span>

### <a name="password-manager"></a><span data-ttu-id="50d27-157">Gerenciador de senhas</span><span class="sxs-lookup"><span data-stu-id="50d27-157">Password manager</span></span>

#### <a name="enable-saving-passwords-to-the-password-manager"></a><span data-ttu-id="50d27-158">Habilitar salvar senhas para o gerenciador de senhas</span><span class="sxs-lookup"><span data-stu-id="50d27-158">Enable saving passwords to the password manager</span></span>

<span data-ttu-id="50d27-159">**Valor padrão:** Desabilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-159">**Default value:** Disabled</span></span>

<span data-ttu-id="50d27-160">O gerenciador de senhas está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="50d27-160">The password manager is disabled by default.</span></span> <span data-ttu-id="50d27-161">Se você estiver como esse recurso habilitado, arquiva uma solicitação de suporte e nossos engenheiros de serviço podem habilitar a configuração em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="50d27-161">If you's like this feature enabled, file a support request and our service engineers can enable the setting in your environment.</span></span> 

### <a name="internet-explorer-mode-in-microsoft-edge"></a><span data-ttu-id="50d27-162">Modo Internet Explorer no Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="50d27-162">Internet Explorer Mode in Microsoft Edge</span></span>
<span data-ttu-id="50d27-163">O modo IE no Microsoft Edge facilita o uso de todos os sites de que sua organização precisa em um único navegador.</span><span class="sxs-lookup"><span data-stu-id="50d27-163">IE mode on Microsoft Edge makes it easy to use all of the sites your organization needs in a single browser.</span></span> <span data-ttu-id="50d27-164">Ele usa o mecanismo de Chromium integrado para sites compatíveis com o mecanismo de renderização Chromium e usa o mecanismo Trident MSHTML do Internet Explorer 11 (IE11) para sites que não são ou têm dependências da funcionalidade do IE.</span><span class="sxs-lookup"><span data-stu-id="50d27-164">It uses the integrated Chromium engine for sites that are compatible with the Chromium rendering engine and it uses the Trident MSHTML engine from Internet Explorer 11 (IE11) for sites that aren't or have dependencies on IE functionality.</span></span> [<span data-ttu-id="50d27-165">Saiba Mais</span><span class="sxs-lookup"><span data-stu-id="50d27-165">Learn more</span></span>](/DeployEdge/edge-ie-mode) 

<span data-ttu-id="50d27-166">Área de Trabalho Gerenciada da Microsoft habilita o modo Internet Explorer para seus dispositivos por padrão</span><span class="sxs-lookup"><span data-stu-id="50d27-166">Microsoft Managed Desktop enables Internet Explorer mode for your devices by default</span></span> 

#### <a name="internet-explorer-mode-integration"></a><span data-ttu-id="50d27-167">Integração do modo Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="50d27-167">Internet Explorer mode integration</span></span>
<span data-ttu-id="50d27-168">**Valor padrão:** Modo Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="50d27-168">**Default Value:** Internet Explorer mode</span></span>

<span data-ttu-id="50d27-169">Por padrão, os dispositivos são definidos para usar o modo Internet Explorer, mas você pode defini-los para abrir sites em uma janela autônoma do Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="50d27-169">By default, devices are set to use Internet Explorer mode, but you can set them to open sites in a standalone Internet Explorer 11 window instead.</span></span> <span data-ttu-id="50d27-170">Para alterar esse comportamento, arquivar uma solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="50d27-170">To change this behavior, file a support request.</span></span>

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a><span data-ttu-id="50d27-171">Adicionar sites à lista de sites Enterprise modo de usuário</span><span class="sxs-lookup"><span data-stu-id="50d27-171">Add sites to the Enterprise Mode Site list</span></span>
<span data-ttu-id="50d27-172">Para que os sites abram no modo Internet Explorer, você deve incluí-los na lista [Enterprise Site.](/DeployEdge/edge-ie-mode-sitelist)</span><span class="sxs-lookup"><span data-stu-id="50d27-172">For sites to open in Internet Explorer mode you must include them on the [Enterprise Site list](/DeployEdge/edge-ie-mode-sitelist).</span></span> <span data-ttu-id="50d27-173">Manter e implantar a lista Enterprise Site é sua responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="50d27-173">Maintaining and deploying the Enterprise Site list is your responsibility.</span></span> <span data-ttu-id="50d27-174">Para obter detalhes, consulte [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span><span class="sxs-lookup"><span data-stu-id="50d27-174">For details, see [Configure using the Configure Enterprise Mode Site List policy](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)</span></span>

### <a name="other-settings"></a><span data-ttu-id="50d27-175">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="50d27-175">Other settings</span></span>

#### <a name="enable-site-isolation-for-every-site"></a><span data-ttu-id="50d27-176">Habilitar o isolamento de site para cada site</span><span class="sxs-lookup"><span data-stu-id="50d27-176">Enable site isolation for every site</span></span>

<span data-ttu-id="50d27-177">**Valor padrão:** Habilitado</span><span class="sxs-lookup"><span data-stu-id="50d27-177">**Default value:** Enabled</span></span>

<span data-ttu-id="50d27-178">Quando essa política é habilitada, os usuários não podem optar pelo comportamento padrão no qual cada site é executado em seu próprio processo.</span><span class="sxs-lookup"><span data-stu-id="50d27-178">When this policy is enabled, users can't opt out of the default behavior in which each site runs in its own process.</span></span>

#### <a name="supported-authentication-schemes"></a><span data-ttu-id="50d27-179">Esquemas de autenticação com suporte</span><span class="sxs-lookup"><span data-stu-id="50d27-179">Supported authentication schemes</span></span>

<span data-ttu-id="50d27-180">**Valor padrão:** NTLM, Negociar</span><span class="sxs-lookup"><span data-stu-id="50d27-180">**Default value:** NTLM, Negotiate</span></span>

<span data-ttu-id="50d27-181">Área de Trabalho Gerenciada da Microsoft não dá suporte a esquemas de Autenticação Básica ou Digest.</span><span class="sxs-lookup"><span data-stu-id="50d27-181">Microsoft Managed Desktop doesn't support Basic or Digest Authentication schemes.</span></span>

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a><span data-ttu-id="50d27-182">Importar automaticamente os dados e configurações de outro navegador na primeira executar</span><span class="sxs-lookup"><span data-stu-id="50d27-182">Automatically import another browser's data and settings at first run</span></span>

<span data-ttu-id="50d27-183">**Valor padrão:** Importar automaticamente todos os tipos de dados e configurações com suporte do navegador padrão</span><span class="sxs-lookup"><span data-stu-id="50d27-183">**Default value:** Automatically import all supported datatypes and settings from the default browser</span></span> 

<span data-ttu-id="50d27-184">Com essa política aplicada, a Experiência de Primeira Executar ignorará a seção de importação, minimizando a interação do usuário.</span><span class="sxs-lookup"><span data-stu-id="50d27-184">With this policy applied, the First Run Experience will skip the import section, minimizing user interaction.</span></span> <span data-ttu-id="50d27-185">Os dados do navegador de versões mais antigas Microsoft Edge sempre serão migrados silenciosamente na primeira executar, independentemente dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="50d27-185">The browser data from older versions of Microsoft Edge will always be silently migrated at the first run, regardless of this setting.</span></span> 


## <a name="settings-you-manage"></a><span data-ttu-id="50d27-186">Configurações gerenciar</span><span class="sxs-lookup"><span data-stu-id="50d27-186">Settings you manage</span></span>

<span data-ttu-id="50d27-187">Você pode implantar qualquer configuração Microsoft Edge não descritas anteriormente usando o perfil Modelos Administrativos no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="50d27-187">You can deploy any Microsoft Edge settings not previously described by using the Administrative Templates profile in Microsoft Intune.</span></span> <span data-ttu-id="50d27-188">Para obter detalhes, [consulte Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune).</span><span class="sxs-lookup"><span data-stu-id="50d27-188">For details, see [Configure Microsoft Edge policy settings with Microsoft Intune](/deployedge/configure-edge-with-intune).</span></span> <span data-ttu-id="50d27-189">Se você quiser avaliar uma política que não está incluída no Microsoft Edge Modelos Administrativos no Intune, você pode usar configurações personalizadas para dispositivos Windows 10 no Intune.</span><span class="sxs-lookup"><span data-stu-id="50d27-189">If you want to evaluate a policy that is not currently included in the Microsoft Edge Administrative Templates in Intune, you can use custom settings for Windows 10 devices in Intune.</span></span>

### <a name="enabling-specific-chrome-extensions"></a><span data-ttu-id="50d27-190">Habilitando extensões específicas do Chrome</span><span class="sxs-lookup"><span data-stu-id="50d27-190">Enabling specific Chrome extensions</span></span>

<span data-ttu-id="50d27-191">O Modelo Administrativo oferece uma configuração para implantar extensões específicas do Chrome com Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="50d27-191">The Administrative Template offers a setting to deploy particular Chrome extensions with Microsoft Intune.</span></span> <span data-ttu-id="50d27-192">Você pode encontrá-lo em Configuração do **Computador > Microsoft Edge > Extensões > Permitir que Extensões Específicas sejam instaladas.**</span><span class="sxs-lookup"><span data-stu-id="50d27-192">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Allow Specific Extensions to be installed**.</span></span>

### <a name="install-extensions-silently"></a><span data-ttu-id="50d27-193">Instalar extensões silenciosamente</span><span class="sxs-lookup"><span data-stu-id="50d27-193">Install extensions silently</span></span>

<span data-ttu-id="50d27-194">Você também pode usar o Modelo Administrativo para definir Microsoft Edge para instalar extensões sem alertar o usuário.</span><span class="sxs-lookup"><span data-stu-id="50d27-194">You can also use the Administrative Template to set Microsoft Edge to install extensions without alerting the user.</span></span> <span data-ttu-id="50d27-195">Você pode encontrá-lo em Configuração do Computador > Microsoft Edge > Extensões > Controlar quais extensões **são instaladas silenciosamente**.</span><span class="sxs-lookup"><span data-stu-id="50d27-195">You can find it in **Computer Configuration > Microsoft Edge > Extensions > Control which extensions are installed silently**.</span></span>

### <a name="microsoft-edge-update-policies"></a><span data-ttu-id="50d27-196">Microsoft Edge políticas de atualização</span><span class="sxs-lookup"><span data-stu-id="50d27-196">Microsoft Edge update policies</span></span>
<span data-ttu-id="50d27-197">Para garantir que Microsoft Edge atualizações corretamente, não modifique as políticas de Microsoft Edge [de atualização.](/deployedge/microsoft-edge-update-policies)</span><span class="sxs-lookup"><span data-stu-id="50d27-197">To ensure that Microsoft Edge updates correctly, do not modify the Microsoft Edge [update policies](/deployedge/microsoft-edge-update-policies).</span></span>

### <a name="other-common-enterprise-policies"></a><span data-ttu-id="50d27-198">Outras políticas corporativas comuns</span><span class="sxs-lookup"><span data-stu-id="50d27-198">Other common enterprise policies</span></span>

<span data-ttu-id="50d27-199">Microsoft Edge oferece muitas outras políticas.</span><span class="sxs-lookup"><span data-stu-id="50d27-199">Microsoft Edge offers a great many other policies.</span></span> <span data-ttu-id="50d27-200">Estas são algumas das mais comuns:</span><span class="sxs-lookup"><span data-stu-id="50d27-200">These are some of the more common ones:</span></span>
 
- [<span data-ttu-id="50d27-201">Configurar sites na lista Enterprise site e modo IE</span><span class="sxs-lookup"><span data-stu-id="50d27-201">Configure Sites on the Enterprise Site List and IE Mode</span></span>](/deployedge/edge-ie-mode-sitelist)
- [<span data-ttu-id="50d27-202">Configurar configurações de página inicial, página inicial e nova guia</span><span class="sxs-lookup"><span data-stu-id="50d27-202">Configure start-up, home page, and new tab page settings</span></span>](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [<span data-ttu-id="50d27-203">Configurar a configuração do jogo de surf</span><span class="sxs-lookup"><span data-stu-id="50d27-203">Configure Surf game setting</span></span>](/deployedge/microsoft-edge-policies#allowsurfgame)
- [<span data-ttu-id="50d27-204">Configurar configurações de servidor proxy</span><span class="sxs-lookup"><span data-stu-id="50d27-204">Configure proxy server settings</span></span>](/deployedge/microsoft-edge-policies#proxy-server)
