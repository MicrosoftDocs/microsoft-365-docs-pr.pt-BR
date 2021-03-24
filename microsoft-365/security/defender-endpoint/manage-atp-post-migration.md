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
ms.openlocfilehash: fbc0abdb9def860df7e553963d7fa3c7f5b5da24
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053919"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade, pós-migração

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Depois de ter movido da sua solução antivírus e proteção de ponto de extremidade anterior para o Microsoft Defender para Ponto de Extremidade, a próxima etapa é gerenciar seus recursos e recursos. Recomendamos usar [o Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview), que inclui o Microsoft [Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e o [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction), para gerenciar os dispositivos e as configurações de segurança da sua organização. No entanto, você pode usar outras ferramentas/métodos, como Objetos de Política de Grupo nos Serviços de Domínio do [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy) 

A tabela a seguir lista várias ferramentas/métodos que você pode usar, com links para saber mais. 
<br/><br/>

|Ferramenta/Método  |Descrição  |
|---------|---------|
|**[Insights do painel de gerenciamento de ameaças e vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** no Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |O painel & gerenciamento de vulnerabilidades fornece informações ativos que sua equipe de operações de segurança pode usar para reduzir a exposição e melhorar a postura de segurança da sua organização. <br/><br/>Consulte [Gerenciamento & de vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) e Visão geral do Centro de Segurança do Microsoft [Defender.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)  |
|**[Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)**  (recomendado)    |O Microsoft Intune (Intune), um componente do [Microsoft Endpoint Manager,](https://docs.microsoft.com/mem/endpoint-manager-overview)se concentra no gerenciamento de dispositivo móvel (MDM) e no gerenciamento de aplicativos móveis (MAM). Com o Intune, você controla como os dispositivos da sua organização são usados, incluindo telefones celulares, tablets e laptops. Você também pode configurar políticas específicas para controlar aplicativos. <br/><br/>Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade usando o Intune](manage-atp-post-migration-intune.md).         |
|**[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction)**     |O Microsoft Endpoint Manager (Configuration Manager), anteriormente conhecido como System Center Configuration Manager, é um componente do [Microsoft Endpoint Manager.](https://docs.microsoft.com/mem/endpoint-manager-overview) O Configuration Manager é uma ferramenta poderosa para gerenciar seus usuários, dispositivos e software.<br/><br/>Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager](manage-atp-post-migration-configuration-manager.md).        |
|**[Objetos de Política de Grupo nos Serviços de Domínio do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)** |[Os Serviços de Domínio do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/overview) incluem Objetos de Política de Grupo integrados para usuários e dispositivos. Você pode personalizar os Objetos de Política de Grupo integrados conforme necessário para seu ambiente, bem como criar objetos de política de grupo personalizados e unidades organizacionais (OUs). <br/><br/>Consulte [Gerenciar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo.](manage-atp-post-migration-group-policy-objects.md) |
|**[PowerShell, WMI e MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Recomendamos usar o Microsoft Endpoint Manager (que inclui o Intune e o Configuration Manager) para gerenciar recursos de proteção contra ameaças nos dispositivos da sua organização. No entanto, você pode configurar algumas configurações, como as configurações do Microsoft Defender Antivírus em dispositivos individuais (pontos de extremidade) com PowerShell, WMI ou a ferramenta MPCmdRun.exe.*<br/><br/>Você pode usar o PowerShell para gerenciar o Microsoft Defender Antivírus, explorar a proteção e suas regras de redução de superfície de ataque. Consulte [Configure Microsoft Defender for Endpoint with PowerShell](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell).<br/><br/>Você pode usar a Instrumentação de Gerenciamento do Windows (WMI) para gerenciar o Microsoft Defender Antivírus e as exclusões. Consulte [Configure Microsoft Defender for Endpoint with WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).<br/><br/>Você pode usar o Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) para gerenciar o Microsoft Defender Antivírus e exclusões, bem como validar conexões entre sua rede e a nuvem. Consulte [Configure Microsoft Defender for Endpoint with MPCmdRun.exe](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe). |

## <a name="see-also"></a>Confira também

- [Resolver falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)
