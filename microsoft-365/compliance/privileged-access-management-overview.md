---
title: Saiba mais sobre o gerenciamento de acesso privilegiado
description: Este artigo fornece uma visão geral sobre o gerenciamento de acesso privilegiado Microsoft 365, incluindo respostas para perguntas frequentes (perguntas frequentes).
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126600"
---
# <a name="learn-about-privileged-access-management"></a>Saiba mais sobre o gerenciamento de acesso privilegiado

O Gerenciamento de Acesso Privilegiado permite um controle granular de acesso das tarefas de administrador privilegiado no Office 365. Ele pode ajudar a proteger sua organização contra violações que usam contas de administrador privilegiado existentes com acesso permanente a dados confidenciais ou acesso a configurações críticas. O Privileged Access Management exige que os usuários solicitem acesso just-in-time para concluir tarefas elevadas e privilegiadas por meio de um fluxo de trabalho de aprovação com escopo alto e limite de tempo. Essa configuração fornece aos usuários acesso suficiente para realizarem a tarefa em questão sem a exposição desnecessária de dados confidenciais ou de configurações críticas. A habilitação do gerenciamento de acesso privilegiado Microsoft 365 permite que sua organização opere com privilégios de posição zero e forneça uma camada de defesa contra vulnerabilidades de acesso administrativo permanentes.

Para uma visão geral rápida do caixa de bloqueio do cliente integrada e fluxo de trabalho de gerenciamento de acesso privilegiado, consulte este vídeo de gerenciamento de acesso privilegiado e Caixa de Bloqueio do [Cliente.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Camadas de proteção

O gerenciamento de acesso privilegiado complementa outras proteções de recursos de acesso e dados na arquitetura Microsoft 365 segurança. Incluir o gerenciamento de acesso privilegiado como parte de uma abordagem integrada e em camadas para a segurança fornece um modelo de segurança que maximiza a proteção de informações confidenciais e configurações Microsoft 365 segurança. Conforme mostrado no diagrama, o gerenciamento de acesso privilegiado se baseia na proteção fornecida com criptografia nativa de dados Microsoft 365 e o modelo de segurança de controle de acesso baseado em função dos serviços Microsoft 365. Quando usados com o [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure), esses dois recursos fornecem controle de acesso com acesso just-in-time em escopos diferentes.

![Proteção em camadas em Microsoft 365](../media/pam-layered-protection.png)

O gerenciamento de acesso privilegiado  é definido e tem escopo no nível da tarefa,  enquanto o Azure AD Privileged Identity Management aplica proteção no nível de função com a capacidade de executar várias tarefas. O Azure AD Privileged Identity Management permite principalmente o acesso de gerenciamento para funções de administrador e grupos de função, enquanto o Privileged Access Management do Microsoft 365 é aplicado somente no nível de tarefa.

- **Habilitando o gerenciamento de acesso privilegiado ao usar o Azure AD Privileged Identity Management:** A adição do gerenciamento de acesso privilegiado fornece outra camada granular de recursos de proteção e auditoria para acesso privilegiado Microsoft 365 dados.

- **Habilitando o Azure AD Privileged Identity Management usando o gerenciamento** de acesso privilegiado em Office 365:  A adição do Azure AD Privileged Identity Management gerenciamento de acesso privilegiado pode estender o acesso privilegiado a dados fora do Microsoft 365 que são definidos principalmente por funções de usuário ou identidade.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitetura de gerenciamento de acesso privilegiado e fluxo de processos

Cada um dos fluxos de processo a seguir descreve a arquitetura do acesso privilegiado e como ele interage com o Microsoft 365, a auditoria e o espaço de Exchange Gerenciamento.

### <a name="step-1-configure-a-privileged-access-policy"></a>Etapa 1: configurar uma política de acesso privilegiado

Quando você configura uma política de acesso privilegiado com o centro de administração do [Microsoft 365](https://admin.microsoft.com) ou o PowerShell de Gerenciamento do Exchange, você define a política e os processos de recurso de acesso privilegiado e os atributos de política no Microsoft 365. As atividades são registradas no Centro &amp; de Conformidade e Segurança. A política está agora habilitada e pronta para lidar com solicitações de aprovações recebidas.

![Etapa 1: Criação de política](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Etapa 2: solicitação de acesso

No centro [Microsoft 365 de](https://admin.microsoft.com) administração ou com o PowerShell de Gerenciamento Exchange, os usuários podem solicitar acesso a tarefas elevadas ou privilegiadas. O recurso de acesso privilegiado envia a solicitação para o Microsoft 365 para processamento em relação à política de acesso de privilégio configurada e registra a Atividade nos logs do Centro de &amp; Conformidade e Segurança.

![Etapa 2: solicitação de acesso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Etapa 3: aprovação de acesso

Uma solicitação de aprovação é gerada e a notificação de solicitação pendente é enviada por email para os aprovadores. Se aprovada, a solicitação de acesso privilegiado é processada como uma aprovação e a tarefa está pronta para ser concluída. Se negada, a tarefa é bloqueada e nenhum acesso é concedido ao solicitante. O solicitante é notificado da aprovação ou negação da solicitação por mensagem de email.

![Etapa 3: aprovação de acesso](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Etapa 4: processamento do acesso

Para uma solicitação aprovada, a tarefa é processada pelo runspace do Gerenciamento do Exchange. A aprovação é verificada de acordo com a política de acesso privilegiado e processada pelo substrato do Microsoft 365. Todas as atividades da tarefa são registradas no Centro &amp; de Conformidade e Segurança.

![Etapa 4: processamento do acesso](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Quais SKUs podem usar o acesso privilegiado Office 365?

O gerenciamento de acesso privilegiado está disponível para clientes para uma ampla seleção de Microsoft 365 e Office 365 assinaturas e complementos. Confira [Começar com o gerenciamento de acesso privilegiado](privileged-access-management-configuration.md) para obter detalhes.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Quando o acesso privilegiado dará suporte Office 365 cargas de trabalho além Exchange?

O gerenciamento de acesso privilegiado estará disponível em outras Office 365 cargas de trabalho em breve. Visite o [Microsoft 365 roteiro para](https://www.microsoft.com/microsoft-365/roadmap) obter mais detalhes.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Minha organização precisa de mais de 30 políticas de acesso privilegiado, esse limite será aumentado?

Sim, a elevação do limite atual de 30 políticas de acesso privilegiado por organização está no roteiro de recursos.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Preciso ser um Administrador Global para gerenciar o acesso privilegiado Office 365?

Não, você precisa da função Exchange Gerenciamento de Função atribuída a contas que gerenciam o acesso privilegiado Office 365. Se você não quiser configurar a função de Gerenciamento de Função como uma permissão de conta autônomo, a função Administrador Global inclui essa função por padrão e pode gerenciar o acesso privilegiado. Os usuários incluídos em um grupo de aprovadores não precisam ser administradores globais ou ter a função de Gerenciamento de Função atribuída para revisar e aprovar solicitações com o PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Como o gerenciamento de acesso privilegiado está relacionado ao Customer Lockbox?

[O Customer Lockbox](/office365/admin/manage/customer-lockbox-requests) permite um nível de controle de acesso para organizações quando a Microsoft acessa dados. O gerenciamento de acesso privilegiado permite o controle de acesso granular em uma organização para todas Microsoft 365 tarefas privilegiadas.

## <a name="ready-to-get-started"></a>Pronto para começar?

Comece [a configurar sua organização para gerenciamento de acesso privilegiado.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Saiba mais

[Guia interativo: Monitorar e controlar tarefas de administrador com gerenciamento de acesso privilegiado](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
