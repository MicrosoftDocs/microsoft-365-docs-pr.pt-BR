---
title: Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Use este guia de laboratório de teste para habilitar o gerenciamento de acesso privilegiado seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864687"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a1516-103">Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1516-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a1516-104">Com as instruções deste artigo, você configura o gerenciamento de acesso privilegiado para aumentar a segurança em seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a1516-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="a1516-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a1516-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="a1516-107">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1516-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="a1516-108">Se você deseja configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="a1516-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a1516-109">Se você deseja configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a1516-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a1516-p101">Testar o gerenciamento de acesso privilegiado não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar privilegiado gerenciamento de acesso e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="a1516-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="a1516-112">Fase 2: Configurar o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="a1516-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="a1516-p102">Nesta fase, você pode configurar um grupo de aprovadores e habilitar o gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise. Para obter detalhes adicionais e uma visão geral dos privilégios gerenciamento de acesso, consulte [gerenciamento de acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="a1516-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="a1516-115">Siga estas etapas para configurar e usar o acesso privilegiado em sua organização do Office 365:</span><span class="sxs-lookup"><span data-stu-id="a1516-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="a1516-116">Etapa 1: Criar um grupo do aprovador</span><span class="sxs-lookup"><span data-stu-id="a1516-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="a1516-p103">Antes de começar a usar o acesso de privilégio, determine quem terá autoridade de aprovação para solicitações de entrada para acesso a tarefas com privilégios elevados e privilegiados. Qualquer usuário que faz parte do grupo dos aprovadores poderão aprovar solicitações de acesso. Esta opção estiver ativada, criando um grupo de segurança habilitados para email no Office 365. Criar um novo grupo de segurança chamado "Privilegiado acesso aprovadores" em seu ambiente de teste e adicionar o "usuário 3", anteriormente criada nas etapas de guia de laboratório de teste anterior.</span><span class="sxs-lookup"><span data-stu-id="a1516-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="a1516-121">Etapa 2: Habilitar o acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="a1516-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="a1516-p104">Acesso privilegiado deve ser explicitamente ativado no Office 365 com o grupo de aprovador padrão e incluindo um conjunto de contas de sistema que deseja sejam excluídos do controle de acesso de gerenciamento de acesso privilegiado. Certifique-se de habilitar o acesso privilegiado em sua organização do Office 365 antes de iniciar a fase 3 deste guia.</span><span class="sxs-lookup"><span data-stu-id="a1516-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="a1516-124">Fase 3: Verificar se é necessário obter aprovação tarefas com privilégios elevados e privilegiadas</span><span class="sxs-lookup"><span data-stu-id="a1516-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="a1516-125">Nesta fase, verifique se a política de acesso privilegiado está funcionando e usuários exigem aprovação para executar tarefas de elevado e privilegiadas definidas.</span><span class="sxs-lookup"><span data-stu-id="a1516-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="a1516-126">Testar a capacidade de executar uma tarefa não definida em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="a1516-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="a1516-p105">Primeiro, conecte-se ao PowerShell de gerenciamento do Exchange com as credenciais de um usuário configurado como um Administrador Global no seu ambiente de teste e tentar criar uma nova regra de diário. A tarefa de [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) atualmente não está definida em uma política de acesso privilegiado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a1516-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="a1516-129">No computador local, abra e entrar no o Exchange Online PowerShell módulo remoto na **Microsoft Corporation** > **Microsoft Exchange Online PowerShell módulo remoto** usando o Administrador Global da conta para o seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a1516-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a1516-130">No Powershell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="a1516-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="a1516-131">Modo de exibição se a nova regra de diário foi criada com êxito no Exchange PowerShell de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a1516-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="a1516-132">Criar uma nova política de acesso privilegiado para a tarefa de New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="a1516-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="a1516-133">Se você já não tiver concluído as etapas 1 e 2 da fase 2 deste guia, ser-se de seguir as etapas para criar o grupo do aprovador chamado "Privilégio acesso aprovadores" e habilitar o acesso privilegiado em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a1516-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="a1516-134">Entrar no [Centro de administração do Microsoft 365](https://portal.office.com) usando credenciais a conta de Administrador Global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a1516-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a1516-135">No Centro de administração, vá para **configurações** > **de segurança e privacidade** > **acesso privilegiado**.</span><span class="sxs-lookup"><span data-stu-id="a1516-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a1516-136">Selecione **solicitações e gerenciar políticas de acesso**.</span><span class="sxs-lookup"><span data-stu-id="a1516-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a1516-137">Selecione **Configurar políticas** e **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="a1516-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="a1516-138">Nos campos de lista suspensa, selecione ou insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="a1516-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="a1516-139">**Tipo de política**: tarefa</span><span class="sxs-lookup"><span data-stu-id="a1516-139">**Policy type**: Task</span></span>

    <span data-ttu-id="a1516-140">**Escopo da política**: Exchange</span><span class="sxs-lookup"><span data-stu-id="a1516-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="a1516-141">**Nome da política**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="a1516-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="a1516-142">**Tipo de aprovação**: Manual</span><span class="sxs-lookup"><span data-stu-id="a1516-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="a1516-143">**Grupo de aprovação**: aprovadores com privilégios de acesso</span><span class="sxs-lookup"><span data-stu-id="a1516-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="a1516-p106">Selecione **criar** e em seguida **Fechar**. Pode levar alguns minutos para a diretiva a ser totalmente configurada e habilitada. Certifique-se de Reserve algum tempo para a política a ser habilitada totalmente antes de testar a exigência de aprovação na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="a1516-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="a1516-147">Requisito de aprovação de teste para a tarefa de New-JournalRule definido em uma política de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="a1516-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="a1516-148">No computador local, abra e entrar no o Exchange Online PowerShell módulo remoto na **Microsoft Corporation** > para seu teste de conta do**Microsoft Exchange Online PowerShell módulo remoto** usando um usando o Administrador Global ambiente.</span><span class="sxs-lookup"><span data-stu-id="a1516-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a1516-149">No Powershell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="a1516-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="a1516-150">Exibir o erro "Insuficiente permissões" no PowerShell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="a1516-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="a1516-151">Solicitação de acesso para criar uma nova regra de diário usando a tarefa de New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="a1516-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="a1516-152">Entrar no [Centro de administração do Microsoft 365](https://portal.office.com) usando a conta de Administrador Global para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a1516-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a1516-153">No Centro de administração, vá para **configurações** > **de segurança e privacidade** > **acesso privilegiado**.</span><span class="sxs-lookup"><span data-stu-id="a1516-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a1516-154">Selecione **solicitações e gerenciar políticas de acesso**.</span><span class="sxs-lookup"><span data-stu-id="a1516-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a1516-p107">Selecione **nova solicitação**. Nos campos de lista suspensa, selecione os valores apropriados para sua organização:</span><span class="sxs-lookup"><span data-stu-id="a1516-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="a1516-157">**Tipo de solicitação**: tarefa</span><span class="sxs-lookup"><span data-stu-id="a1516-157">**Request type**: Task</span></span>

    <span data-ttu-id="a1516-158">**Escopo de solicitação**: Exchange</span><span class="sxs-lookup"><span data-stu-id="a1516-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="a1516-159">**Solicitar para**: nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="a1516-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="a1516-160">**Duração (horas)**: 2</span><span class="sxs-lookup"><span data-stu-id="a1516-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="a1516-161">**Comentários**: solicitar permissão para criar uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="a1516-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="a1516-p108">Selecione **Salvar** e **Fechar**. Sua solicitação será enviada ao grupo do aprovador via email.</span><span class="sxs-lookup"><span data-stu-id="a1516-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="a1516-164">Aprovar solicitações de acesso privilegiado para a criação de uma nova regra de diário</span><span class="sxs-lookup"><span data-stu-id="a1516-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="a1516-165">Entrar no [Centro de administração do Microsoft 365](https://portal.office.com) utilizando as credenciais para o usuário 3 em seu ambiente de teste (membro do grupo de segurança "Privilegiado acesso aprovadores" em seu ambiente de teste).</span><span class="sxs-lookup"><span data-stu-id="a1516-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="a1516-166">No Centro de administração, vá para **configurações** > **de segurança e privacidade** > **acesso privilegiado**.</span><span class="sxs-lookup"><span data-stu-id="a1516-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a1516-167">Selecione **solicitações e gerenciar políticas de acesso**.</span><span class="sxs-lookup"><span data-stu-id="a1516-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a1516-p109">Selecione a solicitação pendente e **Approve** para conceder acesso à conta de Administrador Global para criar uma nova regra de diário. Um email de notificação confirmando que a aprovação tenha sido concedida será enviado para a conta de Administrador Global (o usuário solicitante).</span><span class="sxs-lookup"><span data-stu-id="a1516-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="a1516-170">Criar uma nova regra de diário com acesso privilegiado aprovado para a tarefa de New-JournalRule de teste</span><span class="sxs-lookup"><span data-stu-id="a1516-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="a1516-171">No computador local, abra e entrar no o Exchange Online PowerShell módulo remoto na **Microsoft Corporation** > **Microsoft Exchange Online PowerShell módulo remoto** usando o Administrador Global da conta para o seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a1516-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="a1516-172">No Powershell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:</span><span class="sxs-lookup"><span data-stu-id="a1516-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="a1516-173">Modo de exibição se a nova regra de diário foi criada com êxito no Exchange PowerShell de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a1516-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="a1516-174">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a1516-174">Next step</span></span>

<span data-ttu-id="a1516-175">Explore recursos adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) e recursos no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a1516-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1516-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1516-176">See also</span></span>

[<span data-ttu-id="a1516-177">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1516-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a1516-178">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1516-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="a1516-179">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a1516-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)