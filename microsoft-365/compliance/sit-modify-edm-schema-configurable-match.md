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
ms.openlocfilehash: 2211e4d99d97fcce241a5f4c3ea7c9d8122ca9d7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656794"
---
# <a name="modify-exact-data-match-schema-to-use-configurable-match"></a><span data-ttu-id="4b6de-103">Modificar o esquema de Correspondência de Dados Exato para usar a correspondência configurável</span><span class="sxs-lookup"><span data-stu-id="4b6de-103">Modify Exact Data Match schema to use configurable match</span></span>

<span data-ttu-id="4b6de-104">A classificação baseada no EDM permite criar tipos personalizados de informações confidenciais que fazem referência a valores exatos em um banco de dados de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="4b6de-104">Exact Data Match (EDM) based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="4b6de-105">Quando for necessário permitir variantes de uma cadeia de caracteres exata, você poderá usar *correspondência configurável* para informar à Microsoft 365 para ignorar maiúsculas e minúsculas e alguns delimitadores.</span><span class="sxs-lookup"><span data-stu-id="4b6de-105">When you need to allow for variants of a exact string, you can use *configurable match* to tell Microsoft 365 to ignore case and some delimiters.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="4b6de-106">Use este procedimento para modificar um esquema EDM e um arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="4b6de-106">Use this procedure to modify an existing EDM schema and data file.</span></span>

1. <span data-ttu-id="4b6de-107">Desinstale o **EdmUploadAgent. exe** do computador que você usa para se conectar ao Microsoft 365 para fins de carregamento de arquivos de dados e esquema EDM.</span><span class="sxs-lookup"><span data-stu-id="4b6de-107">Uninstall the **EdmUploadAgent.exe** from the computer that you use to connect to Microsoft 365 for EDM schema and data file upload purposes.</span></span>

2. <span data-ttu-id="4b6de-108">Baixe o arquivo **EdmUploadAgent.exe** apropriado para sua assinatura usando os links a seguir:</span><span class="sxs-lookup"><span data-stu-id="4b6de-108">Download the appropriate **EdmUploadAgent.exe** file for your subscription using the links below:</span></span>
    - <span data-ttu-id="4b6de-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) – a maioria dos clientes comerciais devem usar este</span><span class="sxs-lookup"><span data-stu-id="4b6de-109">[Commercial + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - most commercial customers should use this</span></span>
    - <span data-ttu-id="4b6de-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) – especificamente para assinantes da nuvem governamental de alta segurança</span><span class="sxs-lookup"><span data-stu-id="4b6de-110">[GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - This is specifically for high security government cloud subscribers</span></span>
    - <span data-ttu-id="4b6de-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) – este é especificamente para os clientes de nuvem do Departamento de Defesa dos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="4b6de-111">[DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - this is specifically for United States Department of Defense cloud customers</span></span>

3. <span data-ttu-id="4b6de-112">Para autorizar o Agente de Carregamento EDM, abra o prompt de comando (como um administrador), e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="4b6de-112">Authorize the EDM Upload Agent, open Command Prompt window (as an administrator) and run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

4. <span data-ttu-id="4b6de-113">Se você não tiver uma cópia atual do esquema existente, será necessário baixar uma cópia do esquema existente, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="4b6de-113">If you don't have a current copy of the existing schema, you'll need to download a copy of the existing schema, run this command:</span></span>

    `EdmUploadAgent.exe /SaveSchema /DataStoreName <dataStoreName> [/OutputDir [Output dir location]]`

5. <span data-ttu-id="4b6de-114">Personalize o esquema de modo que cada coluna use "caseInsensitive" e/ou "ignoredDelimiters".</span><span class="sxs-lookup"><span data-stu-id="4b6de-114">Customize the schema so each column utilizes “caseInsensitive” and / or “ignoredDelimiters”.</span></span>  <span data-ttu-id="4b6de-115">O valor padrão para "caseInsensitive" é "falso" e para "ignoredDelimiters", é uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="4b6de-115">The default value for “caseInsensitive” is “false” and for “ignoredDelimiters”, it is an empty string.</span></span> 

> [!NOTE]
> <span data-ttu-id="4b6de-116">O tipo de informação confidencial personalizado subjacente ou o tipo de informações confidenciais incorporadas usado para detectar o padrão de regex geral devem oferecer suporte à detecção das entradas de variações listadas com o ignoredDelimiters.</span><span class="sxs-lookup"><span data-stu-id="4b6de-116">The underlying custom sensitive information type or built in sensitive information type used to detect the general regex pattern must support detection of the variations inputs listed with ignoredDelimiters.</span></span> <span data-ttu-id="4b6de-117">Por exemplo, o tipo de informações confidenciais interna do U.S. Social Security Number (SSN) pode detectar variações nos dados que incluem traços, espaços ou falta de espaço entre os números agrupados que compõem o SSN.</span><span class="sxs-lookup"><span data-stu-id="4b6de-117">For example, the built in U.S. social security number (SSN) sensitive information type can detect variations in the data that include dashes, spaces, or lack of spaces between the grouped numbers that make up the SSN.</span></span> <span data-ttu-id="4b6de-118">Como resultado, os únicos delimitadores relevantes a serem incluídos na ignoredDelimiters do EDM para dados de SSN são: travessão e espaço.</span><span class="sxs-lookup"><span data-stu-id="4b6de-118">As a result, the only delimiters that are relevant to include in EDM’s ignoredDelimiters for SSN data are: dash and space.</span></span>

