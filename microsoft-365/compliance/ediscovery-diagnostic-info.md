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
description: Saiba mais sobre como coletar informações de diagnóstico de Descoberta e Para um caso de Suporte da Microsoft.
ms.openlocfilehash: 842f8baf770f178df3298bbfa911de26ce946ed0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926551"
---
# <a name="collect-ediscovery-diagnostic-information"></a><span data-ttu-id="a7d94-103">Coletar informações de diagnóstico de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="a7d94-103">Collect eDiscovery diagnostic information</span></span>

<span data-ttu-id="a7d94-104">Ocasionalmente, os engenheiros de Suporte da Microsoft exigem informações específicas sobre seu problema quando você abre um caso de suporte relacionado à Descoberta Básica de Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a7d94-104">Occasionally Microsoft Support engineers require specific information about your issue when you open a support case related to Core eDiscovery or Advanced eDiscovery.</span></span> <span data-ttu-id="a7d94-105">Este artigo fornece orientações sobre como coletar informações de diagnóstico para ajudar os engenheiros a investigar e resolver problemas.</span><span class="sxs-lookup"><span data-stu-id="a7d94-105">This article provides guidance on how to collect diagnostic information to help support engineers investigate and resolve issues.</span></span> <span data-ttu-id="a7d94-106">Normalmente, você não precisa coletar essas informações até ser solicitado por um engenheiro de Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7d94-106">Typically, you don't need to collect this information until asked to do so by a Microsoft Support engineer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a7d94-107">A saída dos cmdlets e informações de diagnóstico descritas neste artigo pode incluir informações confidenciais sobre litígio ou investigações internas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a7d94-107">The output from the cmdlets and diagnostic information described in this article may include sensitive information about litigation or internal investigations in your organization.</span></span> <span data-ttu-id="a7d94-108">Antes de enviar as informações de diagnóstico brutas para o Suporte da Microsoft, você deve revisar as informações e rediscar quaisquer informações confidenciais (como nomes ou outras informações sobre partes para litígio ou investigação) substituindo-as por `XXXXXXX` .</span><span class="sxs-lookup"><span data-stu-id="a7d94-108">Before sending the raw diagnostic information to Microsoft Support, you should review the information and redact any sensitive information (such as names or other information about parties to litigation or investigation) by replacing it with `XXXXXXX`.</span></span> <span data-ttu-id="a7d94-109">O uso desse método também indicará ao engenheiro de Suporte da Microsoft que as informações foram redacted.</span><span class="sxs-lookup"><span data-stu-id="a7d94-109">Using this method will also indicate to the Microsoft Support engineer that information was redacted.</span></span>

## <a name="collect-diagnostic-information-for-core-ediscovery"></a><span data-ttu-id="a7d94-110">Coletar informações de diagnóstico para a Descoberta Principal</span><span class="sxs-lookup"><span data-stu-id="a7d94-110">Collect diagnostic information for Core eDiscovery</span></span>

<span data-ttu-id="a7d94-111">A coleta de informações de diagnóstico para a Descoberta Eletrônica Principal é baseada em cmdlet, portanto, você terá que usar o Centro de Conformidade e Segurança & PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a7d94-111">Collecting diagnostic information for Core eDiscovery is cmdlet-based, so you'll have to use Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="a7d94-112">Os exemplos a seguir do PowerShell executarão cmdlets e salvarão a saída em um arquivo de texto especificado.</span><span class="sxs-lookup"><span data-stu-id="a7d94-112">The following PowerShell examples will run cmdlets and then save the output to a specified text file.</span></span> <span data-ttu-id="a7d94-113">Na maioria dos casos de suporte, você deve executar apenas um desses comandos.</span><span class="sxs-lookup"><span data-stu-id="a7d94-113">In most support cases, you should only have to run one of these commands.</span></span>

