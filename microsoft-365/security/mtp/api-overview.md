---
title: Visão geral das APIs do Microsoft 365 defender
description: Saiba mais sobre as APIs disponíveis no Microsoft 365 defender
keywords: API, APIs, visão geral, incidente, incidentes, busca de ameaças
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 75a5853e7128667420819c84fbc3c50b07d669b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845003"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="b55d1-104">Visão geral das APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b55d1-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b55d1-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b55d1-105">**Applies to:**</span></span>
- <span data-ttu-id="b55d1-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="b55d1-106">Microsoft 365 Defender</span></span>


>[!IMPORTANT] 
><span data-ttu-id="b55d1-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="b55d1-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="b55d1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="b55d1-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="b55d1-109">A solução Microsoft 365 defender foi criada na parte superior de uma plataforma pronta para integração.</span><span class="sxs-lookup"><span data-stu-id="b55d1-109">Microsoft 365 Defender solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="b55d1-110">As APIs do Lop do Microsoft 365 defender permitirão que você automatize os fluxos de trabalho com base no incidente compartilhado e nas tabelas de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="b55d1-110">The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="b55d1-111">**Fila de incidentes combinados** -ajuda os profissionais de segurança a se concentrar no que é crítico.</span><span class="sxs-lookup"><span data-stu-id="b55d1-111">**Combined incidents queue** - Helps security professionals focus on what's critical.</span></span> <span data-ttu-id="b55d1-112">Ajuda a garantir que todo o escopo de ataque completo e os ativos afetados sejam agrupados e encaixados de forma oportuna, sob a API de incidente.</span><span class="sxs-lookup"><span data-stu-id="b55d1-112">Helps to ensure that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="b55d1-113">**Busca de ameaças entre produtos** -as equipes de segurança podem aproveitar o conhecimento organizacional exclusivo para procurar sinais de comprometimento criando suas próprias consultas personalizadas por meio de APIs sobre os dados brutos coletados pelos vários produtos de proteção.</span><span class="sxs-lookup"><span data-stu-id="b55d1-113">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="b55d1-114">Além desses conjuntos de APIs, cada um dos vários produtos de proteção expõe APIs adicionais para ajudá-lo a inovar com base na capacidade de cada produto.</span><span class="sxs-lookup"><span data-stu-id="b55d1-114">In addition to these set of APIs, each of the various protection products expose additional APIs to help you innovate based on each product capability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b55d1-115">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b55d1-115">Related topics</span></span>
- [<span data-ttu-id="b55d1-116">Acessar as APIs de proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b55d1-116">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="b55d1-117">Outros recursos da API</span><span class="sxs-lookup"><span data-stu-id="b55d1-117">Other API resources</span></span>](api-articles.md)
