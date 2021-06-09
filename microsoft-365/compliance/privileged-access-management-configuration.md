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
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126528"
---
# <a name="get-started-with-privileged-access-management"></a>Introdução ao gerenciamento de acesso privilegiado

Este tópico orienta você por meio da habilitação e configuração do gerenciamento de acesso privilegiado em sua organização. Você pode usar o centro de administração Microsoft 365 ou o PowerShell de Gerenciamento Exchange gerenciamento para gerenciar e usar o acesso privilegiado.

## <a name="before-you-begin"></a>Antes de começar

Antes de começar com o gerenciamento de acesso privilegiado, você deve confirmar sua assinatura [Microsoft 365 e](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) quaisquer complementos. Para acessar e usar o gerenciamento de acesso privilegiado, sua organização deve ter uma das seguintes assinaturas ou complementos:

- Microsoft 365 E5 assinatura (versão paga ou de avaliação)
- Microsoft 365 E3 assinatura (ou assinatura Office 365 E3 + assinatura Enterprise Mobility and Security E3) + o complemento Microsoft 365 E5 Compliance Microsoft 365 E5 Compliance
- Qualquer Microsoft 365, Office 365, Exchange, SharePoint assinatura ou OneDrive for Business assinatura + o complemento Microsoft 365 E5 Gerenciamento de Riscos do Insider  
- Microsoft 365 Assinatura A5 (versão paga ou avaliação)
- Microsoft 365 Assinatura A3 (ou assinatura Office 365 A3 + assinatura Enterprise Mobility and Security A3) + o complemento conformidade do Microsoft A5
- Qualquer Microsoft 365, Office 365, Exchange, SharePoint ou OneDrive assinatura para Educação + o complemento gerenciamento de riscos do Microsoft 365 A5 Insider
- Office 365 Enterprise Assinatura E5 (versão paga ou avaliação)
- Office 365 Enterprise Assinatura E3 + o Conformidade Avançada do Office 365 complemento (não está mais disponível para novas assinaturas, consulte observação)

Os usuários que estão enviando e respondendo a solicitações de gerenciamento de acesso privilegiado devem receber uma das licenças acima.

>[!IMPORTANT]
>Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma. Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.