<span data-ttu-id="a7d94-114">Para executar os cmdlets a seguir, conecte-se ao Centro de [Conformidade e Segurança & PowerShell </span> ](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="a7d94-114">To run the following cmdlets, [connect to Security & Compliance Center PowerShell</span>](/powershell/exchange/connect-to-scc-powershell).</span></span> <span data-ttu-id="a7d94-115">Depois de conectado, execute um ou mais dos seguintes comandos e substitua os espaço reservados por nomes de objeto reais.</span><span class="sxs-lookup"><span data-stu-id="a7d94-115">After you're connected, run one or more of the following commands and be sure to replace placeholders with the actual object names.</span></span>

<span data-ttu-id="a7d94-116">Depois de revisar o arquivo de texto gerado e redactar informações confidenciais, envie-o para o engenheiro de Suporte da Microsoft que está trabalhando em seu caso.</span><span class="sxs-lookup"><span data-stu-id="a7d94-116">After reviewing the generated text file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>

> [!NOTE]
> <span data-ttu-id="a7d94-117">Você também pode executar os comandos nesta seção para coletar informações de  diagnóstico para as pesquisas e exportações listadas na página de pesquisa de conteúdo no centro de conformidade Microsoft 365 de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a7d94-117">You can also run the commands in this section to collect diagnostic information for the searches and exports listed on the **Content search** page in the Microsoft 365 compliance center.</span></span>

### <a name="collect-information-about-searches"></a><span data-ttu-id="a7d94-118">Coletar informações sobre pesquisas</span><span class="sxs-lookup"><span data-stu-id="a7d94-118">Collect information about searches</span></span>

<span data-ttu-id="a7d94-119">O comando a seguir coleta informações que são úteis ao investigar problemas com uma pesquisa de conteúdo ou uma pesquisa associada a um caso core de Descoberta e Descoberta.</span><span class="sxs-lookup"><span data-stu-id="a7d94-119">The following command collects information that's helpful when investigating issues with a Content search or a search associated with a Core eDiscovery case.</span></span>

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a><span data-ttu-id="a7d94-120">Coletar informações sobre ações de pesquisa</span><span class="sxs-lookup"><span data-stu-id="a7d94-120">Collect information about search actions</span></span>

<span data-ttu-id="a7d94-121">O comando a seguir coleta informações para investigar problemas de visualização, exportação ou purgação dos resultados de uma pesquisa de Conteúdo ou de uma pesquisa associada a um caso de Descoberta Principal de Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="a7d94-121">The following command collects information to investigate problems with previewing, exporting, or purging the results of a Content search or a search associated with a Core eDiscovery case.</span></span> <span data-ttu-id="a7d94-122">Você pode identificar o nome da ação de pesquisa clicando em uma exportação listada na **guia Exportações.** Para identificar os nomes das ações de visualização e limpeza, você pode executar o cmdlet **Get-ComplianceSearchAction** para exibir uma lista de todas as ações.</span><span class="sxs-lookup"><span data-stu-id="a7d94-122">You can identify the name of the search action by clicking an export that's listed on the **Exports** tab. To identify the names of preview and purge actions, you can run the **Get-ComplianceSearchAction** cmdlet to display a list of all actions.</span></span> <span data-ttu-id="a7d94-123">O formato do nome da ação de pesquisa é construído por appending , ou pelo `_Preview` nome da pesquisa `_Export` `_Purge` correspondente.</span><span class="sxs-lookup"><span data-stu-id="a7d94-123">The format for the search action name is constructed by appending `_Preview`, `_Export`, or `_Purge` to the name of the corresponding search.</span></span>

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a><span data-ttu-id="a7d94-124">Coletar informações sobre os ressamentos de Descoberta e</span><span class="sxs-lookup"><span data-stu-id="a7d94-124">Collect information about eDiscovery holds</span></span>

<span data-ttu-id="a7d94-125">Quando uma responsabilidade de Descoberta Externa associada a um caso de Descoberta Externa Principal não estiver funcionando conforme o esperado, execute o seguinte comando para coletar informações sobre a Política de Recolhimento de Caso e a Regra de Recolhimento de Caso associada para a recolhimento de Descoberta e Descoberta.</span><span class="sxs-lookup"><span data-stu-id="a7d94-125">When an eDiscovery hold associated with a Core eDiscovery case isn't functioning as expected, run the following command to collect information about the Case Hold Policy and associated Case Hold Rule for the eDiscovery hold.</span></span> <span data-ttu-id="a7d94-126">O *nome da política de espera de* caso no comando a seguir é o mesmo que o nome da ressução de Descoberta e.</span><span class="sxs-lookup"><span data-stu-id="a7d94-126">The *Case hold policy name* in the following command is the same as the name of the eDiscovery hold.</span></span> <span data-ttu-id="a7d94-127">Você pode identificar esse nome nas guias **Retém** no caso descoberta principal.</span><span class="sxs-lookup"><span data-stu-id="a7d94-127">You can identify this name on the **Holds** tabs in the Core eDiscovery case.</span></span>

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a><span data-ttu-id="a7d94-128">Coletar todas as informações de caso</span><span class="sxs-lookup"><span data-stu-id="a7d94-128">Collect all case information</span></span>

<span data-ttu-id="a7d94-129">Às vezes, não é evidente quais informações são necessárias para o Suporte da Microsoft investigar seu problema.</span><span class="sxs-lookup"><span data-stu-id="a7d94-129">Sometimes, it's not apparent what information is required by Microsoft Support to investigate your issue.</span></span> <span data-ttu-id="a7d94-130">Nessa situação, você pode coletar todas as informações de diagnóstico para um caso core de Descoberta eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="a7d94-130">In this situation, you can collect all of the diagnostics information for a Core eDiscovery case.</span></span> <span data-ttu-id="a7d94-131">O nome da ocorrência de Descoberta *eDiscovery* Principal no comando a seguir é o mesmo que o nome de uma ocorrência exibida na página Descoberta Principal da **Descoberta** e No centro de conformidade Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a7d94-131">The *Core eDiscovery case name* in the following command is the same as the name of a case that's displayed on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span>

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a><span data-ttu-id="a7d94-132">Coletar informações de diagnóstico para Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="a7d94-132">Collect diagnostic information for Advanced eDiscovery</span></span>

<span data-ttu-id="a7d94-133">A **Configurações** guia em um caso Advanced eDiscovery permite copiar rapidamente as informações de diagnóstico para o caso.</span><span class="sxs-lookup"><span data-stu-id="a7d94-133">The **Settings** tab in an Advanced eDiscovery case lets you quickly copy the diagnostic information for the case.</span></span> <span data-ttu-id="a7d94-134">As informações de diagnóstico são salvas na área de transferência para que você possa colar em um arquivo de texto e enviar para o Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a7d94-134">The diagnostic information is saved to the clipboard so you can paste it to a text file and send to Microsoft Support.</span></span>

1. <span data-ttu-id="a7d94-135">Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com/) e clique em Mostrar todas as > Descoberta > **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="a7d94-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Show all > eDiscovery > Advanced**.</span></span>

