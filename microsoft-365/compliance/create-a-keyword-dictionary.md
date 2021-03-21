---
title: Criar um dicionário de palavras-chave
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Aprenda as etapas básicas para criar um dicionário de palavras-chave no Centro de Segurança e Conformidade do Office 365.
ms.openlocfilehash: ff96eda71857b4b0f802462da96e4f4abbaf05f4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908385"
---
# <a name="create-a-keyword-dictionary"></a><span data-ttu-id="82209-103">Criar um dicionário de palavras-chave</span><span class="sxs-lookup"><span data-stu-id="82209-103">Create a keyword dictionary</span></span>

<span data-ttu-id="82209-104">A DLP (prevenção contra perda de dados) pode identificar, monitorar e proteger seus itens confidenciais.</span><span class="sxs-lookup"><span data-stu-id="82209-104">Data loss prevention (DLP) can identify, monitor, and protect your sensitive items.</span></span> <span data-ttu-id="82209-105">Às vezes, a identificação de itens confidenciais requer a procura de palavras-chave, principalmente ao identificar conteúdos genéricos (como comunicações relacionadas à assistência médica), ou linguagem inadequada ou explícita.</span><span class="sxs-lookup"><span data-stu-id="82209-105">Identifying sensitive items sometimes requires looking for keywords, particularly when identifying generic content (such as healthcare-related communication), or inappropriate or explicit language.</span></span> <span data-ttu-id="82209-106">Embora seja possível criar listas de palavras-chave em tipos de informações confidenciais, as listas de palavras-chave têm tamanho limitado e exigem a modificação do XML para criá-las ou editá-las.</span><span class="sxs-lookup"><span data-stu-id="82209-106">Although you can create keyword lists in sensitive information types, keyword lists are limited in size and require modifying XML to create or edit them.</span></span> <span data-ttu-id="82209-107">Os dicionários de palavras-chave fornecem gerenciamento mais simples de palavras-chave e em uma escala muito maior, suportando até 1 MB de termos (pós-compressão) no dicionário e suportam qualquer idioma.</span><span class="sxs-lookup"><span data-stu-id="82209-107">Keyword dictionaries provide simpler management of keywords and at a much larger scale, supporting up to 1MB of terms (post compression) in the dictionary and support any language.</span></span> <span data-ttu-id="82209-108">O limite do locatário também é 1 MB após a compactação.</span><span class="sxs-lookup"><span data-stu-id="82209-108">The tenant limit is also 1MB after compression.</span></span> <span data-ttu-id="82209-109">1 MB de limite de pós-compactação significa que todos os dicionários combinados em um locatário podem ter cerca de 1 milhão de caracteres.</span><span class="sxs-lookup"><span data-stu-id="82209-109">1MB of post compression limit means that all dictionaries combined across a tenant can have close to 1 million character.</span></span>
  
> [!NOTE]
> <span data-ttu-id="82209-110">Há um limite de 50 tipos de informações confidenciais baseadas em dicionário de palavras-chave que podem ser criados por locatário.</span><span class="sxs-lookup"><span data-stu-id="82209-110">There is a limit of 50 keyword dictionary based sensitive information types that can be created per tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="82209-111">A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:</span><span class="sxs-lookup"><span data-stu-id="82209-111">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="82209-112">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="82209-112">Chinese (simplified)</span></span>
> - <span data-ttu-id="82209-113">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="82209-113">Chinese (traditional)</span></span>
> - <span data-ttu-id="82209-114">Coreano</span><span class="sxs-lookup"><span data-stu-id="82209-114">Korean</span></span>
> - <span data-ttu-id="82209-115">Japonês</span><span class="sxs-lookup"><span data-stu-id="82209-115">Japanese</span></span>
>
><span data-ttu-id="82209-116">Este suporte está disponível para tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="82209-116">This support is available for sensitive information types.</span></span> <span data-ttu-id="82209-117">Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="82209-117">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="basic-steps-to-creating-a-keyword-dictionary"></a><span data-ttu-id="82209-118">Etapas básicas para criar um dicionário de palavra-chave</span><span class="sxs-lookup"><span data-stu-id="82209-118">Basic steps to creating a keyword dictionary</span></span>

