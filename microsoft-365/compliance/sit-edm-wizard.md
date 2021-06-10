---
title: Use o Assistente de Correspondência Exata de Dados e Tipo de Informação Confidencial
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Aprenda como usar o assistente do esquema de correspondência exata de dados e tipo de informação confidencial.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9d6f870239b963ee7483b9f08e93e40b10f4f0b
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877999"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="ddbd8-103">Use o Assistente de Correspondência Exata de Dados e Tipo de Informação Confidencial</span><span class="sxs-lookup"><span data-stu-id="ddbd8-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="ddbd8-104">[Criar um tipo personalizado de informação confidencial com classificação baseada em EDM (Correspondência Exata de Dados) ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  envolve várias etapas.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="ddbd8-105">Você pode usar esse assistente para criar seu esquema e arquivos de padrão de tipo de informação confidenciais (SIT) (pacote de regras) para ajudar a simplificar o processo.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-105">You can use this wizard to create your schema and sensitive information type (SIT) pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="ddbd8-106">O Assistente de Correspondência Exata de Dados e Tipo de Informações Confidenciais está disponível apenas para as nuvens WW E GCC.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="ddbd8-107">Esse assistente pode ser usado em vez do:</span><span class="sxs-lookup"><span data-stu-id="ddbd8-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="ddbd8-108">Definição do esquema para seu banco de dados de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="ddbd8-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="ddbd8-109">Configurar um padrão (pacote de regras)</span><span class="sxs-lookup"><span data-stu-id="ddbd8-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="ddbd8-110">etapas na [Parte 1: configurar a classificação baseada em EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="ddbd8-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="ddbd8-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ddbd8-111">Pre-requisites</span></span>

1. <span data-ttu-id="ddbd8-112">Familiarize-se com as etapas para criar um tipo personalizado de informações confidenciais com o EDM [fluxo de trabalho em um relance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span><span class="sxs-lookup"><span data-stu-id="ddbd8-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="ddbd8-113">Execute as etapas em [Salvar dados confidenciais no formato .csv ou .tsv.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format)</span><span class="sxs-lookup"><span data-stu-id="ddbd8-113">Perform the steps in [Save sensitive data in .csv or .tsv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-or-tsv-format).</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="ddbd8-114">Use o esquema exato de correspondência de dados e o assistente do padrão do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="ddbd8-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="ddbd8-115">No centro de Conformidade do Microsoft 365 para seu locatário, acesse **Classificação de dados** > **Correspondência de dados exata**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="ddbd8-116">Escolha **Criar o esquema EDM** para abrir o submenu configuração do assistente de esquema.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Submenu de configuração do assistente para criação de esquemas EDM](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="ddbd8-118">Preencha um **Nome** e uma **Descrição** apropriados.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="ddbd8-119">Escolha **Ignorar delimitadores e pontuação para todos os** campos de esquema se quiser esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-119">Choose **Ignore delimiters and punctuation for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="ddbd8-120">Para saber mais sobre como configurar o EDM para ignorar ocorrências ou delimitadores, consulte Creating a custom sensitive information [type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="ddbd8-120">To learn more about configuring EDM to ignore case or delimiters, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="ddbd8-121">Preencha os valores desejados para seu **Campo de esquema #1** e adicione mais campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ddbd8-122">Pelo menos um, mas não mais de cinco campos de esquema devem ser designados como pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="ddbd8-123">Escolha salvar.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-123">Choose save.</span></span> <span data-ttu-id="ddbd8-124">O esquema agora será listado.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="ddbd8-125">Escolha **Tipos de informações confidenciais do EDM** e **Criar tipo de informações confidenciais EDM** para abrir o assistente de configuração do tipo de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="ddbd8-126">Escolha **Escolher um esquema EDM existente** e escolha o esquema criado nas etapas 2-6 da lista.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="ddbd8-127">Escolha **Próximo** e escolha **Criar padrão**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="ddbd8-128">Escolha o **Nível de confiança** e **Elemento principal**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="ddbd8-129">Para saber mais sobre como configurar um padrão, consulte [Criar um tipo personalizado de informações confidenciais no Centro de Conformidade](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="ddbd8-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="ddbd8-130">Escolha o **Tipo de informações confidenciais do elemento principal** para associá-lo.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="ddbd8-131">Consulte [Definições da Entidade de Tipo de Informações Confidenciais](sensitive-information-type-entity-definitions.md) para saber mais sobre os tipos de informações confidenciais disponíveis..</span><span class="sxs-lookup"><span data-stu-id="ddbd8-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="ddbd8-132">Escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-132">Choose **Done**.</span></span>

13. <span data-ttu-id="ddbd8-133">Escolha o **Nível de confiança e a proximidade de caractere** desejados.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="ddbd8-134">Esse será o valor padrão para todo o tipo de informações confidenciais do EDM</span><span class="sxs-lookup"><span data-stu-id="ddbd8-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="ddbd8-135">Escolha **Criar padrão** se quiser criar padrões adicionais para seu tipo de informações confidenciais do EDM.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-135">Choose **Create pattern** if you want to create additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="ddbd8-136">Escolha **Próximo** e preencha o **Nome** e **Descrição para os administradores**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="ddbd8-137">Examine e escolha **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="ddbd8-138">Você pode excluir ou editar o padrão de tipo de informações confidenciais, selecionando-o que superfícies os controles editar e excluir.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddbd8-139">Se você quiser remover um esquema e já estiver associado a um tipo de informações confidenciais do EDM, primeiro é necessário excluir o tipo de informações confidenciais do EDM. em seguida, você pode excluir o esquema.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-creation-steps"></a><span data-ttu-id="ddbd8-140">Etapas de pós-criação</span><span class="sxs-lookup"><span data-stu-id="ddbd8-140">Post creation steps</span></span>

<span data-ttu-id="ddbd8-141">Depois de usar o assistente para criar o esquema EDM e os arquivos padrão (pacote de regras), você ainda precisará executar as etapas na [Part 2: hash e carregar os dados confidenciais](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) antes de poder usar o tipo personalizado de informações confidenciais do EDM.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>

<span data-ttu-id="ddbd8-142">Depois de verificar se sua tabela de informações confidenciais foi carregada corretamente, você pode testar se ela está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-142">After verifying that your sensitive information table has correctly been uploaded, you can test that it's working properly.</span></span>

1. <span data-ttu-id="ddbd8-143">Open **Compliance center** Data  >  **classification** Sensitive Information  >  **Types**.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-143">Open **Compliance center** > **Data classification** > **Sensitive Information Types**.</span></span>
2. <span data-ttu-id="ddbd8-144">Selecione seu EDM SIT na lista e selecione **Testar** no painel de sobrevoos.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-144">Select your EDM SIT from the list and then select **Test** in the flyout pane.</span></span> 
3. <span data-ttu-id="ddbd8-145">Upload um item que contém dados que você deseja detectar, por exemplo, crie um item que contenha alguns dos dados em sua tabela de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-145">Upload an item that contains data you want to detect, for example create an item that contains some of the data in your sensitive information table.</span></span> <span data-ttu-id="ddbd8-146">Se você usou o recurso de match configurável em seu esquema para definir delimitadores ignorados, certifique-se de que o item inclua exemplos com e sem esses delimitadores.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-146">If you used the configurable match feature in your schema to define ignored delimiters, make sure the item includes examples with and without those delimiters.</span></span>
4. <span data-ttu-id="ddbd8-147">Depois que o arquivo tiver sido carregado e verificado, verifique se há corresponde ao seu EDM SIT.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-147">After the file has been uploaded and scanned, check for matches to your EDM SIT.</span></span>
5. <span data-ttu-id="ddbd8-148">Se a **função Test** no SIT detectar uma combinação, verifique se ela não está aparando-a ou extraindo-a incorretamente.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-148">If the **Test** function in the SIT detects a match, check that it is not trimming it or extracting it incorrectly.</span></span> <span data-ttu-id="ddbd8-149">Por exemplo, extraindo apenas uma subdstring da cadeia de caracteres completa que ela deve detectar ou detectando apenas a primeira palavra em uma cadeia de caracteres de várias palavras ou incluindo símbolos extras ou caracteres na extração.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-149">For example by extracting only a substring of the full string it is supposed to detect, or picking up only the first word in a multi-word string, or including extra symbols or characters in the extraction.</span></span> <span data-ttu-id="ddbd8-150">Consulte [Linguagem de Expressão Regular - Referência Rápida](/dotnet/standard/base-types/regular-expression-language-quick-reference) para a referência de idioma de expressão regular.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-150">See [Regular Expression Language - Quick Reference](/dotnet/standard/base-types/regular-expression-language-quick-reference) for the regular expression language reference.</span></span> 

### <a name="troubleshooting"></a><span data-ttu-id="ddbd8-151">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="ddbd8-151">Troubleshooting</span></span>

<span data-ttu-id="ddbd8-152">Se você não encontrar nenhuma coincidente, tente o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ddbd8-152">If you don't find any matches, try the following:</span></span>
- <span data-ttu-id="ddbd8-153">Confirme se seus dados confidenciais foram carregados corretamente usando os comandos explicados na orientação para carregar seus dados confidenciais usando a [ferramenta EDM](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="ddbd8-153">Confirm that your sensitive data was uploaded correctly using the commands explained in [the guidance for uploading your sensitive data using the EDM tool](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>
- <span data-ttu-id="ddbd8-154">Verifique se os exemplos inseridos no item estão presentes em sua tabela de informações confidenciais e se os delimitadores ignorados estão corretos.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-154">Check that the examples you entered in the item are present in your sensitive information table and that the ignored delimiters are correct.</span></span>
- <span data-ttu-id="ddbd8-155">**Teste** o SIT usado quando configurou o elemento principal em cada um dos seus padrões.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-155">**Test** the SIT you used when you configured the primary element in each of your patterns.</span></span> <span data-ttu-id="ddbd8-156">Isso confirmará se o SIT é capaz de corresponder aos exemplos no item.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-156">This will confirm that the SIT is able to match the examples in the item.</span></span> 
  -  <span data-ttu-id="ddbd8-157">Se o SIT selecionado para um elemento primário no tipo EDM não encontrar uma combinação no item ou encontrar menos combinações do que você esperava, verifique se ele dá suporte a separadores e delimitadores existentes no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-157">If the SIT you selected for a primary element in the EDM type doesn't find a match in the item or finds fewer matches than you expected, check that it supports separators and delimiters that exist in the content.</span></span> <span data-ttu-id="ddbd8-158">Certifique-se de incluir os delimitadores ignorados definidos em seu esquema.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-158">Be sure to include the ignored delimiters defined in your schema.</span></span> 
  -  <span data-ttu-id="ddbd8-159">Se a **função Test** não detectar conteúdo algum, verifique se o SIT selecionado inclui requisitos para palavras-chave adicionais ou outras validações.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-159">If the **Test** function does not detect any content at all, check if the SIT you selected includes requirements for additional keywords or other validations.</span></span> <span data-ttu-id="ddbd8-160">Para os SITs integrados, consulte Definições de entidade de tipos de informações confidenciais para verificar quais são os [requisitos mínimos](sensitive-information-type-entity-definitions.md) para correspondência de cada tipo.</span><span class="sxs-lookup"><span data-stu-id="ddbd8-160">For the built-in SITs, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md) to verify what the minimum requirements are for matching each type.</span></span>
