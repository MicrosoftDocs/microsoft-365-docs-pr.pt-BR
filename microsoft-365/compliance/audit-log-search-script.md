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
description: Use um script Windows PowerShell que execute o cmdlet Search-UnifiedAuditLog no Exchange Online para pesquisar o log de auditoria. Este script é otimizado para retornar um grande conjunto (até 50.000) de registros de auditoria. O script exporta esses registros para um arquivo CSV que você pode exibir ou transformar usando o Power Query no Excel.
ms.openlocfilehash: 3d44054d8d1111fe86e06460f5ca4d442d0d1625
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233325"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>Usar um script Windows PowerShell para pesquisar o log de auditoria

Segurança, conformidade e auditoria se tornaram as principais prioridades dos administradores de TI no mundo de hoje. O Microsoft 365 tem vários recursos integrados para ajudar as organizações a gerenciar a segurança, conformidade e auditoria. Em particular, o registro de auditoria unificado pode ajudá-lo a investigar incidentes de segurança e problemas de conformidade. Você pode recuperar registros de auditoria usando os seguintes métodos:

- [API da Atividade de Gestão do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

- A [ferramenta de pesquisa de registro de auditoria](search-the-audit-log-in-security-and-compliance.md) no Centro de conformidade do Microsoft 365

- O cmdlet [Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) no Exchange Online Windows PowerShell

Se você precisa recuperar logs de auditoria regularmente, deve considerar uma solução que usa a API da Atividade de Gestão do Office 365 porque pode fornecer a grandes organizações a escalabilidade e o desempenho para recuperar milhões de registros de auditoria em uma base contínua. Usar a ferramenta de pesquisa de log de auditoria no Centro de conformidade do Microsoft 365 é uma boa maneira de encontrar rapidamente registros de auditoria para operações específicas que ocorrem em um intervalo de tempo mais curto. O uso de intervalos de tempo mais longos na ferramenta de pesquisa de log de auditoria, especialmente para grandes organizações, pode retornar muitos registros para gerenciar ou exportar facilmente.

Quando há situações em que você precisa recuperar manualmente os dados de auditoria para uma investigação ou incidente específico, especialmente para intervalos de datas mais longos em organizações maiores, usar o cmdlet **Search-UnifiedAuditLog** pode ser a melhor opção. Este artigo inclui um script Windows PowerShell que usa o cmdlet para recuperar até 50.000 registros de auditoria e, em seguida, exportá-los para um arquivo CSV que você pode formatar usando o Power Query no Excel para ajudar em sua revisão. O uso do script neste artigo também minimiza a chance de que grandes pesquisas de log de auditoria expirem no serviço.

## <a name="before-you-run-the-script"></a>Antes de executar o script

- O log de Auditoria deve ser habilitado para que sua organização use com sucesso o script para retornar os registros de auditoria. O log de Auditoria é ativado por padrão para organizações empresariais Microsoft 365 e Office 365. Para verificar se a pesquisa de log de auditoria está ativada para sua organização, você pode executar o seguinte comando no Exchange Online Windows PowerShell:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```
  
  O valor de `True` para a propriedade **UnifiedAuditLogIngestionEnabled** indica que a pesquisa de registro de auditoria está ativada.

- Você deve ser atribuído à função Logs de Auditoria somente para exibição ou Logs de auditoria no Exchange Online para executar o script com êxito. Por padrão, essas funções são atribuídas aos grupos de funções Gerenciamento de Conformidade e Gerenciamento de Organização na página Permissões do centro de administração do Exchange. Para obter mais informações, confira a seção "Requisitos para pesquisar o registro de auditoria" em [Pesquisar o registro de auditoria no centro de conformidade](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).

- O script pode demorar muito para ser concluído. Quanto tempo leva para ser executado depende do intervalo de datas e do tamanho do intervalo para o qual você configura o script para recuperar os registros de auditoria. Intervalos de datas maiores e intervalos menores resultarão em um longo tempo de execução. Confira a tabela na Etapa 2 para obter mais informações sobre o intervalo de datas e intervalos.

- O script de exemplo fornecido neste artigo não é compatível com nenhum programa ou serviço de suporte padrão da Microsoft. O script de amostra é fornecido COMO ESTÁ, sem garantia de nenhum tipo. A Microsoft também se isenta de todas as garantias implícitas, incluindo, sem limitação, quaisquer garantias implícitas de comercialização ou adequação a uma finalidade específica. Todo o risco decorrente do uso ou desempenho do script de amostra e da documentação permanece com você. Em nenhuma hipótese a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou entrega do script será responsável por quaisquer danos (incluindo, sem limitação, danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais, ou outra perda pecuniária) decorrente do uso ou da incapacidade de usar o script ou documentação de amostra, mesmo que a Microsoft tenha sido avisada da possibilidade de tais danos.

## <a name="step-1-connect-to-exchange-online-powershell"></a>Etapa 1: Conecte-se ao Exchange Online Windows PowerShell

A primeira etapa é conectar-se ao Exchange Online Windows PowerShell. Você pode se conectar usando autenticação moderna ou com autenticação multifator (MFA). Para obter instruções passo a passo, confira [Conectar-se ao Exchange Online Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>Etapa 2: modificar e executar o script para recuperar os registros de auditoria

Depois de se conectar ao Exchange Online Windows PowerShell, a próxima etapa é criar, modificar e executar o script para recuperar os dados de auditoria. As primeiras sete linhas no script de pesquisa de log de auditoria contêm as seguintes variáveis ​​que você pode modificar para configurar sua pesquisa. Consulte a tabela na etapa 2 para obter uma descrição dessas variáveis.

1. Salve o texto a seguir em um script do Windows PowerShell usando um sufixo de nome de arquivo .ps1. Por exemplo, SearchAuditLog.ps1.

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
    $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
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

    $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
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

2. Modifique as variáveis ​​listadas na tabela a seguir para configurar os critérios de pesquisa. O script inclui valores de amostra para essas variáveis, mas você deve alterá-los (a menos que indicado de outra forma) para atender aos seus requisitos específicos.

   |Variável|Valor de amostra|Descrição|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|Especifica o nome e a localização do arquivo de log que contém informações sobre o andamento da pesquisa de log de auditoria executada pelo script. O script grava carimbos de data/hora UTC no arquivo de log.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|Especifica o nome e a localização do arquivo CSV que contém os registros de auditoria retornados pelo script.|
   |`[DateTime]$start` e `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|Especifica o intervalo de datas para a pesquisa do log de auditoria. O script retornará registros de atividades de auditoria que ocorreram dentro do intervalo de datas especificado. Por exemplo, para retornar atividades realizadas em janeiro de 2021, você pode usar uma data de início de `"2021-01-01"`e uma data de término de`"2021-01-31"` (certifique-se de colocar os valores entre aspas duplas). O valor de amostra no script retorna registros para atividades realizadas nas 24 horas anteriores. Se você não incluir um carimbo de data/hora no valor, o carimbo de data/hora padrão será 0h (meia-noite) na data especificada.|
   |`$record`|AzureActiveDirectory|Especifica o tipo de registro das atividades de auditoria (também chamadas de *operações*) a serem pesquisadas. Esta propriedade indica o serviço ou recurso em que uma atividade foi acionada. Para obter uma lista dos tipos de registro que você pode usar para esta variável, confira [Tipo de registro do log de Auditoria](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype). Você pode usar o nome do tipo de registro ou valor ENUM. <br/><br/>**Dica:** para retornar registros de auditoria para todos os tipos de registro, use o valor `$null` (sem aspas duplas).|
   |`$resultSize`|5000|Especifica o número de resultados retornados sempre que o cmdlet **Search-UnifiedAuditLog** é chamado pelo script (chamado de *conjunto de resultados*). O valor de 5.000 é o valor máximo compatível com o cmdlet. Deixe este valor como está.|
   |`$intervalMinutes`|60|Para ajudar a superar o limite de 5.000 registros retornados, essa variável pega o intervalo de dados especificado e o divide em intervalos de tempo menores. Agora, cada intervalo, não todo o intervalo de datas, está sujeito ao limite de saída de 5.000 registros do comando. O valor padrão de 5.000 registros por intervalo de 60 minutos dentro do intervalo de datas deve ser suficiente para a maioria das organizações. Mas, se o script retornar um erro que diz, `maximum results limitation reached`, diminua o intervalo de tempo (por exemplo, para 30 minutos ou mesmo 15 minutos) e execute o script novamente.|
   ||||

   A maioria das variáveis ​​listadas na tabela anterior correspondem aos parâmetros do cmdlet **Search-UnifiedAuditLog**. Para obter mais informações sobre esses parâmetros, confira[Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog).

3. No seu computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script modificado.

4. Execute o script no Exchange Online Windows PowerShell; por exemplo:

   ```powershell
   .\SearchAuditLog.ps1
   ```

O script exibe mensagens de progresso durante a execução. Após a conclusão da execução do script, ele cria o arquivo de log e o arquivo CSV que contém os registros de auditoria e os salva nas pastas definidas pelas variáveis ​​`$logFile` e `$outputFile`.

> [!IMPORTANT]
> Há um limite de 50.000 para o número máximo de registros de auditoria retornados cada vez que você executa este script. Se você executar este script e ele retornar 50.000 resultados, é provável que os registros de auditoria para atividades que ocorreram dentro do intervalo de datas não foram incluídos. Se isso acontecer, recomendamos que você divida o período em durações menores e execute novamente o script para cada período. Por exemplo, se um intervalo de datas de 90 dias retornar 50.000 resultados, você poderá executar o script novamente duas vezes, uma nos primeiros 45 dias do intervalo e, em seguida, nos próximos 45 dias.

## <a name="step-3-format-and-view-the-audit-records"></a>Etapa 3: formate e visualize os registros de auditoria

Depois de executar o script e exportar os registros de auditoria para um arquivo CSV, você pode formatar o CSV para facilitar a revisão e análise dos registros de auditoria. Uma maneira de fazer isso é usar o recurso de transformação JSON do Power Query no Excel para dividir cada propriedade no objeto JSON na coluna **AuditData** em sua própria coluna. Para obter instruções passo a passo, consulte "Etapa 2: formatar o registro de auditoria exportado usando o Power Query Editor" em [Exportar, configurar e visualizar registros de registro de auditoria](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).
