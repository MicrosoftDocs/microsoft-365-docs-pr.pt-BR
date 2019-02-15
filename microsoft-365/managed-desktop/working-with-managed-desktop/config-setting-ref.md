---
title: Referência de configurações configuráveis para a área de trabalho gerenciada da Microsoft
description: Definindo categorias para definições configuráveis na área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 1f0301f8660fd7ff60bd347d0d7b88c629d79453
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051092"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a><span data-ttu-id="a9d19-104">Referência de configurações configuráveis-Microsoft Managed desktop</span><span class="sxs-lookup"><span data-stu-id="a9d19-104">Configurable settings reference - Microsoft Managed Desktop</span></span>

<span data-ttu-id="a9d19-p101">Este tópico lista as categorias de configurações que os clientes podem configurar com a área de trabalho gerenciada da Microsoft. Cada categoria de configuração inclui informações sobre requisitos, práticas recomendadas e como personalizar a categoria de configuração.</span><span class="sxs-lookup"><span data-stu-id="a9d19-p101">This topic lists the settings categories that customers can configure with Microsoft Managed Desktop. Each setting category includes info on requirements, best practices, and how to customize the setting category.</span></span> 

## <a name="desktop-background-picture"></a><span data-ttu-id="a9d19-107">Imagem de fundo da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="a9d19-107">Desktop background picture</span></span>
<span data-ttu-id="a9d19-p102">Você pode personalizar a imagem de plano de fundo da área de trabalho para dispositivos de área de trabalho gerenciado da Microsoft em sua organização. Você pode usá-lo para aplicar uma marca da empresa ou um marketing</span><span class="sxs-lookup"><span data-stu-id="a9d19-p102">You can customize the desktop background picture for Microsoft Managed Desktop devices in your organization. You might use this to apply a company brand or marketing</span></span> 

### <a name="requirements"></a><span data-ttu-id="a9d19-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9d19-110">Requirements</span></span>

<span data-ttu-id="a9d19-111">Esses requisitos devem ser atendidos para uma imagem de plano de fundo da área de trabalho:</span><span class="sxs-lookup"><span data-stu-id="a9d19-111">These requirements must be met for a desktop background picture:</span></span>
- <span data-ttu-id="a9d19-112">Formato de arquivo de imagem-. jpg, JPEG ou. png</span><span class="sxs-lookup"><span data-stu-id="a9d19-112">Picture file format - .jpg, jpeg, or .png</span></span>
- <span data-ttu-id="a9d19-113">Local de arquivo-host em um local de http seguro (https) confiável.</span><span class="sxs-lookup"><span data-stu-id="a9d19-113">File location - Host on a trusted secure http (https) location.</span></span> 
- <span data-ttu-id="a9d19-114">Não é permitido-não há suporte para locais de http e de compartilhamento de arquivos (UNC).</span><span class="sxs-lookup"><span data-stu-id="a9d19-114">Not allowed - Http and file share (unc) locations are not supported.</span></span> 

### <a name="customize-and-deploy-desktop-background-picture"></a><span data-ttu-id="a9d19-115">Personalizar e implantar imagem de plano de fundo da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="a9d19-115">Customize and deploy desktop background picture</span></span>

<span data-ttu-id="a9d19-116">**Para adicionar uma imagem de plano de fundo da área de trabalho personalizada**</span><span class="sxs-lookup"><span data-stu-id="a9d19-116">**To add a custom desktop background picture**</span></span>
1. <span data-ttu-id="a9d19-117">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a9d19-117">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a9d19-118">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-118">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a9d19-119">Em espaço de trabalho **configurável** , selecione **imagem de fundo da área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-119">In **Configurable** workspace, select **Desktop background picture**.</span></span> 
4. <span data-ttu-id="a9d19-120">Insira o local da imagem que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="a9d19-120">Enter the location of the picture you want to use.</span></span> 
5. <span data-ttu-id="a9d19-121">Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="a9d19-121">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span> 

## <a name="browser-start-pages"></a><span data-ttu-id="a9d19-122">Páginas iniciais do navegador</span><span class="sxs-lookup"><span data-stu-id="a9d19-122">Browser start pages</span></span>
<span data-ttu-id="a9d19-p103">As páginas iniciais do navegador são abertas em guias individuais quando os usuários iniciam o Microsoft Edge. Se você quiser tornar mais fácil para os usuários abrir um conjunto de sites que eles usam com frequência, adicione uma página inicial de navegador para cada site.</span><span class="sxs-lookup"><span data-stu-id="a9d19-p103">Browser start pages open in individual tabs when your users start Microsoft Edge. If you want to make it easy for your users to open a set of sites that they use frequently, add a browser start page for each site.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a9d19-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9d19-125">Requirements</span></span>

