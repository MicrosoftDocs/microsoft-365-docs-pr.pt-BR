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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: Os administradores podem aprender a exibir e pesquisar o log de auditoria do administrador no Exchange Online Protection (EOP) autônomo.
ms.openlocfilehash: 9fe2c742083cde1ca36f6a04cd357a473a10aeac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196538"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="9b4dc-103">Exibir o log de auditoria de administradores no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="9b4dc-103">View the admin audit log in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9b4dc-104">Em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, você pode usar o centro de administração do Exchange (Eat) ou o PowerShell autônomo do EOP para pesquisar e exibir entradas no log de auditoria do administrador.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-104">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="9b4dc-105">O log de auditoria de administrador registra ações específicas, com base nos cmdlets do PowerShell EOP autônomo, realizadas por administradores e usuários que receberam privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-105">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="9b4dc-106">As entradas no log de auditoria de administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem executou o cmdlet e quais objetos foram afetados.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-106">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9b4dc-107">O log de auditoria de administrador é habilitado por padrão e não pode ser desabilitado.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-107">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="9b4dc-108">O log de auditoria do administrador não registra ações com base nos cmdlets que começam com os verbos **Get**, **Search**ou **Test**.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-108">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="9b4dc-109">As entradas do log de auditoria são armazenadas por 90 dias.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-109">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="9b4dc-110">Quando uma entrada é mais antiga que 90 dias, ela é excluída</span><span class="sxs-lookup"><span data-stu-id="9b4dc-110">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9b4dc-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="9b4dc-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9b4dc-112">Para abrir o centro de administração do Exchange, confira [centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-112">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="9b4dc-113">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-113">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="9b4dc-114">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-114">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="9b4dc-115">Especificamente, você precisa da função logs de auditoria ou de logs de auditoria somente para exibição, que são atribuídos aos grupos de função ComplianceManagement, gerenciamento (administradores globais) e SecurityAdministrator por padrão.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-115">Specifically, you need the Audit Logs or View-Only Audit Logs role, which are assigned to the ComplianceManagement, OrganizationManagement (global admins), and SecurityAdministrator role groups by default.</span></span> <span data-ttu-id="9b4dc-116">Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-116">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="9b4dc-117">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="9b4dc-118">Está com problemas?</span><span class="sxs-lookup"><span data-stu-id="9b4dc-118">Having problems?</span></span> <span data-ttu-id="9b4dc-119">Peça ajuda no fórum [Proteção do Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=285351).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-119">Ask for help in the [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="9b4dc-120">Use o Eat para exibir o log de auditoria de administrador</span><span class="sxs-lookup"><span data-stu-id="9b4dc-120">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="9b4dc-121">No Eat, vá para auditoria de **Gerenciamento de conformidade** \> **Auditing**e, em seguida, escolha **executar o relatório de log de auditoria do administrador**.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-121">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="9b4dc-122">Na página **Pesquisar alterações nos grupos de funções de administrador** que é aberta, escolha uma **data de início** e uma **data de término** (o intervalo padrão é as duas últimas semanas) e, em seguida, escolha **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-122">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="9b4dc-123">Todas as alterações de configuração feitas durante o período especificado são exibidas e podem ser classificadas com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="9b4dc-123">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="9b4dc-124">**Date**: a data e hora em que a alteração de configuração foi feita.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-124">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="9b4dc-125">A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-125">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="9b4dc-126">**Cmdlet**: o nome do cmdlet que foi usado para fazer a alteração da configuração.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-126">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="9b4dc-127">**User**: o nome da conta de usuário do usuário que fez a alteração na configuração.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-127">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="9b4dc-p107">Serão exibidas até 5.000 entradas em várias páginas. Especifique um intervalo de datas menor se precisar restringir os resultados. Se você selecionar um resultado de pesquisa individual, as informações a seguir serão exibidas no painel de detalhes:</span><span class="sxs-lookup"><span data-stu-id="9b4dc-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="9b4dc-131">**Objeto modificado**: o objeto que foi modificado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-131">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="9b4dc-132">**Parâmetros (parâmetro: value)**: os parâmetros de cmdlet que foram usados e qualquer valor especificado com o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-132">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="9b4dc-133">Se quiser imprimir uma determinada entrada do log de auditoria, selecione o botão **Imprimir** no painel de detalhes.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-133">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="9b4dc-134">Usar o EOP PowerShell autônomo para exibir o log de auditoria de administrador</span><span class="sxs-lookup"><span data-stu-id="9b4dc-134">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="9b4dc-135">Você pode usar o PowerShell autônomo do EOP para pesquisar entradas de log de auditoria que atendam aos critérios especificados.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-135">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="9b4dc-136">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9b4dc-136">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="9b4dc-137">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="9b4dc-137">**Notes**:</span></span>

