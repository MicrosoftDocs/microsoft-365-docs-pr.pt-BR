---
title: Integração do servidor SIEM com aplicativos e serviços do Microsoft 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Obter uma visão geral da integração do servidor SIEM (Gerenciamento de Eventos e Informações de Segurança) com seus aplicativos e serviços de nuvem do Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f29da87aa6eab1852330092d93187a27b2d36eb2
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167138"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="16b67-103">Integração do servidor de Gerenciamento de Eventos e Informações de Segurança (SIEM) com aplicativos e serviços do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16b67-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="16b67-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="16b67-104">**Applies to**</span></span>
- [<span data-ttu-id="16b67-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="16b67-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="16b67-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="16b67-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="16b67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16b67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="16b67-108">Resumo</span><span class="sxs-lookup"><span data-stu-id="16b67-108">Summary</span></span>

<span data-ttu-id="16b67-109">Sua organização está usando ou planejando obter um servidor de Gerenciamento de Eventos e Informações de Segurança (SIEM) ?</span><span class="sxs-lookup"><span data-stu-id="16b67-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="16b67-110">Você deve estar se perguntando como ele se integra ao Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="16b67-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="16b67-111">Este artigo fornece uma lista de recursos que você pode usar para integrar seu servidor SIEM aos serviços e aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="16b67-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="16b67-112">Se você ainda não tiver um servidor SIEM e estiver explorando suas opções, considere **[o Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="16b67-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="16b67-113">Preciso de um servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="16b67-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="16b67-114">Se você precisa de um servidor SIEM depende de muitos fatores, como os requisitos de segurança da sua organização e onde seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="16b67-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="16b67-115">O Microsoft 365 inclui uma ampla variedade de recursos de segurança que atendem às necessidades de segurança de muitas organizações sem servidores adicionais, como um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="16b67-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="16b67-116">Algumas organizações têm circunstâncias especiais que exigem o uso de um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="16b67-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="16b67-117">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="16b67-117">Here are some examples:</span></span>

- <span data-ttu-id="16b67-118">*A Fabrikam* tem alguns conteúdos e aplicativos no local e alguns na nuvem (eles têm uma implantação híbrida na nuvem).</span><span class="sxs-lookup"><span data-stu-id="16b67-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="16b67-119">Para obter relatórios de segurança em todo o conteúdo e aplicativos, a Fabrikam implementou um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="16b67-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="16b67-120">*A Contoso* é uma organização de serviços financeiros que tem requisitos de segurança particularmente rigorosos.</span><span class="sxs-lookup"><span data-stu-id="16b67-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="16b67-121">Eles adicionaram um servidor SIEM ao seu ambiente para aproveitar a proteção de segurança extra necessária.</span><span class="sxs-lookup"><span data-stu-id="16b67-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="16b67-122">Integração do servidor SIEM com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16b67-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="16b67-123">Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="16b67-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="16b67-124">A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com entradas de servidor SIEM e recursos para saber mais.</span><span class="sxs-lookup"><span data-stu-id="16b67-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="16b67-125">Serviço ou aplicativo do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="16b67-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="16b67-126">Entradas/métodos do servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="16b67-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="16b67-127">Recursos para saber mais</span><span class="sxs-lookup"><span data-stu-id="16b67-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="16b67-128">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="16b67-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="16b67-129">Logs de auditoria</span><span class="sxs-lookup"><span data-stu-id="16b67-129">Audit logs</span></span>|[<span data-ttu-id="16b67-130">Integração siEM com o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="16b67-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="16b67-131">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="16b67-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="16b67-132">Ponto de extremidade HTTPS hospedado no Azure</span><span class="sxs-lookup"><span data-stu-id="16b67-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="16b67-133">API REST</span><span class="sxs-lookup"><span data-stu-id="16b67-133">REST API</span></span>|[<span data-ttu-id="16b67-134">Pull alerts to your SIEM tools</span><span class="sxs-lookup"><span data-stu-id="16b67-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="16b67-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="16b67-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="16b67-136">Integração de log</span><span class="sxs-lookup"><span data-stu-id="16b67-136">Log integration</span></span>|[<span data-ttu-id="16b67-137">Integração do SIEM com o Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="16b67-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="16b67-138">Dê uma olhada no [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)</span><span class="sxs-lookup"><span data-stu-id="16b67-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="16b67-139">O Azure Sentinel vem com conectores para soluções da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16b67-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="16b67-140">Esses conectores estão disponíveis "imediatamente" e oferecem integração em tempo real.</span><span class="sxs-lookup"><span data-stu-id="16b67-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="16b67-141">Você pode usar o Azure Sentinel com as soluções do Microsoft 365 Defender e os serviços do Microsoft 365, incluindo o Office 365, o Azure AD, o Microsoft Defender for Identity, o Microsoft Cloud App Security e muito mais.</span><span class="sxs-lookup"><span data-stu-id="16b67-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="16b67-142">O log de auditoria deve estar ligado</span><span class="sxs-lookup"><span data-stu-id="16b67-142">Audit logging must be turned on</span></span>

<span data-ttu-id="16b67-143">Certifique-se de que o log de auditoria está ligado antes de configurar a integração com o servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="16b67-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="16b67-144">Para o SharePoint Online, o OneDrive for Business e o Azure Active Directory, o log de auditoria está ativado no Centro de Conformidade & [Segurança.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="16b67-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="16b67-145">Para o Exchange Online, confira [Gerenciar auditoria de caixa de correio.](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="16b67-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="16b67-146">Mais recursos</span><span class="sxs-lookup"><span data-stu-id="16b67-146">More resources</span></span>

[<span data-ttu-id="16b67-147">Integrar soluções de segurança no Azure Defender</span><span class="sxs-lookup"><span data-stu-id="16b67-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="16b67-148">Integrar alertas da API de Segurança do Microsoft Graph com um SIEM</span><span class="sxs-lookup"><span data-stu-id="16b67-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
