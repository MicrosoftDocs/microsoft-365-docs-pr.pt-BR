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
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Gerenciamento de acesso privilegiado para seu Microsoft 365 para ambiente de teste empresarial

*Este Guia de Laboratório de Teste pode ser usado para Microsoft 365 ambientes de teste corporativos e Office 365 Enterprise de teste.*

Este artigo descreve como configurar o gerenciamento de acesso privilegiado para aumentar a segurança em seu Microsoft 365 ambiente de teste empresarial.

A configuração do gerenciamento de acesso privado envolve três fases:
- [Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Configurar o gerenciamento de acesso privilegiado](#phase-2-configure-privileged-access-management)
- [Fase 3: Verificar se a aprovação é necessária para tarefas elevadas e privilegiadas](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial

Se você quiser configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se você quiser configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções em [Autenticação passagem](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>Testar o gerenciamento de acesso privilegiado não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory. Ele é fornecido aqui como uma opção para que você possa testar o gerenciamento de acesso privilegiado e experimentá-lo em um ambiente que representa uma organização típica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: Configurar o gerenciamento de acesso privilegiado

Nesta fase, configure um grupo de aprovadores e habilita o gerenciamento de acesso privilegiado para seu Microsoft 365 ambiente de teste empresarial. Para obter detalhes adicionais e uma visão geral do gerenciamento de acesso privilegiado, consulte [Privileged access management](../compliance/privileged-access-management-overview.md).

Para configurar e usar o acesso privilegiado em sua organização, execute as etapas a seguir.

#### <a name="step-1-create-an-approvers-group"></a>[Etapa 1: Criar um grupo de aprovação](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Antes de começar a usar o acesso privilegiado, determine quem terá autoridade de aprovação para solicitações de entrada para acesso a tarefas elevadas e privilegiadas. Todos os usuários que fazem parte do grupo aprovadores podem aprovar solicitações de acesso. Para usar o acesso privilegiado, você deve criar um grupo de segurança habilitado para email Microsoft 365. Em seu ambiente de teste, nomee o novo grupo de segurança "Aprovadores de Acesso Privilegiado" e adicione o "Usuário 3" que foi criado anteriormente nas etapas anteriores do laboratório de teste.

#### <a name="step-2-enable-privileged-access"></a>[Etapa 2: Habilitar o acesso privilegiado](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

O acesso privilegiado precisa ser explicitamente Microsoft 365 com o grupo aprovador padrão e deve incluir um conjunto de contas do sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado. Certifique-se de habilitar o acesso privilegiado em sua organização antes de iniciar a Fase 3 deste guia.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: Verificar se a aprovação é necessária para tarefas elevadas e privilegiadas

Nesta fase, verifique se a política de acesso privilegiado está funcionando e se os usuários exigem aprovação para executar tarefas definidas elevadas e privilegiadas.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testar a capacidade de executar uma tarefa NÃO definida em uma política de acesso privilegiado

Primeiro, conecte-se ao Exchange Do PowerShell de Gerenciamento com as credenciais de um usuário configurado como Administrador Global em seu ambiente de teste e tente criar uma nova regra de Diário. A [tarefa New-JournalRule](/powershell/module/exchange/new-journalrule) não está definida atualmente em uma política de acesso privilegiado para sua organização.

1. Em seu computador local, abra e entre no módulo Exchange Online PowerShell Remoto da **Microsoft Corporation** Microsoft Exchange Online Módulo Do PowerShell Remoto usando a conta Administrador Global para seu ambiente de  >   teste.

1. No Exchange PowerShell de Gerenciamento, crie uma nova regra de Diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Veja que a nova Regra de Diário foi criada com êxito no Exchange Management PowerShell.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Criar uma nova política de acesso privilegiado para New-JournalRule tarefa

>[!NOTE]
>Se você ainda não concluiu as Etapas 1 e 2 da Fase 2 deste guia, siga as etapas para criar um grupo de aprovadores chamado "Aprovadores de Acesso para Privilégios" para habilitar o acesso privilegiado em seu ambiente de teste.

1. Entre no centro de administração [Microsoft 365 usando](https://admin.microsoft.com) credenciais da conta administrador global para seu ambiente de teste.

2. No Centro de Administração, vá **para** Configurações  >  **Segurança & Acesso Privilegiado**  >  **de Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Configurar políticas** e, em seguida, selecione Adicionar uma **política**.

5. Nos campos drop-down, selecione ou insira os seguintes valores:

    **Tipo de política**: Tarefa

    **Escopo da política**: Exchange

    **Nome da política**: Nova Regra de Diário

    **Tipo de aprovação**: Manual

    **Grupo de aprovação**: Aprovadores de Acesso Privilegiado

6. Selecione **Criar** e, em seguida, selecione **Fechar**. Pode levar alguns minutos para que a política seja totalmente configurada e habilitada. Certifique-se de permitir que o tempo para a política seja totalmente habilitado antes de testar o requisito de aprovação na próxima etapa.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Requisito de aprovação de teste para a tarefa New-JournalRule definida em uma política de acesso privilegiado

1. Em seu computador local, abra e entre no módulo Exchange Online PowerShell Remoto da **Microsoft Corporation** Microsoft Exchange Online Módulo Do PowerShell Remoto usando uma conta de Administrador Global para seu ambiente de  >   teste.

2. No Exchange PowerShell de Gerenciamento, crie uma nova regra de Diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Exibir o erro "Permissões insuficientes" no Exchange Management PowerShell:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acesso para criar uma nova Regra de Diário usando New-JournalRule tarefa

1. Entre no centro de administração [Microsoft 365 usando a](https://admin.microsoft.com) conta Administrador Global para seu ambiente de teste.

2. No Centro de Administração, vá **para** Configurações  >  **Segurança & Acesso Privilegiado**  >  **de Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione **Nova solicitação**. Nos campos drop-down, selecione os valores apropriados para sua organização:

    **Tipo de solicitação**: Tarefa

    **Escopo da solicitação**: Exchange

    **Solicitação para**: Nova Regra de Diário

    **Duração (horas)**: 2

    **Comentários**: Solicitar permissão para criar uma nova Regra de Diário

5. Selecione **Salvar** e, em seguida, selecione **Fechar**. Sua solicitação será enviada para o grupo do aprovador por email.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprovar solicitação de acesso privilegiado para a criação de uma nova Regra de Diário

1. Entre no [](https://admin.microsoft.com) centro de administração Microsoft 365 usando as credenciais do Usuário 3 em seu ambiente de teste (membro do grupo de segurança "Aprovadores de Acesso Privilegiado" em seu ambiente de teste).

2. No Centro de Administração, vá **para** Configurações  >  **Segurança & Acesso Privilegiado**  >  **de Privacidade.**

3. Selecione **Gerenciar políticas e solicitações de acesso.**

4. Selecione a solicitação pendente e selecione **Aprovar** para conceder acesso à conta administrador global para criar uma nova Regra de Diário. A conta administrador global (o usuário solicitando) receberá uma confirmação por email de que a aprovação foi concedida.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testar a criação de uma nova Regra de Diário com acesso privilegiado aprovado para a tarefa New-JournalRule de usuário

1. Em seu computador local, abra e entre no módulo Exchange Online PowerShell Remoto da **Microsoft Corporation** Microsoft Exchange Online Módulo Do PowerShell Remoto usando a conta Administrador Global para seu ambiente de  >   teste.

1. No Exchange PowerShell de Gerenciamento, crie uma nova regra de Diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Veja que a nova Regra de Diário foi criada com êxito no Exchange Management PowerShell.

## <a name="next-step"></a>Próxima etapa

Explore recursos [e recursos adicionais de proteção](m365-enterprise-test-lab-guides.md#information-protection) de informações em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação do Microsoft 365 para empresas](/microsoft-365-enterprise/)
