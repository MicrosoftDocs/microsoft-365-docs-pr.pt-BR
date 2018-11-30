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
# <a name="step-13-monitor-tenant-and-sign-in-activity"></a><span data-ttu-id="5ed00-103">Etapa 13: Monitorar a atividade de entrada e do locatário</span><span class="sxs-lookup"><span data-stu-id="5ed00-103">Step 13: Monitor tenant and sign-in activity</span></span>

<span data-ttu-id="5ed00-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="5ed00-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5ed00-p101">Nesta etapa, você vai revisar os logs de auditoria e a atividade de entrada usando os relatórios do Azure AD. Estão disponíveis dois tipos de relatório.</span><span class="sxs-lookup"><span data-stu-id="5ed00-p101">In Step 13, you'll review audit logs and sign-in activity using Azure AD reporting. Two types of reports are available.</span></span>

<span data-ttu-id="5ed00-p102">O **relatório de atividade de logs de auditoria** registra o histórico de todas as tarefas realizadas em seu locatário do Azure AD. Esse relatório responde a perguntas como:</span><span class="sxs-lookup"><span data-stu-id="5ed00-p102">The **Audit logs activity report** records the history of every task performed in your Azure AD tenant. This report answers questions like:</span></span>

- <span data-ttu-id="5ed00-109">Quem adicionou uma pessoa a um grupo de administração?</span><span class="sxs-lookup"><span data-stu-id="5ed00-109">Who added someone to an admin group?</span></span>
- <span data-ttu-id="5ed00-110">Que usuários estão se conectando em um aplicativo específico?</span><span class="sxs-lookup"><span data-stu-id="5ed00-110">Which users are signing into a specific app?</span></span>
- <span data-ttu-id="5ed00-111">Quantas redefinições de senhas estão ocorrendo?</span><span class="sxs-lookup"><span data-stu-id="5ed00-111">How many password resets are happening?</span></span>

<span data-ttu-id="5ed00-p103">O **relatório de atividade de entradas** registra quem executou as tarefas relatadas pelo relatório de logs de auditoria. Esse relatório responde a perguntas como:</span><span class="sxs-lookup"><span data-stu-id="5ed00-p103">The **Sign-ins activity report** records who performed the tasks reported by the audit logs report. This report answers questions like:</span></span>

- <span data-ttu-id="5ed00-114">Qual é o padrão de entrada de um usuário específico que está sob investigação?</span><span class="sxs-lookup"><span data-stu-id="5ed00-114">For a specific user under investigation, what is their sign-in pattern?</span></span>
- <span data-ttu-id="5ed00-115">Qual é o volume de entradas em um dia, uma semana ou um mês?</span><span class="sxs-lookup"><span data-stu-id="5ed00-115">What is my volume of sign-ins over a day, week, or month?</span></span>
- <span data-ttu-id="5ed00-116">Quantas dessas tentativas de entrada não foram bem-sucedidas, e em que contas ocorreram?</span><span class="sxs-lookup"><span data-stu-id="5ed00-116">How many of these sign-in attempts were not successful, and for which accounts?</span></span>

<span data-ttu-id="5ed00-117">Para saber mais sobre os relatórios e como acessá-los, consulte as informações sobre os [relatórios do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="5ed00-117">For more information about the reports and how to access them, see [Azure Active Directory reporting](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-azure-portal).</span></span>

<span data-ttu-id="5ed00-118">Como resultado desta etapa, você ficará ciente desses relatórios e saberá como usá-los para obter informações de atividades e eventos ocorridos no Azure AD para poder planejar a segurança.</span><span class="sxs-lookup"><span data-stu-id="5ed00-118">As a result of this step, you'll gain awareness of these reports and an understanding of how you can use them to gain insights on Azure AD events and activities for planning and security purposes.</span></span>

## <a name="next-step"></a><span data-ttu-id="5ed00-119">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5ed00-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step14.png)| [<span data-ttu-id="5ed00-120">Permitir que usuários criem e gerenciem os próprios grupos</span><span class="sxs-lookup"><span data-stu-id="5ed00-120">Allow users to create and manage their own groups</span></span>](identity-self-service-group-management.md) |