- <span data-ttu-id="9b4dc-138">Você só pode usar o parâmetro _Parameters_ juntamente com o parâmetro _cmdlets_ .</span><span class="sxs-lookup"><span data-stu-id="9b4dc-138">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="9b4dc-139">O parâmetro _ObjectIDs_ filtra os resultados pelo objeto que foi modificado pelo cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-139">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="9b4dc-140">Um valor válido depende de como o objeto é representado no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-140">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="9b4dc-141">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9b4dc-141">For example:</span></span>

  - <span data-ttu-id="9b4dc-142">Nome</span><span class="sxs-lookup"><span data-stu-id="9b4dc-142">Name</span></span>
  - <span data-ttu-id="9b4dc-143">Nome distinto canônico (por exemplo, contoso.com/Users/Akia Al-Zuhairi)</span><span class="sxs-lookup"><span data-stu-id="9b4dc-143">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="9b4dc-144">Provavelmente você precisará usar outros parâmetros de filtragem nesse cmdlet para restringir os resultados e identificar os tipos de objetos nos quais você está interessado.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-144">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="9b4dc-145">O parâmetro _userids_ filtra os resultados pelo usuário que fez a alteração (quem executou o cmdlet).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-145">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="9b4dc-146">Para os parâmetros _StartDate_ e _EndDate_ , se você especificar um valor de data/hora sem um fuso horário, o valor estará no tempo universal coordenado (UTC).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-146">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="9b4dc-147">Para especificar um valor de data/hora para este parâmetro, use uma das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b4dc-147">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="9b4dc-148">Especificar o valor de data/hora em UTC: por exemplo, "2016-05-06 14:30:00Z".</span><span class="sxs-lookup"><span data-stu-id="9b4dc-148">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="9b4dc-149">Especifique o valor de data/hora como uma fórmula que converte a data/hora em seu fuso horário local em UTC: por exemplo, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` .</span><span class="sxs-lookup"><span data-stu-id="9b4dc-149">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="9b4dc-150">Para mais informações, consulte [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-150">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="9b4dc-151">Por padrão, o cmdlet retorna um máximo de 1.000 entradas de log.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-151">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="9b4dc-152">Use o parâmetro _resultize_ para especificar até 250.000 entradas de log.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-152">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="9b4dc-153">Ou use o valor `Unlimited` para retornar todas as entradas.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-153">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="9b4dc-154">Esse exemplo realiza uma pesquisa em todas as entradas de log de auditoria com os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="9b4dc-154">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="9b4dc-155">**Data de início**: 4 de agosto de 2019</span><span class="sxs-lookup"><span data-stu-id="9b4dc-155">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="9b4dc-156">**Data de término**: 3 de outubro de 2019</span><span class="sxs-lookup"><span data-stu-id="9b4dc-156">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="9b4dc-157">**Cmdlets**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="9b4dc-157">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="9b4dc-158">Para informações detalhadas de sintaxes e de parâmetros, consulte [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-158">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="9b4dc-159">Exibir detalhes de entradas de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="9b4dc-159">View details of audit log entries</span></span>

<span data-ttu-id="9b4dc-160">O cmdlet **Search-AdminAuditLog** retorna os campos descritos na seção [conteúdo do log de auditoria](#audit-log-contents) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-160">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this topic.</span></span> <span data-ttu-id="9b4dc-161">Dos campos retornados pelo cmdlet, dois campos, **CmdletParameters** e **modificados**, contêm informações adicionais que não são retornadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-161">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="9b4dc-162">Para exibir o conteúdo dos campos **CmdletParameters** e **ModifiedProperties**, siga as etapas na sequência.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-162">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="9b4dc-163">Decida quais critérios deseja pesquisa, execute o cmdlet **Search-AdminAuditLog** e armazene os resultados em uma variável usando o seguinte comando.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-163">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="9b4dc-164">Cada entrada de log de auditoria é armazenada como um elemento de matriz na variável `$Results` .</span><span class="sxs-lookup"><span data-stu-id="9b4dc-164">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="9b4dc-165">Você pode selecionar um elemento de matriz especificando seu índice de elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-165">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="9b4dc-166">Os índices de elemento de matriz começam em zero (0) para o primeiro elemento da matriz.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-166">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="9b4dc-167">Por exemplo, para recuperar o elemento da quinta matriz, que tem um índice de 4, use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-167">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="9b4dc-p115">O comando anterior retorna a entrada de log armazenada no elemento de matriz 4. Para ver o conteúdo dos campos **CmdletParameters** e **ModifiedProperties** referentes a essa entrada de log, use os seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="9b4dc-170">Para exibir o conteúdo dos campos **CmdletParameters** ou **ModifiedParameters** em outra entrada de log, altere o índice do elemento de matriz.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-170">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="9b4dc-171">Conteúdo do log de auditoria</span><span class="sxs-lookup"><span data-stu-id="9b4dc-171">Audit log contents</span></span>

<span data-ttu-id="9b4dc-172">Cada entrada de log de auditoria contém as informações descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-172">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="9b4dc-173">O log de auditoria contém uma ou mais entradas de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-173">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="9b4dc-174">Campo</span><span class="sxs-lookup"><span data-stu-id="9b4dc-174">Field</span></span>|<span data-ttu-id="9b4dc-175">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b4dc-175">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="9b4dc-176">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-176">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="9b4dc-177">Este campo contém o objeto que foi modificado pelo cmdlet especificado no `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-177">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="9b4dc-178">Este campo contém o nome do cmdlet que foi executado pelo usuário no `Caller` campo.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-178">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="9b4dc-179">Este campo contém os parâmetros que foram especificados quando o cmdlet no `CmdletName` campo foi executado.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-179">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="9b4dc-180">O valor especificado com o parâmetro, se houver, também é armazenado nesse campo, mas não é visível na saída-padrão.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-180">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="9b4dc-181">Este campo contém as propriedades que foram modificadas no objeto no `ObjectModified` campo.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-181">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="9b4dc-182">O valor antigo da propriedade e o novo valor que foi armazenado também é armazenado nesse campo, mas não é visível na saída-padrão.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-182">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="9b4dc-183">Este campo contém a conta de usuário do usuário que executou o cmdlet no `CmdletName` campo.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-183">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="9b4dc-184">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-184">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="9b4dc-185">Este campo especifica se o cmdlet no `CmdletName` campo foi executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-185">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="9b4dc-186">O valor é `True` ou `False` .</span><span class="sxs-lookup"><span data-stu-id="9b4dc-186">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="9b4dc-187">Este campo contém a mensagem de erro gerada se o cmdlet no `CmdletName` campo não tiver sido concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-187">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="9b4dc-188">Este campo contém a data e hora em que o cmdlet no `CmdletName` campo foi executado.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-188">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="9b4dc-189">A data e a hora são armazenadas no formato UTC (Tempo Universal Coordenado).</span><span class="sxs-lookup"><span data-stu-id="9b4dc-189">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="9b4dc-190">Este campo indica o servidor no qual o cmdlet especificado no `CmdletName` campo foi executado.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-190">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="9b4dc-191">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-191">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="9b4dc-192">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-192">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="9b4dc-193">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-193">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="9b4dc-194">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-194">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="9b4dc-195">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-195">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="9b4dc-196">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-196">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="9b4dc-197">Este campo é usado internamente pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="9b4dc-197">This field is used internally by EOP.</span></span>|
|
