---
title: Pesquisar e localizar dados pessoais
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a pesquisar e encontrar dados pessoais sujeitos a Regulamentações Gerais de Proteção de Dados (RGPD) no Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 50c8db59cfd5e9a7de3da0dc696227e85dab1cee
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208085"
---
# <a name="search-for-and-find-personal-data"></a><span data-ttu-id="5e1ab-103">Pesquisar e localizar dados pessoais</span><span class="sxs-lookup"><span data-stu-id="5e1ab-103">Search for and find personal data</span></span>

<span data-ttu-id="5e1ab-104">A grosso modo, o RGPD define dados pessoais como qualquer dado relativo a uma pessoa física identificada ou identificável que seja residente da União Europeia (UE).</span><span class="sxs-lookup"><span data-stu-id="5e1ab-104">Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="5e1ab-105">Artigo 4 – Definições</span><span class="sxs-lookup"><span data-stu-id="5e1ab-105">Article 4 – Definitions</span></span>

> <span data-ttu-id="5e1ab-106">"dados pessoais" são todas as informações relativas a uma pessoa física identificada ou identificável ("titular dos dados"); uma pessoa física identificável é alguém que pode ser identificado, direta ou indiretamente, em especial por referência a um identificador como um nome, um número de identificação, dados de localização, um identificador online ou por um ou mais elementos específicos da identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física;</span><span class="sxs-lookup"><span data-stu-id="5e1ab-106">'personal data' means any information relating to an identified or identifiable natural person ('data subject'); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="5e1ab-107">Este artigo demonstra como localizar dados pessoais armazenados no SharePoint Online e no OneDrive for Business (que inclui os sites de todos os grupos do Microsoft 365 e Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="5e1ab-107">This article demonstrates how to find personal data stored in SharePoint Online and OneDrive for Business (which includes the sites for all Microsoft 365 groups and Microsoft Teams).</span></span>

<span data-ttu-id="5e1ab-108">A localização de dados pessoais sujeitos ao GDPR se baseia no uso de tipos de informações confidenciais no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-108">Finding personal data subject to GDPR relies on using sensitive information types in Office 365.</span></span> <span data-ttu-id="5e1ab-109">Eles definem como o processo automatizado reconhece os tipos de informações específicas, como números de serviços de saúde e cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-109">These define how the automated process recognizes specific information types such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="5e1ab-110">Você pode usar as políticas de prevenção contra perda de dados para localizar dados pessoais no email enquanto está em trânsito.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-110">You can use data loss prevention policies to find personal data in mail while in transit.</span></span> <span data-ttu-id="5e1ab-111">Você pode usar os tipos de informações confidenciais que deseja para o RGPD localizar e proteger as informações pessoais conforme elas são enviadas por email.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-111">You can use the sensitive information types you curate for GDPR to find and protect personal information as it is sent through email.</span></span> <span data-ttu-id="5e1ab-112">Confira também, [Solicitações de entidades de dados GDPR gerenciados com a ferramenta de caso DSR no Centro de Conformidade & Segurança](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span><span class="sxs-lookup"><span data-stu-id="5e1ab-112">Also see [Managed GDPR data subject requests with the DSR case tool in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).</span></span>

## <a name="use-content-search-to-find-personal-data"></a><span data-ttu-id="5e1ab-113">Usar a Pesquisa de Conteúdo para localizar dados pessoais</span><span class="sxs-lookup"><span data-stu-id="5e1ab-113">Use Content Search to find personal data</span></span>

<span data-ttu-id="5e1ab-p102">A Microsoft recomenda uma abordagem em três etapas para localizar dados pessoais no Office 365. O restante deste tópico orienta sobre cada uma dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p102">Microsoft recommends a three-stage approach to finding personal data in Office 365. The rest of this topic provides guidance for each of these stages.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5e1ab-116"><strong>Etapa</strong></span><span class="sxs-lookup"><span data-stu-id="5e1ab-116"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="5e1ab-117"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="5e1ab-117"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5e1ab-118">1. Pesquisar tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="5e1ab-118">1. Search for sensitive information types</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e1ab-p103">Inicie usando os tipos de informações confidenciais para localizar dados pessoais. Crie uma consulta de Pesquisa de Conteúdo para cada tipo de informação confidencial. Execute a consulta e analise os resultados.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p103">Start by using sensitive information types to find personal data. Create a Content Search query for each sensitive information type. Run the query and analyze the results.</span></span></p>
<span data-ttu-id="5e1ab-122">Se necessário, adicione parâmetros às consultas para reduzir os falsos positivos:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-122">If needed, add parameters to the query to reduce false positives:</span></span> <li><span data-ttu-id="5e1ab-123">Intervalo de contagem</span><span class="sxs-lookup"><span data-stu-id="5e1ab-123">Count range</span></span></li>
    <li><span data-ttu-id="5e1ab-124">Intervalo de confiança</span><span class="sxs-lookup"><span data-stu-id="5e1ab-124">Confidence range</span></span></li>
    <li><span data-ttu-id="5e1ab-125">Outras propriedades ou operadores para consultas mais complexas</span><span class="sxs-lookup"><span data-stu-id="5e1ab-125">Other properties or operators for more complex queries</span></span></li>
<p><span data-ttu-id="5e1ab-126">Se necessário, modifique um tipo de informação confidencial para aprimorar o refinamento para a sua organização:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-126">If necessary, modify a sensitive information type to improve accuracy for your organization:</span></span></p>
<p><li><span data-ttu-id="5e1ab-127">Ajuste o nível de confiança diretamente no XML.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-127">Adjust the confidence level directly in the XML.</span></span></li></p>
<p><li><span data-ttu-id="5e1ab-128">Adicione palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-128">Add key words.</span></span></li></p>
<p><li><span data-ttu-id="5e1ab-129">Ajuste os requisitos de proximidade das palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-129">Adjust the proximity requirements for keywords.</span></span></li></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5e1ab-130">2. Usar a Keyword Query Language (KQL) para localizar dados pessoais adicionais em seu ambiente</span><span class="sxs-lookup"><span data-stu-id="5e1ab-130">2. Use Keyword Query Language (KQL) to find additional personal data in your environment</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e1ab-131">Para localizar dados não incluídos nos tipos de informações confidenciais, use a linguagem de consulta KQL para desenvolver consultas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-131">To find data not included in sensitive information types, use the KQL query language to develop custom queries.</span></span></p>
<p><span data-ttu-id="5e1ab-132">Teste os resultados da pesquisa e ajuste a cadeia de caracteres de consulta da KQL até atingir o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-132">Test the results of these searches and adjust the KQL query string until you achieve the expected result.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5e1ab-133">3. Criar novos tipos de informações confidenciais personalizados usando consultas KQL</span><span class="sxs-lookup"><span data-stu-id="5e1ab-133">3. Create new custom sensitive information types using the KQL queries</span></span></p></td>
<td align="left"><span data-ttu-id="5e1ab-p104">Após otimizar as consultas KQL para localizar os dados de destino, crie novos tipos de informações confidenciais personalizados usando essas consultas. Em seguida, você pode usar esses tipos de informações confidenciais personalizados com a Pesquisa de Conteúdo, com as políticas DLP e outras ferramentas e em outras consultas KQL.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p104">After optimizing KQL queries to find target data, create new custom sensitive information types using these queries. You can then use these custom sensitive information types with Content Search, in DLP policies and other tools, and within other KQL queries.</span></span></td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a><span data-ttu-id="5e1ab-136">Buscar tipos de informações confidenciais usando a Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="5e1ab-136">Search for sensitive information types using Content Search</span></span>

<span data-ttu-id="5e1ab-137">Começar a pesquisar dados pessoais usando os tipos de informações confidenciais incluídas no Office 365.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-137">Begin searching for personal data by using the sensitive information types that are included with Office 365.</span></span> <span data-ttu-id="5e1ab-138">Eles estão listados em Classificação no centro de segurança e no centro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-138">These are listed under Classification in the security center and compliance center.</span></span>

<span data-ttu-id="5e1ab-139">Este tópico inclui uma lista de alguns tipos de informações confidenciais que se aplicam a cidadãos na União Europeia.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-139">This topic includes a list of some sensitive information types that apply to citizens in the European Union.</span></span> <span data-ttu-id="5e1ab-140">Verifique o centro de segurança ou centro de conformidade para novas adições que podem ajudar com a conformidade GDPR.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-140">Check the security center or the compliance center for new additions that can help with GDPR compliance.</span></span>

<span data-ttu-id="5e1ab-141">Confira também este artigo: [Lista de tipos de informações confidenciais e para que serve cada um](https://support.office.com/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span><span class="sxs-lookup"><span data-stu-id="5e1ab-141">Also see this article: [List of sensitive information types and what each one looks for](https://support.office.com/article/What-the-sensitive-information-types-look-for-fd505979-76be-4d9f-b459-abef3fc9e86b).</span></span>

<span data-ttu-id="5e1ab-p107">Os tipos de informações confidenciais definem como o processo automatizado reconhecerá tipos específicos de informação, como números de contas bancárias, números de serviços de saúde e de cartões de crédito. Os tipos de informações confidenciais também são conhecidos como condições. Um tipo de informação confidencial se define por um padrão que pode ser identificado por uma expressão regular ou uma função. Além disso, podem-se usar evidências de comprovação como palavras-chave e somas de verificação para identificar um tipo de informação confidencial. Também se usa o nível de confiança e de proximidade no processo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p107">Sensitive information types define how the automated process recognizes specific information types such as bank account numbers, health service numbers, and credit card numbers. Sensitive information types are also referred to as conditions. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>

<span data-ttu-id="5e1ab-147">No momento, os tipos de informações confidenciais não podem ser usados para localizar dados em repouso nas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-147">At this time sensitive information types cannot be used to find data at rest in mailboxes.</span></span>

### <a name="using-content-search-with-sensitive-information-types"></a><span data-ttu-id="5e1ab-148">Usar a Pesquisa de Conteúdo com os tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="5e1ab-148">Using Content Search with sensitive information types</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5e1ab-149"><strong>Etapa</strong></span><span class="sxs-lookup"><span data-stu-id="5e1ab-149"><strong>Step</strong></span></span></th>
<th align="left"><span data-ttu-id="5e1ab-150"><strong>Mais informações</strong></span><span class="sxs-lookup"><span data-stu-id="5e1ab-150"><strong>More information</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p><span data-ttu-id="5e1ab-151">Acessar a Pesquisa de Conteúdo no Centro de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="5e1ab-151">Go to Content Search in the Security and Compliance Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e1ab-152">No painel esquerdo do Centro de Conformidade e Segurança, clique em **Pesquisa&amp; investigação** &gt; **Pesquisa de Conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-152">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** &gt; **Content search**.</span></span></p>
<p><span data-ttu-id="5e1ab-153">Confira <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Executar uma Pesquisa de Conteúdo no Centro de Conformidade e &amp; Segurança</a>.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-153">See <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Run a Content Search in the Security &amp; Compliance Center</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5e1ab-154">Criar um novo item de pesquisa para cada tipo de informação confidencial</span><span class="sxs-lookup"><span data-stu-id="5e1ab-154">Create a new search item for each sensitive information type</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e1ab-155">Use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-155">Use the following syntax:</span></span></p>
<blockquote>
<p><span data-ttu-id="5e1ab-156">SensitiveType:"&lt;tipo&gt;"</span><span class="sxs-lookup"><span data-stu-id="5e1ab-156">SensitiveType:"&lt;type&gt;"</span></span></p>
</blockquote>
<p><span data-ttu-id="5e1ab-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-157">For example:</span></span></p>
<blockquote>
<p><span data-ttu-id="5e1ab-158">SensitiveType:&quot;Número de passaporte francês&quot;</span><span class="sxs-lookup"><span data-stu-id="5e1ab-158">SensitiveType:&quot;France Passport Number&quot;</span></span></p>
</blockquote>
<p><span data-ttu-id="5e1ab-p108">Amplie a pesquisa para o SharePoint (inclui o OneDrive for Business). A sintaxe deve ser exata e não deve haver erros de digitação ou espaços extras.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p108">Scope the search to SharePoint (includes OneDrive for Business). Make sure the syntax is exact and there are no extra spaces or typos.</span></span></p>
<p><span data-ttu-id="5e1ab-161">Confira <a href="https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Criar uma consulta para localizar dados confidenciais armazenados em sites</a>.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-161">See <a href="https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836">Form a query to find sensitive data stored on sites</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5e1ab-162">Examinar os resultados de cada pesquisa</span><span class="sxs-lookup"><span data-stu-id="5e1ab-162">Review the results for each search</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e1ab-163">Identifique esses tipos de problemas para determinar se a precisão da consulta está adequada:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-163">Look for these types of issues to determine if the query accuracy is on target:</span></span></p>
<p><li><span data-ttu-id="5e1ab-164">Muitos falsos positivos</span><span class="sxs-lookup"><span data-stu-id="5e1ab-164">Many false positives</span></span></li></p>
<p><li><span data-ttu-id="5e1ab-165">Falta de instâncias de dados conhecidos</span><span class="sxs-lookup"><span data-stu-id="5e1ab-165">Missing known instances of data</span></span></li></p>
<p><span data-ttu-id="5e1ab-166">Confira <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Exportar os resultados da Pesquisa de Conteúdo do &amp;Centro de Conformidade e Segurança</a>.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-166">See <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Export Content Search results from the Security &amp; Compliance Center</a>.</span></span></p>
<p><span data-ttu-id="5e1ab-167">Observação: se estiver usando o Mozilla Firefox ou o Chrome, pode ser preciso baixar antes os relatórios usando o Internet Explorer ou o Microsoft Edge para instalar o suplemento necessário.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-167">Note: if you're using Mozilla Firefox or Chrome, you might need to first download reports using Internet Explorer or Edge in order to install the required add-in.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a><span data-ttu-id="5e1ab-168">Tipos de informações confidenciais para os dados de cidadãos da União Europeia</span><span class="sxs-lookup"><span data-stu-id="5e1ab-168">Sensitive information types for EU citizen data</span></span>

<span data-ttu-id="5e1ab-p109">Comece com esses tipos de informações confidenciais, muitos outros chegarão em breve para os dados pessoais na União Europeia.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p109">Start with these sensitive information types. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

> <span data-ttu-id="5e1ab-171">Número nacional belga</span><span class="sxs-lookup"><span data-stu-id="5e1ab-171">Belgium National Number</span></span>
>
> <span data-ttu-id="5e1ab-172">Número de Cartão de Crédito</span><span class="sxs-lookup"><span data-stu-id="5e1ab-172">Credit Card Number</span></span>
>
> <span data-ttu-id="5e1ab-173">Número da carteira de identidade croata</span><span class="sxs-lookup"><span data-stu-id="5e1ab-173">Croatia Identity Card Number</span></span>
>
> <span data-ttu-id="5e1ab-174">Número de identificação pessoal (NIB) croata</span><span class="sxs-lookup"><span data-stu-id="5e1ab-174">Croatia Personal Identification (OIB) Number</span></span>
>
> <span data-ttu-id="5e1ab-175">Número da carteira nacional de identidade tcheca</span><span class="sxs-lookup"><span data-stu-id="5e1ab-175">Czech National Identity Card Number</span></span>
>
> <span data-ttu-id="5e1ab-176">Número de identificação pessoal dinamarquês</span><span class="sxs-lookup"><span data-stu-id="5e1ab-176">Denmark Personal Identification Number</span></span>
>
> <span data-ttu-id="5e1ab-177">Número de cartão de débito da UE</span><span class="sxs-lookup"><span data-stu-id="5e1ab-177">EU Debit Card Number</span></span>
>
> <span data-ttu-id="5e1ab-178">RG nacional finlandês</span><span class="sxs-lookup"><span data-stu-id="5e1ab-178">Finland National ID</span></span>
>
> <span data-ttu-id="5e1ab-179">Número de passaporte finlandês</span><span class="sxs-lookup"><span data-stu-id="5e1ab-179">Finland Passport Number</span></span>
>
> <span data-ttu-id="5e1ab-180">Número da carteira de motorista francesa</span><span class="sxs-lookup"><span data-stu-id="5e1ab-180">France Driver's License Number</span></span>
>
> <span data-ttu-id="5e1ab-181">Carteira nacional de identidade francesa (CNI)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-181">France National ID Card (CNI)</span></span>
>
> <span data-ttu-id="5e1ab-182">Número de passaporte francês</span><span class="sxs-lookup"><span data-stu-id="5e1ab-182">France Passport Number</span></span>
>
> <span data-ttu-id="5e1ab-183">Número da segurança social francesa (INSEE)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-183">France Social Security Number (INSEE)</span></span>
>
> <span data-ttu-id="5e1ab-184">Número de carteira de motorista da Alemanha</span><span class="sxs-lookup"><span data-stu-id="5e1ab-184">German Driver's License Number</span></span>
>
> <span data-ttu-id="5e1ab-185">Número da carteira de identidade alemã</span><span class="sxs-lookup"><span data-stu-id="5e1ab-185">Germany Identity Card Number</span></span>
>
> <span data-ttu-id="5e1ab-186">Número de passaporte alemão</span><span class="sxs-lookup"><span data-stu-id="5e1ab-186">German Passport Number</span></span>
>
> <span data-ttu-id="5e1ab-187">Carteira nacional de identidade grega</span><span class="sxs-lookup"><span data-stu-id="5e1ab-187">Greece National ID Card</span></span>
>
> <span data-ttu-id="5e1ab-188">Número internacional de conta bancária (IBAN)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-188">International Banking Account Number (IBAN)</span></span>
>
> <span data-ttu-id="5e1ab-189">Endereço IP</span><span class="sxs-lookup"><span data-stu-id="5e1ab-189">IP Address</span></span>
>
> <span data-ttu-id="5e1ab-190">Número de serviço público pessoal (PPS) irlandês</span><span class="sxs-lookup"><span data-stu-id="5e1ab-190">Ireland Personal Public Service (PPS) Number</span></span>
>
> <span data-ttu-id="5e1ab-191">Número de carteira de motorista italiana</span><span class="sxs-lookup"><span data-stu-id="5e1ab-191">Italy's Driver's License Number</span></span>
>
> <span data-ttu-id="5e1ab-192">Número do Serviço do Cidadão (BSN) da Países Baixos</span><span class="sxs-lookup"><span data-stu-id="5e1ab-192">Netherlands Citizen's Service (BSN) Number</span></span>
>
> <span data-ttu-id="5e1ab-193">Número de identidade norueguesa</span><span class="sxs-lookup"><span data-stu-id="5e1ab-193">Norway Identity Number</span></span>
>
> <span data-ttu-id="5e1ab-194">Carteira de identidade polonesa</span><span class="sxs-lookup"><span data-stu-id="5e1ab-194">Poland Identity Card</span></span>
>
> <span data-ttu-id="5e1ab-195">RG nacional polonês (PESEL)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-195">Poland National ID (PESEL)</span></span>
>
> <span data-ttu-id="5e1ab-196">Passaporte polonês</span><span class="sxs-lookup"><span data-stu-id="5e1ab-196">Poland Passport</span></span>
>
> <span data-ttu-id="5e1ab-197">Número do cartão do cidadão português</span><span class="sxs-lookup"><span data-stu-id="5e1ab-197">Portugal Citizen Card Number</span></span>
>
> <span data-ttu-id="5e1ab-198">Número da segurança social espanhola (SSN)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-198">Spain Social Security Number (SSN)</span></span>
>
> <span data-ttu-id="5e1ab-199">RG nacional sueco</span><span class="sxs-lookup"><span data-stu-id="5e1ab-199">Sweden National ID</span></span>
>
> <span data-ttu-id="5e1ab-200">Número de passaporte sueco</span><span class="sxs-lookup"><span data-stu-id="5e1ab-200">Sweden Passport Number</span></span>
>
> <span data-ttu-id="5e1ab-p110">Número de carteira de motorista do Reino Unido</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p110">U.K. Driver's License Number</span></span>
>
> <span data-ttu-id="5e1ab-p111">Número do título de eleitor britânico</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p111">U.K. Electoral Roll Number</span></span>
>
> <span data-ttu-id="5e1ab-p112">Número do serviço nacional de saúde britânico</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p112">U.K. National Health Service Number</span></span>
>
> <span data-ttu-id="5e1ab-p113">Número do seguro nacional britânico (NINO)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p113">U.K. National Insurance Number (NINO)</span></span>
>
> <span data-ttu-id="5e1ab-p114">Número de passaporte americano/britânico</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p114">U.S./U.K. Passport Number</span></span>

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a><span data-ttu-id="5e1ab-211">Adicionar parâmetros a uma consulta de tipo de informação confidencial para refinar os resultados</span><span class="sxs-lookup"><span data-stu-id="5e1ab-211">Add parameters to a sensitive information type query to hone the results</span></span>

<span data-ttu-id="5e1ab-212">É possível adicionar esses parâmetros a uma consulta de tipo de informação confidencial:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-212">You can add these parameters to a sensitive information type query:</span></span>

-   <span data-ttu-id="5e1ab-213">Intervalo de contagem: define o número de ocorrências de informações confidenciais que um documento precisa conter para ser incluído nos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-213">Count range — define the number of occurrences of sensitive information a document needs to contain before it's included in the query results.</span></span>

-   <span data-ttu-id="5e1ab-214">Intervalo de confiança: o nível de confiança a que o tipo confidencial detectado realmente corresponde, como 85% (85%).</span><span class="sxs-lookup"><span data-stu-id="5e1ab-214">Confidence range — the level of confidence that the detected sensitive type is actually a match, such as 85 (85%).</span></span>

<span data-ttu-id="5e1ab-215">Sintaxe:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-215">Syntax:</span></span>

-   <span data-ttu-id="5e1ab-216">SensitiveType:"\<tipo\>|\<intervalo de contagem\>|\<intervalo de confiança\>"</span><span class="sxs-lookup"><span data-stu-id="5e1ab-216">SensitiveType:"\<type\>|\<count range\>|\<confidence range\>"</span></span>

<span data-ttu-id="5e1ab-217">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="5e1ab-217">Examples:</span></span>

-   <span data-ttu-id="5e1ab-218">SensitiveType:"Número de cartão de crédito|5" (retornará apenas os documentos que contenham exatamente cinco números de cartão de crédito)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-218">SensitiveType:"Credit Card Number|5" (return only documents that contain exactly five credit card numbers)</span></span>

-   <span data-ttu-id="5e1ab-219">SensitiveType:"Número de cartão de crédito|\*|85.." (o intervalo de confiança é 85% ou mais)</span><span class="sxs-lookup"><span data-stu-id="5e1ab-219">SensitiveType:"Credit Card Number|\*|85.." (confidence range is 85 percent or higher)</span></span>

<span data-ttu-id="5e1ab-220">Observação: "SensitiveType" diferencia maiúsculas e minúsculas, mas o restante da consulta não.</span><span class="sxs-lookup"><span data-stu-id="5e1ab-220">Note: "SensitiveType" is case sensitive, but the rest of the query is not.</span></span>

<span data-ttu-id="5e1ab-p115">Também é possível usar operadores e propriedades para ilustrar como você pode refinar suas consultas. Para obter mais informações e exemplos, confira [Criar uma consulta para localizar dados confidenciais armazenados em sites](https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span><span class="sxs-lookup"><span data-stu-id="5e1ab-p115">You can also use properties, and operators to illustrate how you can refine your queries. For more information and examples, see [Form a query to find sensitive data stored on sites](https://support.office.com/article/Form-a-query-to-find-sensitive-data-stored-on-sites-3019fbc5-7f15-4972-8d0e-dc182dc7f836).</span></span>
