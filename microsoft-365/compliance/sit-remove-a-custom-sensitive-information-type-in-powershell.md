---
title: Remover um tipo personalizado de informações confidenciais usando o PowerShell
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
description: Saiba como remover um tipo personalizado de informações confidenciais usando o PowerShell
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322434"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a><span data-ttu-id="d4821-103">Remover um tipo personalizado de informações confidenciais usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4821-103">Remove a custom sensitive information type using PowerShell</span></span>



<span data-ttu-id="d4821-104">No Centro de Conformidade Windows PowerShell, existem dois métodos para remover tipos de informações confidenciais personalizadas:</span><span class="sxs-lookup"><span data-stu-id="d4821-104">In Compliance center PowerShell, there are two methods to remove custom sensitive information types:</span></span>

- <span data-ttu-id="d4821-105">**Remover tipos de informações confidenciais personalizadas individuais**: Use o método documentado em Modificar um tipo de informação confidenciais personalizado [usando o PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="d4821-105">**Remove individual custom sensitive information types**: Use the method documented in [Modify a custom sensitive information type using PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell).</span></span> <span data-ttu-id="d4821-106">Você exporta o pacote de regras personalizado que contém o tipo de informação confidencial personalizado, remove o tipo de informação confidencial do arquivo XML e importa o arquivo XML atualizado de volta para o pacote de regras personalizadas existente.</span><span class="sxs-lookup"><span data-stu-id="d4821-106">You export the custom rule package that contains the custom sensitive information type, remove the sensitive information type from the XML file, and import the updated XML file back into the existing custom rule package.</span></span>

- <span data-ttu-id="d4821-107">**Remover todos os pacotes de regras personalizados e todos os tipos personalizados de informação confidencial que eles contêm**: este método está documentado nesta seção.</span><span class="sxs-lookup"><span data-stu-id="d4821-107">**Remove a custom rule package and all custom sensitive information types that it contains**: This method is documented in this section.</span></span>

> [!NOTE]
> <span data-ttu-id="d4821-108">Antes de remover um tipo personalizado de informação confidencial, verifique se nenhuma política de DLP ou regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) ainda fazem referência ao tipo de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="d4821-108">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. [<span data-ttu-id="d4821-109">Conecte-se ao centro de conformidade Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4821-109">Connect to Compliance center PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

2. <span data-ttu-id="d4821-110">Para remover um pacote de regras personalizado, use o cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):</span><span class="sxs-lookup"><span data-stu-id="d4821-110">To remove a custom rule package, use the [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet:</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   <span data-ttu-id="d4821-111">Você pode usar o valor de Name (para qualquer idioma) ou o `RulePack id` valor (GUID) para identificar o pacote de regras.</span><span class="sxs-lookup"><span data-stu-id="d4821-111">You can use the Name value (for any language) or the `RulePack id` (GUID) value to identify the rule package.</span></span>

   <span data-ttu-id="d4821-112">Este exemplo remove o pacote de regras chamado "Pacote de regras de personalizado de ID do funcionário".</span><span class="sxs-lookup"><span data-stu-id="d4821-112">This example removes the rule package named "Employee ID Custom Rule Pack".</span></span>

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   <span data-ttu-id="d4821-113">Para informações detalhadas sobre sintaxe e parâmetros, confira [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span><span class="sxs-lookup"><span data-stu-id="d4821-113">For detailed syntax and parameter information, see [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).</span></span>

3. <span data-ttu-id="d4821-114">Para confirmar se você removeu um novo tipo de informação confidencial com êxito, execute uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="d4821-114">To verify that you've successfully removed a custom sensitive information type, do any of the following steps:</span></span>

   - <span data-ttu-id="d4821-115">Execute o cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) e verifique se o pacote de regras não está mais listado:</span><span class="sxs-lookup"><span data-stu-id="d4821-115">Run the [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet and verify the rule package is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - <span data-ttu-id="d4821-116">Execute o cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para verificar se os tipos de informações confidenciais no pacote de regras removido não estão mais listados:</span><span class="sxs-lookup"><span data-stu-id="d4821-116">Run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information types in the removed rule package are no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     <span data-ttu-id="d4821-117">Para tipos personalizados de informação confidencial, o valor da propriedade Publisher será diferente do Microsoft Corporation.</span><span class="sxs-lookup"><span data-stu-id="d4821-117">For custom sensitive information types, the Publisher property value will be something other than Microsoft Corporation.</span></span>

   - <span data-ttu-id="d4821-118">Substitua \<Name\>com o valor Name do tipo de informação confidencial (por exemplo, ID do funcionário) e execute o cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para verificar se o tipo de informação confidencial não está mais listado:</span><span class="sxs-lookup"><span data-stu-id="d4821-118">Replace \<Name\> with the Name value of the sensitive information type (for example, Employee ID) and run the [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet to verify the sensitive information type is no longer listed:</span></span>

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a><span data-ttu-id="d4821-119">Mais informações</span><span class="sxs-lookup"><span data-stu-id="d4821-119">More information</span></span>

- [<span data-ttu-id="d4821-120">Saiba mais sobre a prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="d4821-120">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)

- [<span data-ttu-id="d4821-121">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="d4821-121">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)

- [<span data-ttu-id="d4821-122">O que as funções DLP procuram</span><span class="sxs-lookup"><span data-stu-id="d4821-122">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
