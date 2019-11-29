---
title: Desenvolver um esquema de classificação para dados pessoais
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Determine se sua organização implementará os rótulos como parte do plano do RGPD.
ms.openlocfilehash: 4470f766ad2f8fd2d914e0e45deac8604028ddb5
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615641"
---
# <a name="architect-a-classification-schema-for-personal-data"></a><span data-ttu-id="bdab6-103">Desenvolver um esquema de classificação para dados pessoais</span><span class="sxs-lookup"><span data-stu-id="bdab6-103">Architect a classification schema for personal data</span></span>

<span data-ttu-id="bdab6-p101">Outros artigos desta série se concentram no uso de tipos de informações confidenciais para identificar dados pessoais sujeitos ao RGPD. Os tipos de informações confidenciais são uma forma de classificação, que pode ser tudo de que você precisa. No entanto, muitas organizações implementam uma estratégia de governança de dados mais ampla usando rótulos. Use esse tópico para decidir se também desejará implementar os rótulos como parte do seu plano de RGPD. Em caso afirmativo, este tópico dará algumas diretrizes e exemplos.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p101">Previous articles in this series focus on using sensitive information types to identify personal data that is subject to GDPR. Sensitive information types are a form of classification. This might be all the classification you need. However, many organizations implement a broader data governance strategy using labels. Use this topic to decide if you also want to implement labels as part of your GDPR plan. If you do, this topic provides some guidance and examples.</span></span>

<span data-ttu-id="bdab6-p102">Observação: definir um esquema de classificação para uma organização e configurar políticas, rótulos e condições requer planejamento e preparação cuidadosos. É importante reforçar que este não é um processo de TI. Trabalhe com sua equipe jurídica e de conformidade para desenvolver uma classificação apropriada e um esquema de rotulação para os dados da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p102">Note: Defining a classification schema for an organization and configuring policies, labels, and conditions requires careful planning and preparation. It is important to realize that this is not an IT driven process. Be sure to work with your legal and compliance team to develop an appropriate classification and labeling schema for your organization’s data.</span></span>

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a><span data-ttu-id="bdab6-113">Decidir se vai usar rótulos além dos tipos de dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="bdab6-113">Decide if you are using labels in addition to sensitive data types</span></span>

<span data-ttu-id="bdab6-p103">É possível abordar a classificação de informações pessoais no Office 365 de duas abordagens. Qualquer uma pode ser usada para a proteção de RGPD. Se decidir usar somente tipos de informações confidenciais para classificação, ignore o restante deste tópico.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p103">You can take one of two approaches for classification in Office 365 for personal information. Either of these can be used for GDPR protection. If decide to use only sensitive information types for classification, you can skip the rest of this topic.</span></span>

<span data-ttu-id="bdab6-117">Selecione uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="bdab6-117">Choose one of the following options.</span></span>

### <a name="option-1-use-only-office-365-sensitive-information-types"></a><span data-ttu-id="bdab6-118">Opção 1: usar somente os tipos de informações confidenciais do Office 365</span><span class="sxs-lookup"><span data-stu-id="bdab6-118">Option 1: Use only Office 365 sensitive information types</span></span>

- <span data-ttu-id="bdab6-119">Os tipos de informações confidenciais funcionam bem para identificar e proteger os dados pessoais sujeitos ao RGPD e outros tipos de regulamentações.</span><span class="sxs-lookup"><span data-stu-id="bdab6-119">Sensitive information types work well to identify and protect personal data subject to GDPR and other types of regulations.</span></span>

- <span data-ttu-id="bdab6-120">Eles são mais simples de usar caso sua organização já não tenha ou planeje implementar um plano de governança de dados mais amplo com uso de rótulos.</span><span class="sxs-lookup"><span data-stu-id="bdab6-120">These are simpler to use if your organization doesn’t already have or plan to implement a broader data governance plan using labels.</span></span>

- <span data-ttu-id="bdab6-121">Eles trabalham com regras de DLP (assim como os rótulos do Office).</span><span class="sxs-lookup"><span data-stu-id="bdab6-121">These work with DLP rules (so do retention labels).</span></span>

- <span data-ttu-id="bdab6-122">Tipos de informações confidenciais funcionam com Segurança de aplicativos de nuvem, assim será possível detectar informações confidenciais em outros aplicativos SaaS.</span><span class="sxs-lookup"><span data-stu-id="bdab6-122">Sensitive information types work with Cloud App Security so you can detect sensitive information in other SaaS apps.</span></span>

### <a name="option-2-use-sensitive-information-types--retention-labels"></a><span data-ttu-id="bdab6-123">Opção 2: usar os tipos de informações confidenciais + rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="bdab6-123">Option 2: Use sensitive information types + retention labels</span></span>

- <span data-ttu-id="bdab6-124">Será necessário que os tipos de informações confidenciais apliquem rótulos automaticamente aos dados pessoais sujeitos ao RGPD, o que faz deles um pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="bdab6-124">You’ll need sensitive information types to automatically apply labels to personal data that is subject to GDPR, so these are a prerequisite.</span></span>

- <span data-ttu-id="bdab6-125">Usar a retenção de rótulos permite incluir dados pessoais que são sujeitos ao RGPD em um plano mais amplo de governança de dados para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="bdab6-125">Using retention labels allows you to include personal data that is subject to GDPR into a broader data governance plan for your organization.</span></span>

## <a name="develop-a-label-schema-that-includes-personal-data"></a><span data-ttu-id="bdab6-126">Desenvolver um esquema de rotulação que inclui dados pessoais</span><span class="sxs-lookup"><span data-stu-id="bdab6-126">Develop a label schema that includes personal data</span></span>

<span data-ttu-id="bdab6-p104">Antes de usar os recursos técnicos para aplicar rótulos e proteção, primeiro defina na sua organização um esquema de classificação. Ela pode já ter um, o que facilita adicionar dados pessoais. Este tópico inclui um exemplo de esquema de classificação. Você pode usá-lo como ponto de partida, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p104">Before using technical capabilities to apply labels and protection, first work across your organization to define a classification schema. Your organization might already have a classification schema, which makes it easier to add personal data. This topic includes an example classification schema. You can use this as a starting point, if needed.</span></span>

### <a name="getting-started"></a><span data-ttu-id="bdab6-131">Introdução</span><span class="sxs-lookup"><span data-stu-id="bdab6-131">Getting started</span></span>

<span data-ttu-id="bdab6-p105">Comece por escolher a quantidade e os nomes dos rótulos a implementar. Faça isso sem se preocupar com a tecnologia a se usar nem com como os rótulos serão aplicados. Aplique esse esquema em toda a organização, incluindo os dados guardados no local e em outros serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p105">Begin by deciding on the number and names of labels to implement. Do this activity without worrying about which technology to use and how labels will be applied. Apply this schema universally throughout your organization, including data that resides on premises and in other cloud services.</span></span>

### <a name="recommendations"></a><span data-ttu-id="bdab6-135">Recomendações</span><span class="sxs-lookup"><span data-stu-id="bdab6-135">Recommendations</span></span> 

<span data-ttu-id="bdab6-136">Ao criar e implementar políticas, rótulos e condições, considere essas recomendações:</span><span class="sxs-lookup"><span data-stu-id="bdab6-136">When designing and implementing policies, labels and conditions, consider following these recommendations:</span></span>

- <span data-ttu-id="bdab6-p106">Use esquemas de classificação existentes (se houver)&ndash; muitas organizações já estão usando a classificação de dados de alguma forma. Avalie com cuidado o esquema de rotulação existente e, se possível, use-o como está. Usar rótulos familiares reconhecíveis pelo usuário final ajuda na adesão.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p106">Use existing classification schema (if any) — Many organizations already are using data classification in some form. Carefully evaluate the existing label schema and if possible use it as is. Using familiar labels that are recognizable to the end-user will drive adoption.</span></span>

- <span data-ttu-id="bdab6-p107">Comece com políticas e rótulos padrão&ndash; todas as soluções vêm com um conjunto de políticas e rótulos predefinidos. Avalie-os com cuidado, de acordo com os requisitos corporativos e jurídicos da organização e considere usar esses em vez de criar outros.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p107">Start with default policies and labels — All solutions come with a set of predefined policies and labels. Carefully evaluate these against the organizations legal and business requirements and consider using them instead of creating new ones.</span></span>

