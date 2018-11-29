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
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864687"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise

Com as instruções deste artigo, você configura o gerenciamento de acesso privilegiado para aumentar a segurança em seu ambiente de teste do Microsoft 365 Enterprise.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar o gerenciamento de acesso privilegiado não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar privilegiado gerenciamento de acesso e experimentar em um ambiente que representa uma organização típica. 

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configurar o gerenciamento de acesso privilegiado

Nesta fase, você pode configurar um grupo de aprovadores e habilitar o gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 Enterprise. Para obter detalhes adicionais e uma visão geral dos privilégios gerenciamento de acesso, consulte [gerenciamento de acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

Siga estas etapas para configurar e usar o acesso privilegiado em sua organização do Office 365:

- [Etapa 1: Criar um grupo do aprovador](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    Antes de começar a usar o acesso de privilégio, determine quem terá autoridade de aprovação para solicitações de entrada para acesso a tarefas com privilégios elevados e privilegiados. Qualquer usuário que faz parte do grupo dos aprovadores poderão aprovar solicitações de acesso. Esta opção estiver ativada, criando um grupo de segurança habilitados para email no Office 365. Criar um novo grupo de segurança chamado "Privilegiado acesso aprovadores" em seu ambiente de teste e adicionar o "usuário 3", anteriormente criada nas etapas de guia de laboratório de teste anterior.

- [Etapa 2: Habilitar o acesso privilegiado](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    Acesso privilegiado deve ser explicitamente ativado no Office 365 com o grupo de aprovador padrão e incluindo um conjunto de contas de sistema que deseja sejam excluídos do controle de acesso de gerenciamento de acesso privilegiado. Certifique-se de habilitar o acesso privilegiado em sua organização do Office 365 antes de iniciar a fase 3 deste guia.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Verificar se é necessário obter aprovação tarefas com privilégios elevados e privilegiadas
Nesta fase, verifique se a política de acesso privilegiado está funcionando e usuários exigem aprovação para executar tarefas de elevado e privilegiadas definidas.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testar a capacidade de executar uma tarefa não definida em uma política de acesso privilegiado

Primeiro, conecte-se ao PowerShell de gerenciamento do Exchange com as credenciais de um usuário configurado como um Administrador Global no seu ambiente de teste e tentar criar uma nova regra de diário. A tarefa de [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) atualmente não está definida em uma política de acesso privilegiado para sua organização.

1. No computador local, abra e entrar no o Exchange Online PowerShell módulo remoto na **Microsoft Corporation** > **Microsoft Exchange Online PowerShell módulo remoto** usando o Administrador Global da conta para o seu ambiente de teste.

2. No Powershell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. Modo de exibição se a nova regra de diário foi criada com êxito no Exchange PowerShell de gerenciamento.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Criar uma nova política de acesso privilegiado para a tarefa de New-JournalRule

> [!NOTE]
> Se você já não tiver concluído as etapas 1 e 2 da fase 2 deste guia, ser-se de seguir as etapas para criar o grupo do aprovador chamado "Privilégio acesso aprovadores" e habilitar o acesso privilegiado em seu ambiente de teste.

1. Entrar no [Centro de administração do Microsoft 365](https://portal.office.com) usando credenciais a conta de Administrador Global para seu ambiente de teste.

2. No Centro de administração, vá para **configurações** > **de segurança e privacidade** > **acesso privilegiado**.

3. Selecione **solicitações e gerenciar políticas de acesso**.

4. Selecione **Configurar políticas** e **Adicionar uma política**.

5. Nos campos de lista suspensa, selecione ou insira os seguintes valores:
    
    **Tipo de política**: tarefa

    **Escopo da política**: Exchange

    **Nome da política**: nova regra de diário

    **Tipo de aprovação**: Manual

    **Grupo de aprovação**: aprovadores com privilégios de acesso

6. Selecione **criar** e em seguida **Fechar**. Pode levar alguns minutos para a diretiva a ser totalmente configurada e habilitada. Certifique-se de Reserve algum tempo para a política a ser habilitada totalmente antes de testar a exigência de aprovação na próxima etapa.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprovação de teste para a tarefa de New-JournalRule definido em uma política de acesso privilegiado

1. No computador local, abra e entrar no o Exchange Online PowerShell módulo remoto na **Microsoft Corporation** > para seu teste de conta do**Microsoft Exchange Online PowerShell módulo remoto** usando um usando o Administrador Global ambiente.

2. No Powershell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Exibir o erro "Insuficiente permissões" no PowerShell de gerenciamento do Exchange:

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitação de acesso para criar uma nova regra de diário usando a tarefa de New-JournalRule

1. Entrar no [Centro de administração do Microsoft 365](https://portal.office.com) usando a conta de Administrador Global para seu ambiente de teste.

2. No Centro de administração, vá para **configurações** > **de segurança e privacidade** > **acesso privilegiado**.

3. Selecione **solicitações e gerenciar políticas de acesso**.

4. Selecione **nova solicitação**. Nos campos de lista suspensa, selecione os valores apropriados para sua organização:

    **Tipo de solicitação**: tarefa

    **Escopo de solicitação**: Exchange

    **Solicitar para**: nova regra de diário

    **Duração (horas)**: 2

    **Comentários**: solicitar permissão para criar uma nova regra de diário

5. Selecione **Salvar** e **Fechar**. Sua solicitação será enviada ao grupo do aprovador via email.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprovar solicitações de acesso privilegiado para a criação de uma nova regra de diário

1. Entrar no [Centro de administração do Microsoft 365](https://portal.office.com) utilizando as credenciais para o usuário 3 em seu ambiente de teste (membro do grupo de segurança "Privilegiado acesso aprovadores" em seu ambiente de teste).

2. No Centro de administração, vá para **configurações** > **de segurança e privacidade** > **acesso privilegiado**.

3. Selecione **solicitações e gerenciar políticas de acesso**.

4. Selecione a solicitação pendente e **Approve** para conceder acesso à conta de Administrador Global para criar uma nova regra de diário. Um email de notificação confirmando que a aprovação tenha sido concedida será enviado para a conta de Administrador Global (o usuário solicitante).  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Criar uma nova regra de diário com acesso privilegiado aprovado para a tarefa de New-JournalRule de teste

1. No computador local, abra e entrar no o Exchange Online PowerShell módulo remoto na **Microsoft Corporation** > **Microsoft Exchange Online PowerShell módulo remoto** usando o Administrador Global da conta para o seu ambiente de teste.

2. No Powershell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Modo de exibição se a nova regra de diário foi criada com êxito no Exchange PowerShell de gerenciamento.

## <a name="next-step"></a>Próxima etapa

Explore recursos adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) e recursos no seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)