Se você não tiver um plano Office 365 Enterprise E5 existente e quiser tentar o gerenciamento de acesso privilegiado, adicione o [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) à sua assinatura do Office 365 existente ou inscreva-se para uma avaliação do Microsoft 365 Enterprise E5. [](https://www.microsoft.com/microsoft-365/enterprise)

## <a name="enable-and-configure-privileged-access-management"></a>Habilitar e configurar o gerenciamento de acesso privilegiado

Siga estas etapas para configurar e usar o acesso privilegiado em sua organização:

- [Etapa 1: Criar um grupo de aprovação](privileged-access-management-configuration.md#step1)

    Antes de começar a usar o acesso privilegiado, determine quem precisa de autoridade de aprovação para solicitações de acesso a tarefas elevadas e privilegiadas. Qualquer usuário que faz parte do grupo de Aprovadores pode aprovar solicitações de acesso. Esse grupo é habilitado criando um grupo de segurança habilitado para email no Office 365.

- [Etapa 2: Habilitar o acesso privilegiado](privileged-access-management-configuration.md#step2)

    O acesso privilegiado deve ser explicitamente habilitado no Office 365 com o grupo aprovador padrão, incluindo um conjunto de contas do sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado.

- [Etapa 3: Criar uma política de acesso](privileged-access-management-configuration.md#step3)

    Criar uma política de aprovação permite que você defina os requisitos de aprovação específicos com escopo em tarefas individuais. As opções de tipo de aprovação são **Automática** ou **Manual**.

- [Etapa 4: Enviar/aprovar solicitações de acesso privilegiado](privileged-access-management-configuration.md#step4)

    Uma vez habilitado, o acesso privilegiado requer aprovações para qualquer tarefa que tenha uma política de aprovação associada definida. Para tarefas incluídas em uma política de aprovação, os usuários devem solicitar e ter a aprovação de acesso concedida para que tenham as permissões necessárias para executar a tarefa.

Depois que a aprovação for concedida, o usuário solicitante poderá executar a tarefa pretendida e o acesso privilegiado autorizará e executará a tarefa em nome do usuário. A aprovação permanece válida pelo tempo solicitado (a duração padrão é de quatro horas), durante o qual o solicitante pode executar a tarefa pretendida várias vezes. Todas essas execuções são registradas e disponibilizadas para auditoria de segurança e conformidade. 

>[!NOTE]
>Se você quiser usar o powershell de gerenciamento do Exchange para habilitar e configurar o acesso privilegiado, siga as etapas do Conexão para Exchange Online PowerShell usando a autenticação [multifação](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) para se conectar ao Exchange Online PowerShell com suas credenciais de Office 365. Você não precisa habilitar a autenticação multifabilitar para sua organização usar as etapas para habilitar o acesso privilegiado ao se conectar ao Exchange Online PowerShell. A conexão com a autenticação multifatório cria um token OAuth usado pelo acesso privilegiado para assinar suas solicitações.

<a name="step1"> </a>

## <a name="step-1-create-an-approvers-group"></a>Etapa 1: Criar um grupo de aprovação

1. Entre no centro [de administração Microsoft 365 usando](https://admin.microsoft.com) credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Grupos**  >  **Adicionar um grupo**.

3. Selecione **o grupo de segurança habilitado** para email e conclua os campos **Nome,** Endereço de **email** de grupo e **Descrição** do novo grupo.

4. Salve o grupo. Pode levar alguns minutos para que o grupo esteja totalmente configurado e apareça no Centro de administração do Microsoft 365.

5. Selecione o grupo do novo aprovador e selecione **editar** para adicionar usuários ao grupo.

6. Salve o grupo.

<a name="step2"> </a>

## <a name="step-2-enable-privileged-access"></a>Etapa 2: Habilitar o acesso privilegiado

### <a name="in-the-microsoft-365-admin-center"></a>No Centro Microsoft 365 Admin

1. Entre no Centro [de administração Microsoft 365 usando](https://admin.microsoft.com) credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**

3. Habilita **o controle Exigir aprovações para tarefas privilegiadas.**

4. Atribua o grupo do aprovador que você criou na Etapa 1 como **o grupo aprovadores padrão**.

5. **Salvar** e **fechar**.

### <a name="in-exchange-management-powershell"></a>No Exchange PowerShell de Gerenciamento

Para habilitar o acesso privilegiado e atribuir o grupo do aprovador, execute o seguinte comando Exchange Online PowerShell:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

Exemplo:

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
>O recurso contas do sistema é disponibilizado para garantir que determinadas automações em suas organizações possam funcionar sem dependência de acesso privilegiado, no entanto, é recomendável que essas exclusões sejam excepcionais e as permitidas sejam aprovadas e auditadas regularmente.

<a name="step3"> </a>

## <a name="step-3-create-an-access-policy"></a>Etapa 3: Criar uma política de acesso

Você pode criar e configurar até 30 políticas de acesso privilegiado para sua organização.

### <a name="in-the-microsoft-365-admin-center"></a>No Centro Microsoft 365 Admin

1. Entre no Centro [de administração Microsoft 365 usando](https://admin.microsoft.com) credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Configurar políticas e** selecione Adicionar uma **política**.

5. Nos campos drop-down, selecione os valores apropriados para sua organização:
    
    **Tipo de política**: tarefa, função ou grupo de funções

    **Escopo da política**: Exchange

    **Nome da política**: selecione uma das políticas disponíveis

    **Tipo de aprovação**: manual ou automática

    **Grupo de aprovação**: selecione o grupo de aprovadores criado na Etapa 1

6. Selecione **Criar** **e,** em seguida, Fechar . Pode levar alguns minutos para que a política seja totalmente configurada e habilitada.

### <a name="in-exchange-management-powershell"></a>No Exchange PowerShell de Gerenciamento

Para criar e definir uma política de aprovação, execute o seguinte comando Exchange Online PowerShell:

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

As solicitações de acesso privilegiado são válidas por até 24 horas após o envio da solicitação. Se não forem aprovadas ou negadas, as solicitações expiram e o acesso não é aprovado.

#### <a name="in-the-microsoft-365-admin-center"></a>No Centro Microsoft 365 Admin

1. Entre no Centro [de administração Microsoft 365 usando](https://admin.microsoft.com) suas credenciais.

2. No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Nova solicitação**. Nos campos drop-down, selecione os valores apropriados para sua organização:

    **Tipo de solicitação**: tarefa, função ou grupo de funções

    **Escopo da solicitação**: Exchange

    **Solicitação**: selecione uma das políticas disponíveis

    **Duração (horas)**: número de horas de acesso solicitadas. Não há um limite no número de horas que podem ser solicitadas.

    **Comentários**: Campo de texto para comentários relacionados à sua solicitação de acesso

5. Selecione **Salvar** **e,** em seguida, Fechar . Sua solicitação será enviada para o grupo do aprovador por email.

#### <a name="in-exchange-management-powershell"></a>No Exchange PowerShell de Gerenciamento

Execute o seguinte comando no Exchange Online PowerShell para criar e enviar uma solicitação de aprovação ao grupo do aprovador:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

Exemplo:

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a>Ver o status das solicitações de elevação

Após a criação de uma solicitação de aprovação, o status da solicitação de elevação pode ser revisado no centro de administração ou no Exchange Management PowerShell usando a ID de solicitação associada.

#### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no centro [de administração Microsoft 365 com](https://admin.microsoft.com) suas credenciais.

2. No centro de administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Exibir** para filtrar solicitações enviadas **pelo** status pendente **,** **Aprovado,** Negado ou Bloqueio **do** Cliente.

#### <a name="in-exchange-management-powershell"></a>No Exchange PowerShell de Gerenciamento

Execute o seguinte comando no Exchange Online PowerShell para exibir um status de solicitação de aprovação para uma ID de solicitação específica:

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

Exemplo:

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>Aprovar uma solicitação de autorização de elevação

Quando uma solicitação de aprovação é criada, membros do grupo aprovador relevante recebem uma notificação por email e podem aprovar a solicitação associada à ID da solicitação. O solicitante é notificado da aprovação ou negação da solicitação por mensagem de email.

#### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no centro [de administração Microsoft 365 com](https://admin.microsoft.com) suas credenciais.

2. No centro de administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione uma solicitação listada para exibir os detalhes e para tomar medidas na solicitação.

5. Selecione **Aprovar** para aprovar a solicitação ou selecione **Negar** para negar a solicitação. Solicitações aprovadas anteriormente podem ter acesso revogado selecionando **Revogar**.

#### <a name="in-exchange-management-powershell"></a>No Exchange PowerShell de Gerenciamento

Para aprovar uma solicitação de autorização de elevação, execute o seguinte comando Exchange Online PowerShell:

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

Exemplo:

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

Para negar uma solicitação de autorização de elevação, execute o seguinte comando Exchange Online PowerShell:

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

Exemplo:

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>Excluir uma política de acesso privilegiado Office 365

Se ela não for mais necessária em sua organização, você poderá excluir uma política de acesso privilegiado.

### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no centro [de administração Microsoft 365 usando](https://admin.microsoft.com) credenciais para uma conta de administrador em sua organização.

2. No centro de administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Configurar políticas**.

5. Selecione a política que deseja excluir e selecione **Remover Política**.

6. Selecione **Fechar**.

### <a name="in-exchange-management-powershell"></a>No Exchange PowerShell de Gerenciamento

Para excluir uma política de acesso privilegiado, execute o seguinte comando no Exchange Online Powershell:

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>Desabilitar o acesso privilegiado Office 365

Se necessário, você pode desabilitar o gerenciamento de acesso privilegiado para sua organização. Desabilitar o acesso privilegiado não exclui políticas de aprovação ou grupos de aprovação associados.

### <a name="in-the-microsoft-365-admin-center"></a>No Centro de administração do Microsoft 365

1. Entre no centro [de administração Microsoft 365 com](https://admin.microsoft.com) credenciais para uma conta de administrador em sua organização.

2. No Centro de Administração, vá para **Configurações** Org Configurações Segurança & Acesso Privilegiado de  >    >    >  **Privacidade.**

3. Habilita **o Exigir aprovações para controle de acesso** privilegiado.

### <a name="in-exchange-management-powershell"></a>No Exchange PowerShell de Gerenciamento

Para desabilitar o acesso privilegiado, execute o seguinte comando no Exchange Online Powershell:

```PowerShell
Disable-ElevatedAccessControl
```
