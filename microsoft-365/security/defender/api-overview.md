---
title: Visão geral das APIs do Microsoft 365 Defender
description: Saiba mais sobre as APIs disponíveis no Microsoft 365 Defender
keywords: api, apis, visão geral, incidentes, incidentes, busca de ameaças, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 496ad5695d9cd491817bad5daf3c76a02addefd1
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904183"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="a419b-104">Visão geral das APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a419b-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a419b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a419b-105">**Applies to:**</span></span>

- <span data-ttu-id="a419b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a419b-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a419b-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="a419b-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a419b-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="a419b-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a419b-109">O Microsoft 365 Defender foi criado sobre uma plataforma pronta para integração.</span><span class="sxs-lookup"><span data-stu-id="a419b-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="a419b-110">Use as APIs do Microsoft 365 Defender para automatizar fluxos de trabalho com base no incidente compartilhado e nas tabelas avançadas de busca.</span><span class="sxs-lookup"><span data-stu-id="a419b-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="a419b-111">**[Fila de incidentes combinados](api-incident.md)** - Concentre-se no que é crítico agrupando o escopo de ataque completo e todos os ativos afetados juntos na API de incidente.</span><span class="sxs-lookup"><span data-stu-id="a419b-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="a419b-112">**[Busca de](api-advanced-hunting.md)** ameaças entre produtos - Aproveite o conhecimento organizacional da equipe de segurança para procurar sinais de comprometimento, criando suas próprias consultas personalizadas para sicar dados brutos coletados em vários produtos de proteção.</span><span class="sxs-lookup"><span data-stu-id="a419b-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="a419b-113">Juntamente com essas APIs específicas do Microsoft 365 Defender, cada um dos nossos outros produtos de segurança [expõem APIs](api-articles.md) adicionais para ajudá-lo a tirar proveito de seus recursos exclusivos.</span><span class="sxs-lookup"><span data-stu-id="a419b-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="a419b-114">A transição para o portal unificado não deve afetar os painéis do PowerBi com base nas APIs do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="a419b-114">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="a419b-115">Você pode continuar a trabalhar com as APIs existentes, independentemente da transição de portal interativo.</span><span class="sxs-lookup"><span data-stu-id="a419b-115">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="a419b-116">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="a419b-116">Learn more</span></span>

| <span data-ttu-id="a419b-117">**Entenda como acessar as APIs**</span><span class="sxs-lookup"><span data-stu-id="a419b-117">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="a419b-118">Saiba mais sobre cotas de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="a419b-118">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="a419b-119">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a419b-119">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="a419b-120">**Build apps**</span><span class="sxs-lookup"><span data-stu-id="a419b-120">**Build apps**</span></span> |
| [<span data-ttu-id="a419b-121">Criar um aplicativo 'Hello world'</span><span class="sxs-lookup"><span data-stu-id="a419b-121">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="a419b-122">Criar um aplicativo para acessar APIs do Microsoft 365 Defender em nome de um usuário</span><span class="sxs-lookup"><span data-stu-id="a419b-122">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="a419b-123">Criar um aplicativo para acessar o Microsoft 365 Defender sem um usuário</span><span class="sxs-lookup"><span data-stu-id="a419b-123">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="a419b-124">Criar um aplicativo com acesso de parceiro de vários locatários às APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a419b-124">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="a419b-125">**Solucionar problemas e manter seus aplicativos**</span><span class="sxs-lookup"><span data-stu-id="a419b-125">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="a419b-126">Compreender códigos de erro da API</span><span class="sxs-lookup"><span data-stu-id="a419b-126">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="a419b-127">Gerenciar segredos em seus aplicativos com o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="a419b-127">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="a419b-128">Implementar a autorização OAuth 2.0 para entrar no usuário</span><span class="sxs-lookup"><span data-stu-id="a419b-128">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |