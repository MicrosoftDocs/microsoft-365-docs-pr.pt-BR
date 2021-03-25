---
title: Gerenciar a migração pós-migração do Microsoft Defender para Ponto de Extremidade
description: Agora que você alternou para o Microsoft Defender para Ponto de Extremidade, sua próxima etapa é gerenciar seus recursos de proteção contra ameaças
keywords: pós-migração, gerenciar, operações, manutenção, utilização, proteção avançada contra ameaças do Windows Defender, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: 54302f38f0fd63560ecd1c5545efa4621c6b9bbd
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185856"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a><span data-ttu-id="cb29b-104">Gerenciar o Microsoft Defender para Ponto de Extremidade, pós-migração</span><span class="sxs-lookup"><span data-stu-id="cb29b-104">Manage Microsoft Defender for Endpoint, post migration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cb29b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cb29b-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb29b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cb29b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb29b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb29b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cb29b-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="cb29b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="cb29b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="cb29b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="cb29b-110">Depois de ter movido da sua solução antivírus e proteção de ponto de extremidade anterior para o Microsoft Defender para Ponto de Extremidade, a próxima etapa é gerenciar seus recursos e recursos.</span><span class="sxs-lookup"><span data-stu-id="cb29b-110">After you have moved from your previous endpoint protection and antivirus solution to Microsoft Defender for Endpoint, your next step is to manage your features and capabilities.</span></span> <span data-ttu-id="cb29b-111">Recomendamos usar [o Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), que inclui o Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e o [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction), para gerenciar os dispositivos e as configurações de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb29b-111">We recommend using [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), which includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction), to manage your organization's devices and security settings.</span></span> <span data-ttu-id="cb29b-112">No entanto, você pode usar outras ferramentas/métodos, como Objetos de Política de Grupo nos Serviços de Domínio do [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)</span><span class="sxs-lookup"><span data-stu-id="cb29b-112">However, you can use other tools/methods, such as [Group Policy Objects in Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy).</span></span> 

<span data-ttu-id="cb29b-113">A tabela a seguir lista várias ferramentas/métodos que você pode usar, com links para saber mais.</span><span class="sxs-lookup"><span data-stu-id="cb29b-113">The following table lists various tools/methods you can use, with links to learn more.</span></span> 
<br/><br/>

