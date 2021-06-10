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
ms.openlocfilehash: 15902e02156c59ec4edaed94f4ba321094bd42ac
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843017"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Recomendamos usar [Microsoft Endpoint Manager](/mem) para gerenciar os recursos de proteção contra ameaças da sua organização para dispositivos (também chamados de pontos de extremidade). Endpoint Manager [inclui](/mem/intune/fundamentals/what-is-intune) Microsoft Intune e [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction). **[Saiba mais sobre Endpoint Manager](/mem/endpoint-manager-overview)**. 

Você pode usar Objetos de Política de Grupo Azure Active Directory Serviços de Domínio para gerenciar algumas configurações no Microsoft Defender para Ponto de Extremidade.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Configurar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo

A tabela a seguir lista várias tarefas que você pode executar para configurar o Microsoft Defender para Ponto de Extremidade com Objetos de Política de Grupo.

|Tarefa  |Recursos para saber mais  |
|---------|---------|
|**Gerenciar configurações para objetos de usuário e computador** <br/><br/>*Personalize objetos de Política de Grupo integrados ou crie objetos de política de grupo personalizados e unidades organizacionais para atender às suas necessidades organizacionais.*     |[Administrar a Política de Grupo em um domínio gerenciado Azure Active Directory Serviços de Domínio](/azure/active-directory-domain-services/manage-group-policy)   |
|**Configurar Microsoft Defender Antivírus** <br/><br/>*Configure recursos antivírus & recursos, incluindo configurações de política, exclusões, correção e verificações agendadas nos dispositivos da sua organização (também chamados de pontos de extremidade).*   |[Use as configurações da Política de Grupo para configurar e gerenciar Microsoft Defender Antivírus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Usar a Política de Grupo para habilitar a proteção entregue na nuvem](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**Gerenciar as regras de redução de superfície de ataque da sua organização** <br/><br/>*Personalize suas regras de redução de superfície de ataque excluindo arquivos & pastas ou adicionando texto personalizado a alertas de notificação que aparecem nos dispositivos dos usuários.* |[Personalizar regras de redução de superfície de ataque com objetos de política de grupo](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Gerenciar configurações de proteção de exploração**<br/><br/>*Você pode personalizar suas configurações de proteção de exploração, importar um arquivo de configuração e, em seguida, usar a Política de Grupo para implantar esse arquivo de configuração.*  |[Personalizar configurações de proteção de exploração](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Importar, exportar e implantar configurações da proteção de exploração](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Usar a Política de Grupo para distribuir a configuração](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Habilitar a Proteção** de Rede para ajudar a impedir que os funcionários usem aplicativos com conteúdo mal-intencionado na Internet <br/><br/>*É recomendável usar [o modo de](/microsoft-365/security/defender-endpoint/evaluate-network-protection) auditoria primeiro para proteção de rede em um ambiente de teste para ver quais aplicativos seriam bloqueados antes de ser implantada.* |[Ativar a proteção de rede usando a Política de Grupo](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Configurar o acesso controlado a pastas** para proteger contra ransomware <br/><br/>*[O acesso controlado a](/microsoft-365/security/defender-endpoint/controlled-folders) pastas também é conhecido como proteção antiransomware.*  |[Habilitar o acesso controlado a pastas usando a Política de Grupo](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Configure Microsoft Defender SmartScreen** proteção contra sites mal-intencionados e arquivos na Internet.  |[Configurar Microsoft Defender SmartScreen política de grupo e configurações de gerenciamento de dispositivo móvel (MDM) usando a Política de Grupo](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Configure a criptografia e BitLocker** para proteger informações sobre os dispositivos da sua organização que executam Windows |[BitLocker Configurações da Política de Grupo](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Configurar o Microsoft Defender Credential Guard** para proteger contra ataques de roubo de credenciais |[Habilitar Windows Defender Credential Guard usando a Política de Grupo](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Configure seu Central de Segurança do Microsoft Defender

Se você ainda não fez **isso,** configure seu Central de Segurança do Microsoft Defender ( ) para exibir alertas, configurar recursos de proteção contra ameaças e exibir informações detalhadas sobre a postura geral de segurança da [https://securitycenter.windows.com](https://securitycenter.windows.com) sua organização. 

Você também pode configurar se e quais recursos os usuários finais podem ver no Central de Segurança do Microsoft Defender.

- [Visão geral do Central de Segurança do Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Proteção de ponto de extremidade: Central de Segurança do Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Próximas etapas

- [Obter uma visão geral do Gerenciamento de Ameaças e Vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite o painel de Central de Segurança do Microsoft Defender de operações de segurança](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune](manage-atp-post-migration-intune.md)