<span data-ttu-id="a9d19-p104">Você deve fornecer o nome de domínio totalmente qualificado (FQDN) para sites de intranet ou Internet para as páginas iniciais do seu navegador. Se os sites internos estiverem configurados, permita que os usuários saibam que o acesso a esses sites só será permitido quando você estiver conectado à rede interna no escritório ou quando estiver conectado a uma conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="a9d19-p104">You must provide the fully qualified domain name (FQDN) for intranet or Internet sites for your browser start pages. If internal sites are configured, let users know that access to these sites is only allowed when connected to the internal network when in the office, or when connected with a VPN connection.</span></span> 

### <a name="customize-and-deploy-browser-start-pages"></a><span data-ttu-id="a9d19-128">Personalizar e implantar páginas iniciais do navegador</span><span class="sxs-lookup"><span data-stu-id="a9d19-128">Customize and deploy browser start pages</span></span>

<span data-ttu-id="a9d19-129">**Para adicionar uma página inicial do navegador**</span><span class="sxs-lookup"><span data-stu-id="a9d19-129">**To add a browser start page**</span></span>
1. <span data-ttu-id="a9d19-130">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a9d19-130">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a9d19-131">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-131">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a9d19-132">Em espaço de trabalho **configurável** , selecione **páginas iniciais do navegador**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-132">In **Configurable** workspace, select **Browser start pages**.</span></span> 
4. <span data-ttu-id="a9d19-133">Selecione **Adicionar página inicial**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-133">Select **Add start page**.</span></span>
5. <span data-ttu-id="a9d19-134">Na **página Adicionar do navegador**, digite a URL do site que você deseja usar e, em seguida, selecione **Adicionar página inicial**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-134">On **Add browser start page**, enter the URL for the site you want to use, and then select **Add start page**.</span></span> 
6. <span data-ttu-id="a9d19-135">Repita as etapas 1-5 para as páginas iniciais adicionais do navegador.</span><span class="sxs-lookup"><span data-stu-id="a9d19-135">Repeat steps 1-5 for additional browser start pages.</span></span> 
7. <span data-ttu-id="a9d19-136">Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="a9d19-136">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="enterprise-mode-site-list-location"></a><span data-ttu-id="a9d19-137">Local da lista de sites do modo empresarial</span><span class="sxs-lookup"><span data-stu-id="a9d19-137">Enterprise mode site list location</span></span>

