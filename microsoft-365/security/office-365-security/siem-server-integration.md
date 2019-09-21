---
title: Integração do servidor SIEM com o Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 06/17/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 'Resumo: Leia este artigo para obter uma visão geral da integração do SIEM Server com o Microsoft 365.'
ms.openlocfilehash: 97f1c1d1f1862d140e014b4460ac9f40cb1934bb
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073840"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="b203a-103">Integração com o servidor SIEM com serviços e aplicativos da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b203a-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="overview"></a><span data-ttu-id="b203a-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="b203a-104">Overview</span></span>

<span data-ttu-id="b203a-105">Se sua organização estiver usando um servidor de gerenciamento de eventos e informações de segurança (SIEM) ou se você estiver planejando obter um servidor SIEM em breve, talvez esteja se perguntando como ele se integrará ao seu Microsoft 365, incluindo o Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="b203a-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with your Microsoft 365, including Office 365 E5.</span></span> <span data-ttu-id="b203a-106">Se você precisa de um servidor SIEM depende de vários fatores, como os requisitos de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b203a-106">Whether you need a SIEM server depends on many factors, such as your organization's security requirements.</span></span> <span data-ttu-id="b203a-107">A Microsoft 365 oferece uma variedade de recursos de segurança; no entanto, se sua organização tiver conteúdo e aplicativos locais e na nuvem (como no caso de uma implantação de nuvem híbrida), você pode considerar a adição de um servidor SIEM para proteção adicional.</span><span class="sxs-lookup"><span data-stu-id="b203a-107">Microsoft 365 offers a variety of security features; however, if your organization has content and applications on premises and in the cloud (as in the case of a hybrid cloud deployment), you might consider adding a SIEM server for extra protection.</span></span> <span data-ttu-id="b203a-108">Ou, se sua organização tiver requisitos de segurança especialmente rigorosos que você deve atender, você pode considerar adicionar um servidor SIEM ao seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b203a-108">Or, if your organization has particularly stringent security requirements you must meet, you might consider adding a SIEM server to your environment.</span></span>

## <a name="siem-server-integration-microsoft-365"></a><span data-ttu-id="b203a-109">Integração com o servidor SIEM Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b203a-109">SIEM server integration Microsoft 365</span></span>

<span data-ttu-id="b203a-110">Um servidor SIEM pode receber dados de uma ampla variedade de serviços e aplicativos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b203a-110">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="b203a-111">A tabela a seguir lista vários serviços e aplicativos do Microsoft 365, juntamente com as entradas do servidor SIEM e onde obter mais informações sobre a integração do SIEM Server.</span><span class="sxs-lookup"><span data-stu-id="b203a-111">The following table lists several Microsoft 365 services and applications along with SIEM server inputs and where to go to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="b203a-112">Serviço ou aplicativo Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b203a-112">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="b203a-113">Entradas do servidor SIEM</span><span class="sxs-lookup"><span data-stu-id="b203a-113">SIEM server inputs</span></span> | <span data-ttu-id="b203a-114">Recursos para saber mais</span><span class="sxs-lookup"><span data-stu-id="b203a-114">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="b203a-115">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="b203a-115">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md) <br/><span data-ttu-id="b203a-116">ou</span><span class="sxs-lookup"><span data-stu-id="b203a-116">or</span></span><br/>[<span data-ttu-id="b203a-117">Office 365 Threat Intelligence</span><span class="sxs-lookup"><span data-stu-id="b203a-117">Office 365 Threat Intelligence</span></span>](office-365-ti.md) | <span data-ttu-id="b203a-118">Logs de auditoria</span><span class="sxs-lookup"><span data-stu-id="b203a-118">Audit logs</span></span> | [<span data-ttu-id="b203a-119">Integração do SIEM com a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="b203a-119">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="b203a-120">Segurança no Aplicativo da Nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b203a-120">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="b203a-121">Integração de log</span><span class="sxs-lookup"><span data-stu-id="b203a-121">Log integration</span></span> | [<span data-ttu-id="b203a-122">Integração do SIEM com o Microsoft Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="b203a-122">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |
| [<span data-ttu-id="b203a-123">Proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b203a-123">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="b203a-124">Integração de log</span><span class="sxs-lookup"><span data-stu-id="b203a-124">Log integration</span></span> | [<span data-ttu-id="b203a-125">Extrair alertas para suas ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="b203a-125">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| <span data-ttu-id="b203a-126">[Central de segurança do Azure](https://docs.microsoft.com/azure/security-center/security-center-intro) (Proteção contra ameaças e detecção de ameaças)</span><span class="sxs-lookup"><span data-stu-id="b203a-126">[Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) (Threat Protection and Threat Detection)</span></span> | <span data-ttu-id="b203a-127">Alertas</span><span class="sxs-lookup"><span data-stu-id="b203a-127">Alerts</span></span> | [<span data-ttu-id="b203a-128">Exportação de dados de segurança do Azure para configuração de pipeline SIEM-visualização</span><span class="sxs-lookup"><span data-stu-id="b203a-128">Azure Security data export to SIEM - Pipeline Configuration - Preview</span></span>](https://docs.microsoft.com/azure/security-center/security-center-export-data-to-siem) |
|[<span data-ttu-id="b203a-129">Análises avançadas de ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="b203a-129">Azure Advanced Threat Analytics</span></span>](https://docs.microsoft.com/azure/security/azure-threat-detection) | <span data-ttu-id="b203a-130">Azure monitor</span><span class="sxs-lookup"><span data-stu-id="b203a-130">Azure Monitor</span></span> | [<span data-ttu-id="b203a-131">Escrever Usar o Azure monitor para se integrar às ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="b203a-131">(Blog) Use Azure Monitor to integrate with SIEM tools</span></span>](https://azure.microsoft.com/blog/use-azure-monitor-to-integrate-with-siem-tools) |
|[<span data-ttu-id="b203a-132">Proteção de identidade do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b203a-132">Azure Active Directory Identity Protection</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/overview) |<span data-ttu-id="b203a-133">Integração de log</span><span class="sxs-lookup"><span data-stu-id="b203a-133">Log integration</span></span> |[<span data-ttu-id="b203a-134">Integrar alertas da API de Segurança do Microsoft Graph com um SIEM</span><span class="sxs-lookup"><span data-stu-id="b203a-134">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-siemintegration) |


## <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="b203a-135">O log de auditoria deve estar ativado</span><span class="sxs-lookup"><span data-stu-id="b203a-135">Audit logging must be turned on</span></span>

<span data-ttu-id="b203a-136">Certifique-se de que o registro em log de auditoria está ativado antes de configurar a integração do servidor SIEM.</span><span class="sxs-lookup"><span data-stu-id="b203a-136">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="b203a-137">Para o SharePoint Online, OneDrive for Business e Azure Active Directory, [o log de auditoria está ativado no centro de conformidade de & de segurança](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="b203a-137">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="b203a-138">Para o Exchange Online, o [log de auditoria é ativado com o Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span><span class="sxs-lookup"><span data-stu-id="b203a-138">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="b203a-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="b203a-139">See Also</span></span>

[<span data-ttu-id="b203a-140">Adoção da nuvem e soluções híbridas</span><span class="sxs-lookup"><span data-stu-id="b203a-140">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="b203a-141">Guias do Laboratório de Teste (TLGs) para adoção de nuvem</span><span class="sxs-lookup"><span data-stu-id="b203a-141">Cloud adoption Test Lab Guides (TLGs)</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)