<span data-ttu-id="4b6de-119">Este é um esquema de exemplo que simula correspondência de diferenciação de maiúsculas e minúsculas, criando as colunas extras necessárias para reconhecer variações de caso nos dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="4b6de-119">Here is a sample schema that simulates case insensitive match by creating the extra columns needed to recognize case variations in the sensitive data.</span></span>

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

<span data-ttu-id="4b6de-120">No exemplo acima, as variações da coluna `PolicyNumber` original não serão mais necessárias se `caseInsensitive` e `ignoredDelimiters` forem adicionados.</span><span class="sxs-lookup"><span data-stu-id="4b6de-120">In the above example, the variations of the original `PolicyNumber` column will no longer be needed if both `caseInsensitive` and `ignoredDelimiters` are added.</span></span>

<span data-ttu-id="4b6de-121">Para atualizar esse esquema de modo que o EDM use a combinação configurável use os sinalizadores `caseInsensitive` e `ignoredDelimiters`.</span><span class="sxs-lookup"><span data-stu-id="4b6de-121">To update this schema so that EDM uses configurable match use the `caseInsensitive` and `ignoredDelimiters` flags.</span></span>  <span data-ttu-id="4b6de-122">Veja como isso é possível:</span><span class="sxs-lookup"><span data-stu-id="4b6de-122">Here's how that looks:</span></span>

```xml
<EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
  <DataStore name="PatientRecords" description="Schema for patient records policy" version="1">
         <Field name="PolicyNumber" searchable="true" caseInsensitive="true" ignoredDelimiters="-,/,*,#,^" />
  </DataStore>
</EdmSchema>
```

<span data-ttu-id="4b6de-123">O sinalizador `ignoredDelimiters` dá suporte a qualquer caractere não alfanumérico, aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="4b6de-123">The `ignoredDelimiters` flag supports any non-alphanumeric character, here are some examples:</span></span>
- <span data-ttu-id="4b6de-124">\.</span><span class="sxs-lookup"><span data-stu-id="4b6de-124">\.</span></span>
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

<span data-ttu-id="4b6de-125">O sinalizador `ignoredDelimiters` não tem suporte para:</span><span class="sxs-lookup"><span data-stu-id="4b6de-125">The `ignoredDelimiters` flag doesn't support:</span></span>
- <span data-ttu-id="4b6de-126">caracteres de 0 a 9</span><span class="sxs-lookup"><span data-stu-id="4b6de-126">characters 0-9</span></span>
- <span data-ttu-id="4b6de-127">A-Z</span><span class="sxs-lookup"><span data-stu-id="4b6de-127">A-Z</span></span>
- <span data-ttu-id="4b6de-128">A-Z</span><span class="sxs-lookup"><span data-stu-id="4b6de-128">a-z</span></span>
- \"
- \,

6. <span data-ttu-id="4b6de-129">Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="4b6de-129">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

7. <span data-ttu-id="4b6de-130">Atualize o esquema executando estes cmdlets um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="4b6de-130">Update your schema by running these cmdlets one at a time:</span></span>

`$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0`

`Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true`

8. <span data-ttu-id="4b6de-131">Se necessário, atualize o arquivo de dados para corresponder à nova versão de esquema</span><span class="sxs-lookup"><span data-stu-id="4b6de-131">If necessary, update the data file to match the new schema version</span></span>

> [!TIP]
> <span data-ttu-id="4b6de-132">Opcionalmente, você pode executar uma validação contra o arquivo CSV antes de carregar executando:</span><span class="sxs-lookup"><span data-stu-id="4b6de-132">Optionally, you can run a validation against your csv file before uploading by running:</span></span>
>
>`EdmUploadAgent.exe /ValidateData /DataFile [data file] [schema file]`
>
><span data-ttu-id="4b6de-133">Para obter mais informações sobre todos os parâmetros suportados do EdmUploadAgent.exe >execute</span><span class="sxs-lookup"><span data-stu-id="4b6de-133">For more information on all the EdmUploadAgent.exe >supported parameters run</span></span>
>
> `EdmUploadAgent.exe /?`

9. <span data-ttu-id="4b6de-134">Abra a janela do linha de comando (como um administrador) e execute o seguinte comando para hash e carregamento de dados confidenciais:</span><span class="sxs-lookup"><span data-stu-id="4b6de-134">Open Command Prompt window (as an administrator) and run the following command to hash and upload your sensitive data:</span></span>

    `EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Salt [custom salt] /Schema [Schema file]`


## <a name="related-articles"></a><span data-ttu-id="4b6de-135">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="4b6de-135">Related articles</span></span>

- <span data-ttu-id="4b6de-136">Confira [Criar um tipo de informações confidenciais personalizadas com classificação baseada em Correspondência de Dados Exata](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span><span class="sxs-lookup"><span data-stu-id="4b6de-136">[Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)</span></span>
- [<span data-ttu-id="4b6de-137">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="4b6de-137">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="4b6de-138">Tipos personalizados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="4b6de-138">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="4b6de-139">Visão geral das políticas DLP</span><span class="sxs-lookup"><span data-stu-id="4b6de-139">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="4b6de-140">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="4b6de-140">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="4b6de-141">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="4b6de-141">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)