---
title: Gerenciamento de acesso privilegiado para seu Microsoft 365 para ambiente de teste empresarial
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Use este Guia de Laboratório de Teste para habilitar o gerenciamento de acesso privilegiado Microsoft 365 ambiente de teste empresarial.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126412"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8a540-103">Gerenciamento de acesso privilegiado para seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="8a540-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8a540-104">*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*</span><span class="sxs-lookup"><span data-stu-id="8a540-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8a540-105">Este artigo descreve como configurar o gerenciamento de acesso privilegiado para aumentar a segurança em seu Microsoft 365 ambiente de teste empresarial.</span><span class="sxs-lookup"><span data-stu-id="8a540-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="8a540-106">A configuração do gerenciamento de acesso privado envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="8a540-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="8a540-107">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="8a540-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="8a540-108">Fase 2: Configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8a540-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="8a540-109">Fase 3: Verificar se a aprovação é necessária para tarefas elevadas e privilegiadas</span><span class="sxs-lookup"><span data-stu-id="8a540-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="8a540-111">Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="8a540-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="8a540-112">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="8a540-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="8a540-113">Se você quiser configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="8a540-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="8a540-114">Se você quiser configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8a540-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="8a540-115">Testar o gerenciamento de acesso privilegiado não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8a540-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="8a540-116">Ele é fornecido aqui como uma opção para que você possa testar o gerenciamento de acesso privilegiado e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="8a540-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="8a540-117">Fase 2: Configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8a540-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="8a540-118">Nesta fase, configure um grupo de aprovadores e habilita o gerenciamento de acesso privilegiado para seu Microsoft 365 ambiente de teste empresarial.</span><span class="sxs-lookup"><span data-stu-id="8a540-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="8a540-119">Para obter detalhes adicionais e uma visão geral do gerenciamento de acesso privilegiado, consulte [Privileged access management](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8a540-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="8a540-120">Para configurar e usar o acesso privilegiado em sua organização, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="8a540-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="8a540-121">Etapa 1: Criar um grupo de aprovação</span><span class="sxs-lookup"><span data-stu-id="8a540-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="8a540-122">Antes de começar a usar o acesso privilegiado, determine quem terá autoridade de aprovação para solicitações de entrada para acesso a tarefas elevadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="8a540-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="8a540-123">Todos os usuários que fazem parte do grupo aprovadores podem aprovar solicitações de acesso.</span><span class="sxs-lookup"><span data-stu-id="8a540-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="8a540-124">Para usar o acesso privilegiado, você deve criar um grupo de segurança habilitado para email Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a540-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="8a540-125">Em seu ambiente de teste, nomee o novo grupo de segurança "Aprovadores de Acesso Privilegiado" e adicione o "Usuário 3" que foi criado anteriormente nas etapas anteriores do laboratório de teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="8a540-126">Etapa 2: Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8a540-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="8a540-127">O acesso privilegiado precisa ser explicitamente Microsoft 365 com o grupo aprovador padrão e deve incluir um conjunto de contas do sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="8a540-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="8a540-128">Certifique-se de habilitar o acesso privilegiado em sua organização antes de iniciar a Fase 3 deste guia.</span><span class="sxs-lookup"><span data-stu-id="8a540-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="8a540-129">Fase 3: Verificar se a aprovação é necessária para tarefas elevadas e privilegiadas</span><span class="sxs-lookup"><span data-stu-id="8a540-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="8a540-130">Nesta fase, verifique se a política de acesso privilegiado está funcionando e se os usuários exigem aprovação para executar tarefas definidas elevadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="8a540-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="8a540-131">Testar a capacidade de executar uma tarefa NÃO definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8a540-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="8a540-132">Primeiro, conecte-se ao Exchange Do PowerShell de Gerenciamento com as credenciais de um usuário configurado como Administrador Global em seu ambiente de teste e tente criar uma nova regra de Diário.</span><span class="sxs-lookup"><span data-stu-id="8a540-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="8a540-133">A [tarefa New-JournalRule](/powershell/module/exchange/new-journalrule) não está definida atualmente em uma política de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="8a540-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="8a540-134">Em seu computador local, abra e entre no módulo Exchange Online PowerShell Remoto da **Microsoft Corporation** Microsoft Exchange Online Módulo Do PowerShell Remoto usando a conta Administrador Global para seu ambiente de  >   teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="8a540-135">No Exchange PowerShell de Gerenciamento, crie uma nova regra de Diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="8a540-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="8a540-136">Veja que a nova Regra de Diário foi criada com êxito no Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a540-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="8a540-137">Criar uma nova política de acesso privilegiado para New-JournalRule tarefa</span><span class="sxs-lookup"><span data-stu-id="8a540-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="8a540-138">Se você ainda não concluiu as Etapas 1 e 2 da Fase 2 deste guia, siga as etapas para criar um grupo de aprovadores chamado "Aprovadores de Acesso para Privilégios" para habilitar o acesso privilegiado em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="8a540-139">Entre no centro de administração [Microsoft 365 usando](https://admin.microsoft.com) credenciais da conta administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="8a540-140">No Centro de Administração, vá **para** Configurações  >  **Segurança & Acesso Privilegiado**  >  **de Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8a540-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8a540-141">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8a540-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8a540-142">Selecione **Configurar políticas** e, em seguida, selecione Adicionar uma **política**.</span><span class="sxs-lookup"><span data-stu-id="8a540-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="8a540-143">Nos campos drop-down, selecione ou insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="8a540-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="8a540-144">**Tipo de política**: Tarefa</span><span class="sxs-lookup"><span data-stu-id="8a540-144">**Policy type**: Task</span></span>

    <span data-ttu-id="8a540-145">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="8a540-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="8a540-146">**Nome da política**: Nova Regra de Diário</span><span class="sxs-lookup"><span data-stu-id="8a540-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="8a540-147">**Tipo de aprovação**: Manual</span><span class="sxs-lookup"><span data-stu-id="8a540-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="8a540-148">**Grupo de aprovação**: Aprovadores de Acesso Privilegiado</span><span class="sxs-lookup"><span data-stu-id="8a540-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="8a540-149">Selecione **Criar** e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8a540-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="8a540-150">Pode levar alguns minutos para que a política seja totalmente configurada e habilitada.</span><span class="sxs-lookup"><span data-stu-id="8a540-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="8a540-151">Certifique-se de permitir que o tempo para a política seja totalmente habilitado antes de testar o requisito de aprovação na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="8a540-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="8a540-152">Requisito de aprovação de teste para a tarefa New-JournalRule definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="8a540-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="8a540-153">Em seu computador local, abra e entre no módulo Exchange Online PowerShell Remoto da **Microsoft Corporation** Microsoft Exchange Online Módulo Do PowerShell Remoto usando uma conta de Administrador Global para seu ambiente de  >   teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="8a540-154">No Exchange PowerShell de Gerenciamento, crie uma nova regra de Diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="8a540-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="8a540-155">Exibir o erro "Permissões insuficientes" no Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8a540-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="8a540-156">Solicitar acesso para criar uma nova Regra de Diário usando New-JournalRule tarefa</span><span class="sxs-lookup"><span data-stu-id="8a540-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="8a540-157">Entre no centro de administração [Microsoft 365 usando a](https://admin.microsoft.com) conta Administrador Global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="8a540-158">No Centro de Administração, vá **para** Configurações  >  **Segurança & Acesso Privilegiado**  >  **de Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8a540-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8a540-159">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8a540-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8a540-160">Selecione **Nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="8a540-160">Select **New request**.</span></span> <span data-ttu-id="8a540-161">Nos campos drop-down, selecione os valores apropriados para sua organização:</span><span class="sxs-lookup"><span data-stu-id="8a540-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="8a540-162">**Tipo de solicitação**: Tarefa</span><span class="sxs-lookup"><span data-stu-id="8a540-162">**Request type**: Task</span></span>

    <span data-ttu-id="8a540-163">**Escopo da solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="8a540-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="8a540-164">**Solicitação para**: Nova Regra de Diário</span><span class="sxs-lookup"><span data-stu-id="8a540-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="8a540-165">**Duração (horas)**: 2</span><span class="sxs-lookup"><span data-stu-id="8a540-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="8a540-166">**Comentários**: Solicitar permissão para criar uma nova Regra de Diário</span><span class="sxs-lookup"><span data-stu-id="8a540-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="8a540-167">Selecione **Salvar** e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="8a540-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="8a540-168">Sua solicitação será enviada para o grupo do aprovador por email.</span><span class="sxs-lookup"><span data-stu-id="8a540-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="8a540-169">Aprovar solicitação de acesso privilegiado para a criação de uma nova Regra de Diário</span><span class="sxs-lookup"><span data-stu-id="8a540-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="8a540-170">Entre no [](https://admin.microsoft.com) centro de administração Microsoft 365 usando as credenciais do Usuário 3 em seu ambiente de teste (membro do grupo de segurança "Aprovadores de Acesso Privilegiado" em seu ambiente de teste).</span><span class="sxs-lookup"><span data-stu-id="8a540-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="8a540-171">No Centro de Administração, vá **para** Configurações  >  **Segurança & Acesso Privilegiado**  >  **de Privacidade.**</span><span class="sxs-lookup"><span data-stu-id="8a540-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="8a540-172">Selecione **Gerenciar políticas e solicitações de acesso.**</span><span class="sxs-lookup"><span data-stu-id="8a540-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="8a540-173">Selecione a solicitação pendente e selecione **Aprovar** para conceder acesso à conta administrador global para criar uma nova Regra de Diário.</span><span class="sxs-lookup"><span data-stu-id="8a540-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="8a540-174">A conta administrador global (o usuário solicitando) receberá uma confirmação por email de que a aprovação foi concedida.</span><span class="sxs-lookup"><span data-stu-id="8a540-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="8a540-175">Testar a criação de uma nova Regra de Diário com acesso privilegiado aprovado para a tarefa New-JournalRule de usuário</span><span class="sxs-lookup"><span data-stu-id="8a540-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="8a540-176">Em seu computador local, abra e entre no módulo Exchange Online PowerShell Remoto da **Microsoft Corporation** Microsoft Exchange Online Módulo Do PowerShell Remoto usando a conta Administrador Global para seu ambiente de  >   teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="8a540-177">No Exchange PowerShell de Gerenciamento, crie uma nova regra de Diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="8a540-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="8a540-178">Veja que a nova Regra de Diário foi criada com êxito no Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8a540-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="8a540-179">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="8a540-179">Next step</span></span>

<span data-ttu-id="8a540-180">Explore recursos [e recursos adicionais de proteção](m365-enterprise-test-lab-guides.md#information-protection) de informações em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="8a540-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a540-181">Confira também</span><span class="sxs-lookup"><span data-stu-id="8a540-181">See also</span></span>

[<span data-ttu-id="8a540-182">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8a540-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="8a540-183">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8a540-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8a540-184">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8a540-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