- <span data-ttu-id="bdab6-p108">Comece aos poucos&ndash; não há limites para a quantidade de rótulos que podem ser criados. Contudo, uma quantidade imensa de rótulos e sub-rótulos pode impactar negativamente a adesão. Oferecer muitas opções é quase como não oferecer nenhuma.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p108">Start small — There is virtually no limit to the number of labels that can be created. However, large numbers of labels and sub-labels will negatively impact the adoption. Too many choices often means no choice at all.</span></span>

- <span data-ttu-id="bdab6-145">Utilize cenários e casos de uso&ndash; identifique os casos de uso comuns na organização e use os cenários derivados do RGPD para verificar se a configuração pensada para a rotulação e classificação funcionarão na prática.</span><span class="sxs-lookup"><span data-stu-id="bdab6-145">Use scenarios and use cases — Identify common use cases within the organization and use scenarios derived from the GDPR to verify if the envisioned label and classification configuration will work in practice.</span></span>

- <span data-ttu-id="bdab6-p109">Questione cada solicitação por um novo rótulo&ndash; será que cada cenário ou caso de uso precisa mesmo de um novo rótulo ou pode-se usar o que já existe? Manter a quantidade de rótulos no mínimo facilita a adesão.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p109">Question every request for a new label, does every scenario or use case really need a new label or can we use what we already have? Keeping the number of labels to a minimum improves adoption.</span></span>

- <span data-ttu-id="bdab6-p110">Use sub-rótulos para os departamentos principais&ndash; alguns departamentos terão necessidades específicas que exigirão rótulos específicos. Defina esses rótulos como sub-rótulos de um rótulo existente e considere usar políticas com escopo que sejam atribuídas a grupos de usuários em vez de a toda a organização.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p110">Use sub-labels for key departments, some departments will have specific needs that require specific labels. Define these labels as sub-labels to an existing label and consider using scoped policies that are assigned to user groups instead of globally.</span></span>

- <span data-ttu-id="bdab6-p111">Considere usar políticas com escopo&ndash; políticas direcionadas a subconjuntos de usuários impedirão uma "sobrecarga de rótulos". Uma política com escopo permite atribuir (sub-)rótulos por função ou departamento específico apenas a funcionários que trabalhem para o departamento específico.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p111">Consider scoped policies, polices targeted at subsets of users will prevent "label overload". A scoped policy enables assigning role or department specific (sub-)labels to just employees that work for that specific department.</span></span>

- <span data-ttu-id="bdab6-p112">Use nomes significativos para os rótulos&ndash; recomenda-se não usar jargões, padrões ou acrônimos como nomes de rótulos. Tente usar nomes que façam sentido para o usuário final e melhore a adoção. Em vez de usar rótulos como PII, PCI, HIPAA, LBI, MBI e HBI, considere nomes como Não Corporativo, Público, Geral, Confidencial e Altamente Confidencial.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p112">Use meaningful label names, it is recommended not to use jargon, standards or acronyms as label names. Try to use names that resonate with the end user to improve adoption. Instead of using labels like PII, PCI, HIPAA, LBI, MBI and HBI consider names like Non-Business, Public, General, Confidential and Highly Confidential.</span></span>

