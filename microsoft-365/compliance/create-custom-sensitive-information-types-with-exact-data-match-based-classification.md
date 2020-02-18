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
description: Criar tipos personalizados de informações confidenciais com classificação baseada em Exact Data Match.
ms.openlocfilehash: 044801416c7db4ddec8936a496862c432a63acde
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42077589"
---
# <a name="create-custom-sensitive-information-types-with-exact-data-match-based-classification"></a><span data-ttu-id="26f76-103">Criar tipos personalizados de informações confidenciais com classificação baseada em Exact Data Match</span><span class="sxs-lookup"><span data-stu-id="26f76-103">Create custom sensitive information types with Exact Data Match based classification</span></span>

## <a name="overview"></a><span data-ttu-id="26f76-104">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="26f76-104">Overview</span></span>

<span data-ttu-id="26f76-105">[Tipos personalizados de informações confidenciais](custom-sensitive-info-types.md)  são usados para ajudar a prevenir o compartilhamento acidental ou inadequado de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="26f76-105">[Custom sensitive information types](custom-sensitive-info-types.md) are used to help prevent inadvertent or inappropriate sharing of sensitive information.</span></span> <span data-ttu-id="26f76-106">Como administrador, você pode usar o [Centro de Conformidade e Segurança](create-a-custom-sensitive-information-type.md) ou [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) para definir um tipo personalizado de informação baseado em padrões, evidências (palavras-chave como *funcionário*, *crachá*, *ID* e assim por diante), proximidade de caractere (quão próxima a evidência está dos caracteres em um padrão específico) e níveis de confiança.</span><span class="sxs-lookup"><span data-stu-id="26f76-106">As an administrator, you can use the [Security & Compliance Center](create-a-custom-sensitive-information-type.md) or [PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md) to define a custom sensitive information type based on patterns, evidence (keywords such as *employee*, *badge*, *ID*, and so on), character proximity (how close evidence is to characters in a particular pattern), and confidence levels.</span></span> <span data-ttu-id="26f76-107">Esses tipos personalizados de informações confidenciais atendem às necessidades comerciais de várias organizações.</span><span class="sxs-lookup"><span data-stu-id="26f76-107">Such custom sensitive information types meet business needs for many organizations.</span></span>

<span data-ttu-id="26f76-108">Mas e se você quiser um tipo personalizado de informações confidenciais que usa valores de dados exatos, em vez de corresponder apenas a padrões genéricos?</span><span class="sxs-lookup"><span data-stu-id="26f76-108">But what if you wanted a custom sensitive information type that uses exact data values, instead of matching only with generic patterns?</span></span> <span data-ttu-id="26f76-109">Com a classificação baseada em Exact Data Match (EDM), você pode criar um tipo personalizado de informações confidenciais que é criada para:</span><span class="sxs-lookup"><span data-stu-id="26f76-109">With Exact Data Match (EDM)-based classification, you can create a custom sensitive information type that is designed to:</span></span>

- <span data-ttu-id="26f76-110">ser dinâmico e atualizável.</span><span class="sxs-lookup"><span data-stu-id="26f76-110">be dynamic and refreshable;</span></span>
- <span data-ttu-id="26f76-111">ser mais escalonável;</span><span class="sxs-lookup"><span data-stu-id="26f76-111">be more scalable;</span></span>
- <span data-ttu-id="26f76-112">resultar em menos falso positivos.</span><span class="sxs-lookup"><span data-stu-id="26f76-112">result in fewer false-positives;</span></span>
- <span data-ttu-id="26f76-113">trabalhar com dados confidenciais estruturados;</span><span class="sxs-lookup"><span data-stu-id="26f76-113">work with structured sensitive data;</span></span>
- <span data-ttu-id="26f76-114">lidar com as informações confidenciais com mais segurança; e</span><span class="sxs-lookup"><span data-stu-id="26f76-114">handle sensitive information more securely; and</span></span>
- <span data-ttu-id="26f76-115">ser usado com vários serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26f76-115">be used with several Microsoft cloud services.</span></span>

![Classificação baseada em EDM](../media/EDMClassification.png)

