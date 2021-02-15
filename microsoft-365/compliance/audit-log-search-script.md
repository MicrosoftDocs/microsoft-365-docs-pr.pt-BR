---
title: Usar um script Windows PowerShell para pesquisar o log de auditoria
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Use um script Windows PowerShell, o executa o cmdlet Search-UnifiedAuditLog, para pesquisar o log de auditoria. Este script é otimizado para retornar um grande conjunto (até 50.000) de registros de auditoria. O script exporta esses registros para um arquivo CSV que você pode exibir ou transformar usando o Power Query no Excel.
ms.openlocfilehash: d4fcf59297747d0499f6616438299ad8cbe96d7f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094782"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="d1cc8-105">Usar um script Windows PowerShell para pesquisar o log de auditoria</span><span class="sxs-lookup"><span data-stu-id="d1cc8-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="d1cc8-106">Segurança, conformidade e auditoria se tornaram as principais prioridades dos administradores de TI no mundo de hoje.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="d1cc8-107">O Microsoft 365 tem vários recursos integrados para ajudar as organizações a gerenciar a segurança, conformidade e auditoria.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="d1cc8-108">Em particular, o registro de auditoria unificado pode ajudá-lo a investigar incidentes de segurança e problemas de conformidade.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="d1cc8-109">Você pode recuperar registros de auditoria usando os seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="d1cc8-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="d1cc8-110">API da Atividade de Gestão do Office 365</span><span class="sxs-lookup"><span data-stu-id="d1cc8-110">The Office 365 Management Activity API</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="d1cc8-111">A [ferramenta de pesquisa de registro de auditoria](search-the-audit-log-in-security-and-compliance.md) no Centro de conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d1cc8-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="d1cc8-112">O cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) no Exchange Online Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1cc8-112">The [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="d1cc8-113">Se você precisa recuperar logs de auditoria regularmente, deve considerar uma solução que usa a API da Atividade de Gestão do Office 365 porque pode fornecer a grandes organizações a escalabilidade e o desempenho para recuperar milhões de registros de auditoria em uma base contínua.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="d1cc8-114">Usar a ferramenta de pesquisa de log de auditoria no Centro de conformidade do Microsoft 365 é uma boa maneira de encontrar rapidamente registros de auditoria para operações específicas que ocorrem em um intervalo de tempo mais curto.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="d1cc8-115">O uso de intervalos de tempo mais longos na ferramenta de pesquisa de log de auditoria, especialmente para grandes organizações, pode retornar muitos registros para gerenciar ou exportar facilmente.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="d1cc8-116">Quando há situações em que você precisa recuperar manualmente os dados de auditoria para uma investigação ou incidente específico, especialmente para intervalos de datas mais longos em organizações maiores, usar o cmdlet **Search-UnifiedAuditLog** pode ser a melhor opção.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="d1cc8-117">Este artigo inclui um script Windows PowerShell que usa o cmdlet para recuperar até 50.000 registros de auditoria e, em seguida, exportá-los para um arquivo CSV que você pode formatar usando o Power Query no Excel para ajudar em sua revisão.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="d1cc8-118">O uso do script neste artigo também minimiza a chance de que grandes pesquisas de log de auditoria expirem no serviço.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="d1cc8-119">Antes de executar o script</span><span class="sxs-lookup"><span data-stu-id="d1cc8-119">Before you run the script</span></span>

- <span data-ttu-id="d1cc8-120">O log de Auditoria deve ser habilitado para que sua organização use com sucesso o script para retornar os registros de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="d1cc8-121">O log de Auditoria é ativado por padrão para organizações empresariais Microsoft 365 e Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="d1cc8-122">Para verificar se a pesquisa de log de auditoria está ativada para sua organização, você pode executar o seguinte comando no Exchange Online Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d1cc8-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  <span data-ttu-id="d1cc8-123">O valor de `True` para a propriedade **UnifiedAuditLogIngestionEnabled** indica que a pesquisa de registro de auditoria está ativada.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="d1cc8-124">Você deve ser atribuído à função Logs de Auditoria somente para exibição ou Logs de auditoria no Exchange Online para executar o script com êxito.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="d1cc8-125">Por padrão, essas funções são atribuídas aos grupos de funções Gerenciamento de Conformidade e Gerenciamento de Organização na página Permissões do centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="d1cc8-126">Para obter mais informações, confira a seção "Requisitos para pesquisar o registro de auditoria" em [Pesquisar o registro de auditoria no centro de conformidade](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="d1cc8-127">O script pode demorar muito para ser concluído.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="d1cc8-128">Quanto tempo leva para ser executado depende do intervalo de datas e do tamanho do intervalo para o qual você configura o script para recuperar os registros de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="d1cc8-129">Intervalos de datas maiores e intervalos menores resultarão em um longo tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="d1cc8-130">Confira a tabela na Etapa 2 para obter mais informações sobre o intervalo de datas e intervalos.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="d1cc8-131">O script de exemplo fornecido neste artigo não é compatível com nenhum programa ou serviço de suporte padrão da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="d1cc8-132">O script de amostra é fornecido COMO ESTÁ, sem garantia de nenhum tipo.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="d1cc8-133">A Microsoft também se isenta de todas as garantias implícitas, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou adequação a uma finalidade específica.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="d1cc8-134">Todo o risco decorrente do uso ou desempenho do script de amostra e da documentação permanece com você.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="d1cc8-135">Em nenhuma hipótese a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou entrega do script será responsável por quaisquer danos (incluindo, sem limitação, danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais, ou outra perda pecuniária) decorrente do uso ou da incapacidade de usar o script ou documentação de amostra, mesmo que a Microsoft tenha sido avisada da possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="d1cc8-136">Etapa 1: Conecte-se ao Exchange Online Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1cc8-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="d1cc8-137">A primeira etapa é conectar-se ao Exchange Online Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="d1cc8-138">Você pode se conectar usando autenticação moderna ou com autenticação multifator (MFA).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="d1cc8-139">Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="d1cc8-140">Etapa 2: modificar e executar o script para recuperar os registros de auditoria</span><span class="sxs-lookup"><span data-stu-id="d1cc8-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="d1cc8-141">Depois de se conectar ao Exchange Online Windows PowerShell, a próxima etapa é criar, modificar e executar o script para recuperar os dados de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="d1cc8-142">As primeiras sete linhas no script de pesquisa de log de auditoria contêm as seguintes variáveis ​​que você pode modificar para configurar sua pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="d1cc8-143">Consulte a tabela na etapa 2 para obter uma descrição dessas variáveis.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="d1cc8-144">Salve o texto a seguir em um script do Windows PowerShell usando um sufixo de nome de arquivo .ps1.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-144">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1.</span></span> <span data-ttu-id="d1cc8-145">Por exemplo, SearchAuditLog.ps1.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-145">For example, SearchAuditLog.ps1.</span></span>

```powershell
#Modify the values for the following variables to configure the audit log search.
$logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
$outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
[DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
[DateTime]$end = [DateTime]::UtcNow
$record = "AzureActiveDirectory"
$resultSize = 5000
$intervalMinutes = 60

#Start script
[DateTime]$currentStart = $start
[DateTime]$currentEnd = $start

Function Write-LogFile ([String]$Message)
{
    $final = [DateTime]::Now.ToString("s") + ":" + $Message
    $final | Out-File $logFile -Append
}

Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"

$totalCount = 0
while ($true)
{
    $currentEnd = $currentStart.AddMinutes($intervalMinutes)
    if ($currentEnd -gt $end)
    {
        $currentEnd = $end
    }

    if ($currentStart -eq $currentEnd)
    {
        break
    }

    $sessionID = [DateTime]::Now.ToString("s")
    Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
    $currentCount = 0

    $sw = [Diagnostics.StopWatch]::StartNew()
    do
    {
        $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize

        if (($results | Measure-Object).Count -ne 0)
        {
            $results | export-csv -Path $outputFile -Append -NoTypeInformation

            $currentTotal = $results[0].ResultCount
            $totalCount += $results.Count
            $currentCount += $results.Count
            Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"

            if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
            {
                $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                Write-LogFile $message
                Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                ""
                break
            } 
        }
    }
    while (($results | Measure-Object).Count -ne 0)

    $currentStart = $currentEnd
}

Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green

```

2. <span data-ttu-id="d1cc8-146">Modifique as variáveis ​​listadas na tabela a seguir para configurar os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="d1cc8-147">O script inclui valores de amostra para essas variáveis, mas você deve alterá-los (a menos que indicado de outra forma) para atender aos seus requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   |<span data-ttu-id="d1cc8-148">Variável</span><span class="sxs-lookup"><span data-stu-id="d1cc8-148">Variable</span></span>|<span data-ttu-id="d1cc8-149">Valor de amostra</span><span class="sxs-lookup"><span data-stu-id="d1cc8-149">Sample value</span></span>|<span data-ttu-id="d1cc8-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="d1cc8-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="d1cc8-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="d1cc8-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="d1cc8-152">Especifica o nome e a localização do arquivo de log que contém informações sobre o andamento da pesquisa de log de auditoria executada pelo script.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-152">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script.</span></span>|
   |`$outputFile`|<span data-ttu-id="d1cc8-153">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="d1cc8-153">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="d1cc8-154">Especifica o nome e a localização do arquivo CSV que contém os registros de auditoria retornados pelo script.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-154">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="d1cc8-155">`[DateTime]$start` e `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="d1cc8-155">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="d1cc8-158">Especifica o intervalo de datas para a pesquisa do log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-158">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="d1cc8-159">O script retornará registros de atividades de auditoria que ocorreram dentro do intervalo de datas especificado.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-159">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="d1cc8-160">Por exemplo, para retornar atividades realizadas em janeiro de 2021, você pode usar uma data de início de `"2021-01-01"`e uma data de término de`"2021-01-31"` (certifique-se de colocar os valores entre aspas duplas). O valor de amostra no script retorna registros para atividades realizadas nas 24 horas anteriores.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-160">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="d1cc8-161">Se você não incluir um carimbo de data/hora no valor, o carimbo de data/hora padrão será 0h (meia-noite) na data especificada.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-161">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="d1cc8-162">AzureActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="d1cc8-162">"AzureActiveDirectory"</span></span>|<span data-ttu-id="d1cc8-163">Especifica o tipo de registro das atividades de auditoria (também chamadas de *operações*) a serem pesquisadas.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-163">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="d1cc8-164">Esta propriedade indica o serviço ou recurso em que uma atividade foi acionada.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-164">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="d1cc8-165">Para obter uma lista dos tipos de registro que você pode usar para esta variável, confira [Tipo de registro do log de Auditoria](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-165">For a list of record types that you can use for this variable, see [Audit log record type](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="d1cc8-166">Você pode usar o nome do tipo de registro ou valor ENUM.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-166">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="d1cc8-167">**Dica:** para retornar registros de auditoria para todos os tipos de registro, use o valor `$null` (sem aspas duplas).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-167">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="d1cc8-168">5000</span><span class="sxs-lookup"><span data-stu-id="d1cc8-168">5000</span></span>|<span data-ttu-id="d1cc8-169">Especifica o número de resultados retornados sempre que o cmdlet **Search-UnifiedAuditLog** é chamado pelo script (chamado de *conjunto de resultados*).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-169">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="d1cc8-170">O valor de 5.000 é o valor máximo compatível com o cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-170">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="d1cc8-171">Deixe este valor como está.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-171">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="d1cc8-172">60</span><span class="sxs-lookup"><span data-stu-id="d1cc8-172">60</span></span>|<span data-ttu-id="d1cc8-173">Para ajudar a superar o limite de 5.000 registros retornados, essa variável pega o intervalo de dados especificado e o divide em intervalos de tempo menores.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-173">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="d1cc8-174">Agora, cada intervalo, não todo o intervalo de datas, está sujeito ao limite de saída de 5.000 registros do comando.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-174">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="d1cc8-175">O valor padrão de 5.000 registros por intervalo de 60 minutos dentro do intervalo de datas deve ser suficiente para a maioria das organizações.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-175">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="d1cc8-176">Mas, se o script retornar um erro que diz, `maximum results limitation reached`, diminua o intervalo de tempo (por exemplo, para 30 minutos ou mesmo 15 minutos) e execute o script novamente.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-176">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="d1cc8-177">A maioria das variáveis ​​listadas na tabela anterior correspondem aos parâmetros do cmdlet **Search-UnifiedAuditLog**.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-177">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="d1cc8-178">Para obter mais informações sobre esses parâmetros, confira[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-178">For more information about these parameters, see [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="d1cc8-179">No seu computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script modificado.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-179">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="d1cc8-180">Execute o script no Exchange Online Windows PowerShell; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d1cc8-180">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="d1cc8-181">O script exibe mensagens de progresso durante a execução.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-181">The script displays progress messages while it's running.</span></span> <span data-ttu-id="d1cc8-182">Após a conclusão da execução do script, ele cria o arquivo de log e o arquivo CSV que contém os registros de auditoria e os salva nas pastas definidas pelas variáveis ​​`$logFile` e `$outputFile`.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-182">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1cc8-183">Há um limite de 50.000 para o número máximo de registros de auditoria retornados cada vez que você executa este script.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-183">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="d1cc8-184">Se você executar este script e ele retornar 50.000 resultados, é provável que os registros de auditoria para atividades que ocorreram dentro do intervalo de datas não foram incluídos.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-184">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="d1cc8-185">Se isso acontecer, recomendamos que você divida o período em durações menores e execute novamente o script para cada período.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-185">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="d1cc8-186">Por exemplo, se um intervalo de datas de 90 dias retornar 50.000 resultados, você poderá executar o script novamente duas vezes, uma nos primeiros 45 dias do intervalo e, em seguida, nos próximos 45 dias.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-186">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="d1cc8-187">Etapa 3: formate e visualize os registros de auditoria</span><span class="sxs-lookup"><span data-stu-id="d1cc8-187">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="d1cc8-188">Depois de executar o script e exportar os registros de auditoria para um arquivo CSV, você pode formatar o CSV para facilitar a revisão e análise dos registros de auditoria.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-188">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="d1cc8-189">Uma maneira de fazer isso é usar o recurso de transformação JSON do Power Query no Excel para dividir cada propriedade no objeto JSON na coluna **AuditData** em sua própria coluna.</span><span class="sxs-lookup"><span data-stu-id="d1cc8-189">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="d1cc8-190">Para obter instruções passo a passo, consulte "Etapa 2: formatar o registro de auditoria exportado usando o Power Query Editor" em [Exportar, configurar e visualizar registros de registro de auditoria](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span><span class="sxs-lookup"><span data-stu-id="d1cc8-190">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>