---
title: Atualizar listas de distribuição para grupos do Microsoft 365 no Outlook
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Saiba como atualizar uma ou muitas listas de distribuição para grupos do Microsoft 365 no Outlook e como usar o PowerShell para atualizar várias listas de distribuição simultaneamente.
ms.openlocfilehash: ab7c2ff68b1f16915d65fff0d7292e3b3ad72d02
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579237"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="6417e-103">Atualizar listas de distribuição para grupos do Microsoft 365 no Outlook</span><span class="sxs-lookup"><span data-stu-id="6417e-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="6417e-104">Você pode atualizar listas de distribuição para grupos do Microsoft 365 com o Outlook.</span><span class="sxs-lookup"><span data-stu-id="6417e-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="6417e-105">Essa é uma ótima maneira de dar à sua organização listas de todos os recursos e funcionalidades dos Grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6417e-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="6417e-106">Por que você deve atualizar suas listas de distribuição para grupos no Outlook</span><span class="sxs-lookup"><span data-stu-id="6417e-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="6417e-107">Você pode atualizar DLs uma de cada vez ou várias ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6417e-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="6417e-108">Atualizar uma ou muitas listas de distribuição para grupos do Microsoft 365 no Outlook</span><span class="sxs-lookup"><span data-stu-id="6417e-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="6417e-109">Você deve ser um administrador global ou administrador do Exchange para atualizar uma lista de distribuição.</span><span class="sxs-lookup"><span data-stu-id="6417e-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="6417e-110">Para atualizar para grupos do Microsoft 365, um grupo de distribuição deve ter um proprietário com uma caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="6417e-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span>

