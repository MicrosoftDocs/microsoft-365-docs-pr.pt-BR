---
title: Exibir o log de auditoria de administradores no EOP autônomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Os administradores podem aprender a exibir e pesquisar o log de auditoria de administrador no EOP (Proteção autônoma do Exchange Online).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ed1d1eb121c06e6f5727e8782ba1d8bc8d23a99
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053060"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="7d8c4-103">Exibir o log de auditoria de administradores no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="7d8c4-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="7d8c4-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="7d8c4-104">**Applies to**</span></span>
- [<span data-ttu-id="7d8c4-105">Proteção autônoma do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7d8c4-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7d8c4-106">Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode usar o Centro de administração do Exchange (EAC) ou o EOP PowerShell autônomo para pesquisar e exibir entradas no log de auditoria do administrador.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="7d8c4-107">O log de auditoria do administrador registra ações específicas, com base em cmdlets autônomos do EOP PowerShell, feitos por administradores e usuários que foram atribuídos a privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="7d8c4-108">As entradas no log de auditoria do administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem correu o cmdlet e quais objetos foram afetados.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="7d8c4-109">O log de auditoria de administrador está habilitado por padrão e você não pode desabilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="7d8c4-110">O log de auditoria do administrador não registra ações baseadas em cmdlets que começam com os verbos **Get,** **Search** ou **Test**.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="7d8c4-111">As entradas do log de auditoria são armazenadas por 90 dias.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="7d8c4-112">Quando uma entrada é mais antiga do que 90 dias, ela é excluída</span><span class="sxs-lookup"><span data-stu-id="7d8c4-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7d8c4-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="7d8c4-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7d8c4-114">Para abrir o centro de administração do Exchange, consulte Centro de [administração do Exchange no EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="7d8c4-115">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="7d8c4-116">Você precisa ter permissões atribuídas no Exchange Online Protection antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="7d8c4-117">Especificamente, você precisa da  função Logs de **Auditoria** ou Logs de Auditoria Somente Exibição, que são atribuídos aos grupos de função Gerenciamento da **Organização,** Gerenciamento de Conformidade e Administrador de Segurança por padrão. </span><span class="sxs-lookup"><span data-stu-id="7d8c4-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="7d8c4-118">Para obter mais informações, consulte [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="7d8c4-119">Para obter informações sobre atalhos de teclado que podem se aplicar aos procedimentos neste artigo, consulte [Atalhos](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)de teclado para o centro de administração do Exchange no Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="7d8c4-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="7d8c4-120">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="7d8c4-120">Having problems?</span></span> <span data-ttu-id="7d8c4-121">Peça ajuda no fórum [Proteção do Exchange Online](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="7d8c4-122">Usar o EAC para exibir o log de auditoria do administrador</span><span class="sxs-lookup"><span data-stu-id="7d8c4-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="7d8c4-123">No EAC, vá para Auditoria de **gerenciamento** de conformidade e, em seguida, escolha Executar o relatório de \> log de auditoria do **administrador.**</span><span class="sxs-lookup"><span data-stu-id="7d8c4-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="7d8c4-124">Na página **Pesquisar alterações nos** grupos de função de administrador que é aberta, escolha uma data de início e data de término (o intervalo padrão é as últimas duas semanas) e escolha **Pesquisar**.  </span><span class="sxs-lookup"><span data-stu-id="7d8c4-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="7d8c4-125">Todas as alterações de configuração feitas durante o período especificado são exibidas e podem ser classificadas com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7d8c4-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="7d8c4-126">**Data**: a data e a hora em que a alteração de configuração foi feita.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="7d8c4-127">A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="7d8c4-128">**Cmdlet**: O nome do cmdlet que foi usado para fazer a configuração mudar.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="7d8c4-129">**Usuário**: o nome da conta de usuário do usuário que fez a alteração de configuração.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="7d8c4-p107">Serão exibidas até 5.000 entradas em várias páginas. Especifique um intervalo de datas menor se precisar restringir os resultados. Se você selecionar um resultado de pesquisa individual, as informações a seguir serão exibidas no painel de detalhes:</span><span class="sxs-lookup"><span data-stu-id="7d8c4-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="7d8c4-133">**Objeto modificado**: o objeto que foi modificado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="7d8c4-134">**Parâmetros (Parameter:Value)**: os parâmetros de cmdlet que foram usados e qualquer valor especificado com o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="7d8c4-135">Se quiser imprimir uma determinada entrada do log de auditoria, selecione o botão **Imprimir** no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="7d8c4-136">Usar o EOP PowerShell autônomo para exibir o log de auditoria do administrador</span><span class="sxs-lookup"><span data-stu-id="7d8c4-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="7d8c4-137">Você pode usar o EOP PowerShell autônomo para pesquisar entradas de log de auditoria que atendem aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="7d8c4-138">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7d8c4-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="7d8c4-139">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="7d8c4-139">**Notes**:</span></span>

- <span data-ttu-id="7d8c4-140">Você só pode usar o _parâmetro Parameters_ juntamente com o _parâmetro Cmdlets._</span><span class="sxs-lookup"><span data-stu-id="7d8c4-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="7d8c4-141">O _parâmetro ObjectIds_ filtra os resultados pelo objeto modificado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="7d8c4-142">Um valor válido depende de como o objeto é representado no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="7d8c4-143">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="7d8c4-143">For example:</span></span>

  - <span data-ttu-id="7d8c4-144">Nome</span><span class="sxs-lookup"><span data-stu-id="7d8c4-144">Name</span></span>
  - <span data-ttu-id="7d8c4-145">Nome diferenciado canônico (por exemplo, contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="7d8c4-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="7d8c4-146">Você provavelmente precisará usar outros parâmetros de filtragem neste cmdlet para restringir os resultados e identificar os tipos de objetos nos quais você está interessado.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="7d8c4-147">O _parâmetro UserIds_ filtra os resultados pelo usuário que fez a alteração (que correu o cmdlet).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="7d8c4-148">Para os _parâmetros StartDate_ e _EndDate,_ se você especificar um valor de data/hora sem um fuso horário, o valor está em Tempo Universal Coordenado (UTC).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="7d8c4-149">Para especificar um valor de data/hora para este parâmetro, use uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="7d8c4-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="7d8c4-150">Especificar o valor de data/hora em UTC: por exemplo, "2016-05-06 14:30:00Z".</span><span class="sxs-lookup"><span data-stu-id="7d8c4-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="7d8c4-151">Especifique o valor de data/hora como uma fórmula que converte a data/hora em seu fuso horário local para UTC: por exemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="7d8c4-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="7d8c4-152">Para mais informações, consulte [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-152">For more information, see [Get-Date](/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="7d8c4-153">O cmdlet retorna um máximo de 1.000 entradas de log por padrão.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="7d8c4-154">Use o _parâmetro ResultSize_ para especificar até 250.000 entradas de log.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="7d8c4-155">Ou, use o valor `Unlimited` para retornar todas as entradas.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="7d8c4-156">Esse exemplo realiza uma pesquisa em todas as entradas de log de auditoria com os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="7d8c4-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="7d8c4-157">**Data de início**: 4 de agosto de 2019</span><span class="sxs-lookup"><span data-stu-id="7d8c4-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="7d8c4-158">**Data de término**: 3 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="7d8c4-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="7d8c4-159">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="7d8c4-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="7d8c4-160">Para informações detalhadas de sintaxes e de parâmetros, consulte [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="7d8c4-161">Exibir detalhes de entradas de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="7d8c4-161">View details of audit log entries</span></span>

<span data-ttu-id="7d8c4-162">O cmdlet **Search-AdminAuditLog** retorna os campos descritos na seção Conteúdo do log de [auditoria](#audit-log-contents) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="7d8c4-163">Dos campos retornados pelo cmdlet, dois campos, **CmdletParameters** e **ModifiedProperties**, contêm informações adicionais que não são retornadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="7d8c4-164">Para exibir o conteúdo dos campos **CmdletParameters** e **ModifiedProperties**, siga as etapas na sequência.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="7d8c4-165">Decida quais critérios deseja pesquisa, execute o cmdlet **Search-AdminAuditLog** e armazene os resultados em uma variável usando o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="7d8c4-166">Cada entrada de log de auditoria é armazenada como um elemento de matriz na variável `$Results` .</span><span class="sxs-lookup"><span data-stu-id="7d8c4-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="7d8c4-167">Você pode selecionar um elemento de matriz especificando seu índice de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="7d8c4-168">Os índices de elemento de matriz começam em zero (0) para o primeiro elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="7d8c4-169">Por exemplo, para recuperar o elemento da quinta matriz, que tem um índice de 4, use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="7d8c4-p115">O comando anterior retorna a entrada de log armazenada no elemento de matriz 4. Para ver o conteúdo dos campos **CmdletParameters** e **ModifiedProperties** referentes a essa entrada de log, use os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="7d8c4-172">Para exibir o conteúdo dos campos **CmdletParameters** ou **ModifiedParameters** em outra entrada de log, altere o índice do elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="7d8c4-173">Conteúdo do log de auditoria</span><span class="sxs-lookup"><span data-stu-id="7d8c4-173">Audit log contents</span></span>

<span data-ttu-id="7d8c4-174">Cada entrada de log de auditoria contém as informações descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="7d8c4-175">O log de auditoria contém uma ou mais entradas de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="7d8c4-176">Campo</span><span class="sxs-lookup"><span data-stu-id="7d8c4-176">Field</span></span>|<span data-ttu-id="7d8c4-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="7d8c4-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="7d8c4-178">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="7d8c4-179">Este campo contém o objeto modificado pelo cmdlet especificado no `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="7d8c4-180">Este campo contém o nome do cmdlet que foi executado pelo usuário no `Caller` campo.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="7d8c4-181">Este campo contém os parâmetros que foram especificados quando o cmdlet no `CmdletName` campo foi executado.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="7d8c4-182">O valor especificado com o parâmetro, se houver, também é armazenado nesse campo, mas não é visível na saída-padrão.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="7d8c4-183">Este campo contém as propriedades que foram modificadas no objeto no `ObjectModified` campo.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="7d8c4-184">O valor antigo da propriedade e o novo valor que foi armazenado também é armazenado nesse campo, mas não é visível na saída-padrão.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="7d8c4-185">Este campo contém a conta de usuário do usuário que correu o cmdlet no `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="7d8c4-186">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="7d8c4-187">Este campo especifica se o cmdlet no `CmdletName` campo foi realizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="7d8c4-188">O valor é ou `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="7d8c4-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="7d8c4-189">Este campo contém a mensagem de erro gerada se o cmdlet no `CmdletName` campo não tiver êxito.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="7d8c4-190">Este campo contém a data e a hora em que o cmdlet no `CmdletName` campo foi executado.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="7d8c4-191">A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="7d8c4-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="7d8c4-192">Este campo indica o servidor no qual o cmdlet especificado no `CmdletName` campo foi executado.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="7d8c4-193">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="7d8c4-194">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="7d8c4-195">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="7d8c4-196">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="7d8c4-197">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="7d8c4-198">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="7d8c4-199">Esse campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7d8c4-199">This field is used internally by EOP.</span></span>|
|