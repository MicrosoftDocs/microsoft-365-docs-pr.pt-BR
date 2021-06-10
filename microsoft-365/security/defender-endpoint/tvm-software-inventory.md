---
title: Inventário de software em Gerenciamento de Ameaças e Vulnerabilidades
description: A página de inventário de software do Microsoft Defender para o Gerenciamento de Ameaças e Vulnerabilidades do Endpoint mostra quantas fraquezas e vulnerabilidades foram detectadas no software.
keywords: Gerenciamento de Ameaças e Vulnerabilidades, Microsoft Defender para Ponto de Extremidade, Inventário de software do Microsoft Defender para Ponto de Extremidade, Microsoft Defender for Endpoint threat & Gerenciamento de Vulnerabilidades, Microsoft Defender for Endpoint threat & Gerenciamento de Vulnerabilidades software inventory, Microsoft Defender for Endpoint tvm software inventory, inventário de software tvm
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
ms.openlocfilehash: 0d270760cfed965c8190668afcdb1cc25223d2b1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933716"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="fa0d6-104">Inventário de software - Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="fa0d6-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fa0d6-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="fa0d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="fa0d6-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="fa0d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fa0d6-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="fa0d6-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="fa0d6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fa0d6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fa0d6-109">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="fa0d6-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fa0d6-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="fa0d6-111">O inventário de software no Gerenciamento de Ameaças e Vulnerabilidades é uma lista de softwares conhecidos em sua organização com enumerações de [plataformas comuns oficiais (CPE)](https://nvd.nist.gov/products/cpe).</span><span class="sxs-lookup"><span data-stu-id="fa0d6-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="fa0d6-112">Os produtos de software sem uma CPE oficial não têm vulnerabilidades publicadas.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="fa0d6-113">Ele também inclui detalhes como o nome do fornecedor, número de pontos fracos, ameaças e número de dispositivos expostos.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="fa0d6-114">Como funciona</span><span class="sxs-lookup"><span data-stu-id="fa0d6-114">How it works</span></span>

