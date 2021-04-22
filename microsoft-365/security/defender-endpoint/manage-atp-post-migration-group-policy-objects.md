---
title: Gerenciar o Microsoft Defender para Ponto de Extremidade usando Objetos de Política de Grupo
description: Saiba como gerenciar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo
keywords: pós-migração, gerenciar, operações, manutenção, utilização, PowerShell, Microsoft Defender para Endpoint, edr
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
ms.openlocfilehash: 1b8f2e7c7435f2161f7261722795b35ca848ec2f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934232"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Recomendamos usar [o Microsoft Endpoint Manager](https://docs.microsoft.com/mem) para gerenciar os recursos de proteção contra ameaças da sua organização para dispositivos (também chamados de pontos de extremidade). O Endpoint Manager inclui [o Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) e [o Microsoft Endpoint Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) **[Saiba mais sobre o Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview)**. 

Você pode usar Objetos de Política de Grupo nos Serviços de Domínio do Azure Active Directory para gerenciar algumas configurações no Microsoft Defender para Ponto de Extremidade.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Configurar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo

A tabela a seguir lista várias tarefas que você pode executar para configurar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo.

|Tarefas  |Recursos para saber mais  |
|---------|---------|
|**Gerenciar configurações para objetos de usuário e computador** <br/><br/>*Personalize objetos de Política de Grupo integrados ou crie objetos de política de grupo personalizados e unidades organizacionais para atender às suas necessidades organizacionais.*     |[Administrar a Política de Grupo em um domínio gerenciado dos Serviços de Domínio do Azure Active Directory](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**Configurar o Microsoft Defender Antivírus** <br/><br/>*Configure recursos antivírus & recursos, incluindo configurações de política, exclusões, correção e verificações agendadas nos dispositivos da sua organização (também chamados de pontos de extremidade).*   |[Usar configurações de Política de Grupo para configurar e gerenciar o Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Usar a Política de Grupo para habilitar a proteção entregue na nuvem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Gerenciar as regras de redução de superfície de ataque da sua organização** <br/><br/>*Personalize suas regras de redução de superfície de ataque excluindo arquivos & pastas ou adicionando texto personalizado a alertas de notificação que aparecem nos dispositivos dos usuários.* |[Personalizar regras de redução de superfície de ataque com objetos de política de grupo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Gerenciar configurações de proteção de exploração**<br/><br/>*Você pode personalizar suas configurações de proteção de exploração, importar um arquivo de configuração e, em seguida, usar a Política de Grupo para implantar esse arquivo de configuração.*  |[Personalizar configurações de proteção de exploração](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Importar, exportar e implantar configurações da proteção de exploração](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Usar a Política de Grupo para distribuir a configuração](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Habilitar a Proteção** de Rede para ajudar a impedir que os funcionários usem aplicativos com conteúdo mal-intencionado na Internet <br/><br/>*É recomendável usar [o modo de](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) auditoria primeiro para proteção de rede em um ambiente de teste para ver quais aplicativos seriam bloqueados antes de ser implantada.* |[Ativar a proteção de rede usando a Política de Grupo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Configurar o acesso controlado a pastas** para proteger contra ransomware <br/><br/>*[O acesso controlado a](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) pastas também é conhecido como proteção antiransomware.*  |[Habilitar o acesso controlado a pastas usando a Política de Grupo](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Configure o Microsoft Defender SmartScreen** para proteger contra sites e arquivos mal-intencionados na Internet.  |[Configurar configurações de Política de Grupo do Microsoft Defender SmartScreen e gerenciamento de dispositivo móvel (MDM) usando a Política de Grupo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Configurar a criptografia e o BitLocker** para proteger informações sobre os dispositivos da sua organização que executam o Windows |[Configurações da Política de Grupo do BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Configurar o Microsoft Defender Credential Guard** para proteger contra ataques de roubo de credenciais |[Habilitar Windows Defender Credential Guard usando a Política de Grupo](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configurar seu Centro de Segurança do Microsoft Defender

Se você ainda não fez isso, configure o Centro de Segurança do **Microsoft Defender** ( ) para exibir alertas, configurar recursos de proteção contra ameaças e exibir informações detalhadas sobre a postura geral de segurança da sua [https://securitycenter.windows.com](https://securitycenter.windows.com) organização. 

Você também pode configurar se e quais recursos os usuários finais podem ver no Centro de Segurança do Microsoft Defender.

- [Visão geral do Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Proteção de ponto de extremidade: Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Próximas etapas

- [Obter uma visão geral do gerenciamento de ameaças e vulnerabilidades](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite o painel de operações de segurança do Centro de Segurança do Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune](manage-atp-post-migration-intune.md)