<span data-ttu-id="a9d19-p105">Se você tiver sites e aplicativos específicos que sabe que têm problemas de compatibilidade com o Microsoft Edge, poderá usar a lista de sites do modo empresarial para que os sites sejam abertos automaticamente usando o Internet Explorer 11. Além disso, se você souber que seus sites de intranet não funcionarão corretamente com o Microsoft Edge, você pode definir todos os sites de intranet para serem abertos usando o Internet Explorer 11 automaticamente. O uso do modo empresarial significa que você pode continuar a usar o Microsoft Edge como navegador padrão e, ao mesmo tempo, garantir que seus aplicativos continuem funcionando no Internet Explorer 11. Para obter mais informações sobre as listas de sites do modo empresarial, consulte [Enterprise Mode e Enterprise Mode site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span><span class="sxs-lookup"><span data-stu-id="a9d19-p105">If you have specific websites and apps that you know have compatibility problems with Microsoft Edge, you can use the Enterprise Mode site list so that the websites automatically open using Internet Explorer 11. Also, if you know that your intranet sites aren't going to work correctly with Microsoft Edge, you can set all intranet sites to open using Internet Explorer 11 automatically. Using Enterprise Mode means that you can continue to use Microsoft Edge as your default browser, while also ensuring that your apps continue working on Internet Explorer 11. For more information on enterprise mode site lists,see [Enterprise Mode and Enterprise Mode Site Lists](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode).</span></span> 

<span data-ttu-id="a9d19-142">Você pode especificar um local do https://ou o local de um compartilhamento interno onde você tenha hospedado sua lista de sites do modo empresarial.</span><span class="sxs-lookup"><span data-stu-id="a9d19-142">You can specify an https:// location, or the location for an internal share where you’ve hosted your enterprise mode site list.</span></span> 

### <a name="requirements"></a><span data-ttu-id="a9d19-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9d19-143">Requirements</span></span>

<span data-ttu-id="a9d19-144">Esses requisitos devem ser atendidos para o arquivo de lista de sites do modo empresarial:</span><span class="sxs-lookup"><span data-stu-id="a9d19-144">These requirements must be met for the enterprise mode site list file:</span></span>
- <span data-ttu-id="a9d19-145">Formato de arquivo-arquivo XML que atende [aos requisitos de arquivo](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span><span class="sxs-lookup"><span data-stu-id="a9d19-145">File format - XML file that meets [file requirements](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)</span></span>
- <span data-ttu-id="a9d19-146">Local do arquivo-arquivo host em um local interno HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9d19-146">File location - Host file on an internal https location.</span></span> 
- <span data-ttu-id="a9d19-147">Não é permitido-a hospedagem em um compartilhamento de arquivo interno, como *//ShareName*, não é permitida</span><span class="sxs-lookup"><span data-stu-id="a9d19-147">Not allowed - Hosting on an internal file share, like *//sharename*, is not allowed</span></span>

### <a name="best-practices"></a><span data-ttu-id="a9d19-148">Práticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="a9d19-148">Best practices</span></span>

<span data-ttu-id="a9d19-149">Essas práticas recomendadas são oferecidas para ajudar os clientes a tomar decisões para modernizar sua infraestrutura de ti:</span><span class="sxs-lookup"><span data-stu-id="a9d19-149">These best practices are offered to help customers make decisions to modernize their IT infrastructure:</span></span>
- <span data-ttu-id="a9d19-p106">**Escolha um número limitado de sites** – o Microsoft Managed desktop usa o Microsoft Edge como o navegador preferencial para melhorar a segurança geral da sua organização e usabilidade para seus usuários. A maioria dos sites nessa lista são aplicativos Web herdados que precisam de uma versão mais antiga de um navegador que não inclua tantos recursos de segurança.</span><span class="sxs-lookup"><span data-stu-id="a9d19-p106">**Choose a limited number of sites** – Microsoft Managed Desktop uses Microsoft Edge as the preferred browser to improve overall security for your organization and usability for your users. Most sites in this list are for legacy web apps that need an older version of a browser that will not include as many security features.</span></span> 
- <span data-ttu-id="a9d19-p107">**Considere uma alternativa** – considere um site diferente ou um aplicativo Web que não exija um navegador mais antigo. Ou, considere atualizar o site para que ele possa usar navegadores mais recentes. Navegadores mais recentes usam a tecnologia mais recente e ajudam a melhorar a segurança.</span><span class="sxs-lookup"><span data-stu-id="a9d19-p107">**Consider an alternate** – Consider a different site, or web app that doesn’t require an older browser. Or, consider updating the site so that it can use newer browsers. Newer browsers use the latest technology and help improve security.</span></span>

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a><span data-ttu-id="a9d19-155">Personalizar e implantar o local da lista de modo de site corporativo</span><span class="sxs-lookup"><span data-stu-id="a9d19-155">Customize and deploy Enterprise site mode list location</span></span>

<span data-ttu-id="a9d19-156">**Para adicionar um local de lista de modo de site corporativo**</span><span class="sxs-lookup"><span data-stu-id="a9d19-156">**To add an enterprise site mode list location**</span></span>

1.  <span data-ttu-id="a9d19-157">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a9d19-157">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2.  <span data-ttu-id="a9d19-158">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-158">Under **Settings**, select **Configurable**.</span></span>
3.  <span data-ttu-id="a9d19-159">Em espaço de trabalho **configurável** , selecione **local da lista de sites do modo empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-159">In **Configurable** workspace, select **Enterprise mode site list location**.</span></span> 
4.  <span data-ttu-id="a9d19-160">Insira o local https da sua lista de sites.</span><span class="sxs-lookup"><span data-stu-id="a9d19-160">Enter the https location for your site list.</span></span> 
5.  <span data-ttu-id="a9d19-161">Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="a9d19-161">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="trusted-sites"></a><span data-ttu-id="a9d19-162">Sites confiáveis</span><span class="sxs-lookup"><span data-stu-id="a9d19-162">Trusted sites</span></span>

<span data-ttu-id="a9d19-p108">Os sites confiáveis permitem que você personalize as zonas de segurança ou onde um site pode ser usado, para sites diferentes. As zonas de segurança incluem:</span><span class="sxs-lookup"><span data-stu-id="a9d19-p108">Trusted sites allow you to customize security zones, or where a site can be used, for different sites. Security zones include:</span></span> 
- <span data-ttu-id="a9d19-165">Zona 1 – zona da intranet local</span><span class="sxs-lookup"><span data-stu-id="a9d19-165">Zone 1 – Local Intranet zone</span></span>
- <span data-ttu-id="a9d19-166">Zona 2 – zona de sites confiáveis</span><span class="sxs-lookup"><span data-stu-id="a9d19-166">Zone 2 – Trusted sites zone</span></span>
- <span data-ttu-id="a9d19-167">Zona 3 – zona da Internet</span><span class="sxs-lookup"><span data-stu-id="a9d19-167">Zone 3 – Internet zone</span></span>
- <span data-ttu-id="a9d19-168">Zona 4 – zona de sites restritos</span><span class="sxs-lookup"><span data-stu-id="a9d19-168">Zone 4 – Restricted Sites zone</span></span>

### <a name="requirements"></a><span data-ttu-id="a9d19-169">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9d19-169">Requirements</span></span>

<span data-ttu-id="a9d19-170">Forneça o nome de domínio totalmente qualificado (FQDN) para sites de intranet ou Internet para cada site confiável.</span><span class="sxs-lookup"><span data-stu-id="a9d19-170">Provide the fully qualified domain name (FQDN) for intranet or Internet sites for each trusted site.</span></span> 

### <a name="customize-and-deploy-trusted-sites"></a><span data-ttu-id="a9d19-171">Personalizar e implantar sites confiáveis</span><span class="sxs-lookup"><span data-stu-id="a9d19-171">Customize and deploy trusted sites</span></span>

<span data-ttu-id="a9d19-172">**Para adicionar um site confiável**</span><span class="sxs-lookup"><span data-stu-id="a9d19-172">**To add a trusted site**</span></span>

1. <span data-ttu-id="a9d19-173">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a9d19-173">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a9d19-174">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-174">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a9d19-175">Em espaço de trabalho **configurável** , selecione **sites confiáveis**e, em seguida, selecione **Adicionar site confiável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-175">In **Configurable** workspace, select **Trusted sites**, and then select **Add trusted site**.</span></span> 
4. <span data-ttu-id="a9d19-176">Em **Adicionar site confiável**, digite a URL, escolha uma zona de segurança e, em seguida, selecione **Adicionar site confiável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-176">On **Add trusted site**, enter the URL, choose a security zone, and then select **Add trusted site**.</span></span> 
5. <span data-ttu-id="a9d19-177">Repita as etapas 1-4 para cada site confiável que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="a9d19-177">Repeat steps 1-4 for each trusted site you want to add.</span></span> 
6. <span data-ttu-id="a9d19-178">Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="a9d19-178">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

<span data-ttu-id="a9d19-179">**Para remover um site confiável**</span><span class="sxs-lookup"><span data-stu-id="a9d19-179">**To remove a trusted site**</span></span>

1. <span data-ttu-id="a9d19-180">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a9d19-180">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a9d19-181">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-181">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a9d19-182">Em espaço de trabalho **configurável** , selecione **sites confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-182">In **Configurable** workspace, select **Trusted sites**.</span></span> 
4. <span data-ttu-id="a9d19-183">Selecione o site que você deseja excluir e, em seguida, selecione **excluir**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-183">Select the site that you want to delete, and then select **Delete**.</span></span> 
5. <span data-ttu-id="a9d19-184">Repita as etapas 1-4 para cada site confiável que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="a9d19-184">Repeat steps 1-4 for each trusted site you want to delete.</span></span> 
6. <span data-ttu-id="a9d19-185">Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="a9d19-185">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="proxy"></a><span data-ttu-id="a9d19-186">Proxy</span><span class="sxs-lookup"><span data-stu-id="a9d19-186">Proxy</span></span>
<span data-ttu-id="a9d19-p109">Você pode gerenciar as configurações de proxy de rede para sua organização. Adicione o seu servidor proxy e o número da porta e, em seguida, adicione suas exceções de site de proxy. A área de trabalho gerenciada da Microsoft inclui um conjunto de exceções de proxy padrão necessárias para que o serviço funcione. A lista de exclusão padrão só pode ser modificada pelo serviço de área de trabalho gerenciada da Microsoft.  Para obter mais informações, consulte [configuração de rede para a área de trabalho gerenciada da Microsoft](../get-ready/network.md).</span><span class="sxs-lookup"><span data-stu-id="a9d19-p109">You can manage network proxy settings for your organization. Add your proxy server and port number, and then add your proxy site exceptions. Microsoft Managed Desktop includes a set of default proxy exceptions that are required for the service to operate. The default exclusion list may only be modified by the Microsoft Managed Desktop service.  For more information, see [Network configuration for Microsoft Managed Desktop](../get-ready/network.md).</span></span> 

<span data-ttu-id="a9d19-192">As exceções de site de proxy adicionadas no portal de área de trabalho gerenciada da Microsoft são adicionadas às exceções de proxy padrão incluídas no serviço de área de trabalho gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9d19-192">The proxy site exceptions that you add in the Microsoft Managed Desktop portal are added to the default proxy exceptions included with Microsoft Managed Desktop service.</span></span> 

> [!NOTE]
> <span data-ttu-id="a9d19-p110">A atualização da lista de exceções de proxy padrão é sempre priorizada em implantações de cliente. Isso significa que sua implantação em estágios será pausada se houver uma implantação para a lista de exceções de proxy padrão.</span><span class="sxs-lookup"><span data-stu-id="a9d19-p110">Updating the default proxy exception list is always prioritized over customer deployments. This means that your staged deployment will be paused if there is a deployment for the default proxy exception list.</span></span>  

### <a name="requirements"></a><span data-ttu-id="a9d19-195">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9d19-195">Requirements</span></span>

<span data-ttu-id="a9d19-196">Esses requisitos devem ser atendidos para exceções de servidor proxy e site de proxy:</span><span class="sxs-lookup"><span data-stu-id="a9d19-196">These requirements must be met for proxy server and proxy site exceptions:</span></span>
- <span data-ttu-id="a9d19-197">Deve ser um endereço de servidor válido e um número de porta</span><span class="sxs-lookup"><span data-stu-id="a9d19-197">Must be a valid server address and port number</span></span>
- <span data-ttu-id="a9d19-198">As URLs devem ser um site http válido</span><span class="sxs-lookup"><span data-stu-id="a9d19-198">URLs must be a valid http site</span></span> 

### <a name="customize-and-deploy-proxies"></a><span data-ttu-id="a9d19-199">Personalizar e implantar proxies</span><span class="sxs-lookup"><span data-stu-id="a9d19-199">Customize and deploy proxies</span></span>

<span data-ttu-id="a9d19-200">**Para adicionar uma exceção de site de proxy individual**</span><span class="sxs-lookup"><span data-stu-id="a9d19-200">**To add an individual proxy site exception**</span></span>

1. <span data-ttu-id="a9d19-201">Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)</span><span class="sxs-lookup"><span data-stu-id="a9d19-201">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mwaasportal)</span></span>
2. <span data-ttu-id="a9d19-202">Em **configurações**, selecione **configurável**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-202">Under **Settings**, select **Configurable**.</span></span>
3. <span data-ttu-id="a9d19-203">Em espaço de trabalho **configurável** , selecione **proxy**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-203">In **Configurable** workspace, select **Proxy**.</span></span> 
4. <span data-ttu-id="a9d19-204">Insira o **endereço** e o **número da porta** para o servidor de proxy e, em seguida, selecione **Adicionar exceção de proxy**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-204">Enter the **Address** and **Port number** for you proxy server, and then select **Add proxy exception**.</span></span> 
5. <span data-ttu-id="a9d19-205">Insira a URL de um site http válido e, em seguida, selecione **Adicionar exceção de proxy**.</span><span class="sxs-lookup"><span data-stu-id="a9d19-205">Enter the URL of a valid http site, and then select **Add proxy exception**.</span></span> 
6. <span data-ttu-id="a9d19-206">Repita as etapas 1-5 para cada site confiável que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="a9d19-206">Repeat steps 1-5 for each trusted site you want to add.</span></span> 
7. <span data-ttu-id="a9d19-207">Selecione **implantação de estágio** para salvar suas alterações e implantá-las no anel de teste.</span><span class="sxs-lookup"><span data-stu-id="a9d19-207">Select **Stage deployment** to save your changes and deploy them to the Test ring.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9d19-208">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a9d19-208">Additional resources</span></span>
- [<span data-ttu-id="a9d19-209">Visão geral das configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="a9d19-209">Configurable settings overview</span></span>](config-setting-overview.md) 
- [<span data-ttu-id="a9d19-210">Implantar configurações configuráveis</span><span class="sxs-lookup"><span data-stu-id="a9d19-210">Deploy configurable settings</span></span>](config-setting-deploy.md)