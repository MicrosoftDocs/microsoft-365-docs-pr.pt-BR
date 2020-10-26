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
ms.openlocfilehash: 229eb733af85ea5f450969c6d70709cfadcb8f06
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681769"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="e434a-103">Criar tipos personalizados de informações confidenciais com classificação baseada em Exact Data Match</span><span class="sxs-lookup"><span data-stu-id="e434a-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

<span data-ttu-id="e434a-104">[Tipos de informações confidenciais personalizadas](custom-sensitive-info-types.md) são usadas para ajudar a identificar itens confidenciais para que você possa evitar que sejam compartilhados inadvertidamente ou inadequadamente.</span><span class="sxs-lookup"><span data-stu-id="e434a-104">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help identify sensitive items so that you can prevent them from being inadvertently or inappropriately shared.</span></span> <span data-ttu-id="e434a-105">Você define um tipo de informações confidenciais personalizada com base em:</span><span class="sxs-lookup"><span data-stu-id="e434a-105">You define a custom sensitive information type based on:</span></span>

- <span data-ttu-id="e434a-106">padrões</span><span class="sxs-lookup"><span data-stu-id="e434a-106">patterns</span></span>
- <span data-ttu-id="e434a-107">evidência de palavra-chave, como *funcionário*, \* alça de preenchimento\* ou *ID*</span><span class="sxs-lookup"><span data-stu-id="e434a-107">keyword evidence such as *employee*, *badge*, or *ID*</span></span>
- <span data-ttu-id="e434a-108">proximidade de um caractere da evidência em um padrão específico</span><span class="sxs-lookup"><span data-stu-id="e434a-108">character proximity to evidence in a particular pattern</span></span>
- <span data-ttu-id="e434a-109">níveis de confiança</span><span class="sxs-lookup"><span data-stu-id="e434a-109">confidence levels</span></span>

 <span data-ttu-id="e434a-110">Esses tipos personalizados de informações confidenciais atendem às necessidades comerciais de várias organizações.</span><span class="sxs-lookup"><span data-stu-id="e434a-110">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="e434a-111">Mas e se você quiser um tipo personalizado de informações confidenciais que usa valores de dados exatos, em vez de corresponder apenas a padrões genéricos?</span><span class="sxs-lookup"><span data-stu-id="e434a-111">But what if you wanted a custom sensitive information type that uses exact data values, instead of one that found matches based on generic patterns?</span></span> <span data-ttu-id="e434a-112">Com a classificação baseada em Exact Data Match (EDM), você pode criar um tipo personalizado de informações confidenciais que é criada para:</span><span class="sxs-lookup"><span data-stu-id="e434a-112">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="e434a-113">ser dinâmico e atualizável</span><span class="sxs-lookup"><span data-stu-id="e434a-113">be dynamic and refreshable</span></span>
- <span data-ttu-id="e434a-114">ser mais escalonável</span><span class="sxs-lookup"><span data-stu-id="e434a-114">be more scalable</span></span>
- <span data-ttu-id="e434a-115">resultar em menos falso-positivos</span><span class="sxs-lookup"><span data-stu-id="e434a-115">result in fewer false-positives</span></span>
- <span data-ttu-id="e434a-116">trabalhar com dados confidenciais estruturados</span><span class="sxs-lookup"><span data-stu-id="e434a-116">work with structured sensitive data</span></span>
- <span data-ttu-id="e434a-117">lidar com as informações confidenciais com mais segurança</span><span class="sxs-lookup"><span data-stu-id="e434a-117">handle sensitive information more securely</span></span>
- <span data-ttu-id="e434a-118">ser usado com vários serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e434a-118">be used with several Microsoft cloud services</span></span>

![Classificação baseada em EDM](../media/EDMClassification.png)

<span data-ttu-id="e434a-120">A classificação baseada no EDM permite criar tipos personalizados de informações confidenciais que fazem referência a valores exatos em um banco de dados de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e434a-120">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="e434a-121">O banco de dados pode ser atualizado diariamente e pode conter até 100 milhões de linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="e434a-121">The database can be refreshed daily, and contain up to 100 million rows of data.</span></span> <span data-ttu-id="e434a-122">Assim como funcionários, pacientes ou clientes vêm e vão e os registros são alterados, os tipos personalizados de informações confidenciais permanecem atualizados e aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="e434a-122">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="e434a-123">Você também pode usar a classificação baseada em EDM com políticas, como [políticas de prevenção contra perda de dados](data-loss-prevention-policies.md) (DLP) ou [políticas de arquivo do Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="e434a-123">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

> [!NOTE]
> <span data-ttu-id="e434a-124">A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:</span><span class="sxs-lookup"><span data-stu-id="e434a-124">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="e434a-125">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="e434a-125">Chinese (simplified)</span></span>
> - <span data-ttu-id="e434a-126">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="e434a-126">Chinese (traditional)</span></span>
> - <span data-ttu-id="e434a-127">Coreano</span><span class="sxs-lookup"><span data-stu-id="e434a-127">Korean</span></span>
> - <span data-ttu-id="e434a-128">Japonês</span><span class="sxs-lookup"><span data-stu-id="e434a-128">Japanese</span></span>

><span data-ttu-id="e434a-129">Este suporte está disponível para tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e434a-129">This support is available for sensitive information types.</span></span> <span data-ttu-id="e434a-130">Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="e434a-130">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="e434a-131">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="e434a-131">Required licenses and permissions</span></span>

