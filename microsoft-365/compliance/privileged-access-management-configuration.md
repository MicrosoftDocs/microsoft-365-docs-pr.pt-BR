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
ms.custom: Ent_Solutions
ms.assetid: ''
description: Use este tópico para saber mais sobre como configurar o gerenciamento de acesso privilegiado.
ms.openlocfilehash: 196685eda6818b399c778363ee458f6f2792a33a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626507"
---
# <a name="get-started-with-privileged-access-management"></a>Introdução ao gerenciamento de acesso privilegiado

Este tópico fornece orientações sobre como habilitar e configurar o gerenciamento de acesso privilegiado em sua organização. Você pode usar o centro de administração do Microsoft 365 ou o PowerShell de gerenciamento do Exchange para gerenciar e usar o acesso privilegiado.

## <a name="before-you-begin"></a>Antes de começar

Antes de começar a usar o gerenciamento de acesso privilegiado, você deve confirmar sua [assinatura do Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e outros Complementos. Para acessar e usar o gerenciamento de acesso privilegiado, sua organização deve ter uma das seguintes assinaturas ou Complementos:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 (ou Office 365 E3 Subscription + Enterprise Mobility e Security E3 Subscription) + o complemento de conformidade do Microsoft 365 e5
- Qualquer assinatura do Microsoft 365, do Office 365, do Exchange, do SharePoint ou do OneDrive for Business + o complemento de gerenciamento de risco do Microsoft 365 E5 Insider  
- Assinatura do Microsoft 365 a5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 a3 (ou a assinatura do Office 365 a3 + Enterprise Mobility and Security a3) + o complemento de conformidade da Microsoft a5
- Qualquer assinatura do Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive for Education + o complemento de gerenciamento de risco do Microsoft 365 a5 Insider
- Assinatura do Office 365 Enterprise E5 (versão paga ou de avaliação)
- Assinatura do Office 365 Enterprise E3 + o complemento avançado de conformidade do Office 365 (não está mais disponível para novas assinaturas, consulte observação)

Os usuários que enviam e respondem a solicitações de gerenciamento de acesso privilegiado devem receber uma das licenças acima.

>[!IMPORTANT]
>O Office 365 Advanced Compliance não é mais vendido como uma assinatura autônoma. Quando as assinaturas atuais expiram, os clientes devem fazer a transição para uma das assinaturas acima, que contêm o mesmo ou outros recursos de conformidade.

Se você não tiver um plano existente do Office 365 Enterprise E5 e quiser experimentar o gerenciamento de acesso privilegiado, [adicione o microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente do Office 365 ou [Inscreva-se para obter uma avaliação](https://www.microsoft.com/microsoft-365/enterprise) do Microsoft 365 Enterprise e5.

## <a name="enable-and-configure-privileged-access-management"></a>Habilitar e configurar o gerenciamento de acesso privilegiado

Siga estas etapas para configurar e usar o acesso privilegiado em sua organização:

- [Etapa 1: criar um grupo do aprovador](privileged-access-management-configuration.md#step1)

    Antes de começar a usar o acesso de privilégio, determine quem precisa de autoridade de aprovação para solicitações de entrada para acesso a tarefas privilegiadas e privilegiadas. Qualquer usuário que faça parte do grupo aprovadores é capaz de aprovar as solicitações de acesso. Esse grupo é habilitado pela criação de um grupo de segurança habilitado para email no Office 365.

- [Etapa 2: habilitar o acesso privilegiado](privileged-access-management-configuration.md#step2)

    O acesso privilegiado deve ser explicitamente habilitado no Office 365 com o grupo padrão aprovador, incluindo um conjunto de contas de sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.

- [Etapa 3: criar uma política de acesso](privileged-access-management-configuration.md#step3)

    A criação de uma política de aprovação permite definir os requisitos de aprovação específicos delimitados em tarefas individuais. As opções de tipo de aprovação são **auto** ou **manual**.

- [Etapa 4: enviar/aprovar solicitações de acesso privilegiado](privileged-access-management-configuration.md#step4)

    Uma vez habilitado, o acesso privilegiado requer aprovações para qualquer tarefa que tenha uma política de aprovação associada definida. Para tarefas incluídas em uma política de aprovação, os usuários devem solicitar e receber aprovação de acesso para ter as permissões necessárias para executar a tarefa.

Depois que a aprovação for concedida, o usuário solicitante poderá executar a tarefa pretendida e o acesso privilegiado autorizará e executará a tarefa em nome do usuário. A aprovação permanece válida para a duração solicitada (a duração padrão é de 4 horas), durante a qual o solicitante pode executar a tarefa pretendida várias vezes. Todas essas execuções são registradas e disponibilizadas para auditoria de segurança e conformidade. 

>[!NOTE]
>Se você quiser usar o PowerShell de gerenciamento do Exchange para habilitar e configurar o acesso privilegiado, siga as etapas em [Connect to Exchange Online PowerShell using Multifactor Authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell com suas credenciais do Office 365. Não é necessário habilitar a autenticação multifator para sua organização usar as etapas para habilitar o acesso privilegiado ao se conectar ao PowerShell do Exchange Online. A conexão com a autenticação multifator cria um token OAuth usado pelo acesso privilegiado para assinar suas solicitações.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Etapa 1: criar um grupo do aprovador

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.

2. No centro de administração, vá para **grupos** > **Adicionar um grupo**.

3. Selecione **grupo de segurança habilitado para email** e preencha os **campos nome**, endereço de **email do grupo**e **Descrição** do novo grupo.

4. Salve o grupo. Pode levar alguns minutos para que o grupo seja totalmente configurado e apareça no centro de administração do Microsoft 365.

5. Selecione o novo grupo do aprovador e selecione **Editar** para adicionar usuários ao grupo.

6. Salve o grupo.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Etapa 2: habilitar o acesso privilegiado

### <a name="in-the-microsoft-365-admin-center"></a>No centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.

2. No centro de administração, vá até **configurações > configurações > segurança &** > **acesso privilegiado**privacidade.

3. Habilite o controle **exigir aprovações para tarefas privilegiadas** .

4. Atribua o grupo do aprovador que você criou na etapa 1 como o **grupo de aprovadores padrão**.

5. **Salvar** e **fechar**.

### <a name="in-exchange-management-powershell"></a>No PowerShell de gerenciamento do Exchange

Para habilitar o acesso privilegiado e atribuir o grupo do aprovador, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Exemplo:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>O recurso de contas de sistema é disponibilizado para garantir que determinadas automaçãos em suas organizações possam trabalhar sem dependências de acesso privilegiado, no entanto, é recomendável que essas exclusões sejam excepcionais e que as permitidas sejam aprovadas e auditadas regularmente.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Etapa 3: criar uma política de acesso

Você pode criar e configurar até 30 políticas de acesso privilegiado para sua organização.

### <a name="in-the-microsoft-365-admin-center"></a>No centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.

2. No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione **Configurar políticas** e selecione **Adicionar uma política**.

5. Nos campos suspensos, selecione os valores apropriados para a sua organização:
    
    **Tipo de política**: tarefa, função ou grupo de função

    **Escopo da política**: Exchange

    **Nome da política**: selecione nas políticas disponíveis

    **Tipo de aprovação**: manual ou automática

    **Grupo de aprovação**: selecione o grupo aprovadores criado na etapa 1

6. Selecione **criar** e **fechar**. Pode levar alguns minutos até que a política seja totalmente configurada e habilitada.

### <a name="in-exchange-management-powershell"></a>No PowerShell de gerenciamento do Exchange

Para criar e definir uma política de aprovação, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Exemplo:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Etapa 4: enviar/aprovar solicitações de acesso privilegiado

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Solicitando autorização de elevação para executar tarefas privilegiadas

As solicitações de acesso privilegiado são válidas por até 24 horas após o envio da solicitação. Se não for aprovada ou negada, as solicitações expirarão e o acesso não será aprovado.

#### <a name="in-the-microsoft-365-admin-center"></a>No centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais.

2. No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione **nova solicitação**. Nos campos suspensos, selecione os valores apropriados para a sua organização:

    **Tipo de solicitação**: tarefa, função ou grupo de função

    **Escopo da solicitação**: Exchange

    **Solicitação de**: selecione nas políticas disponíveis

    **Duração (horas)**: número de horas de acesso solicitado. Não há um limite no número de horas que podem ser solicitadas.

    **Comments**: campo de texto para comentários relacionados à sua solicitação de acesso

5. Selecione **salvar** e **fechar**. Sua solicitação será enviada ao grupo do aprovador por email.

#### <a name="in-exchange-management-powershell"></a>No PowerShell de gerenciamento do Exchange

Execute o seguinte comando no PowerShell do Exchange Online para criar e enviar uma solicitação de aprovação para o grupo do aprovador:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Exemplo:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Exibir o status das solicitações de elevação

Após a criação de uma solicitação de aprovação, o status da solicitação de elevação poderá ser revisado no centro de administração ou no PowerShell de gerenciamento do Exchange usando o ID de solicitação associado.

#### <a name="in-the-microsoft-365-admin-center"></a>No centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.

2. No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione **Exibir** para filtrar solicitações enviadas por status **pendente**, **aprovado**, **negado**ou de **Lockbox do cliente** .

#### <a name="in-exchange-management-powershell"></a>No PowerShell de gerenciamento do Exchange

Execute o seguinte comando no PowerShell do Exchange Online para exibir um status de solicitação de aprovação para uma ID de solicitação específica:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Exemplo:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Aprovar uma solicitação de autorização de elevação

Quando uma solicitação de aprovação é criada, os membros do grupo de aprovadores relevantes recebem uma notificação por email e podem aprovar a solicitação associada à ID da solicitação. O solicitante é notificado sobre a aprovação da solicitação ou a negação via mensagem de email.

#### <a name="in-the-microsoft-365-admin-center"></a>No centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.

2. No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione uma solicitação listada para exibir os detalhes e executar a ação na solicitação.

5. Selecione **aprovar** para aprovar a solicitação ou selecione **negar** para negar a solicitação. As solicitações aprovadas anteriormente podem ter acesso revogado ao selecionar **revogar**.

#### <a name="in-exchange-management-powershell"></a>No PowerShell de gerenciamento do Exchange

Para aprovar uma solicitação de autorização de elevação, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Exemplo:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Para negar uma solicitação de autorização de elevação, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Exemplo:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Excluir uma política de acesso privilegiada no Office 365

Se ele não for mais necessário em sua organização, você poderá excluir uma política de acesso privilegiado.

### <a name="in-the-microsoft-365-admin-center"></a>No centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de uma conta de administrador em sua organização.

2. No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione **Configurar políticas**.

5. Selecione a política que você deseja excluir e, em seguida, selecione **remover política**.

6. Selecione **Fechar**.

### <a name="in-exchange-management-powershell"></a>No PowerShell de gerenciamento do Exchange

Para excluir uma política de acesso privilegiada, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Desabilitar o acesso privilegiado no Office 365

Se necessário, você pode desabilitar o gerenciamento de acesso privilegiado para sua organização. Desabilitar o acesso privilegiado não exclui nenhuma política de aprovação associada ou grupos de aprovadores.

### <a name="in-the-microsoft-365-admin-center"></a>No centro de administração do Microsoft 365

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) com as credenciais de uma conta de administrador em sua organização.

2. No centro de administração, vá até **configurações** > de**segurança & privacidade** > **privilegiada**.

3. Habilitar as **aprovações de controle de acesso privilegiado** .

### <a name="in-exchange-management-powershell"></a>No PowerShell de gerenciamento do Exchange

Para desabilitar o acesso privilegiado, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Disable-ElevatedAccessControl
```