<span data-ttu-id="82209-p103">As palavras-chave para o seu dicionário podem vir de uma variedade de fontes, mais comumente de um arquivo (como uma lista .csv ou .txt), importada no serviço ou pelo cmdlet do PowerShell de uma lista que você insere diretamente no cmdlet do PowerShell ou de um dicionário existente. Quando você cria um dicionário de palavras-chave, siga as mesmas etapas principais:</span><span class="sxs-lookup"><span data-stu-id="82209-p103">The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:</span></span>
  
1. <span data-ttu-id="82209-121">Use o **Centro de Conformidade e Segurança** ([https://protection.office.com](https://protection.office.com)) ou conecte-se ao **Centro &amp; de Conformidade e Segurança do PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="82209-121">Use the **Security & Compliance Center** ([https://protection.office.com](https://protection.office.com)) or connect to  **Security &amp; Compliance Center PowerShell**.</span></span>
    
2. <span data-ttu-id="82209-122">**Defina ou carregue suas palavras-chave da fonte pretendida**.</span><span class="sxs-lookup"><span data-stu-id="82209-122">**Define or load your keywords from your intended source**.</span></span> <span data-ttu-id="82209-123">O assistente e o cmdlet aceitam uma lista separada por vírgulas de palavras-chave para criar um dicionário de palavras-chave personalizado, de modo que esta etapa irá variar um pouco dependendo da origem das palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="82209-123">The wizard and the cmdlet both accept a comma-separated list of keywords to create a custom keyword dictionary, so this step will vary slightly depending on where your keywords come from.</span></span> <span data-ttu-id="82209-124">Uma vez carregadas, elas são codificadas e convertidas em uma matriz bytes antes de serem importadas.</span><span class="sxs-lookup"><span data-stu-id="82209-124">Once loaded, they're encoded and converted to a byte array before they're imported.</span></span>
    
3. <span data-ttu-id="82209-125">**Crie seu dicionário**.</span><span class="sxs-lookup"><span data-stu-id="82209-125">**Create your dictionary**.</span></span> <span data-ttu-id="82209-126">Escolha um nome e uma descrição, e crie seu dicionário.</span><span class="sxs-lookup"><span data-stu-id="82209-126">Choose a name and description and create your dictionary.</span></span>

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a><span data-ttu-id="82209-127">Criar um dicionário de palavras-chave usando o Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="82209-127">Create a keyword dictionary using the Security & Compliance Center</span></span>

<span data-ttu-id="82209-128">Use as etapas a seguir para criar e importar palavras-chave para um dicionário personalizado:</span><span class="sxs-lookup"><span data-stu-id="82209-128">Use the following steps to create and import keywords for a custom dictionary:</span></span>

1. <span data-ttu-id="82209-129">Conectar-se ao Centro de Conformidade e Segurança ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="82209-129">Connect to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span>

2. <span data-ttu-id="82209-130">Navegue até **Classificações > Tipos de informações confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="82209-130">Navigate to **Classifications > Sensitive info types**.</span></span>

3. <span data-ttu-id="82209-131">Selecione **Criar** e insira **Nome** e **Descrição** para o tipo de informações confidenciais, em seguida, selecione **Avançar**</span><span class="sxs-lookup"><span data-stu-id="82209-131">Select **Create** and enter a **Name** and **Description** for your sensitive info type, then select **Next**</span></span>

4. <span data-ttu-id="82209-132">Selecione **Adicionar um elemento** e selecione **Dicionário (Palavras-chave grandes)** na lista suspensa **Detectar conteúdo que tenha**.</span><span class="sxs-lookup"><span data-stu-id="82209-132">Select **Add an element**, then select **Dictionary (Large keywords)** in the **Detect content containing** drop-down list.</span></span>

5. <span data-ttu-id="82209-133">Selecione **Adicionar um dicionário**</span><span class="sxs-lookup"><span data-stu-id="82209-133">Select **Add a dictionary**</span></span>

6. <span data-ttu-id="82209-134">Sob o controle da pesquisa, selecione **Você pode criar novos dicionários de palavras-chave**.</span><span class="sxs-lookup"><span data-stu-id="82209-134">Under the Search control, select **You can create new keyword dictionaries here**.</span></span>

7. <span data-ttu-id="82209-135">Insira um **Nome** para o dicionário personalizado.</span><span class="sxs-lookup"><span data-stu-id="82209-135">Enter a **Name** for your custom dictionary.</span></span>

8. <span data-ttu-id="82209-136">Selecione **Importação** e selecione **a partir do texto** ou **a partir do csv** dependendo do tipo de arquivo de palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="82209-136">Select **Import**, and select either **From text** or **From csv** depending on your keyword file type.</span></span>

9. <span data-ttu-id="82209-137">Na caixa de diálogo arquivo, selecione o arquivo de palavra-chave no compartilhamento de arquivos do computador ou rede local e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="82209-137">In the file dialog, select the keyword file from your local PC or network file share, then select **Open**.</span></span>

10. <span data-ttu-id="82209-138">Selecione **Salvar**, em seguida selecione o dicionário personalizado da lista **Dicionários de palavras-chave**.</span><span class="sxs-lookup"><span data-stu-id="82209-138">Select **Save**, then select your custom dictionary from the **Keyword dictionaries** list.</span></span>

11. <span data-ttu-id="82209-139">Selecione **Próximo**, e em seguida **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="82209-139">Select **Add**, then select **Next**.</span></span>

12. <span data-ttu-id="82209-140">Revise e finalize as seleções de tipo de informações confidenciais e selecione **Terminar**.</span><span class="sxs-lookup"><span data-stu-id="82209-140">Review and finalize your sensitive info type selections, then select **Finish**.</span></span>
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a><span data-ttu-id="82209-141">Criar um dicionário de palavras-chave de um arquivo usando o Power Shell</span><span class="sxs-lookup"><span data-stu-id="82209-141">Create a keyword dictionary from a file using PowerShell</span></span>

<span data-ttu-id="82209-142">Frequentemente, quando você precisa criar um dicionário grande, é para usar palavras-chave de um arquivo ou lista exportada de alguma outra fonte.</span><span class="sxs-lookup"><span data-stu-id="82209-142">Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source.</span></span> <span data-ttu-id="82209-143">Nesse caso, você criará um dicionário de palavras-chave contendo uma lista de linguagem imprópria para exibir em email externo.</span><span class="sxs-lookup"><span data-stu-id="82209-143">In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email.</span></span> <span data-ttu-id="82209-144">Primeiro você deve [conectar-se ao Centro &amp; de Conformidade e Segurança do PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="82209-144">You must first [connect to Security &amp; Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
  
1. <span data-ttu-id="82209-145">Copie as palavras-chave para um arquivo de texto e verifique se cada palavra-chave está em uma linha separada.</span><span class="sxs-lookup"><span data-stu-id="82209-145">Copy the keywords into a text file and make sure that each keyword is on a separate line.</span></span>
    
2. <span data-ttu-id="82209-p107">Salve o arquivo de texto com codificação Unicode. No Bloco de Notas \> **Salvar como** \> **Codificação** \> **Unicode**.</span><span class="sxs-lookup"><span data-stu-id="82209-p107">Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.</span></span>
    
3. <span data-ttu-id="82209-148">Leia o arquivo em uma variável executando este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="82209-148">Read the file into a variable by running this cmdlet:</span></span>
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. <span data-ttu-id="82209-149">Crie o dicionário executando este cmdlet:</span><span class="sxs-lookup"><span data-stu-id="82209-149">Create the dictionary by running this cmdlet:</span></span>
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a><span data-ttu-id="82209-150">Como modificar um dicionário de palavra-chave existente</span><span class="sxs-lookup"><span data-stu-id="82209-150">Modifying an existing keyword dictionary</span></span>

<span data-ttu-id="82209-151">Talvez seja necessário modificar palavras-chave em um de seus dicionários de palavras-chave ou modificar um dos dicionários internos.</span><span class="sxs-lookup"><span data-stu-id="82209-151">You might need to modify keywords in one of your keyword dictionaries, or modify one of the built-in dictionaries.</span></span> <span data-ttu-id="82209-152">Atualmente, você pode atualizar somente um dicionário personalizado de palavras-chave usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82209-152">Currently, your can only update a custom keyword dictionary using PowerShell.</span></span> 

<span data-ttu-id="82209-153">Por exemplo, modificaremos alguns termos no PowerShell, salvaremos os termos em um local onde você poderá modificá-los em um editor e atualizaremos os termos anteriores no local.</span><span class="sxs-lookup"><span data-stu-id="82209-153">For example, we'll modify some terms in PowerShell, save the terms locally where you can modify them in an editor, and then update the previous terms in place.</span></span> 

<span data-ttu-id="82209-154">Primeiro, recupere o objeto de dicionário:</span><span class="sxs-lookup"><span data-stu-id="82209-154">First, retrieve the dictionary object:</span></span>
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="82209-155">A impressão do `$dict` exibirá as diversas variáveis.</span><span class="sxs-lookup"><span data-stu-id="82209-155">Printing  `$dict` will show the various variables.</span></span> <span data-ttu-id="82209-156">As palavras-chave são armazenadas em um objeto no back-end, mas o `$dict.KeywordDictionary` contém uma representação de cadeia de caracteres delas, que você usará para modificar o dicionário.</span><span class="sxs-lookup"><span data-stu-id="82209-156">The keywords themselves are stored in an object on the backend, but  `$dict.KeywordDictionary` contains a string representation of them, which you'll use to modify the dictionary.</span></span> 

<span data-ttu-id="82209-157">Antes de modificar o dicionário, você precisa transformar a cadeia de caracteres de termos novamente em uma matriz usando o método `.split(',')`.</span><span class="sxs-lookup"><span data-stu-id="82209-157">Before you modify the dictionary, you need to turn the string of terms back into an array using the  `.split(',')` method.</span></span> <span data-ttu-id="82209-158">Em seguida, você limpará os espaços indesejados entre as palavras-chave com o método `.trim()`, deixando apenas as palavras-chave com as quais trabalhar.</span><span class="sxs-lookup"><span data-stu-id="82209-158">Then you'll clean up the unwanted spaces between the keywords with the  `.trim()` method, leaving just the keywords to work with.</span></span> 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

<span data-ttu-id="82209-p111">Agora, você removerá alguns termos do dicionário. Como o dicionário de exemplo tem apenas alguns as palavras-chave, você poderá ignorar facilmente para exportar o dicionário e editá-lo no Bloco de Notas, mas os dicionários geralmente contêm uma grande quantidade de texto, então você vai aprender primeiro assim para editá-los facilmente no PowerShell.</span><span class="sxs-lookup"><span data-stu-id="82209-p111">Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.</span></span>
  
<span data-ttu-id="82209-p112">Na última etapa, você salvou as palavras-chave em uma matriz. Há várias maneiras de [remover itens de uma matriz](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), mas como uma abordagem simples, você criará uma matriz de termos que deseja remover do dicionário e, em seguida, copia apenas os termos de dicionário para que ele não esteja na lista de termos para remover.</span><span class="sxs-lookup"><span data-stu-id="82209-p112">In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.</span></span>
  
<span data-ttu-id="82209-p113">Execute o comando `$terms` para mostrar a lista atual de termos. A saída do comando tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="82209-p113">Run the command  `$terms` to show the current list of terms. The output of the command looks like this:</span></span> 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

<span data-ttu-id="82209-165">Execute este comando para especificar os termos que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="82209-165">Run this command to specify the terms that you want to remove:</span></span>
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

<span data-ttu-id="82209-166">Execute este comando para remover os termos realmente da lista:</span><span class="sxs-lookup"><span data-stu-id="82209-166">Run this command to actually remove the terms from the list:</span></span>
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

<span data-ttu-id="82209-p114">Execute o comando `$updatedTerms` para mostrar a lista atualizada de termos. A saída do comando tem esta aparência (os termos especificados foram removidos):</span><span class="sxs-lookup"><span data-stu-id="82209-p114">Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed):</span></span> 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

<span data-ttu-id="82209-p115">Agora basta abrir o arquivo, adicionar os termos adicionais e salvar a codificação Unicode (UTF-16). Agora você carregará os termos atualizados e atualizará o dicionário no local.</span><span class="sxs-lookup"><span data-stu-id="82209-p115">Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.</span></span>
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

<span data-ttu-id="82209-p116">Agora, o dicionário foi atualizado no local. Observe que o campo `Identity` leva o nome do dicionário. Se você também quiser alterar o nome do dicionário usando o cmdlet `set-`, basta adicionar o parâmetro `-Name` para o que está acima com o novo nome do dicionário.</span><span class="sxs-lookup"><span data-stu-id="82209-p116">Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name.</span></span> 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a><span data-ttu-id="82209-174">Usar dicionários de palavras-chave em tipos de informação confidencial personalizados e as políticas DLP</span><span class="sxs-lookup"><span data-stu-id="82209-174">Using keyword dictionaries in custom sensitive information types and DLP policies</span></span>

<span data-ttu-id="82209-175">Os dicionários de palavras-chave podem ser usados como parte dos requisitos de correspondência para um tipo de informação confidencial personalizado ou como um tipo de informação confidencial próprio.</span><span class="sxs-lookup"><span data-stu-id="82209-175">Keyword dictionaries can be used as part of the match requirements for a custom sensitive information type, or as a sensitive information type themselves.</span></span> <span data-ttu-id="82209-176">Ambos exigem que você crie um [tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="82209-176">Both require you to create a [custom sensitive information type](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span> <span data-ttu-id="82209-177">Siga as instruções no artigo vinculado para criar um tipo de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="82209-177">Follow the instructions in the linked article to create a sensitive information type.</span></span> <span data-ttu-id="82209-178">Assim que tiver o XML, você precisará do identificador de GUID do dicionário para usá-lo.</span><span class="sxs-lookup"><span data-stu-id="82209-178">Once you have the XML, you'll need the GUID identifier for the dictionary to use it.</span></span>
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

<span data-ttu-id="82209-179">Para obter a identidade do seu dicionário, execute este comando e copie o valor da propriedade **Identity**:</span><span class="sxs-lookup"><span data-stu-id="82209-179">To get the identity of your dictionary, run this command and copy the **Identity** property value:</span></span> 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

<span data-ttu-id="82209-180">A saída do comando será parecida com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="82209-180">The output of the command looks like this:</span></span>
  
<span data-ttu-id="82209-181">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span><span class="sxs-lookup"><span data-stu-id="82209-181">`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`</span></span>
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


<span data-ttu-id="82209-p118">Cole a identidade no XML do seu tipo de informação confidencial personalizado e carregue-a. Agora seu dicionário aparecerá na sua lista de tipos de informação confidencial e você poderá usá-lo direto em sua política, especificando o número de palavras-chave necessário para corresponder.</span><span class="sxs-lookup"><span data-stu-id="82209-p118">Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.</span></span>
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```