---
title: 'Criar tipos personalizados de informações confidenciais com Exact Data Match '
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
description: Criar tipos personalizados de informações confidenciais com classificação baseada em Correspondência Exata de Dados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b120e2bffa4554fb435fe8de2e22d6de2f851544
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604333"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="2c3cf-103">Criar tipos personalizados de informações confidenciais com classificação baseada em Exact Data Match</span><span class="sxs-lookup"><span data-stu-id="2c3cf-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="2c3cf-104">[Tipos de informações confidenciais personalizadas](custom-sensitive-info-types.md) são usadas para ajudar a identificar itens confidenciais para que você possa evitar que sejam compartilhados inadvertidamente ou inadequadamente.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="2c3cf-105">Você define um tipo de informações confidenciais personalizada com base em:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="2c3cf-106">padrões</span><span class="sxs-lookup"><span data-stu-id="2c3cf-106">patterns</span></span>
- <span data-ttu-id="2c3cf-107">evidência de palavra-chave, como *funcionário*, *alça de preenchimento* ou *ID*</span><span class="sxs-lookup"><span data-stu-id="2c3cf-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="2c3cf-108">proximidade de um caractere da evidência em um padrão específico</span><span class="sxs-lookup"><span data-stu-id="2c3cf-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="2c3cf-109">níveis de confiança</span><span class="sxs-lookup"><span data-stu-id="2c3cf-109">confidence levels</span></span>

 <span data-ttu-id="2c3cf-110">Esses tipos personalizados de informações confidenciais atendem às necessidades comerciais de várias organizações.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="2c3cf-111">Mas e se você quiser um tipo personalizado de informações confidenciais que usa valores de dados exatos, em vez de corresponder apenas a padrões genéricos?</span><span class="sxs-lookup"><span data-stu-id="2c3cf-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="2c3cf-112">Com a classificação baseada em Exact Data Match (EDM), você pode criar um tipo personalizado de informações confidenciais que é criada para:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="2c3cf-113">ser dinâmico e atualizável</span><span class="sxs-lookup"><span data-stu-id="2c3cf-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="2c3cf-114">ser mais escalonável</span><span class="sxs-lookup"><span data-stu-id="2c3cf-114">be more scalable</span></span>
- <span data-ttu-id="2c3cf-115">resultar em menos falso-positivos</span><span class="sxs-lookup"><span data-stu-id="2c3cf-115">result in fewer false-positives</span></span>
- <span data-ttu-id="2c3cf-116">trabalhar com dados confidenciais estruturados</span><span class="sxs-lookup"><span data-stu-id="2c3cf-116">work with structured sensitive data</span></span>
- <span data-ttu-id="2c3cf-117">lidar com as informações confidenciais com mais segurança</span><span class="sxs-lookup"><span data-stu-id="2c3cf-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="2c3cf-118">ser usado com vários serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c3cf-118">be used with several Microsoft cloud services</span></span>

![Classificação baseada em EDM](../media/EDMClassification.png)

