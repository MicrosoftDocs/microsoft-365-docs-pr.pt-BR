---
title: Gerenciamento de acesso privilegiado no Office 365
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
description: Use este tópico para saber mais sobre o gerenciamento de acesso privilegiado no Office 365
ms.openlocfilehash: 0c9d8ba22f57c7f6a576f1995e8df92be7478073
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597728"
---
# <a name="privileged-access-management-in-office-365"></a>Gerenciamento de acesso privilegiado no Office 365

> [!IMPORTANT]
> Este tópico aborda as diretrizes de implantação e configuração dos recursos disponíveis atualmente no Office 365 E5 e nas SKUs de conformidade avançada.

O gerenciamento de acesso privilegiado permite o controle de acesso granular sobre tarefas administrativas privilegiadas no Office 365. Ele pode ajudar a proteger sua organização contra violações que usam contas de administrador privilegiadas existentes com acesso à dados confidenciais ou acesso a definições de configuração crítica. O gerenciamento de acesso privilegiado requer que os usuários solicitem acesso just-in-time para concluir tarefas privilegiadas e privilegiadas por meio de um fluxo de trabalho de aprovação com e sem limite de tempo. Isso permite que os usuários tenham acesso apenas o suficiente para executar a tarefa em mãos, sem risco de exposição de dados confidenciais ou definições de configuração crítica. Habilitar o gerenciamento de acesso privilegiado no Office 365 permite que sua organização opere com nenhum privilégio de pé e forneça uma camada de defesa contra vulnerabilidades de acesso administrativo.

