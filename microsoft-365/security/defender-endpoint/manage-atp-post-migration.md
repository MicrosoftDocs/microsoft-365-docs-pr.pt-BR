---
title: Gerenciar a migração pós-migração do Microsoft Defender para Ponto de Extremidade
description: Agora que você alternou para o Microsoft Defender para Ponto de Extremidade, sua próxima etapa é gerenciar seus recursos de proteção contra ameaças
keywords: pós-migração, gerenciar, operações, manutenção, utilização, Microsoft Defender para Ponto de Extremidade, edr
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
ms.openlocfilehash: ea5e4cb1c4a93f5f8bd5da1c0c94b095d03ac680
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845613"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade, pós-migração

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Depois de ter movido da sua solução antivírus e proteção de ponto de extremidade anterior para o Microsoft Defender para Ponto de Extremidade, a próxima etapa é gerenciar seus recursos e recursos. Recomendamos usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), que [](/mem/intune/fundamentals/what-is-intune) inclui Microsoft Intune e [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction), para gerenciar os dispositivos e configurações de segurança da sua organização. No entanto, você pode usar outras ferramentas/métodos, como Objetos de Política de [Grupo Azure Active Directory Serviços de Domínio.](/azure/active-directory-domain-services/manage-group-policy) 

A tabela a seguir lista várias ferramentas/métodos que você pode usar, com links para saber mais. 
<br/><br/>

|Ferramenta/Método  |Descrição  |
|---------|---------|
|**[Ameaças e Gerenciamento de Vulnerabilidades de painel](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** no Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |O painel & Gerenciamento de Vulnerabilidades de ameaças fornece informações a actionable que sua equipe de operações de segurança pode usar para reduzir a exposição e melhorar a postura de segurança da sua organização. <br/><br/>Consulte [Threat & Gerenciamento de Vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) and Overview of the [Central de Segurança do Microsoft Defender](/microsoft-365/security/defender-endpoint/use).  |
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (recomendado)    |Microsoft Intune (Intune), um componente do [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), concentra-se no gerenciamento de dispositivo móvel (MDM) e no gerenciamento de aplicativos móveis (MAM). Com o Intune, você controla como os dispositivos da sua organização são usados, incluindo telefones celulares, tablets e laptops. Você também pode configurar políticas específicas para controlar aplicativos. <br/><br/>Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade usando o Intune](manage-atp-post-migration-intune.md).         |
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), anteriormente conhecido como System Center Configuration Manager, é um componente [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). O Configuration Manager é uma ferramenta poderosa para gerenciar seus usuários, dispositivos e software.<br/><br/>Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager](manage-atp-post-migration-configuration-manager.md).        |
|**[Objetos de Política de Grupo Azure Active Directory Serviços de Domínio](/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory Serviços de Domínio](/azure/active-directory-domain-services/overview) inclui Objetos de Política de Grupo integrados para usuários e dispositivos. Você pode personalizar os Objetos de Política de Grupo integrados conforme necessário para seu ambiente, bem como criar objetos de política de grupo personalizados e unidades organizacionais (OUs). <br/><br/>Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo.](manage-atp-post-migration-group-policy-objects.md) |
|**[PowerShell, WMI e MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Recomendamos usar Microsoft Endpoint Manager (que inclui o Intune e o Configuration Manager) para gerenciar recursos de proteção contra ameaças nos dispositivos da sua organização. No entanto, você pode configurar algumas configurações, como Microsoft Defender Antivírus configurações em dispositivos individuais (pontos de extremidade) com PowerShell, WMI ou a ferramenta MPCmdRun.exe.*<br/><br/>Você pode usar o PowerShell para gerenciar Microsoft Defender Antivírus, explorar a proteção e suas regras de redução de superfície de ataque. Consulte [Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).<br/><br/>Você pode usar Windows Instrumentação de Gerenciamento (WMI) para gerenciar Microsoft Defender Antivírus e exclusões. Consulte [Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).<br/><br/>Você pode usar o Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) para gerenciar Microsoft Defender Antivírus e exclusões, bem como validar conexões entre sua rede e a nuvem. Consulte [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe). |

## <a name="see-also"></a>Confira também

- [Endereços falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)
