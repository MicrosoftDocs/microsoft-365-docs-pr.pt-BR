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
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 for Enterprise

*Este guia de laboratório de teste pode ser usado para ambientes de teste corporativos do Microsoft 365 para Enterprise e Office 365.*

Este artigo descreve como configurar o gerenciamento de acesso privilegiado para aumentar a segurança no ambiente de teste do Microsoft 365 for Enterprise.

A configuração do gerenciamento de acesso privilegiado envolve três fases:
- [Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurar o gerenciamento de acesso privilegiado](#phase-2-configure-privileged-access-management)
- [Fase 3: verificar se a aprovação é necessária para tarefas elevadas e privilegiadas](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise

Se você quiser configurar o gerenciamento de acesso privilegiado de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja configurar o gerenciamento de acesso privilegiado em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
>[!NOTE]
>O teste de gerenciamento de acesso privilegiado não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta de serviços de domínio do Active Directory. É fornecido aqui como uma opção para que você possa testar o gerenciamento de acesso privilegiado e experimentá-lo em um ambiente que representa uma organização típica.

## <a name="phase-2-configure-privileged-access-management"></a>Fase 2: configurar o gerenciamento de acesso privilegiado

Nesta fase, configure um grupo de aprovadores e habilite o gerenciamento de acesso privilegiado para seu ambiente de teste do Microsoft 365 for Enterprise. Para obter detalhes adicionais e uma visão geral do gerenciamento de acesso privilegiado, consulte [Gerenciamento de acesso privilegiado](../compliance/privileged-access-management-overview.md).

Para configurar e usar o acesso privilegiado em sua organização, execute as etapas a seguir.

#### <a name="step-1-create-an-approvers-group"></a>[Etapa 1: criar um grupo do aprovador](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Antes de começar a usar o acesso privilegiado, determine quem terá autoridade de aprovação para as solicitações de entrada para acesso a tarefas elevadas e privilegiadas. Todos os usuários que fazem parte do grupo aprovadores podem aprovar as solicitações de acesso. Para usar o acesso privilegiado, você deve criar um grupo de segurança habilitado para email no Microsoft 365. Em seu ambiente de teste, nomeie o novo grupo de segurança aprovadores de acesso privilegiado e adicione o "usuário 3" que foi criado anteriormente nas etapas anteriores do guia do laboratório de teste.

#### <a name="step-2-enable-privileged-access"></a>[Etapa 2: habilitar o acesso privilegiado](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

O acesso privilegiado precisa estar explicitamente ativado no Microsoft 365 com o grupo padrão aprovador e deve incluir um conjunto de contas de sistema que você deseja excluir do controle de acesso de gerenciamento de acesso privilegiado. Certifique-se de habilitar o acesso privilegiado em sua organização antes de iniciar a fase 3 deste guia.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>Fase 3: verificar se a aprovação é necessária para tarefas elevadas e privilegiadas

Nesta fase, verifique se a política de acesso privilegiado está funcionando e se os usuários precisam de aprovação para executar tarefas elevadas e privilegiadas definidas.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Testar a capacidade de executar uma tarefa não definida em uma política de acesso privilegiado

Primeiro, conecte-se ao PowerShell de gerenciamento do Exchange com as credenciais de um usuário configurado como administrador global no seu ambiente de teste e tente criar uma nova regra de diário. A tarefa [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) não está definida atualmente em uma política de acesso privilegiado para sua organização.

1. No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.

1. No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>Criar uma nova política de acesso privilegiado para a tarefa de New-JournalRule

>[!NOTE]
>Se você ainda não tiver concluído as etapas 1 e 2 da fase 2 deste guia, certifique-se de seguir as etapas para criar um grupo do aprovador chamado "aprovadores de acesso a privilégios" para habilitar o acesso privilegiado no seu ambiente de teste.

1. Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) usando credenciais da conta de administrador global para seu ambiente de teste.

2. No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione **Configurar políticas**e, em seguida, selecione **Adicionar uma política**.

5. Nos campos suspensos, selecione ou insira os seguintes valores:

    **Tipo de política**: tarefa

    **Escopo da política**: Exchange

    **Nome da política**: nova regra de diário

    **Tipo de aprovação**: manual

    **Grupo de aprovação**: aprovadores de acesso privilegiado

6. Selecione **criar**e selecione **fechar**. Pode levar alguns minutos até que a política seja totalmente configurada e habilitada. Certifique-se de permitir que o tempo da política seja totalmente habilitado antes de testar o requisito de aprovação na próxima etapa.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Testar requisitos de aprovação para a tarefa de New-JournalRule definida em uma política de acesso privilegiado

1. No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando um usando a conta de administrador global para seu ambiente de teste.

2. No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Veja o erro "permissões insuficientes" no PowerShell de gerenciamento do Exchange:

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Solicitar acesso para criar uma nova regra de diário usando a tarefa New-JournalRule

1. Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) usando a conta de administrador global para seu ambiente de teste.

2. No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione **nova solicitação**. Nos campos suspensos, selecione os valores apropriados para a sua organização:

    **Tipo de solicitação**: Task

    **Escopo da solicitação**: Exchange

    **Solicitação de**: nova regra de diário

    **Duração (horas)**: 2

    **Comentários**: solicitar permissão para criar uma nova regra de diário

5. Selecione **salvar**e, em seguida, selecione **fechar**. Sua solicitação será enviada ao grupo do aprovador por email.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Aprovar solicitação de acesso privilegiado para a criação de uma nova regra de diário

1. Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais do usuário 3 no seu ambiente de teste (membro do grupo de segurança "aprovadores de acesso privilegiado" no seu ambiente de teste).

2. No centro de administração, vá até **configurações**de  >  **segurança & privacidade**  >  **privilegiada**.

3. Selecione **gerenciar políticas e solicitações de acesso**.

4. Selecione a solicitação pendente e, em seguida, selecione **aprovar** para conceder acesso à conta de administrador global para criar uma nova regra de diário. A conta de administrador global (o usuário solicitante) receberá uma confirmação de email informando que a aprovação foi concedida.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Testar a criação de uma nova regra de diário com acesso privilegiado aprovado para a tarefa de New-JournalRule

1. No computador local, abra e entre no módulo do PowerShell remoto do Exchange Online no módulo Microsoft **Corporation**  >  **Microsoft Exchange Online PowerShell** usando a conta de administrador global para seu ambiente de teste.

1. No PowerShell de gerenciamento do Exchange, crie uma nova regra de diário para sua organização:

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Veja se a nova regra de diário foi criada com êxito no PowerShell de gerenciamento do Exchange.

## <a name="next-step"></a>Próxima etapa

Explore recursos e funcionalidades adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) em seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Documentação da Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
