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
description: Saiba como gerar um relatório que contém informações sobre todas as isenções associadas a ocorrências de descoberta eletrônica.
ms.openlocfilehash: b4387434d57373f9569b6472786e8ad40de85b21
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818030"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="542b5-103">Criar um relatório sobre retenções em ocorrências de Descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="542b5-103">Create a report on holds in eDiscovery cases</span></span>
  
<span data-ttu-id="542b5-104">O script neste artigo permite que os administradores de descoberta eletrônica e os gerentes de descoberta eletrônica gerem um relatório que contém informações sobre todas as isenções associadas a casos de descoberta eletrônica no centro de conformidade no Office 365 ou Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="542b5-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="542b5-105">O relatório contém informações como o nome do caso ao qual uma retenção está associada, os locais de conteúdo que são colocados em espera e se a retenção é baseada em consulta.</span><span class="sxs-lookup"><span data-stu-id="542b5-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="542b5-106">Se houver casos em que não haja isenções, o script criará um relatório adicional com uma lista de casos sem isenções.</span><span class="sxs-lookup"><span data-stu-id="542b5-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="542b5-107">Consulte a seção [mais informações](#more-information) para obter uma descrição detalhada das informações incluídas no relatório.</span><span class="sxs-lookup"><span data-stu-id="542b5-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>
  
## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="542b5-108">Requisitos de administração e informações de script</span><span class="sxs-lookup"><span data-stu-id="542b5-108">Admin requirements and script information</span></span>