### <a name="example-classification-schema"></a><span data-ttu-id="bdab6-155">Exemplo de esquema de classificação</span><span class="sxs-lookup"><span data-stu-id="bdab6-155">Example classification schema</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bdab6-156"><strong>Nome do rótulo</strong></span><span class="sxs-lookup"><span data-stu-id="bdab6-156"><strong>Label name</strong></span></span></th>
<th align="left"><span data-ttu-id="bdab6-157"><strong>Descrição</strong></span><span class="sxs-lookup"><span data-stu-id="bdab6-157"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="bdab6-158">Pessoal</span><span class="sxs-lookup"><span data-stu-id="bdab6-158">Personal</span></span></td>
<td align="left"><span data-ttu-id="bdab6-159">Dados não corporativos, apenas para uso pessoal.</span><span class="sxs-lookup"><span data-stu-id="bdab6-159">Non-business data, for personal use only.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bdab6-160">Público</span><span class="sxs-lookup"><span data-stu-id="bdab6-160">Public</span></span></td>
<td align="left"><span data-ttu-id="bdab6-161">Dados corporativos especificamente preparados e aprovados para o público.</span><span class="sxs-lookup"><span data-stu-id="bdab6-161">Business data that is specifically prepared and approved for public consumption.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="bdab6-162">Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="bdab6-162">Customer data</span></span></td>
<td align="left"><span data-ttu-id="bdab6-p113">Dados corporativos que contêm informações de identificação pessoal. Exemplos são números de cartão de crédito, de contas bancárias e de cadastros de pessoas físicas.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p113">Business data that contains personal identifiable information. Examples are credit card numbers, bank account numbers, and social security numbers.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bdab6-165">Dados de RH</span><span class="sxs-lookup"><span data-stu-id="bdab6-165">HR data</span></span></td>
<td align="left"><span data-ttu-id="bdab6-166">Dados de recursos humanos sobre funcionários da Contoso, como matrícula e salário.</span><span class="sxs-lookup"><span data-stu-id="bdab6-166">Human Resource data about Contoso employees, such as employee number and salary data.</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="bdab6-167">Confidencial</span><span class="sxs-lookup"><span data-stu-id="bdab6-167">Confidential</span></span></td>
<td align="left"><span data-ttu-id="bdab6-p114">Dados corporativos confidenciais que poderiam causar danos à empresa se compartilhados com pessoas não autorizadas. Exemplos incluem contratos, relatórios de segurança, resumos de previsões de mercado e dados de contas de vendas.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p114">Sensitive business data that could cause damage to the business if shared with unauthorized people. Examples include contracts, security reports, forecast summaries, and sales account data.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bdab6-170">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="bdab6-170">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="bdab6-p115">Dados corporativos altamente confidenciais que poderiam causar danos à empresa se compartilhados com pessoas não autorizadas. Exemplos incluem informações de funcionários e clientes, senhas, códigos-fonte e relatórios financeiros prévios.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p115">Very sensitive business data that would cause damage to the business if it was shared with unauthorized people. Examples include employee and customer information, passwords, source code, and pre-announced financial reports.</span></span></td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a><span data-ttu-id="bdab6-173">Definir um critério taxonômico e de pesquisa para todos os rótulos</span><span class="sxs-lookup"><span data-stu-id="bdab6-173">Define a taxonomy and search criteria for each label</span></span>

<span data-ttu-id="bdab6-p116">Após desenvolver um esquema de classificação para a sua organização, a próxima etapa é desenvolver critérios taxonômicos e de pesquisa para localizar os dados. Para dados pessoais, você já concluiu esse trabalho identificando os tipos de informações confidenciais e também personalizando ou criando novos tipos de informações confidenciais para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p116">After developing a classification schema for your organization, the next step is to develop the taxonomy and search criteria for finding this data. For personal data, you’ve already completed this work by identifying sensitive information types and also by customizing or creating new sensitive information types for your environment.</span></span>

<span data-ttu-id="bdab6-p117">A tabela a seguir oferece um exemplo de esquema de critério taxonômico e de pesquisa para uma organização. Os rótulos são ordenados por nível de confidencialidade, do menos afetado ao mais importante, para garantir que os dados que atendam a várias condições de rotulação recebam o rótulo apropriado.</span><span class="sxs-lookup"><span data-stu-id="bdab6-p117">The following table provides an example schema, taxonomy, and search criteria for an organization. The labels are ordered by sensitivity level from least sensitive to most sensitive to ensure that data that matches multiple label conditions is assigned the appropriate label.</span></span>

<span data-ttu-id="bdab6-178">Observação: o exemplo de configuração tem fins meramente ilustrativos e não deve ser considerado referência ou orientação de implantação.</span><span class="sxs-lookup"><span data-stu-id="bdab6-178">Note: The configuration example is provided for illustration only and is not intended as deployment guidance or reference.</span></span>

<span data-ttu-id="bdab6-179">A lição mais importante é que o esforço que você fizer para classificar os dados pessoais para estar em conformidade com o RGPD esteja alinhado aos objetivos de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="bdab6-179">The important takeaway is to ensure that the work you invest to classify personal data for GDPR compliance fits together with the objectives for your entire organization.</span></span>

