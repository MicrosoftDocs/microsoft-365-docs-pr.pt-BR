---
title: Criar um relatório sobre isenções em casos de descoberta eletrônica no Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: Use o script neste artigo para gerar um relatório que contenha informações sobre todas as isenções associadas a ocorrências de descoberta eletrônica no centro de conformidade no Office 365 ou Microsoft 365.
ms.openlocfilehash: 7118b62dcd42413309e33c45e80516c8822faeff
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072115"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>Criar um relatório sobre isenções em casos de descoberta eletrônica no Office 365
  
O script neste artigo permite que os administradores de descoberta eletrônica e os gerentes de descoberta eletrônica gerem um relatório que contém informações sobre todas as isenções associadas a casos de descoberta eletrônica no centro de conformidade no Office 365 ou Microsoft 365. O relatório contém informações como o nome do caso ao qual uma retenção está associada, os locais de conteúdo que são colocados em espera e se a retenção é baseada em consulta. Se houver casos em que não haja isenções, o script criará um relatório adicional com uma lista de casos sem isenções.

Consulte a seção [mais informações](#more-information) para obter uma descrição detalhada das informações incluídas no relatório. 
  
## <a name="before-you-begin"></a>Antes de começar

- Para gerar um relatório sobre todas as ocorrências de descoberta eletrônica em sua organização, você precisa ser um administrador de descoberta eletrônica em sua organização. Se você for um gerente de descoberta eletrônica, o relatório só incluirá informações sobre os casos que você pode acessar. Para obter mais informações sobre permissões de descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).
    
- O script deste artigo tem um tratamento de erros mínimo. O objetivo principal é criar rapidamente um relatório sobre as isenções associadas às ocorrências de descoberta eletrônica em sua organização.
    
- Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a>Etapa 1: conectar-se ao PowerShell do centro de conformidade & segurança

A primeira etapa é conectar-se ao centro de conformidade & segurança da sua organização.
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, `ConnectSCC.ps1`. 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. No computador local, abra o Windows PowerShell e vá para a pasta onde você salvou o script. 
    
3. Executar o script; por exemplo:

    ```
    .\ConnectSCC.ps1
    ```
   
4. Quando solicitar suas credenciais, insira seu endereço de email e senha e clique em **OK**. 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>Etapa 2: executar o script para relatar em suspensões associadas a ocorrências de descoberta eletrônica

Depois de se conectar ao PowerShell do centro de conformidade e segurança &, a próxima etapa é criar e executar o script que coleta informações sobre os casos de descoberta eletrônica em sua organização. 
  
1. Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, CaseHoldsReport. ps1. 
    
  ```
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

2. Na sessão do Windows PowerShell que foi aberta na etapa 1, vá para a pasta onde você salvou o script. 
    
3. Executar o script; por exemplo:

    ```
    .\CaseHoldsReport.ps1
    ```

    O script solicitará uma pasta de destino para salvar o relatório. 
    
4. Digite o nome do caminho completo da pasta para salvar o relatório e pressione **Enter**.
    
    > [!TIP]
    > Para salvar o relatório na mesma pasta em que o script está localizado, digite um ponto (".") quando solicitado a fornecer uma pasta de destino. Para salvar o relatório em uma subpasta na pasta em que o script está localizado, basta digitar o nome da subpasta. 
  
    O script começa a coletar informações sobre todos os casos de descoberta eletrônica em sua organização. Não acesse o arquivo de relatório enquanto o script estiver em execução. Depois que o script for concluído, uma mensagem de confirmação será exibida na sessão do Windows PowerShell. Depois que esta mensagem for exibida, você poderá acessar o relatório na pasta que você especificou na etapa 4. O nome de arquivo para o relatório `CaseHoldsReport<DateTimeStamp>.csv`é.

    O script também cria um relatório com uma lista de casos que não tem nenhuma isenção. O nome de arquivo para esse relatório `CaseswithNoHolds<DateTimeStamp>.csv`é.
    
    Veja um exemplo de execução do script CaseHoldsReport. ps1. 
    
    ![A saída após a execução do script CaseHoldsReport. ps1](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>Mais informações

O relatório de ocorrências que é criado quando você executa o script neste artigo contém as seguintes informações sobre cada isenção. Conforme explicado anteriormente, você precisa ser um administrador de descoberta eletrônica para retornar informações de todas as isenções em sua organização. Para obter mais informações sobre retenções de caso, confira [casos de descoberta eletrônica](ediscovery-cases.md).
  
  - O nome da retenção e o nome da ocorrência de descoberta eletrônica à qual a suspensão está associada.
    
  - Se a ocorrência de descoberta eletrônica está ativa ou fechada.
    
  - Se a retenção está habilitada ou desabilitada.
    
  - Os membros da ocorrência de descoberta eletrônica à qual a suspensão está associada. Os membros de caso podem exibir ou gerenciar um caso, dependendo das permissões de descoberta eletrônica que foram atribuídas.
    
  - A hora e a data em que o caso foi criado.
    
  - Se uma ocorrência estiver fechada, a pessoa que a fechou e a hora e a data em que ela foi fechada.
    
  - Os locais de caixas de correio do Exchange e sites do SharePoint que estão em espera.
    
  - Se a retenção for baseada em consulta, a sintaxe da consulta.
    
  - A hora e a data em que o bloqueio foi criado e a pessoa que o criou.
    
  - A hora e a data em que a retenção foi alterada pela última vez e a pessoa que a alterou.
