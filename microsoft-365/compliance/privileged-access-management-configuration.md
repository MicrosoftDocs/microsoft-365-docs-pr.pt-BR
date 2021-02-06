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
description: Use este artigo para saber mais sobre como ativar e configurar o gerenciamento de acesso privilegiado no Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126528"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="8978c-103">Introdução ao gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8978c-103">Get started with privileged access management</span></span>

<span data-ttu-id="8978c-104">Este tópico orienta você na habilitação e configuração do gerenciamento de acesso privilegiado em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="8978c-105">Você pode usar o Centro de administração do Microsoft 365 ou o PowerShell de Gerenciamento do Exchange para gerenciar e usar o acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="8978c-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8978c-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8978c-106">Before you begin</span></span>

<span data-ttu-id="8978c-107">Antes de começar a trabalhar com o gerenciamento de acesso privilegiado, você deve confirmar sua assinatura do [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e quaisquer complementos.</span><span class="sxs-lookup"><span data-stu-id="8978c-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="8978c-108">Para acessar e usar o gerenciamento de acesso privilegiado, sua organização deve ter uma das seguintes assinaturas ou complementos:</span><span class="sxs-lookup"><span data-stu-id="8978c-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="8978c-109">Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="8978c-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="8978c-110">Assinatura do Microsoft 365 E3 (ou assinatura do Office 365 E3 + assinatura do Enterprise Mobility and Security E3) + o complemento de Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8978c-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="8978c-111">Qualquer assinatura do Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive for Business + o complemento gerenciamento de riscos do Microsoft 365 E5 Insider</span><span class="sxs-lookup"><span data-stu-id="8978c-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="8978c-112">Assinatura do Microsoft 365 A5 (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="8978c-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="8978c-113">Assinatura do Microsoft 365 A3 (ou assinatura do Office 365 A3 + assinatura do Enterprise Mobility and Security A3) + o complemento de Conformidade do Microsoft A5</span><span class="sxs-lookup"><span data-stu-id="8978c-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="8978c-114">Qualquer assinatura do Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive for Education + o complemento Microsoft 365 A5 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="8978c-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="8978c-115">Assinatura do Office 365 Enterprise E5 (versão paga ou de avaliação)</span><span class="sxs-lookup"><span data-stu-id="8978c-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="8978c-116">Assinatura do Office 365 Enterprise E3 + complemento de Conformidade Avançada do Office 365 (não está mais disponível para novas assinaturas, confira a observação)</span><span class="sxs-lookup"><span data-stu-id="8978c-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="8978c-117">Os usuários que estão enviando e respondendo a solicitações de gerenciamento de acesso privilegiado devem receber uma das licenças acima.</span><span class="sxs-lookup"><span data-stu-id="8978c-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="8978c-118">A Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma.</span><span class="sxs-lookup"><span data-stu-id="8978c-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="8978c-119">Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.</span><span class="sxs-lookup"><span data-stu-id="8978c-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="8978c-120">Se você não tiver um plano existente do Office 365 Enterprise E5 e quiser experimentar o gerenciamento de acesso privilegiado, [](https://www.microsoft.com/microsoft-365/enterprise) adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente do Office 365 ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="8978c-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="8978c-121">Habilitar e configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8978c-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="8978c-122">Siga estas etapas para configurar e usar o acesso privilegiado em sua organização:</span><span class="sxs-lookup"><span data-stu-id="8978c-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="8978c-123">Etapa 1: Criar um grupo de aprovador</span><span class="sxs-lookup"><span data-stu-id="8978c-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="8978c-124">Antes de começar a usar o acesso a privilégios, determine quem precisa de autoridade de aprovação para solicitações de entrada de acesso a tarefas elevadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="8978c-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="8978c-125">Qualquer usuário que faz parte do grupo aprovadores é capaz de aprovar solicitações de acesso.</span><span class="sxs-lookup"><span data-stu-id="8978c-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="8978c-126">Esse grupo é habilitado criando um grupo de segurança habilitado para email no Office 365.</span><span class="sxs-lookup"><span data-stu-id="8978c-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="8978c-127">Etapa 2: Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8978c-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="8978c-128">O acesso privilegiado deve ser explicitamente habilitado no Office 365 com o grupo aprovador padrão, incluindo um conjunto de contas do sistema que você deseja excluir do controle de acesso ao gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="8978c-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="8978c-129">Etapa 3: Criar uma política de acesso</span><span class="sxs-lookup"><span data-stu-id="8978c-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="8978c-130">Criar uma política de aprovação permite definir os requisitos de aprovação específicos com escopo em tarefas individuais.</span><span class="sxs-lookup"><span data-stu-id="8978c-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="8978c-131">As opções de tipo de aprovação **são Automático** ou **Manual**.</span><span class="sxs-lookup"><span data-stu-id="8978c-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="8978c-132">Etapa 4: Enviar/aprovar solicitações de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8978c-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="8978c-133">Uma vez habilitado, o acesso privilegiado requer aprovações para qualquer tarefa que tenha uma política de aprovação associada definida.</span><span class="sxs-lookup"><span data-stu-id="8978c-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="8978c-134">Para tarefas incluídas em uma política de aprovação, os usuários devem solicitar e ter a aprovação de acesso concedida para ter permissões necessárias para executar a tarefa.</span><span class="sxs-lookup"><span data-stu-id="8978c-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="8978c-135">Depois que a aprovação for concedida, o usuário solicitante poderá executar a tarefa pretendida e o acesso privilegiado autorizará e executará a tarefa em nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="8978c-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="8978c-136">A aprovação permanece válida pela duração solicitada (a duração padrão é de 4 horas), durante a qual o solicitante pode executar a tarefa pretendida várias vezes.</span><span class="sxs-lookup"><span data-stu-id="8978c-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="8978c-137">Todas essas execuções são registradas e disponibilizadas para auditoria de segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="8978c-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="8978c-138">Se você quiser usar o PowerShell de Gerenciamento do Exchange para habilitar e configurar o acesso privilegiado, siga as etapas em Conectar-se ao PowerShell do Exchange Online usando a autenticação [multifatório](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) para se conectar ao PowerShell do Exchange Online com suas credenciais do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8978c-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="8978c-139">Você não precisa habilitar a autenticação multifabilitar para que sua organização use as etapas para habilitar o acesso privilegiado ao se conectar ao PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8978c-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="8978c-140">A conexão com a autenticação multifatório cria um token OAuth que é usado pelo acesso privilegiado para assinar suas solicitações.</span><span class="sxs-lookup"><span data-stu-id="8978c-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="8978c-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="8978c-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="8978c-142">Etapa 1: Criar um grupo de aprovador</span><span class="sxs-lookup"><span data-stu-id="8978c-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="8978c-143">Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8978c-144">No Centro de Administração, vá para **Grupos**  >  **Adicionar um grupo.**</span><span class="sxs-lookup"><span data-stu-id="8978c-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="8978c-145">Selecione **o grupo de segurança habilitado para email** e  preencha os campos **Nome**, Endereço de **email do** grupo e Descrição do novo grupo.</span><span class="sxs-lookup"><span data-stu-id="8978c-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="8978c-146">Salve o grupo.</span><span class="sxs-lookup"><span data-stu-id="8978c-146">Save the group.</span></span> <span data-ttu-id="8978c-147">Pode levar alguns minutos para que o grupo seja totalmente configurado e apareça no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8978c-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="8978c-148">Selecione o grupo do novo aprovador e selecione **editar** para adicionar usuários ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8978c-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="8978c-149">Salve o grupo.</span><span class="sxs-lookup"><span data-stu-id="8978c-149">Save the group.</span></span>

<span data-ttu-id="8978c-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="8978c-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="8978c-151">Etapa 2: Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8978c-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="8978c-152">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8978c-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8978c-153">Entre no Centro [de Administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8978c-154">No Centro de Administração, vá para **Configurações** de Segurança das Configurações da Organização  >    >  **& acesso privilegiado** de  >  **privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8978c-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8978c-155">Habilita as **Aprovações necessárias para o controle de tarefas privilegiadas.**</span><span class="sxs-lookup"><span data-stu-id="8978c-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="8978c-156">Atribua o grupo do aprovador que você criou na Etapa 1 como o **grupo de aprovadores padrão.**</span><span class="sxs-lookup"><span data-stu-id="8978c-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="8978c-157">**Salvar** e **fechar.**</span><span class="sxs-lookup"><span data-stu-id="8978c-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="8978c-158">No PowerShell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="8978c-159">Para habilitar o acesso privilegiado e atribuir o grupo do aprovador, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8978c-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="8978c-160">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="8978c-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="8978c-161">O recurso de contas do sistema é disponibilizado para garantir que determinadas automações em suas organizações possam funcionar sem dependência de acesso privilegiado, no entanto, é recomendável que essas exclusões sejam excepcionais e as permitidas sejam aprovadas e auditadas regularmente.</span><span class="sxs-lookup"><span data-stu-id="8978c-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="8978c-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="8978c-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="8978c-163">Etapa 3: Criar uma política de acesso</span><span class="sxs-lookup"><span data-stu-id="8978c-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="8978c-164">Você pode criar e configurar até 30 políticas de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="8978c-165">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8978c-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8978c-166">Entre no Centro [de Administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8978c-167">No Centro de Administração, vá para **Configurações** de Segurança das Configurações da Organização  >    >  **& acesso privilegiado** de  >  **privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8978c-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8978c-168">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8978c-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8978c-169">Selecione **Configurar políticas** e selecione Adicionar uma **política.**</span><span class="sxs-lookup"><span data-stu-id="8978c-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="8978c-170">Nos campos da lista lista, selecione os valores apropriados para sua organização:</span><span class="sxs-lookup"><span data-stu-id="8978c-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="8978c-171">**Tipo de política:** Tarefa, Função ou Grupo de Funções</span><span class="sxs-lookup"><span data-stu-id="8978c-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="8978c-172">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="8978c-173">**Nome da** política: selecione entre as políticas disponíveis</span><span class="sxs-lookup"><span data-stu-id="8978c-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="8978c-174">**Tipo de aprovação:** Manual ou Automático</span><span class="sxs-lookup"><span data-stu-id="8978c-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="8978c-175">**Grupo de aprovação:** selecione o grupo de aprovadores criado na Etapa 1</span><span class="sxs-lookup"><span data-stu-id="8978c-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="8978c-176">Selecione **Criar** **e, em seguida, Fechar.**</span><span class="sxs-lookup"><span data-stu-id="8978c-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="8978c-177">Pode levar alguns minutos para que a política seja totalmente configurada e habilitada.</span><span class="sxs-lookup"><span data-stu-id="8978c-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="8978c-178">No PowerShell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="8978c-179">Para criar e definir uma política de aprovação, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8978c-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="8978c-180">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="8978c-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="8978c-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="8978c-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="8978c-182">Etapa 4: Enviar/aprovar solicitações de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8978c-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="8978c-183">Solicitar autorização de elevação para executar tarefas privilegiadas</span><span class="sxs-lookup"><span data-stu-id="8978c-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="8978c-184">As solicitações de acesso privilegiado são válidas por até 24 horas após o envio da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8978c-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="8978c-185">Se não for aprovado ou negado, as solicitações expiram e o acesso não é aprovado.</span><span class="sxs-lookup"><span data-stu-id="8978c-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="8978c-186">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8978c-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="8978c-187">Entre no Centro [de Administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="8978c-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="8978c-188">No Centro de Administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8978c-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8978c-189">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8978c-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8978c-190">Selecione **Nova solicitação.**</span><span class="sxs-lookup"><span data-stu-id="8978c-190">Select **New request**.</span></span> <span data-ttu-id="8978c-191">Nos campos da lista lista, selecione os valores apropriados para sua organização:</span><span class="sxs-lookup"><span data-stu-id="8978c-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="8978c-192">**Tipo de solicitação:** Tarefa, Função ou Grupo de Funções</span><span class="sxs-lookup"><span data-stu-id="8978c-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="8978c-193">**Escopo da solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="8978c-194">**Solicitação para:** Selecionar entre as políticas disponíveis</span><span class="sxs-lookup"><span data-stu-id="8978c-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="8978c-195">**Duração (horas)**: Número de horas de acesso solicitado.</span><span class="sxs-lookup"><span data-stu-id="8978c-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="8978c-196">Não há um limite no número de horas que podem ser solicitadas.</span><span class="sxs-lookup"><span data-stu-id="8978c-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="8978c-197">**Comentários:** campo texto para comentários relacionados à sua solicitação de acesso</span><span class="sxs-lookup"><span data-stu-id="8978c-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="8978c-198">Selecione **Salvar** **e, em seguida, Fechar.**</span><span class="sxs-lookup"><span data-stu-id="8978c-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="8978c-199">Sua solicitação será enviada ao grupo do aprovador por email.</span><span class="sxs-lookup"><span data-stu-id="8978c-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="8978c-200">No PowerShell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="8978c-201">Execute o seguinte comando no PowerShell do Exchange Online para criar e enviar uma solicitação de aprovação ao grupo do aprovador:</span><span class="sxs-lookup"><span data-stu-id="8978c-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="8978c-202">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="8978c-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="8978c-203">Exibir o status das solicitações de elevação</span><span class="sxs-lookup"><span data-stu-id="8978c-203">View status of elevation requests</span></span>

<span data-ttu-id="8978c-204">Depois que uma solicitação de aprovação é criada, o status da solicitação de elevação pode ser revisado no centro de administração ou no PowerShell de Gerenciamento do Exchange usando a ID associada à solicitação.</span><span class="sxs-lookup"><span data-stu-id="8978c-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="8978c-205">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8978c-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="8978c-206">Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="8978c-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="8978c-207">No centro de administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8978c-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8978c-208">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8978c-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8978c-209">Selecione **Exibir** para filtrar as solicitações enviadas por **Pendente,** **Aprovado,** **Negado** ou Status do Sistema de **Bloqueio do** Cliente.</span><span class="sxs-lookup"><span data-stu-id="8978c-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="8978c-210">No PowerShell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="8978c-211">Execute o seguinte comando no PowerShell do Exchange Online para exibir um status de solicitação de aprovação para uma ID de solicitação específica:</span><span class="sxs-lookup"><span data-stu-id="8978c-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="8978c-212">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="8978c-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="8978c-213">Aprovando uma solicitação de autorização de elevação</span><span class="sxs-lookup"><span data-stu-id="8978c-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="8978c-214">Quando uma solicitação de aprovação é criada, os membros do grupo aprovador relevante recebem uma notificação por email e podem aprovar a solicitação associada à ID da solicitação.</span><span class="sxs-lookup"><span data-stu-id="8978c-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="8978c-215">O solicitante é notificado sobre a aprovação ou negação de solicitação via mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="8978c-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="8978c-216">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8978c-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="8978c-217">Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="8978c-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="8978c-218">No centro de administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8978c-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8978c-219">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8978c-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8978c-220">Selecione uma solicitação listada para exibir os detalhes e agir sobre a solicitação.</span><span class="sxs-lookup"><span data-stu-id="8978c-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="8978c-221">Selecione **Aprovar** para aprovar a solicitação ou **Negar** para negar a solicitação.</span><span class="sxs-lookup"><span data-stu-id="8978c-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="8978c-222">Solicitações aprovadas anteriormente podem ter acesso revogado selecionando **Revogar**.</span><span class="sxs-lookup"><span data-stu-id="8978c-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="8978c-223">No PowerShell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="8978c-224">Para aprovar uma solicitação de autorização de elevação, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8978c-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="8978c-225">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="8978c-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="8978c-226">Para negar uma solicitação de autorização de elevação, execute o seguinte comando no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8978c-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="8978c-227">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="8978c-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="8978c-228">Excluir uma política de acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="8978c-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="8978c-229">Se não for mais necessário em sua organização, você poderá excluir uma política de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="8978c-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="8978c-230">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8978c-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="8978c-231">Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8978c-232">No centro de administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8978c-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8978c-233">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8978c-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8978c-234">Selecione **Configurar políticas**.</span><span class="sxs-lookup"><span data-stu-id="8978c-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="8978c-235">Selecione a política que você deseja excluir e, em seguida, **selecione Remover Política.**</span><span class="sxs-lookup"><span data-stu-id="8978c-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="8978c-236">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8978c-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="8978c-237">No PowerShell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="8978c-238">Para excluir uma política de acesso privilegiado, execute o seguinte comando no Powershell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8978c-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="8978c-239">Desabilitar o acesso privilegiado no Office 365</span><span class="sxs-lookup"><span data-stu-id="8978c-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="8978c-240">Se necessário, você pode desabilitar o gerenciamento de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="8978c-241">Desabilitar o acesso privilegiado não exclui quaisquer políticas de aprovação ou grupos de aprovação associados.</span><span class="sxs-lookup"><span data-stu-id="8978c-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="8978c-242">No Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8978c-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="8978c-243">Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) com credenciais para uma conta de administrador em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8978c-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="8978c-244">No Centro de Administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8978c-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8978c-245">Habilita **as Aprovações necessárias para o controle de acesso** privilegiado.</span><span class="sxs-lookup"><span data-stu-id="8978c-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="8978c-246">No PowerShell de Gerenciamento do Exchange</span><span class="sxs-lookup"><span data-stu-id="8978c-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="8978c-247">Para desabilitar o acesso privilegiado, execute o seguinte comando no Powershell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8978c-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
