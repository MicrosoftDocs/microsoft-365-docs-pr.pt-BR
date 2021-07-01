---
title: Visão geral do gerenciamento e APIs
ms.reviewer: ''
description: Saiba mais sobre as ferramentas de gerenciamento e categorias de API no Microsoft Defender para Ponto de Extremidade
keywords: integração, api, siem, rbac, acesso, portal, integração, investigação, resposta, entidades, entidades, contexto do usuário, contexto do aplicativo, streaming
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 471db75102eabd4d7fce14ec42d0a47562007aae
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229978"
---
# <a name="overview-of-management-and-apis"></a><span data-ttu-id="4a3ed-104">Visão geral do gerenciamento e APIs</span><span class="sxs-lookup"><span data-stu-id="4a3ed-104">Overview of management and APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4a3ed-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4a3ed-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a3ed-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4a3ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a3ed-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a3ed-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4a3ed-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4a3ed-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4a3ed-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mgt-apis-abovefoldlink)


<span data-ttu-id="4a3ed-110">O Defender for Endpoint oferece suporte a uma ampla variedade de opções para garantir que os clientes possam adotar facilmente a plataforma.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-110">Defender for Endpoint supports a wide variety of options to ensure that customers can easily adopt the platform.</span></span>

<span data-ttu-id="4a3ed-111">Reconhecendo que os ambientes e estruturas do cliente podem variar, o Defender for Endpoint foi criado com flexibilidade e controle granular para se ajustar a requisitos variados do cliente.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-111">Acknowledging that customer environments and structures can vary, Defender for Endpoint was created with flexibility and granular control to fit varying customer requirements.</span></span>

## <a name="endpoint-onboarding-and-portal-access"></a><span data-ttu-id="4a3ed-112">Integração do ponto de extremidade e acesso ao portal</span><span class="sxs-lookup"><span data-stu-id="4a3ed-112">Endpoint onboarding and portal access</span></span>

<span data-ttu-id="4a3ed-113">A integração de dispositivos está totalmente integrada ao Microsoft Endpoint Manager e Microsoft Intune para dispositivos cliente e ao Azure Defender para dispositivos de servidor, fornecendo uma experiência completa de configuração, implantação e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-113">Device onboarding is fully integrated into Microsoft Endpoint Manager and Microsoft Intune for client devices and Azure Defender for server devices, providing complete end-to-end experience of configuration, deployment, and monitoring.</span></span> <span data-ttu-id="4a3ed-114">Além disso, o Microsoft Defender para Ponto de Extremidade oferece suporte à Política de Grupo e outras ferramentas de terceiros usadas para gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-114">In addition, Microsoft Defender for Endpoint supports Group Policy and other third-party tools used for devices management.</span></span>

<span data-ttu-id="4a3ed-115">O Defender para Ponto de Extremidade fornece controle fino sobre o que os usuários com acesso ao portal podem ver e fazer por meio da flexibilidade do controle de acesso baseado em função (RBAC).</span><span class="sxs-lookup"><span data-stu-id="4a3ed-115">Defender for Endpoint provides fine-grained control over what users with access to the portal can see and do through the flexibility of role-based access control (RBAC).</span></span> <span data-ttu-id="4a3ed-116">O modelo RBAC dá suporte a todos os sabores da estrutura de equipes de segurança:</span><span class="sxs-lookup"><span data-stu-id="4a3ed-116">The RBAC model supports all flavors of security teams structure:</span></span>

- <span data-ttu-id="4a3ed-117">Organizações e equipes de segurança distribuídas globalmente</span><span class="sxs-lookup"><span data-stu-id="4a3ed-117">Globally distributed organizations and security teams</span></span>
- <span data-ttu-id="4a3ed-118">Equipes de operações de segurança de modelo hierárqueo</span><span class="sxs-lookup"><span data-stu-id="4a3ed-118">Tiered model security operations teams</span></span>
- <span data-ttu-id="4a3ed-119">Divisões totalmente segregadas com equipes de operações globais de segurança centralizadas simples</span><span class="sxs-lookup"><span data-stu-id="4a3ed-119">Fully segregated divisions with single centralized global security operations teams</span></span>

