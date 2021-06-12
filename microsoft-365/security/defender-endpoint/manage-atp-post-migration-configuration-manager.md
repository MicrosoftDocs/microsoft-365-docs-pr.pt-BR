---
title: Gerenciar o Microsoft Defender para Ponto de Extremidade usando o Configuration Manager
description: Saiba como gerenciar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager
keywords: pós-migração, gerenciar, operações, manutenção, utilização, Configuration Manager, Microsoft Defender para Endpoint, edr
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
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: 5fde3bfad69a5851dd94b76afb262f8be12d0360
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908252"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Recomendamos o uso do [Microsoft Endpoint Manager](/mem), que inclui o [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) e [o Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) para gerenciar os recursos de proteção contra ameaças da sua organização para dispositivos (também chamados de pontos de extremidade). 
- [Saiba mais sobre Endpoint Manager](/mem/endpoint-manager-overview)
- [Co-gerenciar o Microsoft Defender para Ponto de Extremidade em Windows 10 dispositivos com o Configuration Manager e o Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configurar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager

|Tarefa  |Recursos para saber mais  |
|---------|---------|
|**Instale o console do Configuration Manager** se você ainda não o tiver<br/><br/>*Se você ainda não tiver o console do Configuration Manger, use esses recursos para obter os bits e instalá-lo.* |[Obter a mídia de instalação](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Instalar o console do Configuration Manager](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Usar o Configuration Manager para integração de dispositivos** no Microsoft Defender para Ponto de Extremidade <br/><br/> *Se você tiver dispositivos (ou pontos de extremidade) ainda não conectados ao Microsoft Defender para Ponto de Extremidade, poderá fazer isso com o Configuration Manager.*   |[Integração ao Microsoft Defender para Ponto de Extremidade com o Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Gerenciar políticas antimalware e Windows segurança do Firewall** para computadores cliente (pontos de extremidade)<br/><br/>*Configure os recursos de proteção de ponto de extremidade, incluindo o Microsoft Defender para Ponto de Extremidade, proteção de exploração, controle de aplicativos, antimalware, configurações de firewall e muito mais.*  |[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Escolher métodos para atualizar atualizações de antimalware nos dispositivos** da sua organização <br/><br/>*Com Endpoint Protection no Configuration Manager, você pode escolher entre vários métodos para manter as definições antimalware atualizadas nos dispositivos da sua organização.* |[Configurar atualizações de definição para Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Usar o Configuration Manager para fornecer atualizações de definição](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Habilitar a Proteção** de Rede para ajudar a impedir que os funcionários usem aplicativos com conteúdo mal-intencionado na Internet <br/><br/>*É recomendável usar [o modo de](/microsoft-365/security/defender-endpoint/evaluate-network-protection) auditoria primeiro para proteção de rede em um ambiente de teste para ver quais aplicativos seriam bloqueados antes de ser implantada.* |[Ativar a proteção de rede com o Configuration Manager](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Configurar o acesso controlado a pastas** para proteger contra ransomware <br/><br/>*O acesso controlado a pastas também é conhecido como proteção antiransomware.*   |[Proteção de ponto de extremidade: Acesso controlado a pastas](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Habilitar o acesso controlado a pastas no Microsoft Endpoint Configuration Manage](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configure seu Central de Segurança do Microsoft Defender

Se você ainda não fez isso, configure seu portal do Microsoft 365 Defender para exibir alertas, configurar recursos de proteção contra ameaças e exibir informações detalhadas sobre a postura geral de segurança da sua organização. Consulte [Central de Segurança do Microsoft Defender](microsoft-defender-security-center.md). Você também pode configurar se e quais recursos os usuários finais podem ver no portal Microsoft 365 Defender.

- [Visão geral do Central de Segurança do Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Proteção de ponto de extremidade: Central de Segurança do Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Próximas etapas

- [Obter uma visão geral do Gerenciamento de Ameaças e Vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite o painel de Central de Segurança do Microsoft Defender de operações de segurança](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune](manage-atp-post-migration-intune.md)
