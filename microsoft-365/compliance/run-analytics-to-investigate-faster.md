---
title: Executar análise para investigar mais rápido
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
description: Saiba como usar ferramentas analíticas, como detecção de duplicidades, segmentação de email e temas para acelerar suas investigações.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7a97f5ce7aefdd230a3c7a671155a7b73b2e8e19
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285337"
---
# <a name="run-analytics-to-investigate-faster"></a><span data-ttu-id="e7f3d-103">Executar análise para investigar mais rápido</span><span class="sxs-lookup"><span data-stu-id="e7f3d-103">Run analytics to investigate faster</span></span>

<span data-ttu-id="e7f3d-104">Quando uma coleção de evidências é grande, pode ser difícil revisar todas elas.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-104">When an evidence collection is large, it can be difficult to review them all.</span></span> <span data-ttu-id="e7f3d-105">Um conjunto de evidências geralmente inclui várias cópias das mesmas ou de documentos ou mensagens de email semelhantes.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-105">A set of evidence often includes multiple copies of the same or similar email messages or documents.</span></span> <span data-ttu-id="e7f3d-106">As investigações de dados (visualização) fornecem várias ferramentas de análise que podem ajudá-lo a reduzir o volume de documentos que precisam ser revisados sem qualquer perda de informações.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-106">Data Investigations (preview) provides a number of analytics tools that can help you reduce the volume of documents that need to be reviewed without any loss in information.</span></span> <span data-ttu-id="e7f3d-107">Para saber mais sobre esses recursos, confira:</span><span class="sxs-lookup"><span data-stu-id="e7f3d-107">To learn more about these capabilities, see:</span></span>

- [<span data-ttu-id="e7f3d-108">Próximo detecção duplicada</span><span class="sxs-lookup"><span data-stu-id="e7f3d-108">Near duplicate detection</span></span>](near-duplicates.md)

- [<span data-ttu-id="e7f3d-109">Threading de emails</span><span class="sxs-lookup"><span data-stu-id="e7f3d-109">Email threading</span></span>](email-threading.md)

- [<span data-ttu-id="e7f3d-110">Temas</span><span class="sxs-lookup"><span data-stu-id="e7f3d-110">Themes</span></span>](themes.md)

<span data-ttu-id="e7f3d-111">Para analisar dados em um conjunto de evidências:</span><span class="sxs-lookup"><span data-stu-id="e7f3d-111">To analyze data in an evidence set:</span></span>

1. <span data-ttu-id="e7f3d-112">Configure as definições de análise para sua investigação.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-112">Configure the analytics settings for your investigation.</span></span> <span data-ttu-id="e7f3d-113">Para obter mais informações, consulte [Configurar definições de pesquisa e análise](configure-search-analytics-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e7f3d-113">For more information, see [Configure search and analytics settings](configure-search-analytics-settings.md).</span></span>

2. <span data-ttu-id="e7f3d-114">Abra o conjunto de evidência.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-114">Open the evidence set.</span></span>

3. <span data-ttu-id="e7f3d-115">Clique em **gerenciar evidência**.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-115">Click **Manage evidence**.</span></span>

4. <span data-ttu-id="e7f3d-116">Em **análise**, clique em **analisar**.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-116">Under **Analytics**, click **Analyze**.</span></span>

<span data-ttu-id="e7f3d-117">Você pode verificar o andamento da análise na guia **trabalhos** em sua investigação.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-117">You can check the progress of analysis on the **Jobs** tab in your investigation.</span></span> <span data-ttu-id="e7f3d-118">O tipo de trabalho disparado é chamado de **análise de execução**.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-118">The job type that's triggered is named **Running analytics**.</span></span>

 <span data-ttu-id="e7f3d-119">Após a conclusão da análise, você pode ver uma lista de duplicatas exatas ou quase duplicatas do documento que está sendo revisado localizado no painel à direita.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-119">After analysis is completed, you can see a list of exact duplicates or near-duplicates of the document that you're reviewing located in the panel on the right.</span></span> <span data-ttu-id="e7f3d-120">Para selecionar todas as duplicatas do documento que você está exibindo, você pode facilmente fazer isso usando este painel.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-120">To select all duplicates of the document you're viewing, you can easily do so using this panel.</span></span> <span data-ttu-id="e7f3d-121">Para saber mais sobre outros recursos neste painel, consulte [Review data in Evidence](review-data-in-evidence.md).</span><span class="sxs-lookup"><span data-stu-id="e7f3d-121">To learn more about other features on this panel, see [Review data in evidence](review-data-in-evidence.md).</span></span> 