## <a name="available-apis"></a><span data-ttu-id="4a3ed-120">APIs disponíveis</span><span class="sxs-lookup"><span data-stu-id="4a3ed-120">Available APIs</span></span>
<span data-ttu-id="4a3ed-121">A solução do Microsoft Defender para Ponto de Extremidade foi criada sobre uma plataforma pronta para integração.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-121">The Microsoft Defender for Endpoint solution is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="4a3ed-122">O Defender for Endpoint expõe grande parte de seus dados e ações por meio de um conjunto de APIs programáticas.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-122">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="4a3ed-123">Essas APIs permitirão que você automatize fluxos de trabalho e inove com base nos recursos do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-123">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span>

![Imagem da API disponível e integração no Microsoft Defender para Ponto de Extremidade](images/mdatp-apis.png)

<span data-ttu-id="4a3ed-125">As APIs do Defender para Ponto de Extremidade podem ser agrupadas em três:</span><span class="sxs-lookup"><span data-stu-id="4a3ed-125">The Defender for Endpoint APIs can be grouped into three:</span></span>

- <span data-ttu-id="4a3ed-126">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4a3ed-126">Microsoft Defender for Endpoint APIs</span></span>
- <span data-ttu-id="4a3ed-127">API de streaming de dados não processados</span><span class="sxs-lookup"><span data-stu-id="4a3ed-127">Raw data streaming API</span></span>
- <span data-ttu-id="4a3ed-128">Integração SIEM</span><span class="sxs-lookup"><span data-stu-id="4a3ed-128">SIEM integration</span></span>

## <a name="microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="4a3ed-129">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4a3ed-129">Microsoft Defender for Endpoint APIs</span></span>

<span data-ttu-id="4a3ed-130">O Defender for Endpoint oferece um modelo de API em camadas expondo dados e recursos em um modelo estruturado, claro e fácil de usar, exposto por meio de um modelo de autorização e autenticação padrão baseado no Azure AD que permite o acesso no contexto de usuários ou aplicativos SaaS.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-130">Defender for Endpoint offers a layered API model exposing data and capabilities in a structured, clear, and easy to use model, exposed through a standard Azure  AD-based authentication and authorization model allowing access in context of users or SaaS applications.</span></span> <span data-ttu-id="4a3ed-131">O modelo de API foi projetado para expor entidades e recursos de forma consistente.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-131">The API model was designed to expose entities and capabilities in a consistent form.</span></span>

<span data-ttu-id="4a3ed-132">Assista a este vídeo para uma visão geral rápida do Defender para APIs do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-132">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span>
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="4a3ed-133">A **API** de Investigação expõe a riqueza do Defender para o Ponto de Extremidade - expondo entidades calculadas ou 'perfilada' (por exemplo, dispositivo, usuário e arquivo) e eventos discretos (por exemplo, criação de processo e criação de arquivo) que normalmente descreve um comportamento relacionado a uma entidade, permitindo o acesso a dados por meio de interfaces de investigação permitindo um acesso baseado em consulta aos dados.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-133">The **Investigation API** exposes the richness of Defender for Endpoint - exposing calculated or 'profiled' entities (for example, device, user, and file) and discrete events (for example, process creation and file creation) which typically describes a behavior related to an entity, enabling access to data via investigation interfaces allowing a query-based access to data.</span></span> <span data-ttu-id="4a3ed-134">Para obter mais informações, consulte [APIs com suporte.](exposed-apis-list.md)</span><span class="sxs-lookup"><span data-stu-id="4a3ed-134">For more information, see [Supported APIs](exposed-apis-list.md).</span></span>

<span data-ttu-id="4a3ed-135">A **API** de Resposta expõe a capacidade de tomar ações no serviço e em dispositivos, permitindo que os clientes ingeram indicadores, gerenciem configurações, status de alerta, bem como ações de resposta em dispositivos programaticamente, como isolar dispositivos da rede, arquivos de quarentena e outros.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-135">The **Response API** exposes the ability to take actions in the service and on devices, enabling customers to ingest indicators, manage settings, alert status, as well as take response actions on devices programmatically such as isolate devices from the network, quarantine files, and others.</span></span>

