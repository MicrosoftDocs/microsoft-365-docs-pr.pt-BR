---
title: Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise
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
description: Use este guia de laboratório de teste para habilitar o gerenciamento de acesso privilegiado do ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 68d542b3f97022abc65b94162f333e7059f614a8
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673337"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ae734-103">Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae734-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ae734-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 Enterprise e do Office 365.*</span><span class="sxs-lookup"><span data-stu-id="ae734-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ae734-105">Com as instruções deste artigo, você configura o gerenciamento de acesso privilegiado para aumentar a segurança no seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ae734-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ae734-107">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ae734-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ae734-108">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae734-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ae734-109">Se você só quiser configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ae734-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ae734-110">Se você deseja configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ae734-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae734-111">O teste de gerenciamento de acesso privilegiado não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS.</span><span class="sxs-lookup"><span data-stu-id="ae734-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="ae734-112">Ele é fornecido aqui como uma opção para que você possa testar o gerenciamento de acesso privilegiado e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="ae734-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="ae734-113">Fase 2: configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="ae734-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="ae734-114">Nesta fase, configure um grupo de aprovadores e habilite o gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ae734-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="ae734-115">Para obter detalhes adicionais e uma visão geral do gerenciamento de acesso privilegiado, consulte [Gerenciamento de acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="ae734-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="ae734-116">Siga estas etapas para configurar e usar o acesso privilegiado na sua organização do Office 365:</span><span class="sxs-lookup"><span data-stu-id="ae734-116">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="ae734-117">Etapa 1: criar um grupo do aprovador</span><span class="sxs-lookup"><span data-stu-id="ae734-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="ae734-118">Antes de começar a usar o acesso de privilégio, determine quem terá autoridade de aprovação para solicitações de entrada para acesso a tarefas privilegiadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="ae734-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="ae734-119">Qualquer usuário que faça parte do grupo aprovadores poderá aprovar as solicitações de acesso.</span><span class="sxs-lookup"><span data-stu-id="ae734-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="ae734-120">Isso é habilitado através da criação de um grupo de segurança habilitado para email no Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae734-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="ae734-121">Crie um novo grupo de segurança chamado "aprovadores de acesso privilegiado" em seu ambiente de teste e adicione o "usuário 3" criado anteriormente nas etapas anteriores do guia do laboratório de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="ae734-122">Etapa 2: habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="ae734-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="ae734-123">O acesso privilegiado precisa estar explicitamente ativado no Office 365 com o grupo de aprovadores padrão e incluir um conjunto de contas de sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="ae734-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="ae734-124">Certifique-se de habilitar o acesso privilegiado em sua organização do Office 365 antes de iniciar a fase 3 deste guia.</span><span class="sxs-lookup"><span data-stu-id="ae734-124">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="ae734-125">Fase 3: verificar se a aprovação é necessária para tarefas elevadas e privilegiadas</span><span class="sxs-lookup"><span data-stu-id="ae734-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="ae734-126">Nesta fase, verifique se a política de acesso privilegiado está funcionando e se os usuários exigem aprovação para executar tarefas privilegiadas e privilegiadas definidas.</span><span class="sxs-lookup"><span data-stu-id="ae734-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ae734-127">Testar a capacidade de executar uma tarefa não definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="ae734-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="ae734-128">Primeiro, conecte-se ao PowerShell de gerenciamento do Exchange com as credenciais de um usuário configurado como administrador global no seu ambiente de teste e tente criar uma nova regra de diário.</span><span class="sxs-lookup"><span data-stu-id="ae734-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="ae734-129">A tarefa [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) não está definida atualmente em uma política de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="ae734-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="ae734-130">No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation** > **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-130">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ae734-131">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="ae734-131">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="ae734-132">Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ae734-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="ae734-133">Criar uma nova política de acesso privilegiado para a tarefa New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="ae734-133">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="ae734-134">Se você ainda não tiver concluído as etapas 1 e 2 da fase 2 deste guia, certifique-se de seguir as etapas para criar um grupo do aprovador chamado "aprovadores de acesso a privilégios" e para habilitar o acesso privilegiado em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="ae734-135">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais da conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ae734-136">No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="ae734-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ae734-137">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="ae734-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ae734-138">Selecione **Configurar políticas** e selecione **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="ae734-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="ae734-139">Nos campos suspensos, selecione ou insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae734-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="ae734-140">**Tipo de política**: tarefa</span><span class="sxs-lookup"><span data-stu-id="ae734-140">**Policy type**: Task</span></span>

    <span data-ttu-id="ae734-141">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="ae734-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="ae734-142">**Nome da política**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="ae734-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="ae734-143">**Tipo de aprovação**: manual</span><span class="sxs-lookup"><span data-stu-id="ae734-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="ae734-144">**Grupo de aprovação**: aprovadores de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="ae734-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="ae734-145">Selecione **criar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="ae734-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="ae734-146">Pode levar alguns minutos até que a política seja totalmente configurada e habilitada.</span><span class="sxs-lookup"><span data-stu-id="ae734-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="ae734-147">Certifique-se de permitir que o tempo da política seja totalmente habilitado antes de testar o requisito de aprovação na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ae734-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="ae734-148">Testar requisitos de aprovação para a tarefa New-JournalRule definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="ae734-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="ae734-149">No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation** > **Microsoft Exchange Online PowerShell** usando uma conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-149">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ae734-150">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="ae734-150">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="ae734-151">Exibir o erro "permissões de Insuffient" no PowerShell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="ae734-151">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="ae734-152">Solicitar acesso para criar uma nova regra de diário usando a tarefa New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="ae734-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="ae734-153">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ae734-154">No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="ae734-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ae734-155">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="ae734-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ae734-156">Selecione **nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="ae734-156">Select **New request**.</span></span> <span data-ttu-id="ae734-157">Nos campos suspensos, selecione os valores apropriados para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="ae734-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="ae734-158">**Tipo de solicitação**: Task</span><span class="sxs-lookup"><span data-stu-id="ae734-158">**Request type**: Task</span></span>

    <span data-ttu-id="ae734-159">**Escopo da solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="ae734-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="ae734-160">**Solicitação de**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="ae734-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="ae734-161">**Duração (horas)**: 2</span><span class="sxs-lookup"><span data-stu-id="ae734-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="ae734-162">**Comentários**: solicitar permissão para criar uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="ae734-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="ae734-163">Selecione **salvar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="ae734-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="ae734-164">Sua solicitação será enviada ao grupo do aprovador por email.</span><span class="sxs-lookup"><span data-stu-id="ae734-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="ae734-165">Aprovar solicitação de acesso privilegiado para a criação de uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="ae734-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="ae734-166">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais do usuário 3 no seu ambiente de teste (membro do grupo de segurança "aprovadores de acesso privilegiado" no seu ambiente de teste).</span><span class="sxs-lookup"><span data-stu-id="ae734-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="ae734-167">No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="ae734-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="ae734-168">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="ae734-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="ae734-169">Selecione a solicitação pendente e selecione **aprovar** para conceder acesso à conta de administrador global para criar uma nova regra de diário.</span><span class="sxs-lookup"><span data-stu-id="ae734-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="ae734-170">Um email de notificação confirmando que a aprovação foi concedida será enviado para a conta de administrador global (o usuário solicitante).</span><span class="sxs-lookup"><span data-stu-id="ae734-170">An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="ae734-171">Testar a criação de uma nova regra de diário com acesso privilegiado aprovado para a tarefa New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="ae734-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="ae734-172">No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation** > **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-172">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="ae734-173">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="ae734-173">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="ae734-174">Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="ae734-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae734-175">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ae734-175">Next step</span></span>

<span data-ttu-id="ae734-176">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ae734-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae734-177">Confira também</span><span class="sxs-lookup"><span data-stu-id="ae734-177">See also</span></span>

[<span data-ttu-id="ae734-178">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae734-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ae734-179">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae734-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ae734-180">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ae734-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)