---
title: 'Etapa 13: Monitorar a atividade de entrada e do locatário'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar os relatórios de uso e acesso do Azure AD.
ms.openlocfilehash: 997d52bc11036e1dbb7dcc6e1f9f48a59b2ddbf5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864665"
---
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a>Etapa 13: Monitorar a atividade de entrada e do locatário

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

Nesta etapa, você vai revisar os logs de auditoria e a atividade de entrada usando os relatórios do Azure AD. Estão disponíveis dois tipos de relatório.

O **relatório de atividade de logs de auditoria** registra o histórico de todas as tarefas realizadas em seu locatário do Azure AD. Esse relatório responde a perguntas como:

- Quem adicionou uma pessoa a um grupo de administração?
- Que usuários estão se conectando em um aplicativo específico?
- Quantas redefinições de senhas estão ocorrendo?

O **relatório de atividade de entradas** registra quem executou as tarefas relatadas pelo relatório de logs de auditoria. Esse relatório responde a perguntas como:

- Qual é o padrão de entrada de um usuário específico que está sob investigação?
- Qual é o volume de entradas em um dia, uma semana ou um mês?
- Quantas dessas tentativas de entrada não foram bem-sucedidas, e em que contas ocorreram?

Para saber mais sobre os relatórios e como acessá-los, consulte as informações sobre os [relatórios do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).

Como resultado desta etapa, você ficará ciente desses relatórios e saberá como usá-los para obter informações de atividades e eventos ocorridos no Azure AD para poder planejar a segurança.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [Permitir que usuários criem e gerenciem os próprios grupos](identity-self-service-group-management.md) |
