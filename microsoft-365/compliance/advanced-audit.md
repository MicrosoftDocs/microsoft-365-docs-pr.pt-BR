---
title: Auditoria Avançada no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: A Auditoria Avançada no Microsoft 365 fornece novos recursos de auditoria para ajudar sua organização com investigações forenses e de conformidade.
ms.openlocfilehash: 79c7e24349d3b6603e82946fda4a3c1f0c0ae6ff
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170511"
---
# <a name="advanced-audit-in-microsoft-365"></a>Auditoria Avançada no Microsoft 365

A [funcionalidade de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) no Microsoft 365 oferece às organizações a visibilidade de vários tipos de atividades auditadas em vários serviços do Microsoft 365. Agora, com o lançamento da Auditoria Avançada no Microsoft 365, estamos adicionando novos recursos de auditoria que podem ajudar sua organização nas investigações forenses e de conformidade.

> [!NOTE]
> A Auditoria Avançada está disponível para organizações com uma assinatura do Office 365 ou Microsoft 365 Enterprise E5. Além disso, uma assinatura de complemento do Microsoft 365 E5 Compliance pode ser atribuída aos usuários quando o licenciamento por usuário for necessário aos recursos de Auditoria avançada, como é o caso da retenção a longo prazo dos logs de auditoria e do acesso a eventos cruciais de investigações.

Este artigo fornece uma visão geral desses recursos de Auditoria Avançada.

## <a name="long-term-retention-of-audit-logs"></a>Retenção a longo prazo de logs de auditoria

A Auditoria Avançada mantém todos os registros de auditoria do Exchange, SharePoint e Azure Active Directory por um ano. Isso é feito por uma política de retenção de log de auditoria padrão que mantém qualquer registro de auditoria que contenha o valor **Exchange**, **SharePoint**ou **AzureActiveDirectory** da propriedade **Carga de trabalho** (que indica o serviço em que a atividade ocorreu) por um ano. Isso pode ajudar nas investigações forenses ou de conformidade em andamento. Para saber mais, confira a seção "Política de retenção de log de auditoria padrão" em [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md#default-audit-log-retention-policy).

## <a name="audit-log-retention-policies"></a>Políticas de retenção de log de auditoria

Todos os registros de auditoria gerados em outros serviços que não são cobertos pela política de retenção de log de auditoria padrão (descrita na seção anterior) são retidos por 90 dias. No entanto, agora você pode criar políticas de retenção de logs de auditoria personalizadas para manter outros registros de auditoria por até um ano. Você pode criar uma política para manter registros de auditoria com base em um ou mais dos seguintes critérios:

- O serviço do Microsoft 365 em que as atividades auditadas ocorrem

- Atividades auditadas específicas

- O usuário que executa uma atividade auditada

Você também pode especificar por quanto tempo deseja manter registros de auditoria que correspondam à política e a um nível de prioridade, para que políticas específicas tenham prioridade sobre outras políticas. Observe também que qualquer política de retenção de log de auditoria personalizada terá precedência sobre a política de retenção de auditoria padrão, caso você precise reter registros de auditoria do Exchange, SharePoint ou Azure Active Directory por menos de um ano para alguns ou todos os usuários em sua organização. Para saber mais, confira [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md).

## <a name="access-to-crucial-events-for-investigations"></a>Acesso aos eventos cruciais de investigações

Eventos cruciais de auditoria relacionados à segurança e conformidade são aqueles que podem ajudá-lo a investigar possíveis violações ou outras investigações forenses. O primeiro evento de alto valor que estamos lançando é o evento de auditoria de caixa de correio *MailItemsAccessed*. Este evento é acionado quando os dados de email são acessados ​​por protocolos e clientes de email. O evento MailItemsAccessed pode ajudar os investigadores a identificar violações de dados e determinar o escopo das mensagens que podem ter sido comprometidas. Se um invasor obtiver acesso às mensagens de email, o evento MailItemsAccessed será acionado mesmo se não houver sinal explícito de que foi realmente lido (em outras palavras, o tipo de acesso, como via associação ou sincronização, é registrado no registro de auditoria).

A nova ação da caixa de correio MailItemsAccessed substitui o MessageBind no log de auditoria da caixa de correio do Exchange Online e fornece os seguintes aprimoramentos:

- O MessageBind era configurável apenas para o tipo de logon do usuário AuditAdmin; não se aplicava a ações de representante ou de proprietário. O MailItemsAccessed se aplica a todos os tipos de logon.

- O MessageBind abrangia apenas o acesso por um cliente de email. Não se aplicava a atividades de sincronização. Os eventos MailItemsAccessed são disparados pelos tipos de acesso de ligação e sincronização.

- As ações MessageBind acionariam vários registros de auditoria a serem criados quando a mesma mensagem de email fosse acessada, o que resultava em "ruído" de auditoria. Por outro lado, os eventos MailItemsAccessed são agregados em menos registros de auditoria.

Para obter mais informações sobre o log de auditoria de caixa de correio, confira [Gerenciar a auditoria de caixa de correio](enable-mailbox-auditing.md).

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Acesso de alta largura de banda à API da Atividade de Gerenciamento do Office 365

As organizações que acessam logs de auditoria por meio da API da Atividade de Gestão do Office 365 foram restritas pelos limites no nível do editor. Isso significa que, para um editor obter dados em nome de vários clientes, o limite foi compartilhado por todos esses clientes.

Com o lançamento da Auditoria Avançada, passamos de um limite de nível de editor para um limite de nível de locatário. O resultado é que todas as organizações terão sua própria cota de largura de banda totalmente alocada para acessar os dados de auditoria. A largura de banda não é um limite estático predefinido, mas é modelada em uma combinação de fatores, incluindo o número de assentos na organização e que as organizações E5 terão mais largura de banda do que as organizações que não são E5.

Todas as organizações alocam inicialmente uma linha de base de 2.000 solicitações por minuto. Esse limite aumentará dinamicamente de acordo com a contagem de assentos de uma organização e de sua assinatura de licenciamento. As organizações E5 terão aproximadamente o dobro da largura de banda que as organizações que não são E5. Também haverá limite máximo quanto à largura de banda para proteger a integridade do serviço.

Para mais informações, confira a seção "limitação da API" em [Referência da API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling).
