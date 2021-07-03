---
title: Gerenciar o Microsoft Defender para Ponto de Extremidade usando PowerShell, WMI e MPCmdRun.exe
description: Saiba como gerenciar o Microsoft Defender para Ponto de Extremidade com PowerShell, WMI e MPCmdRun.exe
keywords: pós-migração, gerenciar, operações, manutenção, utilização, PowerShell, WMI, MPCmdRun.exe, Microsoft Defender para Ponto de Extremidade, edr
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
ms.openlocfilehash: 063870c58377d7327f621ec49855b684065f436b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286760"
---
# <a name="manage-microsoft-defender-for-endpoint-with-powershell-wmi-and-mpcmdrunexe"></a>Gerenciar o Microsoft Defender para Ponto de Extremidade com PowerShell, WMI e MPCmdRun.exe

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> Recomendamos usar [Microsoft Endpoint Manager](/mem) para gerenciar os recursos de proteção contra ameaças da sua organização para dispositivos (também chamados de pontos de extremidade). Endpoint Manager [inclui](/mem/intune/fundamentals/what-is-intune) Microsoft Intune e [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction).
>
> - [Saiba mais sobre Endpoint Manager](/mem/endpoint-manager-overview)
> - [Co-gerenciar o Microsoft Defender para Ponto de Extremidade em Windows 10 dispositivos com o Configuration Manager e o Intune](manage-atp-post-migration-intune.md)
> - [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune](manage-atp-post-migration-intune.md)

