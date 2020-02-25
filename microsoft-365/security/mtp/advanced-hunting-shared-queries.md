---
title: Utilize consultas compartilhadas na busca avançada da Proteção contra Ameaças da Microsoft
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, repositório do GitHub, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 7ff46226e2535ed9826a61afa857e38b03c06ce1
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234670"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="42371-105">Usar consultas compartilhadas na busca avançada</span><span class="sxs-lookup"><span data-stu-id="42371-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="42371-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="42371-106">**Applies to:**</span></span>
- <span data-ttu-id="42371-107">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="42371-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="42371-108">[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="42371-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="42371-109">Você também pode encontrar consultas compartilhadas publicamente no GitHub.</span><span class="sxs-lookup"><span data-stu-id="42371-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="42371-110">Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.</span><span class="sxs-lookup"><span data-stu-id="42371-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Imagem de consultas compartilhadas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="42371-112">Salvar, modificar e compartilhar uma consulta</span><span class="sxs-lookup"><span data-stu-id="42371-112">Save, modify, and share a query</span></span>
<span data-ttu-id="42371-113">Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="42371-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="42371-114">Criar ou modificar uma consulta.</span><span class="sxs-lookup"><span data-stu-id="42371-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="42371-115">Clique no botão suspenso **Salvar consulta** e selecione **Salvar como**.</span><span class="sxs-lookup"><span data-stu-id="42371-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="42371-116">Digite um nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="42371-116">Enter a name for the query.</span></span> 

   ![Imagem de salvamento de uma consulta](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="42371-118">Selecione a pasta em que você deseja salvar a consulta.</span><span class="sxs-lookup"><span data-stu-id="42371-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="42371-119">**Consultas compartilhadas** — compartilhadas com todos os usuários da organização</span><span class="sxs-lookup"><span data-stu-id="42371-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="42371-120">**Minhas consultas** — acessíveis somente para você</span><span class="sxs-lookup"><span data-stu-id="42371-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="42371-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="42371-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="42371-122">Excluir ou renomear uma consulta</span><span class="sxs-lookup"><span data-stu-id="42371-122">Delete or rename a query</span></span>
1. <span data-ttu-id="42371-123">Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.</span><span class="sxs-lookup"><span data-stu-id="42371-123">Right-click on a query you want to rename or delete.</span></span>

    ![Imagem da exclusão de consulta](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="42371-125">Selecione **Exclua** e confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="42371-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="42371-126">Ou selecione **Renomear** e forneça um novo nome para a consulta.</span><span class="sxs-lookup"><span data-stu-id="42371-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="42371-127">Acessar consultas no repositório do GitHub</span><span class="sxs-lookup"><span data-stu-id="42371-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="42371-128">Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="42371-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="42371-129">Esse repositório está aberto para a contribuições.</span><span class="sxs-lookup"><span data-stu-id="42371-129">This repository is open to contributions.</span></span> <span data-ttu-id="42371-130">Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="42371-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="42371-131">Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes.</span><span class="sxs-lookup"><span data-stu-id="42371-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="42371-132">Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="42371-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="42371-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="42371-133">Related topics</span></span>
- [<span data-ttu-id="42371-134">Buscar proativamente por ameaças</span><span class="sxs-lookup"><span data-stu-id="42371-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="42371-135">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="42371-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="42371-136">Buscar por ameaças em dispositivos e emails</span><span class="sxs-lookup"><span data-stu-id="42371-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="42371-137">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="42371-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="42371-138">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="42371-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
