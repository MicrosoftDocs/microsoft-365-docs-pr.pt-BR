---
title: Vulnerabilidades na minha organização - gerenciamento de ameaças e vulnerabilidades
description: Lista a ID de vulnerabilidades e exposições comuns (CVE) de pontos fracos encontrados no software em execução em sua organização. Descoberto pelo Microsoft Defender para o recurso de gerenciamento de ameaças e vulnerabilidades do Ponto de Extremidade.
keywords: Microsoft Defender for Endpoint threat & vulnerability management, threat and vulnerability management, Microsoft Defender for Endpoint tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
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
ms.openlocfilehash: a8039a06dc58c31158f90d39857ffbeba92138d5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933068"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a><span data-ttu-id="bc139-105">Vulnerabilidades na minha organização - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="bc139-105">Vulnerabilities in my organization - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc139-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bc139-106">**Applies to:**</span></span>
- [<span data-ttu-id="bc139-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bc139-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="bc139-108">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="bc139-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bc139-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc139-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="bc139-110">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="bc139-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bc139-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="bc139-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="bc139-112">O gerenciamento de ameaças e vulnerabilidades usa os mesmos sinais no Defender for Endpoint's endpoint protection para verificar e detectar vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="bc139-112">Threat and vulnerability management uses the same signals in Defender for Endpoint's endpoint protection to scan and detect vulnerabilities.</span></span>

<span data-ttu-id="bc139-113">A **página Fraquezas** lista as vulnerabilidades de software às que seus dispositivos são expostos listando a ID de Vulnerabilidades Comuns e Exposições (CVE).</span><span class="sxs-lookup"><span data-stu-id="bc139-113">The **Weaknesses** page lists the software vulnerabilities your devices are exposed to by listing the Common Vulnerabilities and Exposures (CVE) ID.</span></span> <span data-ttu-id="bc139-114">Você também pode exibir a gravidade, a classificação do Sistema de Pontuação de Vulnerabilidade Comum (CVSS), a prevalência em sua organização, a violação correspondente, as informações sobre ameaças e muito mais.</span><span class="sxs-lookup"><span data-stu-id="bc139-114">You can also view the severity, Common Vulnerability Scoring System (CVSS) rating, prevalence in your organization, corresponding breach, threat insights, and more.</span></span>

>[!NOTE]
><span data-ttu-id="bc139-115">Se não houver nenhuma CVE-ID oficial atribuída a uma vulnerabilidade, o nome da vulnerabilidade será atribuído pelo gerenciamento de ameaças e vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="bc139-115">If there is no official CVE-ID assigned to a vulnerability, the vulnerability name is assigned by threat and vulnerability management.</span></span>

>[!TIP]
><span data-ttu-id="bc139-116">Para obter emails sobre novos eventos de vulnerabilidade, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="bc139-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-weaknesses-page"></a><span data-ttu-id="bc139-117">Navegue até a página Pontos Fracos</span><span class="sxs-lookup"><span data-stu-id="bc139-117">Navigate to the Weaknesses page</span></span>

<span data-ttu-id="bc139-118">Acesse a página Pontos Fracos de algumas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="bc139-118">Access the Weaknesses page a few different ways:</span></span>

- <span data-ttu-id="bc139-119">Selecionando **pontos fracos** no menu de navegação de gerenciamento de ameaças e vulnerabilidades no [Centro de Segurança do Microsoft Defender](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bc139-119">Selecting **Weaknesses** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="bc139-120">Pesquisa global</span><span class="sxs-lookup"><span data-stu-id="bc139-120">Global search</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="bc139-121">Menu de navegação</span><span class="sxs-lookup"><span data-stu-id="bc139-121">Navigation menu</span></span>

<span data-ttu-id="bc139-122">Vá para o menu de navegação de gerenciamento de ameaças e vulnerabilidades e selecione **Pontos Fracos** para abrir a lista de CVEs.</span><span class="sxs-lookup"><span data-stu-id="bc139-122">Go to the threat and vulnerability management navigation menu and select **Weaknesses** to open the list of CVEs.</span></span>

### <a name="vulnerabilities-in-global-search"></a><span data-ttu-id="bc139-123">Vulnerabilidades na pesquisa global</span><span class="sxs-lookup"><span data-stu-id="bc139-123">Vulnerabilities in global search</span></span>

1. <span data-ttu-id="bc139-124">Vá para o menu suspenso de pesquisa global.</span><span class="sxs-lookup"><span data-stu-id="bc139-124">Go to the global search drop-down menu.</span></span>
2. <span data-ttu-id="bc139-125">Selecione **Vulnerabilidade e** chave na ID de Vulnerabilidades e Exposições Comuns (CVE) que você está procurando e selecione o ícone de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="bc139-125">Select **Vulnerability** and key-in the Common Vulnerabilities and Exposures (CVE) ID that you're looking for, then select the search icon.</span></span> <span data-ttu-id="bc139-126">A **página Pontos Fracos** é aberta com as informações CVE que você está procurando.</span><span class="sxs-lookup"><span data-stu-id="bc139-126">The **Weaknesses** page opens with the CVE information that you're looking for.</span></span>
<span data-ttu-id="bc139-127">![Caixa de pesquisa global com a opção suspenso "vulnerabilidade" selecionada e um CVE de exemplo.](images/tvm-vuln-globalsearch.png)</span><span class="sxs-lookup"><span data-stu-id="bc139-127">![Global search box with the dropdown option "vulnerability" selected and an example CVE.](images/tvm-vuln-globalsearch.png)</span></span>
3. <span data-ttu-id="bc139-128">Selecione o CVE para abrir um painel de sobremenu com mais informações, incluindo a descrição da vulnerabilidade, detalhes, insights de ameaças e dispositivos expostos.</span><span class="sxs-lookup"><span data-stu-id="bc139-128">Select the CVE to open a flyout panel with more information, including the vulnerability description, details, threat insights, and exposed devices.</span></span>

<span data-ttu-id="bc139-129">Para ver o restante das vulnerabilidades na página **Fraquezas,** digite CVE e selecione pesquisar.</span><span class="sxs-lookup"><span data-stu-id="bc139-129">To see the rest of the vulnerabilities in the **Weaknesses** page, type CVE, then select search.</span></span>

## <a name="weaknesses-overview"></a><span data-ttu-id="bc139-130">Visão geral de pontos fracos</span><span class="sxs-lookup"><span data-stu-id="bc139-130">Weaknesses overview</span></span>

<span data-ttu-id="bc139-131">Correção das vulnerabilidades em dispositivos expostos para reduzir o risco para seus ativos e organização.</span><span class="sxs-lookup"><span data-stu-id="bc139-131">Remediate the vulnerabilities in exposed devices to reduce the risk to your assets and organization.</span></span> <span data-ttu-id="bc139-132">Se a **coluna Dispositivos Expostos** mostrar 0, isso significa que você não está em risco.</span><span class="sxs-lookup"><span data-stu-id="bc139-132">If the **Exposed Devices** column shows 0, that means you aren't at risk.</span></span>

![Página inicial de fraquezas.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a><span data-ttu-id="bc139-134">Insights sobre violações e ameaças</span><span class="sxs-lookup"><span data-stu-id="bc139-134">Breach and threat insights</span></span>

<span data-ttu-id="bc139-135">Exibir quaisquer informações relacionadas de violação e ameaça na coluna **Ameaça** quando os ícones são coloridos em vermelho.</span><span class="sxs-lookup"><span data-stu-id="bc139-135">View any related breach and threat insights in the **Threat** column when the icons are colored red.</span></span>

 >[!NOTE]
 > <span data-ttu-id="bc139-136">Sempre priorize as recomendações associadas a ameaças em andamento.</span><span class="sxs-lookup"><span data-stu-id="bc139-136">Always prioritize recommendations that are associated with ongoing threats.</span></span> <span data-ttu-id="bc139-137">Essas recomendações são marcadas com o ícone de visão de ameaça ![ Desenho simples de um bug vermelho.](images/tvm_bug_icon.png)</span><span class="sxs-lookup"><span data-stu-id="bc139-137">These recommendations are marked with the threat insight icon ![Simple drawing of a red bug.](images/tvm_bug_icon.png)</span></span> <span data-ttu-id="bc139-138">e ícone de insight de violação ![ Desenho simples de uma seta atingindo um destino. ](images/tvm_alert_icon.png) .</span><span class="sxs-lookup"><span data-stu-id="bc139-138">and breach insight icon ![Simple drawing of an arrow hitting a target.](images/tvm_alert_icon.png).</span></span>  

<span data-ttu-id="bc139-139">O ícone de insights de violação será realçado se houver uma vulnerabilidade encontrada em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bc139-139">The breach insights icon is highlighted if there's a vulnerability found in your organization.</span></span>
<span data-ttu-id="bc139-140">![Exemplo de um texto de insights de violação que pode aparecer ao passar o mouse sobre o ícone.</span><span class="sxs-lookup"><span data-stu-id="bc139-140">![Example of a breach insights text that could show up when hovering over icon.</span></span> <span data-ttu-id="bc139-141">Este diz "alerta ativo possível está associado a essa recomendação.](images/tvm-breach-insights.png)</span><span class="sxs-lookup"><span data-stu-id="bc139-141">This one says "possible active alert is associated with this recommendation.](images/tvm-breach-insights.png)</span></span>

<span data-ttu-id="bc139-142">O ícone de insights de ameaça será realçado se houver explorações associadas na vulnerabilidade encontrada em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bc139-142">The threat insights icon is highlighted if there are associated exploits in the vulnerability found in your organization.</span></span> <span data-ttu-id="bc139-143">Passar o mouse sobre o ícone mostra se a ameaça faz parte de um kit de exploração ou se está conectada a campanhas ou grupos de atividades persistentes ou persistentes específicos.</span><span class="sxs-lookup"><span data-stu-id="bc139-143">Hovering over the icon shows whether the threat is a part of an exploit kit, or connected to specific advanced persistent campaigns or activity groups.</span></span> <span data-ttu-id="bc139-144">Quando disponível, há um link para um relatório do Threat Analytics com notícias de exploração zero dia, divulgações ou avisos de segurança relacionados.</span><span class="sxs-lookup"><span data-stu-id="bc139-144">When available, there's a link to a Threat Analytics report with zero-day exploitation news, disclosures, or related security advisories.</span></span>  

![Texto de insights de ameaça que podem aparecer ao passar o mouse sobre o ícone.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a><span data-ttu-id="bc139-147">Obter percepções de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="bc139-147">Gain vulnerability insights</span></span>

<span data-ttu-id="bc139-148">Se você selecionar um CVE, um painel de sobremenu será aberto com mais informações, como a descrição da vulnerabilidade, detalhes, percepções de ameaças e dispositivos expostos.</span><span class="sxs-lookup"><span data-stu-id="bc139-148">If you select a CVE, a flyout panel will open with more information such as the vulnerability description, details, threat insights, and exposed devices.</span></span>

- <span data-ttu-id="bc139-149">A categoria "Recurso do sistema operacional" é mostrada em cenários relevantes</span><span class="sxs-lookup"><span data-stu-id="bc139-149">The "OS Feature" category is shown in relevant scenarios</span></span>
- <span data-ttu-id="bc139-150">Você pode ir para a recomendação de segurança relacionada para cada CVE com dispositivo exposto</span><span class="sxs-lookup"><span data-stu-id="bc139-150">You can go to the related security recommendation for every CVE with exposed device</span></span>

 ![Exemplo de flyout de fraqueza.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a><span data-ttu-id="bc139-152">Software que não tem suporte</span><span class="sxs-lookup"><span data-stu-id="bc139-152">Software that isn't supported</span></span>

<span data-ttu-id="bc139-153">As CVEs para softwares que não são suportadas atualmente pelo gerenciamento de vulnerabilidades & ameaças ainda estão presentes na página Pontos Fracos.</span><span class="sxs-lookup"><span data-stu-id="bc139-153">CVEs for software that isn't currently supported by threat & vulnerability management is still present in the Weaknesses page.</span></span> <span data-ttu-id="bc139-154">Como o software não tem suporte, somente dados limitados estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bc139-154">Because the software is not supported, only limited data will be available.</span></span>

<span data-ttu-id="bc139-155">As informações do dispositivo expostos não estarão disponíveis para CVEs com software sem suporte.</span><span class="sxs-lookup"><span data-stu-id="bc139-155">Exposed device information will not be available for CVEs with unsupported software.</span></span> <span data-ttu-id="bc139-156">Filtrar por software sem suporte selecionando a opção "Não disponível" na seção "Dispositivos expostos".</span><span class="sxs-lookup"><span data-stu-id="bc139-156">Filter by unsupported software by selecting the "Not available" option in the "Exposed devices" section.</span></span>

 ![Filtro de dispositivos expostos.](images/tvm-exposed-devices-filter.png)

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a><span data-ttu-id="bc139-158">Exibir entradas CVE (Common Vulnerabilities and Exposures) em outros locais</span><span class="sxs-lookup"><span data-stu-id="bc139-158">View Common Vulnerabilities and Exposures (CVE) entries in other places</span></span>

### <a name="top-vulnerable-software-in-the-dashboard"></a><span data-ttu-id="bc139-159">Principais softwares vulneráveis no painel</span><span class="sxs-lookup"><span data-stu-id="bc139-159">Top vulnerable software in the dashboard</span></span>

1. <span data-ttu-id="bc139-160">Vá para o painel de gerenciamento de ameaças e [vulnerabilidades](tvm-dashboard-insights.md) e role para baixo até o widget de **software principal vulnerável.**</span><span class="sxs-lookup"><span data-stu-id="bc139-160">Go to the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) and scroll down to the **Top vulnerable software** widget.</span></span> <span data-ttu-id="bc139-161">Você verá o número de vulnerabilidades encontradas em cada software, juntamente com informações de ameaça e uma exibição de alto nível da exposição do dispositivo ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="bc139-161">You will see the number of vulnerabilities found in each software, along with threat information and a high-level view of device exposure over time.</span></span>

    ![Principal cartão de software vulnerável com quatro colunas: software, pontos fracos, ameaças, dispositivos expostos.](images/tvm-top-vulnerable-software500.png)

2. <span data-ttu-id="bc139-163">Selecione o software que você deseja investigar para ir para uma página de detalhamento.</span><span class="sxs-lookup"><span data-stu-id="bc139-163">Select the software you want to investigate to go to a drilldown page.</span></span>
3. <span data-ttu-id="bc139-164">Selecione a **guia Vulnerabilidades Descobertas.**</span><span class="sxs-lookup"><span data-stu-id="bc139-164">Select the **Discovered vulnerabilities** tab.</span></span>
4. <span data-ttu-id="bc139-165">Selecione a vulnerabilidade que você deseja investigar para obter mais informações sobre detalhes de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="bc139-165">Select the vulnerability you want to investigate for more information on vulnerability details</span></span>

    ![Visão geral de detalhamento do Windows Server 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a><span data-ttu-id="bc139-167">Descobrir vulnerabilidades na página do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bc139-167">Discover vulnerabilities in the device page</span></span>

<span data-ttu-id="bc139-168">Exibir informações de pontos fracos relacionados na página do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bc139-168">View related weaknesses information in the device page.</span></span>

1. <span data-ttu-id="bc139-169">Vá até a barra de menus do Centro de Segurança do Microsoft Defender e selecione o ícone do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bc139-169">Go to the Microsoft Defender Security Center navigation menu bar, then select the device icon.</span></span> <span data-ttu-id="bc139-170">A **página de lista Dispositivos** é aberta.</span><span class="sxs-lookup"><span data-stu-id="bc139-170">The **Devices list** page opens.</span></span>
2. <span data-ttu-id="bc139-171">Na página **lista Dispositivos,** selecione o nome do dispositivo que você deseja investigar.</span><span class="sxs-lookup"><span data-stu-id="bc139-171">In the **Devices list** page, select the device name that you want to investigate.</span></span>

    ![Lista de dispositivos com dispositivo selecionado para investigar.](images/tvm_machinetoinvestigate.png)

3. <span data-ttu-id="bc139-173">A página do dispositivo será aberta com detalhes e opções de resposta para o dispositivo que você deseja investigar.</span><span class="sxs-lookup"><span data-stu-id="bc139-173">The device page will open with details and response options for the device you want to investigate.</span></span>
4. <span data-ttu-id="bc139-174">Selecione **Vulnerabilidades descobertas.**</span><span class="sxs-lookup"><span data-stu-id="bc139-174">Select **Discovered vulnerabilities**.</span></span>

    ![Página do dispositivo com detalhes e opções de resposta.](images/tvm-discovered-vulnerabilities.png)

5. <span data-ttu-id="bc139-176">Selecione a vulnerabilidade que você deseja investigar para abrir um painel de sobremenu com os detalhes do CVE, como: descrição da vulnerabilidade, insights de ameaças e lógica de detecção.</span><span class="sxs-lookup"><span data-stu-id="bc139-176">Select the vulnerability that you want to investigate to open up a flyout panel with the CVE details, such as: vulnerability description, threat insights, and detection logic.</span></span>

#### <a name="cve-detection-logic"></a><span data-ttu-id="bc139-177">Lógica de Detecção CVE</span><span class="sxs-lookup"><span data-stu-id="bc139-177">CVE Detection logic</span></span>

<span data-ttu-id="bc139-178">Semelhante à evidência de software, agora mostramos a lógica de detecção que aplicamos em um dispositivo para dizer que ele está vulnerável.</span><span class="sxs-lookup"><span data-stu-id="bc139-178">Similar to the software evidence, we now show the detection logic we applied on a device in order to state that it's vulnerable.</span></span> <span data-ttu-id="bc139-179">A nova seção é chamada de "Lógica de Detecção" (em qualquer vulnerabilidade descoberta na página do dispositivo) e mostra a lógica de detecção e a origem.</span><span class="sxs-lookup"><span data-stu-id="bc139-179">The new section is called "Detection Logic" (in any discovered vulnerability in the device page) and shows the detection logic and source.</span></span>

<span data-ttu-id="bc139-180">A categoria "Recurso do sistema operacional" também é mostrada em cenários relevantes.</span><span class="sxs-lookup"><span data-stu-id="bc139-180">The "OS Feature" category is also shown in relevant scenarios.</span></span> <span data-ttu-id="bc139-181">Um CVE afetaria dispositivos que executem um sistema operacional vulnerável somente se um componente do sistema operacional específico estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="bc139-181">A CVE would affect devices that run a vulnerable OS only if a specific OS component is enabled.</span></span> <span data-ttu-id="bc139-182">Digamos que o Windows Server 2019 tenha vulnerabilidade em seu componente DNS.</span><span class="sxs-lookup"><span data-stu-id="bc139-182">Let's say Windows Server 2019 has vulnerability in its DNS component.</span></span> <span data-ttu-id="bc139-183">Com esse novo recurso, só anexamos esse CVE aos dispositivos Windows Server 2019 com a funcionalidade DNS habilitada em seu sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="bc139-183">With this new capability, we’ll only attach this CVE to the Windows Server 2019 devices with the DNS capability enabled in their OS.</span></span>

![Exemplo de Lógica de Detecção que lista o software detectado no dispositivo e nos KBs.](images/tvm-cve-detection-logic.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="bc139-185">Imprecisão de relatório</span><span class="sxs-lookup"><span data-stu-id="bc139-185">Report inaccuracy</span></span>

<span data-ttu-id="bc139-186">Reporte um falso positivo quando vir qualquer informação vagas, impreciso ou incompleta.</span><span class="sxs-lookup"><span data-stu-id="bc139-186">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="bc139-187">Você também pode relatar as recomendações de segurança que já foram remediadas.</span><span class="sxs-lookup"><span data-stu-id="bc139-187">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="bc139-188">Abra o CVE na página Fraquezas.</span><span class="sxs-lookup"><span data-stu-id="bc139-188">Open the CVE on the Weaknesses page.</span></span>
2. <span data-ttu-id="bc139-189">Selecione **Relatório impreciso** e um painel de sub-subfalsão será aberto.</span><span class="sxs-lookup"><span data-stu-id="bc139-189">Select **Report inaccuracy** and a flyout pane will open.</span></span>
3. <span data-ttu-id="bc139-190">Selecione a categoria impreciso no menu suspenso e preencha seu endereço de email e detalhes impreciso.</span><span class="sxs-lookup"><span data-stu-id="bc139-190">Select the inaccuracy category from the drop-down menu and fill in your email address and inaccuracy details.</span></span>
4. <span data-ttu-id="bc139-191">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="bc139-191">Select **Submit**.</span></span> <span data-ttu-id="bc139-192">Seus comentários são enviados imediatamente para os especialistas em gerenciamento de ameaças e vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="bc139-192">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bc139-193">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="bc139-193">Related articles</span></span>

- [<span data-ttu-id="bc139-194">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="bc139-194">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="bc139-195">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="bc139-195">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="bc139-196">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="bc139-196">Software inventory</span></span>](tvm-software-inventory.md)
- [<span data-ttu-id="bc139-197">Painel de insights</span><span class="sxs-lookup"><span data-stu-id="bc139-197">Dashboard insights</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="bc139-198">Exibir e organizar a lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="bc139-198">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
