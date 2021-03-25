---
title: Gerenciar o Microsoft Defender para Ponto de Extremidade usando o Configuration Manager
description: Saiba como gerenciar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager
keywords: pós-migração, gerenciar, operações, manutenção, utilização, Configuration Manager, proteção avançada contra ameaças do Windows Defender, atp, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: bd6b6bd2721b686ab10922d09a9e94b9ebcce522
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185642"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Recomendamos usar o [Microsoft Endpoint Manager](https://docs.microsoft.com/mem), que inclui o Microsoft [Intune (Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e o [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) (Configuration Manager) para gerenciar os recursos de proteção contra ameaças da sua organização para dispositivos (também chamados de pontos de extremidade). 
- [Saiba mais sobre o Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Co-gerenciar o Microsoft Defender para Ponto de Extremidade em dispositivos Windows 10 com o Configuration Manager e o Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configurar o Microsoft Defender para Ponto de Extremidade com o Configuration Manager

|Tarefa  |Recursos para saber mais  |
|---------|---------|
|**Instale o console do Configuration Manager** se você ainda não o tiver<br/><br/>*Se você ainda não tiver o console do Configuration Manger, use esses recursos para obter os bits e instalá-lo.* |[Obter a mídia de instalação](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Instalar o console do Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Usar o Configuration Manager para integração de dispositivos** no Microsoft Defender para Ponto de Extremidade <br/><br/> *Se você tiver dispositivos (ou pontos de extremidade) ainda não conectados ao Microsoft Defender para Ponto de Extremidade, poderá fazer isso com o Configuration Manager.*   |[Integração ao Microsoft Defender para Ponto de Extremidade com o Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Gerenciar políticas antimalware e segurança do Firewall do Windows** para computadores cliente (pontos de extremidade)<br/><br/>*Configure os recursos de proteção de ponto de extremidade, incluindo o Microsoft Defender para Ponto de Extremidade, proteção de exploração, controle de aplicativos, antimalware, configurações de firewall e muito mais.*  |[Gerenciador de Configurações: Proteção do Ponto de Extremidade](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Escolher métodos para atualizar atualizações de antimalware nos dispositivos** da sua organização <br/><br/>*Com a Proteção de Ponto de Extremidade no Configuration Manager, você pode escolher entre vários métodos para manter as definições antimalware atualizadas nos dispositivos da sua organização.* |[Configurar atualizações de definição para a Proteção do Ponto de Extremidade](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Usar o Configuration Manager para fornecer atualizações de definição](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Habilitar a Proteção** de Rede para ajudar a impedir que os funcionários usem aplicativos com conteúdo mal-intencionado na Internet <br/><br/>*É recomendável usar [o modo de](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) auditoria primeiro para proteção de rede em um ambiente de teste para ver quais aplicativos seriam bloqueados antes de ser implantada.* |[Ativar a proteção de rede com o Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Configurar o acesso controlado a pastas** para proteger contra ransomware <br/><br/>*O acesso controlado a pastas também é conhecido como proteção antiransomware.*   |[Proteção de ponto de extremidade: Acesso controlado a pastas](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Habilitar o acesso controlado a pastas no Microsoft Endpoint Configuration Manage](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurar seu Centro de Segurança do Microsoft Defender

Se você ainda não fez isso, configure o Centro de Segurança do **Microsoft Defender** ( ) para exibir alertas, configurar recursos de proteção contra ameaças e exibir informações detalhadas sobre a postura geral de segurança da sua [https://securitycenter.windows.com](https://securitycenter.windows.com) organização. 

Você também pode configurar se e quais recursos os usuários finais podem ver no Centro de Segurança do Microsoft Defender.

- [Visão geral do Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Proteção de ponto de extremidade: Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Próximas etapas

- [Obter uma visão geral do gerenciamento de ameaças e vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite o painel de operações de segurança do Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune](manage-atp-post-migration-intune.md)
