---
title: Alertas de segurança do Microsoft Defender para Identidade no Microsoft 365 Defender
description: Saiba como gerenciar e revisar alertas de segurança emitidos pelo Microsoft Defender for Identity no Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657758"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a><span data-ttu-id="63856-103">Alertas de segurança do Defender para Identidade no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63856-103">Defender for Identity security alerts in Microsoft 365 Defender</span></span>

<span data-ttu-id="63856-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="63856-104">**Applies to:**</span></span>

- <span data-ttu-id="63856-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63856-105">Microsoft 365 Defender</span></span>
- <span data-ttu-id="63856-106">Microsoft Defender para Identidade</span><span class="sxs-lookup"><span data-stu-id="63856-106">Defender for Identity</span></span>

<span data-ttu-id="63856-107">Este artigo explica as noções básicas de como trabalhar com alertas de segurança do [Microsoft Defender for Identity](/defender-for-identity) no centro de segurança Microsoft 365 de [segurança.](/microsoft-365/security/defender/overview-security-center)</span><span class="sxs-lookup"><span data-stu-id="63856-107">This article explains the basics of how to work with [Microsoft Defender for Identity](/defender-for-identity) security alerts in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center).</span></span>

<span data-ttu-id="63856-108">Os alertas do Defender para Identidade são integrados na Microsoft 365 de segurança [com](https://security.microsoft.com) um formato de página de alerta de identidade dedicado.</span><span class="sxs-lookup"><span data-stu-id="63856-108">Defender for Identity alerts are natively integrated into the [Microsoft 365 security center](https://security.microsoft.com) with a dedicated Identity alert page format.</span></span> <span data-ttu-id="63856-109">Isso marca a primeira etapa da jornada para introduzir a experiência completa do [Microsoft Defender for Identity no Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="63856-109">This marks the first step in the journey to [introduce the full Microsoft Defender for Identity experience into Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).</span></span>

<span data-ttu-id="63856-110">A nova página de alerta de identidade oferece aos clientes do Microsoft Defender for Identity melhor enriquecimento de sinal entre domínios e novos recursos automatizados de resposta de identidade.</span><span class="sxs-lookup"><span data-stu-id="63856-110">The new Identity alert page gives Microsoft Defender for Identity customers better cross-domain signal enrichment and new automated identity response capabilities.</span></span> <span data-ttu-id="63856-111">Ele garante que você permaneça seguro e ajude a melhorar a eficiência de suas operações de segurança.</span><span class="sxs-lookup"><span data-stu-id="63856-111">It ensures that you stay secure and helps improve the efficiency of your security operations.</span></span>

<span data-ttu-id="63856-112">Um dos benefícios da investigação de alertas por meio do [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) é que os alertas do Microsoft Defender for Identity são correlacionados ainda mais com as informações obtidas de cada um dos outros produtos do pacote.</span><span class="sxs-lookup"><span data-stu-id="63856-112">One of the benefits of investigating alerts through [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) is that Microsoft Defender for Identity alerts are further correlated with information obtained from each of the other products in the suite.</span></span> <span data-ttu-id="63856-113">Esses alertas aprimorados são consistentes com os outros formatos de alerta do Microsoft 365 Defender provenientes do [Microsoft Defender para Office 365](/microsoft-365/security/office-365-security) e do Microsoft Defender para Ponto de [Extremidade.](/microsoft-365/security/defender-endpoint)</span><span class="sxs-lookup"><span data-stu-id="63856-113">These enhanced alerts are consistent with the other Microsoft 365 Defender alert formats originating from [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) and [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span> <span data-ttu-id="63856-114">A nova página elimina efetivamente a necessidade de navegar até outro portal de produto para investigar alertas associados à identidade.</span><span class="sxs-lookup"><span data-stu-id="63856-114">The new page effectively eliminates the need to navigate to another product portal to investigate alerts associated with identity.</span></span>

<span data-ttu-id="63856-115">Os alertas provenientes do Defender para Identidade agora podem disparar os recursos de investigação e resposta [automatizadas do Microsoft 365 Defender (AIR),](/microsoft-365/security/defender/m365d-autoir) incluindo a correção automática de alertas e a mitigação de ferramentas e processos que podem contribuir para a atividade suspeita.</span><span class="sxs-lookup"><span data-stu-id="63856-115">Alerts originating from Defender for Identity can now trigger the [Microsoft 365 Defender automated investigation and response (AIR)](/microsoft-365/security/defender/m365d-autoir) capabilities, including automatically remediating alerts and the mitigation of tools and processes that can contribute to the suspicious activity.</span></span>

>[!IMPORTANT]
><span data-ttu-id="63856-116">Como parte da convergência com o Microsoft 365 Defender, algumas opções e detalhes foram alterados de sua localização no portal defender para identidade.</span><span class="sxs-lookup"><span data-stu-id="63856-116">As part of the convergence with Microsoft 365 Defender, some options and details have changed from their location in the Defender for Identity portal.</span></span> <span data-ttu-id="63856-117">Leia os detalhes abaixo para descobrir onde encontrar os recursos familiares e novos.</span><span class="sxs-lookup"><span data-stu-id="63856-117">Please read the details below to discover where to find both the familiar and new features.</span></span>

## <a name="review-security-alerts"></a><span data-ttu-id="63856-118">Revisar alertas de segurança</span><span class="sxs-lookup"><span data-stu-id="63856-118">Review security alerts</span></span>

<span data-ttu-id="63856-119">Os alertas podem ser acessados de vários locais, incluindo a página **Alertas,** a página Incidentes, as páginas de **Dispositivos individuais** **e** a partir da página De **busca** avançada.</span><span class="sxs-lookup"><span data-stu-id="63856-119">Alerts can be accessed from multiple locations, including the **Alerts** page, the **Incidents** page, the pages of individual **Devices**, and from the **Advanced hunting** page.</span></span> <span data-ttu-id="63856-120">Neste exemplo, revisaremos a página **Alertas.**</span><span class="sxs-lookup"><span data-stu-id="63856-120">In this example, we'll review the **Alerts page**.</span></span>  

<span data-ttu-id="63856-121">No centro [Microsoft 365 segurança,](https://security.microsoft.com/)vá para **Incidentes & alertas** e, em seguida, **para Alertas**.</span><span class="sxs-lookup"><span data-stu-id="63856-121">In the [Microsoft 365 security center](https://security.microsoft.com/), go to **Incidents & alerts** and then to **Alerts**.</span></span>

![Vá para Incidentes e Alertas, em seguida, Alertas](../../media/defender-identity/incidents-alerts.png)

<span data-ttu-id="63856-123">Para ver alertas do Defender para Identidade, na parte  superior direita selecione **Filtrar** e, em Fontes de serviço, selecione **Microsoft Defender para Identidade** e selecione **Aplicar**:</span><span class="sxs-lookup"><span data-stu-id="63856-123">To see alerts from Defender for Identity, on the top-right select **Filter**, and then under **Service sources** select **Microsoft Defender for Identity**, and select **Apply**:</span></span>

![Filtrar eventos do Defender para Identidade](../../media/defender-identity/filter-defender-for-identity.png)

<span data-ttu-id="63856-125">Os alertas são exibidos com informações nas seguintes colunas: Nome do **alerta,** **Marcas,** **Gravidade,** Estado de investigação, **Status,** **Categoria,** **Fonte** de **Detecção,** Ativos afetados, Primeira atividade e Última **atividade**.</span><span class="sxs-lookup"><span data-stu-id="63856-125">The alerts are displayed with information in the following columns: **Alert name**, **Tags**, **Severity**, **Investigation state**, **Status**, **Category**, **Detection source**, **Impacted assets**, **First activity**, and **Last activity**.</span></span>

![Eventos defender para identidade](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a><span data-ttu-id="63856-127">Gerenciar alertas</span><span class="sxs-lookup"><span data-stu-id="63856-127">Manage alerts</span></span>

<span data-ttu-id="63856-128">Se você clicar **no nome do alerta** para um dos alertas, você irá para a página com detalhes sobre o alerta.</span><span class="sxs-lookup"><span data-stu-id="63856-128">If you click the **Alert name** for one of the alerts, you'll go to the page with details about the alert.</span></span> <span data-ttu-id="63856-129">No painel esquerdo, você verá um resumo do **que aconteceu**:</span><span class="sxs-lookup"><span data-stu-id="63856-129">In the left pane, you'll see a summary of **What happened**:</span></span>

![O que aconteceu em alerta](../../media/defender-identity/what-happened.png)

<span data-ttu-id="63856-131">Acima da **caixa O que aconteceu** estão botões para **contas,** host de **destino** **e host** de origem do alerta.</span><span class="sxs-lookup"><span data-stu-id="63856-131">Above the **What happened** box are buttons for the **Accounts**, **Destination Host** and **Source Host** of the alert.</span></span> <span data-ttu-id="63856-132">Para outros alertas, você pode ver botões para obter detalhes sobre hosts adicionais, contas, endereços IP, domínios e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="63856-132">For other alerts, you might see buttons for details about additional hosts, accounts, IP addresses, domains, and security groups.</span></span> <span data-ttu-id="63856-133">Selecione qualquer um deles para obter mais detalhes sobre as entidades envolvidas.</span><span class="sxs-lookup"><span data-stu-id="63856-133">Select any of them to get more details about the entities involved.</span></span>

<span data-ttu-id="63856-134">No painel direito, você verá os detalhes **do alerta.**</span><span class="sxs-lookup"><span data-stu-id="63856-134">On the right pane, you'll see the **Alert details**.</span></span> <span data-ttu-id="63856-135">Aqui você pode ver mais detalhes e executar várias tarefas:</span><span class="sxs-lookup"><span data-stu-id="63856-135">Here you can see more details and perform several tasks:</span></span>

- <span data-ttu-id="63856-136">**Classificar esse alerta** - Aqui você pode designar esse alerta como um **alerta True** ou Um **alerta False**</span><span class="sxs-lookup"><span data-stu-id="63856-136">**Classify this alert** - Here you can designate this alert as a **True alert** or **False alert**</span></span>

    ![Classificar alerta](../../media/defender-identity/classify-alert.png)

- <span data-ttu-id="63856-138">**Estado de alerta** - Em **Classificação de** Conjunto, você pode classificar o alerta como **True** ou **False**.</span><span class="sxs-lookup"><span data-stu-id="63856-138">**Alert state** - In **Set Classification**, you can classify the alert as **True** or **False**.</span></span> <span data-ttu-id="63856-139">Em **Atribuído a**, você pode atribuir o alerta a si mesmo ou desaigná-lo.</span><span class="sxs-lookup"><span data-stu-id="63856-139">In **Assigned to**, you can assign the alert to yourself or unassign it.</span></span>

    ![Estado de alerta](../../media/defender-identity/alert-state.png)

- <span data-ttu-id="63856-141">Detalhes do alerta **-** Em Detalhes de **alerta,** você pode encontrar mais informações sobre o alerta específico, seguir um link para a documentação sobre o tipo de alerta, ver com qual incidente o alerta está associado, revisar quaisquer investigações automatizadas vinculadas a esse tipo de alerta e ver os dispositivos e usuários afetados.</span><span class="sxs-lookup"><span data-stu-id="63856-141">**Alert details** - Under **Alert details**, you can find more information about the specific alert, follow a link to documentation about the type of alert, see which incident the alert is associated with, review any automated investigations linked to this alert type, and see the impacted devices and users.</span></span>

    ![Detalhes do alerta](../../media/defender-identity/alert-details.png)

- <span data-ttu-id="63856-143">**Comentários & histórico** - Aqui você pode adicionar seus comentários ao alerta e ver o histórico de todas as ações associadas ao alerta.</span><span class="sxs-lookup"><span data-stu-id="63856-143">**Comments & history** - Here you can add your comments to the alert, and see the history of all actions associated with the alert.</span></span>

    ![Comentários e histórico](../../media/defender-identity/comments-history.png)

- <span data-ttu-id="63856-145">**Gerenciar alerta** - Se você selecionar **Gerenciar alerta,** você irá para um painel que permitirá que você edite o:</span><span class="sxs-lookup"><span data-stu-id="63856-145">**Manage alert** - If you select **Manage alert**, you'll go to a pane that will allow you to edit the:</span></span>
  - <span data-ttu-id="63856-146">**Status** - Você pode escolher **Novo**, **Resolvido** ou **Em andamento**.</span><span class="sxs-lookup"><span data-stu-id="63856-146">**Status** - You can choose **New**, **Resolved** or **In progress**.</span></span>
  - <span data-ttu-id="63856-147">**Classificação** - Você pode escolher **Alerta true** ou **alerta False.**</span><span class="sxs-lookup"><span data-stu-id="63856-147">**Classification** - You can choose **True alert** or **False alert**.</span></span>
  - <span data-ttu-id="63856-148">**Comentário** - Você pode adicionar um comentário sobre o alerta.</span><span class="sxs-lookup"><span data-stu-id="63856-148">**Comment** - You can add a comment about the alert.</span></span>

    <span data-ttu-id="63856-149">Se você selecionar os três pontos ao lado de **Gerenciar** alerta, poderá consultar um especialista em **ameaças,** exportar o alerta para um arquivo Excel ou Vincular a **outro incidente.** </span><span class="sxs-lookup"><span data-stu-id="63856-149">If you select the three dots next to **Manage alert**, you can **Consult a threat expert**, **Export** the alert to an Excel file, or **Link to another incident**.</span></span>

    ![Gerenciar alerta](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    ><span data-ttu-id="63856-151">No arquivo Excel, agora você tem dois links disponíveis: Exibir no **Microsoft Defender para** Identidade e Exibir no Microsoft 365 **Defender**.</span><span class="sxs-lookup"><span data-stu-id="63856-151">In the Excel file, you now have two links available: **View in Microsoft Defender for Identity** and **View in Microsoft 365 Defender**.</span></span> <span data-ttu-id="63856-152">Cada link o levará ao portal relevante e fornecerá informações sobre o alerta.</span><span class="sxs-lookup"><span data-stu-id="63856-152">Each link will bring you to the relevant portal, and provide information about the alert there.</span></span>

## <a name="see-also"></a><span data-ttu-id="63856-153">Confira também</span><span class="sxs-lookup"><span data-stu-id="63856-153">See also</span></span>

- [<span data-ttu-id="63856-154">Investigar alertas no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="63856-154">Investigate alerts in Microsoft 365 Defender</span></span>](../defender/investigate-alerts.md)
