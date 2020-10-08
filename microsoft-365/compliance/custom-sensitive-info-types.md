---
title: Tipos de informações confidenciais personalizadas para o DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Obtenha uma visão geral dos tipos de informações confidenciais personalizados para a prevenção contra perda de dados (DLP), como o padrão principal, a proximidade de caractere e o nível de confiança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21d0be23847a8fbd27b6082ca28cdca2d4eed05
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379177"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="1af6d-103">Tipos de informações confidenciais personalizadas</span><span class="sxs-lookup"><span data-stu-id="1af6d-103">Custom sensitive information types</span></span>

<span data-ttu-id="1af6d-104">O Microsoft 365 inclui muitos tipos de informações confidenciais integrados que estão prontos para usar em sua organização, como para a [DLP (prevenção de perda de dados)](data-loss-prevention-policies.md) ou com o [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="1af6d-104">Microsoft 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="1af6d-105">Os tipos de informações confidenciais integrados podem ajudar a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaporte e muito mais, com base em padrões definidos por uma expressão regular (regex) ou por uma função.</span><span class="sxs-lookup"><span data-stu-id="1af6d-105">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="1af6d-106">Para saber mais, consulte [O que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="1af6d-106">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="1af6d-107">Mas e se você precisar identificar e proteger um tipo diferente de informações confidenciais, como IDs de funcionários ou números de projetos, usando um formato específico para sua organização?</span><span class="sxs-lookup"><span data-stu-id="1af6d-107">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="1af6d-108">Para fazer isso, você pode criar um tipo de informação confidencial personalizado.</span><span class="sxs-lookup"><span data-stu-id="1af6d-108">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="1af6d-109">As partes fundamentais de um tipo personalizado de informações confidenciais são:</span><span class="sxs-lookup"><span data-stu-id="1af6d-109">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="1af6d-110">**Padrão principal**: números de ID de funcionário, números de projeto etc. Isso geralmente é identificado por uma expressão regular (RegEx), mas também pode ser uma lista de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="1af6d-110">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="1af6d-p103">**Evidências adicionais**: digamos que você esteja procurando por um número de ID de funcionário de nove dígitos. Nem todos os números de nove dígitos são números de ID de funcionário. Portanto, você pode pesquisar por texto adicional: palavras-chave como "funcionário", "crachá", "ID" ou outros padrões de texto com base em expressões regulares adicionais. Evidências de suporte (também chamadas de _suporte_ ou evidências _comprobatórias_) aumentam a probabilidade de que o número de nove dígitos no conteúdo seja realmente um número de ID de funcionário.</span><span class="sxs-lookup"><span data-stu-id="1af6d-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="1af6d-p104">**Caractere de proximidade**: faz sentido que quanto mais próximos o padrão principal e as evidências de suporte estejam entre si, mais provável seja que o conteúdo detectado seja o que você está procurando. Você pode especificar a distância de caracteres entre o padrão principal e as evidências de suporte (também conhecido como a _janela de proximidade_), conforme mostrado no seguinte diagrama:</span><span class="sxs-lookup"><span data-stu-id="1af6d-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagrama da janela de proximidade e evidências comprobatórias](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="1af6d-p105">**Nível de confiança**: quanto mais evidências de suporte você tiver, maior será a probabilidade de que uma correspondência contenha as informações confidenciais que está procurando. Você pode atribuir níveis mais altos de confiança para correspondências detectadas usando mais evidências.</span><span class="sxs-lookup"><span data-stu-id="1af6d-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="1af6d-p106">Quando satisfeito, um padrão retorna uma contagem e um nível de confiança, que você pode usar nas condições de políticas DLP. Ao adicionar uma condição para detectar um tipo de informação confidencial a uma política DLP, você poderá editar o nível de confiança e a contagem, conforme mostrado no seguinte diagrama:</span><span class="sxs-lookup"><span data-stu-id="1af6d-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Contagem de instâncias e opções de precisão de correspondência](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="1af6d-122">Criando tipos de informações confidenciais personalizadas</span><span class="sxs-lookup"><span data-stu-id="1af6d-122">Creating custom sensitive information types</span></span>

<span data-ttu-id="1af6d-123">Para criar tipos de informações confidenciais personalizadas no Centro de Conformidade e Segurança, você pode escolher entre várias opções:</span><span class="sxs-lookup"><span data-stu-id="1af6d-123">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="1af6d-124">**Use EDM** Você pode configurar tipos de informações confidenciais personalizadas usando a classificação baseada em EDM (Exact Data Match).</span><span class="sxs-lookup"><span data-stu-id="1af6d-124">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="1af6d-125">Esse método permite criar um tipo de informações confidenciais dinâmico usando um banco de dados seguro que você pode atualizar periodicamente.</span><span class="sxs-lookup"><span data-stu-id="1af6d-125">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="1af6d-126">Confira [Criar um tipo de informações confidenciais personalizadas com classificação baseada em Exact Data Match](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="1af6d-126">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="1af6d-127">**Use o PowerShell** Você pode configurar tipos de informações confidenciais personalizadas usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1af6d-127">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="1af6d-128">Embora esse método seja mais complexo do que usar a interface do usuário, você tem mais opções de configuração.</span><span class="sxs-lookup"><span data-stu-id="1af6d-128">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="1af6d-129">Consulte [Criar um tipo de informações confidenciais personalizadas no Centro de Conformidade e Segurança do PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1af6d-129">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="1af6d-130">**Usar a interface do usuário** Você pode configurar um tipo de informações confidenciais personalizadas usando o a interface do usuário do Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="1af6d-130">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="1af6d-131">Com esse método, você pode usar expressões comuns, palavras-chave e dicionários de palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="1af6d-131">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="1af6d-132">Para saber mais, confira [Criar um tipo de informações confidenciais personalizadas](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="1af6d-132">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1af6d-133">A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:</span><span class="sxs-lookup"><span data-stu-id="1af6d-133">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="1af6d-134">Chinês (simplificado)</span><span class="sxs-lookup"><span data-stu-id="1af6d-134">Chinese (simplified)</span></span>
> - <span data-ttu-id="1af6d-135">Chinês (tradicional)</span><span class="sxs-lookup"><span data-stu-id="1af6d-135">Chinese (traditional)</span></span>
> - <span data-ttu-id="1af6d-136">Coreano</span><span class="sxs-lookup"><span data-stu-id="1af6d-136">Korean</span></span>
> - <span data-ttu-id="1af6d-137">Japonês</span><span class="sxs-lookup"><span data-stu-id="1af6d-137">Japanese</span></span>
> 
><span data-ttu-id="1af6d-138">Esta visualização está apenas na nuvem comercial e a implementação está limitada para:</span><span class="sxs-lookup"><span data-stu-id="1af6d-138">This preview is only in the commercial cloud and the rollout is limited to:</span></span>
> - <span data-ttu-id="1af6d-139">Japão</span><span class="sxs-lookup"><span data-stu-id="1af6d-139">Japan</span></span>
> - <span data-ttu-id="1af6d-140">Coreia</span><span class="sxs-lookup"><span data-stu-id="1af6d-140">Korea</span></span>
> - <span data-ttu-id="1af6d-141">China</span><span class="sxs-lookup"><span data-stu-id="1af6d-141">China</span></span>
> - <span data-ttu-id="1af6d-142">Hong Kong</span><span class="sxs-lookup"><span data-stu-id="1af6d-142">Hong Kong</span></span>
> - <span data-ttu-id="1af6d-143">Macau</span><span class="sxs-lookup"><span data-stu-id="1af6d-143">Macau</span></span>
> - <span data-ttu-id="1af6d-144">Taiwan</span><span class="sxs-lookup"><span data-stu-id="1af6d-144">Taiwan</span></span>
>
><span data-ttu-id="1af6d-145">Este suporte está disponível para tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="1af6d-145">This support is available for sensitive information types.</span></span> <span data-ttu-id="1af6d-146">Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="1af6d-146">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

