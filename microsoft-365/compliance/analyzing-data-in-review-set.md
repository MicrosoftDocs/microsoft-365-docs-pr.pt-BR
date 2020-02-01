---
title: Analisar dados em um conjunto de revisão na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 5705edcc4015460a8c6c5a2edc6ebf922dabbb2f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596148"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a><span data-ttu-id="d47fc-102">Analisar dados em um conjunto de revisão na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="d47fc-102">Analyze data in a review set in Advanced eDiscovery</span></span>

<span data-ttu-id="d47fc-103">Quando o número de documentos coletados é grande, pode ser difícil examiná-los.</span><span class="sxs-lookup"><span data-stu-id="d47fc-103">When the number of collected documents is large, it can be difficult to review them all.</span></span> <span data-ttu-id="d47fc-104">A descoberta eletrônica avançada fornece várias ferramentas para analisar os documentos para reduzir o volume de documentos a serem revisados sem perda de informações e para ajudá-lo a organizar os documentos de forma coerente.</span><span class="sxs-lookup"><span data-stu-id="d47fc-104">Advanced eDiscovery provides a number of tools to analyze the documents to reduce the volume of documents to be reviewed without any loss in information, and to help you organize the documents in a coherent manner.</span></span> <span data-ttu-id="d47fc-105">Para saber mais sobre esses recursos, confira:</span><span class="sxs-lookup"><span data-stu-id="d47fc-105">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="d47fc-106">Próximo detecção duplicada</span><span class="sxs-lookup"><span data-stu-id="d47fc-106">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="d47fc-107">Threading de emails</span><span class="sxs-lookup"><span data-stu-id="d47fc-107">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="d47fc-108">Temas</span><span class="sxs-lookup"><span data-stu-id="d47fc-108">Themes</span></span>](themes.md)

<span data-ttu-id="d47fc-109">Para analisar dados em um conjunto de revisão:</span><span class="sxs-lookup"><span data-stu-id="d47fc-109">To analyze data in a review set:</span></span>

1. <span data-ttu-id="d47fc-110">Defina as configurações de análise para o seu caso.</span><span class="sxs-lookup"><span data-stu-id="d47fc-110">Configure analytics settings for your case.</span></span> <span data-ttu-id="d47fc-111">Para obter mais informações, consulte [Configurar definições de pesquisa e análise](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="d47fc-111">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="d47fc-112">Abra o conjunto de revisão que você deseja analisar.</span><span class="sxs-lookup"><span data-stu-id="d47fc-112">Open the review set you want to analyze.</span></span>

3. <span data-ttu-id="d47fc-113">Clique em **gerenciar análise definida**.</span><span class="sxs-lookup"><span data-stu-id="d47fc-113">Click **Manage review set**.</span></span>

4. <span data-ttu-id="d47fc-114">Clique em **executar análise para o conjunto de revisão**.</span><span class="sxs-lookup"><span data-stu-id="d47fc-114">Click **Run analytics for the review set**.</span></span>

<span data-ttu-id="d47fc-115">Você pode verificar o progresso da análise na guia **trabalhos** da ocorrência.</span><span class="sxs-lookup"><span data-stu-id="d47fc-115">You can check the progress of analysis on the **Jobs** tab of the case.</span></span>

 <span data-ttu-id="d47fc-116">Após a conclusão da análise, você pode exibir o relatório de análise, executar consultas em seu conjunto de análise em saídas da análise (consulte [consulta dentro de seu conjunto de análise](review-set-search.md)) e ver documentos relacionados de um determinado documento (consulte [revisando dados no conjunto de revisão](reviewing-data-in-review-set.md)).</span><span class="sxs-lookup"><span data-stu-id="d47fc-116">After analysis is completed, you can view the analytics report, run queries within your review set on outputs of the analysis (see [Query within your review set](review-set-search.md)), and see related documents of a given document (see [Reviewing data in review set](reviewing-data-in-review-set.md)).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="d47fc-117">Relatório de análise</span><span class="sxs-lookup"><span data-stu-id="d47fc-117">Analytics report</span></span>

<span data-ttu-id="d47fc-118">Para exibir um relatório de análise para um conjunto de análise:</span><span class="sxs-lookup"><span data-stu-id="d47fc-118">To view an analytics report for a review set:</span></span>

1. <span data-ttu-id="d47fc-119">Abra o conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d47fc-119">Open the review set.</span></span>

2. <span data-ttu-id="d47fc-120">Clique em **gerenciar análise definida**.</span><span class="sxs-lookup"><span data-stu-id="d47fc-120">Click **Manage review set**.</span></span>

3. <span data-ttu-id="d47fc-121">Clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="d47fc-121">Click **View report**.</span></span>

<span data-ttu-id="d47fc-122">O relatório tem quatro componentes da análise:</span><span class="sxs-lookup"><span data-stu-id="d47fc-122">The report has four components from analysis:</span></span>

- <span data-ttu-id="d47fc-123">**Divisão** -quantas mensagens de email, anexos e documentos soltos foram encontrados no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d47fc-123">**Breakdown** - How many email messages, attachments, and loose documents were found in the review set.</span></span>

- <span data-ttu-id="d47fc-124">**Documentos (exceto anexos)** : Quantos documentos soltos foram dinâmicos, únicos duplicatas próximas de uma tabela dinâmica ou uma duplicata exata de outro documento.</span><span class="sxs-lookup"><span data-stu-id="d47fc-124">**Documents (excluding attachments)** - How many loose documents were pivots, unique near duplicates of a pivot, or an exact duplicate of another document.</span></span>

- <span data-ttu-id="d47fc-125">**Emails** -quantas mensagens de email foram inclusivas, cópias inclusivas, inclusive minuses ou nenhuma das opções acima.</span><span class="sxs-lookup"><span data-stu-id="d47fc-125">**Emails** - How many email messages were inclusives, inclusive copies, inclusive minuses, or none of the above.</span></span>

- <span data-ttu-id="d47fc-126">**Attachments** -quantos anexos de email são exclusivos ou duplicados de outro anexo de email no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d47fc-126">**Attachments** - How many email attachments were unique or duplicates of another email attachment in the review set.</span></span>