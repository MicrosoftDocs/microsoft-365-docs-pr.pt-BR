---
title: Modificar o esquema de Correspondência de Dados Exato para usar a correspondência configurável
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
description: Saiba como modificar um esquema EDM para usar a correspondência configurável.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7d470b986d4a94206935efb832deec7171f8e404
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114189"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a>Modificar o esquema de Correspondência de Dados Exato para usar a correspondência configurável

A classificação baseada no EDM permite criar tipos personalizados de informações confidenciais que fazem referência a valores exatos em um banco de dados de informações confidenciais. Quando for necessário permitir variantes de uma cadeia de caracteres exata, você poderá usar *correspondência configurável* para informar à Microsoft 365 para ignorar maiúsculas e minúsculas e alguns delimitadores. 

> [!IMPORTANT]
> Use este procedimento para modificar um esquema EDM e um arquivo de dados.

1. Desinstale o **EdmUploadAgent. exe** do computador que você usa para se conectar ao Microsoft 365 para fins de carregamento de arquivos de dados e esquema EDM.

2. Baixe o arquivo **EdmUploadAgent.exe** apropriado para sua assinatura usando os links a seguir:
    - [Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – a maioria dos clientes comerciais devem usar este
    - [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) – especificamente para assinantes da nuvem governamental de alta segurança
    - [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – este é especificamente para os clientes de nuvem do Departamento de Defesa dos Estados Unidos

3. Para autorizar o Agente de Carregamento EDM, abra o prompt de comando (como um administrador), e execute o seguinte comando:

   `EdmUploadAgent.exe /Authorize`

4. Se você não tiver uma cópia atual do esquema existente, será necessário baixar uma cópia do esquema existente, execute este comando:

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. Personalize o esquema de modo que cada coluna use "caseInsensitive" e/ou "ignoredDelimiters".  O valor padrão para "caseInsensitive" é "falso" e para "ignoredDelimiters", é uma cadeia de caracteres vazia. 

> [!NOTE]
> O tipo de informação confidencial personalizado subjacente ou o tipo de informações confidenciais incorporadas usado para detectar o padrão de regex geral devem oferecer suporte à detecção das entradas de variações listadas com o ignoredDelimiters. Por exemplo, o tipo de informações confidenciais interna do U.S. Social Security Number (SSN) pode detectar variações nos dados que incluem traços, espaços ou falta de espaço entre os números agrupados que compõem o SSN. Como resultado, os únicos delimitadores relevantes a serem incluídos na ignoredDelimiters do EDM para dados de SSN são: travessão e espaço.

Este é um esquema de exemplo que simula correspondência de diferenciação de maiúsculas e minúsculas, criando as colunas extras necessárias para reconhecer variações de caso nos dados confidenciais.

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
           <Field name="PolicyNumber" searchable="true" />
           <Field name="PolicyNumberLowerCase" searchable="true" />
           <Field name="PolicyNumberUpperCase" searchable="true" />
           <Field name="PolicyNumberCapitalLetters" searchable="true" />
  </DataStore>
</EdmSchema>
```

No exemplo acima, as variações da coluna `PolicyNumber` original não serão mais necessárias se `caseInsensitive` e `ignoredDelimiters` forem adicionados.

Para atualizar esse esquema de modo que o EDM use a combinação configurável use os sinalizadores `caseInsensitive` e `ignoredDelimiters`.  Veja como isso é possível:

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

O sinalizador `ignoredDelimiters` dá suporte a qualquer caractere não alfanumérico, aqui estão alguns exemplos:
- \.
- \-
- \/
- \_
- \*
- \^
- \#
- \!
- \?
- \[
- \]
- \{
- \}
- \\
- \~
- \;

O sinalizador `ignoredDelimiters` não tem suporte para:
- caracteres de 0 a 9
- A-Z
- A-Z
- \"
- \,

6. Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](/powershell/exchange/connect-to-scc-powershell).

> [!NOTE]
> Se sua organização configurou a [Chave de Cliente para Microsoft 365 no nível dos locatários (visualização pública)](customer-key-tenant-level.md#overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview), a Correspondência exata de dados usará sua funcionalidade de criptografia automaticamente. Isso está disponível apenas para locatários licenciados do E5 na nuvem Comercial.

7. Atualize o esquema executando estes cmdlets um de cada vez:

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. Se necessário, atualize o arquivo de dados para corresponder à nova versão de esquema

> [!TIP]
> Opcionalmente, você pode executar uma validação contra o arquivo CSV antes de carregar executando:
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
>Para obter mais informações sobre todos os parâmetros suportados do EdmUploadAgent.exe >execute
>
> `EdmUploadAgent.exe /?`

9. Abra a janela do linha de comando (como um administrador) e execute o seguinte comando para hash e carregamento de dados confidenciais:

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a>Artigos relacionados

- Confira [Criar um tipo de informações confidenciais personalizadas com classificação baseada em Correspondência de Dados Exata](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
- [Tipos personalizados de informações confidenciais](./sensitive-information-type-learn-about.md)
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md)
- [Microsoft Cloud App Security](/cloud-app-security)
- [New-DlpEdmSchema](/powershell/module/exchange/new-dlpedmschema)