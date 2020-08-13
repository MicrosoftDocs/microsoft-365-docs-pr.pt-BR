---
title: Integração com o servidor SIEM com serviços e aplicativos da Microsoft 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Obtenha uma visão geral da integração do servidor de gerenciamento de eventos e informações de segurança (SIEM) com seus serviços e aplicativos em nuvem da Microsoft 365
ms.openlocfilehash: d2be5e0127adf25b3884e3717caccf60d4db1d28
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653564"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="22fed-103">Integração do servidor de gerenciamento de eventos e informações de segurança (SIEM) com serviços e aplicativos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22fed-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="22fed-104">Resumo</span><span class="sxs-lookup"><span data-stu-id="22fed-104">Summary</span></span>

<span data-ttu-id="22fed-105">Sua organização está usando ou planejando obter um servidor de gerenciamento de informações e de segurança (SIEM)?</span><span class="sxs-lookup"><span data-stu-id="22fed-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="22fed-106">Você pode estar se perguntando como ele se integra ao Microsoft 365 ou ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="22fed-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="22fed-107">Este artigo fornece uma lista de recursos que você pode usar para integrar seu servidor SIEM com serviços e aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22fed-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="22fed-108">Se você ainda não tiver um servidor SIEM e estiver explorando suas opções, considere o **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="22fed-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="22fed-109">Preciso de um servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="22fed-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="22fed-110">Se você precisa de um servidor SIEM depende de vários fatores, como os requisitos de segurança da sua organização e onde seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="22fed-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="22fed-111">O Microsoft 365 inclui uma ampla variedade de recursos de segurança que atendem às necessidades de segurança de várias organizações sem servidores adicionais, como um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="22fed-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="22fed-112">Algumas organizações têm circunstâncias especiais que exigem o uso de um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="22fed-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="22fed-113">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="22fed-113">Here are some examples:</span></span>

- <span data-ttu-id="22fed-114">A *Fabrikam* tem alguns conteúdos e aplicativos locais e alguns na nuvem (eles têm uma implantação de nuvem híbrida).</span><span class="sxs-lookup"><span data-stu-id="22fed-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="22fed-115">Para obter relatórios de segurança em todos os seus aplicativos e conteúdo, a Fabrikam implementou um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="22fed-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="22fed-116">A *contoso* é uma organização de serviços financeiros que tem requisitos de segurança especialmente rígidos.</span><span class="sxs-lookup"><span data-stu-id="22fed-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="22fed-117">Eles adicionaram um servidor SIEM ao seu ambiente para aproveitar a proteção extra de segurança de que precisam.</span><span class="sxs-lookup"><span data-stu-id="22fed-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="22fed-118">Integração do servidor SIEM com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22fed-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="22fed-119">Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="22fed-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="22fed-120">A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com entradas e recursos do servidor SIEM para saber mais.</span><span class="sxs-lookup"><span data-stu-id="22fed-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="22fed-121">Serviço ou aplicativo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22fed-121">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="22fed-122">Entradas/métodos do servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="22fed-122">SIEM server inputs/methods</span></span>|<span data-ttu-id="22fed-123">Recursos para saber mais</span><span class="sxs-lookup"><span data-stu-id="22fed-123">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="22fed-124">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="22fed-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="22fed-125">Logs de auditoria</span><span class="sxs-lookup"><span data-stu-id="22fed-125">Audit logs</span></span>|[<span data-ttu-id="22fed-126">Integração do SIEM com a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="22fed-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="22fed-127">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="22fed-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="22fed-128">Ponto de extremidade HTTPS hospedado no Azure</span><span class="sxs-lookup"><span data-stu-id="22fed-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="22fed-129">API REST</span><span class="sxs-lookup"><span data-stu-id="22fed-129">REST API</span></span>|[<span data-ttu-id="22fed-130">Extrair alertas para suas ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="22fed-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="22fed-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="22fed-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="22fed-132">Integração de log</span><span class="sxs-lookup"><span data-stu-id="22fed-132">Log integration</span></span>|[<span data-ttu-id="22fed-133">Integração do SIEM com o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="22fed-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="22fed-134">Dê uma olhada no [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="22fed-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="22fed-135">O Azure Sentinel vem com conectores para soluções da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="22fed-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="22fed-136">Esses conectores estão disponíveis "prontos para uso" e fornecem integração em tempo real.</span><span class="sxs-lookup"><span data-stu-id="22fed-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="22fed-137">Você pode usar o Azure Sentinel com suas soluções de proteção contra ameaças da Microsoft e serviços do Microsoft 365, incluindo o Office 365, o Azure AD, o Azure ATP, o Microsoft Cloud app Security e muito mais.</span><span class="sxs-lookup"><span data-stu-id="22fed-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="22fed-138">O log de auditoria deve estar ativado</span><span class="sxs-lookup"><span data-stu-id="22fed-138">Audit logging must be turned on</span></span>

<span data-ttu-id="22fed-139">Certifique-se de que o log de auditoria está ativado antes de configurar a integração com o servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="22fed-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="22fed-140">Para o SharePoint Online, OneDrive for Business e Azure Active Directory, [o log de auditoria está ativado no centro de conformidade de & de segurança](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="22fed-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="22fed-141">Para o Exchange Online, consulte [gerenciar a auditoria de caixa de correio](../../compliance/enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="22fed-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="22fed-142">Mais recursos</span><span class="sxs-lookup"><span data-stu-id="22fed-142">More resources</span></span>

[<span data-ttu-id="22fed-143">Integrar soluções de segurança na central de segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="22fed-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="22fed-144">Integrar alertas da API de Segurança do Microsoft Graph com um SIEM</span><span class="sxs-lookup"><span data-stu-id="22fed-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