<span data-ttu-id="e434a-132">Você deve ser um administrador global, administrador de conformidade ou administrador do Exchange Online para executar as tarefas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="e434a-132">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="e434a-133">Para saber mais sobre permissões DLP, confira [Permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="e434a-133">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="e434a-134">A classificação baseada em EDM está incluída nestas assinaturas</span><span class="sxs-lookup"><span data-stu-id="e434a-134">EDM-based classification is included in these subscriptions</span></span>

- <span data-ttu-id="e434a-135">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="e434a-135">Office 365 E5</span></span>
- <span data-ttu-id="e434a-136">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e434a-136">Microsoft 365 E5</span></span>
- <span data-ttu-id="e434a-137">Conformidade do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e434a-137">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="e434a-138">Proteção e governança de informações do Microsoft E5/A5</span><span class="sxs-lookup"><span data-stu-id="e434a-138">Microsoft E5/A5 Information Protection and Governance</span></span>

## <a name="portal-links-for-your-subscription"></a><span data-ttu-id="e434a-139">Links do portal para sua assinatura</span><span class="sxs-lookup"><span data-stu-id="e434a-139">Portal links for your subscription</span></span>


|<span data-ttu-id="e434a-140">Portal</span><span class="sxs-lookup"><span data-stu-id="e434a-140">Portal</span></span>  |<span data-ttu-id="e434a-141">World Wide/GCC</span><span class="sxs-lookup"><span data-stu-id="e434a-141">World Wide/GCC</span></span>  |<span data-ttu-id="e434a-142">GCC-High</span><span class="sxs-lookup"><span data-stu-id="e434a-142">GCC-High</span></span>  |<span data-ttu-id="e434a-143">DOD</span><span class="sxs-lookup"><span data-stu-id="e434a-143">DOD</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e434a-144">Office SCC</span><span class="sxs-lookup"><span data-stu-id="e434a-144">Office SCC</span></span>     |  <span data-ttu-id="e434a-145">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="e434a-145">protection.office.com</span></span>       |<span data-ttu-id="e434a-146">scc.office365.us</span><span class="sxs-lookup"><span data-stu-id="e434a-146">scc.office365.us</span></span>         |<span data-ttu-id="e434a-147">scc.protection.apps.mil</span><span class="sxs-lookup"><span data-stu-id="e434a-147">scc.protection.apps.mil</span></span> |
|<span data-ttu-id="e434a-148">Centro de Segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e434a-148">Microsoft 365 Security center</span></span>     |<span data-ttu-id="e434a-149">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e434a-149">security.microsoft.com</span></span>         |<span data-ttu-id="e434a-150">security.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="e434a-150">security.microsoft.us</span></span>         |<span data-ttu-id="e434a-151">security.apps.mil</span><span class="sxs-lookup"><span data-stu-id="e434a-151">security.apps.mil</span></span>|
|<span data-ttu-id="e434a-152">Centro de Conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e434a-152">Microsoft 365 Compliance center</span></span>     |<span data-ttu-id="e434a-153">compliance.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="e434a-153">compliance.microsoft.com</span></span>         |<span data-ttu-id="e434a-154">compliance.microsoft.us</span><span class="sxs-lookup"><span data-stu-id="e434a-154">compliance.microsoft.us</span></span>         |<span data-ttu-id="e434a-155">compliance.apps.mil</span><span class="sxs-lookup"><span data-stu-id="e434a-155">compliance.apps.mil</span></span>|


## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="e434a-156">Visão geral do fluxo de trabalho </span><span class="sxs-lookup"><span data-stu-id="e434a-156">The work flow at a glance</span></span>

|<span data-ttu-id="e434a-157">Fase</span><span class="sxs-lookup"><span data-stu-id="e434a-157">Phase</span></span>  |<span data-ttu-id="e434a-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e434a-158">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="e434a-159">Parte 1: Configuração da classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="e434a-159">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="e434a-160">(conforme o necessário)</span><span class="sxs-lookup"><span data-stu-id="e434a-160">(As needed)</span></span><br/><span data-ttu-id="e434a-161">- [Edite o Esquema de Banco de Dados](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="e434a-161">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="e434a-162">- [Remova o esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="e434a-162">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="e434a-163">– Acesso de leitura aos dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-163">- Read access to the sensitive data</span></span><br/><span data-ttu-id="e434a-164">– Esquema de banco de dados no formato XML (exemplo fornecido)</span><span class="sxs-lookup"><span data-stu-id="e434a-164">- Database schema in XML format (example provided)</span></span><br/><span data-ttu-id="e434a-165">– Pacote de regras no formato XML (exemplo fornecido)</span><span class="sxs-lookup"><span data-stu-id="e434a-165">- Rule package in XML format (example provided)</span></span><br/><span data-ttu-id="e434a-166">– Permissões de administrador ao Centro de Conformidade e Segurança (usando o PowerShell)</span><span class="sxs-lookup"><span data-stu-id="e434a-166">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="e434a-167">Parte 2: hash e carregamento de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-167">Part 2: Hash and upload the sensitive data</span></span>](#part-2-hash-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="e434a-168">(conforme o necessário)</span><span class="sxs-lookup"><span data-stu-id="e434a-168">(As needed)</span></span><br/>[<span data-ttu-id="e434a-169">Atualize os dados</span><span class="sxs-lookup"><span data-stu-id="e434a-169">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="e434a-170">– Grupo de segurança personalizado e conta de usuário</span><span class="sxs-lookup"><span data-stu-id="e434a-170">- Custom security group and user account</span></span><br/><span data-ttu-id="e434a-171">– Acesso de administrador local à máquina com o agente de carregamento do EDM</span><span class="sxs-lookup"><span data-stu-id="e434a-171">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="e434a-172">– Acesso de leitura aos dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-172">- Read access to the sensitive data</span></span><br/><span data-ttu-id="e434a-173">– Processar e agendar a atualização de dados</span><span class="sxs-lookup"><span data-stu-id="e434a-173">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="e434a-174">Parte 3: uso da classificação baseada em EDM com os serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e434a-174">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="e434a-175">– Assinatura do Microsoft 365 com DLP</span><span class="sxs-lookup"><span data-stu-id="e434a-175">- Microsoft 365 subscription with DLP</span></span><br/><span data-ttu-id="e434a-176">– Recurso de classificação baseada em EDM habilitado</span><span class="sxs-lookup"><span data-stu-id="e434a-176">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="e434a-177">Parte 1: Configuração da classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="e434a-177">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="e434a-178">Organizar e configurar a classificação baseada em EDM envolve:</span><span class="sxs-lookup"><span data-stu-id="e434a-178">Setting up and configuring EDM-based classification involves:</span></span>

1. [<span data-ttu-id="e434a-179">Salvar os dados confidenciais no formato .csv</span><span class="sxs-lookup"><span data-stu-id="e434a-179">Saving sensitive data in .csv format</span></span>](#save-sensitive-data-in-csv-format)
2. [<span data-ttu-id="e434a-180">Definir o esquema do banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-180">Define your sensitive information database schema</span></span>](#define-the-schema-for-your-database-of-sensitive-information)
3. [<span data-ttu-id="e434a-181">Configurar um pacote de regras</span><span class="sxs-lookup"><span data-stu-id="e434a-181">Create a rule package</span></span>](#set-up-a-rule-package)


#### <a name="save-sensitive-data-in-csv-format"></a><span data-ttu-id="e434a-182">Salvar os dados confidenciais no formato .csv</span><span class="sxs-lookup"><span data-stu-id="e434a-182">Save sensitive data in .csv format</span></span>

1. <span data-ttu-id="e434a-183">Identifique as informações confidenciais que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="e434a-183">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="e434a-184">Exporte os dados para um aplicativo, como o Microsoft Excel, e salve o arquivo no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="e434a-184">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="e434a-185">O arquivo de dados pode incluir um máximo de:</span><span class="sxs-lookup"><span data-stu-id="e434a-185">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="e434a-186">Até 100 milhões de linhas de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-186">Up to 100 million rows of sensitive data</span></span>
      - <span data-ttu-id="e434a-187">Até 32 colunas (campos) por fonte de dados</span><span class="sxs-lookup"><span data-stu-id="e434a-187">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="e434a-188">Até 5 colunas (campos) marcadas como pesquisáveis</span><span class="sxs-lookup"><span data-stu-id="e434a-188">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="e434a-189">Estruture os dados confidenciais no arquivo .csv, de modo que a primeira linha inclui os nomes dos campos usados na classificação baseada em EDM.</span><span class="sxs-lookup"><span data-stu-id="e434a-189">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="e434a-190">Você pode ter nomes de campo no arquivo .csv, como "CPF", "data de nascimento", "nome", "sobrenome".</span><span class="sxs-lookup"><span data-stu-id="e434a-190">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname".</span></span> <span data-ttu-id="e434a-191">Os nomes de cabeçalhos de coluna não podem conter espaços ou sublinhados.</span><span class="sxs-lookup"><span data-stu-id="e434a-191">The column header names can't include spaces or underscores.</span></span> <span data-ttu-id="e434a-192">Por exemplo, o arquivo .csv de amostra que usamos neste artigo é denominado *PatientRecords.csv* e suas colunas incluem *PatientID*, *MRN*, \* LastName\*, *FirstName*, *SSN* e mais.</span><span class="sxs-lookup"><span data-stu-id="e434a-192">For example, the sample .csv file that we use in this article is named *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN*, and more.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="e434a-193">Definir o esquema para seu banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-193">Define the schema for your database of sensitive information</span></span>

3. <span data-ttu-id="e434a-194">Defina o esquema para o banco de dados de informações confidenciais no formato XML (semelhante ao nosso exemplo a seguir).</span><span class="sxs-lookup"><span data-stu-id="e434a-194">Define the schema for the database of sensitive information in XML format (similar to our example below).</span></span> <span data-ttu-id="e434a-195">Nomeie esse arquivo de esquema como **edm.xml** e configure-o de forma que, para cada coluna no banco de dados, haja uma linha que use a sintaxe:</span><span class="sxs-lookup"><span data-stu-id="e434a-195">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

      <span data-ttu-id="e434a-196">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="e434a-196">`\<Field name="" searchable=""/\>`.</span></span>

      - <span data-ttu-id="e434a-197">Use nomes de coluna para valores de *Nome de campo*.</span><span class="sxs-lookup"><span data-stu-id="e434a-197">Use column names for *Field name* values.</span></span>
      - <span data-ttu-id="e434a-198">Use *searchable = "true"* para os campos que você deseja que sejam pesquisáveis de ​​até no máximo 5 campos.</span><span class="sxs-lookup"><span data-stu-id="e434a-198">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="e434a-199">Pelo menos um campo deve ser pesquisável.</span><span class="sxs-lookup"><span data-stu-id="e434a-199">At least one field must be searchable.</span></span>

      <span data-ttu-id="e434a-200">Como exemplo, o seguinte arquivo XML define o esquema para um banco de dados de registros de pacientes, com cinco campos especificados como pesquisáveis: *PatientID*, *MRN*, *SSN*, *Telefone* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="e434a-200">As an example, the following XML file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

      <span data-ttu-id="e434a-201">(Você pode copiar, modificar e usar nosso exemplo.)</span><span class="sxs-lookup"><span data-stu-id="e434a-201">(You can copy, modify, and use our example.)</span></span>

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

4. <span data-ttu-id="e434a-202">Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e434a-202">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

5. <span data-ttu-id="e434a-203">Para carregar o esquema do banco de dados, execute os seguintes cmdlets, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="e434a-203">To upload the database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="e434a-204">Você será solicitado a confirmar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e434a-204">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="e434a-205">Confirmar</span><span class="sxs-lookup"><span data-stu-id="e434a-205">Confirm</span></span>
      >
      > <span data-ttu-id="e434a-206">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="e434a-206">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="e434a-207">O novo esquema EDM para o repositório de dado 'patientrecords' será importado.</span><span class="sxs-lookup"><span data-stu-id="e434a-207">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
      >
      > <span data-ttu-id="e434a-208">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="e434a-208">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="e434a-209">Se você deseja que suas alterações ocorram sem confirmação, na Etapa 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="e434a-209">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="e434a-210">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="e434a-210">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="e434a-211">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="e434a-211">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="set-up-a-rule-package"></a><span data-ttu-id="e434a-212">Configurar um pacote de regras</span><span class="sxs-lookup"><span data-stu-id="e434a-212">Set up a rule package</span></span>

1. <span data-ttu-id="e434a-213">Crie um pacote de regras no formato XML (com codificação Unicode), semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="e434a-213">Create a rule package in XML format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="e434a-214">(Você pode copiar, modificar e usar nosso exemplo.)</span><span class="sxs-lookup"><span data-stu-id="e434a-214">(You can copy, modify, and use our example.)</span></span>

      <span data-ttu-id="e434a-215">Ao configurar o seu pacote de regras, certifique-se de referenciar corretamente o arquivo .csv e o arquivo **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="e434a-215">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="e434a-216">Você pode copiar, modificar e usar nosso exemplo.</span><span class="sxs-lookup"><span data-stu-id="e434a-216">You can copy, modify, and use our example.</span></span> <span data-ttu-id="e434a-217">Neste exemplo de xml, os seguintes campos precisam ser personalizados para criar seu tipo confidencial do EDM:</span><span class="sxs-lookup"><span data-stu-id="e434a-217">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

      - <span data-ttu-id="e434a-218">**Id do RulePack e id ExactMatch**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) para gerar um GUID.</span><span class="sxs-lookup"><span data-stu-id="e434a-218">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

      - <span data-ttu-id="e434a-219">**Datastore**: este campo especifica o repositório de dados de pesquisa EDM a ser usado.</span><span class="sxs-lookup"><span data-stu-id="e434a-219">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="e434a-220">Forneça um nome de fonte de dados de um esquema EDM configurado.</span><span class="sxs-lookup"><span data-stu-id="e434a-220">You provide a data source name of a configured EDM Schema.</span></span>

      - <span data-ttu-id="e434a-221">**idMatch**: este campo aponta para o elemento principal do EDM.</span><span class="sxs-lookup"><span data-stu-id="e434a-221">**idMatch**: This field points to the primary element for EDM.</span></span>
        - <span data-ttu-id="e434a-222">Correspondências: especifica o campo a ser usado na pesquisa exata.</span><span class="sxs-lookup"><span data-stu-id="e434a-222">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="e434a-223">Forneça um nome de campo pesquisável no esquema EDM para o DataStore.</span><span class="sxs-lookup"><span data-stu-id="e434a-223">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
        - <span data-ttu-id="e434a-224">Classificação: este campo especifica a correspondência de tipo confidencial que dispara a pesquisa EDM.</span><span class="sxs-lookup"><span data-stu-id="e434a-224">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="e434a-225">Você pode fornecer o nome ou o GUID de uma classificação interna ou personalizada existente.</span><span class="sxs-lookup"><span data-stu-id="e434a-225">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

      - <span data-ttu-id="e434a-226">**Corresponder:** este campo aponta para evidências adicionais encontradas em proximidade do idMatch.</span><span class="sxs-lookup"><span data-stu-id="e434a-226">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
        - <span data-ttu-id="e434a-227">Correspondências: forneça o nome do campo no esquema EMD para DataStore.</span><span class="sxs-lookup"><span data-stu-id="e434a-227">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
      - <span data-ttu-id="e434a-228">**Recurso:** esta seção especifica o nome e a descrição do tipo confidencial em várias localidades.</span><span class="sxs-lookup"><span data-stu-id="e434a-228">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
        - <span data-ttu-id="e434a-229">idRef: forneça GUID para ExactMatch id.</span><span class="sxs-lookup"><span data-stu-id="e434a-229">idRef: You provide GUID for ExactMatch ID.</span></span>
        - <span data-ttu-id="e434a-230">Nomes e descrições: personalizar conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e434a-230">Name & descriptions: customize as required.</span></span>

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

1. <span data-ttu-id="e434a-231">Carregue o pacote de regras executando os seguintes cmdlets do PowerShell, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="e434a-231">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

      ```powershell
      $rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
      New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
      ```

<span data-ttu-id="e434a-232">Nesse ponto, você configurou a classificação baseada em EDM.</span><span class="sxs-lookup"><span data-stu-id="e434a-232">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="e434a-233">A próxima etapa é criar o hash dos dados confidenciais e carregar os hashes de indexação.</span><span class="sxs-lookup"><span data-stu-id="e434a-233">The next step is to hash the sensitive data, and then upload the hashes for indexing.</span></span>

<span data-ttu-id="e434a-234">Lembre-se do procedimento anterior onde o nosso esquema PatientRecords define cinco campos como pesquisáveis: *PatientID*, *MRN*, *SSN*, *Phone* e *DOB*.</span><span class="sxs-lookup"><span data-stu-id="e434a-234">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="e434a-235">Nosso pacote de regras de exemplo inclui esses campos e faz referência ao arquivo de esquema do banco de dados (**edm.xml**), com um item *ExactMatch* por campo pesquisável.</span><span class="sxs-lookup"><span data-stu-id="e434a-235">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* item per searchable field.</span></span> <span data-ttu-id="e434a-236">Considere o seguinte item ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="e434a-236">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="e434a-237">Nesse exemplo, observe que:</span><span class="sxs-lookup"><span data-stu-id="e434a-237">In this example, note that:</span></span>

- <span data-ttu-id="e434a-238">O nome do dataStore faz referência ao arquivo .csv que criamos anteriormente: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="e434a-238">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="e434a-239">O valor idMatch faz referência a um campo pesquisável listado no arquivo de esquema do banco de dados: **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="e434a-239">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="e434a-240">O valor de classificação faz referência a um tipo de informação confidencial existente ou personalizada: **classification = "Número de Seguridade Social dos EUA (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="e434a-240">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="e434a-241">(Nesse caso, usamos o tipo de informação confidencial existente do Número de Seguridade Social dos EUA.)</span><span class="sxs-lookup"><span data-stu-id="e434a-241">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="e434a-242">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="e434a-242">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="e434a-243">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="e434a-243">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="e434a-244">Editando o esquema para classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="e434a-244">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="e434a-245">Se você quiser fazer alterações em seu arquivo **edm.xml**, como alterar quais os campos usados para a classificação baseada em EDM, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e434a-245">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="e434a-246">Edite seu arquivo **edm.xml** (este é o arquivo discutido na seção [Definir o esquema](#define-the-schema-for-your-database-of-sensitive-information) deste artigo).</span><span class="sxs-lookup"><span data-stu-id="e434a-246">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="e434a-247">Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e434a-247">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

3. <span data-ttu-id="e434a-248">Para atualizar o seu esquema do banco de dados, execute os seguintes cmdlets, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="e434a-248">To update your database schema, run the following cmdlets, one at a time:</span></span>

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      <span data-ttu-id="e434a-249">Você será solicitado a confirmar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e434a-249">You will be prompted to confirm, as follows:</span></span>

      > <span data-ttu-id="e434a-250">Confirmar</span><span class="sxs-lookup"><span data-stu-id="e434a-250">Confirm</span></span>
      >
      > <span data-ttu-id="e434a-251">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="e434a-251">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="e434a-252">O esquema EDM para o repositório de dados 'patientrecords' será atualizado.</span><span class="sxs-lookup"><span data-stu-id="e434a-252">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
      >
      > <span data-ttu-id="e434a-253">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="e434a-253">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      > <span data-ttu-id="e434a-254">Se você quiser que suas alterações ocorram sem confirmação, na Etapa 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="e434a-254">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

      > [!NOTE]
      > <span data-ttu-id="e434a-255">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="e434a-255">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="e434a-256">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="e434a-256">The update must complete before you execute steps that use the additions.</span></span>

#### <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="e434a-257">Removendo o esquema para classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="e434a-257">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="e434a-258">(Conforme necessário) Se você quiser remover o esquema que está usando para classificação baseada em EDM, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e434a-258">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="e434a-259">Conectar ao centro de Conformidade e Segurança usando os procedimentos em [Conectar ao Centro de Conformidade e Segurança do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e434a-259">Connect to the Security & Compliance center using the procedures in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e434a-260">Execute os seguinte cmdlets do PowerShell, substituindo o nome do repositório de dados do "patient records" pelo nome que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="e434a-260">Run the following PowerShell cmdlets, substituting the data store name of "patient records" with the one you want to remove:</span></span>

      ```powershell
      Remove-DlpEdmSchema -Identity patientrecords
      ```

      <span data-ttu-id="e434a-261">Será solicitado que você confirme:</span><span class="sxs-lookup"><span data-stu-id="e434a-261">You will be prompted to confirm:</span></span>

      > <span data-ttu-id="e434a-262">Confirmar</span><span class="sxs-lookup"><span data-stu-id="e434a-262">Confirm</span></span>
      >
      > <span data-ttu-id="e434a-263">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="e434a-263">Are you sure you want to perform this action?</span></span>
      >
      > <span data-ttu-id="e434a-264">O esquema EDM para o repositório de dados 'patientrecords' será removido.</span><span class="sxs-lookup"><span data-stu-id="e434a-264">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
      >
      > <span data-ttu-id="e434a-265">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="e434a-265">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

      > [!TIP]
      >  <span data-ttu-id="e434a-266">Se você deseja que suas alterações ocorram sem confirmação, na Etapa 2, use este cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm: $ false</span><span class="sxs-lookup"><span data-stu-id="e434a-266">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>


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

### <a name="part-2-hash-and-upload-the-sensitive-data"></a><span data-ttu-id="e434a-267">Parte 2: hash e carregamento de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-267">Part 2: Hash and upload the sensitive data</span></span>

<span data-ttu-id="e434a-268">Nessa fase, você configura um grupo de segurança personalizado e uma conta de usuário, e configura a ferramenta do agente de carregamento do EDM.</span><span class="sxs-lookup"><span data-stu-id="e434a-268">In this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="e434a-269">Depois, use a ferramenta para o hash com valor salt dos dados confidenciais e carregue-los.</span><span class="sxs-lookup"><span data-stu-id="e434a-269">Then, you use the tool to hash with salt value the sensitive data, and upload it.</span></span>

<span data-ttu-id="e434a-270">O hash e o carregamento podem ser feitos usando um computador, ou você pode separar a etapa de hash da etapa de carregamento para obter mais segurança.</span><span class="sxs-lookup"><span data-stu-id="e434a-270">The hashing and uploading can be done using one computer or you can separate the hashing step from the upload step for greater security.</span></span>

<span data-ttu-id="e434a-271">Se você quiser usar o hash e carregá-los de um computador, será preciso fazer isso em um computador que possa se conectar diretamente ao seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e434a-271">If you want to hash and upload from one computer, you need to do it from a computer that can directly connect to your Microsoft 365 tenant.</span></span> <span data-ttu-id="e434a-272">Isso exige que os arquivos de dados confidenciais de texto sem formatação estejam no computador para hash.</span><span class="sxs-lookup"><span data-stu-id="e434a-272">This requires that your clear text sensitive data files are on that computer for hashing.</span></span>

<span data-ttu-id="e434a-273">Se você não quiser expor o seu arquivo de dados confidenciais de texto não criptografado, poderá hashá-lo em um computador em um local seguro e, em seguida, copiar o arquivo de hash e o arquivo salt para um computador que possa conectar-se diretamente ao locatário do Microsoft 365 para carregamento.</span><span class="sxs-lookup"><span data-stu-id="e434a-273">If you do not want to expose your clear text sensitive data file, you can hash it on a computer in a secure location and then copy the hash file and the salt file to a computer that can directly connect to your Microsoft 365 tenant for upload.</span></span> <span data-ttu-id="e434a-274">Neste cenário, você precisará do EDMUploadAgent em ambos os computadores.</span><span class="sxs-lookup"><span data-stu-id="e434a-274">In this scenario, you will need the EDMUploadAgent on both computers.</span></span> 

#### <a name="prerequisites"></a><span data-ttu-id="e434a-275">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e434a-275">Prerequisites</span></span>

- <span data-ttu-id="e434a-276">uma conta corporativa ou de estudante do Microsoft 365 que será adicionada ao grupo de segurança**EDM\_DataUploaders**</span><span class="sxs-lookup"><span data-stu-id="e434a-276">a work or school account for Microsoft 365  that will be added to the **EDM\_DataUploaders** security group</span></span>
- <span data-ttu-id="e434a-277">um computador com Windows 10 ou Windows Server 2016 com o .NET versão 4.6.2 para executar o EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="e434a-277">a Windows 10 or Windows Server 2016 machine with .NET version 4.6.2 for running the EDMUploadAgent</span></span>
- <span data-ttu-id="e434a-278">um diretório no computador de carregamento para o:</span><span class="sxs-lookup"><span data-stu-id="e434a-278">a directory on your upload machine for the:</span></span>
    -  <span data-ttu-id="e434a-279">EDMUploadAgent</span><span class="sxs-lookup"><span data-stu-id="e434a-279">EDMUploadAgent</span></span>
    - <span data-ttu-id="e434a-280">seu arquivo de item confidencial no formato cvs **PatientRecords.csv** em nossos exemplos</span><span class="sxs-lookup"><span data-stu-id="e434a-280">your sensitive item file in csv format **PatientRecords.csv** in our examples</span></span>
    -  <span data-ttu-id="e434a-281">os arquivos hash de saída e salt</span><span class="sxs-lookup"><span data-stu-id="e434a-281">and the output hash and salt files</span></span>
    - <span data-ttu-id="e434a-282">o nome do repositório de armazenamento do arquivo **edm.xml**, para esse exemplo, é `PatientRecords`</span><span class="sxs-lookup"><span data-stu-id="e434a-282">the datastore name from the **edm.xml** file, for this example its `PatientRecords`</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="e434a-283">Configuração do grupo de segurança e conta de usuário</span><span class="sxs-lookup"><span data-stu-id="e434a-283">Set up the security group and user account</span></span>

1. <span data-ttu-id="e434a-284">Como administrador global, vá para o centro de administração usando o [link apropriado para sua assinatura](#portal-links-for-your-subscription) e [crie um grupo de segurança](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) chamado **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="e434a-284">As a global administrator, go to the admin center using the appropriate [link for your subscription](#portal-links-for-your-subscription) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="e434a-285">Adicione um ou mais usuários ao grupo de segurança **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="e434a-285">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="e434a-286">(Esses usuários vão gerenciar o banco de dados de informações confidenciais.)</span><span class="sxs-lookup"><span data-stu-id="e434a-286">(These users will manage the database of sensitive information.)</span></span>

#### <a name="hash-and-upload-from-one-computer"></a><span data-ttu-id="e434a-287">Hash e carregamento de um computador</span><span class="sxs-lookup"><span data-stu-id="e434a-287">Hash and upload from one computer</span></span>

<span data-ttu-id="e434a-288">Esse computador deve ter acesso direto ao seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e434a-288">This computer must have direct access to your Microsoft 365 tenant.</span></span>

>[!NOTE]
> <span data-ttu-id="e434a-289">Antes de iniciar este procedimento, certifique-se de que você é membro do grupo de segurança **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="e434a-289">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group.</span></span>

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a><span data-ttu-id="e434a-290">Links para o agente de carregamento EDM por tipo de assinatura</span><span class="sxs-lookup"><span data-stu-id="e434a-290">Links to EDM upload agent by subscription type</span></span>

- [<span data-ttu-id="e434a-291">Comercial + GCC</span><span class="sxs-lookup"><span data-stu-id="e434a-291">Commercial + GCC</span></span>](https://go.microsoft.com/fwlink/?linkid=2088639)
- [<span data-ttu-id="e434a-292">GCC-High</span><span class="sxs-lookup"><span data-stu-id="e434a-292">GCC-High</span></span>](https://go.microsoft.com/fwlink/?linkid=2137521)
- [<span data-ttu-id="e434a-293">DoD</span><span class="sxs-lookup"><span data-stu-id="e434a-293">DoD</span></span>](https://go.microsoft.com/fwlink/?linkid=2137807)

1. <span data-ttu-id="e434a-294">Crie um diretório de trabalho para o EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="e434a-294">Create a working directory for the EDMUploadAgent.</span></span> <span data-ttu-id="e434a-295">Por exemplo, **C:\EDM\Data**.</span><span class="sxs-lookup"><span data-stu-id="e434a-295">For example, **C:\EDM\Data**.</span></span> <span data-ttu-id="e434a-296">Coloque o arquivo **PatientRecords.csv** lá.</span><span class="sxs-lookup"><span data-stu-id="e434a-296">Place the **PatientRecords.csv** file there.</span></span>

2. <span data-ttu-id="e434a-297">Baixar e instalar o apropriado [Agente de Carregamento EDM](#links-to-edm-upload-agent-by-subscription-type) para sua assinatura no diretório que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="e434a-297">Download and install the appropriate [EDM Upload Agent](#links-to-edm-upload-agent-by-subscription-type) for your subscription into the directory you created in step 1.</span></span>

> [!NOTE]
> <span data-ttu-id="e434a-298">O EDMUploadAgent nos links acima foi atualizado para adicionar automaticamente um valor salt aos dados do hash.</span><span class="sxs-lookup"><span data-stu-id="e434a-298">The EDMUploadAgent at the above links has been updated to automatically add a salt value to the hashed data.</span></span> <span data-ttu-id="e434a-299">Como alternativa, você pode fornecer seu próprio valor salt.</span><span class="sxs-lookup"><span data-stu-id="e434a-299">Alternately, you can provide your own salt value.</span></span> <span data-ttu-id="e434a-300">Depois de usar essa versão, não será possível usar a versão anterior do EDMUploadAgent.</span><span class="sxs-lookup"><span data-stu-id="e434a-300">Once you have used this version, you will not be able to use the previous version of the EDMUploadAgent.</span></span>
>
> <span data-ttu-id="e434a-301">Você pode carregar dados com o EDMUploadAgent para qualquer armazenamento de dados apenas duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="e434a-301">You can upload data with the EDMUploadAgent to any given data store only twice per day.</span></span>

> [!TIP]
> <span data-ttu-id="e434a-302">Para obter uma lista com os parâmetros de comando com suporte, execute o agente sem argumentos.</span><span class="sxs-lookup"><span data-stu-id="e434a-302">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="e434a-303">Por exemplo, ‘EdmUploadAgent.exe’.</span><span class="sxs-lookup"><span data-stu-id="e434a-303">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="e434a-304">Para autorizar o Agente de Carregamento EDM, abra o prompt de comando (como um administrador), mude para o diretório **C:\EDM\Data** e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="e434a-304">Authorize the EDM Upload Agent, open  Command Prompt window (as an administrator), switch to the **C:\EDM\Data** directory and then run the following command:</span></span>

   `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="e434a-305">Entre com sua conta empresarial ou de estudante do Microsoft 365 que foi adicionada ao grupo de segurança EDM_DataUploaders.</span><span class="sxs-lookup"><span data-stu-id="e434a-305">Sign in with your work or school account for Microsoft 365 that was added to the EDM_DataUploaders security group.</span></span> <span data-ttu-id="e434a-306">As informações do locatário são extraídas da conta do usuário para fazer a conexão.</span><span class="sxs-lookup"><span data-stu-id="e434a-306">Your tenant information is extracted from the user account to make the connection.</span></span>

4. <span data-ttu-id="e434a-307">Para criar o hash e carregar os dados confidenciais, execute o seguinte comando no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="e434a-307">To hash and upload the sensitive data, run the following command in Command Prompt window:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="e434a-308">Exemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="e434a-308">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="e434a-309">Isso adicionará automaticamente um valor salt gerado aleatoriamente ao hash para aumentar a segurança.</span><span class="sxs-lookup"><span data-stu-id="e434a-309">This will automatically add a randomly generated salt value to the hash for greater security.</span></span> <span data-ttu-id="e434a-310">Opcionalmente, se você quiser usar seu próprio valor salt, adicione o **/Salt <saltvalue>** ao comando.</span><span class="sxs-lookup"><span data-stu-id="e434a-310">Optionally, if you want to use your own salt value, add the **/Salt <saltvalue>** to the command.</span></span> <span data-ttu-id="e434a-311">Esse valor deve ter 64 caracteres de comprimento e só pode conter os caracteres de a-z e de 0-9.</span><span class="sxs-lookup"><span data-stu-id="e434a-311">This value must be 64 characters in length and can only contain the a-z characters and 0-9 characters.</span></span>

5. <span data-ttu-id="e434a-312">Verifique o status de carregamento executando este comando:</span><span class="sxs-lookup"><span data-stu-id="e434a-312">Check the upload status by running this command:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>`

<span data-ttu-id="e434a-313">Exemplo: **EdmUploadAgent.exe/GetSession/DataStoreName PatientRecords**</span><span class="sxs-lookup"><span data-stu-id="e434a-313">Example: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**</span></span>

<span data-ttu-id="e434a-314">Procure o status em **ProcessingInProgress**.</span><span class="sxs-lookup"><span data-stu-id="e434a-314">Look for the status to be in **ProcessingInProgress**.</span></span> <span data-ttu-id="e434a-315">Verifique novamente em alguns minutos até que o status mude para **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e434a-315">Check again every few minutes until the status changes to **Completed**.</span></span> <span data-ttu-id="e434a-316">Quando o status for concluído, os dados do EDM estarão prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="e434a-316">Once the status is completed, your EDM data is ready for use.</span></span>

#### <a name="separate-hash-and-upload"></a><span data-ttu-id="e434a-317">Separar hash e upload</span><span class="sxs-lookup"><span data-stu-id="e434a-317">Separate Hash and upload</span></span>

<span data-ttu-id="e434a-318">Execute o hash em um computador em um ambiente seguro.</span><span class="sxs-lookup"><span data-stu-id="e434a-318">Perform the hash on a computer in a secure environment.</span></span>

1. <span data-ttu-id="e434a-319">Execute os seguinte comando na janela prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="e434a-319">Run the following command in Command Prompt windows:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="e434a-320">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e434a-320">For example:</span></span>

> <span data-ttu-id="e434a-321">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span><span class="sxs-lookup"><span data-stu-id="e434a-321">**EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash**</span></span>

<span data-ttu-id="e434a-322">Isso gerará um arquivo de hash e um arquivo salt com essas extensões, caso você não tenha especificado a opção **/Salt <saltvalue>**:</span><span class="sxs-lookup"><span data-stu-id="e434a-322">This will output a hashed file and a salt file with these extensions if you didn't specify the **/Salt <saltvalue>** option:</span></span>
- <span data-ttu-id="e434a-323">.EdmHash</span><span class="sxs-lookup"><span data-stu-id="e434a-323">.EdmHash</span></span>
- <span data-ttu-id="e434a-324">.EdmSalt</span><span class="sxs-lookup"><span data-stu-id="e434a-324">.EdmSalt</span></span>

2. <span data-ttu-id="e434a-325">Copie esses arquivos de forma segura para o computador que você usará para carregar seu arquivo cvs de itens confidenciais (PatientRecords) para o seu locatário.</span><span class="sxs-lookup"><span data-stu-id="e434a-325">Copy these files in a secure fashion to the computer you will use to upload your sensitive items csv file (PatientRecords) to your tenant.</span></span>

<span data-ttu-id="e434a-326">Para carregar os dados com hash, execute o seguinte comando no prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="e434a-326">To upload the hashed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="e434a-327">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e434a-327">For example:</span></span>

> <span data-ttu-id="e434a-328">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="e434a-328">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>


<span data-ttu-id="e434a-329">Para verificar se os dados confidenciais foram carregados, execute o seguinte comando na janela do prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="e434a-329">To verify that your sensitive data has been uploaded, run the following command in Command Prompt window:</span></span>


`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="e434a-330">Você verá uma lista de armazenamento de dados e a data da última atualização.</span><span class="sxs-lookup"><span data-stu-id="e434a-330">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="e434a-331">Se você quiser ver todos os carregamentos de dados em um determinado armazenamento, execute o seguinte comando em um prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="e434a-331">If you want to see all the data uploads to a particular store, run the following command in a Windows command prompt:</span></span>

`EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>`

<span data-ttu-id="e434a-332">Prossiga para configurar seu processo e agenda da [Atualização de banco de dados de informação confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="e434a-332">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="e434a-333">Nesse ponto, você já usou a classificação baseada em EDM com os serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e434a-333">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="e434a-334">Por exemplo, você pode [configurar uma política usando a classificação baseada em EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="e434a-334">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="e434a-335">Atualização do banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-335">Refreshing your sensitive information database</span></span>

<span data-ttu-id="e434a-336">Você pode atualizar seu banco de dados confidenciais diariamente, e a ferramenta de carregamento do EDM pode reindexar os dados confidenciais e depois recarregar os dados indexados.</span><span class="sxs-lookup"><span data-stu-id="e434a-336">You can refresh your sensitive information database daily, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="e434a-337">Determine seu processo e a frequência (diariamente ou semanalmente) para atualização do banco de dados de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="e434a-337">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="e434a-338">Exporte novamente os dados confidenciais para um aplicativo, como o Microsoft Excel, e salve o arquivo no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="e434a-338">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="e434a-339">Mantenha o mesmo nome de arquivo e local que você usou quando seguiu as etapas descritas em [Hash e upload de dados confidenciais](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="e434a-339">Keep the same file name and location you used when you followed the steps described in [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data).</span></span>

      > [!NOTE]
      > <span data-ttu-id="e434a-340">Se não houver alterações na estrutura (nomes de campos) do arquivo .csv, você não precisará fazer alterações no arquivo de esquema do banco de dados ao atualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="e434a-340">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="e434a-341">Mas se for necessário fazer alterações, não deixe de editar o esquema de banco de dados e seu pacote de regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="e434a-341">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="e434a-342">Use o [Agendador de tarefas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar as etapas 2 e 3 no procedimento [Hash e fazer upload dos dados confidenciais](#part-2-hash-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="e434a-342">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Hash and upload the sensitive data](#part-2-hash-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="e434a-343">Você pode agendar tarefas usando vários métodos:</span><span class="sxs-lookup"><span data-stu-id="e434a-343">You can schedule tasks using several methods:</span></span>

      | <span data-ttu-id="e434a-344">Método</span><span class="sxs-lookup"><span data-stu-id="e434a-344">Method</span></span>             | <span data-ttu-id="e434a-345">O que fazer</span><span class="sxs-lookup"><span data-stu-id="e434a-345">What to do</span></span> |
      | ---------------------- | ---------------- |
      | <span data-ttu-id="e434a-346">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e434a-346">Windows PowerShell</span></span>     | <span data-ttu-id="e434a-347">Confira a documentação do [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) e o [exemplo do script do PowerShell](#example-powershell-script-for-task-scheduler) neste artigo</span><span class="sxs-lookup"><span data-stu-id="e434a-347">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
      | <span data-ttu-id="e434a-348">API do Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="e434a-348">Task Scheduler API</span></span>     | <span data-ttu-id="e434a-349">Confira a documentação do [Agendador de tarefas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler)</span><span class="sxs-lookup"><span data-stu-id="e434a-349">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
      | <span data-ttu-id="e434a-350">Interface do usuário do Windows</span><span class="sxs-lookup"><span data-stu-id="e434a-350">Windows user interface</span></span> | <span data-ttu-id="e434a-351">No Windows, clique em **Iniciar** e digite Agendador de tarefas.</span><span class="sxs-lookup"><span data-stu-id="e434a-351">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="e434a-352">Em seguida, na lista de resultados, clique com o botão direito do mouse no **Agendador de Tarefas**, e escolha **executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e434a-352">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="e434a-353">Exemplo de script do PowerShell para o Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="e434a-353">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="e434a-354">Esta seção inclui um exemplo de script do PowerShell que você pode usar para agendar as tarefas de dados de hash e para carregamento de dados com hash:</span><span class="sxs-lookup"><span data-stu-id="e434a-354">This section includes an example PowerShell script you can use to schedule your tasks for hashing data and uploading the hashed data:</span></span>

##### <a name="to-schedule-hashing-and-upload-in-a-combined-step"></a><span data-ttu-id="e434a-355">Para agendar o hash e carregamento em uma etapa combinada</span><span class="sxs-lookup"><span data-stu-id="e434a-355">To schedule hashing and upload in a combined step</span></span>

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

#### <a name="to-schedule-hashing-and-upload-as-separate-steps"></a><span data-ttu-id="e434a-356">Para agendar o hash e carregamento em etapas separadas</span><span class="sxs-lookup"><span data-stu-id="e434a-356">To schedule hashing and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="e434a-357">Parte 3: uso da classificação baseada em EDM com os serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e434a-357">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="e434a-358">Estes locais são compatíveis com os tipos de informações confidenciais do EDM:</span><span class="sxs-lookup"><span data-stu-id="e434a-358">These locations are support EDM sensitive information types:</span></span>

- <span data-ttu-id="e434a-359">DLP para Exchange Online (email)</span><span class="sxs-lookup"><span data-stu-id="e434a-359">DLP for Exchange Online (email)</span></span>
- <span data-ttu-id="e434a-360">OneDrive for Business (arquivos)</span><span class="sxs-lookup"><span data-stu-id="e434a-360">OneDrive for Business (files)</span></span>
- <span data-ttu-id="e434a-361">Microsoft Teams (conversas)</span><span class="sxs-lookup"><span data-stu-id="e434a-361">Microsoft Teams (conversations)</span></span>
- <span data-ttu-id="e434a-362">DLP para SharePoint (arquivos)</span><span class="sxs-lookup"><span data-stu-id="e434a-362">DLP for SharePoint (files)</span></span>
- <span data-ttu-id="e434a-363">Políticas DLP de Segurança de Aplicativos do Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="e434a-363">Microsoft Cloud App Security DLP policies</span></span>

<span data-ttu-id="e434a-364">Os tipos de informações confidenciais do EDM para os cenários a seguir estão em desenvolvimento, mas ainda não estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e434a-364">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="e434a-365">Classificação automática de rótulos de confidencialidade e rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="e434a-365">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="e434a-366">Criação de uma política DLP com o EDM</span><span class="sxs-lookup"><span data-stu-id="e434a-366">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="e434a-367">Vá para o Centro de Conformidade e Segurança usando o apropriado [link para sua assinatura](#portal-links-for-your-subscription).</span><span class="sxs-lookup"><span data-stu-id="e434a-367">Go to the Security & Compliance Center using the appropriate [link for your subscription](#portal-links-for-your-subscription).</span></span>

2. <span data-ttu-id="e434a-368">Escolha a **Política**\>**de prevenção contra perda de dados**.</span><span class="sxs-lookup"><span data-stu-id="e434a-368">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="e434a-369">Escolha **Criar uma política**\>**Personalizada**\>**Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e434a-369">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="e434a-370">Na guia **Nomear sua política**, especifique um nome e uma descrição e, em seguida, escolha **Próximo**. </span><span class="sxs-lookup"><span data-stu-id="e434a-370">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="e434a-371">Na guia **Escolher locais**, clique em **Escolher locais específicos** e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e434a-371">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="e434a-372">Na coluna **Status**, selecione **Trocar email, contas do OneDrive, chats do Teams e mensagem do canal**, e escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e434a-372">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span>

7. <span data-ttu-id="e434a-373">Na guia **Configurações de política**, escolha **Usar configurações avançadas** e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e434a-373">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="e434a-374">Escolha **+ Nova regra**.</span><span class="sxs-lookup"><span data-stu-id="e434a-374">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="e434a-375">Na seção **Nome**, especifique um nome e uma descrição para a regra.</span><span class="sxs-lookup"><span data-stu-id="e434a-375">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="e434a-376">Na seção **Condições**, na lista **+ Adicionar uma condição**, escolha **Conteúdo contém tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="e434a-376">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span>

      ![O conteúdo contém tipos de informações confidenciais](../media/edm-dlp-newrule-conditions.png)

11. <span data-ttu-id="e434a-378">Pesquise pelo tipo de informação confidencial que você criou ao configurar o pacote de regras e, em seguida, escolha **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e434a-378">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="e434a-379">Então escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e434a-379">Then choose **Done**.</span></span>

12. <span data-ttu-id="e434a-380">Termine de selecionar as opções para a regra, como **Notificações de usuário**, **Substituições do usuário**, **Relatórios de incidente**, e assim por diante, e depois clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e434a-380">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="e434a-381">Na guia **Configurações de política**, revise suas regras e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e434a-381">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="e434a-382">Especifique se deseja ativar a política imediatamente, testá-la ou desativá-la.</span><span class="sxs-lookup"><span data-stu-id="e434a-382">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="e434a-383">Depois clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e434a-383">Then choose **Next**.</span></span>

15. <span data-ttu-id="e434a-384">Na guia **Revisar suas configurações**, revise sua política.</span><span class="sxs-lookup"><span data-stu-id="e434a-384">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="e434a-385">Faça todas as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="e434a-385">Make any needed changes.</span></span> <span data-ttu-id="e434a-386">Quando concluir, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="e434a-386">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="e434a-387">Espere aproximadamente uma hora para sua nova política DLP funcionar em seu data center.</span><span class="sxs-lookup"><span data-stu-id="e434a-387">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e434a-388">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="e434a-388">Related articles</span></span>

- [<span data-ttu-id="e434a-389">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-389">Sensitive information type-entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="e434a-390">Tipos personalizados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="e434a-390">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)
- [<span data-ttu-id="e434a-391">Visão geral das políticas DLP</span><span class="sxs-lookup"><span data-stu-id="e434a-391">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="e434a-392">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e434a-392">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)
- [<span data-ttu-id="e434a-393">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="e434a-393">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-dlpedmschema)

