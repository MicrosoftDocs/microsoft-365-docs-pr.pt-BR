---
title: Use o Assistente de Correspondência Exata de Dados e Tipo de Informação Confidencial
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
description: Aprenda como usar o assistente do esquema de correspondência exata de dados e tipo de informação confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699139"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="5eb74-103">Use o Assistente de Correspondência Exata de Dados e Tipo de Informação Confidencial</span><span class="sxs-lookup"><span data-stu-id="5eb74-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="5eb74-104">[Criar um tipo personalizado de informação confidencial com classificação baseada em EDM (Correspondência Exata de Dados) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  envolve várias etapas.</span><span class="sxs-lookup"><span data-stu-id="5eb74-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="5eb74-105">Você pode usar este assistente para criar o esquema e os arquivos de padrão do tipo de informações confidenciais (pacote de regra) para ajudar a simplificar o processo.</span><span class="sxs-lookup"><span data-stu-id="5eb74-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="5eb74-106">O Assistente de Correspondência Exata de Dados e Tipo de Informações Confidenciais está disponível apenas para as nuvens WW E GCC.</span><span class="sxs-lookup"><span data-stu-id="5eb74-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="5eb74-107">Esse assistente pode ser usado em vez do:</span><span class="sxs-lookup"><span data-stu-id="5eb74-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="5eb74-108">Definição do esquema para seu banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="5eb74-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="5eb74-109">Configurar um padrão (pacote de regras)</span><span class="sxs-lookup"><span data-stu-id="5eb74-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="5eb74-110">etapas na [Parte 1: configurar a classificação baseada em EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="5eb74-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5eb74-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5eb74-111">Pre-requisites</span></span>

1. <span data-ttu-id="5eb74-112">Familiarize-se com as etapas para criar um tipo personalizado de informações confidenciais com o EDM [fluxo de trabalho em um relance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="5eb74-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="5eb74-113">Execute as etapas na seção [Salvar dados confidenciais no formato .csv](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format).</span><span class="sxs-lookup"><span data-stu-id="5eb74-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="5eb74-114">Use o esquema exato de correspondência de dados e o assistente do padrão do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="5eb74-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="5eb74-115">No centro de Conformidade do Microsoft 365 para seu locatário, acesse **Classificação de dados** > **Correspondência de dados exata**.</span><span class="sxs-lookup"><span data-stu-id="5eb74-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="5eb74-116">Escolha **Criar o esquema EDM** para abrir o submenu configuração do assistente de esquema.</span><span class="sxs-lookup"><span data-stu-id="5eb74-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Submenu de configuração do assistente para criação de esquemas EDM](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="5eb74-118">Preencha um **Nome** e uma **Descrição** apropriados.</span><span class="sxs-lookup"><span data-stu-id="5eb74-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="5eb74-119">Escolha **Ignorar delimitadores e pontuações de todos os campos do esquema** se desejar esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="5eb74-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="5eb74-120">Para saber mais sobre como configurar o EDM para ignorar maiúsculas e minúsculas ou delimitador, consulte [Criar um tipo personalizado de informações confidenciais com classificação baseada em EDM (Correspondência Exata de Dados)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="5eb74-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="5eb74-121">Preencha os valores desejados para seu **Campo de esquema #1** e adicione mais campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5eb74-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5eb74-122">Pelo menos um, mas não mais de cinco campos de esquema devem ser designados como pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="5eb74-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="5eb74-123">Escolha salvar.</span><span class="sxs-lookup"><span data-stu-id="5eb74-123">Choose save.</span></span> <span data-ttu-id="5eb74-124">O esquema agora será listado.</span><span class="sxs-lookup"><span data-stu-id="5eb74-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="5eb74-125">Escolha **Tipos de informações confidenciais do EDM** e **Criar tipo de informações confidenciais EDM** para abrir o assistente de configuração do tipo de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="5eb74-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="5eb74-126">Escolha **Escolher um esquema EDM existente** e escolha o esquema criado nas etapas 2-6 da lista.</span><span class="sxs-lookup"><span data-stu-id="5eb74-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="5eb74-127">Escolha **Próximo** e escolha **Criar padrão**.</span><span class="sxs-lookup"><span data-stu-id="5eb74-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="5eb74-128">Escolha o **Nível de confiança** e **Elemento principal**.</span><span class="sxs-lookup"><span data-stu-id="5eb74-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="5eb74-129">Para saber mais sobre como configurar um padrão, consulte [Criar um tipo personalizado de informações confidenciais no Centro de Conformidade](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="5eb74-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="5eb74-130">Escolha o **Tipo de informações confidenciais do elemento principal** para associá-lo.</span><span class="sxs-lookup"><span data-stu-id="5eb74-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="5eb74-131">Consulte [Definições da Entidade de Tipo de Informações Confidenciais](sensitive-information-type-entity-definitions.md) para saber mais sobre os tipos de informações confidenciais disponíveis..</span><span class="sxs-lookup"><span data-stu-id="5eb74-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="5eb74-132">Escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="5eb74-132">Choose **Done**.</span></span>

13. <span data-ttu-id="5eb74-133">Escolha o **Nível de confiança e a proximidade de caractere** desejados.</span><span class="sxs-lookup"><span data-stu-id="5eb74-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="5eb74-134">Esse será o valor padrão para todo o tipo de informações confidenciais do EDM</span><span class="sxs-lookup"><span data-stu-id="5eb74-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="5eb74-135">Escolha **Criar padrão** se quiser criar padrões adicionais para o tipo de informações confidenciais do EDM.</span><span class="sxs-lookup"><span data-stu-id="5eb74-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="5eb74-136">Escolha **Próximo** e preencha o **Nome** e **Descrição para os administradores**.</span><span class="sxs-lookup"><span data-stu-id="5eb74-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="5eb74-137">Examine e escolha **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="5eb74-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="5eb74-138">Você pode excluir ou editar o padrão de tipo de informações confidenciais, selecionando-o que superfícies os controles editar e excluir.</span><span class="sxs-lookup"><span data-stu-id="5eb74-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5eb74-139">Se você quiser remover um esquema e já estiver associado a um tipo de informações confidenciais do EDM, primeiro é necessário excluir o tipo de informações confidenciais do EDM. em seguida, você pode excluir o esquema.</span><span class="sxs-lookup"><span data-stu-id="5eb74-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="5eb74-140">Etapas da postagem</span><span class="sxs-lookup"><span data-stu-id="5eb74-140">Post steps</span></span>

<span data-ttu-id="5eb74-141">Depois de usar o assistente para criar o esquema EDM e os arquivos padrão (pacote de regras), você ainda precisará executar as etapas na [Part 2: hash e carregar os dados confidenciais](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) antes de poder usar o tipo personalizado de informações confidenciais do EDM.</span><span class="sxs-lookup"><span data-stu-id="5eb74-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>