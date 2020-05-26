---
title: Executar um relatório de grupo de função de administrador no EOP autônomo
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
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a executar um relatório de grupo de funções de administrador no proteção do Exchange Online (EOP) autônomo. Este relatório registra quando um administrador adiciona ou remove membros de grupos de funções de administrador, EOP registra cada ocorrência.
ms.openlocfilehash: 39022892075b295a26645157941195b97897c690
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350934"
---
# <a name="run-an-administrator-role-group-report-in-standalone-eop"></a><span data-ttu-id="2f90e-104">Executar um relatório de grupo de função de administrador no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="2f90e-104">Run an administrator role group report in standalone EOP</span></span>

<span data-ttu-id="2f90e-105">Em organizações autônomas de proteção do Exchange Online (EOP) sem caixas de correio do Exchange Online, quando um administrador adiciona ou remove membros dos grupos de função administrativa, o serviço registra cada ocorrência.</span><span class="sxs-lookup"><span data-stu-id="2f90e-105">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, when an admin adds members to or removes members from administrative role groups, the service logs each occurrence.</span></span> <span data-ttu-id="2f90e-106">Para obter mais informações sobre grupos de função em EOP autônomos, consulte [permissões no EOP autônomo](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2f90e-106">For more information about role groups in standalone EOP, see [Permissions in standalone EOP](feature-permissions-in-eop.md).</span></span>

<span data-ttu-id="2f90e-107">Quando você executa um relatório de grupo de funções de administrador no centro de administração do Exchange (Eat), as entradas são exibidas como resultados de pesquisa e incluem os grupos de função afetados, quem alterou a associação do grupo de função e quando e quais foram feitas as atualizações de associação.</span><span class="sxs-lookup"><span data-stu-id="2f90e-107">When you run an administrator role group report in the Exchange admin center (EAC), entries are displayed as search results and include the role groups affected, who changed the role group membership and when, and what membership updates were made.</span></span> <span data-ttu-id="2f90e-108">Use esse relatório para monitorar as alterações nas permissões administrativas atribuídas aos usuários da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2f90e-108">Use this report to monitor changes to the administrative permissions assigned to users in your organization.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2f90e-109">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="2f90e-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2f90e-110">Para abrir o centro de administração do Exchange, confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2f90e-110">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2f90e-111">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="2f90e-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2f90e-112">Especificamente, você precisa da função logs de auditoria ou de logs de auditoria somente para exibição, que são atribuídos aos grupos de função ComplianceManagement, gerenciamento (administradores globais) e SecurityAdministrator por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f90e-112">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="2f90e-113">Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="2f90e-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="2f90e-114">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="2f90e-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="2f90e-115">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="2f90e-115">Having problems?</span></span> <span data-ttu-id="2f90e-116">Peça ajuda no fórum do [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .</span><span class="sxs-lookup"><span data-stu-id="2f90e-116">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a><span data-ttu-id="2f90e-117">Usar o EAC para executar o relatório de grupo de funções de administrador</span><span class="sxs-lookup"><span data-stu-id="2f90e-117">Use the EAC to run an administrator role group report</span></span>

<span data-ttu-id="2f90e-118">Execute o relatório do grupo de funções de administrador para localizar as alterações nos grupos de função de gerenciamento em sua organização dentro de um determinado período.</span><span class="sxs-lookup"><span data-stu-id="2f90e-118">Run the administrator role group report to find the changes to management role groups in your organization within a particular time frame.</span></span>

1. <span data-ttu-id="2f90e-119">No Eat, vá para auditoria de **Gerenciamento de conformidade** \> **Auditing**e, em seguida, escolha **executar um relatório de grupo de função de administrador**.</span><span class="sxs-lookup"><span data-stu-id="2f90e-119">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run an administrator role group report**.</span></span>

2. <span data-ttu-id="2f90e-120">Na página **Pesquisar alterações nos grupos de funções de administrador** que é aberta, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="2f90e-120">In the **Search for changes to administrator role groups** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2f90e-121">**Data de início** e **data de término**: Insira um intervalo de datas.</span><span class="sxs-lookup"><span data-stu-id="2f90e-121">**Start date** and **End date**: Enter a date range.</span></span> <span data-ttu-id="2f90e-122">Por padrão, o relatório procura alterações feitas nos grupos de funções do administrador nas duas últimas semanas.</span><span class="sxs-lookup"><span data-stu-id="2f90e-122">By default, the report searches for changes made to administrator role groups in the past two weeks.</span></span>

   - <span data-ttu-id="2f90e-123">**Selecionar grupos de função**: por padrão, todos os grupos de função são pesquisados.</span><span class="sxs-lookup"><span data-stu-id="2f90e-123">**Select role groups**: By default, all role groups are searched.</span></span> <span data-ttu-id="2f90e-124">Para filtrar os resultados por grupos de função específicos, clique em **Selecionar grupos de função**.</span><span class="sxs-lookup"><span data-stu-id="2f90e-124">To filter the results by specific role groups, click **Select role groups**.</span></span> <span data-ttu-id="2f90e-125">Na caixa de diálogo exibida, selecione um grupo de função e clique em **Adicionar->**.</span><span class="sxs-lookup"><span data-stu-id="2f90e-125">In the dialog that appears, select a role group and click **add ->**.</span></span> <span data-ttu-id="2f90e-126">Repita essa etapa quantas vezes for necessário e clique em **OK** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="2f90e-126">Repeat this step as many times as necessary, and then click **OK** when you're finished.</span></span>

3. <span data-ttu-id="2f90e-127">Quando tiver concluído, clique em **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="2f90e-127">When you're finished, click **Search**.</span></span>

<span data-ttu-id="2f90e-p108">Se quaisquer alterações forem encontradas usando os critérios especificados, elas aparecerão no painel de resultados. Clique em um grupo de função nos resultados da pesquisa para ver as alterações no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="2f90e-p108">If any changes are found using the criteria you specified, they will appear in the results pane. Click a role group in the search results to see the changes in the details pane.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2f90e-130">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="2f90e-130">How do you know this worked?</span></span>

<span data-ttu-id="2f90e-p109">Se você executou com sucesso um relatório de grupo de funções do administrador, os grupos de funções que foram alterados dentro do intervalo de datas serão exibidos no painel de resultados da pesquisa. Se não houver resultados, nenhuma alteração nos grupos de funções será executada dentro do intervalo de datas especificado. Se julgar que deveria haver resultados, altere o intervalo de dados e execute novamente o relatório.</span><span class="sxs-lookup"><span data-stu-id="2f90e-p109">If you've successfully run an administrator role group report, role groups that have been changed within the date range are displayed in the search results pane. If there are no results, then no changes to role groups have taken place within the specified date range. If you think there should be results, change the date range and then run the report again.</span></span>

## <a name="monitor-changes-to-role-group-membership"></a><span data-ttu-id="2f90e-134">Monitorar alterações na associação de grupo de funções</span><span class="sxs-lookup"><span data-stu-id="2f90e-134">Monitor changes to role group membership</span></span>

<span data-ttu-id="2f90e-p110">Quando os membros são adicionados ou removidos de um grupo de funções, os resultados da pesquisa exibidos no painel de detalhes indicam que a associação de grupo de funções foi atualizada e lista os membros atuais. Os resultados não informam explicitamente qual usuário foi adicionado ou removido.</span><span class="sxs-lookup"><span data-stu-id="2f90e-p110">When members are added to or removed from a role group, the search results displayed in the details pane indicate that the role group membership was updated and lists the current members. The results don't explicitly state which user was added or removed.</span></span>

<span data-ttu-id="2f90e-p111">Para determinar se um usuário foi adicionado ou removido, você terá que comparar duas entradas separadas no relatório. Por exemplo, vamos observar as entradas de log a seguir do grupo de funções de **HelpDesk**:</span><span class="sxs-lookup"><span data-stu-id="2f90e-p111">To determine if a user was added or removed, you have to compare two separate entries in the report. For example, let's look at the following log entries for the **HelpDesk** role group:</span></span>

> <span data-ttu-id="2f90e-139">1/27/2018 4:43 PM</span><span class="sxs-lookup"><span data-stu-id="2f90e-139">1/27/2018 4:43 PM</span></span> <br> <span data-ttu-id="2f90e-140">Administrador</span><span class="sxs-lookup"><span data-stu-id="2f90e-140">Administrator</span></span> <br> <span data-ttu-id="2f90e-141">Membros atualizados: Administrator;annb,florencef;pilarp</span><span class="sxs-lookup"><span data-stu-id="2f90e-141">Updated members: Administrator;annb,florencef;pilarp</span></span> <br> <span data-ttu-id="2f90e-142">2/06/2018 10:09 AM</span><span class="sxs-lookup"><span data-stu-id="2f90e-142">2/06/2018 10:09 AM</span></span> <br> <span data-ttu-id="2f90e-143">Administrador</span><span class="sxs-lookup"><span data-stu-id="2f90e-143">Administrator</span></span> <br> <span data-ttu-id="2f90e-144">Membros atualizados: Administrator;annb;florencef;pilarp;tonip</span><span class="sxs-lookup"><span data-stu-id="2f90e-144">Updated members: Administrator;annb;florencef;pilarp;tonip</span></span> <br> <span data-ttu-id="2f90e-145">2/19/2018 2:12 PM</span><span class="sxs-lookup"><span data-stu-id="2f90e-145">2/19/2018 2:12 PM</span></span> <br> <span data-ttu-id="2f90e-146">Administrador</span><span class="sxs-lookup"><span data-stu-id="2f90e-146">Administrator</span></span> <br> <span data-ttu-id="2f90e-147">Membros atualizados: Administrator;annb;florencef;tonip</span><span class="sxs-lookup"><span data-stu-id="2f90e-147">Updated members: Administrator;annb;florencef;tonip</span></span>

<span data-ttu-id="2f90e-148">Nesse exemplo, a conta de usuário Administrador fez as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="2f90e-148">In this example, the Administrator user account made the following changes:</span></span>

- <span data-ttu-id="2f90e-149">No 2/06/2018, eles adicionaram o usuário tonip.</span><span class="sxs-lookup"><span data-stu-id="2f90e-149">On 2/06/2018, they added the user tonip.</span></span>

- <span data-ttu-id="2f90e-150">No 2/19/2018, eles removeram o usuário pilarp.</span><span class="sxs-lookup"><span data-stu-id="2f90e-150">On 2/19/2018, they removed the user pilarp.</span></span>

## <a name="use-standalone-exchange-online-powershell-to-search-for-audit-log-entries"></a><span data-ttu-id="2f90e-151">Usar o PowerShell autônomo do Exchange Online para pesquisar entradas de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="2f90e-151">Use standalone Exchange Online PowerShell to search for audit log entries</span></span>

<span data-ttu-id="2f90e-152">Você pode usar o PowerShell do Exchange Online para pesquisar entradas de log de auditoria que atendam aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="2f90e-152">You can use Exchange Online PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="2f90e-153">Para obter uma lista de critérios de pesquisa, consulte [Log de auditoria de administrador](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx).</span><span class="sxs-lookup"><span data-stu-id="2f90e-153">For a list of search criteria, see [Administrator audit logging](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx).</span></span> <span data-ttu-id="2f90e-154">Este procedimento usa o cmdlet **Search-AdminAuditLog** e exibe os resultados da pesquisa no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2f90e-154">This procedure uses the **Search-AdminAuditLog** cmdlet and displays search results in Exchange Online PowerShell.</span></span> <span data-ttu-id="2f90e-155">Ele pode ser usado quando você precisa retornar um conjunto de resultados que exceda os limites definidos no cmdlet **New-AdminAuditLogSearch** ou nos Relatórios de Auditoria do EAC.</span><span class="sxs-lookup"><span data-stu-id="2f90e-155">You can use this cmdlet when you need to return a set of results that exceeds the limits defined on the **New-AdminAuditLogSearch** cmdlet or in the EAC Audit Reporting reports.</span></span>

<span data-ttu-id="2f90e-156">Para pesquisar no log de auditoria pelos critérios especificados, use a sintaxe a seguir.</span><span class="sxs-lookup"><span data-stu-id="2f90e-156">To search the audit log for criteria you specify, use the following syntax.</span></span>

```PowerShell
Search-AdminAuditLog - Cmdlets <cmdlet 1, cmdlet 2, ...> -Parameters <parameter 1, parameter 2, ...> -StartDate <start date> -EndDate <end date> -UserIds <user IDs> -ObjectIds <object IDs> -IsSuccess <$True | $False >
```

> [!NOTE]
> <span data-ttu-id="2f90e-157">O cmdlet **Search-AdminAuditLog** retorna um máximo de 1.000 entradas de log por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f90e-157">The **Search-AdminAuditLog** cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="2f90e-158">Use o parâmetro _resultize_ para especificar até 250.000 entradas de log.</span><span class="sxs-lookup"><span data-stu-id="2f90e-158">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="2f90e-159">Ou use o valor `Unlimited` para retornar todas as entradas.</span><span class="sxs-lookup"><span data-stu-id="2f90e-159">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="2f90e-160">Esse exemplo realiza uma pesquisa em todas as entradas de log de auditoria com os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="2f90e-160">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="2f90e-161">**Data de início**: 08/04/2018</span><span class="sxs-lookup"><span data-stu-id="2f90e-161">**Start date**: 08/04/2018</span></span>

- <span data-ttu-id="2f90e-162">**Data de término**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="2f90e-162">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="2f90e-163">**IDs de usuário**: Davids, Carla, Kima</span><span class="sxs-lookup"><span data-stu-id="2f90e-163">**User IDs**: davids, chrisd, kima</span></span>

- <span data-ttu-id="2f90e-164">**Cmdlets**: **Set-Mailbox**</span><span class="sxs-lookup"><span data-stu-id="2f90e-164">**Cmdlets**: **Set-Mailbox**</span></span>

- <span data-ttu-id="2f90e-165">**Parâmetros**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span><span class="sxs-lookup"><span data-stu-id="2f90e-165">**Parameters**: _ProhibitSendQuota_, _ProhibitSendReceiveQuota_, _IssueWarningQuota_, _MaxSendSize_, _MaxReceiveSize_</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Set-Mailbox -Parameters ProhibitSendQuota,ProhibitSendReceiveQuota,IssueWarningQuota,MaxSendSize,MaxReceiveSize -StartDate 08/04/2018 -EndDate 10/03/2018 -UserIds davids,chrisd,kima
```

<span data-ttu-id="2f90e-p114">Este exemplo pesquisa alterações efetuadas em uma caixa de correio específica. Isso será útil se você estiver solucionando problemas ou precisar fornecer informações para uma investigação. Os seguintes critérios são usados:</span><span class="sxs-lookup"><span data-stu-id="2f90e-p114">This example searches for changes made to a specific mailbox. This is useful if you're troubleshooting or you need to provide information for an investigation. The following criteria are used:</span></span>

- <span data-ttu-id="2f90e-169">**Data de início**: 05/01/2018</span><span class="sxs-lookup"><span data-stu-id="2f90e-169">**Start date**: 05/01/2018</span></span>

- <span data-ttu-id="2f90e-170">**Data de término**: 10/03/2018</span><span class="sxs-lookup"><span data-stu-id="2f90e-170">**End date**: 10/03/2018</span></span>

- <span data-ttu-id="2f90e-171">**ID do objeto**: contoso.com/users/DavidS</span><span class="sxs-lookup"><span data-stu-id="2f90e-171">**Object ID**: contoso.com/Users/DavidS</span></span>

```PowerShell
Search-AdminAuditLog -StartDate 05/01/2018 -EndDate 10/03/2018 -ObjectID contoso.com/Users/DavidS
```

<span data-ttu-id="2f90e-172">Se as pesquisas retornarem muitas entradas de log, recomendamos que você use o procedimento fornecido em **usar o PowerShell do Exchange Online para pesquisar entradas de log de auditoria e enviar resultados para um destinatário** mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2f90e-172">If your searches return many log entries, we recommend that you use the procedure provided in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic.</span></span> <span data-ttu-id="2f90e-173">O procedimento dessa seção envia um arquivo XML como anexo de email aos destinatários especificados, permitindo que você extraia com mais facilidade os dados em que está interessado.</span><span class="sxs-lookup"><span data-stu-id="2f90e-173">The procedure in that section sends an XML file as an email attachment to the recipients you specify, enabling you to more easily extract the data you're interested in.</span></span>

<span data-ttu-id="2f90e-174">Para informações detalhadas de sintaxes e de parâmetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="2f90e-174">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="2f90e-175">Exibir detalhes de entradas de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="2f90e-175">View details of audit log entries</span></span>

<span data-ttu-id="2f90e-p116">O cmdlet **Search-AdminAuditLog** retorna os campos descritos na seção "Conteúdo do log de auditoria" de [Log de auditoria de administrador](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx). Desses campos retornados pelo cmdlet, dois campos, **CmdletParameters** e **ModifiedProperties**, contêm informações adicionais que não podem ser exibidas por padrão.</span><span class="sxs-lookup"><span data-stu-id="2f90e-p116">The **Search-AdminAuditLog** cmdlet returns the fields described in the "Audit log contents section of [Administrator audit logging](https://technet.microsoft.com/library/22b17eb8-d8ee-4599-b202-d6a7928c20d9.aspx). Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't viewable by default.</span></span>

<span data-ttu-id="2f90e-178">Para exibir o conteúdo dos campos **CmdletParameters** e **ModifiedProperties**, siga as etapas na sequência.</span><span class="sxs-lookup"><span data-stu-id="2f90e-178">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span> <span data-ttu-id="2f90e-179">Ou você pode usar o procedimento em **usar o Exchange Online PowerShell para pesquisar entradas de log de auditoria e enviar resultados para um destinatário** posteriormente neste tópico para criar um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="2f90e-179">Or, you can use the procedure in **Use Exchange Online PowerShell to search for audit log entries and send results to a recipient** later in this topic to create an XML file.</span></span>

<span data-ttu-id="2f90e-180">Esse procedimento usa os seguintes conceitos:</span><span class="sxs-lookup"><span data-stu-id="2f90e-180">This procedure uses the following concepts:</span></span>

- [<span data-ttu-id="2f90e-181">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="2f90e-181">about_Arrays</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_arrays)

- [<span data-ttu-id="2f90e-182">about_Variables</span><span class="sxs-lookup"><span data-stu-id="2f90e-182">about_Variables</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variables)

1. <span data-ttu-id="2f90e-183">Decida quais critérios deseja pesquisa, execute o cmdlet **Search-AdminAuditLog** e armazene os resultados em uma variável usando o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="2f90e-183">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="2f90e-184">Cada entrada de log de auditoria é armazenada como um elemento de matriz na variável `$Results` .</span><span class="sxs-lookup"><span data-stu-id="2f90e-184">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="2f90e-185">Você pode selecionar um elemento de matriz especificando seu índice de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="2f90e-185">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="2f90e-186">Os índices de elemento de matriz começam em zero (0) para o primeiro elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="2f90e-186">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="2f90e-187">Por exemplo, para recuperar o elemento da quinta matriz, que tem um índice de 4, use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="2f90e-187">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="2f90e-p119">O comando anterior retorna a entrada de log armazenada no elemento de matriz 4. Para ver o conteúdo dos campos **CmdletParameters** e **ModifiedProperties** referentes a essa entrada de log, use os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="2f90e-p119">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="2f90e-190">Para exibir o conteúdo dos campos **CmdletParameters** ou **ModifiedParameters** em outra entrada de log, altere o índice do elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="2f90e-190">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>