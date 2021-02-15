---
title: Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 para empresas
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
description: Use este Guia de Laboratório de Teste para habilitar o gerenciamento de acesso privilegiado no ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126412"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 para empresas

*Este Guia de Laboratório de Teste pode ser usado para ambientes de teste do Microsoft 365 para empresas e do Office 365 Enterprise.*

Este artigo descreve como configurar o gerenciamento de acesso privilegiado para aumentar a segurança em seu ambiente de teste do Microsoft 365 para empresas.

A configuração do gerenciamento de acesso com privilégios envolve três fases:
- [Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar o gerenciamento de acesso privilegiado](#phase-2-configure-privileged-access-management)
- [Fase 3: Verificar se a aprovação é necessária para tarefas elevadas e privilegiadas](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas

Se você quiser configurar o gerenciamento de acesso privilegiado de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções na [autenticação de passagem.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>O teste do gerenciamento de acesso privilegiado não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio Active Directory. Ele é fornecido aqui como uma opção para que você possa testar o gerenciamento de acesso privilegiado e experimentá-lo em um ambiente que representa uma organização típica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configurar o gerenciamento de acesso privilegiado

Nesta fase, configure um grupo de aprovadores e habilita o gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 para empresas. Para obter detalhes adicionais e uma visão geral do gerenciamento de acesso privilegiado, consulte [Gerenciamento de acesso privilegiado.](../compliance/privileged-access-management-overview.md)

Para configurar e usar o acesso privilegiado em sua organização, execute as etapas a seguir.

#### <a name="step-1-create-an-approvers-group"></a>[Etapa 1: Criar um grupo de aprovador](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Antes de começar a usar o acesso privilegiado, determine quem terá autoridade de aprovação para solicitações de entrada de acesso a tarefas elevadas e privilegiadas. Todos os usuários que fazem parte do grupo aprovadores podem aprovar solicitações de acesso. Para usar o acesso privilegiado, você deve criar um grupo de segurança habilitado para email no Microsoft 365. Em seu ambiente de teste, nomee o novo grupo de segurança "Aprovadores de Acesso Privilegiado" e adicione o "Usuário 3" criado anteriormente nas etapas anteriores do guia do laboratório de teste.

#### <a name="step-2-enable-privileged-access"></a>[Etapa 2: Habilitar o acesso privilegiado](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

O acesso privilegiado precisa ser explicitamente ligado no Microsoft 365 com o grupo aprovador padrão e deve incluir um conjunto de contas do sistema que você deseja excluir do controle de acesso ao gerenciamento de acesso privilegiado. Certifique-se de habilitar o acesso privilegiado em sua organização antes de iniciar a Fase 3 deste guia.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Verificar se a aprovação é necessária para tarefas elevadas e privilegiadas

Nesta fase, verifique se a política de acesso privilegiado está funcionando e se os usuários exigem aprovação para executar tarefas elevadas e privilegiadas definidas.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testar a capacidade de executar uma tarefa NÃO definida em uma política de acesso privilegiado

Primeiro, conecte-se ao PowerShell de Gerenciamento do Exchange com as credenciais de um usuário configurado como Administrador Global em seu ambiente de teste e tente criar uma nova regra de Diário. A [tarefa New-JournalRule](/powershell/module/exchange/new-journalrule) não está definida atualmente em uma política de acesso privilegiado para sua organização.

1. No computador local, abra e entre no Módulo do PowerShell Remoto do Exchange Online na Microsoft **Corporation** Módulo do PowerShell Remoto do Microsoft Exchange Online usando a conta de Administrador Global para seu ambiente  >   de teste.

1. No PowerShell de Gerenciamento do Exchange, crie uma nova regra de Diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Veja se a nova Regra de Diário foi criada com êxito no PowerShell de Gerenciamento do Exchange.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Criar uma nova política de acesso privilegiado para a New-JournalRule tarefa

>[!NOTE]
>Se você ainda não concluiu as etapas 1 e 2 da Fase 2 deste guia, siga as etapas para criar um grupo aprovador chamado "Aprovadores de Acesso a Privilégios" para habilitar o acesso privilegiado em seu ambiente de teste.

1. Entre no Centro [de administração do Microsoft 365](https://admin.microsoft.com) usando credenciais da conta de Administrador Global para seu ambiente de teste.

2. No Centro de Administração, vá para **Configurações**  >  **de Segurança & Acesso Privilegiado** à  >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Configurar políticas** e, em seguida, selecione Adicionar uma **política.**

5. Nos campos da lista de lista, selecione ou insira os seguintes valores:

    **Tipo de política**: Tarefa

    **Escopo da política**: Exchange

    **Nome da política**: Nova Regra de Diário

    **Tipo de aprovação**: Manual

    **Grupo de aprovação:** Aprovadores de Acesso Privilegiado

6. Selecione **Criar** e **Fechar.** Pode levar alguns minutos para que a política seja totalmente configurada e habilitada. Certifique-se de permitir que a política seja totalmente habilitada antes de testar o requisito de aprovação na próxima etapa.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprovação de teste para New-JournalRule tarefa definida em uma política de acesso privilegiado

1. No computador local, abra e entre no Módulo do PowerShell Remoto do Exchange Online na Microsoft **Corporation**  >  **Microsoft Exchange Online Remote PowerShell Module** usando uma conta de Administrador Global para seu ambiente de teste.

2. No PowerShell de Gerenciamento do Exchange, crie uma nova regra de Diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Exibir o erro "Permissões insuficientes" no PowerShell de Gerenciamento do Exchange:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acesso para criar uma nova Regra de Diário usando a New-JournalRule tarefa

1. Entre no centro de [administração do Microsoft 365](https://admin.microsoft.com) usando a conta de Administrador Global para seu ambiente de teste.

2. No Centro de Administração, vá para **Configurações**  >  **de Segurança & Acesso Privilegiado** à  >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Nova solicitação.** Nos campos da lista lista, selecione os valores apropriados para sua organização:

    **Tipo de solicitação**: Tarefa

    **Escopo da solicitação**: Exchange

    **Solicitação de**: Nova Regra de Diário

    **Duração (horas)**: 2

    **Comentários**: Solicitar permissão para criar uma nova Regra de Diário

5. Selecione **Salvar** e, em seguida, **Fechar**. Sua solicitação será enviada ao grupo do aprovador por email.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprovar solicitação de acesso privilegiado para a criação de uma nova Regra de Diário

1. Entre no centro de administração do [Microsoft 365](https://admin.microsoft.com) usando as credenciais do Usuário 3 em seu ambiente de teste (membro do grupo de segurança "Aprovadores de Acesso Privilegiado" em seu ambiente de teste).

2. No Centro de Administração, vá para **Configurações**  >  **de Segurança & Acesso Privilegiado** à  >  **Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione a solicitação pendente e, em seguida, **selecione Aprovar** para conceder acesso à conta de Administrador Global para criar uma nova Regra de Diário. A conta de Administrador Global (o usuário solicitando) receberá uma confirmação por email de que a aprovação foi concedida.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testar a criação de uma nova Regra de Diário com acesso privilegiado aprovado para a New-JournalRule tarefa

1. No computador local, abra e entre no Módulo do PowerShell Remoto do Exchange Online na Microsoft **Corporation** Módulo do PowerShell Remoto do Microsoft Exchange Online usando a conta de Administrador Global para seu ambiente  >   de teste.

1. No PowerShell de Gerenciamento do Exchange, crie uma nova regra de Diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Veja se a nova Regra de Diário foi criada com êxito no PowerShell de Gerenciamento do Exchange.

## <a name="next-step"></a>Próxima etapa

Explore recursos [e funcionalidades adicionais](m365-enterprise-test-lab-guides.md#information-protection) de proteção de informações em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)
