---
title: Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 for Enterprise
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
description: Use este guia de laboratório de teste para habilitar o gerenciamento de acesso privilegiado para o ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487583"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6c62c-103">Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="6c62c-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6c62c-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*</span><span class="sxs-lookup"><span data-stu-id="6c62c-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="6c62c-105">Este artigo descreve como configurar o gerenciamento de acesso privilegiado para aumentar a segurança no ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6c62c-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="6c62c-106">A configuração do gerenciamento de acesso privilegiado envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="6c62c-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="6c62c-107">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="6c62c-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="6c62c-108">Fase 2: configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="6c62c-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="6c62c-109">Fase 3: verificar se a aprovação é necessária para tarefas elevadas e privilegiadas</span><span class="sxs-lookup"><span data-stu-id="6c62c-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="6c62c-111">Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="6c62c-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6c62c-112">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="6c62c-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6c62c-113">Se você quiser configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6c62c-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6c62c-114">Se você deseja configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6c62c-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="6c62c-115">O teste de gerenciamento de acesso privilegiado não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6c62c-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="6c62c-116">É fornecido aqui como uma opção para que você possa testar o gerenciamento de acesso privilegiado e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="6c62c-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="6c62c-117">Fase 2: configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="6c62c-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="6c62c-118">Nesta fase, configure um grupo de aprovadores e habilite o gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6c62c-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="6c62c-119">Para obter detalhes adicionais e uma visão geral do gerenciamento de acesso privilegiado, consulte [Gerenciamento de acesso privilegiado](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6c62c-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="6c62c-120">Para configurar e usar o acesso privilegiado em sua organização, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="6c62c-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="6c62c-121">Etapa 1: criar um grupo do aprovador</span><span class="sxs-lookup"><span data-stu-id="6c62c-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="6c62c-122">Antes de começar a usar o acesso privilegiado, determine quem terá autoridade de aprovação para as solicitações de entrada para acesso a tarefas elevadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="6c62c-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="6c62c-123">Todos os usuários que fazem parte do grupo aprovadores podem aprovar as solicitações de acesso.</span><span class="sxs-lookup"><span data-stu-id="6c62c-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="6c62c-124">Para usar o acesso privilegiado, você deve criar um grupo de segurança habilitado para email no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6c62c-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="6c62c-125">Em seu ambiente de teste, nomeie o novo grupo de segurança aprovadores de acesso privilegiado e adicione o "usuário 3" que foi criado anteriormente nas etapas anteriores do guia do laboratório de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="6c62c-126">Etapa 2: habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="6c62c-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="6c62c-127">O acesso privilegiado precisa estar explicitamente ativado no Microsoft 365 com o grupo padrão aprovador e deve incluir um conjunto de contas de sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="6c62c-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="6c62c-128">Certifique-se de habilitar o acesso privilegiado em sua organização antes de iniciar a fase 3 deste guia.</span><span class="sxs-lookup"><span data-stu-id="6c62c-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="6c62c-129">Fase 3: verificar se a aprovação é necessária para tarefas elevadas e privilegiadas</span><span class="sxs-lookup"><span data-stu-id="6c62c-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="6c62c-130">Nesta fase, verifique se a política de acesso privilegiado está funcionando e se os usuários precisam de aprovação para executar tarefas elevadas e privilegiadas definidas.</span><span class="sxs-lookup"><span data-stu-id="6c62c-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="6c62c-131">Testar a capacidade de executar uma tarefa não definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="6c62c-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="6c62c-132">Primeiro, conecte-se ao PowerShell de gerenciamento do Exchange com as credenciais de um usuário configurado como administrador global no seu ambiente de teste e tente criar uma nova regra de diário.</span><span class="sxs-lookup"><span data-stu-id="6c62c-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="6c62c-133">A tarefa [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) não está definida atualmente em uma política de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6c62c-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="6c62c-134">No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="6c62c-135">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="6c62c-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="6c62c-136">Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6c62c-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="6c62c-137">Criar uma nova política de acesso privilegiado para a tarefa de New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="6c62c-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="6c62c-138">Se você ainda não tiver concluído as etapas 1 e 2 da fase 2 deste guia, certifique-se de seguir as etapas para criar um grupo do aprovador chamado "aprovadores de acesso a privilégios" para habilitar o acesso privilegiado no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="6c62c-139">Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) usando credenciais da conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="6c62c-140">No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6c62c-141">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6c62c-142">Selecione **Configurar políticas**e, em seguida, selecione **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="6c62c-143">Nos campos suspensos, selecione ou insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="6c62c-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="6c62c-144">**Tipo de política**: tarefa</span><span class="sxs-lookup"><span data-stu-id="6c62c-144">**Policy type**: Task</span></span>

    <span data-ttu-id="6c62c-145">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6c62c-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="6c62c-146">**Nome da política**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="6c62c-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="6c62c-147">**Tipo de aprovação**: manual</span><span class="sxs-lookup"><span data-stu-id="6c62c-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="6c62c-148">**Grupo de aprovação**: aprovadores de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="6c62c-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="6c62c-149">Selecione **criar**e selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="6c62c-150">Pode levar alguns minutos até que a política seja totalmente configurada e habilitada.</span><span class="sxs-lookup"><span data-stu-id="6c62c-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="6c62c-151">Certifique-se de permitir que o tempo da política seja totalmente habilitado antes de testar o requisito de aprovação na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="6c62c-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="6c62c-152">Testar requisitos de aprovação para a tarefa de New-JournalRule definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="6c62c-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="6c62c-153">No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando um usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="6c62c-154">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="6c62c-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="6c62c-155">Veja o erro "permissões insuficientes" no PowerShell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="6c62c-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="6c62c-156">Solicitar acesso para criar uma nova regra de diário usando a tarefa New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="6c62c-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="6c62c-157">Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="6c62c-158">No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6c62c-159">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6c62c-160">Selecione **nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-160">Select **New request**.</span></span> <span data-ttu-id="6c62c-161">Nos campos suspensos, selecione os valores apropriados para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="6c62c-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="6c62c-162">**Tipo de solicitação**: Task</span><span class="sxs-lookup"><span data-stu-id="6c62c-162">**Request type**: Task</span></span>

    <span data-ttu-id="6c62c-163">**Escopo da solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="6c62c-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="6c62c-164">**Solicitação de**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="6c62c-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="6c62c-165">**Duração (horas)**: 2</span><span class="sxs-lookup"><span data-stu-id="6c62c-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="6c62c-166">**Comentários**: solicitar permissão para criar uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="6c62c-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="6c62c-167">Selecione **salvar**e, em seguida, selecione **fechar**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="6c62c-168">Sua solicitação será enviada ao grupo do aprovador por email.</span><span class="sxs-lookup"><span data-stu-id="6c62c-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="6c62c-169">Aprovar solicitação de acesso privilegiado para a criação de uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="6c62c-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="6c62c-170">Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais do usuário 3 no seu ambiente de teste (membro do grupo de segurança "aprovadores de acesso privilegiado" no seu ambiente de teste).</span><span class="sxs-lookup"><span data-stu-id="6c62c-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="6c62c-171">No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="6c62c-172">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="6c62c-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="6c62c-173">Selecione a solicitação pendente e, em seguida, selecione **aprovar** para conceder acesso à conta de administrador global para criar uma nova regra de diário.</span><span class="sxs-lookup"><span data-stu-id="6c62c-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="6c62c-174">A conta de administrador global (o usuário solicitante) receberá uma confirmação de email informando que a aprovação foi concedida.</span><span class="sxs-lookup"><span data-stu-id="6c62c-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="6c62c-175">Testar a criação de uma nova regra de diário com acesso privilegiado aprovado para a tarefa de New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="6c62c-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="6c62c-176">No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="6c62c-177">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="6c62c-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="6c62c-178">Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6c62c-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="6c62c-179">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6c62c-179">Next step</span></span>

<span data-ttu-id="6c62c-180">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6c62c-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c62c-181">Confira também</span><span class="sxs-lookup"><span data-stu-id="6c62c-181">See also</span></span>

[<span data-ttu-id="6c62c-182">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6c62c-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="6c62c-183">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6c62c-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6c62c-184">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6c62c-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