<span data-ttu-id="fa0d6-115">No campo da descoberta, estamos aproveitando o mesmo conjunto de sinais que é responsável pela avaliação de detecção e vulnerabilidade no Microsoft Defender para recursos de detecção e resposta de ponto de [extremidade.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="fa0d6-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="fa0d6-116">Como é em tempo real, em questão de minutos, você verá informações de vulnerabilidade à medida que elas são descobertas.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="fa0d6-117">O mecanismo captura automaticamente informações de vários feeds de segurança.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="fa0d6-118">Na verdade, você verá se um software específico está conectado a uma campanha de ameaça ao vivo.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="fa0d6-119">Ele também fornece um link para um relatório de Análise de Ameaças assim que ele está disponível.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="fa0d6-120">Navegue até a página Inventário de software</span><span class="sxs-lookup"><span data-stu-id="fa0d6-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="fa0d6-121">Acesse a página Inventário de software selecionando **Inventário de software** Gerenciamento de Ameaças e Vulnerabilidades menu de navegação no [Central de Segurança do Microsoft Defender](portal-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fa0d6-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="fa0d6-122">Exibir software em dispositivos específicos nas páginas de dispositivos individuais da lista [de dispositivos](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fa0d6-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="fa0d6-123">Se você procurar software usando a pesquisa global do Microsoft Defender for Endpoint, certifique-se de colocar um sublinhado em vez de um espaço.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="fa0d6-124">Por exemplo, para os melhores resultados de pesquisa, você escreveria "windows_10" em vez de "Windows 10".</span><span class="sxs-lookup"><span data-stu-id="fa0d6-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="fa0d6-125">Visão geral do inventário de software</span><span class="sxs-lookup"><span data-stu-id="fa0d6-125">Software inventory overview</span></span>

<span data-ttu-id="fa0d6-126">A **página inventário** de software é aberta com uma lista de softwares instalados em sua rede, incluindo o nome do fornecedor, as fraquezas encontradas, as ameaças associadas a eles, dispositivos expostos, impacto na pontuação de exposição e marcas.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="fa0d6-127">Você pode filtrar a exibição de lista com base em pontos fracos encontrados no software, ameaças associadas a eles e marcas como se o software atingiu o fim do suporte.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![Exemplo da página inicial do inventário de software.](images/tvm-software-inventory.png)

<span data-ttu-id="fa0d6-129">Selecione o software que você deseja investigar.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="fa0d6-130">Um painel de sobrevoo será aberto com uma exibição mais compacta das informações na página.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="fa0d6-131">Você pode mergulhar mais profundamente na investigação e selecionar **Abrir página de software** ou sinalizar quaisquer inconsistências técnicas selecionando Report **inexatidão**.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="fa0d6-132">Software que não tem suporte</span><span class="sxs-lookup"><span data-stu-id="fa0d6-132">Software that isn't supported</span></span>

<span data-ttu-id="fa0d6-133">Softwares que não são suportados atualmente por ameaças & Gerenciamento de Vulnerabilidades podem estar presentes na página Inventário de software.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="fa0d6-134">Como não há suporte, apenas dados limitados estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="fa0d6-135">Filtrar por software sem suporte com a opção "Não disponível" na seção "Fraqueza".</span><span class="sxs-lookup"><span data-stu-id="fa0d6-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![Filtro de software sem suporte.](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="fa0d6-137">O seguinte indica que não há suporte para um software:</span><span class="sxs-lookup"><span data-stu-id="fa0d6-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="fa0d6-138">O campo Pontos Fracos mostra "Não disponível"</span><span class="sxs-lookup"><span data-stu-id="fa0d6-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="fa0d6-139">O campo Dispositivos Expostos mostra um traço</span><span class="sxs-lookup"><span data-stu-id="fa0d6-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="fa0d6-140">Texto informacional adicionado no painel lateral e na página de software</span><span class="sxs-lookup"><span data-stu-id="fa0d6-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="fa0d6-141">A página de software não terá as recomendações de segurança, vulnerabilidades descobertas ou seções de linha do tempo do evento</span><span class="sxs-lookup"><span data-stu-id="fa0d6-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="fa0d6-142">Atualmente, os produtos sem um CPE não são mostrados na página de inventário de software, somente no inventário de software no nível do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="fa0d6-143">Inventário de software em dispositivos</span><span class="sxs-lookup"><span data-stu-id="fa0d6-143">Software inventory on devices</span></span>

<span data-ttu-id="fa0d6-144">No painel Central de Segurança do Microsoft Defender de navegação, vá para a lista **[Dispositivos](machines-view-overview.md)**.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="fa0d6-145">Selecione o nome de um dispositivo para abrir a página do dispositivo (como Computador1) e selecione a guia Inventário de **software** para ver uma lista de todos os softwares conhecidos presentes no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="fa0d6-146">Selecione uma entrada de software específica para abrir o sobrevoo com mais informações.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="fa0d6-147">O software pode estar visível no nível do dispositivo, mesmo que ele não tenha suporte no momento por Gerenciamento de Ameaças e Vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="fa0d6-148">No entanto, apenas dados limitados estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-148">However, only limited data will be available.</span></span> <span data-ttu-id="fa0d6-149">Você saberá se o software não tem suporte porque ele dirá "Não disponível" na coluna "Fraqueza".</span><span class="sxs-lookup"><span data-stu-id="fa0d6-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="fa0d6-150">Software sem CPE também pode aparecer no inventário de software específico deste dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="fa0d6-151">Evidências de software</span><span class="sxs-lookup"><span data-stu-id="fa0d6-151">Software evidence</span></span>

<span data-ttu-id="fa0d6-152">Consulte evidências de onde detectamos um software específico em um dispositivo do Registro, disco ou ambos. Você pode encontrá-lo em qualquer dispositivo no inventário de software do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="fa0d6-153">Selecione um nome de software para abrir o sobrevoo e procure a seção chamada "Evidência de Software".</span><span class="sxs-lookup"><span data-stu-id="fa0d6-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![Exemplo de evidência de software Windows 10 da lista de dispositivos, mostrando o caminho do registro de evidências de software.](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="fa0d6-155">Páginas de software</span><span class="sxs-lookup"><span data-stu-id="fa0d6-155">Software pages</span></span>

<span data-ttu-id="fa0d6-156">Você pode exibir páginas de software de algumas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="fa0d6-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="fa0d6-157">Página de inventário de software > Selecione um nome de software > selecione **Abrir página de software** no flyout</span><span class="sxs-lookup"><span data-stu-id="fa0d6-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="fa0d6-158">[Página de recomendações](tvm-security-recommendation.md) de segurança > Selecione uma recomendação > Selecione **Abrir software** no sobrevoo</span><span class="sxs-lookup"><span data-stu-id="fa0d6-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="fa0d6-159">[Página de](threat-and-vuln-mgt-event-timeline.md) linha do tempo do evento > Selecione um evento > Selecione o nome do software hiperlink (como Visual Studio 2017) na seção chamada "Componente relacionado" no flyout</span><span class="sxs-lookup"><span data-stu-id="fa0d6-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="fa0d6-160">Uma página completa aparecerá com todos os detalhes de um software específico e as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="fa0d6-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="fa0d6-161">Painel lateral com informações do fornecedor, prevalência do software na organização (incluindo o número de dispositivos em que ele está instalado e dispositivos expostos que não são remendados), se e exploração está disponível e impacto na pontuação de exposição.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="fa0d6-162">Visualizações de dados mostrando o número de vulnerabilidades e configurações inconfigurações e gravidade.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="fa0d6-163">Além disso, gráficos com o número de dispositivos expostos.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="fa0d6-164">Guias mostrando informações como:</span><span class="sxs-lookup"><span data-stu-id="fa0d6-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="fa0d6-165">Recomendações de segurança correspondentes para as fraquezas e vulnerabilidades identificadas.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="fa0d6-166">CVEs nomeadas de vulnerabilidades descobertas.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="fa0d6-167">Dispositivos que têm o software instalado (juntamente com o nome do dispositivo, domínio, sistema operacional e muito mais).</span><span class="sxs-lookup"><span data-stu-id="fa0d6-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="fa0d6-168">Lista de versões de software (incluindo o número de dispositivos em que a versão está instalada, o número de vulnerabilidades descobertas e os nomes dos dispositivos instalados).</span><span class="sxs-lookup"><span data-stu-id="fa0d6-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![Página de exemplo de software Visual Studio 2017 com detalhes de software, pontos fracos, dispositivos expostos e muito mais.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="fa0d6-170">Imprecisão de relatório</span><span class="sxs-lookup"><span data-stu-id="fa0d6-170">Report inaccuracy</span></span>

<span data-ttu-id="fa0d6-171">Reporte um falso positivo quando vir qualquer informação vagas, impreciso ou incompleta.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="fa0d6-172">Você também pode relatar as recomendações de segurança que já foram remediadas.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="fa0d6-173">Abra o sobrevoo de software na página Inventário de software.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="fa0d6-174">Selecione **Relatório impreciso**.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="fa0d6-175">No painel submenu, selecione a categoria impreciso no menu suspenso, preencha seu endereço de email e detalhes sobre a imprecisão.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="fa0d6-176">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-176">Select **Submit**.</span></span> <span data-ttu-id="fa0d6-177">Seus comentários são enviados imediatamente aos especialistas Gerenciamento de Ameaças e Vulnerabilidades segurança.</span><span class="sxs-lookup"><span data-stu-id="fa0d6-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fa0d6-178">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="fa0d6-178">Related articles</span></span>

- [<span data-ttu-id="fa0d6-179">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="fa0d6-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="fa0d6-180">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="fa0d6-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="fa0d6-181">Cronograma do evento</span><span class="sxs-lookup"><span data-stu-id="fa0d6-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="fa0d6-182">Exibir e organizar a lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="fa0d6-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