## <a name="raw-data-streaming-api"></a><span data-ttu-id="4a3ed-136">API de streaming de dados não processados</span><span class="sxs-lookup"><span data-stu-id="4a3ed-136">Raw data streaming API</span></span>

<span data-ttu-id="4a3ed-137">A API de streaming de dados brutos do Defender for Endpoint oferece a capacidade para os clientes enviarem eventos e alertas em tempo real de suas instâncias conforme ocorrem em um único fluxo de dados, fornecendo um mecanismo de entrega de alta taxa de transferência de baixa latência.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-137">Defender for Endpoint raw data streaming API provides the ability for customers to ship real-time events and alerts from their instances as they occur within a single data stream, providing a low latency, high throughput delivery mechanism.</span></span>

<span data-ttu-id="4a3ed-138">As informações do evento Defender for Endpoint são empurradas diretamente para o armazenamento do Azure para retenção de dados de longo prazo ou para hubs de eventos do Azure para consumo por serviços de visualização ou mecanismos de processamento de dados adicionais.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-138">The Defender for Endpoint event information is pushed directly to Azure storage for long-term data retention, or to Azure Event Hubs for consumption by visualization services or additional data processing engines.</span></span>

<span data-ttu-id="4a3ed-139">Para obter mais informações, consulte [RAW data streaming API](raw-data-export.md).</span><span class="sxs-lookup"><span data-stu-id="4a3ed-139">For more information, see [Raw data streaming API](raw-data-export.md).</span></span>

<span data-ttu-id="4a3ed-140">A nova MICROSOFT 365 DEFENDER de Streaming inclui eventos de email e alerta, além de eventos de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-140">The new Microsoft 365 Defender Streaming API includes email and alert events in addition to device events.</span></span>
<span data-ttu-id="4a3ed-141">Para obter mais informações, [consulte Microsoft 365 Defender API de Streaming.](../defender/streaming-api.md)</span><span class="sxs-lookup"><span data-stu-id="4a3ed-141">For more information, see [Microsoft 365 Defender Streaming API](../defender/streaming-api.md).</span></span>

## <a name="siem-api"></a><span data-ttu-id="4a3ed-142">SIEM API</span><span class="sxs-lookup"><span data-stu-id="4a3ed-142">SIEM API</span></span>

<span data-ttu-id="4a3ed-143">Quando você habilita a integração de informações de segurança e gerenciamento de eventos (SIEM), ele permite que você retire detecções do Central de Segurança do Microsoft Defender usando sua solução SIEM ou conectando-se diretamente à API REST de detecções.</span><span class="sxs-lookup"><span data-stu-id="4a3ed-143">When you enable security information and event management (SIEM) integration, it allows you to pull detections from Microsoft Defender Security Center using your SIEM solution or by connecting directly to the detections REST API.</span></span> <span data-ttu-id="4a3ed-144">Isso ativa a seção detalhes de acesso do conector SIEM com valores pré-preenchidos e um aplicativo é criado em seu locatário Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="4a3ed-144">This activates the SIEM connector access details section with pre-populated values and an application is created under your Azure Active Directory (Azure AD) tenant.</span></span> <span data-ttu-id="4a3ed-145">Para obter mais informações, consulte [Integração siem](enable-siem-integration.md).</span><span class="sxs-lookup"><span data-stu-id="4a3ed-145">For more information, see [SIEM integration](enable-siem-integration.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a3ed-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4a3ed-146">Related topics</span></span>

- [<span data-ttu-id="4a3ed-147">Acessar as APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4a3ed-147">Access the Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
- [<span data-ttu-id="4a3ed-148">APIs com suporte</span><span class="sxs-lookup"><span data-stu-id="4a3ed-148">Supported APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="4a3ed-149">Oportunidades para parceiros técnicos</span><span class="sxs-lookup"><span data-stu-id="4a3ed-149">Technical partner opportunities</span></span>](partner-integration.md)