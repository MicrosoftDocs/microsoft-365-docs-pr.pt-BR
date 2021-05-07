---
title: Remover um ex-funcionário - Visão geral
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga as etapas nesta solução para remover um ex-funcionário do Microsoft 365 e proteger os dados da sua organização.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241731"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="c9ba8-103">Visão geral: remover um ex-funcionário e proteger dados</span><span class="sxs-lookup"><span data-stu-id="c9ba8-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="c9ba8-104">Uma pergunta que muitas vezes fazemos é: "O que devo fazer para proteger os dados e proteger o acesso quando um funcionário sai da minha organização?"</span><span class="sxs-lookup"><span data-stu-id="c9ba8-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="c9ba8-105">Esta série de artigos explica como bloquear o acesso ao Microsoft 365, as etapas que você deve seguir para proteger seus dados e como permitir que outros funcionários acessem os dados.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="c9ba8-106">Assista a um breve vídeo sobre como remover um funcionário.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="c9ba8-107">Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="c9ba8-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="c9ba8-108">Para impedir que um funcionário entre em log:</span><span class="sxs-lookup"><span data-stu-id="c9ba8-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="c9ba8-109">No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="c9ba8-110">Selecione a caixa ao lado do nome do usuário e selecione **Redefinir senha**.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="c9ba8-111">Insira uma nova senha e selecione **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="c9ba8-112">(Não envie para eles.)</span><span class="sxs-lookup"><span data-stu-id="c9ba8-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="c9ba8-113">Selecione o nome do usuário para ir para o  painel de propriedades e, na guia Conta, selecione **Iniciar saída**.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="c9ba8-114">Você precisa ser um administrador global para iniciar a saída.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="c9ba8-115">Dentro de uma hora - ou depois de sair da página Microsoft 365 atual em que estão - eles são solicitados a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="c9ba8-116">Um token de acesso é bom para uma hora, portanto, a linha do tempo depende de quanto tempo resta nesse token e se eles navegam para fora de sua página da Web atual.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9ba8-117">Embora nós numeramos as etapas desta solução e você não precisa concluir a solução usando a ordem exata, recomendamos fazer as etapas dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c9ba8-118">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c9ba8-118">Before you begin</span></span>

<span data-ttu-id="c9ba8-119">Você precisa ser um administrador global para concluir as etapas nesta solução.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9ba8-120">**Etapa**</span><span class="sxs-lookup"><span data-stu-id="c9ba8-120">**Step**</span></span> <br/> |<span data-ttu-id="c9ba8-121">**Por que fazer isso**</span><span class="sxs-lookup"><span data-stu-id="c9ba8-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="c9ba8-122">Etapa 1 - Impedir que um ex-funcionário entre e bloqueie o acesso aos serviços Microsoft 365 serviços</span><span class="sxs-lookup"><span data-stu-id="c9ba8-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="c9ba8-123">Isso impede que seu ex-funcionário entre no Microsoft 365 e impede que a pessoa acesse Microsoft 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="c9ba8-124">Etapa 2 : Salvar o conteúdo da caixa de correio de um ex-funcionário</span><span class="sxs-lookup"><span data-stu-id="c9ba8-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="c9ba8-125">Isso é útil para a pessoa que assumirá o trabalho do funcionário ou se houver litígio.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="c9ba8-126">Etapa 3 - Encaminhar o email de um ex-funcionário para outro funcionário ou converter em uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="c9ba8-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="c9ba8-p104">Isso permite manter o endereço de email do ex-funcionário ativo. Se clientes ou parceiros ainda enviarem emails ao endereço de email do ex-funcionário, isso os encaminhará para a pessoa que assumir o trabalho.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="c9ba8-129">Etapa 4 - Dar a outro funcionário acesso aos OneDrive e Outlook dados</span><span class="sxs-lookup"><span data-stu-id="c9ba8-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="c9ba8-130">Quando você remove apenas a licença e não exclui a conta do usuário, o conteúdo do OneDrive permanece acessível para você mesmo após os 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="c9ba8-131">Antes de excluir a conta, você deve dar acesso às OneDrive e Outlook a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="c9ba8-132">Depois de excluir a conta de um funcionário, o conteúdo no OneDrive e Outlook é mantido por **30** dias.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="c9ba8-133">Durante esses 30 dias, no entanto, você pode restaurar a conta do usuário e obter acesso ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="c9ba8-134">Se você restaurar a conta do usuário, o OneDrive e Outlook conteúdo permanecerá acessível a você mesmo após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="c9ba8-135">Etapa 5 - Apagar e bloquear o dispositivo móvel de um ex-funcionário</span><span class="sxs-lookup"><span data-stu-id="c9ba8-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="c9ba8-136">Remove seus dados comerciais do telefone ou tablet.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="c9ba8-137">Etapa 6 - Remover e excluir a Microsoft 365 de um ex-funcionário</span><span class="sxs-lookup"><span data-stu-id="c9ba8-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="c9ba8-p106">Ao remover uma licença, você pode atribuí-la a outra pessoa. Ou pode excluir a licença para não pagar por ela até contratar outra pessoa.  </span><span class="sxs-lookup"><span data-stu-id="c9ba8-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="c9ba8-p107">Quando você remove ou exclui uma licença, o antigo email, contatos e calendário do usuário são mantidos por **30 dias** e, em seguida, excluídos permanentemente. Se você remover ou excluir a licença, mas não excluir a conta do usuário, o conteúdo do OneDrive permanecerá acessível para você mesmo após os 30 dias.  </span><span class="sxs-lookup"><span data-stu-id="c9ba8-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="c9ba8-142">Etapa 7 - Excluir a conta de usuário de um ex-funcionário</span><span class="sxs-lookup"><span data-stu-id="c9ba8-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="c9ba8-143">Isso remove a conta do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-143">This removes the account from your admin center.</span></span> <span data-ttu-id="c9ba8-144">Mantenha as coisas organizadas.</span><span class="sxs-lookup"><span data-stu-id="c9ba8-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="c9ba8-145">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c9ba8-145">Related articles</span></span>

[<span data-ttu-id="c9ba8-146">Restaurar um usuário</span><span class="sxs-lookup"><span data-stu-id="c9ba8-146">Restore a user</span></span>](restore-user.md)
