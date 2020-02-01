---
title: 'Executar um relatório de grupo de função de administrador no EOP '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Os administradores podem aprender a executar um relatório de grupo de funções de administrador no Exchange Online Protection (EOP). Este relatório registra quando um administrador adiciona ou remove membros dos grupos de função de administrador, o Microsoft proteção do Exchange Online (EOP) registra cada ocorrência.
ms.openlocfilehash: d9e7db8accae259b3eb332ce17c52c6749c2bec2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598538"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a><span data-ttu-id="5c6b9-104">Executar um relatório de grupo de função de administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="5c6b9-104">Run an administrator role group report in EOP</span></span>

 <span data-ttu-id="5c6b9-105">Quando um administrador adiciona ou remove membros dos grupos de funções de administrador, o Exchange Online Protection (EOP) registra cada ocorrência.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-105">When an admin adds members to or removes members from administrator role groups, Exchange Online Protection (EOP) logs each occurrence.</span></span> <span data-ttu-id="5c6b9-106">Quando você executa um relatório de grupo de funções de administrador no centro de administração do Exchange (Eat), as entradas são exibidas como resultados de pesquisa e incluem os grupos de função afetados, quem alterou a associação do grupo de função e quando e quais foram feitas as atualizações de associação.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-106">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="5c6b9-107">Use esse relatório para monitorar as alterações nas permissões administrativas atribuídas aos usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-107">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5c6b9-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="5c6b9-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5c6b9-109">Tempo estimado para conclusão: 2 minutos</span><span class="sxs-lookup"><span data-stu-id="5c6b9-109">Estimated time to complete: 2 minutes</span></span>

- <span data-ttu-id="5c6b9-110">Para abrir o centro de administração do Exchange, confira [Exchange Admin Center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b9-110">To open the Exchange admin center, see [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5c6b9-p103">Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver de que permissões você precisa, consulte o Seção "Relatórios" do tópico [Permissões de recurso no EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b9-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Reports" section of the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span>

- <span data-ttu-id="5c6b9-113">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="5c6b9-113">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="5c6b9-114">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="5c6b9-114">Having problems?</span></span> <span data-ttu-id="5c6b9-115">Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="5c6b9-115">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="5c6b9-116">Usar o EAC para executar o relatório de grupo de funções de administrador</span><span class="sxs-lookup"><span data-stu-id="5c6b9-116">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="5c6b9-117">Execute o relatório do grupo de funções de administrador para localizar as alterações nos grupos de função de gerenciamento em sua organização dentro de um determinado período.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-117">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="5c6b9-118">No EAC, navegue até **Gerenciamento de conformidade** \> **Auditoria** e escolha **Executar o relatório do grupo de funções do administrador**.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-118">In the EAC, navigate to **Compliance management** \> **Auditing**, and choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="5c6b9-p105">Escolha a **Data de início** e a **Data de término**. Por padrão, o relatório procura alterações feitas nos grupos de funções do administrador nas duas últimas semanas.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-p105">Choose the **Start date** and **End date**. By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

3. <span data-ttu-id="5c6b9-p106">Para exibir as alterações de um grupo de funções específico, clique em **Selecionar grupos de função**. Selecione o grupo de função (ou grupos) na caixa de diálogo subsequente e clique em **OK**. Você também pode deixar o campo em branco para encontrar todos os grupos de função alterados.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-p106">To view the changes for a specific role group, click **Select role groups**. Select the role group (or groups) in the subsequent dialog box, and click **OK**. You can also leave the field blank to find all changed role groups.</span></span>

4. <span data-ttu-id="5c6b9-124">Clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-124">Click **Search**.</span></span>

<span data-ttu-id="5c6b9-p107">Se quaisquer alterações forem encontradas usando os critérios especificados, elas aparecerão no painel de resultados. Clique em um grupo de função nos resultados da pesquisa para ver as alterações no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-p107">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5c6b9-127">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="5c6b9-127">How do you know this worked?</span></span>

<span data-ttu-id="5c6b9-p108">Se você executou com sucesso um relatório de grupo de funções do administrador, os grupos de funções que foram alterados dentro do intervalo de datas serão exibidos no painel de resultados da pesquisa. Se não houver resultados, nenhuma alteração nos grupos de funções será executada dentro do intervalo de datas especificado. Se julgar que deveria haver resultados, altere o intervalo de dados e execute novamente o relatório.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-p108">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="5c6b9-131">Monitorar alterações na associação de grupo de funções</span><span class="sxs-lookup"><span data-stu-id="5c6b9-131">Monitor changes to role group membership</span></span>

<span data-ttu-id="5c6b9-p109">Quando os membros são adicionados ou removidos de um grupo de funções, os resultados da pesquisa exibidos no painel de detalhes indicam que a associação de grupo de funções foi atualizada e lista os membros atuais. Os resultados não informam explicitamente qual usuário foi adicionado ou removido.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-p109">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="5c6b9-p110">Para determinar se um usuário foi adicionado ou removido, você terá que comparar duas entradas separadas no relatório. Por exemplo, vamos observar as entradas de log a seguir do grupo de funções de **HelpDesk**:</span><span class="sxs-lookup"><span data-stu-id="5c6b9-p110">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="5c6b9-136">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="5c6b9-136">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="5c6b9-137">Administrador</span><span class="sxs-lookup"><span data-stu-id="5c6b9-137">Administrator</span></span> <br> <span data-ttu-id="5c6b9-138">Membros atualizados: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="5c6b9-138">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="5c6b9-139">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="5c6b9-139">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="5c6b9-140">Administrador</span><span class="sxs-lookup"><span data-stu-id="5c6b9-140">Administrator</span></span> <br> <span data-ttu-id="5c6b9-141">Membros atualizados: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="5c6b9-141">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="5c6b9-142">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="5c6b9-142">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="5c6b9-143">Administrador</span><span class="sxs-lookup"><span data-stu-id="5c6b9-143">Administrator</span></span> <br> <span data-ttu-id="5c6b9-144">Membros atualizados: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="5c6b9-144">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="5c6b9-145">Nesse exemplo, a conta de usuário Administrador fez as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="5c6b9-145">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="5c6b9-146">No 2/06/2018, eles adicionaram o usuário tonip.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-146">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="5c6b9-147">No 2/19/2018, eles removeram o usuário pilarp.</span><span class="sxs-lookup"><span data-stu-id="5c6b9-147">On 2/19/2018, they removed the user pilarp.</span></span>
