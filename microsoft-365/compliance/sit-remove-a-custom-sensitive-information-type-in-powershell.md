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
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>Remover um tipo personalizado de informações confidenciais usando o PowerShell



No Centro de Conformidade Windows PowerShell, existem dois métodos para remover tipos de informações confidenciais personalizadas:

- **Remover tipos de informações confidenciais personalizadas individuais**: Use o método documentado em Modificar um tipo de informação confidenciais personalizado [usando o PowerShell](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell). Você exporta o pacote de regras personalizado que contém o tipo de informação confidencial personalizado, remove o tipo de informação confidencial do arquivo XML e importa o arquivo XML atualizado de volta para o pacote de regras personalizadas existente.

- **Remover todos os pacotes de regras personalizados e todos os tipos personalizados de informação confidencial que eles contêm**: este método está documentado nesta seção.

> [!NOTE]
> Antes de remover um tipo personalizado de informação confidencial, verifique se nenhuma política de DLP ou regras de fluxo de emails do Exchange (também conhecidas como regras de transporte) ainda fazem referência ao tipo de informação confidencial.

1. [Conecte-se ao centro de conformidade Windows PowerShell](/powershell/exchange/exchange-online-powershell)

2. Para remover um pacote de regras personalizado, use o cmdlet [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage):

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   Você pode usar o valor de Name (para qualquer idioma) ou o `RulePack id` valor (GUID) para identificar o pacote de regras.

   Este exemplo remove o pacote de regras chamado "Pacote de regras de personalizado de ID do funcionário".

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   Para informações detalhadas sobre sintaxe e parâmetros, confira [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage).

3. Para confirmar se você removeu um novo tipo de informação confidencial com êxito, execute uma destas etapas:

   - Execute o cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) e verifique se o pacote de regras não está mais listado:

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - Execute o cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para verificar se os tipos de informações confidenciais no pacote de regras removido não estão mais listados:

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     Para tipos personalizados de informação confidencial, o valor da propriedade Publisher será diferente do Microsoft Corporation.

   - Substitua \<Name\>com o valor Name do tipo de informação confidencial (por exemplo, ID do funcionário) e execute o cmdlet [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) para verificar se o tipo de informação confidencial não está mais listado:

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>Mais informações

- [Saiba mais sobre a prevenção contra perda de dados](dlp-learn-about-dlp.md)

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)

- [O que as funções DLP procuram](what-the-dlp-functions-look-for.md)
