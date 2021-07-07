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
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>Modificar um tipo personalizado de informações confidenciais usando o PowerShell

No Centro de Conformidade Windows PowerShell, a modificação de um tipo de informação confidencial personalizada requer que você:

1. Exporte um pacote de regras existente que contém o tipo personalizado de informação confidencial para um arquivo XML (ou use o arquivo XML existente, se você o tiver).

2. Modifique um tipo personalizado de informação confidencial no arquivo XML exportado.

3. Importe o arquivo XML atualizado de volta para o pacote de regras existente.

Para se conectar ao Compliance Center Windows PowerShell, consulte [Conectar ao Compliance Center PowerShell](/powershell/exchange/exchange-online-powershell).

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>Etapa 1: Exportar o pacote de regras existente para um arquivo XML

> [!NOTE]
> Se você tiver uma cópia do arquivo XML (por exemplo, você acabou de criá-lo e importá-lo), poderá pular para a próxima etapa para modificar o arquivo XML.

1. Se você ainda não sabe, execute o cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) para encontrar o nome do pacote de regras personalizado:

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > O pacote de regras interno que contém os tipos de informações confidenciais internos é denominado Pacote de Regras da Microsoft. O pacote de regras que contém os tipos de informações confidenciais personalizados que você criou na IU do Centro de conformidade é denominado Microsoft.SCCManaged.CustomRulePack.

2. Use o cmdlet [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) para armazenar o pacote de regras personalizadas em uma variável:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   Por exemplo, se o nome do pacote de regras for "Pacote de regras personalizadas do ID do funcionário", execute o seguinte cmdlet:

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. Use o cmdlet [Set-Content](/powershell/module/microsoft.powershell.management/set-content) para exportar o pacote de regras personalizadas para um arquivo XML:

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   Este exemplo exporta o pacote de regras para o arquivo chamado ExportedRulePackage.xml na pasta C:\Meus documentos.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>Etapa 2: Modificar um tipo personalizado de informação confidencial no arquivo XML exportado

Os tipos de informação confidencial no arquivo XML e outros elementos no arquivo são descritos anteriormente neste tópico.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>Etapa 3: Importar o arquivo XML atualizado de volta para o pacote de regras existente

Para importar o XML atualizado de volta para o pacote de regras existente, use o cmdlet [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage):

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

Para informações detalhadas sobre sintaxe e parâmetros, confira [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage).


## <a name="more-information"></a>Mais informações

- [Saiba mais sobre a prevenção contra perda de dados](dlp-learn-about-dlp.md)

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)

- [O que as funções DLP procuram](what-the-dlp-functions-look-for.md)