2. <span data-ttu-id="a7d94-136">Selecione um caso e clique na guia **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="a7d94-136">Select a case and then click the **Settings** tab.</span></span>

3. <span data-ttu-id="a7d94-137">Em **Informações de Caso,** clique **em Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="a7d94-137">Under **Case Information**, click **Select**.</span></span>

4. <span data-ttu-id="a7d94-138">Na página de sobrevoo, clique em Copiar informações **de diagnóstico** para copiar as informações para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="a7d94-138">On the flyout page, click **Copy diagnostic information** to copy the info to the clipboard.</span></span>

5. <span data-ttu-id="a7d94-139">Abra um arquivo de texto (em Bloco de notas) e, em seguida, colar as informações no arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a7d94-139">Open a text file (in Notepad) and then paste the information in the text file.</span></span>

6. <span data-ttu-id="a7d94-140">Salve o arquivo de texto e nomee-o como algo parecido `AeD Diagnostic Info YYYY.MM.DD` (por exemplo, `AeD Diagnostic Info 2020.11.03` ).</span><span class="sxs-lookup"><span data-stu-id="a7d94-140">Save the text file and name it something like `AeD Diagnostic Info YYYY.MM.DD` (for example, `AeD Diagnostic Info 2020.11.03`).</span></span>

<span data-ttu-id="a7d94-141">Depois de revisar o arquivo e redactar informações confidenciais, envie-o para o engenheiro de Suporte da Microsoft que está trabalhando em seu caso.</span><span class="sxs-lookup"><span data-stu-id="a7d94-141">After reviewing the file and redacting sensitive information, send it to the Microsoft Support engineer working on your case.</span></span>