Você pode gerenciar algumas configurações Microsoft Defender Antivírus em dispositivos com [o PowerShell](#configure-microsoft-defender-for-endpoint-with-powershell), a Instrumentação de Gerenciamento Windows (WMI) e [o](#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi) Utilitário de Linha de Comando da Proteção de Malware da [Microsoft](#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) (MPCmdRun.exe). Por exemplo, você pode gerenciar algumas Microsoft Defender Antivírus configurações. E, em alguns casos, você pode personalizar suas regras de redução de superfície de ataque e explorar configurações de proteção.

> [!IMPORTANT]
> Os recursos de proteção contra ameaças que você configura usando o PowerShell, WMI ou MCPmdRun.exe podem ser substituídos pelas configurações implantadas com o Intune ou o Configuration Manager.

## <a name="configure-microsoft-defender-for-endpoint-with-powershell"></a>Configurar o Microsoft Defender para Ponto de Extremidade com o PowerShell

Você pode usar o PowerShell para gerenciar Microsoft Defender Antivírus, explorar a proteção e suas regras de redução de superfície de ataque.

|Tarefa|Recursos para saber mais|
|---|---|
|**Gerenciar Microsoft Defender Antivírus** <p> Exibir o status da proteção antimalware, configurar preferências para verificações antivírus & atualizações e fazer outras alterações na proteção antivírus.*|[Usar cmdlets do PowerShell para configurar e gerenciar Microsoft Defender Antivírus](/windows/security/threat-protection/microsoft-defender-antivirus/use-powershell-cmdlets-microsoft-defender-antivirus) <p> [Usar cmdlets do PowerShell para habilitar a proteção entregue na nuvem](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-powershell-cmdlets-to-enable-cloud-delivered-protection)|
|**Configurar a proteção de exploração** para mitigar ameaças nos dispositivos da sua organização <p> *Recomendamos usar a proteção de exploração [no modo de auditoria](/microsoft-365/security/defender-endpoint/evaluate-exploit-protection#powershell) no início. Dessa forma, você pode ver como a proteção de exploração afeta aplicativos que sua organização está usando.*|[Personalizar a proteção de exploração](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <p> [Cmdlets do PowerShell para proteção de exploração](/microsoft-365/security/defender-endpoint/customize-exploit-protection#powershell-reference)|
|**Configurar regras de redução de superfície de ataque** com o PowerShell <p> *Você pode usar o PowerShell para excluir arquivos e pastas de regras de redução de superfície de ataque.*|[Personalizar regras de redução de superfície de ataque: use o PowerShell para excluir arquivos & pastas](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-powershell-to-exclude-files-and-folders) <p> Além disso, consulte [António Vasconcelo's graphic user interface tool for setting attack surface reduction rules with PowerShell](https://github.com/anvascon/MDATP_PoSh_Scripts/tree/master/ASR%20GUI).|
|**Habilitar a Proteção de Rede** com o PowerShell <p> *Você pode usar o PowerShell para habilitar a Proteção de Rede.*|[Ativar a Proteção de Rede com o PowerShell](/microsoft-365/security/defender-endpoint/enable-network-protection#powershell)|
|**Configurar o acesso controlado a pastas** para proteger contra ransomware <p> *[O acesso controlado a](/microsoft-365/security/defender-endpoint/controlled-folders) pastas também é conhecido como proteção antiransomware.*|[Habilitar o acesso controlado a pastas com o PowerShell](/microsoft-365/security/defender-endpoint/enable-controlled-folders#powershell)|
|**Configurar o Microsoft Defender Firewall** para bloquear o tráfego de rede não autorizado fluindo para dentro ou para fora dos dispositivos da sua organização|[Microsoft Defender Firewall com Administração de Segurança Avançada usando Windows PowerShell](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-administration-with-windows-powershell)|
|**Configure a criptografia e o BitLocker** para proteger informações sobre os dispositivos da sua organização que executam Windows|[Guia de referência do BitLocker PowerShell](/powershell/module/bitlocker/)|

## <a name="configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi"></a>Configurar o Microsoft Defender para Ponto de Extremidade com Windows Instrumentação de Gerenciamento (WMI)

WMI é uma interface de script que permite recuperar, modificar e atualizar configurações. Para saber mais, consulte [Using WMI](/windows/win32/wmisdk/using-wmi).

|Tarefa|Recursos para saber mais|
|---|---|
|**Habilitar a proteção entregue na nuvem** em um dispositivo|[Use Windows Instrução de Gerenciamento (WMI) para habilitar a proteção entregue na nuvem](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-windows-management-instruction-wmi-to-enable-cloud-delivered-protection)|
|**Recuperar, modificar e atualizar configurações** para Microsoft Defender Antivírus|[Use o WMI para configurar e gerenciar Microsoft Defender Antivírus] (/windows/security/threat-protection/microsoft-defender-antivírus/use-wmi-microsoft-defender-antivírus <p> [Revise a lista de classes WMI disponíveis e scripts de exemplo](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) <p> Consulte também as informações de referência do [Windows Defender WMIv2 Provider](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal?redirectedfrom=MSDN)|

## <a name="configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe"></a>Configurar o Microsoft Defender para Ponto de Extremidade com o Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe)

Em um dispositivo individual, você pode executar uma verificação, iniciar o rastreamento de diagnóstico, verificar se há atualizações de inteligência de segurança e muito mais usando a ferramenta mpcmdrun.exe linha de comando. Você pode encontrar o utilitário em `%ProgramFiles%\Windows Defender\MpCmdRun.exe` . Execute-o de um prompt de comando.

|Tarefa|Recursos para saber mais|
|---|---|
|**Gerenciar Microsoft Defender Antivírus**|[Configurar e gerenciar Microsoft Defender Antivírus com mpcmdrun.exe](/windows/security/threat-protection/microsoft-defender-antivirus/command-line-arguments-microsoft-defender-antivirus)|

## <a name="configure-your-microsoft-defender-security-center"></a>Configure seu Central de Segurança do Microsoft Defender

Se você ainda não fez **isso,** configure seu Central de Segurança do Microsoft Defender ( ) para exibir alertas, configurar recursos de proteção contra ameaças e exibir informações detalhadas sobre a postura geral de segurança da [https://securitycenter.windows.com](https://securitycenter.windows.com) sua organização.

Você também pode configurar se e quais recursos os usuários finais podem ver no Central de Segurança do Microsoft Defender.

- [Visão geral do Central de Segurança do Microsoft Defender](/microsoft-365/security/defender-endpoint/use)

- [Proteção de ponto de extremidade: Central de Segurança do Microsoft Defender](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Próximas etapas

- [Obtenha uma visão geral do gerenciamento de ameaças e vulnerabilidades](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Visite o painel de Central de Segurança do Microsoft Defender de operações de segurança](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Gerenciar o Microsoft Defender para Ponto de Extremidade com o Intune](manage-atp-post-migration-intune.md)
