---
title: Criar e exibir exceções para recomendações de segurança - Gerenciamento de Ameaças e Vulnerabilidades
description: Crie e monitore exceções para recomendações de segurança Gerenciamento de Ameaças e Vulnerabilidades.
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
ms.openlocfilehash: 1af8e5ec9d3aef560c739de5212e8118cf89cd7a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933740"
---
# <a name="create-and-view-exceptions-for-security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="71fb7-104">Criar e exibir exceções para recomendações de segurança - Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="71fb7-104">Create and view exceptions for security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="71fb7-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="71fb7-105">**Applies to:**</span></span>

- [<span data-ttu-id="71fb7-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="71fb7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="71fb7-107">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="71fb7-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="71fb7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71fb7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="71fb7-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="71fb7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="71fb7-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="71fb7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="71fb7-111">Como alternativa a uma solicitação de correção quando uma recomendação não é relevante no momento, você pode criar exceções para recomendações.</span><span class="sxs-lookup"><span data-stu-id="71fb7-111">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> <span data-ttu-id="71fb7-112">Se sua organização tiver grupos de dispositivos, você poderá escopo da exceção para grupos de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="71fb7-112">If your organization has device groups, you will be able to scope the exception to specific device groups.</span></span> <span data-ttu-id="71fb7-113">As exceções podem ser criadas para grupos de dispositivos selecionados ou para todos os grupos de dispositivos passados e presentes.</span><span class="sxs-lookup"><span data-stu-id="71fb7-113">Exceptions can either be created for selected device groups, or for all device groups past and present.</span></span>  

<span data-ttu-id="71fb7-114">Quando uma exceção é criada para uma recomendação, a recomendação não estará ativa até o final da duração da exceção.</span><span class="sxs-lookup"><span data-stu-id="71fb7-114">When an exception is created for a recommendation, the recommendation will not be active until the end of the exception duration.</span></span> <span data-ttu-id="71fb7-115">O estado de recomendação mudará para **Exceção Total** ou **Parcial** (por grupo de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="71fb7-115">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

## <a name="permissions"></a><span data-ttu-id="71fb7-116">Permissões</span><span class="sxs-lookup"><span data-stu-id="71fb7-116">Permissions</span></span>

<span data-ttu-id="71fb7-117">Somente usuários com permissões de "tratamento de exceções" podem gerenciar exceções (incluindo criação ou cancelamento).</span><span class="sxs-lookup"><span data-stu-id="71fb7-117">Only users with “exceptions handling” permissions can manage exceptions (including creating or canceling).</span></span> <span data-ttu-id="71fb7-118">[Saiba mais sobre funções RBAC](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="71fb7-118">[Learn more about RBAC roles](user-roles.md).</span></span>

![Permissão de tratamento de exceção.](images/tvm-exception-permissions.png)

## <a name="create-an-exception"></a><span data-ttu-id="71fb7-120">Criar uma exceção</span><span class="sxs-lookup"><span data-stu-id="71fb7-120">Create an exception</span></span>

<span data-ttu-id="71fb7-121">Selecione uma recomendação de segurança para a que você gostaria de criar uma exceção e selecione **Opções de exceção** e preencha o formulário.</span><span class="sxs-lookup"><span data-stu-id="71fb7-121">Select a security recommendation you would like create an exception for, and then select **Exception options** and fill out the form.</span></span>  

![Mostrando onde o botão para "opções de exceção" está localizado em um flyout de recomendação de segurança.](images/tvm-exception-options.png)

### <a name="exception-by-device-group"></a><span data-ttu-id="71fb7-123">Exceção por grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="71fb7-123">Exception by device group</span></span>

<span data-ttu-id="71fb7-124">Aplique a exceção a todos os grupos de dispositivos atuais ou escolha grupos de dispositivos específicos.</span><span class="sxs-lookup"><span data-stu-id="71fb7-124">Apply the exception to all current device groups or choose specific device groups.</span></span> <span data-ttu-id="71fb7-125">Os grupos de dispositivos futuros não serão incluídos na exceção.</span><span class="sxs-lookup"><span data-stu-id="71fb7-125">Future device groups won't be included in the exception.</span></span> <span data-ttu-id="71fb7-126">Os grupos de dispositivos que já têm uma exceção não serão exibidos na lista.</span><span class="sxs-lookup"><span data-stu-id="71fb7-126">Device groups that already have an exception will not be displayed in the list.</span></span> <span data-ttu-id="71fb7-127">Se você selecionar apenas determinados grupos de dispositivos, o estado de recomendação mudará de "ativo" para "exceção parcial".</span><span class="sxs-lookup"><span data-stu-id="71fb7-127">If you only select certain device groups, the recommendation state will change from “active” to “partial exception.”</span></span> <span data-ttu-id="71fb7-128">O estado será alternado para "exceção completa" se você selecionar todos os grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="71fb7-128">The state will change to “full exception” if you select all the device groups.</span></span>

![Mostrando o menu suspenso do grupo de dispositivos.](images/tvm-exception-device-group-500.png)

#### <a name="filtered-views"></a><span data-ttu-id="71fb7-130">Exibições filtradas</span><span class="sxs-lookup"><span data-stu-id="71fb7-130">Filtered views</span></span>

<span data-ttu-id="71fb7-131">Se você tiver filtrado por grupo de dispositivos em qualquer uma das páginas Gerenciamento de Ameaças e Vulnerabilidades, somente os grupos de dispositivos filtrados aparecerão como opções.</span><span class="sxs-lookup"><span data-stu-id="71fb7-131">If you have filtered by device group on any of the threat and vulnerability management pages, only your filtered device groups will appear as options.</span></span>

<span data-ttu-id="71fb7-132">Este é o botão para filtrar por grupo de dispositivos em qualquer uma das páginas Gerenciamento de Ameaças e Vulnerabilidades:</span><span class="sxs-lookup"><span data-stu-id="71fb7-132">This is the button to filter by device group on any of the threat and vulnerability management pages:</span></span> 

![Mostrando filtro de grupos de dispositivos selecionados.](images/tvm-selected-device-groups.png)

<span data-ttu-id="71fb7-134">Exibição de exceção com grupos de dispositivos filtrados:</span><span class="sxs-lookup"><span data-stu-id="71fb7-134">Exception view with filtered device groups:</span></span>

![Mostrando o menu suspenso do grupo de dispositivos filtrado.](images/tvm-exception-device-filter500.png)

#### <a name="large-number-of-device-groups"></a><span data-ttu-id="71fb7-136">Grande número de grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="71fb7-136">Large number of device groups</span></span>

<span data-ttu-id="71fb7-137">Se sua organização tiver mais de 20 grupos de dispositivos, selecione **Editar** ao lado da opção grupo de dispositivos filtrado.</span><span class="sxs-lookup"><span data-stu-id="71fb7-137">If your organization has more than 20 device groups, select **Edit** next to the filtered device group option.</span></span>

![Mostrando como editar um grande número de grupos.](images/tvm-exception-edit-groups.png)

<span data-ttu-id="71fb7-139">Um flyout aparecerá onde você pode pesquisar e escolher os grupos de dispositivos que deseja incluir.</span><span class="sxs-lookup"><span data-stu-id="71fb7-139">A flyout will appear where you can search and choose device groups you want included.</span></span> <span data-ttu-id="71fb7-140">Selecione o ícone de marca de seleção abaixo Pesquisar para verificar/desmarcar tudo.</span><span class="sxs-lookup"><span data-stu-id="71fb7-140">Select the check mark icon below Search to check/uncheck all.</span></span>

![Mostrando o sobrevoo de grupo de dispositivos grandes.](images/tvm-exception-device-group-flyout-400.png)

### <a name="global-exceptions"></a><span data-ttu-id="71fb7-142">Exceções globais</span><span class="sxs-lookup"><span data-stu-id="71fb7-142">Global exceptions</span></span>

<span data-ttu-id="71fb7-143">Se você tiver permissões globais de administrador, poderá criar e cancelar uma exceção global.</span><span class="sxs-lookup"><span data-stu-id="71fb7-143">If you have global administrator permissions, you will be able to create and cancel a global exception.</span></span> <span data-ttu-id="71fb7-144">Ele afeta todos **os** grupos de dispositivos atuais e futuros em sua organização, e somente um usuário com permissão semelhante poderá alterá-lo.</span><span class="sxs-lookup"><span data-stu-id="71fb7-144">It affects **all** current and future device groups in your organization, and only a user with similar permission would be able to change it.</span></span> <span data-ttu-id="71fb7-145">O estado de recomendação mudará de "ativo" para "exceção completa".</span><span class="sxs-lookup"><span data-stu-id="71fb7-145">The recommendation state will change from “active” to “full exception.”</span></span>

![Mostrando a opção de exceção global.](images/tvm-exception-global.png)

<span data-ttu-id="71fb7-147">Algumas coisas a se ter em mente:</span><span class="sxs-lookup"><span data-stu-id="71fb7-147">Some things to keep in mind:</span></span>

- <span data-ttu-id="71fb7-148">Se uma recomendação estiver sob exceção global, as exceções recém-criadas para grupos de dispositivos serão suspensas até que a exceção global tenha expirado ou sido cancelada.</span><span class="sxs-lookup"><span data-stu-id="71fb7-148">If a recommendation is under global exception, then newly created exceptions for device groups will be suspended until the global exception has expired or been cancelled.</span></span> <span data-ttu-id="71fb7-149">Após esse ponto, as novas exceções do grupo de dispositivos entrarão em vigor até expirarem.</span><span class="sxs-lookup"><span data-stu-id="71fb7-149">After that point, the new device group exceptions will go into effect until they expire.</span></span>
- <span data-ttu-id="71fb7-150">Se uma recomendação já tiver exceções para grupos de dispositivos específicos e uma exceção global for criada, a exceção do grupo de dispositivos será suspensa até expirar ou a exceção global será cancelada antes de expirar.</span><span class="sxs-lookup"><span data-stu-id="71fb7-150">If a recommendation already has exceptions for specific device groups and a global exception is created, then the device group exception will be suspended until it expires or the global exception is cancelled before it expires.</span></span>

### <a name="justification"></a><span data-ttu-id="71fb7-151">Justification</span><span class="sxs-lookup"><span data-stu-id="71fb7-151">Justification</span></span>

<span data-ttu-id="71fb7-152">Selecione sua justificativa para a exceção que você precisa arquivar em vez de remediar a recomendação de segurança em questão.</span><span class="sxs-lookup"><span data-stu-id="71fb7-152">Select your justification for the exception you need to file instead of remediating the security recommendation in question.</span></span> <span data-ttu-id="71fb7-153">Preencha o contexto de justificativa e de definir a duração da exceção.</span><span class="sxs-lookup"><span data-stu-id="71fb7-153">Fill out the justification context, then set the exception duration.</span></span>

<span data-ttu-id="71fb7-154">A lista a seguir detalha as justificativas por trás das opções de exceção:</span><span class="sxs-lookup"><span data-stu-id="71fb7-154">The following list details the justifications behind the exception options:</span></span>

- <span data-ttu-id="71fb7-155">**Controle de terceiros** - um produto ou software de terceiros já aborda essa recomendação - Escolher esse tipo de justificativa diminuirá sua pontuação de exposição e aumentará sua pontuação segura porque seu risco é reduzido</span><span class="sxs-lookup"><span data-stu-id="71fb7-155">**Third party control** - A third party product or software already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="71fb7-156">**Mitigação alternativa** - uma ferramenta interna já aborda essa recomendação - Escolher esse tipo de justificativa diminuirá sua pontuação de exposição e aumentará sua pontuação segura porque seu risco é reduzido</span><span class="sxs-lookup"><span data-stu-id="71fb7-156">**Alternate mitigation** - An internal tool already addresses this recommendation       - Choosing this justification type will lower your exposure score and increase your secure score because your risk is reduced</span></span>
- <span data-ttu-id="71fb7-157">**Risco aceito** - representa baixo risco e/ou implementar a recomendação é muito caro</span><span class="sxs-lookup"><span data-stu-id="71fb7-157">**Risk accepted** - Poses low risk and/or implementing the recommendation is too expensive</span></span>
- <span data-ttu-id="71fb7-158">**Correção planejada (graça)** - Já planejada, mas aguardando execução ou autorização</span><span class="sxs-lookup"><span data-stu-id="71fb7-158">**Planned remediation (grace)** - Already planned but is awaiting execution or authorization</span></span>

## <a name="view-all-exceptions"></a><span data-ttu-id="71fb7-159">Exibir todas as exceções</span><span class="sxs-lookup"><span data-stu-id="71fb7-159">View all exceptions</span></span>

<span data-ttu-id="71fb7-160">Navegue até a guia **Exceções** na **página Correção.**</span><span class="sxs-lookup"><span data-stu-id="71fb7-160">Navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="71fb7-161">Você pode filtrar por justificativa, tipo e status.</span><span class="sxs-lookup"><span data-stu-id="71fb7-161">You can filter by justification, type, and status.</span></span>

 <span data-ttu-id="71fb7-162">Selecione uma exceção para abrir um sobremenu com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="71fb7-162">Select an exception to open a flyout with more details.</span></span> <span data-ttu-id="71fb7-163">Exceções por grupo de dispositivos terão uma lista de cada grupo de dispositivos que a exceção abrange, que você pode exportar.</span><span class="sxs-lookup"><span data-stu-id="71fb7-163">Exceptions per devices group will have a list of every device group the exception covers, which you can export.</span></span> <span data-ttu-id="71fb7-164">Você também pode exibir a recomendação relacionada ou cancelar a exceção.</span><span class="sxs-lookup"><span data-stu-id="71fb7-164">You can also view the related recommendation or cancel the exception.</span></span>

![Mostrando a guia "Exceções" na página Correção.](images/tvm-exception-view.png)

## <a name="how-to-cancel-an-exception"></a><span data-ttu-id="71fb7-166">Como cancelar uma exceção</span><span class="sxs-lookup"><span data-stu-id="71fb7-166">How to cancel an exception</span></span>

<span data-ttu-id="71fb7-167">Para cancelar uma exceção, navegue até a guia **Exceções** na **página Correção.**</span><span class="sxs-lookup"><span data-stu-id="71fb7-167">To cancel an exception, navigate to the **Exceptions** tab in the **Remediation** page.</span></span> <span data-ttu-id="71fb7-168">Selecione a exceção.</span><span class="sxs-lookup"><span data-stu-id="71fb7-168">Select the exception.</span></span>

<span data-ttu-id="71fb7-169">Para cancelar a exceção para todos os grupos de dispositivos ou para uma exceção global, selecione o botão **Cancelar exceção para todos os grupos de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="71fb7-169">To cancel the exception for all device groups or for a global exception, select the **Cancel exception for all device groups** button.</span></span> <span data-ttu-id="71fb7-170">Você só poderá cancelar exceções para grupos de dispositivos para os que você tem permissões.</span><span class="sxs-lookup"><span data-stu-id="71fb7-170">You will only be able to cancel exceptions for device groups you have permissions for.</span></span>

![O botão cancelar.](images/tvm-exception-cancel.png)

### <a name="cancel-the-exception-for-a-specific-device-group"></a><span data-ttu-id="71fb7-172">Cancelar a exceção para um grupo de dispositivos específico</span><span class="sxs-lookup"><span data-stu-id="71fb7-172">Cancel the exception for a specific device group</span></span>

<span data-ttu-id="71fb7-173">Selecione o grupo de dispositivos específico para cancelar a exceção para ele.</span><span class="sxs-lookup"><span data-stu-id="71fb7-173">Select the specific device group to cancel the exception for it.</span></span> <span data-ttu-id="71fb7-174">Um flyout será exibido para o grupo de dispositivos e você pode selecionar **Cancelar exceção**.</span><span class="sxs-lookup"><span data-stu-id="71fb7-174">A flyout will appear for the device group, and you can select **Cancel exception**.</span></span>

![Mostrando como selecionar um grupo de dispositivos específico.](images/tvm-exception-device-group-hover.png)

## <a name="view-impact-after-exceptions-are-applied"></a><span data-ttu-id="71fb7-176">Exibir impacto após a aplicação de exceções</span><span class="sxs-lookup"><span data-stu-id="71fb7-176">View impact after exceptions are applied</span></span>

<span data-ttu-id="71fb7-177">Na página Segurança Recomendações, selecione Personalizar **colunas** e marque as caixas para dispositivos Expostos **(após exceções)** e **Impacto (após exceções)**.</span><span class="sxs-lookup"><span data-stu-id="71fb7-177">In the Security Recommendations page, select **Customize columns** and check the boxes for **Exposed devices (after exceptions)** and **Impact (after exceptions)**.</span></span>

![Mostrando opções de personalizar colunas.](images/tvm-after-exceptions.png)

<span data-ttu-id="71fb7-179">A coluna dispositivos expostos (após exceções) mostra os dispositivos restantes que ainda estão expostos a vulnerabilidades após a aplicação de exceções.</span><span class="sxs-lookup"><span data-stu-id="71fb7-179">The exposed devices (after exceptions) column shows the remaining devices that are still exposed to vulnerabilities after exceptions are applied.</span></span> <span data-ttu-id="71fb7-180">As justificativas de exceção que afetam a exposição incluem "controle de terceiros" e "mitigação alternativa".</span><span class="sxs-lookup"><span data-stu-id="71fb7-180">Exception justifications that affect the exposure include ‘third party control’ and ‘alternate mitigation’.</span></span> <span data-ttu-id="71fb7-181">Outras justificativas não reduzem a exposição de um dispositivo e ainda são consideradas expostas.</span><span class="sxs-lookup"><span data-stu-id="71fb7-181">Other justifications do not reduce the exposure of a device, and they are still considered exposed.</span></span>

<span data-ttu-id="71fb7-182">O impacto (após exceções) mostra o impacto restante na pontuação de exposição ou na pontuação segura depois que as exceções são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="71fb7-182">The impact (after exceptions) shows remaining impact to exposure score or secure score after exceptions are applied.</span></span> <span data-ttu-id="71fb7-183">As justificativas de exceção que afetam as pontuações incluem "controle de terceiros" e "mitigação alternativa".</span><span class="sxs-lookup"><span data-stu-id="71fb7-183">Exception justifications that affect the scores include ‘third party control’ and ‘alternate mitigation.’</span></span> <span data-ttu-id="71fb7-184">Outras justificativas não reduzem a exposição de um dispositivo e, portanto, a pontuação de exposição e a pontuação segura não mudam.</span><span class="sxs-lookup"><span data-stu-id="71fb7-184">Other justifications do not reduce the exposure of a device, and so the exposure score and secure score do not change.</span></span>

![Mostrando as colunas na tabela.](images/tvm-after-exceptions-table.png)

## <a name="related-topics"></a><span data-ttu-id="71fb7-186">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="71fb7-186">Related topics</span></span>

- [<span data-ttu-id="71fb7-187">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="71fb7-187">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="71fb7-188">Correção de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="71fb7-188">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="71fb7-189">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="71fb7-189">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="71fb7-190">Pontuação de exposição</span><span class="sxs-lookup"><span data-stu-id="71fb7-190">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="71fb7-191">Microsoft Secure Score para dispositivos</span><span class="sxs-lookup"><span data-stu-id="71fb7-191">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
