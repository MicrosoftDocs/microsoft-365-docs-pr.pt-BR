---
title: Usar consultas compartilhadas na busca avançada do Microsoft 365 Defender
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, repo github, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ccf2b52c744e2ae8e7ccfc631268d79a375c91d4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904037"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="c93d0-105">Usar consultas compartilhadas na busca avançada</span><span class="sxs-lookup"><span data-stu-id="c93d0-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c93d0-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c93d0-106">**Applies to:**</span></span>
- <span data-ttu-id="c93d0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c93d0-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="c93d0-108">[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="c93d0-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="c93d0-109">Você também pode encontrar consultas compartilhadas publicamente no GitHub.</span><span class="sxs-lookup"><span data-stu-id="c93d0-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="c93d0-110">Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.</span><span class="sxs-lookup"><span data-stu-id="c93d0-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagem de consultas compartilhadas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="c93d0-112">Salvar, modificar e compartilhar uma consulta</span><span class="sxs-lookup"><span data-stu-id="c93d0-112">Save, modify, and share a query</span></span>
<span data-ttu-id="c93d0-113">Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c93d0-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="c93d0-114">Criar ou modificar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="c93d0-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="c93d0-115">Clique no botão suspenso **Salvar consulta** e selecione **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="c93d0-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="c93d0-116">Digite um nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="c93d0-116">Enter a name for the query.</span></span> 

   ![Imagem de salvamento de uma consulta](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="c93d0-118">Selecione a pasta em que você deseja salvar a consulta.</span><span class="sxs-lookup"><span data-stu-id="c93d0-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="c93d0-119">**Consultas compartilhadas** — compartilhadas com todos os usuários da organização</span><span class="sxs-lookup"><span data-stu-id="c93d0-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="c93d0-120">**Minhas consultas** — acessíveis somente para você</span><span class="sxs-lookup"><span data-stu-id="c93d0-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="c93d0-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c93d0-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="c93d0-122">Excluir ou renomear uma consulta</span><span class="sxs-lookup"><span data-stu-id="c93d0-122">Delete or rename a query</span></span>
1. <span data-ttu-id="c93d0-123">Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.</span><span class="sxs-lookup"><span data-stu-id="c93d0-123">Right-click on a query you want to rename or delete.</span></span>

    ![Imagem da exclusão de consulta](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="c93d0-125">Selecione **Exclua** e confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="c93d0-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="c93d0-126">Ou selecione **Renomear** e forneça um novo nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="c93d0-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="c93d0-127">Criar um link direto para uma consulta</span><span class="sxs-lookup"><span data-stu-id="c93d0-127">Create a direct link to a query</span></span>
<span data-ttu-id="c93d0-128">Para gerar um link que abra sua consulta diretamente no editor de consulta de busca avançada, finalize sua consulta e selecione **Compartilhar link**.</span><span class="sxs-lookup"><span data-stu-id="c93d0-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="c93d0-129">Acessar consultas no repositório do GitHub</span><span class="sxs-lookup"><span data-stu-id="c93d0-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="c93d0-130">Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="c93d0-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="c93d0-131">Esse repositório está aberto para a contribuições.</span><span class="sxs-lookup"><span data-stu-id="c93d0-131">This repository is open to contributions.</span></span> <span data-ttu-id="c93d0-132">Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="c93d0-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="c93d0-133">Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="c93d0-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="c93d0-134">Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c93d0-134">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c93d0-135">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c93d0-135">Related topics</span></span>
- [<span data-ttu-id="c93d0-136">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="c93d0-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c93d0-137">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="c93d0-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c93d0-138">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="c93d0-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c93d0-139">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="c93d0-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c93d0-140">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="c93d0-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c93d0-141">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="c93d0-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)