|<span data-ttu-id="cb29b-114">Ferramenta/Método</span><span class="sxs-lookup"><span data-stu-id="cb29b-114">Tool/Method</span></span>  |<span data-ttu-id="cb29b-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="cb29b-115">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="cb29b-116">**[Insights do painel de gerenciamento de ameaças e vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** no Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="cb29b-116">**[Threat and vulnerability management dashboard insights](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span> |<span data-ttu-id="cb29b-117">O painel & gerenciamento de vulnerabilidades fornece informações ativos que sua equipe de operações de segurança pode usar para reduzir a exposição e melhorar a postura de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="cb29b-117">The threat & vulnerability management dashboard provides actionable information that your security operations team can use to reduce exposure and improve your organization's security posture.</span></span> <br/><br/><span data-ttu-id="cb29b-118">Consulte [Gerenciamento & de vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) e Visão geral do Centro de Segurança do Microsoft [Defender.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)</span><span class="sxs-lookup"><span data-stu-id="cb29b-118">See [Threat & vulnerability management](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) and [Overview of the Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use).</span></span>  |
|<span data-ttu-id="cb29b-119">**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (recomendado)</span><span class="sxs-lookup"><span data-stu-id="cb29b-119">**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (recommended)</span></span>    |<span data-ttu-id="cb29b-120">O Microsoft Intune (Intune), um componente do [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem/endpoint-manager-overview)se concentra no gerenciamento de dispositivo móvel (MDM) e no gerenciamento de aplicativos móveis (MAM).</span><span class="sxs-lookup"><span data-stu-id="cb29b-120">Microsoft Intune (Intune), a component of [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), focuses on mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="cb29b-121">Com o Intune, você controla como os dispositivos da sua organização são usados, incluindo telefones celulares, tablets e laptops.</span><span class="sxs-lookup"><span data-stu-id="cb29b-121">With Intune, you control how your organization’s devices are used, including mobile phones, tablets, and laptops.</span></span> <span data-ttu-id="cb29b-122">Você também pode configurar políticas específicas para controlar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cb29b-122">You can also configure specific policies to control applications.</span></span> <br/><br/><span data-ttu-id="cb29b-123">Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade usando o Intune](manage-atp-post-migration-intune.md).</span><span class="sxs-lookup"><span data-stu-id="cb29b-123">See [Manage Microsoft Defender for Endpoint using Intune](manage-atp-post-migration-intune.md).</span></span>         |
|<span data-ttu-id="cb29b-124">**[Gerenciador de Configuração do Microsoft Endpoint](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**</span><span class="sxs-lookup"><span data-stu-id="cb29b-124">**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**</span></span>     |<span data-ttu-id="cb29b-125">O Microsoft Endpoint Manager (Configuration Manager), anteriormente conhecido como System Center Configuration Manager, é um componente do [Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/endpoint-manager-overview)</span><span class="sxs-lookup"><span data-stu-id="cb29b-125">Microsoft Endpoint Manager (Configuration Manager), formerly known as System Center Configuration Manager, is a component of [Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview).</span></span> <span data-ttu-id="cb29b-126">O Configuration Manager é uma ferramenta poderosa para gerenciar seus usuários, dispositivos e software.</span><span class="sxs-lookup"><span data-stu-id="cb29b-126">Configuration Manager is a powerful tool to manage your users, devices, and software.</span></span><br/><br/><span data-ttu-id="cb29b-127">Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager](manage-atp-post-migration-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="cb29b-127">See [Manage Microsoft Defender for Endpoint with Configuration Manager](manage-atp-post-migration-configuration-manager.md).</span></span>        |
|<span data-ttu-id="cb29b-128">**[Objetos de Política de Grupo nos Serviços de Domínio do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)**</span><span class="sxs-lookup"><span data-stu-id="cb29b-128">**[Group Policy Objects in Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)**</span></span> |<span data-ttu-id="cb29b-129">[Os Serviços de Domínio do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/overview) incluem Objetos de Política de Grupo integrados para usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cb29b-129">[Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/overview) includes built-in Group Policy Objects for users and devices.</span></span> <span data-ttu-id="cb29b-130">Você pode personalizar os Objetos de Política de Grupo integrados conforme necessário para seu ambiente, bem como criar objetos de política de grupo personalizados e unidades organizacionais (OUs).</span><span class="sxs-lookup"><span data-stu-id="cb29b-130">You can customize the built-in Group Policy Objects as needed for your environment, as well as create custom Group Policy Objects and organizational units (OUs).</span></span> <br/><br/><span data-ttu-id="cb29b-131">Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo.](manage-atp-post-migration-group-policy-objects.md)</span><span class="sxs-lookup"><span data-stu-id="cb29b-131">See [Manage Microsoft Defender for Endpoint with Group Policy Objects](manage-atp-post-migration-group-policy-objects.md).</span></span> |
|<span data-ttu-id="cb29b-132">**[PowerShell, WMI e MPCmdRun.exe](manage-atp-post-migration-other-tools.md)**</span><span class="sxs-lookup"><span data-stu-id="cb29b-132">**[PowerShell, WMI, and MPCmdRun.exe](manage-atp-post-migration-other-tools.md)**</span></span> |<span data-ttu-id="cb29b-133">*Recomendamos usar o Microsoft Endpoint Manager (que inclui o Intune e o Configuration Manager) para gerenciar recursos de proteção contra ameaças nos dispositivos da sua organização. No entanto, você pode configurar algumas configurações, como as configurações do Microsoft Defender Antivírus em dispositivos individuais (pontos de extremidade) com PowerShell, WMI ou a ferramenta MPCmdRun.exe.*</span><span class="sxs-lookup"><span data-stu-id="cb29b-133">*We recommend using Microsoft Endpoint Manager (which includes Intune and Configuration Manager) to manage threat protection features on your organization's devices. However, you can configure some settings, such as Microsoft Defender Antivirus settings on individual devices (endpoints) with PowerShell, WMI, or the MPCmdRun.exe tool.*</span></span><br/><br/><span data-ttu-id="cb29b-134">Você pode usar o PowerShell para gerenciar o Microsoft Defender Antivírus, explorar a proteção e suas regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="cb29b-134">You can use PowerShell to manage Microsoft Defender Antivirus, exploit protection, and your attack surface reduction rules.</span></span> <span data-ttu-id="cb29b-135">Consulte [Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).</span><span class="sxs-lookup"><span data-stu-id="cb29b-135">See [Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).</span></span><br/><br/><span data-ttu-id="cb29b-136">Você pode usar a Instrumentação de Gerenciamento do Windows (WMI) para gerenciar o Microsoft Defender Antivírus e as exclusões.</span><span class="sxs-lookup"><span data-stu-id="cb29b-136">You can use Windows Management Instrumentation (WMI) to manage Microsoft Defender Antivirus and exclusions.</span></span> <span data-ttu-id="cb29b-137">Consulte [Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).</span><span class="sxs-lookup"><span data-stu-id="cb29b-137">See [Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).</span></span><br/><br/><span data-ttu-id="cb29b-138">Você pode usar o Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) para gerenciar o Microsoft Defender Antivírus e exclusões, bem como validar conexões entre sua rede e a nuvem.</span><span class="sxs-lookup"><span data-stu-id="cb29b-138">You can use the Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) to manage Microsoft Defender Antivirus and exclusions, as well as validate connections between your network and the cloud.</span></span> <span data-ttu-id="cb29b-139">Consulte [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe).</span><span class="sxs-lookup"><span data-stu-id="cb29b-139">See [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe).</span></span> |

## <a name="see-also"></a><span data-ttu-id="cb29b-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="cb29b-140">See also</span></span>

- [<span data-ttu-id="cb29b-141">Resolver falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="cb29b-141">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)