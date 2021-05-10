---
title: Filtragem de conteúdo da Web
description: Use a filtragem de conteúdo da Web no Microsoft Defender para Ponto de Extremidade para controlar e regular o acesso a sites com base em suas categorias de conteúdo.
keywords: proteção da Web, proteção contra ameaças da Web, navegação na Web, monitoramento, relatórios, cartões, lista de domínios, segurança, phishing, malware, exploração, sites, proteção de rede, Edge, Internet Explorer, Chrome, Firefox, navegador da Web
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47211e187d1f9f883745f008c6d94d04ee762e98
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302059"
---
# <a name="web-content-filtering"></a><span data-ttu-id="b563f-104">Filtragem de conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-104">Web content filtering</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b563f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b563f-105">**Applies to:**</span></span>
- [<span data-ttu-id="b563f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b563f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b563f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b563f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="b563f-108">**A filtragem de conteúdo da Web está atualmente em visualização pública**</span><span class="sxs-lookup"><span data-stu-id="b563f-108">**Web content filtering is currently in public preview**</span></span><br>
> <span data-ttu-id="b563f-109">Esta versão de visualização é fornecida sem um contrato de nível de serviço e não é recomendada para cargas de trabalho de produção.</span><span class="sxs-lookup"><span data-stu-id="b563f-109">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="b563f-110">Determinados recursos podem não ser suportados ou podem ter recursos restritos.</span><span class="sxs-lookup"><span data-stu-id="b563f-110">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="b563f-111">Para obter mais informações, consulte Recursos de visualização do [Microsoft Defender for Endpoint](preview.md).</span><span class="sxs-lookup"><span data-stu-id="b563f-111">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

> [!TIP]
> <span data-ttu-id="b563f-112">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b563f-112">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b563f-113">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b563f-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="b563f-114">A filtragem de conteúdo da Web faz parte dos recursos [de proteção](web-protection-overview.md) da Web no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b563f-114">Web content filtering is part of [Web protection](web-protection-overview.md) capabilities in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="b563f-115">Ele permite que sua organização acompanhe e regular o acesso a sites com base em suas categorias de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="b563f-115">It enables your organization to track and regulate access to websites based on their content categories.</span></span> <span data-ttu-id="b563f-116">Muitos desses sites, embora não sejam mal-intencionados, podem ser problemáticos devido a regulamentos de conformidade, uso de largura de banda ou outras preocupações.</span><span class="sxs-lookup"><span data-stu-id="b563f-116">Many of these websites, while not malicious, might be problematic because of compliance regulations, bandwidth usage, or other concerns.</span></span>

<span data-ttu-id="b563f-117">Configure políticas em seus grupos de dispositivos para bloquear determinadas categorias.</span><span class="sxs-lookup"><span data-stu-id="b563f-117">Configure policies across your device groups to block certain categories.</span></span> <span data-ttu-id="b563f-118">O bloqueio de uma categoria impede que os usuários dentro de grupos de dispositivos especificados acessem URLs associadas à categoria.</span><span class="sxs-lookup"><span data-stu-id="b563f-118">Blocking a category prevents users within specified device groups from accessing URLs associated with the category.</span></span> <span data-ttu-id="b563f-119">Para qualquer categoria que não seja bloqueada, as URLs são auditadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b563f-119">For any category that's not blocked, the URLs are automatically audited.</span></span> <span data-ttu-id="b563f-120">Os usuários podem acessar as URLs sem interrupção e você reunirá estatísticas de acesso para ajudar a criar uma decisão de política mais personalizada.</span><span class="sxs-lookup"><span data-stu-id="b563f-120">Your users can access the URLs without disruption, and you'll gather access statistics to help create a more custom policy decision.</span></span> <span data-ttu-id="b563f-121">Seus usuários verão uma notificação de bloqueio se um elemento na página que eles estão exibindo estiver fazendo chamadas para um recurso bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b563f-121">Your users will see a block notification if an element on the page they're viewing is making calls to a blocked resource.</span></span>

<span data-ttu-id="b563f-122">A filtragem de conteúdo da Web está disponível nos principais navegadores da Web, com blocos executados por Windows Defender SmartScreen (Microsoft Edge) e Proteção de Rede (Chrome, Firefox, Brave e Opera).</span><span class="sxs-lookup"><span data-stu-id="b563f-122">Web content filtering is available on the major web browsers, with blocks performed by Windows Defender SmartScreen (Microsoft Edge) and Network Protection (Chrome, Firefox, Brave and Opera).</span></span> <span data-ttu-id="b563f-123">Para obter mais informações sobre o suporte ao navegador, consulte a seção pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="b563f-123">For more information about browser support, see the prerequisites section.</span></span>

<span data-ttu-id="b563f-124">Resumindo os benefícios:</span><span class="sxs-lookup"><span data-stu-id="b563f-124">Summarizing the benefits:</span></span>

- <span data-ttu-id="b563f-125">Os usuários são impedidos de acessar sites em categorias bloqueadas, quer eles estão navegando no local ou fora</span><span class="sxs-lookup"><span data-stu-id="b563f-125">Users are prevented from accessing websites in blocked categories, whether they're browsing on-premises or away</span></span>
- <span data-ttu-id="b563f-126">Sua equipe de segurança pode implantar convenientemente políticas em grupos de usuários usando grupos de dispositivos definidos no [Microsoft Defender para](/microsoft-365/security/defender-endpoint/rbac) configurações de controle de acesso baseado em função de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="b563f-126">Your security team can conveniently deploy policies to groups of users using device groups defined in [Microsoft Defender for Endpoint role-based access control settings](/microsoft-365/security/defender-endpoint/rbac)</span></span>
- <span data-ttu-id="b563f-127">Sua equipe de segurança pode acessar relatórios da Web no mesmo local central, com visibilidade sobre blocos reais e uso da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-127">Your security team can access web reports in the same central location, with visibility over actual blocks and web usage</span></span>

## <a name="user-experience"></a><span data-ttu-id="b563f-128">Experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="b563f-128">User experience</span></span>

<span data-ttu-id="b563f-129">A experiência de bloqueio para navegadores com suporte de terceiros é fornecida pela Proteção de Rede, que fornece um sistema notificando o usuário de uma conexão bloqueada.</span><span class="sxs-lookup"><span data-stu-id="b563f-129">The blocking experience for 3rd party supported browsers is provided by Network Protection, which provides a system-level toast notifying the user of a blocked connection.</span></span> <span data-ttu-id="b563f-130">Para uma experiência mais fácil de usar no navegador, considere o uso Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="b563f-130">For a more user-friendly, in-browser experience, consider using Microsoft Edge.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b563f-131">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b563f-131">Prerequisites</span></span>

<span data-ttu-id="b563f-132">Antes de tentar esse recurso, certifique-se de ter os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="b563f-132">Before trying out this feature, make sure you have the following requirements:</span></span>

- <span data-ttu-id="b563f-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security complemento ou a licença autônoma do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b563f-133">Windows 10 Enterprise E5, Microsoft 365 E5, Microsoft 365 E5 Security, Microsoft 365 E3 + Microsoft 365 E5 Security add-on or the Microsoft Defender for Endpoint standalone license.</span></span> 
- <span data-ttu-id="b563f-134">Acesso ao Central de Segurança do Microsoft Defender portal ( https://securitycenter.windows.com) .</span><span class="sxs-lookup"><span data-stu-id="b563f-134">Access to Microsoft Defender Security Center portal (https://securitycenter.windows.com).</span></span>
- <span data-ttu-id="b563f-135">Dispositivos executando Windows 10 Atualização de Aniversário (versão 1607) ou posterior com a atualização mais recente do MoCAMP.</span><span class="sxs-lookup"><span data-stu-id="b563f-135">Devices running Windows 10 Anniversary Update (version 1607) or later with the latest MoCAMP update.</span></span>

## <a name="data-handling"></a><span data-ttu-id="b563f-136">Manipulação de dados</span><span class="sxs-lookup"><span data-stu-id="b563f-136">Data handling</span></span>

<span data-ttu-id="b563f-137">Seguiremos qualquer região que você tenha escolhido para usar como parte das configurações de tratamento de dados do [Microsoft Defender for Endpoint.](data-storage-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="b563f-137">We will follow whichever region you have elected to use as part of your [Microsoft Defender for Endpoint data handling settings](data-storage-privacy.md).</span></span> <span data-ttu-id="b563f-138">Seus dados não sairão do data center nessa região.</span><span class="sxs-lookup"><span data-stu-id="b563f-138">Your data will not leave the data center in that region.</span></span> <span data-ttu-id="b563f-139">Além disso, seus dados não serão compartilhados com terceiros, incluindo nossos provedores de dados.</span><span class="sxs-lookup"><span data-stu-id="b563f-139">In addition, your data will not be shared with any third-parties, including our data providers.</span></span>

## <a name="turn-on-web-content-filtering"></a><span data-ttu-id="b563f-140">Ativar a filtragem de conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-140">Turn on web content filtering</span></span>

<span data-ttu-id="b563f-141">No menu de navegação à esquerda, **selecione** Configurações  >  **Recursos**  >  **Avançados Gerais**.</span><span class="sxs-lookup"><span data-stu-id="b563f-141">From the left-hand navigation menu, select **Settings** > **General** > **Advanced Features**.</span></span> <span data-ttu-id="b563f-142">Role para baixo até ver a entrada para filtragem **de conteúdo da Web**.</span><span class="sxs-lookup"><span data-stu-id="b563f-142">Scroll down until you see the entry for **Web content filtering**.</span></span> <span data-ttu-id="b563f-143">Alterne a alternância **para As preferências** **Ligar e Salvar.**</span><span class="sxs-lookup"><span data-stu-id="b563f-143">Switch the toggle to **On** and **Save preferences**.</span></span>

### <a name="configure-web-content-filtering-policies"></a><span data-ttu-id="b563f-144">Configurar políticas de filtragem de conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-144">Configure web content filtering policies</span></span>

<span data-ttu-id="b563f-145">As políticas de filtragem de conteúdo da Web especificam quais categorias de site são bloqueadas em quais grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b563f-145">Web content filtering policies specify which site categories are blocked on which device groups.</span></span> <span data-ttu-id="b563f-146">Para gerenciar as políticas, acesse **Configurações**  >  **filtragem**  >  **de conteúdo da Web de Regras.**</span><span class="sxs-lookup"><span data-stu-id="b563f-146">To manage the policies, go to **Settings** > **Rules** > **Web content filtering**.</span></span>

<span data-ttu-id="b563f-147">Use o filtro para localizar políticas que contêm determinadas categorias bloqueadas ou são aplicadas a grupos de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="b563f-147">Use the filter to locate policies that contain certain blocked categories or are applied to specific device groups.</span></span>

### <a name="create-a-policy"></a><span data-ttu-id="b563f-148">Criar uma política</span><span class="sxs-lookup"><span data-stu-id="b563f-148">Create a policy</span></span>

<span data-ttu-id="b563f-149">Para adicionar uma nova política:</span><span class="sxs-lookup"><span data-stu-id="b563f-149">To add a new policy:</span></span>

1. <span data-ttu-id="b563f-150">Selecione **Adicionar política** na página de **filtragem de** conteúdo da Web em **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="b563f-150">Select **Add policy** on the **Web content filtering** page in **Settings**.</span></span>

2. <span data-ttu-id="b563f-151">Especifique um nome.</span><span class="sxs-lookup"><span data-stu-id="b563f-151">Specify a name.</span></span>

3. <span data-ttu-id="b563f-152">Selecione as categorias a bloquear.</span><span class="sxs-lookup"><span data-stu-id="b563f-152">Select the categories to block.</span></span> <span data-ttu-id="b563f-153">Use o ícone de expansão para expandir totalmente cada categoria pai e selecione categorias de conteúdo da Web específicas.</span><span class="sxs-lookup"><span data-stu-id="b563f-153">Use the expand icon to fully expand each parent category and select specific web content categories.</span></span>

4. <span data-ttu-id="b563f-154">Especifique o escopo da política.</span><span class="sxs-lookup"><span data-stu-id="b563f-154">Specify the policy scope.</span></span> <span data-ttu-id="b563f-155">Selecione os grupos de dispositivos para especificar onde aplicar a política.</span><span class="sxs-lookup"><span data-stu-id="b563f-155">Select the device groups to specify where to apply the policy.</span></span> <span data-ttu-id="b563f-156">Somente dispositivos nos grupos de dispositivos selecionados serão impedidos de acessar sites nas categorias selecionadas.</span><span class="sxs-lookup"><span data-stu-id="b563f-156">Only devices in the selected device groups will be prevented from accessing websites in the selected categories.</span></span>

5. <span data-ttu-id="b563f-157">Revise o resumo e salve a política.</span><span class="sxs-lookup"><span data-stu-id="b563f-157">Review the summary and save the policy.</span></span> <span data-ttu-id="b563f-158">A atualização da política pode levar até 2 horas para ser aplicada aos dispositivos selecionados.</span><span class="sxs-lookup"><span data-stu-id="b563f-158">The policy refresh may take up to 2 hours to apply to your selected devices.</span></span>

> [!TIP]
> <span data-ttu-id="b563f-159">Você pode implantar uma política sem selecionar qualquer categoria em um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b563f-159">You can deploy a policy without selecting any category on a device group.</span></span> <span data-ttu-id="b563f-160">Essa ação criará uma política somente de auditoria, para ajudá-lo a entender o comportamento do usuário antes de criar uma política de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="b563f-160">This action will create an audit only policy, to help you understand user behavior before creating a block policy.</span></span>

>[!NOTE]
><span data-ttu-id="b563f-161">Se você estiver removendo uma política ou alterando grupos de dispositivos ao mesmo tempo, isso pode causar um atraso na implantação da política.</span><span class="sxs-lookup"><span data-stu-id="b563f-161">If you are removing a policy or changing device groups at the same time, this might cause a delay in policy deployment.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b563f-162">Bloquear a categoria "Não categorizada" pode levar a resultados inesperados e indesejáveis.</span><span class="sxs-lookup"><span data-stu-id="b563f-162">Blocking the "Uncategorized" category may lead to unexpected and undesired results.</span></span>  

### <a name="allow-specific-websites"></a><span data-ttu-id="b563f-163">Permitir sites específicos</span><span class="sxs-lookup"><span data-stu-id="b563f-163">Allow specific websites</span></span>

<span data-ttu-id="b563f-164">É possível substituir a categoria bloqueada na filtragem de conteúdo da Web para permitir um único site criando uma política de indicador personalizada.</span><span class="sxs-lookup"><span data-stu-id="b563f-164">It's possible to override the blocked category in web content filtering to allow a single site by creating a custom indicator policy.</span></span> <span data-ttu-id="b563f-165">A política de indicador personalizado irá sobressuar a política de filtragem de conteúdo da Web quando ela for aplicada ao grupo de dispositivos em questão.</span><span class="sxs-lookup"><span data-stu-id="b563f-165">The custom indicator policy will supersede the web content filtering policy when it's applied to the device group in question.</span></span>

1. <span data-ttu-id="b563f-166">Crie um indicador personalizado no Central de Segurança do Microsoft Defender, Configurações  >    >  **URL de indicadores/Item de**  >  **adoção de domínio.**</span><span class="sxs-lookup"><span data-stu-id="b563f-166">Create a custom indicator in the Microsoft Defender Security Center by going to **Settings** > **Indicators** > **URL/Domain** > **Add Item**.</span></span>

2. <span data-ttu-id="b563f-167">Insira o domínio do site.</span><span class="sxs-lookup"><span data-stu-id="b563f-167">Enter the domain of the site.</span></span>

3. <span data-ttu-id="b563f-168">Definir a ação de política como **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="b563f-168">Set the policy action to **Allow**.</span></span>  

### <a name="reporting-inaccuracies"></a><span data-ttu-id="b563f-169">Imprecisões de relatórios</span><span class="sxs-lookup"><span data-stu-id="b563f-169">Reporting inaccuracies</span></span>

<span data-ttu-id="b563f-170">Se você encontrar um domínio que tenha sido categorizado incorretamente, você poderá relatar imprecisões diretamente para nós na página Relatórios de Filtragem de Conteúdo da Web.</span><span class="sxs-lookup"><span data-stu-id="b563f-170">If you encounter a domain that has been incorrectly categorized, you can report inaccuracies directly to us from the Web Content Filtering reports page.</span></span> <span data-ttu-id="b563f-171">Esse recurso está disponível apenas no novo centro de Microsoft 365 de segurança (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b563f-171">This feature is available only in the new Microsoft 365 security center (security.microsoft.com).</span></span>

<span data-ttu-id="b563f-172">Para relatar uma imprecisão, navegue até **Relatórios**  >  **web protection** Web Content  >  **Filtering Details**  >  **Domains**.</span><span class="sxs-lookup"><span data-stu-id="b563f-172">To report an inaccuracy, navigate to **Reports** > **Web protection** > **Web Content Filtering Details** > **Domains**.</span></span> <span data-ttu-id="b563f-173">Na guia domínios de nossos relatórios de Filtragem de Conteúdo da Web, você verá uma elipse ao lado de cada um dos domínios.</span><span class="sxs-lookup"><span data-stu-id="b563f-173">On the domains tab of our Web Content Filtering reports, you will see an ellipsis beside each of the domains.</span></span> <span data-ttu-id="b563f-174">Passe o mouse sobre essa reellipse e selecione **Report Inaccuracy**.</span><span class="sxs-lookup"><span data-stu-id="b563f-174">Hover over this ellipsis and select **Report Inaccuracy**.</span></span>

<span data-ttu-id="b563f-175">Um painel será aberto onde você pode selecionar a prioridade e adicionar detalhes adicionais, como a categoria sugerida para re-categorização.</span><span class="sxs-lookup"><span data-stu-id="b563f-175">A panel will open where you can select the priority and add additional details such as the suggested category for re-categorization.</span></span> <span data-ttu-id="b563f-176">Depois de concluir o formulário, selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="b563f-176">Once you complete the form, select **Submit**.</span></span> <span data-ttu-id="b563f-177">Nossa equipe revisará a solicitação em um dia útil.</span><span class="sxs-lookup"><span data-stu-id="b563f-177">Our team will review the request within one business day.</span></span> <span data-ttu-id="b563f-178">Para desbloquear imediatamente, crie um [indicador de autorização personalizado.](indicator-ip-domain.md)</span><span class="sxs-lookup"><span data-stu-id="b563f-178">For immediate unblocking, create a [custom allow indicator](indicator-ip-domain.md).</span></span>

## <a name="web-content-filtering-cards-and-details"></a><span data-ttu-id="b563f-179">Cartões e detalhes de filtragem de conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-179">Web content filtering cards and details</span></span>

<span data-ttu-id="b563f-180">Selecione **Relatórios > Proteção da Web** para exibir cartões com informações sobre filtragem de conteúdo da Web e proteção contra ameaças da Web.</span><span class="sxs-lookup"><span data-stu-id="b563f-180">Select **Reports > Web protection** to view cards with information about web content filtering and web threat protection.</span></span> <span data-ttu-id="b563f-181">Os cartões a seguir fornecem informações resumidas sobre a filtragem de conteúdo da Web.</span><span class="sxs-lookup"><span data-stu-id="b563f-181">The following cards provide summary information about web content filtering.</span></span>

### <a name="web-activity-by-category"></a><span data-ttu-id="b563f-182">Atividade da Web por categoria</span><span class="sxs-lookup"><span data-stu-id="b563f-182">Web activity by category</span></span>

<span data-ttu-id="b563f-183">Este cartão lista as categorias de conteúdo da Web pai com o maior aumento ou diminuição no número de tentativas de acesso.</span><span class="sxs-lookup"><span data-stu-id="b563f-183">This card lists the parent web content categories with the largest increase or decrease in the number of access attempts.</span></span> <span data-ttu-id="b563f-184">Entenda as alterações drásticas nos padrões de atividade da Web em sua organização dos últimos 30, 3 meses ou 6 meses.</span><span class="sxs-lookup"><span data-stu-id="b563f-184">Understand drastic changes in web activity patterns in your organization from last 30 days, 3 months, or 6 months.</span></span> <span data-ttu-id="b563f-185">Selecione um nome de categoria para exibir mais informações.</span><span class="sxs-lookup"><span data-stu-id="b563f-185">Select a category name to view more information.</span></span>

<span data-ttu-id="b563f-186">Nos primeiros 30 dias de uso desse recurso, sua organização pode não ter dados suficientes para exibir essas informações.</span><span class="sxs-lookup"><span data-stu-id="b563f-186">In the first 30 days of using this feature, your organization might not have enough data to display this information.</span></span>

![Imagem da atividade da Web por cartão de categoria](images/web-activity-by-category600.png)

### <a name="web-content-filtering--summary-card"></a><span data-ttu-id="b563f-188">Cartão de resumo de filtragem de conteúdo da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-188">Web content filtering  summary card</span></span>

<span data-ttu-id="b563f-189">Esse cartão exibe a distribuição de tentativas de acesso bloqueado nas diferentes categorias de conteúdo da Web pai.</span><span class="sxs-lookup"><span data-stu-id="b563f-189">This card displays the distribution of blocked access attempts across the different parent web content categories.</span></span> <span data-ttu-id="b563f-190">Selecione uma das barras coloridas para exibir mais informações sobre uma categoria da Web pai específica.</span><span class="sxs-lookup"><span data-stu-id="b563f-190">Select one of the colored bars to view more information about a specific parent web category.</span></span>

![Imagem do cartão de resumo de filtragem de conteúdo da Web](images/web-content-filtering-summary.png)

### <a name="web-activity-summary-card"></a><span data-ttu-id="b563f-192">Cartão de resumo de atividade da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-192">Web activity summary card</span></span>

<span data-ttu-id="b563f-193">Esse cartão exibe o número total de solicitações de conteúdo da Web em todas as URLs.</span><span class="sxs-lookup"><span data-stu-id="b563f-193">This card displays the total number of requests for web content in all URLs.</span></span>

![Imagem do cartão de resumo da atividade da Web](images/web-activity-summary.png)

### <a name="view-card-details"></a><span data-ttu-id="b563f-195">Exibir detalhes do cartão</span><span class="sxs-lookup"><span data-stu-id="b563f-195">View card details</span></span>

<span data-ttu-id="b563f-196">Você pode acessar os **detalhes do Relatório** para cada cartão selecionando uma linha de tabela ou uma barra colorida do gráfico no cartão.</span><span class="sxs-lookup"><span data-stu-id="b563f-196">You can access the **Report details** for each card by selecting a table row or colored bar from the chart in the card.</span></span> <span data-ttu-id="b563f-197">A página de detalhes do relatório para cada cartão contém dados estatísticos abrangentes sobre categorias de conteúdo da Web, domínios de site e grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b563f-197">The report details page for each card contains extensive statistical data about web content categories, website domains, and device groups.</span></span>

![Imagem dos detalhes do relatório de proteção da Web](images/web-protection-report-details.png)

- <span data-ttu-id="b563f-199">**Categorias da Web**: lista as categorias de conteúdo da Web que tiveram tentativas de acesso em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b563f-199">**Web categories**: Lists the web content categories that have had access attempts in your organization.</span></span> <span data-ttu-id="b563f-200">Selecione uma categoria específica para abrir um sobrevoo de resumo.</span><span class="sxs-lookup"><span data-stu-id="b563f-200">Select a specific category to open a summary flyout.</span></span>

- <span data-ttu-id="b563f-201">**Domínios**: lista os domínios da Web que foram acessados ou bloqueados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b563f-201">**Domains**: Lists the web domains that have been accessed or blocked in your organization.</span></span> <span data-ttu-id="b563f-202">Selecione um domínio específico para exibir informações detalhadas sobre esse domínio.</span><span class="sxs-lookup"><span data-stu-id="b563f-202">Select a specific domain to view detailed information about that domain.</span></span>

- <span data-ttu-id="b563f-203">**Grupos de dispositivos**: lista todos os grupos de dispositivos que geraram atividade da Web em sua organização</span><span class="sxs-lookup"><span data-stu-id="b563f-203">**Device groups**: Lists all the device groups that have generated web activity in your organization</span></span>

<span data-ttu-id="b563f-204">Use o filtro de intervalo de tempo na parte superior esquerda da página para selecionar um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="b563f-204">Use the time range filter at the top left of the page to select a time period.</span></span> <span data-ttu-id="b563f-205">Você também pode filtrar as informações ou personalizar as colunas.</span><span class="sxs-lookup"><span data-stu-id="b563f-205">You can also filter the information or customize the columns.</span></span> <span data-ttu-id="b563f-206">Selecione uma linha para abrir um painel de sobrevoo com ainda mais informações sobre o item selecionado.</span><span class="sxs-lookup"><span data-stu-id="b563f-206">Select a row to open a flyout pane with even more information about the selected item.</span></span>

## <a name="errors-and-issues"></a><span data-ttu-id="b563f-207">Erros e problemas</span><span class="sxs-lookup"><span data-stu-id="b563f-207">Errors and issues</span></span>

### <a name="limitations-and-known-issues-in-this-preview"></a><span data-ttu-id="b563f-208">Limitações e problemas conhecidos nesta visualização</span><span class="sxs-lookup"><span data-stu-id="b563f-208">Limitations and known issues in this preview</span></span>

- <span data-ttu-id="b563f-209">Somente Microsoft Edge suporte se a configuração do sistema operacional do dispositivo for Server (**cmd**  >  **Systeminfo**  >  **OS Configuration**).</span><span class="sxs-lookup"><span data-stu-id="b563f-209">Only Microsoft Edge is supported if your device's OS configuration is Server (**cmd** > **Systeminfo** > **OS Configuration**).</span></span> <span data-ttu-id="b563f-210">A Proteção de Rede só tem suporte no modo Inspecionar em dispositivos Server, que é responsável por proteger o tráfego em navegadores de terceiros com suporte.</span><span class="sxs-lookup"><span data-stu-id="b563f-210">Network Protection is only supported in Inspect mode on Server devices, which is responsible for securing traffic across supported 3rd party browsers.</span></span>

- <span data-ttu-id="b563f-211">Os dispositivos não atribuídos terão dados incorretos mostrados no relatório.</span><span class="sxs-lookup"><span data-stu-id="b563f-211">Unassigned devices will have incorrect data shown within the report.</span></span> <span data-ttu-id="b563f-212">No **pivô Detalhes do relatório**  >  **Grupos de** dispositivos, você pode ver uma linha com um campo Grupo de Dispositivos em branco.</span><span class="sxs-lookup"><span data-stu-id="b563f-212">In the **Report details** > **Device groups** pivot, you might see a row with a blank Device Group field.</span></span> <span data-ttu-id="b563f-213">Esse grupo contém seus dispositivos não atribuídos antes que eles sejam colocados no grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="b563f-213">This group contains your unassigned devices before they get put into your specified group.</span></span> <span data-ttu-id="b563f-214">O relatório dessa linha pode não conter uma contagem precisa de dispositivos ou contagens de acesso.</span><span class="sxs-lookup"><span data-stu-id="b563f-214">The report for this row might not contain an accurate count of devices or access counts.</span></span>

- <span data-ttu-id="b563f-215">Atualmente, os relatórios de Filtragem de Conteúdo da Web estão limitados a mostrar os 5.000 principais registros.</span><span class="sxs-lookup"><span data-stu-id="b563f-215">Web Content Filtering reports are currently limited to showing the top 5000 records.</span></span> <span data-ttu-id="b563f-216">Por exemplo, o relatório Domínios mostrará apenas um máximo dos 5.000 domínios principais para uma determinada consulta de filtro, se aplicável.</span><span class="sxs-lookup"><span data-stu-id="b563f-216">For example, the Domains report will only show a maximum of the top 5000 domains for a given filter query, if applicable.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b563f-217">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b563f-217">Related topics</span></span>

- [<span data-ttu-id="b563f-218">Visão geral da proteção da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-218">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="b563f-219">Proteção contra ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-219">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="b563f-220">Monitorar a segurança da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-220">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="b563f-221">Responder a ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="b563f-221">Respond to web threats</span></span>](web-protection-response.md)
