---
title: Usar consultas compartilhadas Microsoft 365 busca avançada do Defender
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, repo github, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952579"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="028d7-105">Usar consultas compartilhadas na busca avançada</span><span class="sxs-lookup"><span data-stu-id="028d7-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="028d7-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="028d7-106">**Applies to:**</span></span>
- <span data-ttu-id="028d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="028d7-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="028d7-108">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="028d7-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="028d7-109">[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="028d7-109">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="028d7-110">Você também pode encontrar consultas compartilhadas publicamente no GitHub.</span><span class="sxs-lookup"><span data-stu-id="028d7-110">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="028d7-111">Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.</span><span class="sxs-lookup"><span data-stu-id="028d7-111">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagem de consultas compartilhadas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="028d7-113">Salvar, modificar e compartilhar uma consulta</span><span class="sxs-lookup"><span data-stu-id="028d7-113">Save, modify, and share a query</span></span>
<span data-ttu-id="028d7-114">Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="028d7-114">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="028d7-115">Criar ou modificar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="028d7-115">Create or modify a query.</span></span> 

2. <span data-ttu-id="028d7-116">Clique no botão suspenso **Salvar consulta** e selecione **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="028d7-116">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="028d7-117">Digite um nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="028d7-117">Enter a name for the query.</span></span> 

   ![Imagem de salvamento de uma consulta](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="028d7-119">Selecione a pasta em que você deseja salvar a consulta.</span><span class="sxs-lookup"><span data-stu-id="028d7-119">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="028d7-120">**Consultas compartilhadas** — compartilhadas com todos os usuários da organização</span><span class="sxs-lookup"><span data-stu-id="028d7-120">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="028d7-121">**Minhas consultas** — acessíveis somente para você</span><span class="sxs-lookup"><span data-stu-id="028d7-121">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="028d7-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="028d7-122">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="028d7-123">Excluir ou renomear uma consulta</span><span class="sxs-lookup"><span data-stu-id="028d7-123">Delete or rename a query</span></span>
1. <span data-ttu-id="028d7-124">Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.</span><span class="sxs-lookup"><span data-stu-id="028d7-124">Right-click on a query you want to rename or delete.</span></span>

    ![Imagem da exclusão de consulta](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="028d7-126">Selecione **Exclua** e confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="028d7-126">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="028d7-127">Ou selecione **Renomear** e forneça um novo nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="028d7-127">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="028d7-128">Criar um link direto para uma consulta</span><span class="sxs-lookup"><span data-stu-id="028d7-128">Create a direct link to a query</span></span>
<span data-ttu-id="028d7-129">Para gerar um link que abra sua consulta diretamente no editor de consulta de busca avançada, finalize sua consulta e selecione **Compartilhar link**.</span><span class="sxs-lookup"><span data-stu-id="028d7-129">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="028d7-130">Acessar consultas no repositório do GitHub</span><span class="sxs-lookup"><span data-stu-id="028d7-130">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="028d7-131">Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="028d7-131">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="028d7-132">Esse repositório está aberto para a contribuições.</span><span class="sxs-lookup"><span data-stu-id="028d7-132">This repository is open to contributions.</span></span> <span data-ttu-id="028d7-133">Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="028d7-133">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="028d7-134">Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="028d7-134">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="028d7-135">Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="028d7-135">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

>[!NOTE]
><span data-ttu-id="028d7-136">Algumas tabelas neste artigo podem não estar disponíveis no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="028d7-136">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="028d7-137">[A Microsoft 365 Defender para](m365d-enable.md) procurar ameaças usando mais fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="028d7-137">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="028d7-138">Você pode mover seus fluxos de trabalho de busca avançados do Microsoft Defender para o Endpoint para o Microsoft 365 Defender seguindo as etapas em Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de [Extremidade.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="028d7-138">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="028d7-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="028d7-139">Related topics</span></span>
- [<span data-ttu-id="028d7-140">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="028d7-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="028d7-141">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="028d7-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="028d7-142">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="028d7-142">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="028d7-143">Buscar em dispositivos, e-mails, aplicativos e identidades</span><span class="sxs-lookup"><span data-stu-id="028d7-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="028d7-144">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="028d7-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="028d7-145">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="028d7-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)