### <a name="example-schema-taxonomy-and-search-criteria"></a><span data-ttu-id="bdab6-180">Exemplo de esquema de critério taxonômico e de pesquisa</span><span class="sxs-lookup"><span data-stu-id="bdab6-180">Example schema, taxonomy, and search criteria</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bdab6-181"><strong>Rótulo</strong></span><span class="sxs-lookup"><span data-stu-id="bdab6-181"><strong>Label</strong></span></span></th>
<th align="left"><span data-ttu-id="bdab6-182"><strong>Taxonomia</strong></span><span class="sxs-lookup"><span data-stu-id="bdab6-182"><strong>Taxonomy</strong></span></span></th>
<th align="left"><span data-ttu-id="bdab6-183"><strong>Método</strong></span><span class="sxs-lookup"><span data-stu-id="bdab6-183"><strong>Method</strong></span></span></th>
<th align="left"><span data-ttu-id="bdab6-184"><strong>Sintaxe de pesquisa</strong></span><span class="sxs-lookup"><span data-stu-id="bdab6-184"><strong>Search syntax</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="bdab6-185">Pessoal</span><span class="sxs-lookup"><span data-stu-id="bdab6-185">Personal</span></span></td>
<td align="left"><span data-ttu-id="bdab6-186">Documentos rotulados manualmente como pessoais pelo usuário final.</span><span class="sxs-lookup"><span data-stu-id="bdab6-186">Documents manually labelled personal by the end user.</span></span></td>
<td align="left"><span data-ttu-id="bdab6-187">Manual</span><span class="sxs-lookup"><span data-stu-id="bdab6-187">Manual</span></span></td>
<td align="left"><span data-ttu-id="bdab6-188">Documentos rotulados manualmente como pessoais pelo usuário final.</span><span class="sxs-lookup"><span data-stu-id="bdab6-188">Documents manually labelled personal by the end user.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bdab6-189">Público</span><span class="sxs-lookup"><span data-stu-id="bdab6-189">Public</span></span></td>
<td align="left"><span data-ttu-id="bdab6-190">Documentos que contenham a frase aprovado, independente da capitalização, para o lançamento público ##/### em que # representa qualquer dígito.</span><span class="sxs-lookup"><span data-stu-id="bdab6-190">Documents containing the case insensitive phrase Approved for Public Release ##/#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="bdab6-191">KQL</span><span class="sxs-lookup"><span data-stu-id="bdab6-191">KQL</span></span></p>
<p><span data-ttu-id="bdab6-192">RegEx</span><span class="sxs-lookup"><span data-stu-id="bdab6-192">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="bdab6-193">KQL – Aprovado para lançamento público\*</span><span class="sxs-lookup"><span data-stu-id="bdab6-193">KQL — Approved for Public Release\*</span></span></p>
<p><span data-ttu-id="bdab6-194">RegEx — (?i)(\bAprovado para Publicação \d{2}\/\d{4}\b)</span><span class="sxs-lookup"><span data-stu-id="bdab6-194">RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="bdab6-195">Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="bdab6-195">Customer data</span></span></td>
<td align="left"><span data-ttu-id="bdab6-196">Tipos de informações confidenciais para dados de cidadãos da UE.</span><span class="sxs-lookup"><span data-stu-id="bdab6-196">Sensitive information types for EU citizen data.</span></span></td>
<td align="left"><span data-ttu-id="bdab6-197">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="bdab6-197">Sensitive information types</span></span></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bdab6-198">Recursos humanos – dados de funcionários</span><span class="sxs-lookup"><span data-stu-id="bdab6-198">Human Resources — Employee Data</span></span></td>
<td align="left"><span data-ttu-id="bdab6-199">Documentos que incluam a identificação do funcionário, que diferenciam maiúsculas de minúsculas, no formato CONTOSO-9##### em que # representa qualquer dígito.</span><span class="sxs-lookup"><span data-stu-id="bdab6-199">Documents that include the case sensitive employee id in the format CONTOSO-9##### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="bdab6-200">KQL</span><span class="sxs-lookup"><span data-stu-id="bdab6-200">KQL</span></span></p>
<p><span data-ttu-id="bdab6-201">RegEx</span><span class="sxs-lookup"><span data-stu-id="bdab6-201">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="bdab6-202">KQL – CONTOSO-9\*</span><span class="sxs-lookup"><span data-stu-id="bdab6-202">KQL — CONTOSO-9\*</span></span></p>
<p><span data-ttu-id="bdab6-203">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="bdab6-203">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="bdab6-204">Recursos humanos – dados salariais</span><span class="sxs-lookup"><span data-stu-id="bdab6-204">Human Resources — Salary Data</span></span></td>
<td align="left"><span data-ttu-id="bdab6-205">Documentos que incluam a palavra-chave Contoso (com diferenciação de maiúsculas e minúsculas) E tanto a palavra-chave Salário (sem diferenciação de maiúsculas e minúsculas) OU Remuneração</span><span class="sxs-lookup"><span data-stu-id="bdab6-205">Documents that include the keyword (not case sensitive) Contoso AND either keyword (not case sensitive) Salary OR Compensation</span></span></td>
<td align="left"><p><span data-ttu-id="bdab6-206">KQL</span><span class="sxs-lookup"><span data-stu-id="bdab6-206">KQL</span></span></p>
<p><span data-ttu-id="bdab6-207">RegEx</span><span class="sxs-lookup"><span data-stu-id="bdab6-207">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="bdab6-208">KQL – Contoso E (Salário OU Remuneração)</span><span class="sxs-lookup"><span data-stu-id="bdab6-208">KQL — Contoso AND (Salary OR Compensation)</span></span></p>
<p><span data-ttu-id="bdab6-209">RegEx — (\bCONTOSO-9\d{5}\b)</span><span class="sxs-lookup"><span data-stu-id="bdab6-209">RegEx — (\bCONTOSO-9\d{5}\b)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="bdab6-210">Confidencial</span><span class="sxs-lookup"><span data-stu-id="bdab6-210">Confidential</span></span></td>
<td align="left"><span data-ttu-id="bdab6-211">Documentos que contenham a frase (com diferenciação de maiúsculas e minúsculas) Contoso Confidencial.</span><span class="sxs-lookup"><span data-stu-id="bdab6-211">Documents containing the phrase (not case sensitive) Contoso Confidential.</span></span></td>
<td align="left"><p><span data-ttu-id="bdab6-212">KQL</span><span class="sxs-lookup"><span data-stu-id="bdab6-212">KQL</span></span></p>
<p><span data-ttu-id="bdab6-213">RegEx</span><span class="sxs-lookup"><span data-stu-id="bdab6-213">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="bdab6-214">KQL – Contoso Confidencial</span><span class="sxs-lookup"><span data-stu-id="bdab6-214">KQL — Contoso Confidential</span></span></p>
<p><span data-ttu-id="bdab6-215">RegEx — (?i)(\bContoso Confidencial\b)</span><span class="sxs-lookup"><span data-stu-id="bdab6-215">RegEx — (?i)(\bContoso Confidential\b)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="bdab6-216">Altamente Confidencial</span><span class="sxs-lookup"><span data-stu-id="bdab6-216">Highly confidential</span></span></td>
<td align="left"><span data-ttu-id="bdab6-217">Documentos que incluam a frase Contoso Secreto (com diferenciação de maiúsculas e minúsculas) ou Secreto-C#### em que # representa qualquer dígito.</span><span class="sxs-lookup"><span data-stu-id="bdab6-217">Documents that include either pharase (case sensitive) Contoso Secret or Secret-C#### where # represents any digit.</span></span></td>
<td align="left"><p><span data-ttu-id="bdab6-218">KQL</span><span class="sxs-lookup"><span data-stu-id="bdab6-218">KQL</span></span></p>
<p><span data-ttu-id="bdab6-219">RegEx</span><span class="sxs-lookup"><span data-stu-id="bdab6-219">RegEx</span></span></p></td>
<td align="left"><p><span data-ttu-id="bdab6-220">KQL – Contoso Secreto OU o Secreto-C\*</span><span class="sxs-lookup"><span data-stu-id="bdab6-220">KQL — Contoso Secret OR Secret-C\*</span></span></p>
<p><span data-ttu-id="bdab6-221">RegEx — (?i)(\bContoso Secreto\b)|(\bSecreto-C\d\{4}\b)</span><span class="sxs-lookup"><span data-stu-id="bdab6-221">RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</span></span></p></td>
</tr>
</tbody>
</table>
