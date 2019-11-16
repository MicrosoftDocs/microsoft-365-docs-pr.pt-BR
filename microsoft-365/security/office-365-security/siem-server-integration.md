---
title: Integração com o servidor SIEM com serviços e aplicativos da Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Leia este artigo para obter uma visão geral da integração do SIEM Server com o Microsoft 365.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677504"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="ace21-103">Integração com o servidor SIEM com serviços e aplicativos da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ace21-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="ace21-104">Resumo</span><span class="sxs-lookup"><span data-stu-id="ace21-104">Summary</span></span>

<span data-ttu-id="ace21-105">Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM) ou se você estiver planejando obter um servidor SIEM em breve, talvez esteja se perguntando como ele se integrará com o Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ace21-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ace21-106">Este artigo fornece uma lista de recursos que você pode usar para configurar a integração do SIEM Server com seus serviços e aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ace21-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="ace21-107">Se você ainda não tiver um servidor SIEM e estiver explorando suas opções, considere o **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span><span class="sxs-lookup"><span data-stu-id="ace21-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="ace21-108">Preciso de um servidor SIEM?</span><span class="sxs-lookup"><span data-stu-id="ace21-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="ace21-109">Se você precisa de um servidor SIEM depende de vários fatores, como os requisitos de segurança da sua organização e onde seus dados residem.</span><span class="sxs-lookup"><span data-stu-id="ace21-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="ace21-110">O Microsoft 365 inclui uma ampla variedade de recursos de segurança que atendem às necessidades de segurança de várias organizações sem servidores adicionais, como um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="ace21-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="ace21-111">Algumas organizações têm circunstâncias especiais que exigem o uso de um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="ace21-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="ace21-112">Aqui estão alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="ace21-112">Here are some examples:</span></span>

- <span data-ttu-id="ace21-113">A *Fabrikam* tem alguns conteúdos e aplicativos locais e alguns na nuvem (eles têm uma implantação de nuvem híbrida).</span><span class="sxs-lookup"><span data-stu-id="ace21-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="ace21-114">Para obter relatórios de segurança em todos os seus aplicativos e conteúdo, a Fabrikam implementou um servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="ace21-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="ace21-115">A *contoso* é uma organização de serviços financeiros que tem requisitos de segurança especialmente rígidos.</span><span class="sxs-lookup"><span data-stu-id="ace21-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="ace21-116">Eles adicionaram um servidor SIEM ao seu ambiente para aproveitar a proteção extra de segurança de que precisam.</span><span class="sxs-lookup"><span data-stu-id="ace21-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="ace21-117">Integração do servidor SIEM com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ace21-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="ace21-118">Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ace21-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="ace21-119">A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com as entradas do servidor SIEM, e os recursos para saber mais sobre a integração do SIEM Server.</span><span class="sxs-lookup"><span data-stu-id="ace21-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="ace21-120">Serviço ou aplicativo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ace21-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="ace21-121">Entradas do servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="ace21-121">SIEM server inputs</span></span> | <span data-ttu-id="ace21-122">Recursos para saber mais</span><span class="sxs-lookup"><span data-stu-id="ace21-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="ace21-123">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="ace21-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="ace21-124">Logs de auditoria</span><span class="sxs-lookup"><span data-stu-id="ace21-124">Audit logs</span></span> | [<span data-ttu-id="ace21-125">Integração do SIEM com a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="ace21-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="ace21-126">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ace21-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="ace21-127">Ponto de extremidade HTTPS hospedado no Azure</span><span class="sxs-lookup"><span data-stu-id="ace21-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="ace21-128">API REST</span><span class="sxs-lookup"><span data-stu-id="ace21-128">REST API</span></span>| [<span data-ttu-id="ace21-129">Extrair alertas para suas ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="ace21-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="ace21-130">Segurança no Aplicativo da Nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ace21-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="ace21-131">Integração de log</span><span class="sxs-lookup"><span data-stu-id="ace21-131">Log integration</span></span> | [<span data-ttu-id="ace21-132">Integração do SIEM com o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="ace21-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="ace21-133">Dê uma olhada no [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), que vem com vários conectores para soluções da Microsoft, disponível prontos para uso e fornecendo integração em tempo real, incluindo soluções de proteção contra ameaças da Microsoft e fontes do Microsoft 365, incluindo o Office 365, o Azure AD, o Azure ATP e o Microsoft Cloud app Security e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ace21-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="ace21-134">O log de auditoria deve estar ativado</span><span class="sxs-lookup"><span data-stu-id="ace21-134">Audit logging must be turned on</span></span>

<span data-ttu-id="ace21-135">Certifique-se de que o registro em log de auditoria está ativado antes de configurar a integração do servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="ace21-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="ace21-136">Para o SharePoint Online, OneDrive for Business e Azure Active Directory, [o log de auditoria está ativado no centro de conformidade de & de segurança](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="ace21-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="ace21-137">Para o Exchange Online, o [log de auditoria é ativado com o Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="ace21-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="ace21-138">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ace21-138">Additional resources</span></span>

[<span data-ttu-id="ace21-139">Integrar soluções de segurança na central de segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="ace21-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="ace21-140">Integrar alertas da API de Segurança do Microsoft Graph com um SIEM</span><span class="sxs-lookup"><span data-stu-id="ace21-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)