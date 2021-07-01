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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Use este artigo para saber mais sobre a habilitação e configuração do gerenciamento de acesso privilegiado Office 365.
ms.openlocfilehash: 13b600c60e1b9c88285ee58efcf80a7ff5ea17fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226114"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="645fd-103">Introdução ao gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="645fd-103">Get started with privileged access management</span></span>

<span data-ttu-id="645fd-104">Este tópico orienta você por meio da habilitação e configuração do gerenciamento de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="645fd-105">Você pode usar o PowerShell de gerenciamento Centro de administração do Microsoft 365 ou Exchange gerenciamento para gerenciar e usar o acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="645fd-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="645fd-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="645fd-106">Before you begin</span></span>

<span data-ttu-id="645fd-107">Antes de começar com o gerenciamento de acesso privilegiado, você deve confirmar sua assinatura [Microsoft 365 e](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) quaisquer complementos.</span><span class="sxs-lookup"><span data-stu-id="645fd-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="645fd-108">Para acessar e usar o gerenciamento de acesso privilegiado, sua organização deve ter uma das seguintes assinaturas ou complementos:</span><span class="sxs-lookup"><span data-stu-id="645fd-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="645fd-109">Microsoft 365 E5 assinatura (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="645fd-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="645fd-110">Microsoft 365 E3 assinatura (ou assinatura Office 365 E3 + assinatura Enterprise Mobility e Security E3) + o Microsoft 365 E5 Compliance complemento do Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="645fd-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="645fd-111">Qualquer Microsoft 365, Office 365, Exchange, SharePoint assinatura ou OneDrive for Business assinatura + o complemento Microsoft 365 E5 Gerenciamento de Riscos do Insider</span><span class="sxs-lookup"><span data-stu-id="645fd-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="645fd-112">Microsoft 365 A5 assinatura (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="645fd-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="645fd-113">Microsoft 365 A3 assinatura (ou assinatura Office 365 A3 + assinatura Enterprise Mobility and Security A3) + o complemento conformidade do Microsoft A5</span><span class="sxs-lookup"><span data-stu-id="645fd-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="645fd-114">Qualquer Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive assinatura para Educação + o complemento Microsoft 365 A5 Gerenciamento de Riscos do Microsoft 365 A5 Insider</span><span class="sxs-lookup"><span data-stu-id="645fd-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="645fd-115">Office 365 Enterprise Assinatura E5 (versão paga ou avaliação)</span><span class="sxs-lookup"><span data-stu-id="645fd-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="645fd-116">Office 365 Enterprise Assinatura E3 + o Conformidade Avançada do Office 365 complemento (não está mais disponível para novas assinaturas, consulte observação)</span><span class="sxs-lookup"><span data-stu-id="645fd-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="645fd-117">Os usuários que estão enviando e respondendo a solicitações de gerenciamento de acesso privilegiado devem receber uma das licenças acima.</span><span class="sxs-lookup"><span data-stu-id="645fd-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="645fd-118">Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma.</span><span class="sxs-lookup"><span data-stu-id="645fd-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="645fd-119">Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.</span><span class="sxs-lookup"><span data-stu-id="645fd-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="645fd-120">Se você não tiver um plano Office 365 Enterprise E5 existente e quiser tentar o gerenciamento de acesso privilegiado, adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura do Office 365 existente ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5. [](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="645fd-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="645fd-121">Habilitar e configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="645fd-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="645fd-122">Siga estas etapas para configurar e usar o acesso privilegiado em sua organização:</span><span class="sxs-lookup"><span data-stu-id="645fd-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="645fd-123">Etapa 1: Criar um grupo de aprovação</span><span class="sxs-lookup"><span data-stu-id="645fd-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="645fd-124">Antes de começar a usar o acesso privilegiado, determine quem precisa de autoridade de aprovação para solicitações de acesso a tarefas elevadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="645fd-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="645fd-125">Qualquer usuário que faz parte do grupo de Aprovadores pode aprovar solicitações de acesso.</span><span class="sxs-lookup"><span data-stu-id="645fd-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="645fd-126">Esse grupo é habilitado criando um grupo de segurança habilitado para email no Office 365.</span><span class="sxs-lookup"><span data-stu-id="645fd-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="645fd-127">Etapa 2: Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="645fd-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="645fd-128">O acesso privilegiado deve ser explicitamente habilitado no Office 365 com o grupo aprovador padrão, incluindo um conjunto de contas do sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="645fd-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="645fd-129">Etapa 3: Criar uma política de acesso</span><span class="sxs-lookup"><span data-stu-id="645fd-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="645fd-130">Criar uma política de aprovação permite que você defina os requisitos de aprovação específicos com escopo em tarefas individuais.</span><span class="sxs-lookup"><span data-stu-id="645fd-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="645fd-131">As opções de tipo de aprovação são **Automática** ou **Manual**.</span><span class="sxs-lookup"><span data-stu-id="645fd-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="645fd-132">Etapa 4: Enviar/aprovar solicitações de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="645fd-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="645fd-133">Uma vez habilitado, o acesso privilegiado requer aprovações para qualquer tarefa que tenha uma política de aprovação associada definida.</span><span class="sxs-lookup"><span data-stu-id="645fd-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="645fd-134">Para tarefas incluídas em uma política de aprovação, os usuários devem solicitar e ter a aprovação de acesso concedida para que tenham as permissões necessárias para executar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="645fd-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="645fd-135">Depois que a aprovação for concedida, o usuário solicitante poderá executar a tarefa pretendida e o acesso privilegiado autorizará e executará a tarefa em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="645fd-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="645fd-136">A aprovação permanece válida pelo tempo solicitado (a duração padrão é de quatro horas), durante o qual o solicitante pode executar a tarefa pretendida várias vezes.</span><span class="sxs-lookup"><span data-stu-id="645fd-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="645fd-137">Todas essas execuções são registradas e disponibilizadas para auditoria de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="645fd-137">All such executions are logged and made available for security and compliance auditing.</span></span>

> [!NOTE]
> <span data-ttu-id="645fd-138">Se você quiser usar o powershell de gerenciamento do Exchange para habilitar e configurar o acesso privilegiado, siga as etapas do Conexão para Exchange Online PowerShell usando a autenticação [multifação](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) para se conectar ao Exchange Online PowerShell com suas credenciais de Office 365.</span><span class="sxs-lookup"><span data-stu-id="645fd-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="645fd-139">Você não precisa habilitar a autenticação multifabilitar para sua organização usar as etapas para habilitar o acesso privilegiado ao se conectar ao Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="645fd-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="645fd-140">A conexão com a autenticação multifatório cria um token OAuth usado pelo acesso privilegiado para assinar suas solicitações.</span><span class="sxs-lookup"><span data-stu-id="645fd-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="645fd-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="645fd-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="645fd-142">Etapa 1: Criar um grupo de aprovação</span><span class="sxs-lookup"><span data-stu-id="645fd-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="645fd-143">Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="645fd-144">No Centro de Administração, vá para **Grupos**  >  **Adicionar um grupo**.</span><span class="sxs-lookup"><span data-stu-id="645fd-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="645fd-145">Selecione **o grupo de segurança habilitado** para email e conclua os campos **Nome,** Endereço de **email** de grupo e **Descrição** do novo grupo.</span><span class="sxs-lookup"><span data-stu-id="645fd-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="645fd-146">Salve o grupo.</span><span class="sxs-lookup"><span data-stu-id="645fd-146">Save the group.</span></span> <span data-ttu-id="645fd-147">Pode levar alguns minutos para que o grupo esteja totalmente configurado e apareça no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="645fd-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="645fd-148">Selecione o grupo do novo aprovador e selecione **editar** para adicionar usuários ao grupo.</span><span class="sxs-lookup"><span data-stu-id="645fd-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="645fd-149">Salve o grupo.</span><span class="sxs-lookup"><span data-stu-id="645fd-149">Save the group.</span></span>

<span data-ttu-id="645fd-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="645fd-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="645fd-151">Etapa 2: Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="645fd-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="645fd-152">No Centro de Administração Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645fd-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="645fd-153">Entre na central [Administração Microsoft 365 usando](https://admin.microsoft.com) credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="645fd-154">No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="645fd-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="645fd-155">Habilita **o controle Exigir aprovações para tarefas privilegiadas.**</span><span class="sxs-lookup"><span data-stu-id="645fd-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="645fd-156">Atribua o grupo do aprovador que você criou na Etapa 1 como **o grupo aprovadores padrão**.</span><span class="sxs-lookup"><span data-stu-id="645fd-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="645fd-157">**Salvar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="645fd-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="645fd-158">No Exchange PowerShell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645fd-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="645fd-159">Para habilitar o acesso privilegiado e atribuir o grupo do aprovador, execute o seguinte comando Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="645fd-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="645fd-160">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="645fd-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="645fd-161">O recurso contas do sistema é disponibilizado para garantir que determinadas automações em suas organizações possam funcionar sem dependência de acesso privilegiado, no entanto, é recomendável que essas exclusões sejam excepcionais e as permitidas sejam aprovadas e auditadas regularmente.</span><span class="sxs-lookup"><span data-stu-id="645fd-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="645fd-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="645fd-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="645fd-163">Etapa 3: Criar uma política de acesso</span><span class="sxs-lookup"><span data-stu-id="645fd-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="645fd-164">Você pode criar e configurar até 30 políticas de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="645fd-165">No Centro de Administração Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645fd-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="645fd-166">Entre na central [Administração Microsoft 365 usando](https://admin.microsoft.com) credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="645fd-167">No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="645fd-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="645fd-168">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="645fd-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="645fd-169">Selecione **Configurar políticas e** selecione Adicionar uma **política**.</span><span class="sxs-lookup"><span data-stu-id="645fd-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="645fd-170">Nos campos drop-down, selecione os valores apropriados para sua organização:</span><span class="sxs-lookup"><span data-stu-id="645fd-170">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="645fd-171">**Tipo de política**: tarefa, função ou grupo de funções</span><span class="sxs-lookup"><span data-stu-id="645fd-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="645fd-172">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="645fd-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="645fd-173">**Nome da política**: selecione uma das políticas disponíveis</span><span class="sxs-lookup"><span data-stu-id="645fd-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="645fd-174">**Tipo de aprovação**: manual ou automática</span><span class="sxs-lookup"><span data-stu-id="645fd-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="645fd-175">**Grupo de aprovação**: selecione o grupo de aprovadores criado na Etapa 1</span><span class="sxs-lookup"><span data-stu-id="645fd-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="645fd-176">Selecione **Criar** **e,** em seguida, Fechar .</span><span class="sxs-lookup"><span data-stu-id="645fd-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="645fd-177">Pode levar alguns minutos para que a política seja totalmente configurada e habilitada.</span><span class="sxs-lookup"><span data-stu-id="645fd-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="645fd-178">No Exchange PowerShell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645fd-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="645fd-179">Para criar e definir uma política de aprovação, execute o seguinte comando Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="645fd-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="645fd-180">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="645fd-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="645fd-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="645fd-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="645fd-182">Etapa 4: Enviar/aprovar solicitações de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="645fd-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="645fd-183">Solicitar autorização de elevação para executar tarefas privilegiadas</span><span class="sxs-lookup"><span data-stu-id="645fd-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="645fd-184">As solicitações de acesso privilegiado são válidas por até 24 horas após o envio da solicitação.</span><span class="sxs-lookup"><span data-stu-id="645fd-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="645fd-185">Se não forem aprovadas ou negadas, as solicitações expiram e o acesso não é aprovado.</span><span class="sxs-lookup"><span data-stu-id="645fd-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="645fd-186">No Centro de Administração Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645fd-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="645fd-187">Entre na central [Administração Microsoft 365 usando](https://admin.microsoft.com) suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="645fd-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="645fd-188">No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="645fd-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="645fd-189">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="645fd-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="645fd-190">Selecione **Nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="645fd-190">Select **New request**.</span></span> <span data-ttu-id="645fd-191">Nos campos drop-down, selecione os valores apropriados para sua organização:</span><span class="sxs-lookup"><span data-stu-id="645fd-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="645fd-192">**Tipo de solicitação**: tarefa, função ou grupo de funções</span><span class="sxs-lookup"><span data-stu-id="645fd-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="645fd-193">**Escopo da solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="645fd-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="645fd-194">**Solicitação**: selecione uma das políticas disponíveis</span><span class="sxs-lookup"><span data-stu-id="645fd-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="645fd-195">**Duração (horas)**: número de horas de acesso solicitadas.</span><span class="sxs-lookup"><span data-stu-id="645fd-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="645fd-196">Não há um limite no número de horas que podem ser solicitadas.</span><span class="sxs-lookup"><span data-stu-id="645fd-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="645fd-197">**Comentários**: Campo de texto para comentários relacionados à sua solicitação de acesso</span><span class="sxs-lookup"><span data-stu-id="645fd-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="645fd-198">Selecione **Salvar** **e,** em seguida, Fechar .</span><span class="sxs-lookup"><span data-stu-id="645fd-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="645fd-199">Sua solicitação será enviada para o grupo do aprovador por email.</span><span class="sxs-lookup"><span data-stu-id="645fd-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="645fd-200">No Exchange PowerShell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645fd-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="645fd-201">Execute o seguinte comando no Exchange Online PowerShell para criar e enviar uma solicitação de aprovação ao grupo do aprovador:</span><span class="sxs-lookup"><span data-stu-id="645fd-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="645fd-202">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="645fd-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="645fd-203">Ver o status das solicitações de elevação</span><span class="sxs-lookup"><span data-stu-id="645fd-203">View status of elevation requests</span></span>

<span data-ttu-id="645fd-204">Após a criação de uma solicitação de aprovação, o status da solicitação de elevação pode ser revisado no centro de administração ou no Exchange Management PowerShell usando a ID de solicitação associada.</span><span class="sxs-lookup"><span data-stu-id="645fd-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="645fd-205">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645fd-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="645fd-206">Entre [na](https://admin.microsoft.com) Centro de administração do Microsoft 365 com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="645fd-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="645fd-207">No centro de administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="645fd-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="645fd-208">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="645fd-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="645fd-209">Selecione **Exibir** para filtrar solicitações enviadas **pelo** status pendente **,** **Aprovado,** Negado ou Bloqueio **do** Cliente.</span><span class="sxs-lookup"><span data-stu-id="645fd-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="645fd-210">No Exchange PowerShell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645fd-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="645fd-211">Execute o seguinte comando no Exchange Online PowerShell para exibir um status de solicitação de aprovação para uma ID de solicitação específica:</span><span class="sxs-lookup"><span data-stu-id="645fd-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="645fd-212">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="645fd-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="645fd-213">Aprovar uma solicitação de autorização de elevação</span><span class="sxs-lookup"><span data-stu-id="645fd-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="645fd-214">Quando uma solicitação de aprovação é criada, membros do grupo aprovador relevante recebem uma notificação por email e podem aprovar a solicitação associada à ID da solicitação.</span><span class="sxs-lookup"><span data-stu-id="645fd-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="645fd-215">O solicitante é notificado da aprovação ou negação da solicitação por mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="645fd-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="645fd-216">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645fd-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="645fd-217">Entre [na](https://admin.microsoft.com) Centro de administração do Microsoft 365 com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="645fd-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="645fd-218">No centro de administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="645fd-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="645fd-219">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="645fd-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="645fd-220">Selecione uma solicitação listada para exibir os detalhes e para tomar medidas na solicitação.</span><span class="sxs-lookup"><span data-stu-id="645fd-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="645fd-221">Selecione **Aprovar** para aprovar a solicitação ou selecione **Negar** para negar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="645fd-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="645fd-222">Solicitações aprovadas anteriormente podem ter acesso revogado selecionando **Revogar**.</span><span class="sxs-lookup"><span data-stu-id="645fd-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="645fd-223">No Exchange PowerShell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645fd-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="645fd-224">Para aprovar uma solicitação de autorização de elevação, execute o seguinte comando Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="645fd-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="645fd-225">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="645fd-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="645fd-226">Para negar uma solicitação de autorização de elevação, execute o seguinte comando Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="645fd-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="645fd-227">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="645fd-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="645fd-228">Excluir uma política de acesso privilegiado Office 365</span><span class="sxs-lookup"><span data-stu-id="645fd-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="645fd-229">Se ela não for mais necessária em sua organização, você poderá excluir uma política de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="645fd-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="645fd-230">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645fd-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="645fd-231">Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="645fd-232">No centro de administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="645fd-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="645fd-233">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="645fd-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="645fd-234">Selecione **Configurar políticas**.</span><span class="sxs-lookup"><span data-stu-id="645fd-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="645fd-235">Selecione a política que deseja excluir e selecione **Remover Política**.</span><span class="sxs-lookup"><span data-stu-id="645fd-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="645fd-236">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="645fd-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="645fd-237">No Exchange PowerShell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645fd-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="645fd-238">Para excluir uma política de acesso privilegiado, execute o seguinte comando no Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="645fd-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="645fd-239">Desabilitar o acesso privilegiado Office 365</span><span class="sxs-lookup"><span data-stu-id="645fd-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="645fd-240">Se necessário, você pode desabilitar o gerenciamento de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="645fd-241">Desabilitar o acesso privilegiado não exclui políticas de aprovação ou grupos de aprovação associados.</span><span class="sxs-lookup"><span data-stu-id="645fd-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="645fd-242">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="645fd-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="645fd-243">Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com) com credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="645fd-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="645fd-244">No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="645fd-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="645fd-245">Habilita **o Exigir aprovações para controle de acesso** privilegiado.</span><span class="sxs-lookup"><span data-stu-id="645fd-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="645fd-246">No Exchange PowerShell de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="645fd-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="645fd-247">Para desabilitar o acesso privilegiado, execute o seguinte comando no Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="645fd-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