<span data-ttu-id="2c3cf-120">A classificação baseada no EDM permite criar tipos personalizados de informações confidenciais que fazem referência a valores exatos em um banco de dados de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="2c3cf-121">O banco de dados pode ser atualizado diariamente e pode conter até 100 milhões de linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="2c3cf-122">Assim como funcionários, pacientes ou clientes vêm e vão e os registros são alterados, os tipos personalizados de informações confidenciais permanecem atualizados e aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="2c3cf-123">Você também pode usar a classificação baseada em EDM com políticas, como [políticas de prevenção contra perda de dados](data-loss-prevention-policies.md) (DLP) ou [políticas de arquivo do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="2c3cf-124">A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="2c3cf-125">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="2c3cf-126">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="2c3cf-127">Coreano</span><span class="sxs-lookup"><span data-stu-id="2c3cf-127">Korean</span></span>
> - <span data-ttu-id="2c3cf-128">Japonês</span><span class="sxs-lookup"><span data-stu-id="2c3cf-128">Japanese</span></span>

><span data-ttu-id="2c3cf-129">Este suporte está disponível para tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="2c3cf-130">Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="2c3cf-131">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="2c3cf-131">Required licenses and permissions</span></span>

<span data-ttu-id="2c3cf-132">Você deve ser um administrador global, administrador de conformidade ou administrador do Exchange Online para executar as tarefas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="2c3cf-133">Para saber mais sobre permissões DLP, confira [Permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="2c3cf-134">A classificação baseada em EDM está incluída nestas assinaturas</span><span class="sxs-lookup"><span data-stu-id="2c3cf-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="2c3cf-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="2c3cf-135">Office 365 E5</span></span>
- <span data-ttu-id="2c3cf-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2c3cf-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="2c3cf-137">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="2c3cf-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="2c3cf-138">Proteção e governança de informações do Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="2c3cf-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="2c3cf-139">Links do portal para sua assinatura</span><span class="sxs-lookup"><span data-stu-id="2c3cf-139">Portal links for your subscription</span></span>


|<span data-ttu-id="2c3cf-140">Portal</span><span class="sxs-lookup"><span data-stu-id="2c3cf-140">Portal</span></span>  |<span data-ttu-id="2c3cf-141">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="2c3cf-141">World Wide/GCC</span></span>  |<span data-ttu-id="2c3cf-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="2c3cf-142">GCC-High</span></span>  |<span data-ttu-id="2c3cf-143">DOD</span><span class="sxs-lookup"><span data-stu-id="2c3cf-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="2c3cf-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="2c3cf-144">Office SCC</span></span>     |  <span data-ttu-id="2c3cf-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="2c3cf-145">protection.office.com</span></span>       |<span data-ttu-id="2c3cf-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="2c3cf-146">scc.office365.us</span></span>         |<span data-ttu-id="2c3cf-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="2c3cf-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="2c3cf-148">Centro de Segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c3cf-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="2c3cf-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2c3cf-149">security.microsoft.com</span></span>         |<span data-ttu-id="2c3cf-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="2c3cf-150">security.microsoft.us</span></span>         |<span data-ttu-id="2c3cf-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="2c3cf-151">security.apps.mil</span></span>|
|<span data-ttu-id="2c3cf-152">Centro de Conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2c3cf-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="2c3cf-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="2c3cf-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="2c3cf-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="2c3cf-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="2c3cf-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="2c3cf-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="2c3cf-156">Visão geral do fluxo de trabalho </span><span class="sxs-lookup"><span data-stu-id="2c3cf-156">The work flow at a glance</span></span>

|<span data-ttu-id="2c3cf-157">Fase</span><span class="sxs-lookup"><span data-stu-id="2c3cf-157">Phase</span></span>  |<span data-ttu-id="2c3cf-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c3cf-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="2c3cf-159">Parte 1: Configuração da classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="2c3cf-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="2c3cf-160">(conforme o necessário)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-160">(As needed)</span></span><br/><span data-ttu-id="2c3cf-161">- [Edite o Esquema de Banco de Dados](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="2c3cf-162">- [Remova o esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="2c3cf-163">– Acesso de leitura aos dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="2c3cf-164">– Esquema de banco de dados no formato XML (exemplo fornecido)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="2c3cf-165">– Pacote de regras no formato XML (exemplo fornecido)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="2c3cf-166">– Permissões de administrador ao Centro de Conformidade e Segurança (usando o PowerShell)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="2c3cf-167">Parte 2: hash e carregamento de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="2c3cf-168">(conforme o necessário)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-168">(As needed)</span></span><br/>[<span data-ttu-id="2c3cf-169">Atualize os dados</span><span class="sxs-lookup"><span data-stu-id="2c3cf-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="2c3cf-170">– Grupo de segurança personalizado e conta de usuário</span><span class="sxs-lookup"><span data-stu-id="2c3cf-170">- Custom security group and user account</span></span><br/><span data-ttu-id="2c3cf-171">– Acesso de administrador local à máquina com o agente de carregamento do EDM</span><span class="sxs-lookup"><span data-stu-id="2c3cf-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="2c3cf-172">– Acesso de leitura aos dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="2c3cf-173">– Processar e agendar a atualização de dados</span><span class="sxs-lookup"><span data-stu-id="2c3cf-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="2c3cf-174">Parte 3: uso da classificação baseada em EDM com os serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c3cf-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="2c3cf-175">– Assinatura do Microsoft 365 com DLP</span><span class="sxs-lookup"><span data-stu-id="2c3cf-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="2c3cf-176">– Recurso de classificação baseada em EDM habilitado</span><span class="sxs-lookup"><span data-stu-id="2c3cf-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="2c3cf-177">Parte 1: Configuração da classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="2c3cf-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="2c3cf-178">Organizar e configurar a classificação baseada em EDM envolve:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="2c3cf-179">Salvar os dados confidenciais no formato .csv</span><span class="sxs-lookup"><span data-stu-id="2c3cf-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="2c3cf-180">Definir o esquema do banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="2c3cf-181">Configurar um pacote de regras</span><span class="sxs-lookup"><span data-stu-id="2c3cf-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="2c3cf-182">Salvar os dados confidenciais no formato .csv</span><span class="sxs-lookup"><span data-stu-id="2c3cf-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="2c3cf-183">Identifique as informações confidenciais que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="2c3cf-184">Exporte os dados para um aplicativo, como o Microsoft Excel, e salve o arquivo no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="2c3cf-185">O arquivo de dados pode incluir um máximo de:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="2c3cf-186">Até 100 milhões de linhas de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="2c3cf-187">Até 32 colunas (campos) por fonte de dados</span><span class="sxs-lookup"><span data-stu-id="2c3cf-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="2c3cf-188">Até 5 colunas (campos) marcadas como pesquisáveis</span><span class="sxs-lookup"><span data-stu-id="2c3cf-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="2c3cf-189">Estruture os dados confidenciais no arquivo .csv, de modo que a primeira linha inclui os nomes dos campos usados na classificação baseada em EDM.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="2c3cf-190">Você pode ter nomes de campo no arquivo .csv, como "CPF", "data de nascimento", "nome", "sobrenome".</span><span class="sxs-lookup"><span data-stu-id="2c3cf-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="2c3cf-191">Os nomes de cabeçalhos de coluna não podem conter espaços ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="2c3cf-192">Por exemplo, o arquivo .csv de amostra que usamos neste artigo é denominado *PatientRecords.csv* e suas colunas incluem *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* e mais.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

3. <span data-ttu-id="2c3cf-193">Preste atenção ao formato dos campos de dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-193">Pay attention to the format of the sensitive data fields.</span></span> <span data-ttu-id="2c3cf-194">Em particular, os campos que podem conter vírgulas no conteúdo (por exemplo, um endereço com o valor "Seattle,WA") seriam analisados como dois campos separados quando analisados pela ferramenta EDM.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-194">In particular, fields that may contain commas in their content (e.g. a street address that contains the value "Seattle,WA") would be parsed as two eparate fields when parsed by the EDM tool.</span></span> <span data-ttu-id="2c3cf-195">Para evitar isso, certifique-se de que esses campos estejam entre aspas simples ou duplas na tabela de dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-195">In order to avoid this, you need to ensure such fields are surrounded by single or double quotes in the sensitive data table.</span></span> <span data-ttu-id="2c3cf-196">Se os campos com vírgulas também podem conter espaços, você precisará criar um Tipo de Informação Confidencial personalizado compatível com o formato correspondente (por exemplo, uma cadeia de caracteres de várias palavras com vírgulas e espaços) para garantir que a cadeia de caracteres corresponde corretamente quando o documento for verificado.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-196">If fields with commas in them may also contain spaces, you would need to create a custom Sensitive Information Type that matches the corresponding format (e.g. a multi-word string with commas and spaces in it) to ensure the string is correctly matched wjen the document is scanned.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="2c3cf-197">Definir o esquema para seu banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-197">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="2c3cf-198">Defina o esquema para o banco de dados de informações confidenciais no formato XML (semelhante ao nosso exemplo a seguir).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-198">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="2c3cf-199">Nomeie esse arquivo de esquema como **edm.xml** e configure-o de forma que, para cada coluna no banco de dados, haja uma linha que use a sintaxe:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-199">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="2c3cf-200">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-200">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="2c3cf-201">Use nomes de coluna para valores de *Nome de campo*.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-201">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="2c3cf-202">Use *searchable = "true"* para os campos que você deseja que sejam pesquisáveis de ​​até no máximo 5 campos.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-202">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="2c3cf-203">Pelo menos um campo deve ser pesquisável.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-203">At least one field must be searchable.</span></span>

      <span data-ttu-id="2c3cf-204">Como exemplo, o seguinte arquivo XML define o esquema para um banco de dados de registros de pacientes, com cinco campos especificados como pesquisáveis: *PatientID*, *MRN*, *SSN*, *Telefone* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-204">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="2c3cf-205">(Você pode copiar, modificar e usar nosso exemplo.)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-205">(You can copy, modify, and use our example.)</span></span>

      ```xml
      <EdmSchema xmlns="http://schemas.microsoft.com/office/2018/edm">
            <DataStore name="PatientRecords" description="Schema for patient records" version="1">
                  <Field name="PatientID" searchable="true" />
                  <Field name="MRN" searchable="true" />
                  <Field name="FirstName" />
                  <Field name="LastName" />
                  <Field name="SSN" searchable="true" />
                  <Field name="Phone" searchable="true" />
                  <Field name="DOB" searchable="true" />
                  <Field name="Gender" />
                  <Field name="Address" />
            </DataStore>
      </EdmSchema>
      ```

4. <span data-ttu-id="2c3cf-206">Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-206">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="2c3cf-207">Para carregar o esquema do banco de dados, execute os seguintes cmdlets, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-207">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="2c3cf-208">Você será solicitado a confirmar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-208">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="2c3cf-209">Confirmar</span><span class="sxs-lookup"><span data-stu-id="2c3cf-209">Confirm</span></span>
      >
      > <span data-ttu-id="2c3cf-210">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="2c3cf-210">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="2c3cf-211">O novo esquema EDM para o repositório de dado 'patientrecords' será importado.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-211">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="2c3cf-212">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="2c3cf-212">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="2c3cf-213">Se você deseja que suas alterações ocorram sem confirmação, na Etapa 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="2c3cf-213">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="2c3cf-214">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-214">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="2c3cf-215">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-215">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="2c3cf-216">Configurar um pacote de regras</span><span class="sxs-lookup"><span data-stu-id="2c3cf-216">Set up a rule package</span></span>

1. <span data-ttu-id="2c3cf-217">Crie um pacote de regras no formato XML (com codificação Unicode), semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-217">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="2c3cf-218">(Você pode copiar, modificar e usar nosso exemplo.)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-218">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="2c3cf-219">Ao configurar o seu pacote de regras, certifique-se de referenciar corretamente o arquivo .csv e o arquivo **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-219">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="2c3cf-220">Você pode copiar, modificar e usar nosso exemplo.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-220">You can copy, modify, and use our example.</span></span> <span data-ttu-id="2c3cf-221">Neste exemplo de xml, os seguintes campos precisam ser personalizados para criar seu tipo confidencial do EDM:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-221">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="2c3cf-222">**Id do RulePack e id ExactMatch**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) para gerar um GUID.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-222">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="2c3cf-223">**Datastore**: este campo especifica o repositório de dados de pesquisa EDM a ser usado.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-223">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="2c3cf-224">Forneça um nome de fonte de dados de um esquema EDM configurado.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-224">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="2c3cf-225">**idMatch**: este campo aponta para o elemento principal do EDM.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-225">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="2c3cf-226">Correspondências: especifica o campo a ser usado na pesquisa exata.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-226">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="2c3cf-227">Forneça um nome de campo pesquisável no esquema EDM para o DataStore.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-227">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="2c3cf-228">Classificação: este campo especifica a correspondência de tipo confidencial que dispara a pesquisa EDM.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-228">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="2c3cf-229">Você pode fornecer o nome ou o GUID de uma classificação interna ou personalizada existente.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-229">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="2c3cf-230">**Corresponder:** este campo aponta para evidências adicionais encontradas em proximidade do idMatch.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-230">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="2c3cf-231">Correspondências: forneça o nome do campo no esquema EMD para DataStore.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-231">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="2c3cf-232">**Recurso:** esta seção especifica o nome e a descrição do tipo confidencial em várias localidades.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-232">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="2c3cf-233">idRef: forneça GUID para ExactMatch id.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-233">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="2c3cf-234">Nomes e descrições: personalizar conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-234">Name & descriptions: customize as required.</span></span>

      ```xml
      <RulePackage xmlns="http://schemas.microsoft.com/office/2018/edm">
        <RulePack id="fd098e03-1796-41a5-8ab6-198c93c62b11">
          <Version build="0" major="2" minor="0" revision="0" />
          <Publisher id="eb553734-8306-44b4-9ad5-c388ad970528" />
          <Details defaultLangCode="en-us">
            <LocalizedDetails langcode="en-us">
              <PublisherName>IP DLP</PublisherName>
              <Name>Health Care EDM Rulepack</Name>
              <Description>This rule package contains the EDM sensitive type for health care sensitive types.</Description>
            </LocalizedDetails>
          </Details>
        </RulePack>
        <Rules>
          <ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
            <Pattern confidenceLevel="65">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
            </Pattern>
            <Pattern confidenceLevel="75">
              <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
              <Any minMatches ="3" maxMatches ="6">
                <match matches="PatientID" />
                <match matches="MRN"/>
                <match matches="FirstName"/>
                <match matches="LastName"/>
                <match matches="Phone"/>
                <match matches="DOB"/>
              </Any>
            </Pattern>
          </ExactMatch>
          <LocalizedStrings>
            <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
              <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
              <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
            </Resource>
          </LocalizedStrings>
        </Rules>
      </RulePackage>
      ```

1. <span data-ttu-id="2c3cf-235">Carregue o pacote de regras executando os seguintes cmdlets do PowerShell, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-235">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="2c3cf-236">Nesse ponto, você configurou a classificação baseada em EDM.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-236">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="2c3cf-237">A próxima etapa é criar o hash dos dados confidenciais e carregar os hashes de indexação.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-237">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="2c3cf-238">Lembre-se do procedimento anterior onde o nosso esquema PatientRecords define cinco campos como pesquisáveis: *PatientID*, *MRN*, *SSN*, *Phone* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-238">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="2c3cf-239">Nosso pacote de regras de exemplo inclui esses campos e faz referência ao arquivo de esquema do banco de dados (**edm.xml**), com um item *ExactMatch* por campo pesquisável.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-239">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="2c3cf-240">Considere o seguinte item ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-240">Consider the following ExactMatch item:</span></span>

```xml
<ExactMatch id = "E1CC861E-3FE9-4A58-82DF-4BD259EAB371" patternsProximity = "300" dataStore ="PatientRecords" recommendedConfidence = "65" >
      <Pattern confidenceLevel="65">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <idMatch matches = "SSN" classification = "U.S. Social Security Number (SSN)" />
        <Any minMatches ="3" maxMatches ="100">
          <match matches="PatientID" />
          <match matches="MRN"/>
          <match matches="FirstName"/>
          <match matches="LastName"/>
          <match matches="Phone"/>
          <match matches="DOB"/>
        </Any>
      </Pattern>
    </ExactMatch>
```

<span data-ttu-id="2c3cf-241">Nesse exemplo, observe que:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-241">In this example, note that:</span></span>

- <span data-ttu-id="2c3cf-242">O nome do dataStore faz referência ao arquivo .csv que criamos anteriormente: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-242">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="2c3cf-243">O valor idMatch faz referência a um campo pesquisável listado no arquivo de esquema do banco de dados: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-243">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="2c3cf-244">O valor de classificação faz referência a um tipo de informação confidencial existente ou personalizada: **classification = "Número de Seguridade Social dos EUA (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-244">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="2c3cf-245">(Nesse caso, usamos o tipo de informação confidencial existente do Número de Seguridade Social dos EUA.)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-245">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="2c3cf-246">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-246">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="2c3cf-247">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-247">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="2c3cf-248">Editando o esquema para classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="2c3cf-248">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="2c3cf-249">Se você quiser fazer alterações em seu arquivo **edm.xml**, como alterar quais os campos usados para a classificação baseada em EDM, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-249">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="2c3cf-250">Edite seu arquivo **edm.xml** (este é o arquivo discutido na seção [Definir o esquema](#define-the-schema-for-your-database-of-sensitive-information) deste artigo).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-250">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="2c3cf-251">Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-251">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="2c3cf-252">Para atualizar o seu esquema do banco de dados, execute os seguintes cmdlets, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-252">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="2c3cf-253">Você será solicitado a confirmar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-253">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="2c3cf-254">Confirmar</span><span class="sxs-lookup"><span data-stu-id="2c3cf-254">Confirm</span></span>
      >
      > <span data-ttu-id="2c3cf-255">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="2c3cf-255">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="2c3cf-256">O esquema EDM para o repositório de dados 'patientrecords' será atualizado.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-256">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="2c3cf-257">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="2c3cf-257">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="2c3cf-258">Se você quiser que suas alterações ocorram sem confirmação, na Etapa 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="2c3cf-258">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="2c3cf-259">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-259">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="2c3cf-260">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-260">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="2c3cf-261">Removendo o esquema para classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="2c3cf-261">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="2c3cf-262">(Conforme necessário) Se você quiser remover o esquema que está usando para classificação baseada em EDM, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-262">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="2c3cf-263">Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-263">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="2c3cf-264">Execute os seguinte cmdlets do PowerShell, substituindo o nome do repositório de dados do "patient records" pelo nome que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-264">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="2c3cf-265">Será solicitado que você confirme:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-265">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="2c3cf-266">Confirmar</span><span class="sxs-lookup"><span data-stu-id="2c3cf-266">Confirm</span></span>
      >
      > <span data-ttu-id="2c3cf-267">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="2c3cf-267">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="2c3cf-268">O esquema EDM para o repositório de dados 'patientrecords' será removido.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-268">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="2c3cf-269">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="2c3cf-269">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="2c3cf-270">Se você deseja que suas alterações ocorram sem confirmação, na Etapa 2, use este cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm: $ false</span><span class="sxs-lookup"><span data-stu-id="2c3cf-270">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


<!-- salt notes
need two salting procedures, one for onestep from the externally facing and another for two step, on an internal machine then the upload from the external machine

- create A  folder put the edmupload agent and, csv and salt file there, run all processes there
- 
- stuff you need to have first: DataStoreName, /DataFile name (csv file)  /Hashlocation

- salt can be randomly generated by Microsoft or can be provided by the customer. If provided by the customer it must follow  format of 64 character, and can contain only letters or 0-9 characters.  Use a website to generate a valid salt value.
 
- can run EDMuploadagent.exe from PS or Windows cmd window . tested on Windows Server 2016 or Windows 10 and dot net version 4.6.2

when defiuning the schema file the searchable fields must be either an out of box SIT or custom SIT, only 5 fields )column headings) can be searchable

1. From outbound access device from the cmd prompt run EdmUploadAgent.exe /Authorize -  
2. data store schema must have already been uploaded
3.  create hash first then do upload
4. EdmUploadAgent.exe /CreateHash /DataFile (where the data file is ) E:\emd\test\data\schema32_1000000,csv /HashLocation  (where to store it) E:\edm\tat\hash this makes the salt file and the hash file as output
5. next is upload EdmUploadAgent.exe /UploadHash /DataStoreName (found in the Schema file DataSore name="FOO" /HashFile (path to hash file locaztion and file name /HashLocation path to hash)  for example
1.EdmUploadAgent/exe /UploadHash /DataStoreName schema321 /HashFile E:\edm\test\hash\schema32_10000000.EdmHash /HashLocation E:\edm\test\hash  -this one  uses MSFT generated salt, so no need to provide

Salt is an optional parameter so if yo uwant to use a custom salt add /salt and the salt value if salt file not copied to the outbound machine 

OR copy both files hash and salt to the same directory and the commmand will get both


OR do it in single step hash, salt ulopad

!! once they download the updated upload agent they will always have SALT, there is no going back.


all in one step: EdmUploadAgent.exe /UploadData /DataStoreName schema321 /DataFile E:\edm\test\data\schema32_10000.csv /HashLocation E:\edm\test\hash

tshooting/check status cmd



Once it gets to completed the admin can start using it in the custom SIT

they have to get their own custom SALT

just copy SALT over in a secure fashion










1.
6.
7.
1.  


 -->

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="2c3cf-271">Parte 2: hash e carregamento de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-271">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="2c3cf-272">Nessa fase, você configura um grupo de segurança personalizado e uma conta de usuário, e configura a ferramenta do agente de carregamento do EDM.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-272">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="2c3cf-273">Depois, use a ferramenta para o hash com valor salt dos dados confidenciais e carregue-los.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-273">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="2c3cf-274">O hash e o carregamento podem ser feitos usando um computador, ou você pode separar a etapa de hash da etapa de carregamento para obter mais segurança.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-274">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="2c3cf-275">Se você quiser usar o hash e carregá-los de um computador, será preciso fazer isso em um computador que possa se conectar diretamente ao seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-275">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="2c3cf-276">Isso exige que os arquivos de dados confidenciais de texto sem formatação estejam no computador para hash.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-276">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="2c3cf-277">Se você não quiser expor o seu arquivo de dados confidenciais de texto não criptografado, poderá hashá-lo em um computador em um local seguro e, em seguida, copiar o arquivo de hash e o arquivo salt para um computador que possa conectar-se diretamente ao locatário do Microsoft 365 para carregamento.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-277">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="2c3cf-278">Neste cenário, você precisará do EDMUploadAgent em ambos os computadores.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-278">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="2c3cf-279">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2c3cf-279">Prerequisites</span></span>

- <span data-ttu-id="2c3cf-280">uma conta corporativa ou de estudante do Microsoft 365 que será adicionada ao grupo de segurança **EDM\_DataUploaders**</span><span class="sxs-lookup"><span data-stu-id="2c3cf-280">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="2c3cf-281">um computador com Windows 10 ou Windows Server 2016 com o .NET versão 4.6.2 para executar o EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="2c3cf-281">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="2c3cf-282">um diretório no computador de carregamento para o:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-282">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="2c3cf-283">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="2c3cf-283">EDMUploadAgent</span></span>
    - <span data-ttu-id="2c3cf-284">seu arquivo de item confidencial no formato cvs **PatientRecords.csv** em nossos exemplos</span><span class="sxs-lookup"><span data-stu-id="2c3cf-284">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="2c3cf-285">os arquivos hash de saída e salt</span><span class="sxs-lookup"><span data-stu-id="2c3cf-285">and the output hash and salt files</span></span>
    - <span data-ttu-id="2c3cf-286">o nome do repositório de armazenamento do arquivo **edm.xml**, para esse exemplo, é `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="2c3cf-286">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="2c3cf-287">Configuração do grupo de segurança e conta de usuário</span><span class="sxs-lookup"><span data-stu-id="2c3cf-287">Set up the security group and user account</span></span>

1. <span data-ttu-id="2c3cf-288">Como administrador global, vá para o centro de administração usando o [link apropriado para sua assinatura](#portal-links-for-your-subscription) e [crie um grupo de segurança](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) chamado **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-288">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="2c3cf-289">Adicione um ou mais usuários ao grupo de segurança **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-289">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="2c3cf-290">(Esses usuários vão gerenciar o banco de dados de informações confidenciais.)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-290">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="2c3cf-291">Hash e carregamento de um computador</span><span class="sxs-lookup"><span data-stu-id="2c3cf-291">Hash and upload from one computer</span></span>

<span data-ttu-id="2c3cf-292">Esse computador deve ter acesso direto ao seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-292">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="2c3cf-293">Antes de iniciar este procedimento, certifique-se de que você é membro do grupo de segurança **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-293">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="2c3cf-294">Links para o agente de carregamento EDM por tipo de assinatura</span><span class="sxs-lookup"><span data-stu-id="2c3cf-294">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="2c3cf-295">Comercial + GCC</span><span class="sxs-lookup"><span data-stu-id="2c3cf-295">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="2c3cf-296">GCC-High</span><span class="sxs-lookup"><span data-stu-id="2c3cf-296">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="2c3cf-297">DoD</span><span class="sxs-lookup"><span data-stu-id="2c3cf-297">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="2c3cf-298">Crie um diretório de trabalho para o EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-298">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="2c3cf-299">Por exemplo, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-299">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="2c3cf-300">Coloque o arquivo **PatientRecords.csv** lá.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-300">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="2c3cf-301">Baixar e instalar o apropriado [Agente de Carregamento EDM](#links-to-edm-upload-agent-by-subscription-type) para sua assinatura no diretório que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-301">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="2c3cf-302">O EDMUploadAgent nos links acima foi atualizado para adicionar automaticamente um valor salt aos dados do hash.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-302">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="2c3cf-303">Como alternativa, você pode fornecer seu próprio valor salt.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-303">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="2c3cf-304">Depois de usar essa versão, não será possível usar a versão anterior do EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-304">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="2c3cf-305">Você pode carregar dados com o EDMUploadAgent para qualquer armazenamento de dados apenas duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-305">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="2c3cf-306">Para obter uma lista com os parâmetros de comando com suporte, execute o agente sem argumentos.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-306">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="2c3cf-307">Por exemplo, ‘EdmUploadAgent.exe’.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-307">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="2c3cf-308">Para autorizar o Agente de Carregamento EDM, abra o prompt de comando (como um administrador), mude para o diretório **C:\EDM\Data** e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-308">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="2c3cf-309">Entre com sua conta empresarial ou de estudante do Microsoft 365 que foi adicionada ao grupo de segurança EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-309">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="2c3cf-310">As informações do locatário são extraídas da conta do usuário para fazer a conexão.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-310">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="2c3cf-311">Para criar o hash e carregar os dados confidenciais, execute o seguinte comando no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-311">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="2c3cf-312">Exemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="2c3cf-312">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="2c3cf-313">Isso adicionará automaticamente um valor salt gerado aleatoriamente ao hash para aumentar a segurança.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-313">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="2c3cf-314">Opcionalmente, se você quiser usar seu próprio valor salt, adicione o **/Salt <saltvalue>** ao comando.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-314">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="2c3cf-315">Esse valor deve ter 64 caracteres de comprimento e só pode conter os caracteres de a-z e de 0-9.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-315">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="2c3cf-316">Verifique o status de carregamento executando este comando:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-316">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="2c3cf-317">Exemplo: **EdmUploadAgent.exe/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="2c3cf-317">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="2c3cf-318">Procure o status em **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-318">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="2c3cf-319">Verifique novamente em alguns minutos até que o status mude para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-319">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="2c3cf-320">Quando o status for concluído, os dados do EDM estarão prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-320">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="2c3cf-321">Separar hash e upload</span><span class="sxs-lookup"><span data-stu-id="2c3cf-321">Separate Hash and upload</span></span>

<span data-ttu-id="2c3cf-322">Execute o hash em um computador em um ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-322">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="2c3cf-323">Execute os seguinte comando na janela prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-323">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="2c3cf-324">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-324">For example:</span></span>

> <span data-ttu-id="2c3cf-325">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="2c3cf-325">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="2c3cf-326">Isso gerará um arquivo de hash e um arquivo salt com essas extensões, caso você não tenha especificado a opção **/Salt <saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-326">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="2c3cf-327">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="2c3cf-327">.EdmHash</span></span>
- <span data-ttu-id="2c3cf-328">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="2c3cf-328">.EdmSalt</span></span>

2. <span data-ttu-id="2c3cf-329">Copie esses arquivos de forma segura para o computador que você usará para carregar seu arquivo cvs de itens confidenciais (PatientRecords) para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-329">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="2c3cf-330">Para carregar os dados com hash, execute o seguinte comando no prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-330">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="2c3cf-331">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-331">For example:</span></span>

> <span data-ttu-id="2c3cf-332">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="2c3cf-332">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="2c3cf-333">Para verificar se os dados confidenciais foram carregados, execute o seguinte comando na janela do prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-333">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="2c3cf-334">Você verá uma lista de armazenamento de dados e a data da última atualização.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-334">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="2c3cf-335">Se você quiser ver todos os carregamentos de dados em um determinado armazenamento, execute o seguinte comando em um prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-335">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="2c3cf-336">Prossiga para configurar seu processo e agenda da [Atualização de banco de dados de informação confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-336">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="2c3cf-337">Nesse ponto, você já usou a classificação baseada em EDM com os serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-337">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="2c3cf-338">Por exemplo, você pode [configurar uma política usando a classificação baseada em EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-338">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="2c3cf-339">Atualização do banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-339">Refreshing your sensitive information database</span></span>

<span data-ttu-id="2c3cf-340">Você pode atualizar seu banco de dados confidenciais diariamente, e a ferramenta de carregamento do EDM pode reindexar os dados confidenciais e depois recarregar os dados indexados.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-340">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="2c3cf-341">Determine seu processo e a frequência (diariamente ou semanalmente) para atualização do banco de dados de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-341">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="2c3cf-342">Exporte novamente os dados confidenciais para um aplicativo, como o Microsoft Excel, e salve o arquivo no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-342">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="2c3cf-343">Mantenha o mesmo nome de arquivo e local que você usou quando seguiu as etapas descritas em [Hash e upload de dados confidenciais](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-343">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="2c3cf-344">Se não houver alterações na estrutura (nomes de campos) do arquivo .csv, você não precisará fazer alterações no arquivo de esquema do banco de dados ao atualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-344">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="2c3cf-345">Mas se for necessário fazer alterações, não deixe de editar o esquema de banco de dados e seu pacote de regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-345">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="2c3cf-346">Use o [Agendador de tarefas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar as etapas 2 e 3 no procedimento [Hash e fazer upload dos dados confidenciais](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-346">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="2c3cf-347">Você pode agendar tarefas usando vários métodos:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-347">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="2c3cf-348">Método</span><span class="sxs-lookup"><span data-stu-id="2c3cf-348">Method</span></span>             | <span data-ttu-id="2c3cf-349">O que fazer</span><span class="sxs-lookup"><span data-stu-id="2c3cf-349">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="2c3cf-350">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c3cf-350">Windows PowerShell</span></span>     | <span data-ttu-id="2c3cf-351">Confira a documentação do [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) e o [exemplo do script do PowerShell](#example-powershell-script-for-task-scheduler) neste artigo</span><span class="sxs-lookup"><span data-stu-id="2c3cf-351">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="2c3cf-352">API do Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="2c3cf-352">Task Scheduler API</span></span>     | <span data-ttu-id="2c3cf-353">Confira a documentação do [Agendador de tarefas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-353">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="2c3cf-354">Interface do usuário do Windows</span><span class="sxs-lookup"><span data-stu-id="2c3cf-354">Windows user interface</span></span> | <span data-ttu-id="2c3cf-355">No Windows, clique em **Iniciar** e digite Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-355">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="2c3cf-356">Em seguida, na lista de resultados, clique com o botão direito do mouse no **Agendador de Tarefas**, e escolha **executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-356">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="2c3cf-357">Exemplo de script do PowerShell para o Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="2c3cf-357">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="2c3cf-358">Esta seção inclui um exemplo de script do PowerShell que você pode usar para agendar as tarefas de dados de hash e para carregamento de dados com hash:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-358">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="2c3cf-359">Para agendar o hash e carregamento em uma etapa combinada</span><span class="sxs-lookup"><span data-stu-id="2c3cf-359">To schedule hashing and upload in a combined step</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ' /HashLocation' + $hashLocation
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadDataArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="2c3cf-360">Para agendar o hash e carregamento em etapas separadas</span><span class="sxs-lookup"><span data-stu-id="2c3cf-360">To schedule hashing and upload as separate steps</span></span>

```powershell
param(\[string\]$dataStoreName,\[string\]$fileLocation)
\# Assuming current user is also the user context to run the task
$user = "$env:USERDOMAIN\\$env:USERNAME"
$edminstallpath = 'C:\\Program Files\\Microsoft\\EdmUploadAgent\\'
$edmuploader = $edminstallpath + 'EdmUploadAgent.exe'
$csvext = '.csv'
$edmext = '.EdmHash'
\# Assuming CSV file name is same as data store name
$dataFile = "$fileLocation\\$dataStoreName$csvext"
$hashFile = "$fileLocation\\$dataStoreName$edmext"
\# Assuming location to store hash file is same as the location of csv file
$hashLocation = $fileLocation
$createHashArgs = '/CreateHash' + ' /DataFile ' + $dataFile + ' /HashLocation ' + $hashLocation
$uploadHashArgs = '/UploadHash /DataStoreName ' + $dataStoreName + ' /HashFile ' + $hashFile
\# Set up actions associated with the task
$actions = @()
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $createHashArgs -WorkingDirectory $edminstallpath
$actions += New-ScheduledTaskAction -Execute $edmuploader -Argument $uploadHashArgs -WorkingDirectory $edminstallpath
\# Set up trigger for the task
$trigger = New-ScheduledTaskTrigger -Weekly -DaysOfWeek Sunday -At 2am
\# Set up task settings
$principal = New-ScheduledTaskPrincipal -UserId $user -LogonType S4U -RunLevel Highest
$settings = New-ScheduledTaskSettingsSet -RunOnlyIfNetworkAvailable -StartWhenAvailable -WakeToRun
\# Create the scheduled task
$scheduledTask = New-ScheduledTask -Action $actions -Principal $principal -Trigger $trigger -Settings $settings
\# Get credentials to run the task
$creds = Get-Credential -UserName $user -Message "Enter credentials to run the task"
$password=\[Runtime.InteropServices.Marshal\]::PtrToStringAuto(\[Runtime.InteropServices.Marshal\]::SecureStringToBSTR($creds.Password))
\# Register the scheduled task
$taskName = 'EDMUpload\_' + $dataStoreName
Register-ScheduledTask -TaskName $taskName -InputObject $scheduledTask -User $user -Password $password
```

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="2c3cf-361">Parte 3: uso da classificação baseada em EDM com os serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="2c3cf-361">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="2c3cf-362">Estes locais são compatíveis com os tipos de informações confidenciais do EDM:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-362">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="2c3cf-363">DLP para Exchange Online (email)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-363">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="2c3cf-364">OneDrive for Business (arquivos)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-364">OneDrive for Business (files)</span></span>
- <span data-ttu-id="2c3cf-365">Microsoft Teams (conversas)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-365">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="2c3cf-366">DLP para SharePoint (arquivos)</span><span class="sxs-lookup"><span data-stu-id="2c3cf-366">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="2c3cf-367">Políticas DLP de Segurança de Aplicativos do Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="2c3cf-367">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="2c3cf-368">Os tipos de informações confidenciais do EDM para os cenários a seguir estão em desenvolvimento, mas ainda não estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="2c3cf-368">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="2c3cf-369">Classificação automática de rótulos de confidencialidade e rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-369">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="2c3cf-370">Criação de uma política DLP com o EDM</span><span class="sxs-lookup"><span data-stu-id="2c3cf-370">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="2c3cf-371">Vá para o Centro de Conformidade e Segurança usando o apropriado [link para sua assinatura](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="2c3cf-371">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="2c3cf-372">Escolha a **Política**\>**de prevenção contra perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-372">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="2c3cf-373">Escolha **Criar uma política**\>**Personalizada**\>**Avançar**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-373">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="2c3cf-374">Na guia **Nomear sua política**, especifique um nome e uma descrição e, em seguida, escolha **Próximo**. </span><span class="sxs-lookup"><span data-stu-id="2c3cf-374">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="2c3cf-375">Na guia **Escolher locais**, clique em **Escolher locais específicos** e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-375">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="2c3cf-376">Na coluna **Status**, selecione **Trocar email, contas do OneDrive, chats do Teams e mensagem do canal**, e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-376">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="2c3cf-377">Na guia **Configurações de política**, escolha **Usar configurações avançadas** e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-377">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="2c3cf-378">Escolha **+ Nova regra**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-378">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="2c3cf-379">Na seção **Nome**, especifique um nome e uma descrição para a regra.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-379">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="2c3cf-380">Na seção **Condições**, na lista **+ Adicionar uma condição**, escolha **Conteúdo contém tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-380">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![O conteúdo contém tipos de informações confidenciais](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="2c3cf-382">Pesquise pelo tipo de informação confidencial que você criou ao configurar o pacote de regras e, em seguida, escolha **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-382">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="2c3cf-383">Então escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-383">Then choose **Done**.</span></span>

12. <span data-ttu-id="2c3cf-384">Termine de selecionar as opções para a regra, como **Notificações de usuário**, **Substituições do usuário**, **Relatórios de incidente**, e assim por diante, e depois clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-384">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="2c3cf-385">Na guia **Configurações de política**, revise suas regras e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-385">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="2c3cf-386">Especifique se deseja ativar a política imediatamente, testá-la ou desativá-la.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-386">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="2c3cf-387">Depois clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-387">Then choose **Next**.</span></span>

15. <span data-ttu-id="2c3cf-388">Na guia **Revisar suas configurações**, revise sua política.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-388">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="2c3cf-389">Faça todas as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-389">Make any needed changes.</span></span> <span data-ttu-id="2c3cf-390">Quando concluir, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-390">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="2c3cf-391">Espere aproximadamente uma hora para sua nova política DLP funcionar em seu data center.</span><span class="sxs-lookup"><span data-stu-id="2c3cf-391">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="2c3cf-392">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="2c3cf-392">Related articles</span></span>

- [<span data-ttu-id="2c3cf-393">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-393">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="2c3cf-394">Tipos personalizados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="2c3cf-394">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="2c3cf-395">Visão geral das políticas DLP</span><span class="sxs-lookup"><span data-stu-id="2c3cf-395">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="2c3cf-396">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2c3cf-396">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="2c3cf-397">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="2c3cf-397">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)
