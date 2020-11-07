---
title: Coletar informações de diagnóstico de descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba mais sobre como coletar informações de diagnóstico de descoberta eletrônica para um caso de suporte da Microsoft.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944385"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="0608c-103">Coletar informações de diagnóstico de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="0608c-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="0608c-104">Ocasionalmente, os engenheiros de suporte da Microsoft exigem informações específicas sobre o problema quando você abre um caso de suporte relacionado à descoberta eletrônica principal ou à descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="0608c-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="0608c-105">Este artigo fornece orientação sobre como coletar informações de diagnóstico para ajudar os engenheiros de suporte a investigar e resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="0608c-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="0608c-106">Normalmente, você não precisa coletar essas informações até que seja solicitado por um engenheiro de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0608c-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0608c-107">A saída dos cmdlets e das informações de diagnóstico descritas neste artigo pode incluir informações confidenciais sobre litígios ou investigações internas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0608c-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="0608c-108">Antes de enviar as informações de diagnóstico brutos para o suporte da Microsoft, você deve revisar as informações e redigir quaisquer informações confidenciais (como nomes ou outras informações sobre as partes de litígio ou investigação) substituindo-as por `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="0608c-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="0608c-109">O uso desse método também indicará ao engenheiro de suporte da Microsoft que as informações foram redigidas.</span><span class="sxs-lookup"><span data-stu-id="0608c-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="0608c-110">Coletar informações de diagnóstico para a descoberta eletrônica principal</span><span class="sxs-lookup"><span data-stu-id="0608c-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="0608c-111">A coleta de informações de diagnóstico para a descoberta eletrônica principal é baseada em cmdlet, portanto, você terá que usar o PowerShell de segurança & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="0608c-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="0608c-112">Os seguintes exemplos do PowerShell executarão cmdlets e, em seguida, salvarão a saída em um arquivo de texto especificado.</span><span class="sxs-lookup"><span data-stu-id="0608c-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="0608c-113">Na maioria dos casos de suporte, você só deve executar um desses comandos.</span><span class="sxs-lookup"><span data-stu-id="0608c-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="0608c-114">Para executar os cmdlets a seguir, [Conecte-se ao PowerShell </span> do centro de conformidade & segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="0608c-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="0608c-115">Depois que você estiver conectado, execute um ou mais dos seguintes comandos e certifique-se de substituir os espaços reservados pelos nomes de objeto reais.</span><span class="sxs-lookup"><span data-stu-id="0608c-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="0608c-116">Após analisar o arquivo de texto gerado e redigir informações confidenciais, envie-o ao engenheiro de suporte da Microsoft em seu caso.</span><span class="sxs-lookup"><span data-stu-id="0608c-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="0608c-117">Você também pode executar os comandos nesta seção para coletar informações de diagnóstico para as pesquisas e exportações listadas na página de **pesquisa de conteúdo** no centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0608c-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="0608c-118">Coletar informações sobre pesquisas</span><span class="sxs-lookup"><span data-stu-id="0608c-118">Collect information about searches</span></span>

<span data-ttu-id="0608c-119">O comando a seguir coleta informações que são úteis ao investigar problemas com uma pesquisa de conteúdo ou uma pesquisa associada a um caso de descoberta eletrônica principal.</span><span class="sxs-lookup"><span data-stu-id="0608c-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="0608c-120">Coletar informações sobre ações de pesquisa</span><span class="sxs-lookup"><span data-stu-id="0608c-120">Collect information about search actions</span></span>

<span data-ttu-id="0608c-121">O comando a seguir coleta informações para investigar problemas com a visualização, exportação ou limpeza dos resultados de uma pesquisa de conteúdo ou de uma pesquisa associada a um caso de descoberta eletrônica principal.</span><span class="sxs-lookup"><span data-stu-id="0608c-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="0608c-122">Você pode identificar o nome da ação de pesquisa clicando em uma exportação que está listada na guia **exportações** . Para identificar os nomes das ações de visualização e limpeza, você pode executar o cmdlet **Get-ComplianceSearchAction** para exibir uma lista de todas as ações.</span><span class="sxs-lookup"><span data-stu-id="0608c-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="0608c-123">O formato do nome da ação de pesquisa é construído acrescentando `_Preview` , `_Export` ou `_Purge` ao nome da pesquisa correspondente.</span><span class="sxs-lookup"><span data-stu-id="0608c-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="0608c-124">Coletar informações sobre as suspensões de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="0608c-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="0608c-125">Quando um controle de descoberta eletrônica associado a um caso de descoberta eletrônica principal não está funcionando conforme o esperado, execute o seguinte comando para coletar informações sobre a política de bloqueio de caso e a regra de bloqueio de caso associada para a descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="0608c-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="0608c-126">O *nome da política de retenção de caso* no seguinte comando é o mesmo que o nome da descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="0608c-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="0608c-127">Você pode identificar esse nome nas guias **isenções** no caso de descoberta eletrônica principal.</span><span class="sxs-lookup"><span data-stu-id="0608c-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="0608c-128">Coletar todas as informações do caso</span><span class="sxs-lookup"><span data-stu-id="0608c-128">Collect all case information</span></span>

<span data-ttu-id="0608c-129">Às vezes, não é aparente quais informações são necessárias para o suporte da Microsoft investigar seu problema.</span><span class="sxs-lookup"><span data-stu-id="0608c-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="0608c-130">Nessa situação, você pode coletar todas as informações de diagnóstico para uma ocorrência de descoberta eletrônica principal.</span><span class="sxs-lookup"><span data-stu-id="0608c-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="0608c-131">O *nome da caixa de descoberta eletrônica principal* no seguinte comando é o mesmo que o nome de um caso exibido na página de **descoberta eletrônica principal** no centro de conformidade da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0608c-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="0608c-132">Coletar informações de diagnóstico para descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="0608c-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="0608c-133">A guia **configurações** em uma ocorrência de descoberta eletrônica avançada permite que você copie rapidamente as informações de diagnóstico para o caso.</span><span class="sxs-lookup"><span data-stu-id="0608c-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="0608c-134">As informações de diagnóstico são salvas na área de transferência para que você possa colá-las em um arquivo de texto e enviar para o suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0608c-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="0608c-135">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em **Mostrar todos os > de descoberta eletrônica > avançado**.</span><span class="sxs-lookup"><span data-stu-id="0608c-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="0608c-136">Selecione uma ocorrência e, em seguida, clique na guia **configurações** .</span><span class="sxs-lookup"><span data-stu-id="0608c-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="0608c-137">Em **informações do caso** , clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="0608c-137">Under **Case Information** , click **Select**.</span></span>

4. <span data-ttu-id="0608c-138">Na página do menu suspenso, clique em **copiar informações de diagnóstico** para copiar as informações para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="0608c-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="0608c-139">Abra um arquivo de texto (no bloco de notas) e cole as informações no arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="0608c-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="0608c-140">Salve o arquivo de texto e nomeie-o como `AeD Diagnostic Info YYYY.MM.DD` (por exemplo, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="0608c-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="0608c-141">Após revisar o arquivo e redigir informações confidenciais, envie-o ao engenheiro de suporte da Microsoft que está trabalhando no seu caso.</span><span class="sxs-lookup"><span data-stu-id="0608c-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>
