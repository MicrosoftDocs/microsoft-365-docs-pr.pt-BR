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
description: Saiba como gerar um relatório que contenha informações sobre todas as retém associadas a ocorrências de Descobertas e Descobertas.
ms.openlocfilehash: 35e432104e7c1358887eb89ae96b9bb0d1d12a0f
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546973"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="07c3a-103">Criar um relatório sobre retenções em ocorrências de Descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="07c3a-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="07c3a-104">O script neste artigo permite que os administradores de Descobertas e Gerentes de Descobertas De eDiscovery gerem um relatório que contém informações sobre todas as reações associadas a ocorrências de Descoberta e No centro de conformidade no Office 365 ou no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07c3a-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="07c3a-105">O relatório contém informações como o nome da ocorrência à que uma isenção está associada, os locais de conteúdo que são colocados em espera e se a isenção é baseada em consulta.</span><span class="sxs-lookup"><span data-stu-id="07c3a-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="07c3a-106">Se houver casos que não tenham retém, o script criará um relatório adicional com uma lista de casos sem retém.</span><span class="sxs-lookup"><span data-stu-id="07c3a-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="07c3a-107">Consulte a [seção Mais](#more-information) informações para obter uma descrição detalhada das informações incluídas no relatório.</span><span class="sxs-lookup"><span data-stu-id="07c3a-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="07c3a-108">Requisitos de administrador e informações de script</span><span class="sxs-lookup"><span data-stu-id="07c3a-108">Admin requirements and script information</span></span>

- <span data-ttu-id="07c3a-109">Para gerar um relatório sobre todas as ocorrências de Descobertas Na sua organização, você precisa ser Um Administrador de Descobertas Na sua organização.</span><span class="sxs-lookup"><span data-stu-id="07c3a-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="07c3a-110">Se você for um Gerente de Descoberta eDiscovery, o relatório incluirá apenas informações sobre os casos que você pode acessar.</span><span class="sxs-lookup"><span data-stu-id="07c3a-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="07c3a-111">Para obter mais informações sobre permissões de Descoberta eDiscovery, consulte [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="07c3a-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="07c3a-112">O script neste artigo tem tratamento mínimo de erros.</span><span class="sxs-lookup"><span data-stu-id="07c3a-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="07c3a-113">O objetivo principal é criar rapidamente um relatório sobre as isenções que estão associadas aos casos de Descoberta eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07c3a-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="07c3a-p104">Os scripts de exemplo fornecidos neste tópico não são compatíveis com nenhum serviço ou programa de suporte padrão da Microsoft. Os scripts de exemplo são fornecidos COMO ESTÃO sem qualquer tipo de garantia. A Microsoft também se isenta de todas as garantias implícitas, incluindo sem limitações quaisquer garantias aplicáveis de padrões de comercialização ou de adequação a uma finalidade específica. Todos os riscos decorrentes do uso ou da execução da documentação ou scripts de exemplo serão de sua responsabilidade. De modo algum a Microsoft, seus autores ou qualquer outra pessoa envolvida na criação, produção ou veiculação dos scripts serão considerados responsáveis por quaisquer danos (incluindo sem limitações danos por perda de lucros comerciais, interrupção de negócios, perda de informações comerciais ou outras perdas pecuniárias) resultantes do uso ou da incapacidade de uso da documentação ou scripts de exemplo, mesmo que a Microsoft tenha sido alertada sobre a possibilidade de tais danos.</span><span class="sxs-lookup"><span data-stu-id="07c3a-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="07c3a-119">Etapa 1: Conectar-se ao PowerShell do Centro de Conformidade & segurança</span><span class="sxs-lookup"><span data-stu-id="07c3a-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="07c3a-120">A primeira etapa é conectar-se ao PowerShell do Centro de & Conformidade e Segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="07c3a-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="07c3a-121">Para obter instruções passo a passo, confira [Conectar-se ao Centro de Segurança e Conformidade no PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="07c3a-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="07c3a-122">Etapa 2: Executar o script para relatar resções associadas a casos de Descoberta</span><span class="sxs-lookup"><span data-stu-id="07c3a-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="07c3a-123">Depois de & se conectar ao PowerShell do Centro de Conformidade e Segurança, a próxima etapa é criar e executar o script que coleta informações sobre os casos de Descoberta eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07c3a-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="07c3a-124">Salve o texto a seguir em um arquivo de script do Windows PowerShell usando um sufixo de nome de arquivo .ps1; por exemplo, CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="07c3a-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

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

2. <span data-ttu-id="07c3a-125">Na sessão do Windows PowerShell aberta na Etapa 1, vá para a pasta onde você salvou o script.</span><span class="sxs-lookup"><span data-stu-id="07c3a-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="07c3a-126">Execute o script; por exemplo:</span><span class="sxs-lookup"><span data-stu-id="07c3a-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="07c3a-127">O script solicitará uma pasta de destino para salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="07c3a-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="07c3a-128">Digite o nome do caminho completo da pasta para salvar o relatório e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="07c3a-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="07c3a-129">Para salvar o relatório na mesma pasta em que o script está localizado, digite um ponto (".") quando solicitado a uma pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="07c3a-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="07c3a-130">Para salvar o relatório em uma subpasta na pasta onde o script está localizado, basta digitar o nome da subpasta.</span><span class="sxs-lookup"><span data-stu-id="07c3a-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="07c3a-131">O script começa a coletar informações sobre todos os casos de Descoberta eDiscovery em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07c3a-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="07c3a-132">Não acesse o arquivo de relatório enquanto o script estiver em execução.</span><span class="sxs-lookup"><span data-stu-id="07c3a-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="07c3a-133">Depois que o script for concluído, uma mensagem de confirmação será exibida na sessão do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07c3a-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="07c3a-134">Depois que essa mensagem for exibida, você poderá acessar o relatório na pasta especificada na Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="07c3a-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="07c3a-135">O nome do arquivo para o relatório é `CaseHoldsReport<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="07c3a-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="07c3a-136">Além disso, o script também cria um relatório com uma lista de casos que não têm retém.</span><span class="sxs-lookup"><span data-stu-id="07c3a-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="07c3a-137">O nome do arquivo para este relatório é `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="07c3a-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="07c3a-138">Aqui está um exemplo de execução do script CaseHoldsReport.ps1 script.</span><span class="sxs-lookup"><span data-stu-id="07c3a-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![A saída após a execução do CaseHoldsReport.ps1 script](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="07c3a-140">Mais informações</span><span class="sxs-lookup"><span data-stu-id="07c3a-140">More information</span></span>

<span data-ttu-id="07c3a-141">O relatório de ocorrências criado quando você executar o script neste artigo contém as seguintes informações sobre cada espera.</span><span class="sxs-lookup"><span data-stu-id="07c3a-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="07c3a-142">Conforme explicado anteriormente, você precisa ser um Administrador de Descobertas e Para retornar informações sobre todas as retém em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07c3a-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="07c3a-143">Para obter mais informações sobre retém de caso, consulte [ocorrências de Descoberta eDiscovery](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="07c3a-143">For more information about case holds, see [eDiscovery cases](ediscovery-cases.md).</span></span>

- <span data-ttu-id="07c3a-144">O nome da isenção e o nome da ocorrência de Descoberta e à que a isenção está associada.</span><span class="sxs-lookup"><span data-stu-id="07c3a-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="07c3a-145">Se o caso de Descoberta eDiscovery está ativo ou fechado.</span><span class="sxs-lookup"><span data-stu-id="07c3a-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="07c3a-146">Se a espera está habilitada ou desabilitada ou não.</span><span class="sxs-lookup"><span data-stu-id="07c3a-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="07c3a-147">Os membros da ocorrência de Descoberta e à que a isenção está associada.</span><span class="sxs-lookup"><span data-stu-id="07c3a-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="07c3a-148">Os membros da ocorrência podem exibir ou gerenciar uma ocorrência, dependendo das permissões de Descoberta eDiscovery que eles foram atribuídos.</span><span class="sxs-lookup"><span data-stu-id="07c3a-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="07c3a-149">A hora e a data em que o caso foi criado.</span><span class="sxs-lookup"><span data-stu-id="07c3a-149">The time and date the case was created.</span></span>

- <span data-ttu-id="07c3a-150">Se um caso for fechado, a pessoa que o fechou e a hora e a data em que foi fechado.</span><span class="sxs-lookup"><span data-stu-id="07c3a-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="07c3a-151">As caixas de correio do Exchange e locais de sites do SharePoint que estão em espera.</span><span class="sxs-lookup"><span data-stu-id="07c3a-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="07c3a-152">Se a isenção for baseada em consulta, a sintaxe da consulta.</span><span class="sxs-lookup"><span data-stu-id="07c3a-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="07c3a-153">A hora e a data em que a espera foi criada e a pessoa que a criou.</span><span class="sxs-lookup"><span data-stu-id="07c3a-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="07c3a-154">A hora e a data em que a espera foi alterada pela última vez e a pessoa que o alterou.</span><span class="sxs-lookup"><span data-stu-id="07c3a-154">The time and date the hold was last changed and the person who changed it.</span></span>
