---
title: Correção de vulnerabilidades com Gerenciamento de Ameaças e Vulnerabilidades
description: Remediar as deficiências de segurança descobertas por meio de recomendações de segurança e criar exceções, se necessário, Gerenciamento de Ameaças e Vulnerabilidades.
keywords: Microsoft Defender for Endpoint tvm remediation, Microsoft Defender for Endpoint tvm, Gerenciamento de Ameaças e Vulnerabilidades, threat & Gerenciamento de Vulnerabilidades, threat & Gerenciamento de Vulnerabilidades remediation, tvm remediation intune, tvm remediation sccm
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
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840905"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="619a0-104">Correção de vulnerabilidades com Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="619a0-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="619a0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="619a0-105">**Applies to:**</span></span>
- [<span data-ttu-id="619a0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="619a0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="619a0-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="619a0-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="619a0-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="619a0-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="619a0-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="619a0-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="619a0-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="619a0-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="619a0-111">Solicitar correção</span><span class="sxs-lookup"><span data-stu-id="619a0-111">Request remediation</span></span>

<span data-ttu-id="619a0-112">A Gerenciamento de Ameaças e Vulnerabilidades no Microsoft Defender para Ponto de Extremidade faz a ponte entre administradores de SEGURANÇA e DES por meio do fluxo de trabalho de solicitação de correção.</span><span class="sxs-lookup"><span data-stu-id="619a0-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="619a0-113">Administradores de segurança como você podem solicitar que o Administrador de TI correção de uma vulnerabilidade das páginas de recomendação de **segurança** para o Intune.</span><span class="sxs-lookup"><span data-stu-id="619a0-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="619a0-114">Habilitar Microsoft Intune conexão</span><span class="sxs-lookup"><span data-stu-id="619a0-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="619a0-115">Para usar esse recurso, habilita suas Microsoft Intune conexões.</span><span class="sxs-lookup"><span data-stu-id="619a0-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="619a0-116">No Central de Segurança do Microsoft Defender, navegue **até** Configurações  >  **Recursos Avançados**  >  **Gerais.**</span><span class="sxs-lookup"><span data-stu-id="619a0-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="619a0-117">Role para baixo e procure **Microsoft Intune conexão**.</span><span class="sxs-lookup"><span data-stu-id="619a0-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="619a0-118">Por padrão, a alternância está desligada.</span><span class="sxs-lookup"><span data-stu-id="619a0-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="619a0-119">Ativar a **Microsoft Intune de conexão** de Microsoft Intune **.**</span><span class="sxs-lookup"><span data-stu-id="619a0-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="619a0-120">**Observação**: se você tiver a conexão do Intune habilitada, você terá uma opção para criar uma tarefa de segurança do Intune ao criar uma solicitação de correção.</span><span class="sxs-lookup"><span data-stu-id="619a0-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="619a0-121">Essa opção não será exibida se a conexão não estiver definida.</span><span class="sxs-lookup"><span data-stu-id="619a0-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="619a0-122">Consulte [Usar o Intune para correção de vulnerabilidades identificadas](/intune/atp-manage-vulnerabilities) pelo Microsoft Defender para Ponto de Extremidade para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="619a0-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="619a0-123">Etapas de solicitação de correção</span><span class="sxs-lookup"><span data-stu-id="619a0-123">Remediation request steps</span></span>

1. <span data-ttu-id="619a0-124">Vá para o menu Gerenciamento de Ameaças e Vulnerabilidades de navegação no Central de Segurança do Microsoft Defender e selecione [**Recomendações de segurança.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="619a0-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="619a0-125">Selecione uma recomendação de segurança que você gostaria de solicitar correção e selecione **Opções de correção.**</span><span class="sxs-lookup"><span data-stu-id="619a0-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="619a0-126">Preencha o formulário, incluindo o que você está solicitando correção, grupos de dispositivos aplicáveis, prioridade, data de vencimento e anotações opcionais.</span><span class="sxs-lookup"><span data-stu-id="619a0-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="619a0-127">Se você escolher a opção de correção "atenção necessária", a seleção de uma data de vencimento não estará disponível, pois não há nenhuma ação específica.</span><span class="sxs-lookup"><span data-stu-id="619a0-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="619a0-128">Selecione **Enviar solicitação**.</span><span class="sxs-lookup"><span data-stu-id="619a0-128">Select **Submit request**.</span></span> <span data-ttu-id="619a0-129">Enviar uma solicitação de correção cria um item de atividade de correção dentro Gerenciamento de Ameaças e Vulnerabilidades, que pode ser usado para monitorar o andamento da correção para essa recomendação.</span><span class="sxs-lookup"><span data-stu-id="619a0-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="619a0-130">Isso não disparará uma correção ou aplicará alterações a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="619a0-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="619a0-131">Notifique o administrador de IT sobre a nova solicitação e faça com que eles faça logoff no Intune para aprovar ou rejeitar a solicitação e iniciar uma implantação de pacote.</span><span class="sxs-lookup"><span data-stu-id="619a0-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="619a0-132">Vá para a [**página Correção**](tvm-remediation.md) para exibir o status da sua solicitação de correção.</span><span class="sxs-lookup"><span data-stu-id="619a0-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="619a0-133">Se você quiser verificar como o tíquete aparece no Intune, confira [Usar o Intune](/intune/atp-manage-vulnerabilities) para correção de vulnerabilidades identificadas pelo Microsoft Defender para o Ponto de Extremidade para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="619a0-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="619a0-134">Se sua solicitação envolver a correção de mais de 10.000 dispositivos, só podemos enviar 10.000 dispositivos para correção para o Intune.</span><span class="sxs-lookup"><span data-stu-id="619a0-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="619a0-135">Depois que as fraquezas de segurança cibernética da sua organização são [identificadas](tvm-security-recommendation.md)e mapeadas para recomendações de segurança ativas, comece a criar tarefas de segurança.</span><span class="sxs-lookup"><span data-stu-id="619a0-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="619a0-136">Você pode criar tarefas por meio da integração com Microsoft Intune onde os tíquetes de correção são criados.</span><span class="sxs-lookup"><span data-stu-id="619a0-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="619a0-137">Reduza a exposição da sua organização contra vulnerabilidades e aumente sua configuração de segurança, remediando as recomendações de segurança.</span><span class="sxs-lookup"><span data-stu-id="619a0-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="619a0-138">Exibir suas atividades de correção</span><span class="sxs-lookup"><span data-stu-id="619a0-138">View your remediation activities</span></span>

<span data-ttu-id="619a0-139">Quando você envia uma solicitação de correção da página Recomendações de segurança, ela inicia uma atividade de correção.</span><span class="sxs-lookup"><span data-stu-id="619a0-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="619a0-140">Uma tarefa de segurança é criada que pode ser rastreada na página Gerenciamento de Ameaças e Vulnerabilidades **Correção** e um tíquete de correção é criado Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="619a0-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="619a0-141">Se você escolher a opção de correção "atenção necessária", não haverá barra de progresso, status de tíquete ou data de vencimento, já que não há nenhuma ação real que possamos monitorar.</span><span class="sxs-lookup"><span data-stu-id="619a0-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="619a0-142">Depois de estar na página Correção, selecione a atividade de correção que você deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="619a0-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="619a0-143">Você pode seguir as etapas de correção, acompanhar o andamento, exibir a recomendação relacionada, exportar para CSV ou marcar como concluída.</span><span class="sxs-lookup"><span data-stu-id="619a0-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="619a0-144">![Exemplo da página Correção, com uma atividade de correção selecionada, e o flyout dessa atividade listando a descrição, as ferramentas de gerenciamento de dispositivo e serviço de IT e o progresso da correção do dispositivo.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="619a0-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="619a0-145">Há um período de retenção de 180 dias para atividades de correção concluídas.</span><span class="sxs-lookup"><span data-stu-id="619a0-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="619a0-146">Para manter a página correção com desempenho ideal, a atividade de correção será removida 6 meses após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="619a0-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="619a0-147">Concluído por coluna</span><span class="sxs-lookup"><span data-stu-id="619a0-147">Completed by column</span></span>

<span data-ttu-id="619a0-148">Acompanhe quem fechou a atividade de correção com a coluna "Concluído por" na página Correção.</span><span class="sxs-lookup"><span data-stu-id="619a0-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="619a0-149">**Endereço de** email : o email da pessoa que concluiu manualmente a tarefa</span><span class="sxs-lookup"><span data-stu-id="619a0-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="619a0-150">**Confirmação do** sistema : a tarefa foi concluída automaticamente (todos os dispositivos remediados)</span><span class="sxs-lookup"><span data-stu-id="619a0-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="619a0-151">**N/A**: As informações não estão disponíveis porque não sabemos como essa tarefa mais antiga foi concluída</span><span class="sxs-lookup"><span data-stu-id="619a0-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Criado por e concluído por colunas com duas linhas.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="619a0-154">Principais atividades de correção no painel</span><span class="sxs-lookup"><span data-stu-id="619a0-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="619a0-155">Exibir **Principais atividades de correção** no painel Gerenciamento de Ameaças e Vulnerabilidades [.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="619a0-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="619a0-156">Selecione qualquer uma das entradas para ir para a **página Correção.**</span><span class="sxs-lookup"><span data-stu-id="619a0-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="619a0-157">Você pode marcar a atividade de correção como concluída após a equipe de administração de TI remediar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="619a0-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Exemplo do cartão principais atividades de correção com uma tabela que lista as principais atividades geradas a partir de recomendações de segurança.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="619a0-159">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="619a0-159">Related articles</span></span>

- [<span data-ttu-id="619a0-160">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="619a0-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="619a0-161">Painel</span><span class="sxs-lookup"><span data-stu-id="619a0-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="619a0-162">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="619a0-162">Security recommendations</span></span>](tvm-security-recommendation.md)