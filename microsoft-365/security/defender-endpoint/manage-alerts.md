---
title: Gerenciar alertas do Microsoft Defender para Pontos de Extremidade
description: Altere o status dos alertas, crie regras de supressão para ocultar alertas, enviar comentários e revisar o histórico de alterações para alertas individuais com o menu Gerenciar Alerta.
keywords: gerenciar alertas, gerenciar, alertas, status, novo, em andamento, resolvido, resolver alertas, suprimir, suprimir, regras, contexto, histórico, comentários, alterações
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f03c2209b369e6fb9e001452c53073daeb5fe1c6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186996"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a><span data-ttu-id="53c24-104">Gerenciar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="53c24-104">Manage Microsoft Defender for Endpoint alerts</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="53c24-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="53c24-105">**Applies to:**</span></span>
- [<span data-ttu-id="53c24-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="53c24-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="53c24-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="53c24-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="53c24-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="53c24-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="53c24-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="53c24-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="53c24-110">O Defender for Endpoint notifica você sobre possíveis eventos mal-intencionados, atributos e informações contextuais por meio de alertas.</span><span class="sxs-lookup"><span data-stu-id="53c24-110">Defender for Endpoint notifies you of possible malicious events, attributes, and contextual information through alerts.</span></span> <span data-ttu-id="53c24-111">Um resumo de novos alertas é exibido no painel Operações de segurança **e** você pode acessar todos os alertas na fila **de alertas.**</span><span class="sxs-lookup"><span data-stu-id="53c24-111">A summary of new alerts is displayed in the **Security operations dashboard**, and you can access all alerts in the **Alerts queue**.</span></span>

<span data-ttu-id="53c24-112">Você pode gerenciar alertas selecionando um alerta na fila **alertas** ou a guia **Alertas** da página Dispositivo para um dispositivo individual.</span><span class="sxs-lookup"><span data-stu-id="53c24-112">You can manage alerts by selecting an alert in the **Alerts queue**, or the **Alerts** tab of the Device page for an individual device.</span></span>

<span data-ttu-id="53c24-113">Selecionar um alerta em qualquer um desses locais traz o painel gerenciamento **de alertas**.</span><span class="sxs-lookup"><span data-stu-id="53c24-113">Selecting an alert in either of those places brings up the **Alert management pane**.</span></span>

![Imagem do painel de gerenciamento de alertas e fila de alertas](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a><span data-ttu-id="53c24-115">Link para outro incidente</span><span class="sxs-lookup"><span data-stu-id="53c24-115">Link to another incident</span></span>
<span data-ttu-id="53c24-116">Você pode criar um novo incidente a partir do alerta ou do link para um incidente existente.</span><span class="sxs-lookup"><span data-stu-id="53c24-116">You can create a new incident from the alert or link to an existing incident.</span></span> 

## <a name="assign-alerts"></a><span data-ttu-id="53c24-117">Atribuir alertas</span><span class="sxs-lookup"><span data-stu-id="53c24-117">Assign alerts</span></span>
<span data-ttu-id="53c24-118">Se um alerta ainda não estiver atribuído, você poderá selecionar **Atribuir a mim** para atribuir o alerta a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="53c24-118">If an alert is not yet assigned, you can select **Assign to me** to assign the alert to yourself.</span></span>


## <a name="suppress-alerts"></a><span data-ttu-id="53c24-119">Suprimir alertas</span><span class="sxs-lookup"><span data-stu-id="53c24-119">Suppress alerts</span></span>
<span data-ttu-id="53c24-120">Pode haver cenários em que você precisa suprimir alertas de aparecer no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="53c24-120">There might be scenarios where you need to suppress alerts from appearing in Microsoft Defender Security Center.</span></span> <span data-ttu-id="53c24-121">O Defender for Endpoint permite que você crie regras de supressão para alertas específicos que são conhecidos como ferramentas ou processos conhecidos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="53c24-121">Defender for Endpoint lets you create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span>

<span data-ttu-id="53c24-122">As regras de supressão podem ser criadas a partir de um alerta existente.</span><span class="sxs-lookup"><span data-stu-id="53c24-122">Suppression rules can be created from an existing alert.</span></span> <span data-ttu-id="53c24-123">Eles podem ser desabilitados e reenvelizáveis, se necessário.</span><span class="sxs-lookup"><span data-stu-id="53c24-123">They can be disabled and reenabled if needed.</span></span>

<span data-ttu-id="53c24-124">Quando uma regra de supressão é criada, ela terá efeito a partir do ponto em que a regra for criada.</span><span class="sxs-lookup"><span data-stu-id="53c24-124">When a suppression rule is created, it will take effect from the point when the rule is created.</span></span> <span data-ttu-id="53c24-125">A regra não afetará alertas existentes já na fila, antes da criação da regra.</span><span class="sxs-lookup"><span data-stu-id="53c24-125">The rule will not affect existing alerts already in the queue, prior to the rule creation.</span></span> <span data-ttu-id="53c24-126">A regra só será aplicada em alertas que atendam às condições definidas após a criação da regra.</span><span class="sxs-lookup"><span data-stu-id="53c24-126">The rule will only be applied on alerts that satisfy the conditions set after the rule is created.</span></span>

<span data-ttu-id="53c24-127">Há dois contextos para uma regra de supressão que você pode escolher:</span><span class="sxs-lookup"><span data-stu-id="53c24-127">There are two contexts for a suppression rule that you can choose from:</span></span>

- <span data-ttu-id="53c24-128">**Suprimir alerta neste dispositivo**</span><span class="sxs-lookup"><span data-stu-id="53c24-128">**Suppress alert on this device**</span></span>
- <span data-ttu-id="53c24-129">**Suprimir alerta na minha organização**</span><span class="sxs-lookup"><span data-stu-id="53c24-129">**Suppress alert in my organization**</span></span>

<span data-ttu-id="53c24-130">O contexto da regra permite adaptar o que é feito no portal e garantir que apenas alertas reais de segurança sejam a tona no portal.</span><span class="sxs-lookup"><span data-stu-id="53c24-130">The context of the rule lets you tailor what gets surfaced into the portal and ensure that only real security alerts are surfaced into the portal.</span></span>

<span data-ttu-id="53c24-131">Você pode usar os exemplos na tabela a seguir para ajudá-lo a escolher o contexto de uma regra de supressão:</span><span class="sxs-lookup"><span data-stu-id="53c24-131">You can use the examples in the following table to help you choose the context for a suppression rule:</span></span>

| <span data-ttu-id="53c24-132">**Context**</span><span class="sxs-lookup"><span data-stu-id="53c24-132">**Context**</span></span>                           | <span data-ttu-id="53c24-133">**Definição**</span><span class="sxs-lookup"><span data-stu-id="53c24-133">**Definition**</span></span>                                                                                                                                              | <span data-ttu-id="53c24-134">**Exemplos de cenários**</span><span class="sxs-lookup"><span data-stu-id="53c24-134">**Example scenarios**</span></span>                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="53c24-135">**Suprimir alerta neste dispositivo**</span><span class="sxs-lookup"><span data-stu-id="53c24-135">**Suppress alert on this device**</span></span>    | <span data-ttu-id="53c24-136">Os alertas com o mesmo título de alerta e nesse dispositivo específico serão suprimidos.</span><span class="sxs-lookup"><span data-stu-id="53c24-136">Alerts with the same alert title and on that specific device only will be suppressed.</span></span> <br /><br /><span data-ttu-id="53c24-137">Todos os outros alertas nesse dispositivo não serão suprimidos.</span><span class="sxs-lookup"><span data-stu-id="53c24-137">All other alerts on that device will not be suppressed.</span></span> | <ul><li><span data-ttu-id="53c24-138">Um pesquisador de segurança está investigando um script mal-intencionado que foi usado para atacar outros dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="53c24-138">A security researcher is investigating a malicious script that has been used to attack other devices in your organization.</span></span></li><li><span data-ttu-id="53c24-139">Um desenvolvedor cria regularmente scripts do PowerShell para sua equipe.</span><span class="sxs-lookup"><span data-stu-id="53c24-139">A developer regularly creates PowerShell scripts for their team.</span></span></li></ul> |
| <span data-ttu-id="53c24-140">**Suprimir alerta na minha organização**</span><span class="sxs-lookup"><span data-stu-id="53c24-140">**Suppress alert in my organization**</span></span> | <span data-ttu-id="53c24-141">Alertas com o mesmo título de alerta em qualquer dispositivo serão suprimidos.</span><span class="sxs-lookup"><span data-stu-id="53c24-141">Alerts with the same alert title on any device will be suppressed.</span></span>                                                                                         | <ul><li><span data-ttu-id="53c24-142">Uma ferramenta administrativa benigna é usada por todos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="53c24-142">A benign administrative tool is used by everyone in your organization.</span></span></li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a><span data-ttu-id="53c24-143">Suprimir um alerta e criar uma nova regra de supressão:</span><span class="sxs-lookup"><span data-stu-id="53c24-143">Suppress an alert and create a new suppression rule:</span></span>
<span data-ttu-id="53c24-144">Crie regras personalizadas para controlar quando os alertas são suprimidos ou resolvidos.</span><span class="sxs-lookup"><span data-stu-id="53c24-144">Create custom rules to control when alerts are suppressed, or resolved.</span></span> <span data-ttu-id="53c24-145">Você pode controlar o contexto para quando um alerta é suprimido especificando o título do alerta, o indicador de comprometimento e as condições.</span><span class="sxs-lookup"><span data-stu-id="53c24-145">You can control the context for when an alert is suppressed by specifying the alert title, Indicator of compromise, and the conditions.</span></span> <span data-ttu-id="53c24-146">Depois de especificar o contexto, você poderá configurar a ação e o escopo no alerta.</span><span class="sxs-lookup"><span data-stu-id="53c24-146">After specifying the context, you’ll be able to configure the action and scope on the alert.</span></span> 

1. <span data-ttu-id="53c24-147">Selecione o alerta que você gostaria de suprimir.</span><span class="sxs-lookup"><span data-stu-id="53c24-147">Select the alert you'd like to suppress.</span></span> <span data-ttu-id="53c24-148">Isso gera o **painel gerenciamento de** alertas.</span><span class="sxs-lookup"><span data-stu-id="53c24-148">This brings up the **Alert management** pane.</span></span>

2.  <span data-ttu-id="53c24-149">Selecione **Criar uma regra de supressão.**</span><span class="sxs-lookup"><span data-stu-id="53c24-149">Select **Create a suppression rule**.</span></span>

    <span data-ttu-id="53c24-150">Você pode criar uma condição de supressão usando esses atributos.</span><span class="sxs-lookup"><span data-stu-id="53c24-150">You can create a suppression condition using these attributes.</span></span> <span data-ttu-id="53c24-151">Um operador AND é aplicado entre cada condição, portanto, a supressão ocorre somente se todas as condições são atendidas.</span><span class="sxs-lookup"><span data-stu-id="53c24-151">An AND operator is applied between each condition, so suppression occurs only if all conditions are met.</span></span>
    
    * <span data-ttu-id="53c24-152">Arquivo SHA1</span><span class="sxs-lookup"><span data-stu-id="53c24-152">File SHA1</span></span>
    * <span data-ttu-id="53c24-153">Nome do arquivo - curinga com suporte</span><span class="sxs-lookup"><span data-stu-id="53c24-153">File name - wildcard supported</span></span>
    * <span data-ttu-id="53c24-154">Caminho da pasta - curinga com suporte</span><span class="sxs-lookup"><span data-stu-id="53c24-154">Folder path - wildcard supported</span></span>
    * <span data-ttu-id="53c24-155">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="53c24-155">IP address</span></span>
    * <span data-ttu-id="53c24-156">URL - curinga com suporte</span><span class="sxs-lookup"><span data-stu-id="53c24-156">URL - wildcard supported</span></span>
    * <span data-ttu-id="53c24-157">Linha de comando - curinga com suporte</span><span class="sxs-lookup"><span data-stu-id="53c24-157">Command line - wildcard supported</span></span>

3. <span data-ttu-id="53c24-158">Selecione o **IOC de acionamento.**</span><span class="sxs-lookup"><span data-stu-id="53c24-158">Select the **Triggering IOC**.</span></span>
    
4. <span data-ttu-id="53c24-159">Especifique a ação e o escopo no alerta.</span><span class="sxs-lookup"><span data-stu-id="53c24-159">Specify the action and scope on the alert.</span></span> <br>
   <span data-ttu-id="53c24-160">Você pode resolver automaticamente um alerta ou escondê-lo do portal.</span><span class="sxs-lookup"><span data-stu-id="53c24-160">You can automatically resolve an alert or hide it from the portal.</span></span> <span data-ttu-id="53c24-161">Os alertas que são resolvidos automaticamente serão exibidos na seção resolvida da fila de alertas, da página de alerta e da linha do tempo do dispositivo e serão exibidos como resolvidos no Defender para APIs do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="53c24-161">Alerts that are automatically resolved will appear in the resolved section of the alerts queue, alert page, and device timeline and will appear as resolved across Defender for Endpoint APIs.</span></span> <br><br> <span data-ttu-id="53c24-162">Os alertas marcados como ocultos serão suprimidos de todo o sistema, tanto nos alertas associados do dispositivo quanto no painel e não serão transmitidos no Defender para APIs do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="53c24-162">Alerts that are marked as hidden will be suppressed from the entire system, both on the device's associated alerts and from the dashboard and will not be streamed across Defender for Endpoint APIs.</span></span>


5. <span data-ttu-id="53c24-163">Insira um nome de regra e um comentário.</span><span class="sxs-lookup"><span data-stu-id="53c24-163">Enter a rule name and a comment.</span></span>

6. <span data-ttu-id="53c24-164">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="53c24-164">Click **Save**.</span></span>

#### <a name="view-the-list-of-suppression-rules"></a><span data-ttu-id="53c24-165">Exibir a lista de regras de supressão</span><span class="sxs-lookup"><span data-stu-id="53c24-165">View the list of suppression rules</span></span>

1. <span data-ttu-id="53c24-166">No painel de navegação, selecione **Configurações**  >  **Supressão de alerta**.</span><span class="sxs-lookup"><span data-stu-id="53c24-166">In the navigation pane, select **Settings** > **Alert suppression**.</span></span>

2. <span data-ttu-id="53c24-167">A lista de regras de supressão mostra todas as regras que os usuários em sua organização criaram.</span><span class="sxs-lookup"><span data-stu-id="53c24-167">The list of suppression rules shows all the rules that users in your organization have created.</span></span>

<span data-ttu-id="53c24-168">Para obter mais informações sobre como gerenciar regras de supressão, consulte [Gerenciar regras de supressão](manage-suppression-rules.md)</span><span class="sxs-lookup"><span data-stu-id="53c24-168">For more information on managing suppression rules, see [Manage suppression rules](manage-suppression-rules.md)</span></span>

## <a name="change-the-status-of-an-alert"></a><span data-ttu-id="53c24-169">Alterar o status de um alerta</span><span class="sxs-lookup"><span data-stu-id="53c24-169">Change the status of an alert</span></span>

<span data-ttu-id="53c24-170">Você pode categorizar alertas (como **Novo**, **Em Andamento** ou **Resolvido)** alterando seu status à medida que a investigação progride.</span><span class="sxs-lookup"><span data-stu-id="53c24-170">You can categorize alerts (as **New**, **In Progress**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="53c24-171">Isso ajuda você a organizar e gerenciar como sua equipe pode responder a alertas.</span><span class="sxs-lookup"><span data-stu-id="53c24-171">This helps you organize and manage how your team can respond to alerts.</span></span>

<span data-ttu-id="53c24-172">Por exemplo, um líder de equipe pode revisar todos os **novos** alertas e decidir atribuí-los à fila **Em** Andamento para análise posterior.</span><span class="sxs-lookup"><span data-stu-id="53c24-172">For example, a team leader can review all **New** alerts, and decide to assign them to the **In Progress** queue for further analysis.</span></span>

<span data-ttu-id="53c24-173">Como alternativa, o líder da equipe  pode atribuir o alerta à fila Resolvido se ele sabe que o alerta é benigno, proveniente de um dispositivo irrelevante (como um pertencente a um administrador de segurança) ou está sendo tratado por meio de um alerta anterior.</span><span class="sxs-lookup"><span data-stu-id="53c24-173">Alternatively, the team leader might assign the alert to the **Resolved** queue if they know the alert is benign, coming from a device that is irrelevant (such as one belonging to a security administrator), or is being dealt with through an earlier alert.</span></span>



## <a name="alert-classification"></a><span data-ttu-id="53c24-174">Classificação de alerta</span><span class="sxs-lookup"><span data-stu-id="53c24-174">Alert classification</span></span>
<span data-ttu-id="53c24-175">Você pode optar por não definir uma classificação ou especificar se um alerta é um alerta verdadeiro ou um alerta falso.</span><span class="sxs-lookup"><span data-stu-id="53c24-175">You can choose not to set a classification, or specify whether an alert is a true alert or a false alert.</span></span> <span data-ttu-id="53c24-176">É importante fornecer a classificação de verdadeiro positivo/falso positivo.</span><span class="sxs-lookup"><span data-stu-id="53c24-176">It's important to provide the classification of true positive/false positive.</span></span> <span data-ttu-id="53c24-177">Essa classificação é usada para monitorar a qualidade do alerta e tornar os alertas mais precisos.</span><span class="sxs-lookup"><span data-stu-id="53c24-177">This classification is used to monitor alert quality, and make alerts more accurate.</span></span> <span data-ttu-id="53c24-178">O campo "determinação" define fidelidade adicional para uma classificação "verdadeiro positivo".</span><span class="sxs-lookup"><span data-stu-id="53c24-178">The "determination" field defines additional fidelity for a "true positive" classification.</span></span> 

## <a name="add-comments-and-view-the-history-of-an-alert"></a><span data-ttu-id="53c24-179">Adicionar comentários e exibir o histórico de um alerta</span><span class="sxs-lookup"><span data-stu-id="53c24-179">Add comments and view the history of an alert</span></span>
<span data-ttu-id="53c24-180">Você pode adicionar comentários e exibir eventos históricos sobre um alerta para ver as alterações anteriores feitas no alerta.</span><span class="sxs-lookup"><span data-stu-id="53c24-180">You can add comments and view historical events about an alert to see previous changes made to the alert.</span></span>

<span data-ttu-id="53c24-181">Sempre que uma alteração ou comentário é feita em um alerta, ela é registrada na seção **Comentários e** histórico.</span><span class="sxs-lookup"><span data-stu-id="53c24-181">Whenever a change or comment is made to an alert, it is recorded in the **Comments and history** section.</span></span>

<span data-ttu-id="53c24-182">Os comentários adicionados aparecem instantaneamente no painel.</span><span class="sxs-lookup"><span data-stu-id="53c24-182">Added comments instantly appear on the pane.</span></span>


## <a name="related-topics"></a><span data-ttu-id="53c24-183">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="53c24-183">Related topics</span></span>
- [<span data-ttu-id="53c24-184">Gerenciar regras de supressão</span><span class="sxs-lookup"><span data-stu-id="53c24-184">Manage suppression rules</span></span>](manage-suppression-rules.md)
- [<span data-ttu-id="53c24-185">Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="53c24-185">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="53c24-186">Investigar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="53c24-186">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="53c24-187">Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="53c24-187">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="53c24-188">Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="53c24-188">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="53c24-189">Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="53c24-189">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="53c24-190">Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="53c24-190">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="53c24-191">Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="53c24-191">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
