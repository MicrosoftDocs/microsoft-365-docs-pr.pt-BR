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
# <a name="get-started-with-privileged-access-management"></a>Introdução ao gerenciamento de acesso privilegiado

Este tópico orienta você na habilitação e configuração do gerenciamento de acesso privilegiado em sua organização. Você pode usar o Centro de administração do Microsoft 365 ou o PowerShell de Gerenciamento do Exchange para gerenciar e usar o acesso privilegiado.

## <a name="before-you-begin"></a>Antes de começar

Antes de começar a trabalhar com o gerenciamento de acesso privilegiado, você deve confirmar sua assinatura do [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e quaisquer complementos. Para acessar e usar o gerenciamento de acesso privilegiado, sua organização deve ter uma das seguintes assinaturas ou complementos:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 (ou assinatura do Office 365 E3 + assinatura do Enterprise Mobility and Security E3) + o complemento de Conformidade do Microsoft 365 E5
- Qualquer assinatura do Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive for Business + o complemento gerenciamento de riscos do Microsoft 365 E5 Insider  
- Assinatura do Microsoft 365 A5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 A3 (ou assinatura do Office 365 A3 + assinatura do Enterprise Mobility and Security A3) + o complemento de Conformidade do Microsoft A5
- Qualquer assinatura do Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive for Education + o complemento Microsoft 365 A5 Insider Risk Management
- Assinatura do Office 365 Enterprise E5 (versão paga ou de avaliação)
- Assinatura do Office 365 Enterprise E3 + complemento de Conformidade Avançada do Office 365 (não está mais disponível para novas assinaturas, confira a observação)

Os usuários que estão enviando e respondendo a solicitações de gerenciamento de acesso privilegiado devem receber uma das licenças acima.

>[!IMPORTANT]
>A Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma. Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.

Se você não tiver um plano existente do Office 365 Enterprise E5 e quiser experimentar o gerenciamento de acesso privilegiado, [](https://www.microsoft.com/microsoft-365/enterprise) adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura existente do Office 365 ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5.

## <a name="enable-and-configure-privileged-access-management"></a>Habilitar e configurar o gerenciamento de acesso privilegiado

Siga estas etapas para configurar e usar o acesso privilegiado em sua organização:

- [Etapa 1: Criar um grupo de aprovador](privileged-access-management-configuration.md#step1)

    Antes de começar a usar o acesso a privilégios, determine quem precisa de autoridade de aprovação para solicitações de entrada de acesso a tarefas elevadas e privilegiadas. Qualquer usuário que faz parte do grupo aprovadores é capaz de aprovar solicitações de acesso. Esse grupo é habilitado criando um grupo de segurança habilitado para email no Office 365.

- [Etapa 2: Habilitar o acesso privilegiado](privileged-access-management-configuration.md#step2)

    O acesso privilegiado deve ser explicitamente habilitado no Office 365 com o grupo aprovador padrão, incluindo um conjunto de contas do sistema que você deseja excluir do controle de acesso ao gerenciamento de acesso privilegiado.

- [Etapa 3: Criar uma política de acesso](privileged-access-management-configuration.md#step3)

    Criar uma política de aprovação permite definir os requisitos de aprovação específicos com escopo em tarefas individuais. As opções de tipo de aprovação **são Automático** ou **Manual**.

- [Etapa 4: Enviar/aprovar solicitações de acesso privilegiado](privileged-access-management-configuration.md#step4)

    Uma vez habilitado, o acesso privilegiado requer aprovações para qualquer tarefa que tenha uma política de aprovação associada definida. Para tarefas incluídas em uma política de aprovação, os usuários devem solicitar e ter a aprovação de acesso concedida para ter permissões necessárias para executar a tarefa.

Depois que a aprovação for concedida, o usuário solicitante poderá executar a tarefa pretendida e o acesso privilegiado autorizará e executará a tarefa em nome do usuário. A aprovação permanece válida pela duração solicitada (a duração padrão é de 4 horas), durante a qual o solicitante pode executar a tarefa pretendida várias vezes. Todas essas execuções são registradas e disponibilizadas para auditoria de segurança e conformidade. 

>[!NOTE]
>Se você quiser usar o PowerShell de Gerenciamento do Exchange para habilitar e configurar o acesso privilegiado, siga as etapas em Conectar-se ao PowerShell do Exchange Online usando a autenticação [multifatório](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) para se conectar ao PowerShell do Exchange Online com suas credenciais do Office 365. Você não precisa habilitar a autenticação multifabilitar para que sua organização use as etapas para habilitar o acesso privilegiado ao se conectar ao PowerShell do Exchange Online. A conexão com a autenticação multifatório cria um token OAuth que é usado pelo acesso privilegiado para assinar suas solicitações.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Etapa 1: Criar um grupo de aprovador

1. Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Grupos**  >  **Adicionar um grupo.**

3. Selecione **o grupo de segurança habilitado para email** e  preencha os campos **Nome**, Endereço de **email do** grupo e Descrição do novo grupo.

4. Salve o grupo. Pode levar alguns minutos para que o grupo seja totalmente configurado e apareça no centro de administração do Microsoft 365.

5. Selecione o grupo do novo aprovador e selecione **editar** para adicionar usuários ao grupo.

6. Salve o grupo.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Etapa 2: Habilitar o acesso privilegiado

### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no Centro [de Administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Configurações** de Segurança das Configurações da Organização  >    >  **& acesso privilegiado** de  >  **privacidade.**

3. Habilita as **Aprovações necessárias para o controle de tarefas privilegiadas.**

4. Atribua o grupo do aprovador que você criou na Etapa 1 como o **grupo de aprovadores padrão.**

5. **Salvar** e **fechar.**

### <a name="in-exchange-management-powershell"></a>No PowerShell de Gerenciamento do Exchange

Para habilitar o acesso privilegiado e atribuir o grupo do aprovador, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Exemplo:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>O recurso de contas do sistema é disponibilizado para garantir que determinadas automações em suas organizações possam funcionar sem dependência de acesso privilegiado, no entanto, é recomendável que essas exclusões sejam excepcionais e as permitidas sejam aprovadas e auditadas regularmente.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Etapa 3: Criar uma política de acesso

Você pode criar e configurar até 30 políticas de acesso privilegiado para sua organização.

### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no Centro [de Administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Configurações** de Segurança das Configurações da Organização  >    >  **& acesso privilegiado** de  >  **privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Configurar políticas** e selecione Adicionar uma **política.**

5. Nos campos da lista lista, selecione os valores apropriados para sua organização:
    
    **Tipo de política:** Tarefa, Função ou Grupo de Funções

    **Escopo da política**: Exchange

    **Nome da** política: selecione entre as políticas disponíveis

    **Tipo de aprovação:** Manual ou Automático

    **Grupo de aprovação:** selecione o grupo de aprovadores criado na Etapa 1

6. Selecione **Criar** **e, em seguida, Fechar.** Pode levar alguns minutos para que a política seja totalmente configurada e habilitada.

### <a name="in-exchange-management-powershell"></a>No PowerShell de Gerenciamento do Exchange

Para criar e definir uma política de aprovação, execute o seguinte comando no PowerShell do Exchange Online:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

Exemplo:

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>Etapa 4: Enviar/aprovar solicitações de acesso privilegiado

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>Solicitar autorização de elevação para executar tarefas privilegiadas

As solicitações de acesso privilegiado são válidas por até 24 horas após o envio da solicitação. Se não for aprovado ou negado, as solicitações expiram e o acesso não é aprovado.

#### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no Centro [de Administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais.

2. No Centro de Administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Nova solicitação.** Nos campos da lista lista, selecione os valores apropriados para sua organização:

    **Tipo de solicitação:** Tarefa, Função ou Grupo de Funções

    **Escopo da solicitação**: Exchange

    **Solicitação para:** Selecionar entre as políticas disponíveis

    **Duração (horas)**: Número de horas de acesso solicitado. Não há um limite no número de horas que podem ser solicitadas.

    **Comentários:** campo texto para comentários relacionados à sua solicitação de acesso

5. Selecione **Salvar** **e, em seguida, Fechar.** Sua solicitação será enviada ao grupo do aprovador por email.

#### <a name="in-exchange-management-powershell"></a>No PowerShell de Gerenciamento do Exchange

Execute o seguinte comando no PowerShell do Exchange Online para criar e enviar uma solicitação de aprovação ao grupo do aprovador:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Exemplo:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Exibir o status das solicitações de elevação

Depois que uma solicitação de aprovação é criada, o status da solicitação de elevação pode ser revisado no centro de administração ou no PowerShell de Gerenciamento do Exchange usando a ID associada à solicitação.

#### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.

2. No centro de administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Exibir** para filtrar as solicitações enviadas por **Pendente,** **Aprovado,** **Negado** ou Status do Sistema de **Bloqueio do** Cliente.

#### <a name="in-exchange-management-powershell"></a>No PowerShell de Gerenciamento do Exchange

Execute o seguinte comando no PowerShell do Exchange Online para exibir um status de solicitação de aprovação para uma ID de solicitação específica:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Exemplo:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Aprovando uma solicitação de autorização de elevação

Quando uma solicitação de aprovação é criada, os membros do grupo aprovador relevante recebem uma notificação por email e podem aprovar a solicitação associada à ID da solicitação. O solicitante é notificado sobre a aprovação ou negação de solicitação via mensagem de email.

#### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) com suas credenciais.

2. No centro de administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione uma solicitação listada para exibir os detalhes e agir sobre a solicitação.

5. Selecione **Aprovar** para aprovar a solicitação ou **Negar** para negar a solicitação. Solicitações aprovadas anteriormente podem ter acesso revogado selecionando **Revogar**.

#### <a name="in-exchange-management-powershell"></a>No PowerShell de Gerenciamento do Exchange

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

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Excluir uma política de acesso privilegiado no Office 365

Se não for mais necessário em sua organização, você poderá excluir uma política de acesso privilegiado.

### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais para uma conta de administrador em sua organização.

2. No centro de administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Configurar políticas**.

5. Selecione a política que você deseja excluir e, em seguida, **selecione Remover Política.**

6. Selecione **Fechar**.

### <a name="in-exchange-management-powershell"></a>No PowerShell de Gerenciamento do Exchange

Para excluir uma política de acesso privilegiado, execute o seguinte comando no Powershell do Exchange Online:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Desabilitar o acesso privilegiado no Office 365

Se necessário, você pode desabilitar o gerenciamento de acesso privilegiado para sua organização. Desabilitar o acesso privilegiado não exclui quaisquer políticas de aprovação ou grupos de aprovação associados.

### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) com credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Configurações** de Segurança das  >  **Configurações** da  >  **Organização & acesso privilegiado** de  >  **privacidade.**

3. Habilita **as Aprovações necessárias para o controle de acesso** privilegiado.

### <a name="in-exchange-management-powershell"></a>No PowerShell de Gerenciamento do Exchange

Para desabilitar o acesso privilegiado, execute o seguinte comando no Powershell do Exchange Online:

```PowerShell
Disable-ElevatedAccessControl
```
