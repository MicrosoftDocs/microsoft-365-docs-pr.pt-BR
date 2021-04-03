---
title: Recomendações de segurança por gerenciamento de ameaças e vulnerabilidades
description: Obter recomendações de segurança ativas priorizadas por ameaça, probabilidade de violação e valor, no gerenciamento de ameaças e vulnerabilidades.
keywords: gerenciamento de ameaças e vulnerabilidades, recomendação de segurança de tvm mdatp, recomendação de segurança cibernética, recomendação de segurança a ação
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
ms.openlocfilehash: 97d496271c1ef7185419f7d39956da0429f070aa
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500484"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="cbc7d-104">Recomendações de segurança - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cbc7d-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cbc7d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cbc7d-105">**Applies to:**</span></span>

- [<span data-ttu-id="cbc7d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cbc7d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="cbc7d-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cbc7d-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cbc7d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cbc7d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cbc7d-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cbc7d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cbc7d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="cbc7d-111">As deficiências de segurança cibernética identificadas em sua organização são mapeadas para recomendações de segurança ativas e priorizadas pelo impacto.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="cbc7d-112">Recomendações priorizadas ajudam a reduzir o tempo para mitigar ou remediar vulnerabilidades e impulsionar a conformidade.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="cbc7d-113">Cada recomendação de segurança inclui etapas de correção ativas.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="cbc7d-114">Para ajudar no gerenciamento de tarefas, a recomendação também pode ser enviada usando o Microsoft Intune e o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="cbc7d-115">Quando o cenário de ameaças muda, a recomendação também muda conforme coleta informações continuamente do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="cbc7d-116">Para obter emails sobre novos eventos de vulnerabilidade, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="cbc7d-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="cbc7d-117">Como funciona</span><span class="sxs-lookup"><span data-stu-id="cbc7d-117">How it works</span></span>

<span data-ttu-id="cbc7d-118">Cada dispositivo na organização é pontuado com base em três fatores importantes para ajudar os clientes a se concentrarem nas coisas certas no momento certo.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="cbc7d-119">**Ameaça** - Características das vulnerabilidades e explorações nos dispositivos de suas organizações e no histórico de violações.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="cbc7d-120">Com base nesses fatores, as recomendações de segurança mostram os links correspondentes para alertas ativos, campanhas de ameaças em andamento e seus relatórios de análise de ameaças correspondentes.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="cbc7d-121">**Probabilidade de violação** - Postura de segurança e resiliência da sua organização contra ameaças</span><span class="sxs-lookup"><span data-stu-id="cbc7d-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="cbc7d-122">**Valor comercial** - ativos, processos críticos e propriedades intelectuais da sua organização</span><span class="sxs-lookup"><span data-stu-id="cbc7d-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="cbc7d-123">Navegue até a página Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="cbc7d-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="cbc7d-124">Acesse a página Recomendações de segurança de algumas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="cbc7d-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="cbc7d-125">Menu de navegação de gerenciamento de ameaças e vulnerabilidades no [Centro de Segurança do Microsoft Defender](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cbc7d-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="cbc7d-126">Principais recomendações de segurança no painel de gerenciamento de ameaças [e vulnerabilidades](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="cbc7d-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="cbc7d-127">Exibir recomendações de segurança relacionadas nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="cbc7d-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="cbc7d-128">Página de software</span><span class="sxs-lookup"><span data-stu-id="cbc7d-128">Software page</span></span>
- <span data-ttu-id="cbc7d-129">Página do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cbc7d-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="cbc7d-130">Menu de navegação</span><span class="sxs-lookup"><span data-stu-id="cbc7d-130">Navigation menu</span></span>

<span data-ttu-id="cbc7d-131">Vá para o menu de navegação de gerenciamento de ameaças e vulnerabilidades e selecione **Recomendações de segurança.**</span><span class="sxs-lookup"><span data-stu-id="cbc7d-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="cbc7d-132">A página contém uma lista de recomendações de segurança para as ameaças e vulnerabilidades encontradas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="cbc7d-133">Principais recomendações de segurança no painel de gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cbc7d-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="cbc7d-134">Em um determinado dia como Administrador de Segurança, [](tvm-dashboard-insights.md) você pode dar uma [](tvm-exposure-score.md) olhada no painel de gerenciamento de ameaças e vulnerabilidades para ver sua pontuação de exposição lado a lado com sua Pontuação Segura da [Microsoft para Dispositivos.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="cbc7d-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="cbc7d-135">O objetivo é **reduzir** a exposição da sua  organização contra vulnerabilidades e aumentar a segurança do dispositivo da sua organização para ser mais resiliente contra ataques de ameaças de segurança cibernética.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="cbc7d-136">A lista de recomendações de segurança principais pode ajudá-lo a atingir essa meta.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-136">The top security recommendations list can help you achieve that goal.</span></span>

![Exemplo de cartão de principais recomendações de segurança, com quatro recomendações de segurança.](images/top-security-recommendations350.png)

<span data-ttu-id="cbc7d-138">As principais recomendações de segurança listam as oportunidades de melhoria priorizadas com base nos fatores importantes mencionados na seção anterior : ameaça, probabilidade de violação e valor.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="cbc7d-139">Selecionar uma recomendação levará você para a página de recomendações de segurança com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="cbc7d-140">Visão geral das recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="cbc7d-140">Security recommendations overview</span></span>

<span data-ttu-id="cbc7d-141">Recomendações de exibição, o número de pontos fracos encontrados, componentes relacionados, insights de ameaças, número de dispositivos expostos, status, tipo de correção, atividades de correção, impacto na pontuação de exposição e Pontuação Segura da Microsoft para Dispositivos e marcas associadas.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="cbc7d-142">A cor do gráfico **de dispositivos expostos** muda conforme a tendência muda.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="cbc7d-143">Se o número de dispositivos expostos estiver em alta, a cor será muda para vermelho.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="cbc7d-144">Se houver uma diminuição no número de dispositivos expostos, a cor do gráfico mudará para verde.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="cbc7d-145">O gerenciamento de ameaças e vulnerabilidades mostra dispositivos que estavam em uso até **30 dias** atrás.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="cbc7d-146">Isso é diferente do restante do Microsoft Defender para Ponto de Extremidade, onde se um dispositivo não estiver em uso há mais de 7 dias, ele terá um status 'Inativo'.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![Exemplo da página inicial para recomendações de segurança.](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="cbc7d-148">Ícones</span><span class="sxs-lookup"><span data-stu-id="cbc7d-148">Icons</span></span>

<span data-ttu-id="cbc7d-149">Ícones úteis também chamam sua atenção rapidamente:</span><span class="sxs-lookup"><span data-stu-id="cbc7d-149">Useful icons also quickly call your attention to:</span></span>
- ![seta atingindo um destino](images/tvm_alert_icon.png) <span data-ttu-id="cbc7d-151">possíveis alertas ativos</span><span class="sxs-lookup"><span data-stu-id="cbc7d-151">possible active alerts</span></span>
- ![bug vermelho](images/tvm_bug_icon.png) <span data-ttu-id="cbc7d-153">explorações públicas associadas</span><span class="sxs-lookup"><span data-stu-id="cbc7d-153">associated public exploits</span></span>
- ![lâmpada](images/tvm_insight_icon.png) <span data-ttu-id="cbc7d-155">insights de recomendação</span><span class="sxs-lookup"><span data-stu-id="cbc7d-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="cbc7d-156">Explorar opções de recomendação de segurança</span><span class="sxs-lookup"><span data-stu-id="cbc7d-156">Explore security recommendation options</span></span>

<span data-ttu-id="cbc7d-157">Selecione a recomendação de segurança que você deseja investigar ou processar.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-157">Select the security recommendation that you want to investigate or process.</span></span>

![Exemplo de uma página de recomendação de segurança.](images/secrec-flyouteolsw.png)

<span data-ttu-id="cbc7d-159">No sobrevoo, você pode escolher qualquer uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="cbc7d-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="cbc7d-160">**Abra a página de** software - Abra a página de software para obter mais contexto sobre o software e como ele é distribuído.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="cbc7d-161">As informações podem incluir contexto de ameaça, recomendações associadas, pontos fracos descobertos, número de dispositivos expostos, vulnerabilidades descobertas, nomes e detalhes de dispositivos com o software instalado e distribuição de versão.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="cbc7d-162">[**Opções de correção**](tvm-remediation.md) - Envie uma solicitação de correção para abrir um tíquete no Microsoft Intune para que o administrador de IT escolha e endereço.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="cbc7d-163">Acompanhe a atividade de correção na página Correção.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="cbc7d-164">[**Opções de**](tvm-exception.md) exceção - Envie uma exceção, forneça justificativa e desembaixe a duração da exceção se você ainda não puder remediar o problema.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="cbc7d-165">Quando uma alteração de software é feita em um dispositivo, normalmente leva 2 horas para que os dados sejam refletidos no portal de segurança.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="cbc7d-166">No entanto, às vezes, pode levar mais tempo.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="cbc7d-167">As alterações de configuração podem levar de 4 a 24 horas.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="cbc7d-168">Investigar alterações na exposição ou impacto do dispositivo</span><span class="sxs-lookup"><span data-stu-id="cbc7d-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="cbc7d-169">Se houver um grande salto no número de dispositivos expostos ou um aumento acentuado no impacto na pontuação de exposição da sua organização e na Pontuação Segura da Microsoft para Dispositivos, essa recomendação de segurança vale a pena investigar.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="cbc7d-170">Selecione a página de recomendação e **abrir software**</span><span class="sxs-lookup"><span data-stu-id="cbc7d-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="cbc7d-171">Selecione a **guia Linha do tempo** do evento para exibir todos os eventos impactados relacionados a esse software, como novas vulnerabilidades ou novas explorações públicas.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="cbc7d-172">Saiba mais sobre a linha do tempo do evento</span><span class="sxs-lookup"><span data-stu-id="cbc7d-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="cbc7d-173">Decida como resolver o aumento ou a exposição da sua organização, como enviar uma solicitação de correção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="cbc7d-174">Solicitar correção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-174">Request remediation</span></span>

<span data-ttu-id="cbc7d-175">O recurso de correção de ameaças e vulnerabilidades faz a ponte entre os administradores de Segurança e DES por meio do fluxo de trabalho de solicitação de correção.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="cbc7d-176">Os administradores de segurança como você podem solicitar que o Administrador de TI correção de uma vulnerabilidade da página de recomendação **de** segurança para o Intune.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="cbc7d-177">Saiba mais sobre opções de correção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="cbc7d-178">Como solicitar correção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-178">How to request remediation</span></span>

<span data-ttu-id="cbc7d-179">Selecione uma recomendação de segurança que você gostaria de solicitar correção e selecione **Opções de correção.**</span><span class="sxs-lookup"><span data-stu-id="cbc7d-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="cbc7d-180">Preencha o formulário e selecione **Enviar solicitação**.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="cbc7d-181">Vá para a [**página Correção**](tvm-remediation.md) para exibir o status da sua solicitação de correção.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="cbc7d-182">Saiba mais sobre como solicitar correção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="cbc7d-183">Arquivo para exceção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-183">File for exception</span></span>

<span data-ttu-id="cbc7d-184">Como alternativa a uma solicitação de correção quando uma recomendação não é relevante no momento, você pode criar exceções para recomendações.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="cbc7d-185">Saiba mais sobre exceções</span><span class="sxs-lookup"><span data-stu-id="cbc7d-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="cbc7d-186">Somente usuários com permissões de "tratamento de exceções" podem adicionar exceção.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="cbc7d-187">[Saiba mais sobre funções RBAC](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cbc7d-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="cbc7d-188">Quando uma exceção é criada para uma recomendação, a recomendação não está mais ativa.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="cbc7d-189">O estado de recomendação mudará para **Exceção Total** ou **Parcial** (por grupo de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="cbc7d-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="cbc7d-190">Como criar uma exceção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-190">How to create an exception</span></span>

<span data-ttu-id="cbc7d-191">Selecione uma recomendação de segurança para a que você gostaria de criar uma exceção e selecione **Opções de exceção.**</span><span class="sxs-lookup"><span data-stu-id="cbc7d-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![Mostrando onde o botão para "opções de exceção" está localizado em um flyout de recomendação de segurança.](images/tvm-exception-options.png)

<span data-ttu-id="cbc7d-193">Preencha o formulário e envie.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-193">Fill out the form and submit.</span></span> <span data-ttu-id="cbc7d-194">Para exibir todas as exceções (atuais e [](tvm-remediation.md) passadas), navegue até a página Correção  no menu Gerenciamento de Vulnerabilidades & Ameaça e selecione **a** guia [Exceções.](tvm-exception.md#create-an-exception) Saiba mais sobre como criar uma exceção</span><span class="sxs-lookup"><span data-stu-id="cbc7d-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="cbc7d-195">Imprecisão de relatório</span><span class="sxs-lookup"><span data-stu-id="cbc7d-195">Report inaccuracy</span></span>

<span data-ttu-id="cbc7d-196">Você pode relatar um falso positivo quando vir qualquer informação de recomendação de segurança impreciso, impreciso, incompleta ou já remediada.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="cbc7d-197">Abra a recomendação segurança.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="cbc7d-198">Selecione os três pontos ao lado da recomendação de segurança que você deseja relatar e selecione **Relatar imprecisão**.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![Mostrando onde o botão "Relatar imprecisão" está em um sub-relatório de recomendação de segurança.](images/report-inaccuracy500.png)

3. <span data-ttu-id="cbc7d-200">No painel submenu, selecione a categoria impreciso no menu suspenso, preencha seu endereço de email e detalhes sobre a imprecisão.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="cbc7d-201">Selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-201">Select **Submit**.</span></span> <span data-ttu-id="cbc7d-202">Seus comentários são enviados imediatamente para os especialistas em gerenciamento de ameaças e vulnerabilidades.</span><span class="sxs-lookup"><span data-stu-id="cbc7d-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cbc7d-203">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="cbc7d-203">Related articles</span></span>

- [<span data-ttu-id="cbc7d-204">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cbc7d-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="cbc7d-205">Painel</span><span class="sxs-lookup"><span data-stu-id="cbc7d-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="cbc7d-206">Pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="cbc7d-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="cbc7d-207">Microsoft Secure Score para dispositivos</span><span class="sxs-lookup"><span data-stu-id="cbc7d-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="cbc7d-208">Correção de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="cbc7d-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="cbc7d-209">Criar e exibir exceções para recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="cbc7d-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="cbc7d-210">Cronograma do evento</span><span class="sxs-lookup"><span data-stu-id="cbc7d-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
