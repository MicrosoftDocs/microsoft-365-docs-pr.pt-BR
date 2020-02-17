---
title: Usuários de gerenciamento de risco do Insider (versão prévia)
description: Saiba mais sobre usuários de gerenciamento de risco do insider no Microsoft 365
keywords: Microsoft 365, gerenciamento de risco do Insider, gerenciamento de riscos, conformidade
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: a9ff7e38a99a5fe5bd8da5301bec5e19bc015cf3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072779"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="e6323-104">Usuários de gerenciamento de risco do Insider (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="e6323-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="e6323-105">Os usuários de gerenciamento de risco do insider são funcionários em sua organização que estão incluídos em uma ou mais políticas de gerenciamento de risco do insider.</span><span class="sxs-lookup"><span data-stu-id="e6323-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="e6323-106">Use o **painel usuários** para examinar rapidamente as informações de risco sobre os funcionários e para adicionar um funcionário a uma política de gerenciamento de risco do insider existente.</span><span class="sxs-lookup"><span data-stu-id="e6323-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="e6323-107">Cada usuário incluído em uma política de gerenciamento de risco do insider possui as seguintes informações exibidas no **painel usuários**:</span><span class="sxs-lookup"><span data-stu-id="e6323-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="e6323-108">**Usuários**: o nome de usuário para um usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="e6323-109">**Nível de risco**:</span><span class="sxs-lookup"><span data-stu-id="e6323-109">**Risk level**:</span></span> 
- <span data-ttu-id="e6323-110">**Alertas ativos**: o número de alertas ativos para todas as políticas.</span><span class="sxs-lookup"><span data-stu-id="e6323-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="e6323-111">**Violações confirmadas**: o número de ocorrências resolvidas como *violação de política confirmada* para o usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="e6323-112">**Caso**: o caso ativo atual do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-112">**Case**: The current active case for the user.</span></span>

![Painel usuários de gerenciamento de risco do insider](../media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="e6323-114">Exibir detalhes do usuário</span><span class="sxs-lookup"><span data-stu-id="e6323-114">View user details</span></span>

<span data-ttu-id="e6323-115">Para exibir mais detalhes sobre a atividade de risco de um usuário, abra o painel de detalhes do usuário clicando duas vezes em um usuário no **painel usuários**.</span><span class="sxs-lookup"><span data-stu-id="e6323-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="e6323-116">No painel de detalhes, você pode exibir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="e6323-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="e6323-117">Guia **perfil de usuário**</span><span class="sxs-lookup"><span data-stu-id="e6323-117">**User profile** tab</span></span>
    - <span data-ttu-id="e6323-118">**Nome e título**: o nome e o título da posição do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="e6323-119">**Email do usuário**: o endereço de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="e6323-120">**Alias**: o alias de rede do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="e6323-121">**Organização ou departamento**: a organização ou departamento do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="e6323-122">Guia **atividade do usuário**</span><span class="sxs-lookup"><span data-stu-id="e6323-122">**User activity** tab</span></span>
    - <span data-ttu-id="e6323-123">**Histórico da atividade recente do usuário**: lista os eventos de acionamento de política e os indicadores de risco para atividades do usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="e6323-124">Um evento de acionamento pode ser a aceitação de uma data de demissão ou da última data de trabalho agendada para o funcionário.</span><span class="sxs-lookup"><span data-stu-id="e6323-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="e6323-125">Os indicadores de risco são atividades determinadas para ter um elemento de risco e que são correspondidas às políticas nas quais o usuário está incluído.</span><span class="sxs-lookup"><span data-stu-id="e6323-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="e6323-126">Eventos e atividades de risco são listados com o item mais recente listado primeiro.</span><span class="sxs-lookup"><span data-stu-id="e6323-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="e6323-127">Adicionar um usuário a uma política</span><span class="sxs-lookup"><span data-stu-id="e6323-127">Add a user to a policy</span></span>

<span data-ttu-id="e6323-128">Para adicionar um usuário a uma política de gerenciamento de risco do Insider, você usará o assistente de nova política ou a guia **usuários** na solução de **Gerenciamento de risco do insider** no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6323-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="e6323-129">Conclua as seguintes etapas para adicionar um usuário a uma política de risco Insider existente:</span><span class="sxs-lookup"><span data-stu-id="e6323-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="e6323-130">No [centro de conformidade da Microsoft 365](https://compliance.microsoft.com), vá para gerenciamento de **risco do insider** e selecione a guia **usuários** .</span><span class="sxs-lookup"><span data-stu-id="e6323-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="e6323-131">Selecione **Adicionar um usuário a uma política** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="e6323-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="e6323-132">Na caixa de diálogo **Adicionar um novo usuário** , comece a digitar um nome de usuário no campo **usuário** .</span><span class="sxs-lookup"><span data-stu-id="e6323-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="e6323-133">Selecione o usuário que você deseja adicionar a uma política.</span><span class="sxs-lookup"><span data-stu-id="e6323-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="e6323-134">Selecione a seta suspensa do campo **política** para exibir as políticas de gerenciamento de risco do insider configuradas.</span><span class="sxs-lookup"><span data-stu-id="e6323-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="e6323-135">Selecione a política à qual adicionar o usuário.</span><span class="sxs-lookup"><span data-stu-id="e6323-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="e6323-136">Use o controle deslizante da **janela de monitoramento** para definir os...... O intervalo para a janela de monitoramento é de 5 a 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e6323-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="e6323-137">Selecione **Adicionar** e depois em **confirmar** para adicionar o usuário à política.</span><span class="sxs-lookup"><span data-stu-id="e6323-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