- <span data-ttu-id="542b5-109">Para gerar um relatório sobre todas as ocorrências de descoberta eletrônica em sua organização, você precisa ser um administrador de descoberta eletrônica em sua organização.</span><span class="sxs-lookup"><span data-stu-id="542b5-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="542b5-110">Se você for um gerente de descoberta eletrônica, o relatório só incluirá informações sobre os casos que você pode acessar.</span><span class="sxs-lookup"><span data-stu-id="542b5-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="542b5-111">Para obter mais informações sobre permissões de descoberta eletrônica, consulte [atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="542b5-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="542b5-112">O script deste artigo tem um tratamento de erros mínimo.</span><span class="sxs-lookup"><span data-stu-id="542b5-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="542b5-113">O objetivo principal é criar rapidamente um relatório sobre as isenções associadas às ocorrências de descoberta eletrônica em sua organização.</span><span class="sxs-lookup"><span data-stu-id="542b5-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="542b5-p104">Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="542b5-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="542b5-119">Etapa 1: conectar-se ao PowerShell do centro de conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="542b5-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="542b5-120">A primeira etapa é conectar-se ao PowerShell de segurança & centro de conformidade da sua organização.</span><span class="sxs-lookup"><span data-stu-id="542b5-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="542b5-121">Para obter instruções passo a passo, confira [Conectar-se ao Centro de Segurança e Conformidade no PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="542b5-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="542b5-122">Se a sua conta do Microsoft 365 utiliza autenticação multifator (MFA) ou autenticação federada, você não pode utilizar as instruções do tópico anterior para conectar no Centro de Conformidade e Segurança do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="542b5-122">If your Microsoft 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="542b5-123">Em vez disso, confira as instruções no tópico [ Conectar-se ao Centro de Segurança e Conformidade no PowerShell, usando a autenticação multifator](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="542b5-123">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="542b5-124">Etapa 2: executar o script para relatar em suspensões associadas a ocorrências de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="542b5-124">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="542b5-125">Depois de se conectar ao PowerShell do centro de conformidade e segurança &, a próxima etapa é criar e executar o script que coleta informações sobre os casos de descoberta eletrônica em sua organização.</span><span class="sxs-lookup"><span data-stu-id="542b5-125">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="542b5-126">Salve o seguinte texto em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo. ps1; por exemplo, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="542b5-126">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="542b5-127">Na sessão do Windows PowerShell que foi aberta na etapa 1, vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="542b5-127">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="542b5-128">Executar o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="542b5-128">Run the script; for example:</span></span>

    ```powershell
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="542b5-129">O script solicitará uma pasta de destino para salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="542b5-129">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="542b5-130">Digite o nome do caminho completo da pasta para salvar o relatório e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="542b5-130">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="542b5-131">Para salvar o relatório na mesma pasta em que o script está localizado, digite um ponto (".") quando solicitado a fornecer uma pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="542b5-131">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="542b5-132">Para salvar o relatório em uma subpasta na pasta em que o script está localizado, basta digitar o nome da subpasta.</span><span class="sxs-lookup"><span data-stu-id="542b5-132">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="542b5-133">O script começa a coletar informações sobre todos os casos de descoberta eletrônica em sua organização.</span><span class="sxs-lookup"><span data-stu-id="542b5-133">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="542b5-134">Não acesse o arquivo de relatório enquanto o script estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="542b5-134">Don't access the report file while the script is running.</span></span> <span data-ttu-id="542b5-135">Depois que o script for concluído, uma mensagem de confirmação será exibida na sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="542b5-135">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="542b5-136">Depois que esta mensagem for exibida, você poderá acessar o relatório na pasta que você especificou na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="542b5-136">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="542b5-137">O nome de arquivo para o relatório é `CaseHoldsReport<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="542b5-137">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="542b5-138">O script também cria um relatório com uma lista de casos que não tem nenhuma isenção.</span><span class="sxs-lookup"><span data-stu-id="542b5-138">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="542b5-139">O nome de arquivo para esse relatório é `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="542b5-139">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="542b5-140">Veja um exemplo de execução do script CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="542b5-140">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![A saída após a execução do script de CaseHoldsReport.ps1](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="542b5-142">Mais informações</span><span class="sxs-lookup"><span data-stu-id="542b5-142">More information</span></span>

<span data-ttu-id="542b5-143">O relatório de ocorrências que é criado quando você executa o script neste artigo contém as seguintes informações sobre cada isenção.</span><span class="sxs-lookup"><span data-stu-id="542b5-143">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="542b5-144">Conforme explicado anteriormente, você precisa ser um administrador de descoberta eletrônica para retornar informações de todas as isenções em sua organização.</span><span class="sxs-lookup"><span data-stu-id="542b5-144">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="542b5-145">Para obter mais informações sobre retenções de caso, confira [casos de descoberta eletrônica](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="542b5-145">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="542b5-146">O nome da retenção e o nome da ocorrência de descoberta eletrônica à qual a suspensão está associada.</span><span class="sxs-lookup"><span data-stu-id="542b5-146">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="542b5-147">Se a ocorrência de descoberta eletrônica está ativa ou fechada.</span><span class="sxs-lookup"><span data-stu-id="542b5-147">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="542b5-148">Se a retenção está habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="542b5-148">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="542b5-149">Os membros da ocorrência de descoberta eletrônica à qual a suspensão está associada.</span><span class="sxs-lookup"><span data-stu-id="542b5-149">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="542b5-150">Os membros de caso podem exibir ou gerenciar um caso, dependendo das permissões de descoberta eletrônica que foram atribuídas.</span><span class="sxs-lookup"><span data-stu-id="542b5-150">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="542b5-151">A hora e a data em que o caso foi criado.</span><span class="sxs-lookup"><span data-stu-id="542b5-151">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="542b5-152">Se uma ocorrência estiver fechada, a pessoa que a fechou e a hora e a data em que ela foi fechada.</span><span class="sxs-lookup"><span data-stu-id="542b5-152">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="542b5-153">Os locais de caixas de correio do Exchange e sites do SharePoint que estão em espera.</span><span class="sxs-lookup"><span data-stu-id="542b5-153">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="542b5-154">Se a retenção for baseada em consulta, a sintaxe da consulta.</span><span class="sxs-lookup"><span data-stu-id="542b5-154">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="542b5-155">A hora e a data em que o bloqueio foi criado e a pessoa que o criou.</span><span class="sxs-lookup"><span data-stu-id="542b5-155">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="542b5-156">A hora e a data em que a retenção foi alterada pela última vez e a pessoa que a alterou.</span><span class="sxs-lookup"><span data-stu-id="542b5-156">The time and date the hold was last changed and the person who changed it.</span></span>
