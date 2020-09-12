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
ms.openlocfilehash: d8d92aa86076e323e4b5bb5c8eb1385edcac420c
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545937"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d1ff7-103">Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="d1ff7-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d1ff7-104">*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*</span><span class="sxs-lookup"><span data-stu-id="d1ff7-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="d1ff7-105">Com as instruções deste artigo, você configura o gerenciamento de acesso privilegiado para aumentar a segurança no ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

>[!TIP]
><span data-ttu-id="d1ff7-107">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d1ff7-108">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="d1ff7-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d1ff7-109">Se você só quiser configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d1ff7-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d1ff7-110">Se você deseja configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d1ff7-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="d1ff7-111">O teste de gerenciamento de acesso privilegiado não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="d1ff7-112">Ele é fornecido aqui como uma opção para que você possa testar o gerenciamento de acesso privilegiado e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="d1ff7-113">Fase 2: configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="d1ff7-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="d1ff7-114">Nesta fase, configure um grupo de aprovadores e habilite o gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="d1ff7-115">Para obter detalhes adicionais e uma visão geral do gerenciamento de acesso privilegiado, consulte [Gerenciamento de acesso privilegiado](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d1ff7-115">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="d1ff7-116">Siga estas etapas para configurar e usar o acesso privilegiado em sua organização:</span><span class="sxs-lookup"><span data-stu-id="d1ff7-116">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="d1ff7-117">Etapa 1: criar um grupo do aprovador</span><span class="sxs-lookup"><span data-stu-id="d1ff7-117">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

    <span data-ttu-id="d1ff7-118">Antes de começar a usar o acesso de privilégio, determine quem terá autoridade de aprovação para solicitações de entrada para acesso a tarefas privilegiadas e privilegiadas.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="d1ff7-119">Qualquer usuário que faça parte do grupo aprovadores poderá aprovar as solicitações de acesso.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="d1ff7-120">Isso é habilitado através da criação de um grupo de segurança habilitado para email no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-120">This is enabled by creating a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="d1ff7-121">Crie um novo grupo de segurança chamado "aprovadores de acesso privilegiado" em seu ambiente de teste e adicione o "usuário 3" criado anteriormente nas etapas anteriores do guia do laboratório de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="d1ff7-122">Etapa 2: habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="d1ff7-122">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

    <span data-ttu-id="d1ff7-123">O acesso privilegiado precisa estar explicitamente ativado no Microsoft 365 com o grupo de aprovadores padrão e incluir um conjunto de contas de sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-123">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="d1ff7-124">Certifique-se de habilitar o acesso privilegiado em sua organização antes de iniciar a fase 3 deste guia.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-124">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="d1ff7-125">Fase 3: verificar se a aprovação é necessária para tarefas elevadas e privilegiadas</span><span class="sxs-lookup"><span data-stu-id="d1ff7-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="d1ff7-126">Nesta fase, verifique se a política de acesso privilegiado está funcionando e se os usuários exigem aprovação para executar tarefas privilegiadas e privilegiadas definidas.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="d1ff7-127">Testar a capacidade de executar uma tarefa não definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="d1ff7-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="d1ff7-128">Primeiro, conecte-se ao PowerShell de gerenciamento do Exchange com as credenciais de um usuário configurado como administrador global no seu ambiente de teste e tente criar uma nova regra de diário.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="d1ff7-129">A tarefa [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) não está definida atualmente em uma política de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="d1ff7-130">No computador local, abra e entre no módulo PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d1ff7-131">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="d1ff7-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="d1ff7-132">Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="d1ff7-133">Criar uma nova política de acesso privilegiado para a tarefa New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="d1ff7-133">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="d1ff7-134">Se você ainda não tiver concluído as etapas 1 e 2 da fase 2 deste guia, certifique-se de seguir as etapas para criar um grupo do aprovador chamado "aprovadores de acesso a privilégios" e para habilitar o acesso privilegiado em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="d1ff7-135">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais da conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d1ff7-136">No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d1ff7-137">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d1ff7-138">Selecione **Configurar políticas** e selecione **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="d1ff7-139">Nos campos suspensos, selecione ou insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="d1ff7-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="d1ff7-140">**Tipo de política**: tarefa</span><span class="sxs-lookup"><span data-stu-id="d1ff7-140">**Policy type**: Task</span></span>

    <span data-ttu-id="d1ff7-141">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="d1ff7-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="d1ff7-142">**Nome da política**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="d1ff7-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="d1ff7-143">**Tipo de aprovação**: manual</span><span class="sxs-lookup"><span data-stu-id="d1ff7-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="d1ff7-144">**Grupo de aprovação**: aprovadores de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="d1ff7-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="d1ff7-145">Selecione **criar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="d1ff7-146">Pode levar alguns minutos até que a política seja totalmente configurada e habilitada.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="d1ff7-147">Certifique-se de permitir que o tempo da política seja totalmente habilitado antes de testar o requisito de aprovação na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="d1ff7-148">Testar requisitos de aprovação para a tarefa New-JournalRule definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="d1ff7-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="d1ff7-149">No computador local, abra e entre no módulo PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando uma conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d1ff7-150">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="d1ff7-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="d1ff7-151">Exibir o erro "permissões insuficientes" no PowerShell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="d1ff7-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="d1ff7-152">Solicitar acesso para criar uma nova regra de diário usando a tarefa New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="d1ff7-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="d1ff7-153">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d1ff7-154">No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d1ff7-155">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d1ff7-156">Selecione **nova solicitação**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-156">Select **New request**.</span></span> <span data-ttu-id="d1ff7-157">Nos campos suspensos, selecione os valores apropriados para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="d1ff7-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="d1ff7-158">**Tipo de solicitação**: Task</span><span class="sxs-lookup"><span data-stu-id="d1ff7-158">**Request type**: Task</span></span>

    <span data-ttu-id="d1ff7-159">**Escopo da solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="d1ff7-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="d1ff7-160">**Solicitação de**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="d1ff7-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="d1ff7-161">**Duração (horas)**: 2</span><span class="sxs-lookup"><span data-stu-id="d1ff7-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="d1ff7-162">**Comentários**: solicitar permissão para criar uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="d1ff7-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="d1ff7-163">Selecione **salvar** e **fechar**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="d1ff7-164">Sua solicitação será enviada ao grupo do aprovador por email.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="d1ff7-165">Aprovar solicitação de acesso privilegiado para a criação de uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="d1ff7-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="d1ff7-166">Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais do usuário 3 no seu ambiente de teste (membro do grupo de segurança "aprovadores de acesso privilegiado" no seu ambiente de teste).</span><span class="sxs-lookup"><span data-stu-id="d1ff7-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="d1ff7-167">No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d1ff7-168">Selecione **gerenciar políticas e solicitações de acesso**.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d1ff7-169">Selecione a solicitação pendente e selecione **aprovar** para conceder acesso à conta de administrador global para criar uma nova regra de diário.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="d1ff7-170">Um email de notificação confirmando que a aprovação foi concedida será enviado para a conta de administrador global (o usuário solicitante).</span><span class="sxs-lookup"><span data-stu-id="d1ff7-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="d1ff7-171">Testar a criação de uma nova regra de diário com acesso privilegiado aprovado para a tarefa New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="d1ff7-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="d1ff7-172">No computador local, abra e entre no módulo PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="d1ff7-173">No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="d1ff7-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="d1ff7-174">Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="d1ff7-175">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d1ff7-175">Next step</span></span>

<span data-ttu-id="d1ff7-176">Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d1ff7-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1ff7-177">Confira também</span><span class="sxs-lookup"><span data-stu-id="d1ff7-177">See also</span></span>

[<span data-ttu-id="d1ff7-178">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d1ff7-178">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d1ff7-179">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d1ff7-179">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d1ff7-180">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d1ff7-180">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