Para obter uma visão geral rápida do fluxo de trabalho integrado de gerenciamento de acesso privilegiado e de lockbox do cliente, confira o [Gerenciamento de acesso privilegiado e de lockbox do cliente no Office 365 Video](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Camadas de proteção

O gerenciamento de acesso privilegiado complementa outras proteções de recursos de dados e acesso dentro da arquitetura de segurança do Office 365. A inclusão de gerenciamento de acesso privilegiado como parte de uma abordagem integrada e em camadas à segurança fornece um modelo de segurança que maximiza a proteção de informações confidenciais e definições de configuração do Office 365. Conforme mostrado no diagrama, o gerenciamento de acesso privilegiado se baseia na proteção fornecida com a criptografia nativa dos dados do Office 365 e o modelo de segurança de controle de acesso baseado em função dos serviços do Office 365. Quando usado com o [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), esses dois recursos fornecem controle de acesso com acesso just-in-time em escopos diferentes.

![Proteção em camadas no Office 365](media/pam-layered-protection.png)

O gerenciamento de acesso privilegiado no Office 365 é definido e escopo no nível da **tarefa** , enquanto o gerenciamento de identidade privilegiada do Azure ad aplica proteção no nível da **função** com a capacidade de executar várias tarefas. O gerenciamento de identidade privilegiada do Azure AD permite principalmente o gerenciamento de acessos para funções do AD e grupos de função, enquanto o gerenciamento de acesso privilegiado no Office 365 aplica-se apenas no nível da tarefa.

- **Habilitando o gerenciamento de acesso privilegiado no Office 365 enquanto já estava usando o gerenciamento de identidade privilegiada do Azure AD:** A adição de gerenciamento de acesso privilegiado no Office 365 fornece outra camada granular de recursos de proteção e auditoria para acesso privilegiado aos dados do Office 365.

- **Habilitar o Azure ad Privileged Identity Management enquanto já usa o gerenciamento de acesso privilegiado no Office 365:**  Adicionar o Azure AD Privileged Identity Management ao gerenciamento de acesso privilegiado no Office 365 pode estender o acesso privilegiado a dados fora do Office 365, que é definido principalmente por funções de usuário ou identidade.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Arquitetura de gerenciamento de acesso privilegiado e fluxo de processo

Cada um dos fluxos de processo a seguir descreve a arquitetura de acesso privilegiado e como ele interage com o substrato do Office 365, a auditoria do Office 365 e o espaço de gerenciamento do Exchange.

### <a name="step-1-configure-a-privileged-access-policy"></a>Etapa 1: configurar uma política de acesso privilegiado

Quando você configura uma política de acesso privilegiada com o [centro de administração do Microsoft 365](https://admin.microsoft.com) ou o PowerShell de gerenciamento do Exchange, você define a política e os processos de recurso de acesso privilegiado e os atributos de política no substrato do Office 365. As atividades são registradas no centro de segurança e conformidade do Office 365. A política agora está habilitada e pronta para lidar com solicitações de entrada para aprovações.

![Etapa 1: criação de política](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Etapa 2: solicitação de acesso

No [centro de administração do Microsoft 365](https://admin.microsoft.com) ou com o PowerShell de gerenciamento do Exchange, os usuários podem solicitar acesso a tarefas privilegiadas ou privilegiadas. O recurso de acesso privilegiado envia a solicitação para o substrato do Office 365 para processamento com a política de acesso de privilégio configurada e registra a atividade nos logs do centro de conformidade e segurança do Office 365.

![Etapa 2: solicitação de acesso](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Etapa 3: aprovação do acesso

Uma solicitação de aprovação é gerada e a notificação de solicitação pendente é enviada por email aos aprovadores. Se for aprovada, a solicitação de acesso privilegiado será processada como uma aprovação e a tarefa estará pronta para ser concluída. Se negado, a tarefa é bloqueada e nenhum acesso é concedido ao solicitante. O solicitante é notificado sobre a aprovação da solicitação ou a negação via mensagem de email.

![Etapa 3: aprovação do acesso](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Etapa 4: processamento de acesso

Para uma solicitação aprovada, a tarefa é processada pelo runspace de gerenciamento do Exchange. A aprovação é verificada em relação à política de acesso privilegiado e processada pelo substrato do Office 365. Todas as atividades da tarefa são registradas no centro de segurança e conformidade do Office 365.

![Etapa 4: processamento de acesso](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Quais SKUs podem usar o acesso privilegiado no Office 365?
O gerenciamento de acesso privilegiado está disponível para clientes com SKUs de conformidade avançada e do Office 365 e5.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Quando o acesso privilegiado será compatível com cargas de trabalho do Office 365 além do Exchange?
O gerenciamento de acesso privilegiado estará disponível em outras cargas de trabalho do Office 365 em breve. Visite o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para obter mais detalhes.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Minha organização precisa de mais de 30 políticas de acesso privilegiado, esse limite será aumentado?
Sim, a geração do limite atual de 30 políticas de acesso privilegiado por organização do Office 365 está no roteiro do recurso.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Preciso ser um administrador global para gerenciar o acesso privilegiado no Office 365?
Não, você precisa da função de gerenciamento de função do Exchange atribuída às contas que gerenciam o acesso privilegiado no Office 365. Se você não quiser configurar a função de gerenciamento de função como uma permissão de conta autônoma, a função de administrador global inclui essa função por padrão e pode gerenciar o acesso privilegiado. Os usuários incluídos em um grupo de aprovadores não precisam ser um administrador global ou ter a função de gerenciamento de função atribuída para revisar e aprovar solicitações.

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>Como o gerenciamento de acesso privilegiado no Office 365 está relacionado ao Lockbox do cliente?
O [Lockbox de cliente](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) permite um nível de controle de acesso para organizações quando o Microsoft acessa dados. O gerenciamento de acesso privilegiado no Office 365 permite o controle de acesso granular dentro de uma organização para todas as tarefas privilegiadas do Office 365.

## <a name="ready-to-get-started"></a>Pronto para começar?

Comece [a configurar sua organização para o gerenciamento de acesso privilegiado](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Saiba mais

[Guia interativo: monitorar e controlar as tarefas do administrador com gerenciamento de acesso privilegiado](https://content.cloudguides.com/guides/Privileged%20Access%20Management)