1. <span data-ttu-id="6417e-111">Vá até o <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administração do Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="6417e-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="6417e-112">No Centro de administração do Exchange, vá para **Grupos de** \> **Destinatários.**</span><span class="sxs-lookup"><span data-stu-id="6417e-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="6417e-113">Você verá um aviso indicando que você tem listas de distribuição (também chamadas de grupos de distribuição **)** que estão qualificadas para serem atualizadas para grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6417e-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="6417e-114">![Selecione o botão Iniciar](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="6417e-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="6417e-115">Selecione uma ou mais listas de distribuição (também chamada de grupo **de distribuição** ) na página **grupos.**</span><span class="sxs-lookup"><span data-stu-id="6417e-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="6417e-116">![Selecionar um grupo de distribuição](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="6417e-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="6417e-117">Selecione o ícone de atualização.</span><span class="sxs-lookup"><span data-stu-id="6417e-117">Select the upgrade icon.</span></span><br/>![Atualizar para o ícone grupos do Microsoft 365](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="6417e-119">Na caixa de diálogo informações, selecione **Sim** para confirmar a atualização.</span><span class="sxs-lookup"><span data-stu-id="6417e-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="6417e-120">O processo começa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="6417e-120">The process begins immediately.</span></span> <span data-ttu-id="6417e-121">Dependendo do tamanho e do número de DLs que você está atualizando, o processo pode levar minutos ou horas.</span><span class="sxs-lookup"><span data-stu-id="6417e-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="6417e-122">Se a lista de distribuição não puder ser atualizada, uma caixa de diálogo aparecerá dizendo isso.</span><span class="sxs-lookup"><span data-stu-id="6417e-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="6417e-123">Veja [Quais listas de distribuição não podem ser atualizadas?](#which-distribution-lists-cant-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="6417e-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="6417e-124">Se você estiver atualizando várias listas de distribuição, use a listada para filtrar quais listas de distribuição foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="6417e-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="6417e-125">Se a lista não estiver concluída, aguarde um pouco mais e selecione **Atualizar** para ver o que foi atualizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="6417e-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="6417e-126">Não há nenhum aviso informando quando o processo de atualização foi concluído para todas as DLs selecionadas.</span><span class="sxs-lookup"><span data-stu-id="6417e-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="6417e-127">Você pode descobrir isso procurando ver o que está listado em Disponível para **atualização** ou **DLs atualizadas.**</span><span class="sxs-lookup"><span data-stu-id="6417e-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="6417e-128">Se você selecionou uma DL para atualização, mas ela ainda aparece na página como Disponível para atualização, então ela falhou ao atualizar.</span><span class="sxs-lookup"><span data-stu-id="6417e-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="6417e-129">Consulte [O que fazer se a atualização não funcionar](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="6417e-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="6417e-130">Se você estiver recebendo os grupos digere emails, você pode notar, na parte inferior, que às vezes ele oferecerá para permitir que você atualize quaisquer listas de distribuição qualificadas das que você é o proprietário.</span><span class="sxs-lookup"><span data-stu-id="6417e-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="6417e-131">Confira [Ter uma conversa em grupo no Outlook para](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) obter mais informações sobre emails de digest.</span><span class="sxs-lookup"><span data-stu-id="6417e-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="6417e-132">O que fazer se a atualização não funcionar</span><span class="sxs-lookup"><span data-stu-id="6417e-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="6417e-133">As listas de distribuição que não conseguem atualizar permanecem inalteradas.</span><span class="sxs-lookup"><span data-stu-id="6417e-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="6417e-134">Se uma ou mais **listas de** distribuição qualificadas não conseguirem ser atualizadas, abra um [tíquete de Suporte](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="6417e-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="6417e-135">O problema precisará ser escalonado para a equipe de Engenharia de Grupos para que eles descubram o problema.</span><span class="sxs-lookup"><span data-stu-id="6417e-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="6417e-136">É possível que a lista de distribuição não tenha se atualizado devido a uma paralisação de serviço, mas muito improvável.</span><span class="sxs-lookup"><span data-stu-id="6417e-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="6417e-137">Se quiser, aguarde um pouco e tente atualizar o DL novamente.</span><span class="sxs-lookup"><span data-stu-id="6417e-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="6417e-138">Como usar o PowerShell para atualizar várias listas de distribuição ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="6417e-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="6417e-139">Se você tiver experiência em usar o PowerShell, talvez queira seguir essa rota em vez de usar a interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="6417e-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="6417e-140">Temos um conjunto de cmdlets que ajudarão você a atualizar listas de distribuição.</span><span class="sxs-lookup"><span data-stu-id="6417e-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="6417e-141">Confira a seguir.</span><span class="sxs-lookup"><span data-stu-id="6417e-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="6417e-142">Atualizar um único DL</span><span class="sxs-lookup"><span data-stu-id="6417e-142">Upgrade a single DL</span></span>

<span data-ttu-id="6417e-143">Para atualizar um único DL, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6417e-143">To upgrade a single DL run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="6417e-144">Por exemplo, se você quiser atualizar uma DLs com endereço SMTP dl1@contoso.com, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6417e-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="6417e-145">Você também pode atualizar uma única lista de distribuição para um grupo do Microsoft 365 usando o cmdlet [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell</span><span class="sxs-lookup"><span data-stu-id="6417e-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="6417e-146">Atualizar várias DLs em um lote</span><span class="sxs-lookup"><span data-stu-id="6417e-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="6417e-147">Você também pode passar várias DLs como um lote e atualiza-las juntas:</span><span class="sxs-lookup"><span data-stu-id="6417e-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="6417e-148">Por exemplo, se você quiser atualizar cinco DLs com endereço SMTP e `dl1@contoso.com` , e , execute o seguinte `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` comando:</span><span class="sxs-lookup"><span data-stu-id="6417e-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="6417e-149">Atualizar todas as DLs qualificadas</span><span class="sxs-lookup"><span data-stu-id="6417e-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="6417e-150">Há duas maneiras de atualizar todas as DLs qualificadas.</span><span class="sxs-lookup"><span data-stu-id="6417e-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="6417e-151">O Upgrade-DistributionGroup cmdlet não recebe dados do pipeline, por esse motivo, é necessário usar o operador "foreach-object" para ser executado com {} êxito.</span><span class="sxs-lookup"><span data-stu-id="6417e-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="6417e-152">Obter as DLs qualificadas no locatário e atualize-as usando o comando de atualização:</span><span class="sxs-lookup"><span data-stu-id="6417e-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="6417e-153">Obter a lista de todas as DLs e atualizar apenas as DLs qualificadas:</span><span class="sxs-lookup"><span data-stu-id="6417e-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="6417e-154">Perguntas frequentes sobre como atualizar listas de distribuição para grupos do Microsoft 365 no Outlook</span><span class="sxs-lookup"><span data-stu-id="6417e-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="6417e-155">Quais listas de distribuição não podem ser atualizadas?</span><span class="sxs-lookup"><span data-stu-id="6417e-155">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="6417e-156">Você só pode atualizar listas de distribuição gerenciadas por nuvem, simples e não aninhadas.</span><span class="sxs-lookup"><span data-stu-id="6417e-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="6417e-157">A tabela a seguir lista listas de distribuição que **NÃO PODEM** ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="6417e-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="6417e-158">**Propriedade**</span><span class="sxs-lookup"><span data-stu-id="6417e-158">**Property**</span></span>|<span data-ttu-id="6417e-159">**Qualificado?**</span><span class="sxs-lookup"><span data-stu-id="6417e-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6417e-160">Lista de distribuição gerenciada local.</span><span class="sxs-lookup"><span data-stu-id="6417e-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="6417e-161">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-161">No</span></span>  <br/> |
|<span data-ttu-id="6417e-162">Listas de distribuição aninhadas.</span><span class="sxs-lookup"><span data-stu-id="6417e-162">Nested distribution lists.</span></span> <span data-ttu-id="6417e-163">A lista de distribuição tem grupos filho ou é membro de outro grupo.</span><span class="sxs-lookup"><span data-stu-id="6417e-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="6417e-164">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-164">No</span></span>  <br/> |
|<span data-ttu-id="6417e-165">Listas de distribuição com **recipientTypeDetails** que não **seja UserMailbox,** **SharedMailbox,** **TeamMailbox,** **MailUser**</span><span class="sxs-lookup"><span data-stu-id="6417e-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="6417e-166">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-166">No</span></span>  <br/> |
|<span data-ttu-id="6417e-167">Lista de distribuição que tem mais de 100 proprietários</span><span class="sxs-lookup"><span data-stu-id="6417e-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="6417e-168">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-168">No</span></span>  <br/> |
|<span data-ttu-id="6417e-169">Lista de distribuição que só tem membros, mas nenhum proprietário</span><span class="sxs-lookup"><span data-stu-id="6417e-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="6417e-170">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-170">No</span></span>  <br/> |
|<span data-ttu-id="6417e-171">Lista de distribuição que tem alias contendo caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="6417e-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="6417e-172">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-172">No</span></span>  <br/> |
|<span data-ttu-id="6417e-173">Se a lista de distribuição estiver configurada para ser um endereço de encaminhamento para Caixa de Correio Compartilhada</span><span class="sxs-lookup"><span data-stu-id="6417e-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="6417e-174">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-174">No</span></span>  <br/> |
|<span data-ttu-id="6417e-175">Se a DL faz parte da **Restrição do Remetente** em outro DL.</span><span class="sxs-lookup"><span data-stu-id="6417e-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="6417e-176">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-176">No</span></span>  <br/> |
|<span data-ttu-id="6417e-177">Grupos de segurança</span><span class="sxs-lookup"><span data-stu-id="6417e-177">Security groups</span></span>  <br/> |<span data-ttu-id="6417e-178">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-178">No</span></span>  <br/> |
|<span data-ttu-id="6417e-179">Listas de Distribuição Dinâmica</span><span class="sxs-lookup"><span data-stu-id="6417e-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="6417e-180">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-180">No</span></span>  <br/> |
|<span data-ttu-id="6417e-181">Listas de distribuição que foram convertidas em **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="6417e-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="6417e-182">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-182">No</span></span>  <br/> |
|<span data-ttu-id="6417e-183">Listas de distribuição **onde MemberJoinRestriction** e/ou **MemberDepartRestriction** é **Fechado**</span><span class="sxs-lookup"><span data-stu-id="6417e-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="6417e-184">Não</span><span class="sxs-lookup"><span data-stu-id="6417e-184">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="6417e-185">Verificar quais DLs estão qualificadas para atualização</span><span class="sxs-lookup"><span data-stu-id="6417e-185">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="6417e-186">Se você quiser verificar se uma DL está qualificada ou não, você pode executar o comando abaixo:</span><span class="sxs-lookup"><span data-stu-id="6417e-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="6417e-187">Se você quiser verificar quais DLs estão qualificadas para atualização, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="6417e-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="6417e-188">Quem pode executar os scripts de atualização?</span><span class="sxs-lookup"><span data-stu-id="6417e-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="6417e-189">Pessoas com direitos de administrador global ou administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="6417e-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="6417e-190">Por que o cartão de visita ainda está mostrando uma lista de distribuição?</span><span class="sxs-lookup"><span data-stu-id="6417e-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="6417e-191">O que devo fazer para impedir que uma lista de distribuição atualizada seja aparecendo na minha lista de sugestões automáticas?</span><span class="sxs-lookup"><span data-stu-id="6417e-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="6417e-192">Para o Outlook: quando alguém tentar enviar um email no Outlook digitando o nome do grupo do Microsoft 365 após a migração, o destinatário será resolvido como a lista de distribuição em vez do grupo.</span><span class="sxs-lookup"><span data-stu-id="6417e-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="6417e-193">O cartão de visita do destinatário será o cartão de visita de listas de distribuição.</span><span class="sxs-lookup"><span data-stu-id="6417e-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="6417e-194">Isso se deve ao cache de destinatário ou cache de nome de nick no Outlook.</span><span class="sxs-lookup"><span data-stu-id="6417e-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="6417e-195">O email será enviado com êxito para o grupo, mas pode causar confusão ao remetente.</span><span class="sxs-lookup"><span data-stu-id="6417e-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="6417e-196">Você pode executar as etapas neste tópico, Informações sobre a lista [de Preenchimento Automático](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) do Outlook para redefinir o cache, o que corrigirá esse problema.</span><span class="sxs-lookup"><span data-stu-id="6417e-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="6417e-197">Para o Outlook na Web: no caso do Outlook na Web, o destinatário da lista de distribuição ainda permanecerá no cache.</span><span class="sxs-lookup"><span data-stu-id="6417e-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="6417e-198">Você pode seguir as etapas em [Remover nome](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) sugerido ou endereço de email da Lista De Conclusão Automática para atualizar o cache para ver o cartão de visita do grupo.</span><span class="sxs-lookup"><span data-stu-id="6417e-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="6417e-199">Os novos membros do grupo recebem um email de boas-vindas na caixa de entrada?</span><span class="sxs-lookup"><span data-stu-id="6417e-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="6417e-200">Não.</span><span class="sxs-lookup"><span data-stu-id="6417e-200">No.</span></span> <span data-ttu-id="6417e-201">A configuração para habilitar mensagens de boas-vindas é definida como false por padrão.</span><span class="sxs-lookup"><span data-stu-id="6417e-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="6417e-202">Essa configuração afeta os membros existentes e novos do grupo que podem ingressar após a conclusão da migração.</span><span class="sxs-lookup"><span data-stu-id="6417e-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="6417e-203">Se o proprietário do grupo permitir mais tarde os usuários convidados, os usuários convidados não receberão um email de boas-vindas em sua caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="6417e-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="6417e-204">Os membros convidados podem continuar trabalhando com o grupo.</span><span class="sxs-lookup"><span data-stu-id="6417e-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="6417e-205">E se uma ou algumas DLs não são atualizadas?</span><span class="sxs-lookup"><span data-stu-id="6417e-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="6417e-206">Há alguns casos em que a DL é qualificada, mas não pode ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="6417e-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="6417e-207">A DL não é atualizada e permanece como uma DL.</span><span class="sxs-lookup"><span data-stu-id="6417e-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="6417e-208">Onde o administrador aplicou a Política de Endereço de **Email** de Grupo para os grupos de uma organização e tenta atualizar DLs que não cumprem os critérios, a DL não é atualizada</span><span class="sxs-lookup"><span data-stu-id="6417e-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="6417e-209">As DLs **com MemberJoinRestriction** **ou MemberDepartRestriction definidas** como **Closed**, não puderam ser atualizadas</span><span class="sxs-lookup"><span data-stu-id="6417e-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="6417e-210">O que acontece com a DL se a atualização do EAC falhar?</span><span class="sxs-lookup"><span data-stu-id="6417e-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="6417e-211">A atualização só acontecerá quando a chamada for enviada para o servidor.</span><span class="sxs-lookup"><span data-stu-id="6417e-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="6417e-212">Se a atualização falhar, suas DLs estarão intactas.</span><span class="sxs-lookup"><span data-stu-id="6417e-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="6417e-213">Eles funcionarão como antes.</span><span class="sxs-lookup"><span data-stu-id="6417e-213">They will work like they used to.</span></span>