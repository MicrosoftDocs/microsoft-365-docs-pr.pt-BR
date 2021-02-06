---
title: Saiba mais sobre o gerenciamento de acesso privilegiado
description: Este artigo fornece uma visão geral sobre o gerenciamento de acesso privilegiado no Microsoft 365, incluindo respostas para perguntas frequentes.
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

O gerenciamento de acesso privilegiado permite o controle de acesso granular sobre tarefas de administração privilegiadas no Office 365. Ele pode ajudar a proteger sua organização contra violações que usam contas de administrador privilegiadas existentes com acesso permanente a dados confidenciais ou acesso a configurações críticas. O gerenciamento de acesso privilegiado requer que os usuários solicitem acesso just-in-time para concluir tarefas elevadas e privilegiadas por meio de um fluxo de trabalho de aprovação com escopo altamente delimitado e com limite de tempo. Essa configuração oferece aos usuários acesso suficiente para executar a tarefa em mãos, sem exposição desnecessária de dados confidenciais ou definições de configuração críticas. A habilitação do gerenciamento de acesso privilegiado no Microsoft 365 permite que sua organização opere com zero privilégios permanentes e forneça uma camada de defesa contra vulnerabilidades permanentes de acesso administrativo.

Para uma rápida visão geral do Sistema de Bloqueio do Cliente integrado e do fluxo de trabalho de gerenciamento de acesso privilegiado, consulte este Vídeo de gerenciamento de acesso privilegiado e Sistema de Bloqueio de [Cliente.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Camadas de proteção

O gerenciamento de acesso privilegiado complementa outras proteções de recursos de acesso e dados dentro da arquitetura de segurança do Microsoft 365. Incluir o gerenciamento de acesso privilegiado como parte de uma abordagem integrada e em camadas para a segurança fornece um modelo de segurança que maximiza a proteção de informações confidenciais e as definições de configuração do Microsoft 365. Conforme mostrado no diagrama, o gerenciamento de acesso privilegiado se baseia na proteção fornecida com criptografia nativa de dados do Microsoft 365 e no modelo de segurança de controle de acesso baseado em função dos serviços do Microsoft 365. Quando usados com o [Azure AD Privileged Identity Management,](/azure/active-directory/active-directory-privileged-identity-management-configure)esses dois recursos fornecem controle de acesso com acesso just-in-time em escopos diferentes.

![Proteção em camadas no Microsoft 365](../media/pam-layered-protection.png)

O gerenciamento de acesso privilegiado  é definido e com escopo no nível da tarefa, enquanto o Azure AD Privileged Identity Management aplica proteção no nível da função com a capacidade de executar várias tarefas.  O Azure AD Privileged Identity Management permite principalmente o gerenciamento de acessos para funções e grupos de funções do AD, enquanto o gerenciamento de acesso privilegiado no Microsoft 365 só se aplica no nível da tarefa.

- **Habilitando o gerenciamento de acesso privilegiado ao usar o Azure AD Privileged Identity Management:** A adição do gerenciamento de acesso privilegiado fornece outra camada granular de recursos de proteção e auditoria para acesso privilegiado aos dados do Microsoft 365.

- **Habilitando o Azure AD Privileged Identity Management enquanto já usa o gerenciamento de acesso privilegiado no Office 365:**  Adicionar o Azure AD Privileged Identity Management ao gerenciamento de acesso privilegiado pode estender o acesso privilegiado a dados fora do Microsoft 365 que são definidos principalmente por funções de usuário ou identidade.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitetura de gerenciamento de acesso privilegiado e fluxo de processos

Cada um dos fluxos de processo a seguir descreve a arquitetura do acesso privilegiado e como ele interage com o substrate do Microsoft 365, a auditoria e o runspace gerenciamento do Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Etapa 1: Configurar uma política de acesso privilegiado

Ao configurar uma política de acesso privilegiado com o Centro de administração do [Microsoft 365](https://admin.microsoft.com) ou o PowerShell de Gerenciamento do Exchange, você define a política, os processos de recurso de acesso privilegiado e os atributos de política no substrate do Microsoft 365. As atividades são registradas no Centro de Conformidade &amp; de Segurança. A política agora está habilitada e pronta para lidar com solicitações de entrada para aprovações.

![Etapa 1: Criação de política](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Etapa 2: Solicitação de acesso

No Centro [de administração do Microsoft 365](https://admin.microsoft.com) ou com o PowerShell de Gerenciamento do Exchange, os usuários podem solicitar acesso a tarefas elevadas ou privilegiadas. O recurso de acesso privilegiado envia a solicitação ao substrate do Microsoft 365 para processamento em relação à política de acesso a privilégios configurados e registra a Atividade nos logs do Centro de Conformidade &amp; de Segurança.

![Etapa 2: Solicitação de acesso](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Etapa 3: Aprovação de acesso

Uma solicitação de aprovação é gerada e a notificação de solicitação pendente é enviada por email aos aprovadores. Se aprovado, a solicitação de acesso privilegiado é processada como uma aprovação e a tarefa está pronta para ser concluída. Se for negada, a tarefa será bloqueada e nenhum acesso será concedido ao solicitante. O solicitante é notificado sobre a aprovação ou negação de solicitação via mensagem de email.

![Etapa 3: Aprovação de acesso](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Etapa 4: Acessar o processamento

Para uma solicitação aprovada, a tarefa é processada pelo runspace gerenciamento do Exchange. A aprovação é verificada em relação à política de acesso privilegiado e processada pelo substrate do Microsoft 365. Todas as atividades da tarefa são registradas no Centro de Conformidade &amp; de Segurança.

![Etapa 4: Acessar o processamento](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Quais SKUs podem usar o acesso privilegiado no Office 365?

O gerenciamento de acesso privilegiado está disponível para clientes para uma ampla seleção de assinaturas e complementos do Microsoft 365 e office 365. Consulte [Começar a trabalhar com o gerenciamento de acesso privilegiado](privileged-access-management-configuration.md) para obter detalhes.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Quando o acesso privilegiado dará suporte a cargas de trabalho do Office 365 além do Exchange?

O gerenciamento de acesso privilegiado estará disponível em outras cargas de trabalho do Office 365 em breve. Visite o [Mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obter mais detalhes.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Minha organização precisa de mais de 30 políticas de acesso privilegiado, esse limite será aumentado?

Sim, aumentar o limite atual de 30 políticas de acesso privilegiado por organização está no mapa de recursos.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Preciso ser um Administrador Global para gerenciar o acesso privilegiado no Office 365?

Não, você precisa da função Gerenciamento de Função do Exchange atribuída a contas que gerenciam o acesso privilegiado no Office 365. Se você não quiser configurar a função gerenciamento de função como uma permissão de conta autônomo, a função de Administrador Global inclui essa função por padrão e pode gerenciar o acesso privilegiado. Os usuários incluídos em um grupo de aprovadores não precisam ser administradores globais ou ter a função de Gerenciamento de Função atribuída para analisar e aprovar solicitações com o PowerShell.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Como o gerenciamento de acesso privilegiado está relacionado ao Sistema de Bloqueio do Cliente?

[O Sistema de Proteção de](/office365/admin/manage/customer-lockbox-requests) Dados do Cliente permite um nível de controle de acesso para organizações quando a Microsoft acessa dados. O gerenciamento de acesso privilegiado permite o controle de acesso granular em uma organização para todas as tarefas privilegiadas do Microsoft 365.

## <a name="ready-to-get-started"></a>Pronto para começar?

Comece [a configurar sua organização para gerenciamento de acesso privilegiado.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Saiba mais

[Guia interativo: Monitorar e controlar tarefas de administrador com gerenciamento de acesso privilegiado](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
