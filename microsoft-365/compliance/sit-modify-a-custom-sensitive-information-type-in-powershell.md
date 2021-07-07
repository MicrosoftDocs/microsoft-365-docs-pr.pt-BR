---
title: Modificar um tipo personalizado de informações confidenciais usando o PowerShell
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como modificar informações confidenciais personalizadas usando o PowerShell.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322435"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="1ac33-103">Modificar um tipo personalizado de informações confidenciais usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ac33-103">Modify a custom sensitive information type using PowerShell</span></span>

<span data-ttu-id="1ac33-104">No Centro de Conformidade Windows PowerShell, a modificação de um tipo de informação confidencial personalizada requer que você:</span><span class="sxs-lookup"><span data-stu-id="1ac33-104">In Compliance center PowerShell, modifying a custom sensitive information type requires you to:</span></span>

1. <span data-ttu-id="1ac33-105">Exporte um pacote de regras existente que contém o tipo personalizado de informação confidencial para um arquivo XML (ou use o arquivo XML existente, se você o tiver).</span><span class="sxs-lookup"><span data-stu-id="1ac33-105">Export the existing rule package that contains the custom sensitive information type to an XML file (or use the existing XML file if you have it).</span></span>

2. <span data-ttu-id="1ac33-106">Modifique um tipo personalizado de informação confidencial no arquivo XML exportado.</span><span class="sxs-lookup"><span data-stu-id="1ac33-106">Modify the custom sensitive information type in the exported XML file.</span></span>

3. <span data-ttu-id="1ac33-107">Importe o arquivo XML atualizado de volta para o pacote de regras existente.</span><span class="sxs-lookup"><span data-stu-id="1ac33-107">Import the updated XML file back into the existing rule package.</span></span>

<span data-ttu-id="1ac33-108">Para se conectar ao Compliance Center Windows PowerShell, consulte [Conectar ao Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1ac33-108">To connect to Compliance Center PowerShell, see [Connect to Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).</span></span>

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a><span data-ttu-id="1ac33-109">Etapa 1: Exportar o pacote de regras existente para um arquivo XML</span><span class="sxs-lookup"><span data-stu-id="1ac33-109">Step 1: Export the existing rule package to an XML file</span></span>

> [!NOTE]
> <span data-ttu-id="1ac33-110">Se você tiver uma cópia do arquivo XML (por exemplo, você acabou de criá-lo e importá-lo), poderá pular para a próxima etapa para modificar o arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="1ac33-110">If you have a copy of the XML file (for example, you just created and imported it), you can skip to the next step to modify the XML file.</span></span>

1. <span data-ttu-id="1ac33-111">Se você ainda não sabe, execute o cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) para encontrar o nome do pacote de regras personalizado:</span><span class="sxs-lookup"><span data-stu-id="1ac33-111">If you don't already know it, run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to find the name of the custom rule package:</span></span>

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > <span data-ttu-id="1ac33-p101">O pacote de regras interno que contém os tipos de informações confidenciais internos é denominado Pacote de Regras da Microsoft. O pacote de regras que contém os tipos de informações confidenciais personalizados que você criou na IU do Centro de conformidade é denominado Microsoft.SCCManaged.CustomRulePack.</span><span class="sxs-lookup"><span data-stu-id="1ac33-p101">The built-in rule package that contains the built-in sensitive information types is named Microsoft Rule Package. The rule package that contains the custom sensitive information types that you created in the Compliance center UI is named Microsoft.SCCManaged.CustomRulePack.</span></span>

2. <span data-ttu-id="1ac33-114">Use o cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) para armazenar o pacote de regras personalizadas em uma variável:</span><span class="sxs-lookup"><span data-stu-id="1ac33-114">Use the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet to store the custom rule package to a variable:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   <span data-ttu-id="1ac33-115">Por exemplo, se o nome do pacote de regras for "Pacote de regras personalizadas do ID do funcionário", execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1ac33-115">For example, if the name of the rule package is "Employee ID Custom Rule Pack", run the following cmdlet:</span></span>

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. <span data-ttu-id="1ac33-116">Use o cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) para exportar o pacote de regras personalizadas para um arquivo XML:</span><span class="sxs-lookup"><span data-stu-id="1ac33-116">Use the [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet to export the custom rule package to an XML file:</span></span>

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   <span data-ttu-id="1ac33-117">Este exemplo exporta o pacote de regras para o arquivo chamado ExportedRulePackage.xml na pasta C:\Meus documentos.</span><span class="sxs-lookup"><span data-stu-id="1ac33-117">This example export the rule package to the file named ExportedRulePackage.xml in the C:\My Documents folder.</span></span>

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a><span data-ttu-id="1ac33-118">Etapa 2: Modificar um tipo personalizado de informação confidencial no arquivo XML exportado</span><span class="sxs-lookup"><span data-stu-id="1ac33-118">Step 2: Modify the sensitive information type in the exported XML file</span></span>

<span data-ttu-id="1ac33-119">Os tipos de informação confidencial no arquivo XML e outros elementos no arquivo são descritos anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="1ac33-119">Sensitive information types in the XML file and other elements in the file are described earlier in this topic.</span></span>

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a><span data-ttu-id="1ac33-120">Etapa 3: Importar o arquivo XML atualizado de volta para o pacote de regras existente</span><span class="sxs-lookup"><span data-stu-id="1ac33-120">Step 3: Import the updated XML file back into the existing rule package</span></span>

<span data-ttu-id="1ac33-121">Para importar o XML atualizado de volta para o pacote de regras existente, use o cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="1ac33-121">To import the updated XML back into the existing rule package, use the [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

<span data-ttu-id="1ac33-122">Para informações detalhadas sobre sintaxe e parâmetros, confira [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="1ac33-122">For detailed syntax and parameter information, see [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).</span></span>


## <a name="more-information"></a><span data-ttu-id="1ac33-123">Mais informações</span><span class="sxs-lookup"><span data-stu-id="1ac33-123">More information</span></span>

- [<span data-ttu-id="1ac33-124">Saiba mais sobre a prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="1ac33-124">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="1ac33-125">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="1ac33-125">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="1ac33-126">O que as funções DLP procuram</span><span class="sxs-lookup"><span data-stu-id="1ac33-126">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