<span data-ttu-id="e7f3d-122">Você também pode executar consultas adicionais dentro de suas evidências usando as saídas da análise, como temas.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-122">You can also run additional queries within your evidence using the outputs of the analysis such as themes.</span></span> <span data-ttu-id="e7f3d-123">Para obter mais informações, consulte [Query The data in Evidence](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="e7f3d-123">For more information, see [Query the data in evidence](evidence-query.md).</span></span>

## <a name="analytics-report"></a><span data-ttu-id="e7f3d-124">Relatório de análise</span><span class="sxs-lookup"><span data-stu-id="e7f3d-124">Analytics report</span></span>

<span data-ttu-id="e7f3d-125">Para exibir um relatório de análise de suas evidências:</span><span class="sxs-lookup"><span data-stu-id="e7f3d-125">To view an analytics report for your evidence:</span></span>

1. <span data-ttu-id="e7f3d-126">Abra o conjunto de evidência.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-126">Open the evidence set.</span></span>

2. <span data-ttu-id="e7f3d-127">Clique em **gerenciar evidência**.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-127">Click **Manage evidence**.</span></span>

3. <span data-ttu-id="e7f3d-128">Em **análise**, clique em **Exibir relatório**.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-128">Under **Analytics**, click **View report**.</span></span>

<span data-ttu-id="e7f3d-129">O relatório tem quatro componentes da análise:</span><span class="sxs-lookup"><span data-stu-id="e7f3d-129">The report has four components from analysis:</span></span>

- <span data-ttu-id="e7f3d-130">**Divisão** -o número de emails, anexos e documentos brutos encontrados no conjunto de evidências.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-130">**Breakdown** - The number of raw emails, attachments, and documents found in the evidence set.</span></span>

- <span data-ttu-id="e7f3d-131">**Emails** : o número de mensagens do eamil incluindo, inclusive minuses, cópias inclusivas ou nenhuma das opções acima.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-131">**Emails** - The number of eamil messages that are inclusives, inclusive minuses, inclusive copies, or none of the above.</span></span>
   - <span data-ttu-id="e7f3d-132">Inclusive: a última mensagem no thread de email que contém todo o histórico anterior e requer revisão.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-132">Inclusives: The last message in the email thread that contains all previous history and requires review.</span></span>
   - <span data-ttu-id="e7f3d-133">Minuses inclusivo: a mensagem no thread que contém um ou mais anexos diferentes que requer revisão.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-133">Inclusive minuses: The message in the thread that contains one or more different attachments that requires review.</span></span>
   - <span data-ttu-id="e7f3d-134">Cópias inclusivas: a mensagem é uma cópia de outra mensagem inclusiva ou inclusiva (assunto e corpo).</span><span class="sxs-lookup"><span data-stu-id="e7f3d-134">Inclusive copies: The message that is a copy of another inclusive or inclusive minus message (subject and body).</span></span>

- <span data-ttu-id="e7f3d-135">**Attachments** : o número de anexos de email exclusivos ou duplicados de um anexo de email diferente dentro da mesma evidência.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-135">**Attachments** - The number of email attachments that are unique or duplicates of a different email attachment within the same evidence same.</span></span>

- <span data-ttu-id="e7f3d-136">**Documentos (exceto anexos de email)** : o número de documentos exclusivos que exigem revisão, por exemplo, o documento mais representativo do conjunto quase duplicado ou uma duplicata exata de outro documento.</span><span class="sxs-lookup"><span data-stu-id="e7f3d-136">**Documents (excluding email attachments)** - The number of unique documents that require review, for example, the most representative document of the near-duplicate set or an exact duplicate of another document).</span></span>
