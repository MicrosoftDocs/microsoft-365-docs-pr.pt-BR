---
title: Introdução ao gerenciamento de acesso privilegiado
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Use este artigo para saber mais sobre como habilitar e configurar o gerenciamento de acesso privilegiado no Office 365.
ms.openlocfilehash: 7b3ac9dbc065bcbbdf48e805a3975886a894c645
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545991"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="62953-103">Introdução ao gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="62953-103">Get started with privileged access management</span></span>

<span data-ttu-id="62953-104">Este tópico fornece orientações sobre como habilitar e configurar o gerenciamento de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="62953-105">Você pode usar o centro de administração do Microsoft 365 ou o PowerShell de gerenciamento do Exchange para gerenciar e usar o acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="62953-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="62953-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="62953-106">Before you begin</span></span>

<span data-ttu-id="62953-107">Antes de começar a usar o gerenciamento de acesso privilegiado, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e outros Complementos.</span><span class="sxs-lookup"><span data-stu-id="62953-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="62953-108">Para acessar e usar o gerenciamento de acesso privilegiado, sua organização deve ter uma das seguintes assinaturas ou Complementos:</span><span class="sxs-lookup"><span data-stu-id="62953-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="62953-109">Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="62953-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="62953-110">Assinatura do Microsoft 365 E3 (ou Office 365 E3 Subscription + Enterprise Mobility e Security E3 Subscription) + o complemento de conformidade do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="62953-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="62953-111">Qualquer assinatura do Microsoft 365, do Office 365, do Exchange, do SharePoint ou do OneDrive for Business + o complemento de gerenciamento de risco do Microsoft 365 E5 Insider</span><span class="sxs-lookup"><span data-stu-id="62953-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="62953-112">Assinatura do Microsoft 365 a5 (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="62953-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="62953-113">Assinatura do Microsoft 365 a3 (ou a assinatura do Office 365 a3 + Enterprise Mobility and Security a3) + o complemento de conformidade da Microsoft a5</span><span class="sxs-lookup"><span data-stu-id="62953-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="62953-114">Qualquer assinatura do Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive for Education + o complemento de gerenciamento de risco do Microsoft 365 a5 Insider</span><span class="sxs-lookup"><span data-stu-id="62953-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="62953-115">Assinatura do Office 365 Enterprise E5 (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="62953-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="62953-116">Assinatura do Office 365 Enterprise E3 + o complemento avançado de conformidade do Office 365 (não está mais disponível para novas assinaturas, consulte observação)</span><span class="sxs-lookup"><span data-stu-id="62953-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="62953-117">Os usuários que enviam e respondem a solicitações de gerenciamento de acesso privilegiado devem receber uma das licenças acima.</span><span class="sxs-lookup"><span data-stu-id="62953-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="62953-118">O Office 365 Advanced Compliance não é mais vendido como uma assinatura autônoma.</span><span class="sxs-lookup"><span data-stu-id="62953-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="62953-119">Quando as assinaturas atuais expiram, os clientes devem fazer a transição para uma das assinaturas acima, que contêm o mesmo ou outros recursos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="62953-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="62953-120">Se você não tiver um plano existente do Office 365 Enterprise E5 e quiser experimentar o gerenciamento de acesso privilegiado, [adicione o microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente do Office 365 ou [Inscreva-se para obter uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Microsoft 365 Enterprise e5.</span><span class="sxs-lookup"><span data-stu-id="62953-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="62953-121">Habilitar e configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="62953-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="62953-122">Siga estas etapas para configurar e usar o acesso privilegiado em sua organização:</span><span class="sxs-lookup"><span data-stu-id="62953-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="62953-123">Etapa 1: criar um grupo do aprovador</span><span class="sxs-lookup"><span data-stu-id="62953-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="62953-124">Antes de começar a usar o acesso de privilégio, determine quem precisa de autoridade de aprovação para solicitações de entrada para acesso a tarefas privilegiadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="62953-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="62953-125">Qualquer usuário que faça parte do grupo aprovadores é capaz de aprovar as solicitações de acesso.</span><span class="sxs-lookup"><span data-stu-id="62953-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="62953-126">Esse grupo é habilitado pela criação de um grupo de segurança habilitado para email no Office 365.</span><span class="sxs-lookup"><span data-stu-id="62953-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="62953-127">Etapa 2: habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="62953-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="62953-128">O acesso privilegiado deve ser explicitamente habilitado no Office 365 com o grupo padrão aprovador, incluindo um conjunto de contas de sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="62953-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="62953-129">Etapa 3: criar uma política de acesso</span><span class="sxs-lookup"><span data-stu-id="62953-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="62953-130">A criação de uma política de aprovação permite definir os requisitos de aprovação específicos delimitados em tarefas individuais.</span><span class="sxs-lookup"><span data-stu-id="62953-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="62953-131">As opções de tipo de aprovação são **auto** ou **manual**.</span><span class="sxs-lookup"><span data-stu-id="62953-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="62953-132">Etapa 4: enviar/aprovar solicitações de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="62953-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="62953-133">Uma vez habilitado, o acesso privilegiado requer aprovações para qualquer tarefa que tenha uma política de aprovação associada definida.</span><span class="sxs-lookup"><span data-stu-id="62953-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="62953-134">Para tarefas incluídas em uma política de aprovação, os usuários devem solicitar e receber aprovação de acesso para ter as permissões necessárias para executar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="62953-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="62953-135">Depois que a aprovação for concedida, o usuário solicitante poderá executar a tarefa pretendida e o acesso privilegiado autorizará e executará a tarefa em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="62953-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="62953-136">A aprovação permanece válida para a duração solicitada (a duração padrão é de 4 horas), durante a qual o solicitante pode executar a tarefa pretendida várias vezes.</span><span class="sxs-lookup"><span data-stu-id="62953-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="62953-137">Todas essas execuções são registradas e disponibilizadas para auditoria de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="62953-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="62953-138">Se você quiser usar o PowerShell de gerenciamento do Exchange para habilitar e configurar o acesso privilegiado, siga as etapas em [Connect to Exchange Online PowerShell using Multifactor Authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to Connect to Exchange Online PowerShell com suas credenciais do Office 365.</span><span class="sxs-lookup"><span data-stu-id="62953-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="62953-139">Não é necessário habilitar a autenticação multifator para sua organização usar as etapas para habilitar o acesso privilegiado ao se conectar ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="62953-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="62953-140">A conexão com a autenticação multifator cria um token OAuth usado pelo acesso privilegiado para assinar suas solicitações.</span><span class="sxs-lookup"><span data-stu-id="62953-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="62953-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="62953-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="62953-142">Etapa 1: criar um grupo do aprovador</span><span class="sxs-lookup"><span data-stu-id="62953-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="62953-143">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="62953-144">No centro de administração, vá para **grupos**  >  **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="62953-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="62953-145">Selecione **grupo de segurança habilitado para email** e preencha os **campos nome**, endereço de **email do grupo**e **Descrição** do novo grupo.</span><span class="sxs-lookup"><span data-stu-id="62953-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="62953-146">Salve o grupo.</span><span class="sxs-lookup"><span data-stu-id="62953-146">Save the group.</span></span> <span data-ttu-id="62953-147">Pode levar alguns minutos para que o grupo seja totalmente configurado e apareça no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="62953-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="62953-148">Selecione o novo grupo do aprovador e selecione **Editar** para adicionar usuários ao grupo.</span><span class="sxs-lookup"><span data-stu-id="62953-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="62953-149">Salve o grupo.</span><span class="sxs-lookup"><span data-stu-id="62953-149">Save the group.</span></span>

<span data-ttu-id="62953-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="62953-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="62953-151">Etapa 2: habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="62953-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="62953-152">No centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62953-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="62953-153">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="62953-154">No centro de administração, acesse **configurações**  >  **org**Settings  >  **Security & Privacy**  >  **Privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="62953-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62953-155">Habilite o controle **exigir aprovações para tarefas privilegiadas** .</span><span class="sxs-lookup"><span data-stu-id="62953-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="62953-156">Atribua o grupo do aprovador que você criou na etapa 1 como o **grupo de aprovadores padrão**.</span><span class="sxs-lookup"><span data-stu-id="62953-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="62953-157">**Salvar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="62953-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="62953-158">No PowerShell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="62953-159">Para habilitar o acesso privilegiado e atribuir o grupo do aprovador, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="62953-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="62953-160">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="62953-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="62953-161">O recurso de contas de sistema é disponibilizado para garantir que determinadas automaçãos em suas organizações possam trabalhar sem dependências de acesso privilegiado, no entanto, é recomendável que essas exclusões sejam excepcionais e que as permitidas sejam aprovadas e auditadas regularmente.</span><span class="sxs-lookup"><span data-stu-id="62953-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="62953-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="62953-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="62953-163">Etapa 3: criar uma política de acesso</span><span class="sxs-lookup"><span data-stu-id="62953-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="62953-164">Você pode criar e configurar até 30 políticas de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="62953-165">No centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62953-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="62953-166">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="62953-167">No centro de administração, acesse **configurações**  >  **org**Settings  >  **Security & Privacy**  >  **Privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="62953-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62953-168">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="62953-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62953-169">Selecione **Configurar políticas** e selecione **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="62953-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="62953-170">Nos campos suspensos, selecione os valores apropriados para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="62953-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="62953-171">**Tipo de política**: tarefa, função ou grupo de função</span><span class="sxs-lookup"><span data-stu-id="62953-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="62953-172">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="62953-173">**Nome da política**: selecione nas políticas disponíveis</span><span class="sxs-lookup"><span data-stu-id="62953-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="62953-174">**Tipo de aprovação**: manual ou automática</span><span class="sxs-lookup"><span data-stu-id="62953-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="62953-175">**Grupo de aprovação**: selecione o grupo aprovadores criado na etapa 1</span><span class="sxs-lookup"><span data-stu-id="62953-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="62953-176">Selecione **criar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="62953-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="62953-177">Pode levar alguns minutos até que a política seja totalmente configurada e habilitada.</span><span class="sxs-lookup"><span data-stu-id="62953-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="62953-178">No PowerShell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="62953-179">Para criar e definir uma política de aprovação, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="62953-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="62953-180">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="62953-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="62953-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="62953-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="62953-182">Etapa 4: enviar/aprovar solicitações de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="62953-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="62953-183">Solicitando autorização de elevação para executar tarefas privilegiadas</span><span class="sxs-lookup"><span data-stu-id="62953-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="62953-184">As solicitações de acesso privilegiado são válidas por até 24 horas após o envio da solicitação.</span><span class="sxs-lookup"><span data-stu-id="62953-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="62953-185">Se não for aprovada ou negada, as solicitações expirarão e o acesso não será aprovado.</span><span class="sxs-lookup"><span data-stu-id="62953-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="62953-186">No centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62953-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="62953-187">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="62953-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="62953-188">No centro de administração, acesse **configurações**  >  **org**Settings  >  **Security & Privacy**  >  **Privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="62953-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62953-189">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="62953-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62953-190">Selecione **nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="62953-190">Select **New request**.</span></span> <span data-ttu-id="62953-191">Nos campos suspensos, selecione os valores apropriados para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="62953-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="62953-192">**Tipo de solicitação**: tarefa, função ou grupo de função</span><span class="sxs-lookup"><span data-stu-id="62953-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="62953-193">**Escopo da solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="62953-194">**Solicitação de**: selecione nas políticas disponíveis</span><span class="sxs-lookup"><span data-stu-id="62953-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="62953-195">**Duração (horas)**: número de horas de acesso solicitado.</span><span class="sxs-lookup"><span data-stu-id="62953-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="62953-196">Não há um limite no número de horas que podem ser solicitadas.</span><span class="sxs-lookup"><span data-stu-id="62953-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="62953-197">**Comments**: campo de texto para comentários relacionados à sua solicitação de acesso</span><span class="sxs-lookup"><span data-stu-id="62953-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="62953-198">Selecione **salvar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="62953-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="62953-199">Sua solicitação será enviada ao grupo do aprovador por email.</span><span class="sxs-lookup"><span data-stu-id="62953-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="62953-200">No PowerShell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="62953-201">Execute o seguinte comando no PowerShell do Exchange Online para criar e enviar uma solicitação de aprovação para o grupo do aprovador:</span><span class="sxs-lookup"><span data-stu-id="62953-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="62953-202">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="62953-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="62953-203">Exibir o status das solicitações de elevação</span><span class="sxs-lookup"><span data-stu-id="62953-203">View status of elevation requests</span></span>

<span data-ttu-id="62953-204">Após a criação de uma solicitação de aprovação, o status da solicitação de elevação poderá ser revisado no centro de administração ou no PowerShell de gerenciamento do Exchange usando o ID de solicitação associado.</span><span class="sxs-lookup"><span data-stu-id="62953-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="62953-205">No centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62953-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="62953-206">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="62953-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="62953-207">No centro de administração, acesse **configurações**  >  **org**Settings  >  **Security & Privacy**  >  **Privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="62953-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62953-208">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="62953-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62953-209">Selecione **Exibir** para filtrar solicitações enviadas por status **pendente**, **aprovado**, **negado**ou de **Lockbox do cliente** .</span><span class="sxs-lookup"><span data-stu-id="62953-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="62953-210">No PowerShell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="62953-211">Execute o seguinte comando no PowerShell do Exchange Online para exibir um status de solicitação de aprovação para uma ID de solicitação específica:</span><span class="sxs-lookup"><span data-stu-id="62953-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="62953-212">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="62953-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="62953-213">Aprovar uma solicitação de autorização de elevação</span><span class="sxs-lookup"><span data-stu-id="62953-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="62953-214">Quando uma solicitação de aprovação é criada, os membros do grupo de aprovadores relevantes recebem uma notificação por email e podem aprovar a solicitação associada à ID da solicitação.</span><span class="sxs-lookup"><span data-stu-id="62953-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="62953-215">O solicitante é notificado sobre a aprovação da solicitação ou a negação via mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="62953-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="62953-216">No centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62953-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="62953-217">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="62953-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="62953-218">No centro de administração, acesse **configurações**  >  **org**Settings  >  **Security & Privacy**  >  **Privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="62953-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62953-219">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="62953-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62953-220">Selecione uma solicitação listada para exibir os detalhes e executar a ação na solicitação.</span><span class="sxs-lookup"><span data-stu-id="62953-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="62953-221">Selecione **aprovar** para aprovar a solicitação ou selecione **negar** para negar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="62953-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="62953-222">As solicitações aprovadas anteriormente podem ter acesso revogado ao selecionar **revogar**.</span><span class="sxs-lookup"><span data-stu-id="62953-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="62953-223">No PowerShell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="62953-224">Para aprovar uma solicitação de autorização de elevação, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="62953-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="62953-225">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="62953-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="62953-226">Para negar uma solicitação de autorização de elevação, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="62953-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="62953-227">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="62953-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="62953-228">Excluir uma política de acesso privilegiada no Office 365</span><span class="sxs-lookup"><span data-stu-id="62953-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="62953-229">Se ele não for mais necessário em sua organização, você poderá excluir uma política de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="62953-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="62953-230">No centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62953-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="62953-231">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="62953-232">No centro de administração, acesse **configurações**  >  **org**Settings  >  **Security & Privacy**  >  **Privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="62953-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62953-233">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="62953-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="62953-234">Selecione **Configurar políticas**.</span><span class="sxs-lookup"><span data-stu-id="62953-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="62953-235">Selecione a política que você deseja excluir e, em seguida, selecione **remover política**.</span><span class="sxs-lookup"><span data-stu-id="62953-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="62953-236">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="62953-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="62953-237">No PowerShell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="62953-238">Para excluir uma política de acesso privilegiada, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="62953-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="62953-239">Desabilitar o acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="62953-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="62953-240">Se necessário, você pode desabilitar o gerenciamento de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="62953-241">Desabilitar o acesso privilegiado não exclui nenhuma política de aprovação associada ou grupos de aprovadores.</span><span class="sxs-lookup"><span data-stu-id="62953-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="62953-242">No centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="62953-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="62953-243">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com as credenciais de uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="62953-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="62953-244">No centro de administração, acesse **configurações**  >  **org**Settings  >  **Security & Privacy**  >  **Privileged Access**.</span><span class="sxs-lookup"><span data-stu-id="62953-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="62953-245">Habilitar as **aprovações de controle de acesso privilegiado** .</span><span class="sxs-lookup"><span data-stu-id="62953-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="62953-246">No PowerShell de gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="62953-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="62953-247">Para desabilitar o acesso privilegiado, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="62953-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
