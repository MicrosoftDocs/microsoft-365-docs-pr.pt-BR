---
title: Visão geral da Proteção de Informações do Office 365 para o GDPR
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
description: Tenha uma visão geral da Proteção de Informações do Office 365 para o GDPR. Saiba como descobrir, classificar, proteger e monitorar dados pessoais.
ms.openlocfilehash: 83a090b214821142a312ee81463fb3c395876867
ms.sourcegitcommit: 2399ee6f9bc955cf8f2a76c01fc84c19eb37ff42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43919600"
---
# <a name="overview-of-office-365-information-protection-for-gdpr"></a><span data-ttu-id="4b68d-104">Visão geral da Proteção de Informações do Office 365 para o GDPR</span><span class="sxs-lookup"><span data-stu-id="4b68d-104">Overview of Office 365 Information Protection for GDPR</span></span>

<span data-ttu-id="4b68d-p102">Esta solução demonstra como proteger dados confidenciais armazenados nos serviços do Office 365. Ela inclui recomendações prescritivas para a descoberta, a classificação, a proteção e o monitoramento de dados pessoais. Ela usa o GDPR (Regulamento Geral sobre Proteção de Dados) como exemplo, mas é possível aplicar o mesmo processo para estar em conformidade com vários outros regulamentos.</span><span class="sxs-lookup"><span data-stu-id="4b68d-p102">This solution demonstrates how to protect sensitive data that is stored in Office 365 services. It includes prescriptive recommendations for discovering, classifying, protecting, and monitoring personal data. This solution uses General Data Protection Regulation (GDPR) as an example, but you can apply the same process to achieve compliance with many other regulations.</span></span>

<span data-ttu-id="4b68d-p103">O GDPR regulamenta a coleta, o armazenamento, o processamento e o compartilhamento de dados pessoais. A grosso modo, o GDPR define dados pessoais como qualquer dado relativo a uma pessoa física identificada ou identificável que seja residente da União Europeia (UE).</span><span class="sxs-lookup"><span data-stu-id="4b68d-p103">GDPR regulates the collection, storage, processing, and sharing of personal data. Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person that is a resident of the European Union (EU).</span></span>

<span data-ttu-id="4b68d-110">Artigo 4 – Definições</span><span class="sxs-lookup"><span data-stu-id="4b68d-110">Article 4 – Definitions</span></span>

> <span data-ttu-id="4b68d-111">"dados pessoais" são todas as informações relativas a uma pessoa física identificada ou identificável ("titular dos dados"); uma pessoa física identificável é alguém que pode ser identificado, direta ou indiretamente, em especial por referência a um identificador como um nome, um número de identificação, dados de localização, um identificador online ou por um ou mais elementos específicos da identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física;</span><span class="sxs-lookup"><span data-stu-id="4b68d-111">‘personal data’ means any information relating to an identified or identifiable natural person (‘data subject’); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural or social identity of that natural person;</span></span>

<span data-ttu-id="4b68d-p104">Essa solução se destina a ajudar as organizações a descobrir e proteger os dados pessoais no Office 365 que possam estar sujeitos ao GDPR, mas não é oferecida como uma comprovação de conformidade com o GDPR. A responsabilidade de garantir a conformidade com o GDPR é da própria organização e recomenda-se que ela consulte suas equipes jurídicas e de conformidade ou que busque orientação e consultoria de entidades terceiras especializadas em conformidade.</span><span class="sxs-lookup"><span data-stu-id="4b68d-p104">This solution is intended to help organizations discover and protect personal data in Office 365 that might be subject to the GDPR. It is not offered as a GDPR compliance attestation. Organizations are responsible for ensuring their own GDPR compliance and are advised to consult their legal and compliance teams or to seek guidance and advice from third parties that specialize in compliance.</span></span>