<span data-ttu-id="26f76-117">A classificação baseada no EDM permite criar tipos personalizados de informações confidenciais que fazem referência a valores exatos em um banco de dados de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="26f76-117">EDM-based classification enables you to create custom sensitive information types that refer to exact values in a database of sensitive information.</span></span> <span data-ttu-id="26f76-118">O banco de dados pode ser atualizado diariamente ou semanalmente, e pode conter até 10 milhões linhas de dados.</span><span class="sxs-lookup"><span data-stu-id="26f76-118">The database can be refreshed daily or weekly, and it can contain up to 10 million rows of data.</span></span> <span data-ttu-id="26f76-119">Assim como funcionários, pacientes ou clientes vêm e vão e os registros são alterados, os tipos personalizados de informações confidenciais permanecem atualizados e aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="26f76-119">So as employees, patients, or clients come and go, and records change, your custom sensitive information types remain current and applicable.</span></span> <span data-ttu-id="26f76-120">Você também pode usar a classificação baseada em EDM com políticas, como [políticas de prevenção contra perda de dados](data-loss-prevention-policies.md) (DLP) ou políticas de arquivo do [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span><span class="sxs-lookup"><span data-stu-id="26f76-120">And, you can use EDM-based classification with policies, such as [data loss prevention policies](data-loss-prevention-policies.md) (DLP) or [Microsoft Cloud App Security file policies](https://docs.microsoft.com/cloud-app-security/data-protection-policies).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="26f76-121">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="26f76-121">Required licenses and permissions</span></span>

<span data-ttu-id="26f76-122">Você deve ser um administrador global, administrador de conformidade ou administrador do Exchange Online para executar as tarefas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="26f76-122">You must be a global admin, compliance administrator, or Exchange Online administrator to perform the tasks described in this article.</span></span> <span data-ttu-id="26f76-123">Para saber mais sobre permissões DLP, consulte [Permissões](data-loss-prevention-policies.md#permissions).</span><span class="sxs-lookup"><span data-stu-id="26f76-123">To learn more about DLP permissions, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

<span data-ttu-id="26f76-124">Quando estiver disponível para o público geral, a classificação baseada em EDM será incluída nessas assinaturas</span><span class="sxs-lookup"><span data-stu-id="26f76-124">When generally available, EDM-based classification will be included in these subscriptions</span></span>

- <span data-ttu-id="26f76-125">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="26f76-125">Office 365 E5</span></span>
- <span data-ttu-id="26f76-126">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="26f76-126">Microsoft 365 E5</span></span>
- <span data-ttu-id="26f76-127">Proteção de Informações e Conformidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26f76-127">Microsoft 365 Information Protection and Compliance</span></span>
- <span data-ttu-id="26f76-128">Conformidade Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="26f76-128">Office 365 Advanced Compliance</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="26f76-129">Visão geral do fluxo de trabalho </span><span class="sxs-lookup"><span data-stu-id="26f76-129">The work flow at a glance</span></span>

|<span data-ttu-id="26f76-130">Fase</span><span class="sxs-lookup"><span data-stu-id="26f76-130">Phase</span></span>  |<span data-ttu-id="26f76-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26f76-131">What's needed</span></span>  |
|---------|---------|
|[<span data-ttu-id="26f76-132">Parte 1: Configuração da classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="26f76-132">Part 1: Set up EDM-based classification</span></span>](#part-1-set-up-edm-based-classification)<br/><br/><span data-ttu-id="26f76-133">(conforme o necessário)</span><span class="sxs-lookup"><span data-stu-id="26f76-133">(As needed)</span></span><br/><span data-ttu-id="26f76-134">- [Edite o Esquema de Banco de Dados](#editing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="26f76-134">- [Edit the database schema](#editing-the-schema-for-edm-based-classification)</span></span> <br/><span data-ttu-id="26f76-135">- [Remova o esquema](#removing-the-schema-for-edm-based-classification)</span><span class="sxs-lookup"><span data-stu-id="26f76-135">- [Remove the schema](#removing-the-schema-for-edm-based-classification)</span></span> |<span data-ttu-id="26f76-136">– Acesso de leitura aos dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-136">- Read access to the sensitive data</span></span><br/><span data-ttu-id="26f76-137">– Esquema de banco de dados no formato. XML (exemplo fornecido)</span><span class="sxs-lookup"><span data-stu-id="26f76-137">- Database schema in .xml format (example provided)</span></span><br/><span data-ttu-id="26f76-138">– Pacote de regras no formato. XML (exemplo fornecido)</span><span class="sxs-lookup"><span data-stu-id="26f76-138">- Rule package in .xml format (example provided)</span></span><br/><span data-ttu-id="26f76-139">– Permissões de administrador ao Centro de Conformidade e Segurança (usando o PowerShell)</span><span class="sxs-lookup"><span data-stu-id="26f76-139">- Admin permissions to the Security & Compliance Center (using PowerShell)</span></span> |
|[<span data-ttu-id="26f76-140">Parte 2: indexação e carregamento de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-140">Part 2: Index and upload the sensitive data</span></span>](#part-2-index-and-upload-the-sensitive-data)<br/><br/><span data-ttu-id="26f76-141">(conforme o necessário)</span><span class="sxs-lookup"><span data-stu-id="26f76-141">(As needed)</span></span><br/>[<span data-ttu-id="26f76-142">Atualize os dados</span><span class="sxs-lookup"><span data-stu-id="26f76-142">Refresh the data</span></span>](#refreshing-your-sensitive-information-database) |<span data-ttu-id="26f76-143">– Grupo de segurança personalizado e conta de usuário</span><span class="sxs-lookup"><span data-stu-id="26f76-143">- Custom security group and user account</span></span><br/><span data-ttu-id="26f76-144">– Acesso de administrador local à máquina com o agente de carregamento do EDM</span><span class="sxs-lookup"><span data-stu-id="26f76-144">- Local admin access to machine with EDM Upload Agent</span></span><br/><span data-ttu-id="26f76-145">– Acesso de leitura aos dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-145">- Read access to the sensitive data</span></span><br/><span data-ttu-id="26f76-146">– Processar e agendar a atualização de dados</span><span class="sxs-lookup"><span data-stu-id="26f76-146">- Process and schedule for refreshing the data</span></span>|
|[<span data-ttu-id="26f76-147">Parte 3: uso da classificação baseada em EDM com os serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="26f76-147">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>](#part-3-use-edm-based-classification-with-your-microsoft-cloud-services) |<span data-ttu-id="26f76-148">– Assinatura do Office 365 com DLP</span><span class="sxs-lookup"><span data-stu-id="26f76-148">- Office 365 subscription with DLP</span></span><br/><span data-ttu-id="26f76-149">– Recurso de classificação baseada em EDM habilitado</span><span class="sxs-lookup"><span data-stu-id="26f76-149">- EDM-based classification feature enabled</span></span> |

### <a name="part-1-set-up-edm-based-classification"></a><span data-ttu-id="26f76-150">Parte 1: Configuração da classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="26f76-150">Part 1: Set up EDM-based classification</span></span>

<span data-ttu-id="26f76-151">Definição e configuração da classificação baseada em EDM envolve o salvamento de dados confidenciais no formato .csv, a definição de um esquema para seu banco de dados de informações confidenciais, a criação de um pacote de regras e o carregamento do esquema e do pacote de regras.</span><span class="sxs-lookup"><span data-stu-id="26f76-151">Setting up and configuring EDM-based classification involves saving sensitive data in .csv format, defining a schema for your database of sensitive information, creating a rule package, and then uploading the schema and rule package.</span></span>

#### <a name="define-the-schema-for-your-database-of-sensitive-information"></a><span data-ttu-id="26f76-152">Definição do esquema para seu banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-152">Define the schema for your database of sensitive information</span></span>

1. <span data-ttu-id="26f76-153">Identifique as informações confidenciais que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="26f76-153">Identify the sensitive information you want to use.</span></span> <span data-ttu-id="26f76-154">Exporte os dados para um aplicativo, como o Microsoft Excel, e salve o arquivo no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="26f76-154">Export the data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="26f76-155">O arquivo de dados pode incluir um máximo de:</span><span class="sxs-lookup"><span data-stu-id="26f76-155">The data file can include a maximum of:</span></span>
      - <span data-ttu-id="26f76-156">Até 10 milhões linhas de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-156">Up to 10 million rows of sensitive data</span></span>
      - <span data-ttu-id="26f76-157">Até 32 colunas (campos) por fonte de dados</span><span class="sxs-lookup"><span data-stu-id="26f76-157">Up to 32 columns (fields) per data source</span></span>
      - <span data-ttu-id="26f76-158">Até 5 colunas (campos) marcadas como pesquisáveis</span><span class="sxs-lookup"><span data-stu-id="26f76-158">Up to 5 columns (fields) marked as searchable</span></span>

2. <span data-ttu-id="26f76-159">Estruture os dados confidenciais no arquivo .csv, de modo que a primeira linha inclui os nomes dos campos usados na classificação baseada em EDM.</span><span class="sxs-lookup"><span data-stu-id="26f76-159">Structure the sensitive data in the .csv file such that the first row includes the names of the fields used for EDM-based classification.</span></span> <span data-ttu-id="26f76-160">Você pode ter nomes de campo no arquivo .csv, como "CPF", "data de nascimento", "nome", "sobrenome" e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="26f76-160">In your .csv file, you might have field names, such as "ssn", "birthdate", "firstname", "lastname", and so on.</span></span> <span data-ttu-id="26f76-161">Por exemplo, o arquivo .csv é chamado  *PatientRecords.csv*, e suas colunas incluem  *PatientID*, *Número de prontuário médico*, *Sobrenome*, *Nome*, *CPF*  e mais.</span><span class="sxs-lookup"><span data-stu-id="26f76-161">As an example, our .csv file is called *PatientRecords.csv*, and its columns include *PatientID*, *MRN*, *LastName*, *FirstName*, *SSN* and more.</span></span>

3. <span data-ttu-id="26f76-162">Defina o esquema para o banco de dados de informações confidenciais no formato .xml (semelhante ao nosso exemplo a seguir).</span><span class="sxs-lookup"><span data-stu-id="26f76-162">Define the schema for the database of sensitive information in .xml format (similar to our example below).</span></span> <span data-ttu-id="26f76-163">Nomeie esse esquema do arquivo **edm.xml** e configure-o para cada coluna no banco de dados, há uma linha que usa a sintaxe:</span><span class="sxs-lookup"><span data-stu-id="26f76-163">Name this schema file **edm.xml**, and configure it such that for each column in the database, there is a line that uses the syntax:</span></span> 

<span data-ttu-id="26f76-164">`\<Field name="" searchable=""/\>`.</span><span class="sxs-lookup"><span data-stu-id="26f76-164">`\<Field name="" searchable=""/\>`.</span></span>

- <span data-ttu-id="26f76-165">Use nomes de coluna para valores de *Nome do campo* .</span><span class="sxs-lookup"><span data-stu-id="26f76-165">Use column names for *Field name* values.</span></span>
- <span data-ttu-id="26f76-166">Use  *searchable="true"*  para até 5 campos pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="26f76-166">Use *searchable="true"* for the fields that you want to be searchable up to a maximum of 5 fields.</span></span> <span data-ttu-id="26f76-167">Você deve designar pelo menos um campo como pesquisável.</span><span class="sxs-lookup"><span data-stu-id="26f76-167">You must designate a minimum of one field as searchable.</span></span>

<span data-ttu-id="26f76-168">Por exemplo, o arquivo .xml a seguir define o esquema para um banco de dados de registros de paciente, com cinco campos especificados como pesquisáveis:  *PatientID*, *Número de prontuário médico*, *CPF*, *Telefone*e  *Data de nascimento*.</span><span class="sxs-lookup"><span data-stu-id="26f76-168">As an example, the following .xml file defines the schema for a patient records database, with five fields specified as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span>

<span data-ttu-id="26f76-169">(Você pode copiar, modificar e usar nosso exemplo.)</span><span class="sxs-lookup"><span data-stu-id="26f76-169">(You can copy, modify, and use our example.)</span></span>

 ```xml
<EdmSchema xmlns="https://schemas.microsoft.com/office/2018/edm">
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

4. <span data-ttu-id="26f76-170">[Conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="26f76-170">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

5. <span data-ttu-id="26f76-171">Para carregar o esquema do banco de dados, execute os seguintes cmdlets, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="26f76-171">To upload the database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
New-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="26f76-172">Você será solicitado a confirmar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="26f76-172">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="26f76-173">Confirmar</span><span class="sxs-lookup"><span data-stu-id="26f76-173">Confirm</span></span>
>
> <span data-ttu-id="26f76-174">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="26f76-174">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="26f76-175">O novo esquema EDM para o repositório de dado 'patientrecords' será importado.</span><span class="sxs-lookup"><span data-stu-id="26f76-175">New EDM Schema for the data store 'patientrecords' will be imported.</span></span>
>
> <span data-ttu-id="26f76-176">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="26f76-176">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="26f76-177">Se você quiser que as suas alterações ocorram sem confirmação, na Etapa 5, use este cmdlet: New-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="26f76-177">If you want your changes to occur without confirmation, in Step 5, use this cmdlet instead: New-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="26f76-178">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="26f76-178">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="26f76-179">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="26f76-179">The update must complete before you execute steps that use the additions.</span></span>

<span data-ttu-id="26f76-180">Agora que o esquema para o seu banco de dados de informações confidenciais está definido, a próxima etapa é configurar um pacote de regras.</span><span class="sxs-lookup"><span data-stu-id="26f76-180">Now that the schema for your database of sensitive information is defined, the next step is to set up a rule package.</span></span> <span data-ttu-id="26f76-181">Continue na seção [Configurar um pacote de regras](#set-up-a-rule-package).</span><span class="sxs-lookup"><span data-stu-id="26f76-181">Proceed to the section [Set up a rule package](#set-up-a-rule-package).</span></span>

#### <a name="editing-the-schema-for-edm-based-classification"></a><span data-ttu-id="26f76-182">Editando o esquema para classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="26f76-182">Editing the schema for EDM-based classification</span></span>

<span data-ttu-id="26f76-183">Se você quiser fazer alterações em seu arquivo **edm.xml**, como alterar quais os campos usados para a classificação baseada em EDM, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="26f76-183">If you want to make changes to your **edm.xml** file, such as changing which fields are used for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="26f76-184">Edite o seu arquivo **edm.xml** (este é o arquivo discutido na seção [Definir o esquema](#define-the-schema-for-your-database-of-sensitive-information)  deste artigo).</span><span class="sxs-lookup"><span data-stu-id="26f76-184">Edit your **edm.xml** file (this is the file discussed in the [Define the schema](#define-the-schema-for-your-database-of-sensitive-information) section of this article).</span></span>

2. <span data-ttu-id="26f76-185">[Conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="26f76-185">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="26f76-186">Para atualizar o seu esquema do banco de dados, execute os seguintes cmdlets, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="26f76-186">To update your database schema, run the following cmdlets, one at a time:</span></span>

```powershell
$edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
```

<span data-ttu-id="26f76-187">Você será solicitado a confirmar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="26f76-187">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="26f76-188">Confirmar</span><span class="sxs-lookup"><span data-stu-id="26f76-188">Confirm</span></span>
>
> <span data-ttu-id="26f76-189">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="26f76-189">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="26f76-190">O esquema EDM para o repositório de dados 'patientrecords' será atualizado.</span><span class="sxs-lookup"><span data-stu-id="26f76-190">EDM Schema for the data store 'patientrecords' will be updated.</span></span>
>
> <span data-ttu-id="26f76-191">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="26f76-191">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
> <span data-ttu-id="26f76-192">Se você quiser que as suas alterações ocorram sem confirmação, na Etapa 3, use este cmdlet: Set-DlpEdmSchema -FileData $edmSchemaXml</span><span class="sxs-lookup"><span data-stu-id="26f76-192">If you want your changes to occur without confirmation, in Step 3, use this cmdlet instead: Set-DlpEdmSchema -FileData $edmSchemaXml</span></span>

> [!NOTE]
> <span data-ttu-id="26f76-193">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="26f76-193">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="26f76-194">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="26f76-194">The update must complete before you execute steps that use the additions.</span></span>

## <a name="removing-the-schema-for-edm-based-classification"></a><span data-ttu-id="26f76-195">Removendo o esquema para classificação baseada em EDM</span><span class="sxs-lookup"><span data-stu-id="26f76-195">Removing the schema for EDM-based classification</span></span>

<span data-ttu-id="26f76-196">(Conforme necessário) Se você quiser remover o esquema que está usando para classificação baseada em EDM, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="26f76-196">(As needed) If you want to remove the schema you're using for EDM-based classification, follow these steps:</span></span>

1. <span data-ttu-id="26f76-197">[Conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="26f76-197">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="26f76-198">Execute os seguinte cmdlets do PowerShell, substituindo o nome do repositório de dados de "patientrecords" pelo nome que você deseja remover:</span><span class="sxs-lookup"><span data-stu-id="26f76-198">Run the following PowerShell cmdlets, substituting the data store name of "patientrecords" with the one you want to remove:</span></span>

```powershell
Remove-DlpEdmSchema -Identity patientrecords
```

<span data-ttu-id="26f76-199">Você será solicitado a confirmar da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="26f76-199">You will be prompted to confirm, as follows:</span></span>

> <span data-ttu-id="26f76-200">Confirmar</span><span class="sxs-lookup"><span data-stu-id="26f76-200">Confirm</span></span>
>
> <span data-ttu-id="26f76-201">Tem certeza que deseja executar essa ação?</span><span class="sxs-lookup"><span data-stu-id="26f76-201">Are you sure you want to perform this action?</span></span>
>
> <span data-ttu-id="26f76-202">O esquema EDM para o repositório de dados 'patientrecords' será removido.</span><span class="sxs-lookup"><span data-stu-id="26f76-202">EDM Schema for the data store 'patientrecords' will be removed.</span></span>
>
> <span data-ttu-id="26f76-203">\[S\] Sim \[A\] Sim para Todos \[N\] Não \[L\] Não para Todos \[?\] Ajuda (padrão é “Y”):</span><span class="sxs-lookup"><span data-stu-id="26f76-203">\[Y\] Yes \[A\] Yes to All \[N\] No \[L\] No to All \[?\] Help (default is "Y"):</span></span>

> [!TIP]
>  <span data-ttu-id="26f76-204">Se você quiser que as alterações ocorram sem confirmação, na Etapa 2, use este cmdlet: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span><span class="sxs-lookup"><span data-stu-id="26f76-204">If you want your changes to occur without confirmation, in Step 2, use this cmdlet instead: Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false</span></span>

### <a name="set-up-a-rule-package"></a><span data-ttu-id="26f76-205">Configurar um pacote de regras</span><span class="sxs-lookup"><span data-stu-id="26f76-205">Set up a rule package</span></span>

1. <span data-ttu-id="26f76-206">Crie um pacote de regras no formato .xml (com codificação Unicode), semelhante ao exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="26f76-206">Create a rule package in .xml format (with Unicode encoding), similar to the following example.</span></span> <span data-ttu-id="26f76-207">(Você pode copiar, modificar e usar nosso exemplo.)</span><span class="sxs-lookup"><span data-stu-id="26f76-207">(You can copy, modify, and use our example.)</span></span>

<span data-ttu-id="26f76-208">Ao configurar o seu pacote de regras, certifique-se de referenciar corretamente o arquivo .csv e o arquivo **edm.xml**.</span><span class="sxs-lookup"><span data-stu-id="26f76-208">When you set up your rule package, make sure to correctly reference your .csv file and **edm.xml** file.</span></span> <span data-ttu-id="26f76-209">Você pode copiar, modificar e usar nosso exemplo.</span><span class="sxs-lookup"><span data-stu-id="26f76-209">You can copy, modify, and use our example.</span></span> <span data-ttu-id="26f76-210">Neste exemplo de xml, os seguintes campos precisam ser personalizados para criar seu tipo confidencial do EDM:</span><span class="sxs-lookup"><span data-stu-id="26f76-210">In this sample xml the following fields needs to be customized to create your EDM sensitive type:</span></span>

- <span data-ttu-id="26f76-211">**RulePack id e ExactMatch id**: use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) para gerar um GUID.</span><span class="sxs-lookup"><span data-stu-id="26f76-211">**RulePack id & ExactMatch id**: Use [New-GUID](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) to generate a GUID.</span></span>

- <span data-ttu-id="26f76-212">**Datastore**: este campo especifica o repositório de dados de pesquisa EDM a ser usado.</span><span class="sxs-lookup"><span data-stu-id="26f76-212">**Datastore**: This field specifies EDM lookup data store to be used.</span></span> <span data-ttu-id="26f76-213">Forneça um nome de fonte de dados de um esquema EDM configurado.</span><span class="sxs-lookup"><span data-stu-id="26f76-213">You provide a data source name of a configured EDM Schema.</span></span>

- <span data-ttu-id="26f76-214">**idMatch**: este campo aponta para o elemento principal do EDM.</span><span class="sxs-lookup"><span data-stu-id="26f76-214">**idMatch**: This field points to the primary element for EDM.</span></span>
  - <span data-ttu-id="26f76-215">Correspondências: especifica o campo a ser usado na pesquisa exata.</span><span class="sxs-lookup"><span data-stu-id="26f76-215">Matches: Specifies the field to be used in exact lookup.</span></span> <span data-ttu-id="26f76-216">Forneça um nome de campo pesquisável no esquema EDM para o DataStore.</span><span class="sxs-lookup"><span data-stu-id="26f76-216">You provide a searchable field name in EDM Schema for the DataStore.</span></span>
  - <span data-ttu-id="26f76-217">Classificação: este campo especifica a correspondência de tipo confidencial que dispara a pesquisa EDM.</span><span class="sxs-lookup"><span data-stu-id="26f76-217">Classification: This field specifies the sensitive type match that triggers EDM lookup.</span></span> <span data-ttu-id="26f76-218">Você pode fornecer o nome ou o GUID de uma classificação interna ou personalizada existente.</span><span class="sxs-lookup"><span data-stu-id="26f76-218">You can provide Name or GUID of an existing built-in or custom classification.</span></span>

- <span data-ttu-id="26f76-219">**Corresponder:** este campo aponta para evidências adicionais encontradas em proximidade do idMatch.</span><span class="sxs-lookup"><span data-stu-id="26f76-219">**Match:** This field points to additional evidence found in proximity of idMatch.</span></span>
  - <span data-ttu-id="26f76-220">Correspondências: forneça o nome do campo no esquema EMD para DataStore.</span><span class="sxs-lookup"><span data-stu-id="26f76-220">Matches: You provide any field name in EDM Schema for DataStore.</span></span>
- <span data-ttu-id="26f76-221">**Recurso:** esta seção especifica o nome e a descrição do tipo confidencial em várias localidades.</span><span class="sxs-lookup"><span data-stu-id="26f76-221">**Resource:** This section specifies the name and description for sensitive type in multiple locales.</span></span>
  - <span data-ttu-id="26f76-222">idRef: forneça GUID para ExactMatch id.</span><span class="sxs-lookup"><span data-stu-id="26f76-222">idRef: You provide GUID for ExactMatch id.</span></span>
  - <span data-ttu-id="26f76-223">Nome e Edição de descrições de esquema: personalize conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="26f76-223">Name & des Editing the schema criptions: customize as required.</span></span>

```xml
<RulePackage xmlns="https://schemas.microsoft.com/office/2018/edm">
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
    <LocalizedStrings>
      <Resource idRef="E1CC861E-3FE9-4A58-82DF-4BD259EAB371">
        <Name default="true" langcode="en-us">Patient SSN Exact Match.</Name>
        <Description default="true" langcode="en-us">EDM Sensitive type for detecting Patient SSN.</Description>
      </Resource>
    </LocalizedStrings>
  </Rules>
</RulePackage>
```

1. <span data-ttu-id="26f76-224">Carregue o pacote de regras executando os seguintes cmdlets do PowerShell, um de cada vez:</span><span class="sxs-lookup"><span data-stu-id="26f76-224">Upload the rule package by running the following PowerShell cmdlets, one at a time:</span></span>

```powershell
$rulepack=Get-Content .\\rulepack.xml -Encoding Byte -ReadCount 0
New-DlpSensitiveInformationTypeRulePackage -FileData $rulepack
```

<span data-ttu-id="26f76-225">Nesse ponto, você configurou a classificação baseada em EDM.</span><span class="sxs-lookup"><span data-stu-id="26f76-225">At this point, you have set up EDM-based classification.</span></span> <span data-ttu-id="26f76-226">A próxima etapa é indexar os dados confidenciais e carregá-los.</span><span class="sxs-lookup"><span data-stu-id="26f76-226">The next step is to index the sensitive data, and then upload the indexed data.</span></span>

<span data-ttu-id="26f76-227">Lembre-se do procedimento anterior onde o nosso esquema PatientRecords define cinco campos como pesquisáveis:  *PatientID*, *Número de prontuário médico*, *CPF*, *Telefone* e  *Data de nascimento*.</span><span class="sxs-lookup"><span data-stu-id="26f76-227">Recall from the previous procedure that our PatientRecords schema defines five fields as searchable: *PatientID*, *MRN*, *SSN*, *Phone*, and *DOB*.</span></span> <span data-ttu-id="26f76-228">O nosso pacote de regras de exemplo inclui esses campos e faz referência ao arquivo de esquema do banco de dados (**edm.xml**), com um item  *ExactMatch*  por campo pesquisável.</span><span class="sxs-lookup"><span data-stu-id="26f76-228">Our example rule package includes those fields and references the database schema file (**edm.xml**), with one *ExactMatch* items per searchable field.</span></span> <span data-ttu-id="26f76-229">Considere o seguinte item ExactMatch:</span><span class="sxs-lookup"><span data-stu-id="26f76-229">Consider the following ExactMatch item:</span></span>

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

<span data-ttu-id="26f76-230">Neste exemplo, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="26f76-230">In this example, note the following:</span></span>

- <span data-ttu-id="26f76-231">O nome do dataStore faz referência ao arquivo .csv que criamos anteriormente: **dataStore = "PatientRecords"**.</span><span class="sxs-lookup"><span data-stu-id="26f76-231">The dataStore name references the .csv file we created earlier: **dataStore = "PatientRecords"**.</span></span>

- <span data-ttu-id="26f76-232">O valor idMatch faz referência a um campo pesquisável listado no arquivo de esquema do banco de dados:  **idMatch matches = "SSN"**.</span><span class="sxs-lookup"><span data-stu-id="26f76-232">The idMatch value references a searchable field that is listed in the database schema file: **idMatch matches = "SSN"**.</span></span>

- <span data-ttu-id="26f76-233">O valor de classificação faz referência a um tipo de informação confidencial existente ou personalizada: **classification = "Número de Seguridade Social dos EUA (SSN)"**.</span><span class="sxs-lookup"><span data-stu-id="26f76-233">The classification value references an existing or custom sensitive information type: **classification = "U.S. Social Security Number (SSN)"**.</span></span> <span data-ttu-id="26f76-234">(Nesse caso, usamos o tipo de informação confidencial existente do Número de Seguridade Social dos EUA.)</span><span class="sxs-lookup"><span data-stu-id="26f76-234">(In this case, we use the existing sensitive information type of U.S. Social Security Number.)</span></span>

> [!NOTE]
> <span data-ttu-id="26f76-235">Pode levar de 10 a 60 minutos para atualizar o EDMSchema com as adições.</span><span class="sxs-lookup"><span data-stu-id="26f76-235">It can take between 10-60 minutes to update the EDMSchema with additions.</span></span> <span data-ttu-id="26f76-236">A atualização deve ser concluída antes que você execute as etapas que usam as adições.</span><span class="sxs-lookup"><span data-stu-id="26f76-236">The update must complete before you execute steps that use the additions.</span></span>

### <a name="part-2-index-and-upload-the-sensitive-data"></a><span data-ttu-id="26f76-237">Parte 2: indexação e carregamento de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-237">Part 2: Index and upload the sensitive data</span></span>

<span data-ttu-id="26f76-238">Durante essa fase, você configura um grupo de segurança personalizado e uma conta de usuário, e configura a ferramenta do agente de carregamento do EDM.</span><span class="sxs-lookup"><span data-stu-id="26f76-238">During this phase, you set up a custom security group and user account, and set up the EDM Upload Agent tool.</span></span> <span data-ttu-id="26f76-239">Depois indexe os dados confidenciais e carregá-los.</span><span class="sxs-lookup"><span data-stu-id="26f76-239">Then, you use the tool to index the sensitive data, and upload the indexed data.</span></span>

#### <a name="set-up-the-security-group-and-user-account"></a><span data-ttu-id="26f76-240">Configuração do grupo de segurança e conta de usuário</span><span class="sxs-lookup"><span data-stu-id="26f76-240">Set up the security group and user account</span></span>

1. <span data-ttu-id="26f76-241">Como um administrador global, acesse o centro de administração ([https://admin.microsoft.com](https://admin.microsoft.com/)) e [crie um grupo de segurança](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) chamado  **EDM\_DataUploaders**.</span><span class="sxs-lookup"><span data-stu-id="26f76-241">As a global administrator, go to the admin center ([https://admin.microsoft.com](https://admin.microsoft.com/)) and [create a security group](https://docs.microsoft.com/office365/admin/email/create-edit-or-delete-a-security-group?view=o365-worldwide) called **EDM\_DataUploaders**.</span></span>

2. <span data-ttu-id="26f76-242">Adicione um ou mais usuários ao grupo de segurança **EDM\_DataUploaders** .</span><span class="sxs-lookup"><span data-stu-id="26f76-242">Add one or more users to the **EDM\_DataUploaders** security group.</span></span> <span data-ttu-id="26f76-243">(Esses usuários vão gerenciar o banco de dados de informações confidenciais.)</span><span class="sxs-lookup"><span data-stu-id="26f76-243">(These users will manage the database of sensitive information.)</span></span>

3. <span data-ttu-id="26f76-244">Certifique-se de que todos os usuários que estão gerenciando os dados confidenciais sejam um administrador local no computador usado para o agente de carregamento do EDM.</span><span class="sxs-lookup"><span data-stu-id="26f76-244">Make sure each user who is managing the sensitive data is a local admin on the machine used for the EDM Upload Agent.</span></span>

#### <a name="set-up-the-edm-upload-agent"></a><span data-ttu-id="26f76-245">Configurar o agente de carregamento do EDM</span><span class="sxs-lookup"><span data-stu-id="26f76-245">Set up the EDM Upload Agent</span></span>

>[!NOTE]
> <span data-ttu-id="26f76-246">Antes de iniciar esse procedimento, certifique-se de que você é um membro do grupo de segurança **EDM\_DataUploaders**  e um administrador local no computador.</span><span class="sxs-lookup"><span data-stu-id="26f76-246">Before you begin this procedure, make sure that you are a member of the **EDM\_DataUploaders** security group and a local admin on your machine.</span></span>

1. <span data-ttu-id="26f76-247">Baixe e instale o [Agente de Carregamento do EDM](https://go.microsoft.com/fwlink/?linkid=2088639).</span><span class="sxs-lookup"><span data-stu-id="26f76-247">Download and install the [EDM Upload Agent](https://go.microsoft.com/fwlink/?linkid=2088639).</span></span> <span data-ttu-id="26f76-248">Por padrão, o local de instalação deve ser  **C:\\Arquivos de Programa \\Microsoft\\EdmUploadAgent**.</span><span class="sxs-lookup"><span data-stu-id="26f76-248">By default, the installation location should be **C:\\Program Files\\Microsoft\\EdmUploadAgent**.</span></span>

> [!TIP]
> <span data-ttu-id="26f76-249">Para obter uma lista com os parâmetros de comando com suporte, execute o agente sem argumentos.</span><span class="sxs-lookup"><span data-stu-id="26f76-249">To a get a list out of the supported command parameters, run the agent no arguments.</span></span> <span data-ttu-id="26f76-250">Por exemplo, ‘EdmUploadAgent.exe’.</span><span class="sxs-lookup"><span data-stu-id="26f76-250">For example 'EdmUploadAgent.exe'.</span></span>

2. <span data-ttu-id="26f76-251">Para autorizar o agente de carregamento do EDM, abra o prompt de comando do Windows (como um administrador) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="26f76-251">To authorize the EDM Upload Agent, open Windows Command Prompt (as an administrator), and then run the following command:</span></span>

    `EdmUploadAgent.exe /Authorize`

3. <span data-ttu-id="26f76-252">Entre com sua conta corporativa ou de estudante do Office 365.</span><span class="sxs-lookup"><span data-stu-id="26f76-252">Sign in with your work or school account for Office 365.</span></span>

<span data-ttu-id="26f76-253">A próxima etapa é usar o agente de carregamento do EDM para indexar os dados confidenciais e depois carregá-los.</span><span class="sxs-lookup"><span data-stu-id="26f76-253">The next step is to use the EDM Upload Agent to index the sensitive data, and then upload the indexed data.</span></span>

#### <a name="index-and-upload-the-sensitive-data"></a><span data-ttu-id="26f76-254">Indexação e carregamento de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-254">Index and upload the sensitive data</span></span>

<span data-ttu-id="26f76-255">Salve o arquivo de dados confidenciais (lembre-se de que o nosso exemplo é **PatientRecords.csv**) para a unidade local no computador.</span><span class="sxs-lookup"><span data-stu-id="26f76-255">Save the sensitive data file (recall our example is **PatientRecords.csv**) to the local drive on the machine.</span></span> <span data-ttu-id="26f76-256">(Salvamos nosso arquivo de exemplo **PatientRecords.csv**  em  **C:\\Edm\\Data**.)</span><span class="sxs-lookup"><span data-stu-id="26f76-256">(We saved our example **PatientRecords.csv** file to **C:\\Edm\\Data**.)</span></span>

<span data-ttu-id="26f76-257">Para indexar e carregar os dados confidenciais, execute o seguinte comando no prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="26f76-257">To index and upload the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadData /DataStoreName \<DataStoreName\> /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="26f76-258">Exemplo: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="26f76-258">Example: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\\Edm\\Hash\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="26f76-259">Para separar e executar o índice de dados confidenciais em um ambiente isolado, execute as etapas de indexação e carregamento separadamente.</span><span class="sxs-lookup"><span data-stu-id="26f76-259">To separate and execute index of sensitive data in an isolated environment, execute index and upload steps separately.</span></span>

<span data-ttu-id="26f76-260">Para indexar os dados confidenciais, execute o seguinte comando no prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="26f76-260">To index the sensitive data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /CreateHash /DataFile \<DataFilePath\> /HashLocation \<HashedFileLocation\>`

<span data-ttu-id="26f76-261">por exemplo,</span><span class="sxs-lookup"><span data-stu-id="26f76-261">for example,</span></span>

> <span data-ttu-id="26f76-262">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span><span class="sxs-lookup"><span data-stu-id="26f76-262">**EdmUploadAgent.exe /CreateHash /DataFile C:\\Edm\\Data\\PatientRecords.csv /HashLocation C:\\Edm\\Hash**</span></span>

<span data-ttu-id="26f76-263">Para carregar os dados indexados, execute o seguinte comando no prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="26f76-263">To upload the indexed data, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\>`

<span data-ttu-id="26f76-264">por exemplo,</span><span class="sxs-lookup"><span data-stu-id="26f76-264">for example,</span></span> 

> <span data-ttu-id="26f76-265">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span><span class="sxs-lookup"><span data-stu-id="26f76-265">**EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\PatientRecords.EdmHash**</span></span>

<span data-ttu-id="26f76-266">Para verificar os dados confidenciais indexados, execute o seguinte comando no prompt de comando do Windows:</span><span class="sxs-lookup"><span data-stu-id="26f76-266">To verify your sensitive data has been uploaded, run the following command in Windows Command Prompt:</span></span>

`EdmUploadAgent.exe /GetDataStore`

<span data-ttu-id="26f76-267">Você verá uma lista de repositórios de dados e a data da última atualização.</span><span class="sxs-lookup"><span data-stu-id="26f76-267">You'll see a list of data stores and when they were last updated.</span></span>

<span data-ttu-id="26f76-268">Prossiga para configurar seu processo e cronograma da [Atualização de banco de dados de informação confidencial](#refreshing-your-sensitive-information-database).</span><span class="sxs-lookup"><span data-stu-id="26f76-268">Proceed to set up your process and schedule for [Refreshing your sensitive information database](#refreshing-your-sensitive-information-database).</span></span>

<span data-ttu-id="26f76-269">Nesse ponto, você já usou a classificação baseada em EDM com os serviços de nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26f76-269">At this point, you are ready to use EDM-based classification with your Microsoft cloud services.</span></span> <span data-ttu-id="26f76-270">Por exemplo, você pode [configurar uma política usando a classificação baseada em EDM](#to-create-a-dlp-policy-with-edm).</span><span class="sxs-lookup"><span data-stu-id="26f76-270">For example, you can [set up a DLP policy using EDM-based classification](#to-create-a-dlp-policy-with-edm).</span></span>

#### <a name="refreshing-your-sensitive-information-database"></a><span data-ttu-id="26f76-271">Atualização do banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-271">Refreshing your sensitive information database</span></span>

<span data-ttu-id="26f76-272">Você pode atualizar seu banco de dados confidenciais diariamente ou semanalmente, e a ferramenta de carregamento do EDM pode reindexar os dados confidenciais e depois recarregar os dados indexados.</span><span class="sxs-lookup"><span data-stu-id="26f76-272">You can refresh your sensitive information database daily or weekly, and the EDM Upload Tool can reindex the sensitive data and then reupload the indexed data.</span></span>

1. <span data-ttu-id="26f76-273">Determine seu processo e a frequência (diariamente ou semanalmente) para atualização do banco de dados de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="26f76-273">Determine your process and frequency (daily or weekly) for refreshing the database of sensitive information.</span></span>

2. <span data-ttu-id="26f76-274">Exporte novamente os dados confidenciais para um aplicativo, como o Microsoft Excel, e salve o arquivo no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="26f76-274">Re-export the sensitive data to an app, such as Microsoft Excel, and save the file in .csv format.</span></span> <span data-ttu-id="26f76-275">Mantenha o mesmo nome do arquivo e o local que você usou ao seguir as etapas descritas em [indexação e carregamento de dados confidenciais](#index-and-upload-the-sensitive-data).</span><span class="sxs-lookup"><span data-stu-id="26f76-275">Keep the same file name and location you used when you followed the steps described in [Index and upload the sensitive data](#index-and-upload-the-sensitive-data).</span></span>

> [!NOTE]
> <span data-ttu-id="26f76-276">Se não houver alterações na estrutura (nomes de campos) do arquivo .csv, você não precisará fazer alterações no arquivo de esquema do banco de dados ao atualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="26f76-276">If there are no changes to the structure (field names) of the .csv file, you won't need to make any changes to your database schema file when you refresh the data.</span></span> <span data-ttu-id="26f76-277">Mas se for necessário fazer alterações, não deixe de editar o esquema de banco de dados e seu pacote de regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="26f76-277">But if you must make changes, make sure to edit the database schema and your rule package accordingly.</span></span>

3. <span data-ttu-id="26f76-278">Use o [Agendador de tarefas](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) para automatizar as etapas 2 e 3 [no procedimento de indexação e carregamento de dados confidenciais](#index-and-upload-the-sensitive-data) .</span><span class="sxs-lookup"><span data-stu-id="26f76-278">Use [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/task-scheduler-start-page) to automate steps 2 and 3 in the [Index and upload the sensitive data](#index-and-upload-the-sensitive-data) procedure.</span></span> <span data-ttu-id="26f76-279">Você pode agendar tarefas usando vários métodos:</span><span class="sxs-lookup"><span data-stu-id="26f76-279">You can schedule tasks using several methods:</span></span>

| <span data-ttu-id="26f76-280">**Método**</span><span class="sxs-lookup"><span data-stu-id="26f76-280">**Method**</span></span>             | <span data-ttu-id="26f76-281">**O que fazer**</span><span class="sxs-lookup"><span data-stu-id="26f76-281">**What to do**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="26f76-282">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26f76-282">Windows PowerShell</span></span>     | <span data-ttu-id="26f76-283">Confira a [documentação do ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) e o [exemplo do script do PowerShell](#example-powershell-script-for-task-scheduler) neste artigo.</span><span class="sxs-lookup"><span data-stu-id="26f76-283">See the [ScheduledTasks](https://docs.microsoft.com/powershell/module/scheduledtasks/?view=win10-ps) documentation and the [example PowerShell script](#example-powershell-script-for-task-scheduler) in this article</span></span> |
| <span data-ttu-id="26f76-284">API do Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="26f76-284">Task Scheduler API</span></span>     | <span data-ttu-id="26f76-285">Confira a documentação do [Agendador de Tarefas](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) </span><span class="sxs-lookup"><span data-stu-id="26f76-285">See the [Task Scheduler](https://docs.microsoft.com/windows/desktop/TaskSchd/using-the-task-scheduler) documentation</span></span>                                                                                                                                                                                                                                                                                |
| <span data-ttu-id="26f76-286">Interface do usuário do Windows</span><span class="sxs-lookup"><span data-stu-id="26f76-286">Windows user interface</span></span> | <span data-ttu-id="26f76-287">No Windows, clique em **Iniciar** e digite Agendador de Tarefas.</span><span class="sxs-lookup"><span data-stu-id="26f76-287">In Windows, click **Start**, and type Task Scheduler.</span></span> <span data-ttu-id="26f76-288">Em seguida, na lista de resultados, clique com o botão direito do mouse no **Agendador de Tarefas** e escolha **executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="26f76-288">Then, in the list of results, right-click **Task Scheduler**, and choose **Run as administrator**.</span></span>                                                                                                                                                                                                                                                                           |

#### <a name="example-powershell-script-for-task-scheduler"></a><span data-ttu-id="26f76-289">Exemplo de script do PowerShell para o Agendador de Tarefas</span><span class="sxs-lookup"><span data-stu-id="26f76-289">Example PowerShell script for Task Scheduler</span></span>

<span data-ttu-id="26f76-290">Esta seção inclui um exemplo de script do PowerShell que pode ser usado para agendar as tarefas de indexação de dados e carregamento dos dados indexados:</span><span class="sxs-lookup"><span data-stu-id="26f76-290">This section includes an example PowerShell script you can use to schedule your tasks for indexing data and uploading the indexed data:</span></span>

##### <a name="to-schedule-index-and-upload-in-a-combined-step"></a><span data-ttu-id="26f76-291">Para agendar o índice e carregar em uma etapa combinada</span><span class="sxs-lookup"><span data-stu-id="26f76-291">To schedule index and upload in a combined step</span></span>

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
$uploadDataArgs = '/UploadData /DataStoreName ' + $dataStoreName + ' /DataFile ' + $dataFile + ‘ /HashLocation’ + $hashLocation
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

#### <a name="to-schedule-index-and-upload-as-separate-steps"></a><span data-ttu-id="26f76-292">Para agendar o índice e carregar como etapas separadas</span><span class="sxs-lookup"><span data-stu-id="26f76-292">To schedule index and upload as separate steps</span></span>

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

### <a name="part-3-use-edm-based-classification-with-your-microsoft-cloud-services"></a><span data-ttu-id="26f76-293">Parte 3: uso da classificação baseada em EDM com os serviços de nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="26f76-293">Part 3: Use EDM-based classification with your Microsoft cloud services</span></span>

<span data-ttu-id="26f76-294">A DLP do Office 365 para Exchange Online (email), OneDrive for Business (arquivos), Microsoft Teams (conversas) e as políticas de segurança do Microsoft Cloud App serão compatíveis com os tipos de informações confidenciais do EDM.</span><span class="sxs-lookup"><span data-stu-id="26f76-294">Office 365 DLP for Exchange Online (email), OneDrive for Business (files), Microsoft Teams (conversations) and Microsoft Cloud App Security DLP policies will support EDM sensitive information types.</span></span>

<span data-ttu-id="26f76-295">Os tipos de informações confidenciais do EDM para os cenários a seguir estão em desenvolvimento, mas ainda não estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="26f76-295">EDM sensitive information types for following scenarios are currently in development, but not yet available:</span></span>

- <span data-ttu-id="26f76-296">A DLP do Office 365 para SharePoint (arquivos)</span><span class="sxs-lookup"><span data-stu-id="26f76-296">Office 365 DLP for SharePoint (files)</span></span>
- <span data-ttu-id="26f76-297">Classificação automática de rótulos de confidencialidade e rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="26f76-297">Auto-classification of sensitivity labels and retention labels</span></span>

#### <a name="to-create-a-dlp-policy-with-edm"></a><span data-ttu-id="26f76-298">Criação de uma política DLP com o EDM</span><span class="sxs-lookup"><span data-stu-id="26f76-298">To create a DLP policy with EDM</span></span>

1. <span data-ttu-id="26f76-299">Acesse o Centro de Conformidade e Segurança ([https://protection.office.com](https://protection.office.com/)).</span><span class="sxs-lookup"><span data-stu-id="26f76-299">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com/)).</span></span>

2. <span data-ttu-id="26f76-300">Clique em **Prevenção contra perda de dados** \> **Política**.</span><span class="sxs-lookup"><span data-stu-id="26f76-300">Choose **Data loss prevention** \> **Policy**.</span></span>

3. <span data-ttu-id="26f76-301">Clique em **Criar uma política** \> **Personalizar** \> **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="26f76-301">Choose **Create a policy** \> **Custom** \> **Next**.</span></span>

4. <span data-ttu-id="26f76-302">Na guia **Nomear sua política** , especifique um nome e uma descrição e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="26f76-302">On the **Name your policy** tab, specify a name and description, and then choose **Next**.</span></span>

5. <span data-ttu-id="26f76-303">Na guia **Escolher locais** , clique em **Escolher locais específicos**e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="26f76-303">On the **Choose locations** tab, select **Let me choose specific locations**, and then choose **Next**.</span></span>

6. <span data-ttu-id="26f76-304">Na coluna **Status** , escolha **email do Exchange, contas do OneDrive, mensagem de canal e chat do Teams** e, em seguida, escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="26f76-304">In the **Status** column, select **Exchange email, OneDrive accounts, Teams chat and channel message** , and then choose **Next**.</span></span> <span data-ttu-id="26f76-305">(Observação: atualmente, o EDM não é compatível com sites do SharePoint e a política de DLP não irá detectar arquivos no SharePoint para EDM)</span><span class="sxs-lookup"><span data-stu-id="26f76-305">(Note: EDM is currently not supported in SharePoint sites and DLP policy will not detect files in Sharepoint for EDM)</span></span>

7. <span data-ttu-id="26f76-306">Na guia **Configurações de política** , escolha **Usar configurações avançadas**e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="26f76-306">On the **Policy settings** tab, choose **Use advanced settings**, and then choose **Next**.</span></span>

8. <span data-ttu-id="26f76-307">Escolha **+ Nova regra**.</span><span class="sxs-lookup"><span data-stu-id="26f76-307">Choose **+ New rule**.</span></span>

9. <span data-ttu-id="26f76-308">Na seção **Nome** , especifique um nome e uma descrição para a regra.</span><span class="sxs-lookup"><span data-stu-id="26f76-308">In the **Name** section, specify a name and description for the rule.</span></span>

10. <span data-ttu-id="26f76-309">Na seção **Condições** , na lista **Adicionar uma condição** , escolha **Conteúdo contém tipo confidencial**.</span><span class="sxs-lookup"><span data-stu-id="26f76-309">In the **Conditions** section, in the **+ Add a condition** list, choose **Content contains sensitive type**.</span></span><br/><span data-ttu-id="26f76-310">![Conteúdo tem tipos de informações confidenciais](../media/edm-dlp-newrule-conditions.png)</span><span class="sxs-lookup"><span data-stu-id="26f76-310">![Content contains sensitive info types](../media/edm-dlp-newrule-conditions.png)</span></span><br/>

11. <span data-ttu-id="26f76-311">Pesquise o tipo de informação confidencial que você criou ao configurar o pacote de regras e, em seguida, escolha **+ Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="26f76-311">Search for the sensitive information type you created when you set up your rule package, and then choose **+ Add**.</span></span>  
    <span data-ttu-id="26f76-312">Em seguida, escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="26f76-312">Then choose **Done**.</span></span>

12. <span data-ttu-id="26f76-313">Termine de selecionar as opções para a regra, como **Notificações de usuário**, **Substituições do usuário**, **Relatórios de incidente**, e assim por diante, e depois clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="26f76-313">Finish selecting options for your rule, such as **User notifications**, **User overrides**, **Incident reports**, and so on, and then choose **Save**.</span></span>

13. <span data-ttu-id="26f76-314">Na guia **Configurações de política** , revise suas regras e, em seguida, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="26f76-314">On the **Policy settings** tab, review your rules, and then choose **Next**.</span></span>

14. <span data-ttu-id="26f76-315">Especifique se deseja ativar a política imediatamente, testá-la ou desativá-la.</span><span class="sxs-lookup"><span data-stu-id="26f76-315">Specify whether to turn on the policy right away, test it out, or keep it turned off.</span></span> <span data-ttu-id="26f76-316">Em seguida, escolha **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="26f76-316">Then choose **Next**.</span></span>

15. <span data-ttu-id="26f76-317">Na guia **Revisar suas configurações** , revise sua política.</span><span class="sxs-lookup"><span data-stu-id="26f76-317">On the **Review your settings** tab, review your policy.</span></span> <span data-ttu-id="26f76-318">Faça todas as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="26f76-318">Make any needed changes.</span></span> <span data-ttu-id="26f76-319">Quando concluir, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="26f76-319">When you're ready, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="26f76-320">Espere aproximadamente uma hora para sua nova política DLP funcionar em seu data center.</span><span class="sxs-lookup"><span data-stu-id="26f76-320">Allow approximately one hour for your new DLP policy to work its way through your data center.</span></span>

## <a name="related-articles"></a><span data-ttu-id="26f76-321">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="26f76-321">Related articles</span></span>

[<span data-ttu-id="26f76-322">Tipos de informações confidenciais integradas e o que procuram</span><span class="sxs-lookup"><span data-stu-id="26f76-322">Built-in sensitive information types and what they look for</span></span>](what-the-sensitive-information-types-look-for.md)

[<span data-ttu-id="26f76-323">Tipos personalizados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="26f76-323">Custom sensitive information types</span></span>](custom-sensitive-info-types.md)

[<span data-ttu-id="26f76-324">Visão geral das políticas DLP</span><span class="sxs-lookup"><span data-stu-id="26f76-324">Overview of DLP policies</span></span>](data-loss-prevention-policies.md)

[<span data-ttu-id="26f76-325">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="26f76-325">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)

[<span data-ttu-id="26f76-326">New-DlpEdmSchema</span><span class="sxs-lookup"><span data-stu-id="26f76-326">New-DlpEdmSchema</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/new-dlpedmschema?view=exchange-ps)

## <a name="feedback"></a><span data-ttu-id="26f76-327">Feedback</span><span class="sxs-lookup"><span data-stu-id="26f76-327">Feedback</span></span>

<span data-ttu-id="26f76-328">Os comentários do GitHub estão habilitados, mas não é possível adicionar problemas no site público.</span><span class="sxs-lookup"><span data-stu-id="26f76-328">GitHub feedback is enabled, but adding issues is only available on the public site.</span></span>
