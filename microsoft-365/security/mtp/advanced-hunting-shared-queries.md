---
title: Utilize consultas compartilhadas na busca avançada da Proteção contra Ameaças da Microsoft
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: busca avançada, busca de ameaças, busca por ameaças cibernéticas, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, repositório do github, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: fb8addc7bc9e8ab01cc72bbdf02c12559d263196
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808686"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="87494-105">Usar consultas compartilhadas na busca avançada</span><span class="sxs-lookup"><span data-stu-id="87494-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="87494-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="87494-106">**Applies to:**</span></span>
- <span data-ttu-id="87494-107">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="87494-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="87494-108">[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="87494-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="87494-109">Você também pode encontrar consultas compartilhadas publicamente no GitHub.</span><span class="sxs-lookup"><span data-stu-id="87494-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="87494-110">Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.</span><span class="sxs-lookup"><span data-stu-id="87494-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagem de consultas compartilhadas](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="87494-112">Salvar, modificar e compartilhar uma consulta</span><span class="sxs-lookup"><span data-stu-id="87494-112">Save, modify, and share a query</span></span>
<span data-ttu-id="87494-113">Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="87494-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="87494-114">Criar ou modificar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="87494-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="87494-115">Clique no botão suspenso **Salvar consulta** e selecione **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="87494-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="87494-116">Digite um nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="87494-116">Enter a name for the query.</span></span> 

   ![Imagem de salvamento de uma consulta](../images/advanced-hunting-save-query.png)

4. <span data-ttu-id="87494-118">Selecione a pasta em que você deseja salvar a consulta.</span><span class="sxs-lookup"><span data-stu-id="87494-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="87494-119">**Consultas compartilhadas** — compartilhadas com todos os usuários da organização</span><span class="sxs-lookup"><span data-stu-id="87494-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="87494-120">**Minhas consultas** — acessíveis somente para você</span><span class="sxs-lookup"><span data-stu-id="87494-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="87494-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="87494-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="87494-122">Excluir ou renomear uma consulta</span><span class="sxs-lookup"><span data-stu-id="87494-122">Delete or rename a query</span></span>
1. <span data-ttu-id="87494-123">Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.</span><span class="sxs-lookup"><span data-stu-id="87494-123">Right-click on a query you want to rename or delete.</span></span>

    ![Imagem da exclusão de consulta](../images/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="87494-125">Selecione **Exclua** e confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="87494-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="87494-126">Ou selecione **Renomear** e forneça um novo nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="87494-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="87494-127">Acessar consultas no repositório do GitHub</span><span class="sxs-lookup"><span data-stu-id="87494-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="87494-128">Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="87494-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="87494-129">Esse repositório está aberto para a contribuições.</span><span class="sxs-lookup"><span data-stu-id="87494-129">This repository is open to contributions.</span></span> <span data-ttu-id="87494-130">Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="87494-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="87494-131">Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="87494-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="87494-132">Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="87494-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="87494-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="87494-133">Related topics</span></span>
- [<span data-ttu-id="87494-134">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="87494-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="87494-135">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="87494-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="87494-136">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="87494-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="87494-137">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="87494-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="87494-138">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="87494-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)