<span data-ttu-id="4b68d-115">A [Avaliação do GDPR](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) é uma ferramenta online para uma autoavaliação rápida e sem custo para ajudar sua organização a analisar o nível geral de preparação para cumprir com o GDPR.</span><span class="sxs-lookup"><span data-stu-id="4b68d-115">[GDPR Assessment](https://www.microsoft.com/cyberassessment/en/gdpr/uso365?ls=Email&mkt_tok=eyJpIjoiTTJFeE5USXlOR1EwTWpJMiIsInQiOiJQTmdCYWR5NTlOd3JLWHZlb2NzNldKclQ4ZVBzVmhGeUhoUlFcL1pvSDIyXC9Ka05iTUR1aGpxT0YxQ0FUeGNDOUlkbWZLM1U4SUZWZmEyaGF6XC9ueUxkTHJzZnB3VDRMZlhPdkR4MzRLWkF5ckRNdWwxUkgzXC9yRU8yNkttSHhTb3VpZjNyVlJrNm9TTVZRYU5HR240a0FRPT0ifQ%3D%3D) is a quick, online self-evaluation tool available at no cost to help your organization review its overall level of readiness to comply with the GDPR.</span></span>

## <a name="assess-and-manage-your-compliance-risk"></a><span data-ttu-id="4b68d-116">Avaliar e gerenciar o risco de conformidade</span><span class="sxs-lookup"><span data-stu-id="4b68d-116">Assess and manage your compliance risk</span></span>

<span data-ttu-id="4b68d-p105">A primeira etapa para estar em conformidade com o GDPR é avaliar se ele se aplica à sua organização e, em caso afirmativo, até que ponto. Essa análise inclui entender os dados que a sua organização processa e onde estão localizados.</span><span class="sxs-lookup"><span data-stu-id="4b68d-p105">The first step towards GDPR compliance is to assess whether the GDPR applies to your organization, and, if so, to what extent. This analysis includes understanding the data your organization processes and where it resides.</span></span>

### <a name="step-1--use-compliance-score-to-view-the-regulation-requirements-and-track-your-progress"></a><span data-ttu-id="4b68d-119">Etapa 1: usar a Pontuação de Conformidade para exibir as exigências regulatórias e acompanhar o progresso</span><span class="sxs-lookup"><span data-stu-id="4b68d-119">Step 1 — Use Compliance Score to view the regulation requirements and track your progress</span></span>

<span data-ttu-id="4b68d-120">A Pontuação de Conformidade fornece ferramentas para acompanhar, implementar e gerenciar os controles de auditoria para ajudar sua organização a estar em conformidade com vários padrões, incluindo o GDPR.</span><span class="sxs-lookup"><span data-stu-id="4b68d-120">Compliance Score provides tools to track, implement, and manage the auditing controls to help your organization reach compliance against various standards, including GDPR.</span></span>

![Use a Pontuação de Conformidade e o Gerenciador de Conformidade para exibir as exigências e acompanhar o progresso](../media/Overview-image1.png)

<span data-ttu-id="4b68d-122">Para saber mais, consulte os [pontuação de conformidade](compliance-score.md).</span><span class="sxs-lookup"><span data-stu-id="4b68d-122">For more information, see [Compliance Score](compliance-score.md).</span></span>

### <a name="step-2--use-content-search-and-sensitive-information-types-to-find-personal-data"></a><span data-ttu-id="4b68d-123">Etapa 2: usar a Pesquisa de Conteúdo e os tipos de informações confidenciais para encontrar dados pessoais</span><span class="sxs-lookup"><span data-stu-id="4b68d-123">Step 2 — Use Content Search and sensitive information types to find personal data</span></span> 

<span data-ttu-id="4b68d-p106">Descubra os dados pessoais em seu ambiente que estão sujeitos ao GDPR. Use a Pesquisa de Conteúdo em conjunto com os tipos de informações confidenciais para:</span><span class="sxs-lookup"><span data-stu-id="4b68d-p106">Discover personal data in your environment that is subject to the GDPR. Use Content Search together with sensitive information types to:</span></span>

- <span data-ttu-id="4b68d-126">Localizar e gerar relatórios sobre a localização dos dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="4b68d-126">Find and report on where personal data resides.</span></span>

- <span data-ttu-id="4b68d-127">Otimizar os tipos de dados confidenciais e outras consultas para localizar todos os dados pessoais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4b68d-127">Optimize sensitive data types and other queries to find all personal data in your environment.</span></span>

![Use a Pesquisa de Conteúdo e os tipos de informações confidenciais para encontrar dados pessoais](../media/Overview-image2.png)

<span data-ttu-id="4b68d-p107">Os tipos de informações confidenciais definem como o processo automatizado reconhecerá os tipos de informações específicas, como os números de serviço de saúde e de cartões de crédito. Este artigo inclui um conjunto que você pode usar como ponto de partida. Vários outros tipos de informações confidenciais chegarão em breve para os dados pessoais de países da UE.</span><span class="sxs-lookup"><span data-stu-id="4b68d-p107">Sensitive information types define how the automated process recognizes specific information types such as health service numbers and credit card numbers. This article includes a set you can use as a starting point. Many more sensitive information types are coming soon for personal data in EU countries.</span></span>

<span data-ttu-id="4b68d-132">Para mais informações, confira [Pesquisar e encontrar dados pessoais](search-for-and-find-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="4b68d-132">For more information, see [Search for and find personal data](search-for-and-find-personal-data.md).</span></span> 

## <a name="classify-protect-and-monitor-personal-data-in-office-365-and-other-saas-apps"></a><span data-ttu-id="4b68d-133">Classificar, proteger e monitorar dados pessoais no Office 365 e em outros aplicativos SaaS</span><span class="sxs-lookup"><span data-stu-id="4b68d-133">Classify, protect, and monitor personal data in Office 365 and other SaaS apps</span></span>

<span data-ttu-id="4b68d-134">Alguns dos recursos usados para a proteção de informações do Office 365 também podem ser usados para proteger dados confidenciais em outros aplicativos SaaS.</span><span class="sxs-lookup"><span data-stu-id="4b68d-134">Some of the capabilities used for information protection in Office 365 can also be used to protect sensitive data in other SaaS applications.</span></span>

![Classificar, proteger e monitorar dados pessoais](../media/Overview-image3.png)

<span data-ttu-id="4b68d-136">Esta ilustração é descrita pelo restante desta seção (etapas 3 a 5).</span><span class="sxs-lookup"><span data-stu-id="4b68d-136">This illustration is described by the rest this section (steps 3-5).</span></span>

### <a name="step-3--decide-if-you-want-to-use-labels-in-addition-to-sensitive-information-types"></a><span data-ttu-id="4b68d-137">Etapa 3: decidir se você deseja usar rótulos junto com os tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="4b68d-137">Step 3 — Decide if you want to use labels in addition to sensitive information types</span></span>

<span data-ttu-id="4b68d-p108">Os tipos de informações confidenciais são uma forma de classificação. Confira [Projetar um esquema de classificação de dados pessoais](architect-a-classification-schema-for-personal-data.md) para decidir se você também deseja implementar rótulos. Para aplicar rótulos, confira [Aplicar rótulos a dados pessoais no Office 365](apply-labels-to-personal-data-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4b68d-p108">Sensitive information types are a form of classification. See [Architect a classification schema for personal data](architect-a-classification-schema-for-personal-data.md), to decide if you also want to implement labels. To apply labels, see [Apply labels to personal data in Office 365](apply-labels-to-personal-data-in-office-365.md).</span></span>

<span data-ttu-id="4b68d-p109">Na ilustração, os rótulos e tipos de informações confidenciais funcionam em todo o Office 365. Em breve, será possível usá-los com o Cloud App Security para localizar dados confidenciais em outros aplicativos SaaS, como o Box e o Salesforce.</span><span class="sxs-lookup"><span data-stu-id="4b68d-p109">In the illustration, sensitive information types and labels work across Office 365. Coming soon, you can use these with Cloud App Security to find sensitive data in other SaaS apps, such as Box and Salesforce.</span></span>

### <a name="step-4--protect-personal-data-in-office-365"></a><span data-ttu-id="4b68d-143">Etapa 4: proteger dados pessoais no Office 365</span><span class="sxs-lookup"><span data-stu-id="4b68d-143">Step 4 — Protect personal data in Office 365</span></span> 

<span data-ttu-id="4b68d-p110">A proteção de dados pessoais começa com a prevenção contra perda de dados do Office 365. Há vários outros recursos recomendados para proteger o acesso aos dados pessoais, incluindo a Criptografia de Mensagens do Office 365 para email.</span><span class="sxs-lookup"><span data-stu-id="4b68d-p110">Protection for personal data starts with Office 365 data loss prevention. There are several other capabilities recommended for protecting access to personal data, including Office 365 Message Encryption for email.</span></span>

<span data-ttu-id="4b68d-146">Essas proteções podem ser direcionadas para conjuntos de dados específicos:</span><span class="sxs-lookup"><span data-stu-id="4b68d-146">These protections can be targeted to specific data sets:</span></span>

- <span data-ttu-id="4b68d-147">Permissões de nível de site e de biblioteca</span><span class="sxs-lookup"><span data-stu-id="4b68d-147">Site and library-level permissions</span></span>

- <span data-ttu-id="4b68d-148">Políticas de compartilhamento externo de nível de site</span><span class="sxs-lookup"><span data-stu-id="4b68d-148">Site-level external sharing policies</span></span>

- <span data-ttu-id="4b68d-149">Políticas de acesso de dispositivo no nível do site</span><span class="sxs-lookup"><span data-stu-id="4b68d-149">Site-level device access policies</span></span>

<span data-ttu-id="4b68d-150">A proteção de acesso ao Office 365 e a outros serviços de nuvem incluem:</span><span class="sxs-lookup"><span data-stu-id="4b68d-150">Protection for access to Office 365 and other cloud services include:</span></span>

- <span data-ttu-id="4b68d-151">Proteção à identidade e ao acesso a dispositivos no Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="4b68d-151">Identity and device access protection in Enterprise Mobility + Security (EMS)</span></span>

- <span data-ttu-id="4b68d-152">Gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="4b68d-152">Privileged access management</span></span>

- <span data-ttu-id="4b68d-153">Recursos de segurança do Windows 10</span><span class="sxs-lookup"><span data-stu-id="4b68d-153">Windows 10 security capabilities</span></span>

<span data-ttu-id="4b68d-154">Para obter mais informações sobre como aplicar proteção, consulte [Aplicar proteção aos dados pessoais no Office 365](apply-protection-to-personal-data-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4b68d-154">For more information about applying protection, see [Apply protection to personal data in Office 365](apply-protection-to-personal-data-in-office-365.md).</span></span>

### <a name="step-5--monitor-for-leaks-of-personal-data"></a><span data-ttu-id="4b68d-155">Etapa 5: monitorar o vazamento de dados pessoais</span><span class="sxs-lookup"><span data-stu-id="4b68d-155">Step 5 — Monitor for leaks of personal data</span></span>

<span data-ttu-id="4b68d-p111">Os relatórios de prevenção contra perda de dados do Office 365 oferecem o mais alto nível de detalhamento para o monitoramento de dados confidenciais. É possível configurar alertas automatizados e investigar violações usando o log de auditoria. O Cloud App Security estende a outros provedores SaaS a capacidade de localizar e monitorar dados confidenciais. Confira mais informações sobre essas ferramentas em [Monitorar violações de dados pessoais](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="4b68d-p111">Office 365 data loss prevention reports provide the greatest level of detail for monitoring sensitive data. You can setup automated alerts and investigate breaches by using the audit log. Cloud App Security extends the ability to find and monitor sensitive data to other SaaS providers. For more information on these tools, see [Monitor for breaches of personal data](/security/office-365-security/monitor-for-leaks-of-personal-data.md).</span></span>
