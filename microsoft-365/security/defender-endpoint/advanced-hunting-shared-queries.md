---
title: Usar consultas compartilhadas na busca avançada
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, detecções personalizadas, esquema, kusto, repo github, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054202"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="5ce6f-105">Usar consultas compartilhadas na busca avançada</span><span class="sxs-lookup"><span data-stu-id="5ce6f-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5ce6f-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5ce6f-106">**Applies to:**</span></span>
- [<span data-ttu-id="5ce6f-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5ce6f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="5ce6f-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5ce6f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5ce6f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="5ce6f-110">[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="5ce6f-111">Você também pode encontrar consultas compartilhadas publicamente no GitHub.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="5ce6f-112">Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagem de consultas compartilhadas](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="5ce6f-114">Salvar, modificar e compartilhar uma consulta</span><span class="sxs-lookup"><span data-stu-id="5ce6f-114">Save, modify, and share a query</span></span>
<span data-ttu-id="5ce6f-115">Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="5ce6f-116">Digite uma nova consulta ou carregue uma existente em **Consultas compartilhadas** ou **Minhas consultas**.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="5ce6f-117">Selecione **Salvar** ou **Salvar como** nas opções de salvar.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="5ce6f-118">Para evitar a substituição de uma consulta existente, escolha **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="5ce6f-119">Digite um nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-119">Enter a name for the query.</span></span>

   ![Imagem de salvamento de uma consulta](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="5ce6f-121">Selecione a pasta em que você deseja salvar a consulta.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="5ce6f-122">**Consultas compartilhadas** — compartilhadas com todos os usuários em sua organização</span><span class="sxs-lookup"><span data-stu-id="5ce6f-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="5ce6f-123">**Minhas consultas** — acessíveis somente para você</span><span class="sxs-lookup"><span data-stu-id="5ce6f-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="5ce6f-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="5ce6f-125">Excluir ou renomear uma consulta</span><span class="sxs-lookup"><span data-stu-id="5ce6f-125">Delete or rename a query</span></span>
1. <span data-ttu-id="5ce6f-126">Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-126">Right-click on a query you want to rename or delete.</span></span>

    ![Imagem da exclusão de consulta](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="5ce6f-128">Selecione **Exclua** e confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="5ce6f-129">Ou selecione **Renomear** e forneça um novo nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="5ce6f-130">Criar um link direto para uma consulta</span><span class="sxs-lookup"><span data-stu-id="5ce6f-130">Create a direct link to a query</span></span>
<span data-ttu-id="5ce6f-131">Para gerar um link que abra sua consulta diretamente no editor de consulta de busca avançada, finalize sua consulta e selecione **Compartilhar link**.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="5ce6f-132">Acessar consultas no repositório do GitHub</span><span class="sxs-lookup"><span data-stu-id="5ce6f-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="5ce6f-133">Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span><span class="sxs-lookup"><span data-stu-id="5ce6f-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="5ce6f-134">Esse repositório está aberto para a contribuições.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-134">This repository is open to contributions.</span></span> <span data-ttu-id="5ce6f-135">Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="5ce6f-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="5ce6f-136">Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="5ce6f-137">Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](threat-analytics.md) da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5ce6f-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5ce6f-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5ce6f-138">Related topics</span></span>
- [<span data-ttu-id="5ce6f-139">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="5ce6f-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="5ce6f-140">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="5ce6f-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="5ce6f-141">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="5ce6f-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="5ce6f-142">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="5ce6f-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="5ce6f-143">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="5ce6f-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="5ce6f-144">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="5ce6f-144">Custom detections overview</span></span>](overview-custom-detections.md)
