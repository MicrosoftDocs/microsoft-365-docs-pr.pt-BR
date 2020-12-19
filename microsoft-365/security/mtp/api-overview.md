---
title: Visão geral das APIs do Microsoft 365 defender
description: Saiba mais sobre as APIs disponíveis no Microsoft 365 defender
keywords: API, APIs, visão geral, incidente, incidentes, busca de ameaças, Microsoft 365 defender
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719185"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="979a3-104">Visão geral das APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="979a3-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="979a3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="979a3-105">**Applies to:**</span></span>

- <span data-ttu-id="979a3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="979a3-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="979a3-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="979a3-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="979a3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="979a3-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="979a3-109">O Microsoft 365 defender foi criado na parte superior de uma plataforma pronta para integração.</span><span class="sxs-lookup"><span data-stu-id="979a3-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="979a3-110">Use as APIs do Microsoft 365 defender para automatizar fluxos de trabalho com base no incidente compartilhado e nas tabelas de busca avançada.</span><span class="sxs-lookup"><span data-stu-id="979a3-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="979a3-111">**[Incidentes combinados](api-incident.md)** enfocam o que é crítico ao agrupar o escopo de ataque completo e todos os ativos impactados juntos na API de incidentes.</span><span class="sxs-lookup"><span data-stu-id="979a3-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="979a3-112">**[Busca de ameaças entre produtos](api-advanced-hunting.md)** -Aproveite o conhecimento organizacional da equipe de segurança para procurar sinais de comprometimento, criando suas próprias consultas personalizadas para buscar dados brutos coletados por vários produtos de proteção.</span><span class="sxs-lookup"><span data-stu-id="979a3-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="979a3-113">Juntamente com essas APIs específicas do Microsoft 365 defender, cada um dos outros produtos de segurança expõem [APIs adicionais](api-articles.md) para ajudá-lo a aproveitar seus recursos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="979a3-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="979a3-114">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="979a3-114">Learn more</span></span>

| <span data-ttu-id="979a3-115">**Entender como acessar as APIs**</span><span class="sxs-lookup"><span data-stu-id="979a3-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="979a3-116">Saiba mais sobre cotas de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="979a3-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="979a3-117">Acessar as APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="979a3-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="979a3-118">**Build apps**</span><span class="sxs-lookup"><span data-stu-id="979a3-118">**Build apps**</span></span> |
| [<span data-ttu-id="979a3-119">Criar um aplicativo "Olá mundo"</span><span class="sxs-lookup"><span data-stu-id="979a3-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="979a3-120">Criar um aplicativo para acessar as APIs do Microsoft 365 defender em nome de um usuário</span><span class="sxs-lookup"><span data-stu-id="979a3-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="979a3-121">Criar um aplicativo para acessar o Microsoft 365 defender sem um usuário</span><span class="sxs-lookup"><span data-stu-id="979a3-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="979a3-122">Criar um aplicativo com acesso de parceiro multilocatário às APIs do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="979a3-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="979a3-123">**Solucionar problemas e manter seus aplicativos**</span><span class="sxs-lookup"><span data-stu-id="979a3-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="979a3-124">Entender códigos de erro da API</span><span class="sxs-lookup"><span data-stu-id="979a3-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="979a3-125">Gerenciar segredos em seus aplicativos com o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="979a3-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="979a3-126">Implementar a autorização do OAuth 2,0 para entrar no usuário</span><span class="sxs-lookup"><span data-stu-id="979a3-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
