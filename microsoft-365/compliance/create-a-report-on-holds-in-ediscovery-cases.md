---
title: Criar um relatório sobre retenções em ocorrências de Descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: Saiba como gerar um relatório que contém informações sobre todas as ressarcições associadas a casos de Descoberta e.
ms.openlocfilehash: 04282f6f2481d892fa16d685936efeec55feae77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908405"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a>Criar um relatório sobre retenções em ocorrências de Descoberta eletrônica

O script deste artigo permite que os administradores de Descobertas EDiscovery e gerentes de Descobertas Públicas gerenciem um relatório que contém informações sobre todas as resvasões associadas aos casos de Descoberta eDiscovery no centro de conformidade no Office 365 ou Microsoft 365. O relatório contém informações como o nome do caso ao que uma hold está associada, os locais de conteúdo que são colocados em espera e se a espera é baseada em consulta. Se houver casos que não tenham qualquer ressução, o script criará um relatório adicional com uma lista de casos sem ressál.

Consulte a [seção Mais informações](#more-information) para obter uma descrição detalhada das informações incluídas no relatório.

## <a name="admin-requirements-and-script-information"></a>Requisitos de administrador e informações de script

- Para gerar um relatório sobre todos os casos de Descoberta e Descoberta Na sua organização, você precisa ser um Administrador de Descoberta De eDiscovery em sua organização. Se você for um Gerente de Descoberta De eDiscovery, o relatório incluirá apenas informações sobre os casos que você pode acessar. Para obter mais informações sobre permissões de Descoberta e, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

- O script deste artigo tem tratamento mínimo de erros. O objetivo principal é criar rapidamente um relatório sobre os ressarcições associados aos casos de Descoberta e Na organização.

- Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Etapa 1: Conexão ao Centro de Conformidade e Segurança & PowerShell

A primeira etapa é conectar-se ao PowerShell do Centro de Conformidade e Segurança da sua organização. Para obter instruções passo a passo, consulte [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](/powershell/exchange/connect-to-scc-powershell).

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Etapa 2: executar o script para relatar sobre ressarcições associadas a casos de Descoberta e

Depois de se conectar ao Centro de Conformidade & Segurança do PowerShell, a próxima etapa é criar e executar o script que coleta informações sobre os casos de Descoberta Digital em sua organização.

1. Salve o texto a seguir em um arquivo Windows PowerShell script usando um sufixo de nome de arquivo de .ps1; por exemplo, CaseHoldsReport.ps1.

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. Na sessão Windows PowerShell aberta na Etapa 1, vá para a pasta onde você salvou o script.

3. Execute o script; por exemplo:

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   O script solicitará que uma pasta de destino salve o relatório.

4. Digite o nome completo do caminho da pasta para salvar o relatório e pressione **Enter**.

   > [!TIP]
   > Para salvar o relatório na mesma pasta em que o script está localizado, digite um ponto (".") quando solicitado a uma pasta de destino. Para salvar o relatório em uma subpasta na pasta onde o script está localizado, basta digitar o nome da subpasta.

   O script começa a coletar informações sobre todos os casos de Descoberta eDiscovery em sua organização. Não acesse o arquivo de relatório enquanto o script estiver em execução. Depois que o script for concluído, uma mensagem de confirmação será exibida na Windows PowerShell sessão. Depois que essa mensagem for exibida, você poderá acessar o relatório na pasta especificada na Etapa 4. O nome do arquivo do relatório é `CaseHoldsReport<DateTimeStamp>.csv` .

   Em termos adicionais, o script também cria um relatório com uma lista de casos que não têm nenhuma ressalção. O nome do arquivo para este relatório é `CaseswithNoHolds<DateTimeStamp>.csv` .

   Aqui está um exemplo de execução do CaseHoldsReport.ps1 script.

   ![A saída após a execução do CaseHoldsReport.ps1 script](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a>Mais informações

O relatório de caso contém o relatório criado quando você executar o script neste artigo contém as seguintes informações sobre cada ressução. Como explicado anteriormente, você precisa ser um Administrador de Descoberta De e Para retornar informações para todos os ressarce em sua organização. Para obter mais informações sobre os casos de segurança, consulte [eDiscovery cases](./get-started-core-ediscovery.md).

- O nome da isenção e o nome do caso de Descoberta E que a responsabilidade está associada.

- Se o caso de Descoberta eDiscovery está ativo ou fechado.

- Se a espera está habilitada ou desabilitada.

- Os membros do caso de Descoberta e que a responsabilidade está associada. Os membros do caso podem exibir ou gerenciar um caso, dependendo das permissões de Descoberta De eDiscover que foram atribuídas.

- A hora e a data em que o caso foi criado.

- Se um caso for fechado, a pessoa que o fechou e a hora e a data foram fechadas.

- As Exchange caixas de correio e SharePoint locais de sites que estão em espera.

- Se a espera for baseada em consulta, a sintaxe de consulta.

- A hora e a data em que a espera foi criada e a pessoa que a criou.

- A hora e a data em que a espera foi alterada pela última vez e a pessoa que a alterou.